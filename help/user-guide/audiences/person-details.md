---
title: 人员详细信息
description: 查看人员人工智能生成的角色、参与和意图摘要、活动历史记录、配置文件属性和公司详细信息，并在Marketo Optimizer中向同事询问有关记录的问题。
source-git-commit: 75b481faf0d66210329f95c8afabdfa59e7bcb79
workflow-type: tm+mt
source-wordcount: '690'
ht-degree: 7%

---


# 个人详细信息

在[!DNL Adobe Marketo Optimizer]中，当您在[人员列表](./people-lists.md)的&#x200B;_[!UICONTROL 成员]_&#x200B;选项卡上单击某个人员的姓名时，将打开该人员的详细信息页面，其中包含该人员的综合视图。 本页提供：

* AI生成的角色、参与和意图摘要
* 完整的活动历史记录
* 用户档案和公司属性
* 同事聊天界面具有回答有关人员问题的范围

## 打开人员详细信息 {#open-person-details}

1. 在左侧导航栏中，展开&#x200B;**[!UICONTROL 营销管理]**。

1. 在&#x200B;**[!UICONTROL 营销]**&#x200B;资源列表的右侧，选择&#x200B;**[!UICONTROL 人员列表]**。

1. 打开动态或静态列表。

1. 单击列表中人员的&#x200B;**[!UICONTROL 姓名]**。

   ![静态联系人列表 — “成员”选项卡](./assets/people-list-members-tab.png){width="600" zoomable="yes"}

人员详细信息页面打开，其中包含三个选项卡：**[!UICONTROL 概述]**、**[!UICONTROL 属性]**&#x200B;和&#x200B;**[!UICONTROL 公司]**。

## 页眉 {#page-header}

标题将人员的姓名显示为页面标题，并快速浏览联系人信息栏：

* 职务名称
* 公司
* 电子邮件地址
* 电话号码

单击“**[!UICONTROL 上一步]**”返回原始列表。

## Overview 选项卡 {#overview-tab}

**[!UICONTROL 概述]**&#x200B;选项卡包含潜在客户摘要卡片和活动时间线。

![个人详细信息 — 概述选项卡](./assets/people-list-person-details-overview-tab.png){width="700" zoomable="yes"}

### 商机摘要 {#lead-summary}

三张卡片用于由人工智能生成的人员评估：

| 卡片 | 目录 |
|---|---|
| **[!UICONTROL 角色]** | 人员的[派生角色](./personas.md)，以及描述其角色、公司和行业的简短描述。 单击信息图标可获取更多详细信息。 |
| **[!UICONTROL 参与度]** | [人员参与度分数](./engagement-scores.md)、趋势（例如&#x200B;_正在增加_）和级别（_低_、_Medium_、_高_）。 |
| **[!UICONTROL 意图]** | 检测到购买意图，或&#x200B;_未检测到_，其中包含上下文指南和可帮助您提高产品意图的链接。 |

### 活动 {#activities}

在潜在客户摘要下，**[!UICONTROL 活动]**&#x200B;面板列出了人员的完整交互历史记录，并按日期分组。 每个日期组均可展开和折叠，并且每行都显示时间戳、活动类型标记（例如，_[!UICONTROL 更改数据值]_、_[!UICONTROL 添加到列表]_、_[!UICONTROL 将人员添加到历程]_，或&#x200B;_[!UICONTROL 历程过渡]_）以及所发生情况的纯语言描述。 在适用的情况下，描述包括跳到相关对象的链接，如&#x200B;**[!UICONTROL 查看列表]**&#x200B;或&#x200B;**[!UICONTROL 查看历程]**。

使用面板控件来处理时间线：

* **活动类型** — 将时间线过滤为特定活动类型，如电子邮件发送、网络研讨会交互或列表和历程更改。
* **日期范围** — 使用日历控件将时间线限制为特定日期范围。
* **[!UICONTROL 导出]** — 导出可见的活动数据。
* **[!UICONTROL 全部折叠] / [!UICONTROL 全部展开]** — 一次打开或关闭每个日期分组。

## “属性”选项卡 {#attributes-tab}

![人员详细信息 — 属性选项卡](./assets/people-list-person-details-attributes-tab.png){width="700" zoomable="yes"}

**[!UICONTROL 属性]**&#x200B;选项卡将人员的存储配置文件字段显示为标签/值列表：

* 名
* 中间名
* 姓
* 电子邮件
* 标题
* 电话
* 地址
* 城市
* State
* 国家
* 公司
* 创建时间
* 上次更新时间

## “公司”选项卡 {#company-tab}

![人员详细信息 — 公司选项卡](./assets/people-list-person-details-company-tab.png){width="700" zoomable="yes"}

**[!UICONTROL 公司]**&#x200B;选项卡显示与人员的公司关联的第一层数据：

* 公司
* 行业
* 年收入
* 帐单街道
* 帐单寄送城市
* 帐单寄送州
* 帐单邮寄邮政编码
* 帐单寄送国家/地区

没有可用数据的字段显示为破折号。

## 向同事询问有关人员的信息 {#ask-coworker}

打开页面顶部附近的&#x200B;**[!UICONTROL Co-worker]**&#x200B;面板图标以获取有关当前人员记录的帮助。 该面板将打开指向该人员的范围 — 消息线程下面的芯片（例如，_人员： [人员名称]_）确认您的提示目标记录是什么。

![人员详细信息 — 同事](./assets/people-list-person-details-coworker.png){width="700" zoomable="yes"}

### 从建议的提示开始 {#suggested-prompts}

当您从人员详细信息页面打开面板时，同事会向您发送上下文欢迎消息和默认建议提示，例如：

* _帮助我了解[人员姓名]_
* _告诉我[人员姓名]的角色_
* _总结[人员姓名]的参与活动_

单击建议的提示，或在面板底部的输入框中键入您自己的问题。

### 查看响应 {#review-response}

选择提示将运行多步骤[技能](../agents/skills.md)，显示为顺序状态步骤（例如，_按ID查找人员_&#x200B;和&#x200B;_获取人员故事_），而同事将编写答案。 响应是结构化的摘要，其中可能包括人员的配置文件详细信息、参与历史记录和电子邮件效果。

使用thumbs-up/thumbs-down控件对响应进行评级。 与所有同事输出一样，在使用响应之前对其进行审阅。 有关详细信息，请参阅[Adobe Generative AI用户准则](https://www.adobe.com/cn/legal/licenses-terms/adobe-dx-gen-ai-user-guidelines.html){target="_blank"}。
