---
title: Personalization编辑器
description: 了解如何使用Marketo Optimizer中的个性化编辑器选择、排列、自定义和验证电子邮件、WhatsApp消息、登陆页面和URL字段中的配置文件属性令牌。
feature: Content Design Tools
role: User
source-git-commit: 75b481faf0d66210329f95c8afabdfa59e7bcb79
workflow-type: tm+mt
source-wordcount: '1002'
ht-degree: 12%

---

# 个性化编辑器

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_personalization_editor"
>title="关于个性化编辑器"
>abstract="个性化编辑器让您可以选择、排列、自定义和验证轮廓属性，创建个性化内容。"

个性化编辑器是[!DNL Marketo Optimizer]中个性化的核心。 您可以随时随地使用这些动态内容 — 在电子邮件、WhatsApp消息、登陆页面和URL字段中。

在个性化编辑器界面中，您可以选择、排列、自定义和验证配置文件属性以创建个性化内容。

![个性化表达式编辑器](./assets/personalization-editor.png){width="700" zoomable="yes"}

>[!NOTE]
>
>在此Beta版本中，个性化编辑器中仅提供配置文件属性。 帐户级别的个性化和自定义对象数据不可用。 查看[当前限制](../marketing/email-channel.md#limitations)。

您可以使用&#x200B;_个性化_ （ ![个性化图标](../assets/do-not-localize/icon-personalize.svg) ）图标在任意字段中添加个性化。 展开以下部分，了解更多详细信息。

+++电子邮件和WhatsApp消息

在[电子邮件](./email-authoring.md#personalize-content)和[WhatsApp消息](./whatsapp-authoring.md#personalize-message-content)中，可以在不同位置添加个性化设置，例如电子邮件中的&#x200B;**[!UICONTROL 主题行]**&#x200B;字段或批准的WhatsApp模板中的动态参数。

还可以在内容的其他部分添加该标记，包括电子邮件正文文本、标头和按钮URL。

+++

+++内容设计空间

编辑可视内容时，您可以使用上下文工具栏中的图标在大多数文本元素中添加个性化。

<!-- ![](assets/perso_insert.png) -->

+++

+++URL

[!DNL Marketo Optimizer]还允许您个性化邮件中的&#x200B;**URL**。 个性化 URL 可将收件人引导至网站的特定页面，或引导至个性化的微型网站，具体取决于轮廓属性。

<!-- ![](assets/perso-url.png){width="50%"} -->

>[!NOTE]
>
>URL个性化可用于以下类型的链接： **外部链接**、**退订链接**&#x200B;和&#x200B;**选择退出**。

+++

+++电子邮件配置

创建[电子邮件渠道配置](../admin/email-channel-configuration.md)时，您可以为子域、标题和URL跟踪参数定义个性化值。

+++

## 添加个性化 {#add}

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_perso_editor_autocomplete"
>title="自动完成"
>abstract="切换该选项可让系统在您键入时自动建议并完成代码。 此功能仅适用于 HTML 和文本格式，支持轮廓属性。 如果通过切换禁用，编辑器将提供原生 HTML 代码自动完成。"

中央工作区是您构建个性化语法的位置。 若要使用属性来个性化您的消息，请将其定位到左侧导航窗格中，然后单击`+`按钮以将其添加到表达式中。

<!-- ![](assets/personalization-add-attribute.png) -->

`+`图标旁边的省略号菜单允许您获取每个属性的更多详细信息，并将最常用的属性添加到收藏夹。 添加到收藏夹的属性可从导航窗格中的&#x200B;**[!UICONTROL 收藏夹]**&#x200B;菜单访问。

>[!NOTE]
>
>默认情况下，属性窗格仅显示填充的属性。 要显示所有属性，请在属性窗格中选择&#x200B;**[!UICONTROL 设置]**&#x200B;按钮，然后关闭&#x200B;**[!UICONTROL 仅显示填充的属性]**&#x200B;选项。

此外，您可以定义在字符串类型配置文件属性为空时显示的默认回退文本。 为此，请单击属性旁边的省略号按钮，然后选择&#x200B;**[!UICONTROL 插入后备文本]**。 写入配置文件属性值为空时默认显示的文本，然后单击&#x200B;**[!UICONTROL 添加]**。

<!-- ![](assets/attribute-details.png) -->

例如，您可以用`{{profile.firstName}}`以名字迎接每个收件人，并在缺少值时进行回退： `{{profile.firstName | default: "there"}}`。

## 表达式编辑选项 {#options}

中央工作区提供了各种工具来帮助您编写个性化表达式。

<!-- ![](assets/perso-workspace.png) -->

可用选项包括：

1. **[!UICONTROL 查找]** / **[!UICONTROL 查找并替换]**：搜索表达式并自动替换部分代码。
1. **[!UICONTROL 撤消]** / **[!UICONTROL 重做]**：撤消/重做上一个操作。
1. **[!UICONTROL 自动完成]**：在您键入时自动建议并完成代码。 此功能仅适用于 HTML 和文本格式，支持轮廓属性。 如果通过切换禁用，编辑器将提供原生 HTML 代码自动完成。

   <!-- ![](assets/perso-complete.png){width="70%" align="center" zoomable="yes"} -->

1. **[!UICONTROL HTML]** / **[!UICONTROL JSON]** / **[!UICONTROL 文本]**：标识代码格式。 这使系统能够根据所选语言调整验证和自动完成功能。
1. **[!UICONTROL 验证]**：检查表达式的语法。
1. **[!UICONTROL 字体大小]**：调整编辑器内内容的字体大小，以提高可读性。
1. **[!UICONTROL 自动换行]**：启用或禁用自动换行，从而允许在编辑器中单行显示或自动换行的长表达式。 选项包括：
   * **关**（默认） — 无自动换行。 长线延伸到编辑器视图之外，需要水平滚动。
   * **On** — 以编辑器的宽度换行。
   * **自动换行** — 当行达到80个字符时换行。
   * **绑定** — 以编辑器宽度或80个字符（以较小者为准）换行。
1. **[!UICONTROL Picks]**：将属性显示为紧凑的“Picks”，通过隐藏长属性路径来提高可读性。 单击属性以显示其完整路径。

   >[!NOTE]
   >
   >此选项仅适用于配置文件属性。

在导航窗格中，提供其他功能以帮助您构建个性化表达式。

<!-- ![](assets/perso-features.png) -->

* **[!UICONTROL 辅助函数]** — 辅助函数允许您对数据执行操作，例如计算、数据格式或转换、条件，并在个性化上下文中处理这些操作。

* **[!UICONTROL 收藏夹]** — 已添加到收藏夹的属性将显示在此列表中。 这允许您快速访问最常用的项目。 若要向收藏夹添加属性，请单击省略号菜单，然后选择&#x200B;**[!UICONTROL 添加到收藏夹]**。

Co-worker可以从纯语言描述生成Handlebars表达式，解释现有表达式并确定潜在问题。

当个性化表达式准备就绪时，单击&#x200B;**[!UICONTROL 确认]**&#x200B;或&#x200B;**[!UICONTROL 插入]**&#x200B;以将其添加到您的内容中。

## 验证机制 {#validation-mechanisms}

当您单击&#x200B;**[!UICONTROL 确认]**&#x200B;或&#x200B;**[!UICONTROL 插入]**&#x200B;以关闭编辑器时，表达式的验证将自动运行。 您还可以单击&#x200B;**[!UICONTROL 验证]**&#x200B;以在关闭前检查您的个性化语法。

有关阻止历程激活的内容警报，请参阅[验证电子邮件内容](./email-authoring.md#validation)。

展开以下部分可查看验证个性化设置时可能发生的常见错误。

+++常见错误

* **找不到“XYZ”路径**

当您引用未在架构中定义的字段时，会发生此错误。

在这种情况下，**firstName1**&#x200B;未定义为配置文件架构中的属性：

```handlebars
{{profile.firstName1}}
```

* **变量“XYZ”的类型不匹配。 应为数组。 找到字符串。**

当您尝试对字符串而不是数组进行迭代时，会发生此错误。

在这种情况下，**jobTitle**&#x200B;是字符串，而不是数组：

```handlebars
{{#each profile.jobTitle as |item|}}
  {{item}}
{{/each}}
```

* **无效的Handlebars语法。 找到`'[XYZ}}'`**

当使用无效的Handlebars语法时，会发生此错误。

```handlebars
{{[profile.firstName}}
```

+++
