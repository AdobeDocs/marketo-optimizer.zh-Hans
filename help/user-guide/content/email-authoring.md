---
title: 电子邮件内容
description: 了解如何使用可视画布、拖放工具、Adobe导入和可重用模板，在HTML Marketo Optimizer中撰写和设计电子邮件内容。
source-git-commit: 75b481faf0d66210329f95c8afabdfa59e7bcb79
workflow-type: tm+mt
source-wordcount: '2287'
ht-degree: 2%

---

# 电子邮件内容创作

在[!DNL Adobe Marketo Optimizer]中，电子邮件设计空间提供了一个可视化画布，营销人员可在其中撰写电子邮件。 左侧和顶部面板中的电子邮件设计工具（结构、内容组件、模板、片段等）支持通过拖放从头开始构建。 您还可以选择从模板开始，粘贴原始HTML，或从可重用可视片段组合消息。

>[!IMPORTANT]
>
>有关子域的管理员设置、身份验证、IP池和电子邮件通道配置，请参阅[电子邮件可投放性](../start/email-deliverability.md)和[电子邮件通道配置](../admin/email-channel-configuration.md)。

在[!DNL Marketo Optimizer]中，每封电子邮件都与人员历程中的&#x200B;_[!UICONTROL 发送电子邮件]_&#x200B;操作相关联。 从历程设计到电子邮件定义的完整工作流发生在一个连续的体验中。 当您[将&#x200B;_发送电子邮件_&#x200B;节点](../marketing/action-nodes.md#add-an-action-node)添加到人员历程时，单击&#x200B;**[!UICONTROL 创建电子邮件]**&#x200B;以开始此过程。 首先，定义电子邮件的操作和内容设置。 单击&#x200B;**[!UICONTROL 编辑电子邮件正文]**&#x200B;以启动电子邮件内容设计空间，您可以在其中从以下选项中选择希望如何设计电子邮件：

