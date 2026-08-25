---
title: 片段创作
description: 在Marketo Optimizer中，通过可视化设计工具创作可重用的内容片段 — 为电子邮件和模板添加结构、资源、个性化、条件内容以及链接的URL跟踪。
source-git-commit: c7d3546d075f5a58923134231217b2fd10fe4aca
workflow-type: tm+mt
source-wordcount: '203'
ht-degree: 3%

---

# 片段创作

在您[创建片段](./fragments.md#create-fragments)后，请使用可视化设计空间在片段中创作结构和内容组件。

## 添加结构和内容 {#design-fragment}

{{$include /help/_includes/content-design-components-prime.md}}

## 添加资源 {#add-assets}

在可视设计空间中，选择左侧导航栏中的&#x200B;_Assets_ （![Assets图标](../assets/do-not-localize/icon-assets-me.svg) ）图标以浏览和选择[!DNL Marketo Optimizer]资源库中的图像资源。

有关选择、替换或上传图像资产的步骤，请参阅[使用资产进行内容创作](./digital-asset-management.md#assets-authoring)。

## 导航图层、设置和样式 {#navigate-layers-settings-styles}

{{$include /help/_includes/content-design-navigation.md}}

## 个性化内容 {#personalize-content}

[!DNL Marketo Optimizer]使用Handlebars语法进行个性化。 在发送时，令牌会被替换为来自每个收件人的配置文件数据的值。

添加个性化&#x200B;:_(_T)

1. 选择文本组件，然后单击工具栏中的&#x200B;_添加个性化_ （ ![个性化图标](../assets/do-not-localize/icon-personalize.svg) ）图标。
1. 在个性化对话框中，浏览左侧的架构树并选择配置文件属性。 编辑器插入相应的Handlebars表达式 — 例如，`{{profile.firstName}}`。
1. 如果需要，添加回退值以处理缺少的数据，例如`{{profile.firstName | default: "there"}}`。
1. 单击&#x200B;**[!UICONTROL 确认]**&#x200B;或&#x200B;**[!UICONTROL 插入]**。 表达式在字段中内联显示。

有关表达式编辑器工具和语法的详细信息，请参阅[Personalization编辑器](./personalization-expressions.md)。

## 编辑链接的URL跟踪 {#edit-linked-url-tracking}

{{$include /help/_includes/content-design-links.md}}
