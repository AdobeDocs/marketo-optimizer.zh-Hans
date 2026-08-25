---
title: 人员受众历程节点
description: 在Journey Optimizer B2B中配置人员受众节点，以指定哪些用户档案使用动态人员列表或基于事件的受众进入历程。
source-git-commit: c7d3546d075f5a58923134231217b2fd10fe4aca
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 0%

---

# 人员受众节点

_人员受众_&#x200B;节点指定哪些人员配置文件进入历程。 当您[创建人员历程](./person-journeys.md)时，该历程始终以定义其输入的人员受众节点开始。 人员受众节点可以具有以下两种受众输入类型之一：动态人员列表或事件触发器。

如果人员历程所需的动态人员列表不存在，请[创建人员列表](../audiences/people-lists.md#create-a-people-list)，然后配置人员受众节点。

配置历程受众(_T):_

1. 单击&#x200B;**[!UICONTROL 人员受众]**&#x200B;节点。

   此操作在右侧显示节点属性。

   ![人员受众历程节点](./assets/person-audience-node-properties.png){width="600" zoomable="yes"}

1. 对人员受众使用以下受众配置选项之一：

   * **[!UICONTROL 动态列表]** — 使用基于规则的动态人员列表。 在历程运行时将评估列表规则，以限定历程的成员。 以后不符合动态列表资格的人不会从历程中删除。 请参阅&#x200B;_[动态列表](../audiences/people-lists.md#dynamic-lists)_。

   * **[!UICONTROL 事件受众]** — 使用事件受众根据符合条件的事项定义历程受众。 使用人员配置文件筛选定义受众成员，并使用事件标准触发历程条目。 查看&#x200B;_[基于事件的受众](../audiences/event-based-audiences.md)_。