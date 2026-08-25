---
title: 登陆页面设计
description: 使用可视化工具设计登陆页面 — 在Marketo Optimizer中为人员历程添加内容组件、表单、自定义CSS、个性化和设备预览。
feature: Landing Pages, Content Design Tools
role: User
source-git-commit: c7d3546d075f5a58923134231217b2fd10fe4aca
workflow-type: tm+mt
source-wordcount: '556'
ht-degree: 2%

---

# 登陆页面设计

在您[创建登陆页面](./landing-pages-create-publish.md#create-landing-page)之后，请使用可视化设计空间在页面中创作结构和内容组件。

## 添加结构和内容 {#structure-content-landing-page}

{{$include /help/_includes/content-design-components-prime.md}}

### 添加自定义 CSS {#add-custom-css}

您可以直接在登陆页面设计空间中添加自己的自定义CSS。 使用自定义CSS可应用高级和特定的样式，以便更加灵活地控制内容的外观。 最佳实践是在包含组件（如图像、按钮和文本）之前添加此最高级别的样式。

如果画布中至少有一个内容组件，请选择左侧导航树中的&#x200B;**[!UICONTROL Body]**&#x200B;组件以访问自定义CSS编辑器。

![访问正文样式](assets/landing-page-body-styles-css.png){width="800" zoomable="yes"}

有关步骤、语法规则和疑难解答，请参阅[为您的内容添加自定义CSS](./design-custom-css.md)。

### 添加资源 {#add-assets}

在可视设计空间中，选择左侧导航栏中的&#x200B;_Assets_ （![Assets图标](../assets/do-not-localize/icon-assets-me.svg) ）图标以浏览和选择[!DNL Marketo Optimizer]资源库中的图像资源。

有关选择、替换或上传图像资产的步骤，请参阅[使用资产进行内容创作](./digital-asset-management.md#assets-authoring)。

### 添加表单 {#add-forms}

{{$include /help/_includes/content-design-add-forms.md}}

### 导航图层、设置和样式 {#navigate-layers-settings-styles}

{{$include /help/_includes/content-design-navigation.md}}

### 个性化内容 {#personalize-content}

[!DNL Marketo Optimizer]使用Handlebars语法进行个性化。 在查看登陆页面时，令牌会被替换为每位访客的配置文件数据中的值。

添加个性化&#x200B;:_(_T)

1. 选择文本组件，然后单击工具栏中的&#x200B;_添加个性化_ （ ![个性化图标](../assets/do-not-localize/icon-personalize.svg) ）图标。
1. 在个性化对话框中，浏览左侧的架构树并选择属性。 编辑器将插入相应的Handlebars表达式。
1. 如果需要，添加回退值以处理缺少的数据。
1. 单击&#x200B;**[!UICONTROL 确认]**&#x200B;或&#x200B;**[!UICONTROL 插入]**。 表达式在字段中内联显示。

有关表达式编辑器工具和语法的详细信息，请参阅[Personalization编辑器](./personalization-expressions.md)。

### 编辑链接的URL跟踪 {#linked-url-tracking}

{{$include /help/_includes/content-design-links.md}}

![单击“编辑”图标以访问链接跟踪](assets/landing-page-link-tracking.png){width="400"}

使用&#x200B;**[!UICONTROL 跟踪类型]**&#x200B;控制链接的跟踪：

* **[!UICONTROL 已跟踪]** — 激活对链接URL的跟踪。
* **[!UICONTROL 从不]** — 从不激活链接URL的跟踪。

### 保存您所做的工作 {#save-your-work}

随时单击&#x200B;**[!UICONTROL 保存]**&#x200B;以保存草稿登陆页面。

您可以继续对草稿页面进行编辑。 当您准备好显示页面并在电子邮件或短信消息中提供链接时，可以发布页面。

### 查看选项 {#view-options}

利用可视设计空间中可用的视图和内容验证选项。

* 通过预设缩放选项放大/缩小内容。

* 切换在桌面、移动设备或纯文本/纯文本中查看内容。
  * 单击&#x200B;_查看_&#x200B;图标可跨设备预览内容。
  * 选择一个现成的设备或输入自定义维度以预览内容。

### 更多选项 {#more-options}

从可视化设计空间顶部的&#x200B;_[!UICONTROL 更多……]_&#x200B;菜单中，可以执行以下操作：

![单击“更多”以访问登陆页面操作](assets/landing-page-designer-more-menu.png){width="500"}

* **[!UICONTROL 重置登陆页面]** — 单击此选项可将可视化设计画布清除为空白并重新启动页面内容生成操作。
* **[!UICONTROL 更改您的设计]** — 返回到&#x200B;_[!UICONTROL 创建您的主登陆页面]_&#x200B;主页。 从该位置，您可以选择另一个模板来重新启动设计过程，或者选择在空白画布中从头开始设计页面。
* **[!UICONTROL 导出HTML]** — 将可视画布中的内容以HTML格式下载到您的本地系统，并打包为zip文件。
