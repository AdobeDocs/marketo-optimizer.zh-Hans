---
title: 按角色个性化电子邮件内容
description: 使用Marketo Optimizer中的Content Personalization技能将电子邮件转换为基于角色、基于数据的变体。 个性化或分析电子邮件。
source-git-commit: 75b481faf0d66210329f95c8afabdfa59e7bcb79
workflow-type: tm+mt
source-wordcount: '1236'
ht-degree: 0%

---


# 按角色个性化电子邮件内容

通过&#x200B;_Content Personalization_&#x200B;技能，可以将一封电子邮件转换为基于角色、基于数据的变体，因此您无需为每个受众构建单独的电子邮件。 该技能不是在活动后发送一条消息，而是将受众解析为[派生角色](../audiences/personas.md)同类群组，显示洞察并生成个性化的变体。 每个变体都会另存为一封电子邮件中的条件内容，因此在历程发送时，每个人都会自动收到与其角色匹配的版本。

* **技能** - `content-personalization`
* **调用** — 从[聊天界面](./chat-interface.md)描述新电子邮件的目标受众，或选择&#x200B;**[!UICONTROL 个性化此电子邮件]**&#x200B;或&#x200B;**[!UICONTROL 在[发送电子邮件节点](../marketing/action-nodes.md)中的现有电子邮件上分析此电子邮件]**
* **从**&#x200B;读取/写入 — [!DNL Marketo Optimizer]

## 重要概念 {#key-concepts}

| 术语 | 定义 |
|---|---|
| **角色同类群组** | 一组共享[派生角色](../audiences/personas.md)的人员，如&#x200B;_CXO/EVP_&#x200B;或&#x200B;_个人参与者_。 |
| **区段** | 由任何标准（如角色、行业或参与层）定义的一组人员。 角色同类群组是由共享派生角色专门定义的区段。 |
| **目标组** | 您用自然语言描述的受众。 该技能将其解析为匹配的角色同类群组。 |
| **Insight** | 从您自己的数据中得出的关于消息传送、定位或基调的数据通知发现，最适合一个角色同类群组。 |
| **变体** | 您选择个性化的电子邮件部分的个性化版本，为一个角色同类群组生成。 |
| **AI个性化电子邮件** | 将每个变体捆绑为[条件内容](../content/conditional-content.md)块的单个已保存电子邮件。 |
| **电子邮件审核** | 针对每个目标组区段审查现有电子邮件，显示哪些内容能够引起共鸣，以及在您进行个性化之前需要为每个角色改进哪些内容。 |

## 先决条件 {#prerequisites}

* 在启用了同事的情况下访问[!DNL Marketo Optimizer]。
* 在您的数据中解析了[派生角色](../audiences/personas.md)。 该技能依赖这些分类来构建角色同类群组。 计划在未来的版本中提供自定义角色支持。
* 有足够多的历史数据用于见解。 如果某个角色同类群组没有洞察信息，则该技能会告知您数据不足，并回退到该角色的常规最佳实践。
* [电子邮件模板](../content/templates.md)或&#x200B;[_发送电子邮件_&#x200B;操作节点](../marketing/action-nodes.md)引用的现有电子邮件。
* 包含用于投放个性化电子邮件的&#x200B;_发送电子邮件_&#x200B;操作节点的[人员历程](../marketing/person-journeys.md)。

## 从模板创建和个性化电子邮件 {#create-personalize-from-template}

此流程会创建新的电子邮件，并在同一对话中对其进行个性化设置。

1. **提供内容。** 上传内容摘要，或以自然语言描述您想要的内容。

1. 从模板库中选择&#x200B;**一个[模板](../content/templates.md)**。

1. **审阅草稿。**

   同事将您的内容映射到模板并生成草稿电子邮件。 您可以内联编辑基本文本。

   >[!WARNING]
   >
   >创作期间仅可在内联编辑基本文本。 若要进行高级编辑，请保存电子邮件并在[可视设计空间](../content/email-authoring.md)中将其打开。

1. **用自然语言描述目标组**。

1. **查看已解析的角色同类群组**。

   同事会检查您的数据，并返回与您的描述匹配的角色同类群组，并为每个同类群组指定一个计数。 修改目标组描述，并在需要时重试。

1. **确认目标组**。

   然后，同事检索每个已解析角色同类群组的见解。

1. **选择要个性化的部分**，如主题行或正文部分，并查看生成的变体。

   如果变体不适合，则重新生成变体。 角色同类群组的数量不是固定的。 这取决于您的目标组和数据。

1. **保存电子邮件**。

   所有变体都存储在一封AI个性化电子邮件中，而不是作为单独的电子邮件进行。

<!-- screenshot: Coworker chat panel showing the resolved persona cohorts with counts, and the "Personalized variants" review grid -->

## 分析现有电子邮件 {#analyze-existing-email}

在引用现有电子邮件的历程&#x200B;[_发送电子邮件_&#x200B;节点](../marketing/action-nodes.md)上，**[!UICONTROL 执行操作]**&#x200B;面板显示具有两个选项的电子邮件名称：**[!UICONTROL 个性化此电子邮件]**&#x200B;和&#x200B;**[!UICONTROL 分析此电子邮件]**。

