---
title: C2PA元数据
description: 了解Adobe Marketo Optimizer如何自动将C2PA元数据应用于通过创作AI生成的图像，以及这对于您的内容意味着什么。
feature: Assets, Content
role: User
source-git-commit: c7d3546d075f5a58923134231217b2fd10fe4aca
workflow-type: tm+mt
source-wordcount: '547'
ht-degree: 0%

---

# C2PA元数据

营销机构比以往任何时候都更关注内容透明度、人工智能披露，以及防止资产被篡改。 Adobe的Content Authenticity Initiative (CAI)构建符合[内容来源和授权联盟](https://c2pa.org/specifications/specifications/1.1/specs/C2PA_Specification.html#_trust_model) (C2PA)技术标准的工具。 _C2PA元数据_&#x200B;是加密的、显示篡改的信息，可帮助查看者了解内容的历程并确保品牌资产的完整性。 此信息包括：

* 发行者或签名者 — 关于发行数字签名以证明或签署资产的实体或公司的信息。
* 问题日期 — 将C2PA元数据应用于资源的日期。
* 信用和使用 — 有关资产制作者的信息，包括名称、社交媒体句柄或其他身份相关信息。
* 进程 — 对资产进行任何编辑或修改的记录。
* 设备详细信息 — 有关用于创建或编辑资产的应用程序或设备的信息。
* 使用的AI工具 — 如果使用创作AI创建资产，则可能会包含所使用的模型的名称。
* 其他相关信息 — 还包括其他数据，以帮助提供有关资产历史记录的更多上下文。

有关资产历史记录的全面信息，您可以使用Adobe Content Authenticity [检查工具](https://contentauthenticity.adobe.com/inspect)。

C2PA元数据会随图像文件一起保留。 使用创作AI生成或编辑的图像上传到[!DNL Adobe Marketo Optimizer]或从导出时，其C2PA元数据将保留。

>[!NOTE]
>
>某些将图像导入内容的方法(例如从PDF或从嵌入的(base64)源中提取图像)可能不会保留原始C2PA元数据。 在这些情况下，无法从源中读取C2PA元数据，并且不会为结果创建任何元数据。

>[!BEGINSHADEBOX]

## 通过渠道的C2PA元数据持久性 {#channels}

当您将图像包含在电子邮件或WhatsApp消息中时，也会保留已投放图像的C2PA元数据：

* **电子邮件** — 当您使用&#x200B;_发送电子邮件_&#x200B;历程操作时，请将该图像从&#x200B;_Assets_&#x200B;库添加到您的电子邮件内容。 在发送电子邮件时，收件人可以从邮件中下载图像，并且C2PA元数据保持不变。
* **WhatsApp** — 将图像添加到您的Meta商业帐户的WhatsApp消息模板中。 您可以直接从系统中添加它，或从&#x200B;_Assets_&#x200B;库下载图像文件。 使用此模板进行&#x200B;_发送WhatsApp_&#x200B;历程操作。 在传递WhatsApp消息时，收件人可以从消息中下载图像，并且C2PA元数据是完整的。

>[!ENDSHADEBOX]

## 图像生成 {#generate}

>[!INFO]
>
>围绕创新型人工智能透明度的新法律正在出现，Adobe正在努力满足跨司法辖区的适用要求。 C2PA元数据是Adobe用于满足这些法规要求的源工具。

当您使用创作AI为[!DNL Marketo Optimizer]中的电子邮件内容创建图像时，C2PA元数据会自动附加到生成的图像，您无需执行任何操作。 创作AI工具为具有现有元数据（包括原始源）的图像变体生成一个组合的C2PA元数据元素。

>[!NOTE]
>
>[!DNL Marketo Optimizer]当前不支持手动图像编辑操作。 这些操作的C2PA元数据工作流目前不适用。
