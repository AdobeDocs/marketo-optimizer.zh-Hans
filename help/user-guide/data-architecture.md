---
title: 数据架构
description: 了解Marketo Optimizer和Marketo Engage如何共享数据，包括实体同步方向和延迟、活动数据流和基于沙盒的数据隔离。
role: User, Admin
autotag-review: '2026-10-01T18:40:38.362Z'
TQID: 'https://experienceleague.adobe.com/oelEtys81g6TzM8bi-qy1nuWw6scOBry7tbZkMkZ6u0'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 3c1de303-7a7c-59a6-abca-8c534730e19c
    internal-label: Reporting
  - id: 3cf5f37e-e87e-5179-812b-53ce05d7eebb
    internal-label: Setup
  - id: 46e599c6-e20f-5f67-9824-93415016f66b
    internal-label: Audiences
  - id: 64b90904-e4f0-5c1b-a871-8c6a40b204a1
    internal-label: Journeys
  - id: d4203578-d294-5145-b397-f26f4488a904
    internal-label: Channels
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
source-git-commit: 518a807aeed2471772b4f0a4d6d8d525cd3e22fd
workflow-type: tm+mt
source-wordcount: '771'
ht-degree: 1%
---

# 数据架构

[!DNL Adobe Marketo Optimizer]与[!DNL Adobe Marketo Engage]集成以提供B2B潜在客户的全面视图。 双向可信同步可保持两个产品保持一致，以便它们共享人员、公司、自定义对象和活动的单一视图。 [!DNL Marketo Engage]仍然是人员数据的权威来源。 每个[!DNL Marketo Optimizer]实例都与一个[!DNL Marketo Engage]实例配对。

## 数据基础 {#data-foundation}

[!DNL Marketo Optimizer]和[!DNL Marketo Engage]共享一个共同的数据基础，该基础在馈送下游分析时保持它们同步。

![Marketo Optimizer和Marketo Engage架构图，显示这两个产品的服务、运行时和数据存储如何跨Microsoft Azure和AWS进行连接](./assets/marketo-optimizer-architecture.svg)

在高级别上：

* **[!DNL Marketo Engage]**&#x200B;是潜在客户和自定义对象数据的确定源，它可确保捕获点的数据完整性。
* **数据代理层**&#x200B;协调数据在两个产品之间的移动方式。 它将共享和复制的数据聚合到一个随时可用的操作数据库中。 整个Exchange在一个Aurora MySQL集群中运行。
* **[!DNL Marketo Optimizer]**&#x200B;是其运行的历程活动的权威来源。

## 实体同步 {#entity-sync}

每个实体类型都按照最能保护数据完整性的方向和速度进行同步。

| [!DNL Marketo Engage]实体 | 同步方向 | 延迟 |
| --- | --- | --- |
| 潜在客户 | 双向 | 1秒以下 |
| 公司 | 双向 | 1秒以下 |
| 自定义对象 | 单向 | 少于5秒 |
| 活动 | 单向 | 少于5秒 |
| 计划会员资格 | 未同步 | 不适用 |
| 资产 | 未同步 | 不适用 |

同步的工作方式有两种：

* **潜在客户、公司和标准对象：** [!DNL Marketo Engage]拥有人员表并通过读写数据库视图共享它。 一个产品中的更新会立即出现在另一个产品中，并且不会创建重复的副本。
* **自定义对象：**&#x200B;数据在秒内从[!DNL Marketo Engage]复制。 [!DNL Marketo Engage]中的架构更新对活动历程立即可用。

[!DNL Marketo Engage]和[!DNL Marketo Optimizer]不同步项目成员资格或资源。 此排除项可保持系统速度和完整性。

>[!NOTE]
>
>同步到[!DNL Marketo Optimizer]的数据和同步到数据仓库的数据最终是一致的。 计时取决于底层变更数据捕获、批处理或流机制。

这种近乎实时的设计可为您提供历程和报告中的当前数据。 您可以快速跟进高优先级的潜在客户。 您还可以在历程决策中随着其更改使用B2B上下文数据，如产品使用和意图。

