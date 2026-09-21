---
title: 报告
description: 了解Adobe Marketo Optimizer中的“报表”选项卡，包括其报表部分、导出和计划选项，以及如何更改日期范围。
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 3c1de303-7a7c-59a6-abca-8c534730e19c
    internal-label: Reporting
source-git-commit: 6e919a66af259ea1f5facf7f5c3e811d76101e85
workflow-type: tm+mt
source-wordcount: '491'
ht-degree: 2%
---

# 报告

[!UICONTROL 报表]选项卡为您提供[!DNL Adobe Marketo Optimizer]中的性能分析，包括历程参与度、电子邮件性能和Web活动。 在左侧导航中，选择&#x200B;**[!UICONTROL 报表]**&#x200B;以将其打开。

每个报告都基于[!DNL Adobe Customer Journey Analytics]构建并直接嵌入到[!DNL Marketo Optimizer]中。 单击&#x200B;_列表_&#x200B;图标（![列表图标](../assets/do-not-localize/icon-table-of-contents.svg)）可使用左侧的&#x200B;**[!UICONTROL 目录]**&#x200B;面板在分区之间跳转。

![报告页面列出了人员历程概述、参与度、电子邮件参与度和Web参与度部分](./assets/reports-table-of-contents.png){width="800" zoomable="yes"}

## 报表节 {#report-sections}

[!UICONTROL 报告]选项卡将预建报告分为四个部分。 每个部分都有一个或多个可下载的项目，以及它自己的文档页面，其中包含有关其量度和可视化图表的详细信息。

| 部分 | 可下载项目 | 报告页面 |
| --- | --- | --- |
| [!UICONTROL 人员历程概述] | 活跃历程数 | [人员历程概述报告](./person-journey-overview-report.md) |
| [!UICONTROL 参与度] | 按人员列出的参与度，随时间变化的人员参与度 | [互动报告](./engagement-report.md) |
| [!UICONTROL 电子邮件往来] | 电子邮件参与度 | [电子邮件参与报告](./email-engagement-report.md) |
| [!UICONTROL Web参与] | 最多页面浏览量 | [Web参与报告](./web-engagement-report.md) |

## 个人记录报表 {#individual-record-reports}

某些报表侧重于单个记录而不是全部分割视图，可从应用程序的不同区域进行访问。

* 要获得电子邮件发送时间优化性能，请从[!UICONTROL 同事]聊天界面打开报告。 有关步骤，请参阅[电子邮件发送时间优化](../marketing/email-send-time-optimization.md#reporting)。
* 对于个人在单次历程中的进度，从该历程中打开[个人历程个人报表](./person-journey-individual-report.md)。

## 导出报告 {#export-a-report}

选择报表页顶部的&#x200B;**[!UICONTROL 共享]**&#x200B;以导出或计划其数据的提交。

![使用“下载CSV”、“下载PDF”、“计划导出”和“管理计划”选项共享菜单](./assets/reports-share-menu.png){width="500"}

* **[!UICONTROL 下载CSV]** — 将报表数据导出为纯文本值。

* **[!UICONTROL 下载PDF]** — 将报表中的所有可见表格和可视化导出为PDF文件。

* **[!UICONTROL 计划导出]** — 设置定期导出报告，每周或每月以CSV或PDF文件形式提交。

* **[!UICONTROL 管理计划]** — 查看和管理现有的计划导出。 选项显示针对您组织的限制使用的计划的运行计数，如`3/10`。

>[!NOTE]
>
>您的组织可以每周或每月跨所有报告的最多10次计划导出。 如果您不是管理员，则只能管理自己的计划导出。 管理员可以查看和管理组织内的每个计划导出。

## 在[!DNL Customer Journey Analytics]中分析报告 {#analyze-a-report-in-cja}

>[!AVAILABILITY]
>
>如果您的组织已获得[!DNL Adobe Customer Journey Analytics]的许可并且您分配了产品配置文件，则可以使用此功能。

在任意报表节上选择&#x200B;**[!UICONTROL 在CJA中分析]**，以在[!DNL Adobe Customer Journey Analytics] Workspace中打开它，除了嵌入式报表中可用的可视化图表之外，你可以在其中创建自定义可视化图表。

## 更改日期范围 {#change-the-date-range}

每个报表部分都会显示特定日期范围的数据，该数据显示在部分的右上角。 单击日期范围字段以显示日期选择工具并选择日期范围。 您可以选择其他预设或定义自定义范围。

![日期范围选取器，包含两个月日历、开始和结束日期字段以及预设选项](./assets/reports-date-range.png){width="600"}
