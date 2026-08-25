---
title: 电子邮件渠道配置
description: 创建和管理电子邮件渠道配置，以绑定Marketo Optimizer的发件人身份、子域、IP池、电子邮件类型和URL跟踪。
feature: Administration
role: Admin
source-git-commit: c7d3546d075f5a58923134231217b2fd10fe4aca
workflow-type: tm+mt
source-wordcount: '624'
ht-degree: 0%

---

# 电子邮件渠道配置

渠道配置是将发件人身份、子域、IP池和跟踪设置绑定在一起的中心对象。 历程中的电子邮件操作引用渠道配置，以了解如何发送消息。 在创建配置之前，请完成[子域委派和IP池设置](../start/email-deliverability.md)。

* **渠道：**&#x200B;电子邮件。
* **电子邮件类型：**&#x200B;营销或事务性。 此设置确定是否应用禁止显示规则（营销应用这些规则；默认情况下，事务型消息绕过合法事务型消息的垃圾邮件投诉禁止显示）。
* **标头参数：**&#x200B;来自姓名、电子邮件、回复姓名、回复电子邮件、错误电子邮件。
* **子域：**&#x200B;用于发送的已委派子域。 发件人电子邮件必须使用此子域。
* **IP池：**&#x200B;用于传递消息的IP池。
* **URL跟踪：**&#x200B;启用或禁用点击并打开跟踪；配置跟踪域。
* **标记：**&#x200B;组织和搜索标记。

## 创建电子邮件渠道配置 {#create-email-channel-configuration}

>[!PREREQUISITES]
>
>* 必须至少委派一个[子域](../start/email-deliverability.md#subdomain-delegation)并且处于活动状态。
>* 必须为您的组织至少分配一个[IP池](../start/email-deliverability.md#ip-pools)。
>* 您需要管理员角色。
>* 查看[当前限制](../start/email-deliverability.md#limitations) — Beta中没有专用IP池。

1. 在[!DNL Adobe Marketo Optimizer]左侧导航中，展开&#x200B;**[!UICONTROL 管理]**&#x200B;并选择&#x200B;**[!UICONTROL 渠道]**。
1. 在面板中，展开&#x200B;**[!UICONTROL 电子邮件设置]**&#x200B;并选择&#x200B;**[!UICONTROL 渠道配置]**。
1. 单击&#x200B;**[!UICONTROL 创建渠道配置]**。
1. 输入名称（例如，_Contoso B2B Marketing — North America_）和可选的描述。
1. 选择&#x200B;**[!UICONTROL 电子邮件]**&#x200B;渠道。
1. （可选）选择标记以对配置进行分类。
1. 在&#x200B;**[!UICONTROL 电子邮件类型]**&#x200B;部分中，选择“营销”或“事务性”。
1. 在&#x200B;**[!UICONTROL 子域]**&#x200B;部分中，选择之前委派的子域。
1. 在&#x200B;**[!UICONTROL IP池]**&#x200B;部分中，选择一个活动的IP池。

   在Beta，只有共享IP池可用。 您可以将鼠标悬停在IP上以查看PTR记录。

1. 配置&#x200B;**[!UICONTROL 标头参数]**：
   * 源名称（例如“Contoso Marketing”）。
   * 发件人电子邮件 — 必须使用选定的子域（例如，`marketing@mail.contoso.com`）。
   * 回复姓名和回复电子邮件 — 如果为空，则默认为&#x200B;_From_。
   * 错误电子邮件 — 接收未送达通知的地址。
1. 启用&#x200B;**[!UICONTROL URL跟踪]**&#x200B;并选择跟踪域。
1. 单击&#x200B;**[!UICONTROL 提交]**。

>[!NOTE]
>
>提交后，系统会运行验证：子域状态、MX记录、SPF/DKIM/DMARC校准、IP池准备情况、FBL注册。 配置将通过“草稿”→“处理”→“活动”。

>[!NOTE]
>
>如果验证失败，配置将移至&#x200B;**[!UICONTROL 失败]**&#x200B;状态。 打开配置以查看失败原因 — 常见原因是MX记录验证失败、池中的IP与配置不匹配或DMARC未对齐。 解决并重新提交。

## 编辑或删除渠道配置 {#edit-channel-configuration}

您可以在创建后编辑渠道配置，但具有一个重要限制： **无法更改渠道。** 配置已绑定到其通道。

编辑正在使用的配置时：

* **对于已发布的历程：**，此更改将在下次循环或下次执行时应用。 在执行中，执行将继续使用以前的设置。
* **对于事务性或实时消息：**&#x200B;更改会在大约五分钟内传播。

>[!WARNING]
>
>删除渠道配置是永久性的。 您无法删除活动历程引用的配置。 先删除或重新分配所有电子邮件操作。

要删除配置，请先删除或更新在[向历程](../marketing/email-channel.md#define-email-properties)添加电子邮件中引用该配置的每个电子邮件操作。 [!DNL Marketo Optimizer]不删除活动历程当前使用的配置。

## 多渠道配置 {#multiple-channel-configurations}

大多数B2B组织都使用多个渠道配置来分隔品牌、区域或发送类型。 常见模式：

* 每个业务部门的独立营销配置（例如，*BU-A营销*、*BU-B营销*）。
* 用于产品或合同通知的专用事务型配置，其电子邮件类型为“事务型”。
* 使用特定于区域的子域（例如，`mail.eu.contoso.com`、`mail.us.contoso.com`）的区域特定配置与区域ISP和合规性保持一致。

>[!TIP]
>
>使用清晰的结构化约定命名您的配置 — 例如： *[品牌] - [地区] - [类型]*。 一旦您拥有十几个或更多配置，这一点就变得至关重要。