* [使用可视化设计界面从头开始设计电子邮件](#design-from-scratch)。 在空白画布上使用拖放操作，通过组件构建电子邮件布局组件。 此方法最适合创建新模板或一次性电子邮件。

* [将现有HTML内容](#import-html-content)导入代码编辑器或与可视画布并排工作。

* [从内置或自定义电子邮件模板列表中选择现有模板](#templates)。 此方法最适合可重复电子邮件用例。

<!-- * Upload a design prototype (JPG, PNG, PDF, or Figma export) and have Coworker convert it into a responsive HTML email. (Image to HTML (Img2HTML) -->

![创建您的电子邮件页面](./assets/email-design-create-your-email.png){width="800" zoomable="yes"}

## 电子邮件设计工具 {#email-design-tools}

* **顶部工具栏：**&#x200B;保存，返回，切换到代码编辑器，预览控件。
* **左侧面板：**&#x200B;结构（列布局）、内容（文本、按钮、图像、分隔符、社交、HTML）、片段、模板、导航树（电子邮件的DOM样式层次结构）。
* **中心画布：**&#x200B;带有桌面和移动设备预览的WYSIWYG编辑器。
* **右侧面板：**&#x200B;当前选定组件的设置和样式，包括内容属性、背景、边框、填充和个性化。

>[!BEGINSHADEBOX]

## 电子邮件设计最佳实践 {#design-best-practices}

遵循HTML和CSS最佳实践有助于确保跨电子邮件客户端进行一致的呈现。

| 方法 | 指引 |
| -------- | -------- |
| **推荐** | 基于表的静态布局· HTML表和嵌套表·模板宽度为600-800像素·简单的内联CSS · Web安全字体 |
| **谨慎使用** | 背景图像（有限的客户端支持） ·自定义Web字体（始终定义回退字体） ·布局超过800像素·图像映射 |
| **避免** | JavaScript、iframe或Flash ·嵌入式音频或视频· HTML forms ·基于Div的布局 |

>[!NOTE]
>
>电子邮件内容还必须满足适用的数字辅助功能要求。 在逻辑上构建标题，为所有图像提供替换文本，并验证浅色和深色模式下的颜色对比度。

>[!ENDSHADEBOX]

## 从头开始设计您的电子邮件 {#design-from-scratch}

使用可视内容设计空间来定义电子邮件的结构和内容。 通过执行简单的拖放操作来添加和移动结构组件，您可以在几秒钟内设计电子邮件内容的布局和组织。

1. 从&#x200B;_[!UICONTROL 设计电子邮件]_&#x200B;页面中，选择&#x200B;**[!UICONTROL 从头开始设计]**&#x200B;选项。

<!-- 

1. In the _[!UICONTROL Create email]_ dialog, choose the type of email content that you want to author.

   * **[!UICONTROL Use Themes]** - Choose this option to create the email in _Theme mode_. In this mode, you can use a defined brand theme to streamline the content authoring process and make sure that the design aligns with defined standards.

   * **[!UICONTROL Manual Styling]** - Choose this option to create the email in _Manual mode_. In this mode, you manually set the styling for all structure and content components that you add to the blank canvas.

-->

1. [在画布中添加结构和内容组件](#structure-content)。

1. [审阅并更新链接](#preview-and-edit-linked-urls)。

1. [测试电子邮件](#check-and-test-the-email)。

如果对内容满意，请单击&#x200B;**[!UICONTROL 保存]**。

## 导入现有HTML内容 {#import-html-content}

<!-- originally  from   /help/_includes/content-design-import.md but copied and revised to omit the part about Marketo Engage assets and AEM assets -->

导入的内容可以是：

* 包含合并样式表的HTML文件
* 包含HTML文件、样式表(.css)和图像的.zip文件

  >[!NOTE]
  >
  >.zip 文件结构没有任何限制。 但是，引用必须是相对的，并且适合.zip文件夹的树结构。 图像始终上载到[资源存储库](./digital-asset-management.md)。

导入包含HTML内容的文件(_T):_

1. 从设计主页中，选择&#x200B;**[!UICONTROL 导入HTML]**&#x200B;选项。

1. 拖放包含 HTML 内容的 HTML 或 .zip 文件，然后单击&#x200B;**[!UICONTROL 导入]**。

![在zip文件中导入html内容](assets/email-import-zip-file.png){width="500"}

>[!NOTE]
>
>在HTML文件中使用`<table>`标记作为第一层可能会导致样式丢失，包括顶层标记中的背景和宽度设置。

您可以根据需要使用可视电子邮件编辑器工具个性化导入的内容。

## 选择模板 {#templates}

打开电子邮件设计空间时，使用&#x200B;**[!UICONTROL 选择设计模板]**&#x200B;部分从内置示例模板或保存的自定义模板开始。 请参阅[在电子邮件中使用模板](./templates.md#use-in-journey)以了解完整的工作流。

>[!NOTE]
>
>保存的模板可以将管理（内容锁定）设置应用于一个或多个组件。 当您[从受控制的模板](./template-content-governance.md)创作电子邮件时，可视设计空间提供了有关锁定的组件的准则。

## 添加结构和内容 {#structure-content}

使用可视电子邮件编辑器构建电子邮件。 添加预编译标题，使用列和分隔符构建布局，然后使用内容组件（如图像、按钮和文本）填充这些结构。 您还可以为高级样式应用自定义CSS，并预览设计在深色模式中的呈现方式。

### 设置预编译标头 {#preheader}

预览标题是收件箱预览中主题行后面显示的文本片段。 在[!DNL Marketo Optimizer]中，预标头是在电子邮件设计空间的可视画布上配置的 — 而不是在主题行旁边的电子邮件属性屏幕上配置。

在左侧导航树中选择&#x200B;**[!UICONTROL Body]**，打开右侧的&#x200B;**[!UICONTROL 设置]**&#x200B;面板。

单击&#x200B;**[!UICONTROL 预览标题]**&#x200B;文本区域，然后输入预览标题副本。 单击&#x200B;_添加个性化_ （![添加个性化图标](../assets/do-not-localize/icon-personalization-field.svg) ）图标以根据需要使用富文本控件应用格式设置和[个性化令牌](#personalize-content)。

>[!TIP]
>
>将预告长度保持在40到100个字符之间。 它应该补充主题行（而不是重复），并为收件人提供打开电子邮件的额外原因。

### 深色模式 {#dark-mode}

通过CSS `prefers-color-scheme`媒体查询支持深色模式渲染。 电子邮件设计工具包括深色模式预览和用于定义支持电子邮件客户端的自定义样式的选项 — 可帮助您验证文本是否可读、徽标是否可见，以及品牌颜色是否适合深色背景。

有关预览、配置自定义深色模式设置、电子邮件客户端支持和测试最佳实践的详细指导，请参阅电子邮件内容的[深色模式](./email-dark-mode.md)。

### 添加结构和内容组件 {#components}

通过将[结构组件](./structure-components.md)和[内容组件](./content-components.md)添加到画布来构建电子邮件布局。

从左侧面板的&#x200B;**[!UICONTROL 结构]**&#x200B;和&#x200B;**[!UICONTROL 内容]**&#x200B;部分中拖动项目，然后在右侧的&#x200B;_[!UICONTROL 设置]_&#x200B;和&#x200B;_[!UICONTROL 样式]_&#x200B;选项卡中配置每个组件。

### 添加自定义 CSS {#custom-css}

您可以直接在电子邮件设计空间中添加自定义CSS，以进行标准组件设置以外的高级样式设置。 最佳实践是在包含内容组件（如图像、按钮和文本）之前添加此最高级别的样式。

有关步骤、语法规则和疑难解答，请参阅[为您的内容添加自定义CSS](./design-custom-css.md)。

>[!NOTE]
>
>如果您的电子邮件是使用包含锁定内容[&#128279;](./template-content-governance.md)的模板设计的，则无法向内容添加自定义CSS。 按钮标签更改为&#x200B;**[!UICONTROL 查看自定义CSS]**，内容中已存在的任何自定义CSS均为只读。

### 添加片段 {#visual-fragments}

可视化片段是可重复使用的设计组件，可由[!DNL Marketo Optimizer]中的多个内容资产引用。 它通常是预先创建并快速插入的一个内容块，用于使创作更快捷、更一致。

以下示例概述了在创作内容时添加片段的步骤。

1. 要打开片段列表，请选择&#x200B;_片段_&#x200B;图标（![片段图标](../assets/do-not-localize/icon-fragments.svg)）。

   您可以：

   * 对列表进行排序。
   * 浏览、搜索或筛选列表。
   * 在缩略图和列表视图之间切换。
   * 刷新列表以反映任何最近创建的片段。

   ![从列表中选择片段](assets/visual-designer-fragments.png){width="700" zoomable="yes"}

1. 将任意片段拖放到结构组件中。

   编辑器在电子邮件结构的部分/元素中呈现片段。

   片段的内容在结构中动态更新，以预览片段在电子邮件中的呈现方式。

<!-- 
>[!BEGINSHADEBOX]

**Editable fields in customizable fragments**

A visual fragment can include editable fields that you can customize. Custom fields allow you to modify parameters when you incorporate the fragment into your content and create a tailored experience without affecting the original fragment. The fragment author can design the fragment for customization of text, image, and button components. If an included fragment contains components with editable fields, you can change the default values to customize it for your content.

1. Select the fragment component.

   The Settings displayed on the right include editable fields with the default values.

   ![Change fragment component parameters](assets/fragment-editable-fields-displayed-design.png){width="700" zoomable="yes"}   

1. Change any editable field as needed.

>[!ENDSHADEBOX]
-->

保存电子邮件后，当您在摘要中选择&#x200B;_[!UICONTROL 使用者]_&#x200B;选项卡时，该电子邮件会显示在片段详细信息页面中。

### 添加图像资源 {#insert-image}

配置[!DNL Marketo Optimizer]后，现有Marketo Design Studio资源在电子邮件设计空间中可用。 您可以直接从资产选取器浏览这些图像并将其插入电子邮件中。

>[!IMPORTANT]
>
>[!DNL Marketo Optimizer]中的资源可用性基于Marketo Design Studio中的&#x200B;**一次性资源副本**。 在初始副本为&#x200B;**且未在[!DNL Marketo Optimizer]中反映**&#x200B;后，在Marketo Engage中修改资源。 您还可以直接从可视化设计空间或[Assets库](./digital-asset-management.md)上传图像资产。

支持的图像文件类型：

* **完全支持**（在选取器中可见，可内嵌项目）：JPG、PNG、GIF、WebP。
* **可访问，但有警告**： SVG （警告某些电子邮件客户端不渲染SVG）。
* **此Beta版本不支持：** TIFF、PDF、DOCX、XLSX、PPTX、CSS、JS、HTML、TXT、二进制文件、PSD、AI、INDD。

在可视内容设计空间中，选择左侧导航栏中的&#x200B;_Assets_ （ ![Assets图标](../assets/do-not-localize/icon-assets-me.svg) ）图标。 在资源选择器中，您可以直接选择存储在Assets库中的资源。

* 通过将图像资产拖放到结构组件中来添加新资产。

  ![将内部资产拖到画布上并调整设置](./assets/content-design-add-asset.png){width="800" zoomable="yes"}

* 通过在画布上选择现有图像资源并单击图像源工具中的&#x200B;**[!UICONTROL 选择资源]**&#x200B;来替换该资源。

  ![从源库中选择资产](./assets/content-design-select-an-asset.png){width="600" zoomable="yes"}

有关使用资源的详细信息，请参阅&#x200B;[_使用资源进行内容创作_](./digital-asset-management.md#assets-authoring)。

### 导航图层、设置和样式 {#navigation-layers}

使用导航树选择组件和列，然后在右侧面板中调整其设置和样式。 请参阅[导航树](./structure-components.md#navigation-tree)。

### 个性化内容 {#personalize-content}

[!DNL Marketo Optimizer]使用Handlebars语法进行个性化。 在发送时，令牌会被替换为来自每个收件人的配置文件数据的值。 您可以在电子邮件中的多个位置使用个性化：

* **主题行** — 最常见的个性化点。
* **Preheader** — 在可视画布中设置；支持配置文件属性令牌。
* **电子邮件正文文本** — 名字和其他配置文件属性已内嵌插入。
* **按钮URL** — 附加每个收件人的参数。

>[!NOTE]
>
>在此Beta版本中，Personalization编辑器中仅提供配置文件属性。

添加个性化&#x200B;:_(_T)

1. 在电子邮件设计空间（或在主题行的电子邮件属性页面上）中，单击要在其中插入令牌的字段。
1. 单击&#x200B;_个性化_ （![个性化图标](../assets/do-not-localize/icon-personalize.svg) ）图标以使用个性化令牌。
1. 在个性化对话框中，浏览左侧的架构树。 列出了配置文件属性（名字、姓氏、电子邮件、职务和其他配置文件字段）。
1. 选择属性。 编辑器插入相应的Handlebars表达式 — 例如，`{{profile.firstName}}`。
1. 添加回退值以处理缺少的数据： `{{profile.firstName | default: "there"}}`。
1. 单击&#x200B;**[!UICONTROL 确认]**&#x200B;或&#x200B;**[!UICONTROL 插入]**。 表达式在字段中内联显示。

+++常见个性化模式{#personalization-patterns}

使用Handlebars表达式，如以下内容（个性化使用[个性化内容](#personalize-content)中描述的相同语法）：

* `{{profile.lastName}}` — 插入收件人的姓氏。
* `{{profile.jobTitle}}` — 在正文引用收件人的职务。
* `{{profile.firstName}}, ready to take the next step?` — 将令牌与静态文本内嵌相结合。

对于缺少值时带有回退的名字问候语，请使用前面个性化步骤中显示的`default`帮助程序（例如，默认值为`"there"`的名字）。

+++

+++Handlebars帮助程序{#handlebars-helpers}

在`default`之外，个性化编辑器包含用于条件逻辑、文本转换和日期格式的内置Handlebars帮助程序。 使用编辑器的函数浏览器浏览可用的帮助程序，并使用正确的语法插入它们。

>[!TIP]
>
>在电子邮件设计空间中，直接在任何文本字段中键入`{{`以触发内联自动完成下拉列表，其中列出可用的配置文件属性 — 无需打开完整的个性化对话框即可快速插入。

+++

+++AI辅助表达式{#ai-personalization}

个性化编辑器中的Co-worker可以从纯语言描述生成Handlebars表达式，说明现有表达式的用途，并确定潜在问题。 使用它可以加快表达式创作，尤其是对于条件逻辑或日期格式帮助程序。

+++

有关表达式编辑器工具和语法的详细信息，请参阅[Personalization表达式](./personalization-expressions.md)。

### 编辑链接的URL跟踪 {#preview-and-edit-linked-urls}

{{$include /help/_includes/content-design-links.md}}

## 检查并测试电子邮件 {#check-and-test-the-email}

使用电子邮件设计空间工具栏中的桌面和移动设备预览控件，在保存之前查看电子邮件布局。 切换到深色模式预览以验证可读性和对比度（请参阅电子邮件内容的[深色模式](./email-dark-mode.md)）。

测试配置文件、[!UICONTROL 模拟内容]和发送验证工作流在此Beta版本中不可用。 请参阅电子邮件渠道概述中的[当前限制](../marketing/email-channel.md#limitations)。

查看[验证电子邮件内容](#validation)以了解在历程激活之前必须解决的内容警报。

## 验证电子邮件内容 {#validation}

在激活历程之前，电子邮件内容必须有效。 [!DNL Marketo Optimizer]在电子邮件和历程画布上显示内容级警报。 本节介绍您可能会看到的警报以及如何解决这些警报。

### 常见内容警报 {#content-alerts}

| 警报 | 它的含义 | 如何解决 |
| ----- | ------------- | -------------- |
| **主题行缺失** | 主题行字段为空。 | 打开电子邮件并在&#x200B;**[!UICONTROL Content]**&#x200B;选项卡上输入主题行。 允许使用Personalization令牌，但字段不能为空。 |
| **电子邮件正文为空** | 电子邮件设计空间中的画布没有内容。 | 单击&#x200B;**[!UICONTROL 编辑电子邮件正文]**&#x200B;以打开电子邮件设计空间。 将至少一个结构和一个内容组件拖动到画布上，然后单击保存。 |
| 未选择&#x200B;**渠道配置** | 尚未为电子邮件节点选择电子邮件渠道配置。 | 在&#x200B;**[!UICONTROL 操作]**&#x200B;选项卡上，选择活动的&#x200B;**[!UICONTROL 电子邮件渠道配置]**。 |
| **渠道配置已删除** | 以前选择的渠道配置已被删除或不再有效。 | 在&#x200B;**[!UICONTROL 操作]**&#x200B;选项卡上，选择另一个活动的&#x200B;**[!UICONTROL 电子邮件渠道配置]**。 如果没有可用，管理员必须在[电子邮件渠道配置](../admin/email-channel-configuration.md)中创建或重新激活一个渠道。 |
| **电子邮件大小超过100 KB** | 电子邮件总大小（HTML、内联CSS、编码的内容）大于100 KB ISP最佳实践上限。 | 减小电子邮件大小：使用Marketo Design Studio中的外部托管图像替换大型内联图像，删除未使用的内联CSS，简化嵌套结构。 |
| **未解析的个性化令牌** | Handlebars令牌引用没有回退的配置文件属性，并且某些收件人可能缺少该属性。 | 使用Handlebars `default`帮助程序添加回退，如[个性化内容](#personalize-content)中所述。 或者，将历程受众限制到保证属性的用户档案。 |
| **映像未加载** | 图像组件引用了不再可用的资产。 | 单击图像，打开资源选取器，然后从Assets库中重新选择资源。 |
