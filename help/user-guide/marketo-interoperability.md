---
title: 与Marketo Engage的互操作性
description: 了解Marketo Optimizer与Marketo Engage共享的内容（包括数据、活动和受众），以及如何从历程中的任一产品发送电子邮件。
role: User, Admin
autotag-review: '2026-10-01T18:40:01.444Z'
TQID: 'https://experienceleague.adobe.com/7TB6JG9yiUT-l0VevNW4tvwieCyFjOypZwI0SlUzmmY'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 3c1de303-7a7c-59a6-abca-8c534730e19c
    internal-label: Reporting
  - id: 46e599c6-e20f-5f67-9824-93415016f66b
    internal-label: Audiences
  - id: 64b90904-e4f0-5c1b-a871-8c6a40b204a1
    internal-label: Journeys
  - id: a29661b8-f7a4-53d1-a9ac-fdec08c092e4
    internal-label: Programs
  - id: d4203578-d294-5145-b397-f26f4488a904
    internal-label: Channels
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
    internal-label: Governance
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
source-git-commit: 518a807aeed2471772b4f0a4d6d8d525cd3e22fd
workflow-type: tm+mt
source-wordcount: '496'
ht-degree: 0%
---

# 与Marketo Engage的互操作性

[!DNL Adobe Marketo Optimizer]和[!DNL Adobe Marketo Engage]共享数据、某些活动和受众。 它们会将资产分开。 了解每个产品共享的内容，以决定构建和发送营销内容的位置。

## 在产品之间共享 {#shared}

* [!DNL Marketo Engage]个潜在客户和活动自动流入[!DNL Marketo Optimizer]。
* 历程可以侦听[!DNL Marketo Engage]个活动。
* 基于事件的受众可以包括执行[!DNL Marketo Engage]活动的人员。
* 历程操作可以与[!DNL Marketo Engage]交互。 您可以在[!DNL Marketo Engage]列表中添加或删除人员并请求[!DNL Marketo Engage]营销活动。
* [!UICONTROL 评分工作室]针对[!DNL Marketo Engage]和[!DNL Marketo Optimizer]活动对人进行评分。 您可以在[!DNL Marketo Engage]中使用得分。
* 两个产品都共享IP地址和子域。
* 统一的对话报告涵盖了这两种产品。

## 保持独立 {#separate}

* **Assets：**&#x200B;电子邮件、模板、项目和图像位于不同的存储库中。
* **活动：** [!DNL Marketo Optimizer]活动未共享回[!DNL Marketo Engage]。
* **字段和限制：**&#x200B;派生的[!DNL Marketo Optimizer]角色字段在[!DNL Marketo Engage]中不可用。 每款产品均单独设定通信限制。

有关同步详细信息，请参阅[实体同步](./data-architecture.md#entity-sync)。

## 从Marketo Engage发送电子邮件 {#send-from-marketo}

在[!DNL Marketo Engage]发送每封电子邮件时，使用此方法在[!DNL Marketo Optimizer]中运行历程、等待步骤和AI决策。

1. 在[!DNL Marketo Optimizer]中，构建一个包含等待步骤和AI决策的历程。
1. 对于每个发送步骤，添加&#x200B;**[!UICONTROL 请求Marketo Engage营销活动]**&#x200B;操作并选择匹配的[!DNL Marketo Engage]营销活动。
1. 可选：在[!DNL Marketo Engage]中添加一个默认的首要项目，以汇总历程中的成功报表。

有关操作详细信息，请参阅[执行操作节点](./marketing/action-nodes.md)。

[!DNL Marketo Engage]通过您现有的渠道设置发送电子邮件。 由于[!DNL Marketo Engage]发送电子邮件，因此您不会在[!DNL Marketo Optimizer]中配置渠道或电子邮件。 此外：

* 发送、打开和点击记录在[!DNL Marketo Engage]中。
* 取消订阅管理和电子邮件治理适用于[!DNL Marketo Engage]。
* 电子邮件活动信息源为您现有的[!DNL Marketo Engage]评分营销活动。
* 活动触发了Salesforce同步营销活动按预期运行。
* 每次发送映射到[!DNL Marketo Engage]营销活动，因此您可以跟踪每个电子邮件营销活动的项目成员资格，并在熟悉的项目中进行报告。

## 从Marketo Optimizer发送电子邮件 {#send-from-optimizer}

使用此方法构建历程并完全在[!DNL Marketo Optimizer]中发送电子邮件。 [!DNL Marketo Engage]仍然是移交给您的客户关系管理(CRM)系统的记录系统。

1. 设置电子邮件渠道。 创建电子邮件模板，并配置IP地址和子域、取消订阅链接和登陆页面。 查看[电子邮件可投放性](./start/email-deliverability.md)。
1. 在[!DNL Marketo Optimizer]中设置通信限制。 共享通信限制不可用。
1. 利用受众、AI决策和下一个最佳路径构建历程。
1. 从[!DNL Marketo Optimizer]发送电子邮件。 [!DNL Marketo Optimizer]记录活动。
1. 对[!UICONTROL 评分工作室]中的人进行评分，以在[!DNL Marketo Engage]和[!DNL Marketo Optimizer]活动中创建一个模型。 查看[评分工作室](./labs/scoring-studio.md)。

取消订阅通过共享字段自动同步到[!DNL Marketo Engage]。 [!DNL Marketo Optimizer]电子邮件活动未发送回[!DNL Marketo Engage]，但[!UICONTROL 评分工作室]仍在使用它。

### 将潜在客户移交给销售人员 {#hand-off}

[!DNL Marketo Optimizer]没有直接CRM集成。 使用以下方法之一路由通过[!DNL Marketo Engage]的潜在客户：

* **基于得分：**&#x200B;得分字段显示在[!DNL Marketo Engage]中，并且智能营销活动会将商机同步到您的CRM。
* **基于活动：** [!DNL Marketo Optimizer]历程侦听该活动并将潜在客户添加到[!DNL Marketo Engage]智能营销活动。
* **计划成员资格：**&#x200B;历程位于[!DNL Marketo Optimizer]计划中，因此您从开始到结束跟踪状态。
