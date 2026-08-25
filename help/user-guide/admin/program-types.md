---
title: 程序类型
description: 在Marketo Optimizer中创建和管理程序类型，这些类型为程序定义属性和成员状态流。
source-git-commit: c7d3546d075f5a58923134231217b2fd10fe4aca
workflow-type: tm+mt
source-wordcount: '389'
ht-degree: 0%

---

# 程序类型

计划类型定义[计划](../marketing/programs.md)及其成员的重要方面，并区分不同类型的营销计划。 每个程序类型定义以下属性，这些属性为使用程序类型的程序继承：

* **属性** — 属性描述程序类型的重要方面，如事件日期和位置属性。

* **项目群状态流程** — 每个状态都分配给项目群类型中的一个步骤（如1、2或3）。 程序成员只能从具有相同步骤编号的状态（例如，从&#x200B;_No-Showed_&#x200B;到&#x200B;_Attended_）或具有较高步骤编号的状态（例如，从&#x200B;_Required_&#x200B;到&#x200B;_Registered_）。

  项目状态是互斥的且线性的，因此每个项目只能有一个状态值。 在设计状态时，请思考您希望在哪些状态之间允许移动。 例如，如果某个人未参加网络研讨会，但可以选择稍后应需参加，则您可能希望他们具有相同的状态编号，或者将应需设置为更高的状态编号，以便项目成员可以进入该编号。

>[!NOTE]
>
>如果某个程序类型被至少一个程序使用，则无法对其进行编辑。

定义自定义程序类型(_T):_

1. 在[!DNL Adobe Marketo Optimizer]左侧导航中，展开&#x200B;**[!UICONTROL 管理]**&#x200B;并选择&#x200B;**[!UICONTROL 程序类型]**。

   ![访问程序类型列表](./assets/program-types-list.png){width="800" zoomable="yes"}

1. 单击右上方的&#x200B;**[!UICONTROL 创建类型]**。

1. 输入唯一的&#x200B;**[!UICONTROL Name]**（必需）和&#x200B;**[!UICONTROL Description]**（可选）。

   ![创建程序类型](./assets/program-type-create.png){width="600" zoomable="yes"}

   >[!TIP]
   >
   >包含描述是一种最佳实践，可使您的程序类型库更易于管理。

1. 单击&#x200B;**[!UICONTROL 创建类型]**。

1. 为程序类型添加&#x200B;**[!UICONTROL 属性]**。

   对于要添加的每个属性：

   * 单击&#x200B;**[!UICONTROL 添加属性]**。
   * 选择&#x200B;**[!UICONTROL API名称]**&#x200B;并输入&#x200B;**[!UICONTROL 显示名称]**。
   * 单击&#x200B;**[!UICONTROL 保存]**。

   ![项目群类型属性](./assets/program-type-attributes.png){width="600" zoomable="yes"}

1. 为&#x200B;**[!UICONTROL 项目状态]**&#x200B;定义步骤。

   定义要包含在流中的每个步骤：

   * 单击&#x200B;**[!UICONTROL 添加步骤]**。
   * 输入状态名称。
   * （可选）单击&#x200B;**[!UICONTROL 添加状态]**，然后输入要包含在该步骤中的其他状态名称。

   对于要作为成功项目执行跟踪的任何步骤，选中&#x200B;**[!UICONTROL 标记为成功]**&#x200B;复选框。

   ![程序类型状态](./assets/program-type-statuses.png){width="600" zoomable="yes"}

1. 单击&#x200B;**[!UICONTROL 完成]**&#x200B;以保存更改并返回程序类型列表。