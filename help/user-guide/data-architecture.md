---
title: 高级体系结构
description: 了解连接Marketo Optimizer和Marketo Engage的数据架构，包括双向同步、实体延迟和租户数据隔离。
role: User, Admin
source-git-commit: ef30aa7a901c18c7b9b0919d537ad59db9a6c481
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 1%

---


# 高层架构

[!DNL Adobe Marketo Optimizer]与[!DNL Adobe Marketo Engage]集成以提供B2B潜在客户的360度视图。 双向的受信任同步可保持[!DNL Marketo Engage]和[!DNL Marketo Optimizer]一致，从而为两个平台提供人员、公司、自定义对象和活动的单个共享视图。 高性能、近乎实时的数据流可确保记录保持最新状态并可供操作，以便营销活动和历程能够在客户参与时响应潜在客户。

## 数据基础

[!DNL Marketo Optimizer]和[!DNL Marketo Engage]共享一个共同的数据基础，该基础在馈送下游分析时保持它们同步。

![Marketo Optimizer和Marketo Engage架构图，其中显示了这两种产品的服务、运行时和数据存储如何跨Microsoft Azure和AWS进行连接](./assets/marketo-optimizer-architecture.svg)

在高级别上：

* **[!DNL Marketo Engage]Core**&#x200B;是潜在客户和自定义对象数据的确定源，确保捕获点的数据完整性。
* **数据代理层**&#x200B;协调数据在[!DNL Marketo Engage]和[!DNL Marketo Optimizer]之间的移动方式，将共享和复制的数据聚合到可操作、随时可用的环境中。 此整个交换在单个共享AWS Aurora实例中运行，从而构成了高规模B2B编排的闭环基础。
* **活动**&#x200B;遵循定义的路径：首先将这些活动写入[!DNL Marketo Engage]数据库并在Apache SOLR中编制索引以便快速进行产品内搜索，然后将其发布到活动管道，以便[!DNL Marketo Optimizer]具有即时感知功能。 历程运行时会处理该活动并将其写入Snowflake，从而将运营数据转换为分析就绪状态。 从该位置，活动被复制到[!DNL Adobe Experience Platform]个数据集和[!DNL Adobe Customer Journey Analytics]中，以便进行报告。
* 不同的实体类型以不同的速度和方向进行同步，以平衡新鲜度和系统完整性：

| [!DNL Marketo Engage]实体 | 同步方向 | 延迟 |
| --- | --- | --- |
| 潜在客户 | 双向 | &lt; 1秒 |
| 公司 | 双向 | &lt; 1秒 |
| 自定义对象 | 单向 | &lt; 5秒 |
| 活动 | 单向 | &lt; 5秒 |
| 计划会员资格 | 未同步 | — |
| 资产 | 未同步 | — |

潜在客户和公司可双向即时更新，而不会创建重复的数据拷贝。 自定义对象在几秒钟内复制，因此[!DNL Marketo Engage]中的架构更新可在活动历程中立即操作。 为了保持系统速度和完整性，有意将项目成员资格和Assets从同步中排除。

这种近乎零延迟的设计意味着近乎实时地提供Analytics功能板和下游系统，从而实现实时活动优化和对高优先级潜在客户的快速跟进。

### 数据隔离和租赁

* 作为产品数据同步和分析架构的一部分，客户数据在[!DNL Marketo Engage]、[!DNL Marketo Optimizer]和[!DNL Experience Platform]之间共享。
* 数据按租户进行逻辑隔离，并受Adobe安全控制的保护。
* 数据通过安全、加密的通道传输，并使用行业标准的加密和访问控制存储在Adobe托管服务中。
* 根据数据类型，信息可在[!DNL Marketo Engage]和[!DNL Marketo Optimizer]之间同步或复制到[!DNL Experience Platform]以支持报告和分析功能，同时保持安全和租户隔离。