## 活动数据流 {#activity-flow}

活动遵循与其他实体不同的路径。 每个活动会经历五个阶段：

1. **主捕获：** [!DNL Marketo Engage]将活动写入其共享数据库，并在Apache SOLR中对其进行索引以在[!DNL Marketo Engage]内进行快速搜索。
1. **跨产品识别：** [!DNL Marketo Engage]将该活动发布到活动管道，因此[!DNL Marketo Optimizer]立即收到该活动。
1. **分析转换：**&#x200B;历程运行时处理该活动并将其写入Snowflake，这将操作数据转换为分析就绪的数据。 Amazon Web Services (AWS)中目前运行的所有阶段。
1. **下游目标：** [!DNL Marketo Optimizer]将该活动复制到[!DNL Adobe Experience Platform]个数据集中。
1. **报告：**&#x200B;数据集馈送嵌入了[!DNL Adobe Customer Journey Analytics]报告。 [!DNL Customer Journey Analytics]可以托管在Microsoft Azure或AWS上。 您还可以使用[!DNL Query Service]查询数据集。 查看[Experience Platform数据集](./reports/aep-datasets.md)。

历程和事件受众可以同时使用[!DNL Marketo Optimizer]个活动和[!DNL Marketo Engage]个活动的子集。 以相同的方式使用两个集。 [!DNL Marketo Optimizer]活动未发送回[!DNL Marketo Engage]。

使用表单填充、Web访问和电子邮件参与度等活动来触发、过滤和分支人员历程：

* [侦听事件节点的事件触发器](./marketing/listen-for-event-nodes.md#event-triggers)
* [侦听事件节点的事件过滤器](./marketing/listen-for-event-nodes.md#event-filters)
* [拆分路径节点的匹配人员过滤器](./marketing/split-merge-paths-nodes.md#matched-person-filters)
* [基于事件的受众](./audiences/event-based-audiences.md)

## 数据隔离和沙盒 {#data-isolation}

[!DNL Marketo Engage]、[!DNL Marketo Optimizer]和[!DNL Experience Platform]在此架构中共享客户数据。 Adobe使用[!DNL Experience Platform]沙盒从逻辑上将您的数据与其他租户隔离。 数据通过安全、加密的通道移动。 Adobe将其存储在Adobe Managed Services中，并带有行业标准的加密和访问控制。

每个[!DNL Marketo Optimizer]实例在[!DNL Adobe Admin Console]中都有一个专用产品卡和一个专用沙盒。 Adobe会自动配置这两个项目，因此您不会创建沙盒。 沙盒名称使用模式`mktoaep<prefix>`，其中前缀是您的[!DNL Marketo Engage]前缀。 如果您将[!DNL Marketo Optimizer]与多个[!DNL Marketo Engage]实例一起使用，则每个实例都有自己的产品卡和沙盒。

[!DNL Marketo Optimizer]仅在此沙盒中可用，即使您的组织具有其他沙盒也是如此。

配置不分配沙盒访问权限。 角色通常有权访问默认的`prod`沙盒，但[!DNL Marketo Optimizer]不使用它。 将专用沙盒显式分配给每个[!DNL Experience Platform]角色，否则用户无法在[!DNL Marketo Optimizer]中工作。 使用用户组添加和删除用户，而无需重复角色设置。 有关完整过程，请参阅[用户访问和权限](./start/user-management.md)。

[!DNL Marketo Optimizer]还在后台使用[!DNL Experience Platform]服务。 这些资源包括架构注册表、付费媒体导出的目标、访问控制和[!DNL Customer Journey Analytics]。 您未设置架构或命名空间。 [!DNL Marketo Optimizer]不需要[!DNL Real-Time Customer Data Platform]、实时客户资料或分段。

>[!WARNING]
>
>请勿删除专用的[!DNL Marketo Optimizer]沙盒。 删除是永久性的，无法撤消。 重新配置[!DNL Marketo Optimizer]以进行恢复。
