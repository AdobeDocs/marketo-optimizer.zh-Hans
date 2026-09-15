---
title: 侦听事件节点
description: 在Marketo Optimizer中配置侦听事件节点 — 设置事件触发器，应用可选过滤器，并在发生活动或数据更改时提升人员。
TQID: 'https://experienceleague.adobe.com/6v3i6M-Hhr2RAWrS68WaEVb8VJEzJZbD7vXOJOsjgc8'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
source-git-commit: cc98b02f4273c5df2e27b52acd1239f0f0bf8aa0
workflow-type: tm+mt
source-wordcount: '1139'
ht-degree: 6%
---
# 侦听事件节点

要在事件发生时将受众推进到历程的下一步，请添加&#x200B;_侦听事件_&#x200B;节点。

## 事件触发器 {#event-triggers}

定义触发历程节点并将受众成员向前移动的事件标准。

| 触发器 | 描述 |
| -------- | ----------- |
| Brand Concierge | 与[!DNL Brand Concierge]接洽的潜在客户的活动。 |
| 电子邮件 | 潜在客户的电子邮件活动，包括发送、投放和参与。 |
| 活动 | 针对潜在客户的交互式网络研讨会活动，包括注册、出席和互动。 |
| 商机 | 与商机或客户关联的商机记录相关的活动。 |
| 销售应用程序 | 与[!DNL Sales Qualifier]或[!DNL Marketo Sales Insights]相关的潜在客户活动。 |
| 其他 | 不属于预定义类别的活动，为自定义或其他事件触发器提供了灵活性。 |

>[!BEGINSHADEBOX]

**触发器支持的Marketo Engage活动**

在触发事件时，[!DNL Marketo Optimizer]支持来自作为数据源连接的[!DNL Marketo Engage]实例的活动。

>[!NOTE]
>
>只能有一个[!DNL Marketo Engage]实例作为数据源，并在预配[!DNL Marketo Optimizer]实例时对其进行预配置。

您可以针对以下[!DNL Marketo Engage]活动生成事件触发器：

* [!UICONTROL 填写Marketo Engage表单] — 当潜在客户提交指定的[!DNL Marketo Engage]表单时触发。
* [!UICONTROL 访问Marketo Engage网页] — 当具有Munchkin跟踪Cookie的潜在客户访问指定的网页时触发。
* [!UICONTROL 单击Marketo Engage网页上的链接] — 当潜在客户单击已安装[!DNL Marketo Engage] Munchkin跟踪代码的网页上的跟踪超链接时触发。
* [!UICONTROL Marketo Engage电子邮件已投放] — 当商机的邮件服务器(MX)向[!DNL Marketo Engage]发送服务器返回成功响应（250 OK消息）时触发。
* [!UICONTROL Marketo Engage电子邮件退回] — 当Target邮件服务器将已发送的[!DNL Marketo Engage]电子邮件拒绝为永久错误（如无效用户或未知域）时触发。
* [!UICONTROL Marketo Engage电子邮件软退回] — 当Target邮件服务器将已发送的[!DNL Marketo Engage]电子邮件作为临时问题（如服务器忙或邮箱已满）拒绝时触发。 [!DNL Marketo Engage]在标记问题之前通过MX服务器自动重试软退回，次数最多三次。
* [!UICONTROL 取消订阅Marketo Engage电子邮件] — 当潜在客户选择退出非运营营销电子邮件时触发。 触发时，[!DNL Marketo Engage]会自动将商机的`Unsubscribed`字段值更新为`true`，禁止在未来发送标准电子邮件时发送它们。
* [!UICONTROL 打开Marketo Engage电子邮件] — 当潜在客户打开跟踪的[!DNL Marketo Engage]电子邮件时触发。
* [!UICONTROL 单击Marketo Engage电子邮件中的链接] — 当潜在客户单击[!DNL Marketo Engage]电子邮件中的任何链接（或特定的受限链接）时触发。

>[!ENDSHADEBOX]

## 事件过滤器 {#event-filters}

您可以包括筛选，以根据各种条件限制匹配的事件触发器：

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

**过滤器支持的Marketo Engage活动**

筛选触发的事件时，[!DNL Marketo Optimizer]支持来自作为数据源连接的[!DNL Marketo Engage]实例的活动。

>[!NOTE]
>
>只能有一个[!DNL Marketo Engage]实例作为数据源，并在预配[!DNL Marketo Optimizer]实例时对其进行预配置。

您可以针对以下[!DNL Marketo Engage]个活动构建事件过滤器：

