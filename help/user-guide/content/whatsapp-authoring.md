---
title: WhatsApp创作
description: 在Marketo Optimizer中使用经过批准的Meta模板、个性化令牌和投放设置，为人员历程创建WhatsApp消息。
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
source-git-commit: c7d3546d075f5a58923134231217b2fd10fe4aca
workflow-type: tm+mt
source-wordcount: 801
ht-degree: 1%

---

# WhatsApp创作

使用[!DNL Adobe Marketo Optimizer]将WhatsApp消息发送给其移动设备上的用户。 您可以使用WhatsApp编辑器中的已批准Meta消息模板创建、个性化和预览消息。

在为人员历程创建WhatsApp消息之前，请确保在&#x200B;_[!UICONTROL 管理员]_&#x200B;设置中配置了[WhatsApp渠道](../admin/configuration-channels-whatsapp.md)。

>[!NOTE]
>
>[!DNL Marketo Optimizer]中仅支持&#x200B;_出站_ WhatsApp消息元素。

+++ 支持的消息元素和call-to-action选项

使用此部分中的表作为参考，了解可包含在已批准Meta模板中的出站WhatsApp内容以及可添加到消息中的交互式按钮。

下表总结了支持的报文元素及其要求。

| 消息元素 | 描述 |
| - | - |
| 标头 | 显示在消息正文上方的可选文本。 |
| 文本 | 通过参数支持动态内容。 |
| 图像(JPEG、PNG) | 必须是8位RGB或RGBA格式，且大小必须小于5 MB。 |
| 视频 | 必须为3GPP或MP4，小于16 MB，并由URL托管。 |
| 音频 | 仅适用于响应消息。 必须是AAC、AMR、MP3、MP4音频或OGG格式，托管在URL上，并且小于16 MB。 |
| 文档 | 必须小于100 MB，在URL上托管，并且采用以下格式之一： `.txt`、`.xls`/`.xlsx`、`.doc`/`.docx`、`.ppt`/`.pptx`或`.pdf`。 |
| 正文文本 | 通过参数支持动态内容。 |
| 页脚文本 | 通过参数支持动态内容。 |

下表列出了call-to-action按钮类型以及每个按钮在消息中的行为方式。

| call to action | 描述 |
| - | - |
| 访问网站 | 仅允许一个按钮，并包含变量参数。 |
| 用WhatsApp打电话 | 提供一个按钮，用于直接从消息中打开与指定电话号码的WhatsApp聊天。 |
| 呼叫电话号码 | 提供一个按钮，当用户点按时，该按钮会向指定号码发起电话呼叫。 |

+++

## 在人员历程中添加WhatsApp操作 {#add-whatsapp-journey-action}

>[!IMPORTANT]
>
>**WhatsApp同意管理**：根据Meta的政策和适用法规，所有WhatsApp营销消息必须仅发送给选择接收通信的收件人。 WhatsApp收件人可以随时通过用“选择退出”关键字进行回复来选择退出。 选择退出响应会自动生效，并且将从未来的营销消息受众中删除相应的用户档案。

当您[添加&#x200B;_[!UICONTROL 执行操作]_&#x200B;节点](../marketing/action-nodes.md)并从操作列表中选择&#x200B;**[!UICONTROL 发送WhatsApp]**&#x200B;时，可以在人员历程中设置WhatsApp消息投放。

## 创建WhatsApp消息 {#create-whatsapp-message}

1. 在&#x200B;_[!UICONTROL 执行操作]_&#x200B;面板的底部，单击&#x200B;**[!UICONTROL 创建WhatsApp]**。

1. 在对话框中，为WhatsApp消息输入唯一的&#x200B;**[!UICONTROL Name]**（必需）和&#x200B;**[!UICONTROL Description]**（可选）。

   ![创建新的WhatsApp消息对话框](assets/whatsapp-create-dialog.png){width="400"}

1. 单击&#x200B;**[!UICONTROL 创建]**。

   _WhatsApp设计空间_&#x200B;打开，您可以在其中定义WhatsApp操作并创建用于发送消息的内容。

### 选择操作配置 {#select-actions-configuration}

1. 在&#x200B;_WhatsApp设计空间_&#x200B;中，选择&#x200B;**[!UICONTROL 操作]**&#x200B;选项卡。

1. 对于&#x200B;**[!UICONTROL WhatsApp配置]**，请选择支持营销操作和消息投放设置的配置，以满足您的需求。

   ![创建WhatsApp — 操作选项卡](assets/whatsapp-create-actions-tab.png){width="700" zoomable="yes"}

1. 单击&#x200B;**[!UICONTROL 编辑内容]**&#x200B;以继续查看消息参数和文本。

### 选择消息模板 {#select-message-template}

使用您Meta WhatsApp商业帐户中的预批准消息模板发送WhatsApp消息。 **模板必须由Meta审核和批准**，然后才能在[!DNL Marketo Optimizer]中使用。 要管理和提交模板以供审批，请与您的[!DNL Meta Business Manager]帐户管理员联系。

1. 对于&#x200B;**[!UICONTROL 选择模板类别]**，请选择下列选项之一：

   * 营销
   * 实用工具
   * 身份验证

1. 对于&#x200B;**[!UICONTROL 选择WhatsApp模板]**，为已配置的业务帐户选择批准的模板。

   模板内容会加载到消息编辑器中，并显示模板结构和可用于个性化的任何变量字段。

   ![在预览窗口中加载了消息的WhatsApp选定消息模板](assets/whatsapp-create-select-template.png){width="700" zoomable="yes"}

   系统按类别（_营销_、_实用程序_&#x200B;和&#x200B;_身份验证_）和状态组织模板。 仅&#x200B;**_已批准_**&#x200B;模板可供选择。 有关创建WhatsApp模板的更多信息，请参阅Meta文档中的&#x200B;[_为您的WhatsApp商业帐户创建消息模板_](https://www.facebook.com/business/help/2055875911147364?id=2129163877102343)。

### 图像URL {#image-urls}

如果您的模板包含任何图像，请使用&#x200B;**[!UICONTROL 图像URL]**&#x200B;字段添加媒体URL以替换模板中的任何占位符。 Meta的模板介质只是占位符。 要正确显示图像、音频或视频，您必须使用Adobe Experience Manager或其他源中的外部URL。

### 个性化消息内容 {#personalize-message-content}

批准的WhatsApp模板可以包含您使用配置文件数据或动态值定义的变量占位符。

对于模板中显示的每个变量字段，单击该字段旁边的&#x200B;_个性化_&#x200B;图标（![个性化图标](../assets/do-not-localize/icon-personalize.svg)）。

WhatsApp模板中的![变量](assets/whatsapp-create-variables.png){width="700" zoomable="yes"}

通过对话框可访问人员令牌和系统令牌。 包括标准令牌和自定义令牌。 您可以使用&#x200B;_搜索_&#x200B;栏找到所需的令牌，或者浏览文件夹树查找并选择任何令牌。

定义个性化令牌后，单击&#x200B;**[!UICONTROL 保存]**&#x200B;以保存更改并返回主WhatsApp消息工作区。
