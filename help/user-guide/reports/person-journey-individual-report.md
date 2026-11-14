---
title: 人员历程详细信息报表
description: 了解Adobe Marketo Optimizer中的人员历程详细信息报表，该报表显示所选历程的完成、参与和电子邮件指标。
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 3c1de303-7a7c-59a6-abca-8c534730e19c
    internal-label: Reporting
source-git-commit: 84abcbf4ddf114898768766d6e91ec855e3f979f
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 0%
---

# 人员历程详细信息报表

<!-- SPHR-39120: UX plans to move the Journey activity flow tile to the top of the report. Update the tile order in this page when that ships. -->

单击&#x200B;**[!UICONTROL 查看实时或完成人员历程的报告]**，以查看其绩效指标和活动流程。 打开报告后，您可以选择要包含在报告中的多个历程。

>[!PREREQUISITES]
>
>要查看此报告，您必须具有&#x200B;**[!UICONTROL 查看B2B人员历程报告]** [权限](../start/permissions-reference.md)。

查看报告(_T):_

1. 从&#x200B;_[!UICONTROL 人员历程]_&#x200B;列表中打开&#x200B;**[!UICONTROL 实时]**&#x200B;或&#x200B;**[!UICONTROL 已完成]**&#x200B;人员历程。
1. 在历程标题中，选择&#x200B;**[!UICONTROL 查看报告]**。

   ![在历程标题中突出显示“查看报告”按钮的人员历程画布。](./assets/reports-person-journey-view-report.png){width="600" zoomable="yes"}

您可以[更改报告的日期范围](./reports-overview.md#change-the-date-range)。

选择报表顶部的&#x200B;**[!UICONTROL 共享]**&#x200B;以下载或计划导出数据。 请参阅报告概述中的&#x200B;[_导出报告_](./reports-overview.md#export-a-report)。

![个人历程个人报告，其历程名称（活动）和角色（活动）筛选器位于历程状态、完成趋势和参与磁贴之上。](./assets/reports-individual-journey.png){width="700" zoomable="yes"}

## 过滤器 {#filters}

报表最初会显示从中打开它的历程。 使用报告顶部的过滤器可更改包含哪些历程和角色。

* **[!UICONTROL 历程名称（事件）]** — 已预先设置为您从中打开报告的历程。 打开过滤器列表并选择要包含的历程。 您可以选择多个历程。
* **[!UICONTROL 角色（事件）]** — 将报告筛选为与特定[派生角色](../audiences/personas.md#filter-by-derived-persona)匹配的人员。 默认值为[!UICONTROL 无筛选器]。

![人员历程报告，其中历程名称（事件）筛选器列表已打开，且选择了三个历程，以及角色（事件）筛选器。](./assets/reports-person-journey-details-filters.png){width="700" zoomable="yes"}

要按角色进行筛选，请打开报表顶部的&#x200B;**[!UICONTROL 角色（事件）]**&#x200B;筛选器列表，并选择要包含的值。

选择&#x200B;**[!UICONTROL 全部重置]**&#x200B;以重置报表筛选器。

## 人员状态和参与 {#person-status-and-engagement}

本节介绍四个图块：

* **[!UICONTROL 历程中人员的状态]** — 将历程中的人员划分为&#x200B;_[!UICONTROL 已完成]_&#x200B;和&#x200B;_[!UICONTROL 进行中]_&#x200B;类别，并带有相应的百分比。
* **[!UICONTROL 随时间变化的已完成人数]** — 跟踪选定日期范围内完成历程的人数的折线图。
* **[!UICONTROL 已参与和未参与的人员]** — 将历程中的人员分为&#x200B;_[!UICONTROL 已参与]_&#x200B;和&#x200B;_[!UICONTROL 未参与]_&#x200B;类别，并提供相应的百分比。
* **[!UICONTROL 参与的人员]** — 符合参与历程条件的总人数。

## 电子邮件绩效 {#email-performance}

[!UICONTROL 电子邮件性能]表显示历程中发送的每个电子邮件的投放和参与量度。 对于所有历程中的相同电子邮件量度，请参阅[电子邮件参与报告](./email-engagement-report.md)。

![电子邮件性能表显示三封电子邮件的已发送、已投放、已打开和已点击量度。](./assets/reports-individual-journey-email-performance.png){width="700" zoomable="yes"}

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

[!UICONTROL 历程活动流]可视化图表显示人员通过旅程的路径，从&#x200B;_[!UICONTROL 将人员添加到历程]_&#x200B;活动开始。 每个节点会显示该活动的查看次数。

![历程活动流可视化图表显示通过“发送电子邮件”活动和电子邮件退回活动从“添加用户”到历程的路径视图。](./assets/reports-individual-journey-activity-flow.png){width="500" zoomable="yes"}