* [!UICONTROL 已填写Marketo Engage表单] — 匹配在其非过期活动日志中任何时候已完成特定[!DNL Marketo Engage]表单的潜在客户。
* [!UICONTROL 已访问Marketo Engage网页] — 匹配已在您的网站或[!DNL Marketo Engage]登陆页面上查看特定URL的潜在客户。 它直接依赖于您网站上安装的Munchkin跟踪代码。
* [!UICONTROL 已单击Marketo Engage网页上的链接] — 匹配已单击跟踪页面上的特定链接或资源的潜在客户。
* [!UICONTROL 已发送Marketo Engage电子邮件] — 匹配[!DNL Marketo Engage]尝试向其发送特定电子邮件的潜在客户，考虑硬退回或服务器接受之前的部署操作。
* [!UICONTROL 已投放Marketo Engage电子邮件] — 与邮件服务器(MX)向[!DNL Marketo Engage]发送服务器返回成功响应（250 OK消息）的潜在客户匹配。
* [!UICONTROL Marketo Engage电子邮件退回] — 匹配在特定电子邮件发送或时间范围内遇到硬退回（永久投放失败）的潜在客户。
* [!UICONTROL Marketo Engage电子邮件软退回] — 匹配其电子邮件遇到临时投放失败（如收件箱已满或服务器已脱机）而不是永久硬退回的潜在客户。
* [!UICONTROL 取消订阅Marketo Engage电子邮件] — 匹配选择退出非运营营销电子邮件的潜在客户。 发生这种情况时，[!DNL Marketo Engage]会自动将商机的`Unsubscribed`字段值更新为`true`，从而禁止将来发送标准电子邮件时发送它们。
* [!UICONTROL 已打开Marketo Engage电子邮件] — 匹配已打开跟踪的[!DNL Marketo Engage]电子邮件的潜在客户。
* [!UICONTROL 在Marketo Engage电子邮件中点击的链接] — 匹配点击了[!DNL Marketo Engage]电子邮件中的任何链接（或特定链接）的潜在客户。

>[!ENDSHADEBOX]

## 添加事件节点 {#add-event-node}

1. 导航到历程画布。

1. 单击路径上的加号( **+** )图标，然后选择&#x200B;**[!UICONTROL 侦听事件]**。

   ![单击历程路径上的“添加”图标](./assets/person-journey-canvas-add-node.png){width="200"}

1. 在右侧的节点属性中，单击&#x200B;**[!UICONTROL 添加事件条件]**。

1. 在&#x200B;_[!UICONTROL 编辑事件]_&#x200B;对话框中，添加一个事件并设置要与触发器匹配的约束。

   将事件触发器拖放到生成器空间中并设置定义。 为要用于优化事件匹配的每个约束单击&#x200B;**[!UICONTROL 添加约束]**。

   ![编辑事件 — 事件触发器](./assets/edit-event-triggers.png){width="700" zoomable="yes"}

   您可以添加多个要匹配的事件。 第一个符合条件事件会前进历程中的人员配置文件。

1. （可选）选择&#x200B;**[!UICONTROL 筛选器]**&#x200B;选项卡并为触发器添加筛选条件。

   将筛选器拖放到生成器空间中，并设置定义。 为要用于优化筛选器匹配的每个约束单击&#x200B;**[!UICONTROL 添加约束]**。

   ![编辑事件 — 事件筛选](./assets/edit-event-filters.png){width="700" zoomable="yes"}

1. 单击&#x200B;**[!UICONTROL 保存]**。

   您可以随时单击&#x200B;**[!UICONTROL 编辑事件]**&#x200B;以更改节点的事件条件。

1. 如果需要，请设置&#x200B;**[!UICONTROL Timeout]**&#x200B;选项以限制侦听事件的时间段。

   >[!NOTE]
   >
   >该历程在超时后结束，除非您定义了一个超时路径，您可以在其中添加其他节点。

   启用&#x200B;**[!UICONTROL 超时]**&#x200B;选项，并选择历程在超时之前等待事件发生的持续时间。

   为侦听事件历程节点启用了![超时选项](./assets/person-journey-event-node-timeout.png){width="550" zoomable="yes"}

   您可以选择在此处结束路径，或通过设置其他路径而采取不同的操作。 要在历程中创建一个新路径，以便在不发生事件时添加适用于用户档案的操作和事件，请选中&#x200B;**[!UICONTROL 设置超时路径]**&#x200B;复选框。
