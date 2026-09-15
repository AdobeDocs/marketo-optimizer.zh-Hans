---
title: 拆分和合并路径节点
description: 了解如何在人员历程中使用拆分和合并路径节点，根据定义的条件将人员划分为不同的路径，然后在下游的某个公共点将其重新联合。
TQID: 'https://experienceleague.adobe.com/XMN7lgb77bFlJkNXrmPf9ZSCV-GgIuybtr-O3AsqT2U'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 64b90904-e4f0-5c1b-a871-8c6a40b204a1
    internal-label: Journeys
source-git-commit: 9d9f2ae1aafc5ffdc2bcc6546c7eb2ddcbaa4ab2
workflow-type: tm+mt
source-wordcount: '1064'
ht-degree: 6%
---
# 拆分和合并路径节点

在人员历程中使用拆分和合并路径节点，根据您定义的条件将人员划分为不同的路径，然后合并这些路径，以便历程可以继续。 通过拆分路径，可针对特定受众区段定制操作和事件，而合并路径可在同一个点组合这些区段。

## 拆分路径节点

使用拆分节点，根据您定义的条件进行人员分段。 根据条件为受众列表创建路径，使用区段的操作和事件节点定义每个路径，然后组合路径并继续历程。

“拆分路径”节点根据人员筛选器定义一个或多个分段路径。

<!-- A split based on a people filter is automatically closed with a merge paths node so that all people can move forward to the next step. Split by people paths can include only people actions. These paths cannot be split again and automatically join back. _not currently true_ -->

_&#x200B;**拆分路径节点的运行方式**&#x200B;_

* 每个路径的评估是从上到下。 如果人员匹配第一条和第二条路径，则他们仅沿着第一条路径前进。
* 该节点支持&#x200B;_其他人员_&#x200B;路径的定义，您可以在其中添加与定义的区段/路径之一不匹配的人员的操作或事件。

### 匹配的人员过滤器

对于您为节点定义的每个路径，使用以下过滤器类型根据一个或多个条件匹配人员。

| 过滤器 | 描述 |
| ------- | ----------- |
| 活动历史记录 | 基于使用一个或多个选定项目评估的条件的活动 |
| Brand Concierge | 与[!DNL Brand Concierge]接洽的潜在客户的活动。 |
| 公司属性 | 公司/帐户个人资料中的属性，包括： <li>年收入 <li>公司名称 <li>帐单寄送国家/地区 <li>行业 <li>员工数 <li>SIC 代码 <li>State |
| 意图数据 | 基于与人员配置文件关联的目的数据的属性。 |
| 商机 | 基于与人员配置文件关联的机会的属性。 |
| 人员属性 | B2B人员配置文件中的属性，包括： <li>城市 <li>国家 <li>出生日期 <li>电子邮件地址 <li>电子邮件无效 <li>电子邮件已暂停 <li>名字 <li>推断的州区域<li>作业名称 <li>姓 <li>手机号码 <li>人员参与度评分 <li>电话号码 <li>邮政编码 <li>State <li>取消订阅 <li>取消订阅的原因 |
| 销售应用程序 | 与[!DNL Sales Qualifier]或[!DNL Marketo Sales Insights]相关的潜在客户活动。 |
| 特殊筛选条件 | 筛选不属于预定义类别的属性，为自定义或其他筛选条件提供了灵活性。 |

>[!BEGINSHADEBOX]

条件筛选器&#x200B;**的**&#x200B;支持的[!DNL Marketo Optimizer]活动

对于路径条件，[!DNL Marketo Optimizer]支持来自作为数据源连接的[!DNL Marketo Engage]实例的活动。

>[!NOTE]
>
>只能有一个[!DNL Marketo Engage]实例作为数据源，并在预配[!DNL Marketo Optimizer]实例时对其进行预配置。

您可以围绕以下[!DNL Marketo Engage]活动构建条件：

* [!UICONTROL 已填写Marketo Engage表单] — 匹配在其非过期活动日志中任何时候已完成特定[!DNL Marketo Engage]表单的潜在客户。
* [!UICONTROL 已访问Marketo Engage网页] — 匹配已在您的网站或[!DNL Marketo Engage]登陆页面上查看特定URL的潜在客户。 它可直接使用您网站上安装的Munchkin跟踪代码运行。
* [!UICONTROL 已单击Marketo Engage网页上的链接] — 匹配已单击跟踪页面上的特定链接或资源的潜在客户。
* [!UICONTROL 已发送Marketo Engage电子邮件] — 匹配[!DNL Marketo Engage]尝试向其发送特定电子邮件的潜在客户，考虑硬退回或服务器接受之前的部署操作。
* [!UICONTROL 已传递Marketo Engage电子邮件] — 匹配其邮件服务器(MX)向[!DNL Marketo Engage]发送服务器返回成功响应（250 OK消息）的潜在客户。
* [!UICONTROL Marketo Engage电子邮件已退回] — 匹配在特定电子邮件发送时或时间范围内遇到硬退回（永久投放失败）的潜在客户。
* [!UICONTROL Marketo Engage电子邮件软退回] — 匹配其电子邮件遇到临时投放失败（如收件箱已满或服务器已脱机）而不是永久硬退回的潜在客户。
* [!UICONTROL 取消订阅Marketo Engage电子邮件] — 匹配选择退出非运营营销电子邮件的潜在客户。 发生这种情况时，[!DNL Marketo Engage]会自动将商机的`Unsubscribed`字段值更新为`true`，从而禁止将来发送标准电子邮件时发送它们。
* [!UICONTROL 已打开Marketo Engage电子邮件] — 匹配已打开跟踪的[!DNL Marketo Engage]电子邮件的潜在客户。
* [!UICONTROL 在Marketo Engage电子邮件中点击的链接] — 匹配点击了[!DNL Marketo Engage]电子邮件中的任何链接（或特定链接）的潜在客户。

>[!ENDSHADEBOX]

### 添加拆分路径节点

1. 导航到历程画布。

1. 单击路径上的加号( **+** )图标，然后选择&#x200B;**[!UICONTROL 拆分路径]**。

   ![单击历程路径上的“添加”图标](./assets/person-journey-canvas-add-node.png){width="200"}

1. 要定义适用于&#x200B;_[!UICONTROL 路径1]_&#x200B;的条件，请单击&#x200B;**[!UICONTROL 应用条件]**。

1. 要定义拆分路径，请在条件编辑器中添加一个或多个筛选器。

   * 从左侧导航中拖放任何人员筛选器并完成匹配定义。

   * 为要用于优化筛选器匹配的每个约束单击&#x200B;**[!UICONTROL 添加约束]**。

     ![拆分路径节点 — 路径条件的匹配人员筛选器](./assets/journey-node-split-conditions-people.png){width="700" zoomable="yes"}

   * 通过在顶部应用&#x200B;**[!UICONTROL 筛选器逻辑]**&#x200B;优化条件。 您可以选择匹配所有条件或任一条件。

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

   每个路径都应该具有操作和事件节点的组合。

1. 单击这些路径中任一路径末尾的加号( **+** )图标，然后从显示的选项中选择&#x200B;**[!UICONTROL 合并路径]**。

1. 在右侧的节点属性中，选择要合并的路径。

   <!-- ![Journey node - merge paths](./assets/node-merge-select-paths.png){width="600" zoomable="yes"} -->

   此时，路径会被合并，以便选定路径中的人合并到单个路径中，从而继续完成历程。

1. 如果需要，您可以通过导航回合并路径节点属性并清除要删除的任何路径的复选框来取消合并路径。