---
title: 个人历程个人报表
description: 了解Adobe Marketo Optimizer中的人员历程个人报表，该报表显示一次历程的完成、参与和电子邮件指标。
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 3c1de303-7a7c-59a6-abca-8c534730e19c
    internal-label: Reporting
source-git-commit: 531dce4ffe6000efa0296f0e2393423f54124ea7
workflow-type: tm+mt
source-wordcount: '441'
ht-degree: 0%
---

# 个人历程个人报表

<!-- SPHR-39120: UX plans to move the Journey activity flow tile to the top of the report. Update the tile order in this page when that ships. -->

单击&#x200B;**[!UICONTROL 查看实时或完成人员历程的报告]**&#x200B;以查看其性能，包括状态、参与度、电子邮件量度和活动流程。

查看报告(_T):_

1. 从&#x200B;_[!UICONTROL 人员历程]_&#x200B;列表中打开&#x200B;**[!UICONTROL 实时]**&#x200B;或&#x200B;**[!UICONTROL 已完成]**&#x200B;人员历程。
1. 在历程标题中，选择&#x200B;**[!UICONTROL 查看报告]**。

   ![在历程标题中突出显示“查看报告”按钮的人员历程画布。](./assets/reports-person-journey-view-report.png){width="600" zoomable="yes"}

您可以[更改报告的日期范围](./reports-overview.md#change-the-date-range)。

选择报表顶部的&#x200B;**[!UICONTROL 共享]**&#x200B;以下载或计划导出数据。 请参阅报告概述中的&#x200B;[_导出报告_](./reports-overview.md#export-a-report)。

![显示历程状态、完成趋势和参与磁贴的人员历程个人报告。](./assets/reports-individual-journey.png){width="700" zoomable="yes"}

## 过滤器 {#filters}

报告过滤器的作用域限于当前历程。

* **[!UICONTROL 历程名称（事件）]** — 已预先设置为您从中打开报告的历程。
* **[!UICONTROL 角色（事件）]** - （_尚不受支持_）将报告筛选为与特定[派生角色](../audiences/personas.md#filter-by-derived-persona)匹配的人员。 默认值为[!UICONTROL 无筛选器]。

选择&#x200B;**[!UICONTROL 重置全部]**&#x200B;以清除&#x200B;_[!UICONTROL 角色（事件）]_&#x200B;筛选器并返回默认视图。

## 人员状态和参与 {#person-status-and-engagement}

本节介绍四个图块：

* **[!UICONTROL 历程中的人员状态]** — 将历程中的人员分成&#x200B;_[!UICONTROL 已完成]_&#x200B;和&#x200B;_[!UICONTROL 进行中]_&#x200B;类别，并具有相应的百分比。
* **[!UICONTROL 随时间变化的已完成人数]** — 跟踪选定日期范围内完成旅程人数的折线图。
* **[!UICONTROL 已参与和未参与的人员]** — 将历程中的人员分为&#x200B;_[!UICONTROL 已参与]_&#x200B;和&#x200B;_[!UICONTROL 未参与]_&#x200B;类别，并提供相应的百分比。
* **[!UICONTROL 参与的人员]** — 符合参与历程条件的人员总数。

## 电子邮件绩效 {#email-performance}

[!UICONTROL 电子邮件性能]表显示历程中发送的每个电子邮件的投放和参与量度。 对于所有历程中的相同电子邮件量度，请参阅[电子邮件参与报告](./email-engagement-report.md)。

![电子邮件性能表显示一个电子邮件的已发送、已投放、已打开和已点击指标。](./assets/reports-individual-journey-email-performance.png){width="700" zoomable="yes"}

[!UICONTROL 电子邮件性能]表列：

* [!UICONTROL 电子邮件名称] — 电子邮件的名称。
* [!UICONTROL 已发送] — 已发送的电子邮件数。
* [!UICONTROL 已传递] — 已传递的电子邮件数。
* [!UICONTROL %已投放] — 已投放电子邮件数除以已发送数量。
* [!UICONTROL 已打开] — 收件人打开电子邮件的次数。
* [!UICONTROL %已打开] — 已打开电子邮件的数量除以投放的数量。
* [!UICONTROL 已单击] — 收件人单击电子邮件中链接的次数。
* [!UICONTROL %已点击] — 已点击电子邮件数除以发送数量。

## 历程活动流程 {#journey-activity-flow}

[!UICONTROL 历程活动流]可视化图表显示人员通过旅程的路径，从&#x200B;_[!UICONTROL 将人员添加到历程]_&#x200B;活动开始。 每个节点会显示该活动的路径查看次数。

![历程活动流可视化图表显示从添加人员到电子邮件投放历程的路径视图。](./assets/reports-individual-journey-activity-flow.png){width="700" zoomable="yes"}
