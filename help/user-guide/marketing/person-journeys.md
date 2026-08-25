---
title: 人员历程
description: 在Marketo Optimizer中创建、发布和管理人员历程 — 浏览历程列表、设计多步骤流以及复制或删除历程。
source-git-commit: c7d3546d075f5a58923134231217b2fd10fe4aca
workflow-type: tm+mt
source-wordcount: '1418'
ht-degree: 19%

---

# 人员历程

在[!DNL Adobe Marketo Optimizer]中，人员历程是基于商机的自动多步骤营销计划，可在各个渠道之间编排个性化体验。 这些历程使用Marketo Engage数据执行这些营销计划，以响应参与、业务事件或计划的营销活动。

>[!NOTE]
>
>每个历程都驻留在定义的[项目](./programs.md)中。 在创建历程之前，您必须至少有一个项目用作父项。

构建新的人员历程(_T):_

1. 创建人员历程。
1. 在历程画布中添加节点并定义历程流。
1. [发布历程](#publish-a-journey)。

## 访问和浏览人员历程 {#access-and-browse-person-journeys}

1. 在左侧导航栏中，展开&#x200B;**[!UICONTROL 营销管理]**。

1. 在&#x200B;**[!UICONTROL 营销]**&#x200B;资源列表的右侧，选择&#x200B;**[!UICONTROL 人员历程]**。

   _人员历程_&#x200B;列表在主工作区中显示为选项卡页。

   您可以在列表顶部的&#x200B;_搜索_&#x200B;工具中输入文本，以按名称筛选显示的列表。

   ![人员历程列表](./assets/person-journeys-list-search.png){width="800" zoomable="yes"}

1. 使用列表工具自定义显示的列表：

   * 单击&#x200B;_筛选器_ （![筛选器图标](../assets/do-not-localize/icon-react-filter.svg)）图标以按状态筛选列表。
   * 单击&#x200B;_自定义表_ （![自定义表图标](../assets/do-not-localize/icon-falco-customize-table.svg)）图标以控制显示的列。
   * 单击&#x200B;_重置列_ （![重置列宽图标](../assets/do-not-localize/icon-falco-reset-columns.svg) ）图标可重置列宽。

### 历程列表列 {#journey-list-columns}

历程列表页面包含以下列：

* [!UICONTROL 名称] （单击名称以打开历程画布进行编辑）
* [!UICONTROL 状态]
* [!UICONTROL 创建日期]
* [!UICONTROL 创建者]
* [!UICONTROL 上次更新]
* [!UICONTROL 上次更新者]
* [!UICONTROL 发布日期]
* [!UICONTROL 发布者]
* [!UICONTROL 开始日期]
* [!UICONTROL 结束日期]

您可以通过单击列标题按&#x200B;_[!UICONTROL 状态]_、_[!UICONTROL 创建日期]_&#x200B;或&#x200B;_[!UICONTROL 上次更新]_&#x200B;对列表进行排序。 您可以抓取并拖动标题边框，以更改显示的列宽。 在&#x200B;_自定义表_&#x200B;对话框中，选中或清除复选框，然后单击&#x200B;**[!UICONTROL 应用]**。

### 历程状态 {#journey-status}

历程的状态会根据您应用的操作而改变。 根据历程的状态，某些操作在标题右侧可用。

| 状态 | 描述 | 可用操作 |
| ------ | ----------- | ----------------- |
| _**草稿**_ | 可编辑的未发布历程。 | [发布](#publish-a-journey)，[重复](#duplicate-a-journey)，[删除](#delete-a-journey) |
| _**实时**_ | 发布历程时，历程状态从&#x200B;_草稿_&#x200B;更改为&#x200B;_实时_。 在这种状态下，历程无法再编辑。 | [重复](#duplicate-a-journey)，[关闭新条目](#close-to-new-entries)，[中止](#abort-a-journey) |
| _**对新条目关闭**_ | 当您在历程标题中单击&#x200B;**[!UICONTROL 关闭新条目]**&#x200B;时，历程状态将从&#x200B;_实时_&#x200B;更改为&#x200B;_已关闭新条目_。 | [重复](#duplicate-a-journey)，[中止](#abort-a-journey) |
| _**已中止**_ | 历程中止后，历程状态从&#x200B;_实时_&#x200B;或&#x200B;_对新条目关闭_&#x200B;改变。 已中止历程无法重新开始。 | [重复](#duplicate-a-journey)，[删除](#delete-a-journey) |
| _**已完成**_ | 当历程中的所有人员受众成员完成历程时，状态将从&#x200B;_实时_&#x200B;或&#x200B;_已关闭到新条目_&#x200B;更改为&#x200B;_已完成_。 | [重复](#duplicate-a-journey)，[删除](#delete-a-journey) |

## 创建人员历程 {#create-a-person-journey}

1. 单击旅程列表右上角的&#x200B;**[!UICONTROL 创建历程]**。

1. 在对话框中，为人员历程选择&#x200B;**[!UICONTROL 父]**&#x200B;项目。

1. 输入唯一的&#x200B;**[!UICONTROL Name]**（必需）和&#x200B;**[!UICONTROL Description]**（可选）。

   ![创建人员历程对话框](./assets/person-journey-create-dialog.png){width="400"}

1. 单击&#x200B;**[!UICONTROL 创建]**。

   历程画布将打开，并带有起始人员受众节点。

   新人员历程的![历程画布](./assets/person-journey-new.png){width="600" zoomable="yes"}

### 历程标题 {#journey-header}

每个历程画布的标题包括历程名称、状态和计划。

![人员历程标题](./assets/person-journey-header.png){width="600" zoomable="yes"}

* 单击&#x200B;_编辑_&#x200B;图标（![编辑图标](../assets/do-not-localize/icon-react-edit.svg)）以更改历程名称或描述信息。
* 单击&#x200B;**[!UICONTROL 历程设置]**&#x200B;以更改历程开始和循环。
* 单击&#x200B;**[!UICONTROL ...更多]**&#x200B;以应用历程操作，或者启用/禁用[历程流量控制](./journey-traffic-control.md)并重新进入。
* 如果解决了所有错误且您希望激活历程，请单击&#x200B;**[!UICONTROL 发布]**。

### 历程设计 {#journey-design}

_历程画布_&#x200B;是历程工作区的中心区域。 您可以在此处添加并配置历程节点。 单击某个节点，在布局右侧的面板中打开其属性，并根据您的设计设置这些属性。 人员历程始终以[_[!UICONTROL 人员受众&#x200B;]_节点](./person-audience-node.md)开始，您可以在其中定义历程的输入。

创建人员历程并定义人员受众后，使用节点构建历程。 历程画布提供了一个可视设计空间，您可以在其中使用以下节点类型构建分步式B2B营销用例以构建历程：

* [执行操作](./action-nodes.md)
* [侦听事件](./listen-for-event-nodes.md)
* [等待](./wait-nodes.md)
* [拆分路径](./split-merge-paths-nodes.md)
* [下一个最佳路径](./next-best-path.md)
* [合并路径](./split-merge-paths-nodes.md)

## 历程管理 {#journey-management}

打开历程列表以查看历程状态、进行更改并采取操作。

### 历程操作 {#journey-actions}

历程列表页面包含您的Marketo Optimizer实例中的所有人员历程。 从列表页面，您可以将多个操作应用到历程。

#### 发布历程 {#publish}

如果没有阻止程序错误，则可以发布历程。 发布后，历程状态更改为&#x200B;_实时_。 如果历程有错误，**[!UICONTROL 发布]**&#x200B;按钮将灰显，并显示消息`Resolve errors before publishing`。

1. 从&#x200B;_[!UICONTROL 人员历程]_&#x200B;列表中打开草稿历程。

1. 在历程画布的右上方，单击&#x200B;**[!UICONTROL 发布]**。

1. 在&#x200B;_[!UICONTROL 查看历程设置]_&#x200B;对话框中，设置历程开始选项。

   如果已在&#x200B;**[!UICONTROL 历程设置]**&#x200B;中定义计划，请查看设置。

   如果需要设置历程激活，请选择计划类型：

   * 要在发布时激活历程，请选择&#x200B;**[!UICONTROL 立即]**。
   * 要在将来的某个日期激活历程，请选择&#x200B;**[!UICONTROL 在特定日期]**，然后单击&#x200B;_日历_&#x200B;图标以选择日期。

1. 如果需要，请为历程指定&#x200B;**[!UICONTROL 结束日期]**。

   ![查看历程设置对话框](./assets/journey-publish-review-settings.png){width="400" zoomable="no"}

   从开始日期起最多可以为三年。 发布时需要此字段。

1. 单击&#x200B;**[!UICONTROL 下一步]**。

1. 在确认对话框中，单击&#x200B;**[!UICONTROL 发布]**。

#### 中止历程 {#abort-a-journey}

如果您中止（停止）安排在将来开始日期的实时历程或历程，则历程中的人会立即停止进度，并且不会发生进一步的历程进入。 已中止历程无法重新开始。

1. 从&#x200B;_[!UICONTROL 人员历程]_&#x200B;列表中打开历程。

1. 单击&#x200B;**[!UICONTROL ...在右上角显示更多]**，然后选择&#x200B;**[!UICONTROL 中止]**。

   ![实时人员历程标题](./assets/person-journey-live-header.png){width="600" zoomable="yes"}

1. 在确认对话框中单击&#x200B;**[!UICONTROL 中止]**。

#### 对新条目关闭 {#close-to-new-entries}

如果您对新条目关闭实时历程，则当前历程中的人会继续其在该历程中的路径，并且不会发生进一步的历程进入。 已关闭历程无法重新开始。 您可以重复一个已关闭的历程。

1. 从&#x200B;_[!UICONTROL 人员历程]_&#x200B;列表中打开历程。

1. 单击&#x200B;**[!UICONTROL ...在右上角显示更多]**，然后选择&#x200B;**[!UICONTROL 关闭新条目]**。

1. 在确认对话框中单击&#x200B;**[!UICONTROL 对新条目关闭]**。

#### 复制历程 {#duplicate-a-journey}

复制操作类似于克隆功能，但复制的历程不包含任何已创建的历程内容资产。 您可以复制历程的详细信息，或仅复制流量和路径结构的简单框架。

1. 在&#x200B;_[!UICONTROL 人员历程]_&#x200B;列表中，单击历程名称旁边的&#x200B;_更多_&#x200B;图标( **...**)，然后选择&#x200B;**[!UICONTROL 复制]**。

   ![草稿人员历程更多菜单](./assets/person-journey-draft-more-menu.png){width="400"}

   根据历程的状态，您还可以从历程详细信息或历程画布访问重复操作：

   * 对于草稿历程，单击&#x200B;**[!UICONTROL ...右上角的More]**&#x200B;并选择&#x200B;**[!UICONTROL 复制]**。
   * 对于所有其他历程状态，请单击右上角的&#x200B;**[!UICONTROL 复制]**。

1. 在对话框中，为复制的历程选择&#x200B;**[!UICONTROL 父]**&#x200B;程序。

1. 输入唯一的&#x200B;**[!UICONTROL Name]**（必需）和&#x200B;**[!UICONTROL Description]**（可选）。

   默认情况下，该对话框使用附加了`_copy`的原始历程的名称。 根据需要为历程输入其他唯一名称。

   ![重复的历程对话框](./assets/journey-duplicate-dialog.png){width="370"}

1. 选择复制&#x200B;**[!UICONTROL 类型]**：

   * **[!UICONTROL 部分内容复制]** - 使用此类型来复制历程中的所有内容，但不包括任何已创建的电子邮件或 SMS 消息。 引用 Marketo Engage 电子邮件或 SMS 消息的节点会被完整保留。

   * **[!UICONTROL 复制但不包含详细信息]** — 使用此类型仅复制节点结构和路径。 所有节点设置和路径条件均未定义（默认），以便您可以重复使用具有不同受众、操作和路径分段设置的基本流程。 所有“等待”节点都使用默认的5天。

1. 单击&#x200B;**[!UICONTROL 复制]**。

   重复的历程在历程画布中打开，您可以在其中设置详细信息并根据需要创建历程内容。

#### 删除历程 {#delete-a-journey}

使用删除操作来永久删除历程。 您无法删除实时历程或安排在将来开始日期的历程。

>[!WARNING]
>
>删除历程是永久性的，无法撤消。

1. 在&#x200B;_[!UICONTROL 人员历程]_&#x200B;列表中，单击历程名称旁边的&#x200B;_更多_&#x200B;图标( **...**)，然后选择&#x200B;**[!UICONTROL 删除]**。

   根据历程的状态，您还可以从历程标题访问删除操作：

   * 对于草稿历程，单击&#x200B;**[!UICONTROL ...右上角的“更多]**”，然后选择&#x200B;**[!UICONTROL 删除]**。
   * 对于其他历程状态，例如&#x200B;_已完成_&#x200B;或&#x200B;_已中止_，请单击右上角的&#x200B;**[!UICONTROL 删除]**。

1. 在确认对话框中单击&#x200B;**[!UICONTROL 删除]**。
