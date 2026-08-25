---
title: 拆分和合并路径节点
description: 了解如何在人员历程中使用拆分和合并路径节点，根据定义的条件将人员划分为不同的路径，然后在下游的某个公共点将其重新联合。
source-git-commit: c7d3546d075f5a58923134231217b2fd10fe4aca
workflow-type: tm+mt
source-wordcount: '660'
ht-degree: 0%

---

# 拆分和合并路径节点

在人员历程中使用拆分和合并路径节点，根据您定义的条件将人员划分为不同的路径，然后将这些路径统一在一起，以便历程可以继续。 通过拆分路径，可针对特定受众区段定制操作和事件，而合并路径可在下游的共同点重新统一这些区段。

## 拆分路径节点

使用拆分节点，根据您定义的条件进行人员分段。 根据条件为受众列表创建路径，使用区段的操作和事件节点定义每个路径，然后组合路径并继续历程。

“拆分路径”节点根据人员筛选器定义一个或多个分段路径。

<!-- A split based on a people filter is automatically closed with a merge paths node so that all people can move forward to the next step. Split by people paths can include only people actions. These paths cannot be split again and automatically join back. _not currently true_ -->

_**按人员节点划分的拆分路径的工作方式**_

* 每个路径的评估是从上到下。 如果人员与第一条和第二条路径匹配，则他们仅沿着第一条路径前进。
* 该节点支持&#x200B;_其他人员_&#x200B;路径的定义，您可以在其中添加与定义的区段/路径之一不匹配的人员的操作或事件。

### 匹配过滤器

对于您为节点定义的每个路径，使用以下过滤器类型根据一个或多个条件匹配人员：

* 活动历史记录 — 您可以根据与以下项相关的人员活动定义路径：

  * 电子邮件消息
  * 数据值更改

* 人员属性 — 根据人员的属性定义条件，例如国家/地区、职务、派生角色或列表成员资格。

### 添加拆分路径节点

1. 导航到历程画布。

1. 单击路径上的加号( **+** )图标，然后选择&#x200B;**[!UICONTROL 拆分路径]**。

   ![单击历程路径上的“添加”图标](./assets/person-journey-canvas-add-node.png){width="200"}

1. 要定义适用于&#x200B;_[!UICONTROL 路径1]_&#x200B;的条件，请单击&#x200B;**[!UICONTROL 应用条件]**。

1. 在条件编辑器中，添加一个或多个过滤器以定义拆分路径。

   * 从左侧导航中拖放任何人员筛选器并完成匹配定义。

   * 通过在顶部应用&#x200B;**[!UICONTROL 筛选器逻辑]**&#x200B;来优化条件。 您可以选择匹配所有条件或任一条件。

     <!-- ![Split path node - conditions person filter logic](./assets/node-split-conditions-people.png){width="700" zoomable="yes"} -->

   * 单击&#x200B;**[!UICONTROL 完成]**。

1. 要添加更多路径，请单击&#x200B;**[!UICONTROL 添加路径]**，然后重复上述步骤以添加适用于该路径的条件。

   您还可以根据这些条件标记每个路径或使用默认标签。

1. 如果需要，可根据所需的拆分优先级对路径重新排序。

   路径过滤将按自上而下的顺序进行计算。 每个人沿着第一个匹配的路径前进。

   单击每个路径卡右上角的向上和向下箭头，将其在路径列表中向上或向下移动。

   <!-- ![Split path node - reorder paths](./assets/node-split-reorder-paths-people.png){width="500" zoomable="yes"} -->

1. 启用&#x200B;**[!UICONTROL 其他人]**&#x200B;选项，为与定义的路径不匹配的人添加默认路径。

   未启用此选项时，与定义的区段/路径不匹配的用户将越过拆分，继续历程中的下一步。

为每个路径定义了条件后，您可以添加要应用于路径上人员的操作或事件节点。

## 合并路径节点

1. 导航到历程画布，并找到包含两个或更多路径的拆分路径节点。

   每个路径都应该包含每个路径上的操作和事件的组合。

1. 单击这些路径中任一路径末尾的加号( **+** )图标，然后从显示的选项中选择&#x200B;**[!UICONTROL 合并路径]**。

1. 在右侧的节点属性中，选择要合并的路径。

   <!-- ![Journey node - merge paths](./assets/node-merge-select-paths.png){width="600" zoomable="yes"} -->

   此时，路径会被合并，以便选定路径中的人合并到单个路径中，从而继续完成历程。

1. 如果需要，您可以通过导航回合并路径节点属性并清除要删除的任何路径的复选框来取消合并路径。