<!-- screenshot: Send Email node "Take an action" panel showing the email name and the Personalize this email / Analyze this Email options -->

选择&#x200B;**[!UICONTROL 分析此电子邮件]**&#x200B;以运行电子邮件审核：

1. **根据角色描述要个性化的目标组**。

   例如，_营销职位人员_&#x200B;或&#x200B;_领导职位人员_。

1. **查看电子邮件审核。**

   同事将您的描述解析为角色区段，并显示一张&#x200B;**电子邮件审核**&#x200B;卡片，其中列出了每个区段，然后针对每个区段查看电子邮件，以突出显示引起共鸣的内容和需要改进的内容。

1. 同事询问下一步要做什么，包括&#x200B;**[!UICONTROL 查看逐节审核]**&#x200B;和&#x200B;**[!UICONTROL 个性化此电子邮件]**。

1. 选择&#x200B;**[!UICONTROL 查看逐节审核]**&#x200B;以打开&#x200B;**_电子邮件分析_**&#x200B;视图，其中包含角色选择器和每个部分的特定建议。

   每个部分显示推荐的更改数，每个角色显示推荐计数，如`4 recommendations for SVP/VP`。 您也可以在聊天中输入&#x200B;_个性化_，直接应用推荐。

1. 从审核中，选择&#x200B;**[!UICONTROL 个性化此电子邮件]**&#x200B;以应用见解并生成变体。

   请参阅以下部分，[_个性化现有电子邮件_](#personalize-existing-email)。

<!-- screenshot: Email analysis view with persona selector, per-section "N changes" badges, and "what needs work" recommendations -->

## 将现有电子邮件个性化 {#personalize-existing-email}

在&#x200B;_发送电子邮件_&#x200B;操作节点中选择&#x200B;**[!UICONTROL 个性化此电子邮件]**，或继续进行[电子邮件审核](#analyze-existing-email)，以个性化您已经构建的电子邮件。

1. **查看已解析的角色同类群组。**

   同事会检查您的数据，并返回与您的描述匹配的角色同类群组，并为每个同类群组指定一个计数。 修改目标组描述，并在需要时重试。

   如果您是通过电子邮件审核到达此步骤的，Co-worker将直接从审核见解继续。

1. **选择要在电子邮件预览中个性化的部分**，如主题行和特定内容部分，然后进行确认。

1. **查看生成的变体。**

   除了角色之外，各种变体也可能因行业而异，例如，医疗保健行业中的CXO与金融服务行业中的CXO相比。 同事提供&#x200B;**[!UICONTROL 个性化变体]**&#x200B;网格，每个角色同类群组一张卡片，每张卡片都具有主题行、标题、正文和&#x200B;**[!UICONTROL 预览]**&#x200B;选项。

   选择信息卡上的&#x200B;_信息_&#x200B;图标可查看该变体背后的insight（它所基于的角色以及塑造该变体的参与insight），并根据需要重新生成变体。

   您可以按角色筛选网格。

1. **保存集。**

   单击&#x200B;**[!UICONTROL 保存]**&#x200B;并确认。 同事确认电子邮件现在可以在AI库中使用，然后询问是否将更改同时应用于原始电子邮件，以就地更新原始电子邮件。

<!-- screenshot: "Personalized variants" grid showing persona cards with subject, headline, body, Preview, and the info-icon insight tooltip -->

## 已保存输出并在历程中使用 {#saved-output}

无论您从哪个流程开始，个性化都会生成一个存储在AI库中的&#x200B;**AI个性化电子邮件**。 该电子邮件包含[条件内容](../content/conditional-content.md)个由角色键入的块。 若要编辑节，请在[可视化设计空间](../content/email-authoring.md)中打开它，并预览每个角色键控块的解析方式，请使用&#x200B;**[!UICONTROL 模拟内容]**。

要在历程中使用电子邮件，请添加[发送电子邮件节点](../marketing/action-nodes.md)并选择&#x200B;**[!UICONTROL AI个性化电子邮件]**&#x200B;而不是&#x200B;**[!UICONTROL 创建电子邮件]**，然后选择保存的电子邮件。 照常将您的配置和业务规则应用到节点。

<!-- screenshot: Send Email node configuration with "AI Personalized Emails" selected and the saved email applied -->

## 运行时行为 {#run-time-behavior}

您在历程中选择单个AI个性化电子邮件，而不是为每个受众选择一个变体。 当历程运行时，电子邮件会自动解析为与每个收件人的角色匹配的变体。 您不会为每个收件人选择变体。

## 限制 {#limitations}

| 限制 | 详细信息 |
|---|---|
| **自定义角色** | 尚不受支持。 该技能仅对来自现成[派生角色](../audiences/personas.md)的角色同类群组进行分类。 |
| **分析的数据不足** | 如果您的数据不支持面向角色同类群组的insight，则该技能会指出这一点并回退到该角色的一般最佳实践。 |
| **在创作过程中内联编辑** | 当您[从模板](#create-personalize-from-template)创建并个性化电子邮件时，只能内联编辑基本文本。 高级编辑需要[可视设计空间](../content/email-authoring.md)。 |
| **需要起始点** | 个性化电子邮件需要模板或“发送电子邮件”节点引用的现有电子邮件。 |
