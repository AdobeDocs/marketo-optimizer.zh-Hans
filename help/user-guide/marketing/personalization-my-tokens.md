---
title: Personalization的自定义令牌
description: 创建和管理自定义“我的令牌”以动态个性化营销工件 — 在Marketo Optimizer中为项目定义文本和数字变量。
TQID: 'https://experienceleague.adobe.com/utVM69g7aQSuF-V3XQIdVBqvBXyiDz1ZWr0WtE67UCg'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 64b90904-e4f0-5c1b-a871-8c6a40b204a1
    internal-label: Journeys
  - id: a29661b8-f7a4-53d1-a9ac-fdec08c092e4
    internal-label: Programs
topic_v2:
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: 177e7c3d0806febd730104b19787ba3cbea2914a
workflow-type: tm+mt
source-wordcount: '704'
ht-degree: 2%
---
# 用于个性化的自定义令牌

内容个性化使用令牌作为生成内容工件时填充的占位符或变量。 标准个性化令牌可用于电子邮件、登陆页面、片段和模板。 您还可以使用特定于程序或文件夹的值定义一组自定义令牌。 这组自定义令牌称为&#x200B;_我的令牌_，其中的任何自定义令牌均可用于个性化。

<!-- 
When you add a custom token to an email, it is displayed as `{{my.TokenName}}`. For example, you might have `{{my.EventDate}}` or `{{my.WebinarSpeaker}}` tokens created to manage email content related to upcoming webinars in your program.
-->

除了特定于程序或文件夹的&#x200B;_我的令牌_&#x200B;之外，您还可以使用任何标准（内置）令牌进行个性化。

>[!IMPORTANT]
>
>对于初始Marketo Optimizer版本，“更改数据值”历程操作节点支持&#x200B;_我的令牌_，并且限制在字符串和文本属性中使用。 _我的令牌_&#x200B;当前在Personalization编辑器中&#x200B;**未**&#x200B;启用。

## 访问令牌 {#access-tokens}

1. 在左侧导航栏中，展开&#x200B;**[!UICONTROL 营销管理]**。

1. 在&#x200B;**[!UICONTROL 营销]**&#x200B;资源列表的右侧，选择&#x200B;**[!UICONTROL 项目]**。

1. 在树结构中，选择程序或文件夹，以在中心工作区中打开详细信息。

1. 单击&#x200B;**[!UICONTROL 令牌]**&#x200B;选项卡。

   所选程序中的![令牌选项卡](./assets/program-tokens-tab.png){width="800" zoomable="yes"}

   该选项卡显示在该文件夹或程序中定义的所有自定义令牌，以及为父文件夹或程序定义的所有自定义令牌。

### 令牌类型 {#my-tokens}

_我的令牌_&#x200B;是您为程序或文件夹创建或修改的自定义变量。 此自定义令牌集支持以下令牌类型：

| 令牌类型 | 描述 |
| ---------- | ----------- |
| 文本 | 此类型包含标准文本字符串。 文本令牌的大小限制为524,288个字符(UTF-8)或2 MB。 |
| 日期 | 此类型包含日期值。 日期显示为月 — 日 — 年（例如，09-23-2026）。 |
| 日期和时间 | 此类型包含日期和时间值。 |
| 数字 | 此类型保存一个标准整数值。 |
| 电子邮件 | 此类型包含有效的电子邮件地址。 |
| 得分 | 使用此令牌可更改历程操作节点的分数。 |
| 布尔值 | 此类型包含标准布尔值，即true或false。 |
| 富文本 | 此类型保存带格式的文本。 |

### 令牌嵌套 {#nesting}

在程序或文件夹中创建令牌时，可供层次结构中的对象引用。

* **本地令牌** — 令牌在同一程序或文件夹中定义。
* **继承的令牌** — 该令牌定义在父程序或文件夹中，比当前程序或文件夹高一个或多个级别。
* **覆盖的令牌** — 令牌定义在父程序或文件夹中，但在当前程序或文件夹中定义了不同的值。 令牌状态更改为&#x200B;_已覆盖_，并且所有子文件夹、项目和营销项目都将继承新值。

![令牌类型和继承](./assets/program-tokens-inherited-overridden.png){width="600" zoomable="yes"}

### 创建令牌 {#create}

1. 在&#x200B;_[!UICONTROL 令牌]_&#x200B;选项卡中，单击&#x200B;**[!UICONTROL 创建]**。

1. 在对话框中，输入令牌的&#x200B;**[!UICONTROL 名称]**。

   ![输入文本令牌的名称和值](./assets/token-create-dialog.png){width="400"}

   令牌名称中不能使用空格或特殊字符。 您可以使用&#x200B;_驼峰式大小写_（如`EventType`）来使用易于识别的多词名称。

1. 为令牌选择&#x200B;**[!UICONTROL 类型]**。

1. 为令牌设置&#x200B;**[!UICONTROL 值]**。

1. 单击&#x200B;**[!UICONTROL 创建]**。

### 编辑令牌 {#edit}

您可以编辑任何已定义的“我的令牌”的值，这会覆盖继承令牌的值。

<!-- (How does this affect live person journeys? ) -->

1. 在&#x200B;_[!UICONTROL 令牌]_&#x200B;上，单击令牌名称旁边的&#x200B;_编辑_&#x200B;图标。

1. 在字段中，根据需要更改值。

   ![更改令牌的名称和值](assets/my-tokens-edit-text-token-dialog.png){width="400"}

1. 单击&#x200B;_保存_&#x200B;图标。

### 删除令牌 {#delete}

如果历程电子邮件内容当前未使用自定义令牌，您可以从列表中删除该令牌。

1. 在&#x200B;_[!UICONTROL 令牌]_&#x200B;上，单击令牌名称旁边的&#x200B;_删除_&#x200B;图标。

1. 在确认对话框中单击&#x200B;**[!UICONTROL 删除]**。

## 自动建议和预览 {#autosuggest}

当您在历程中包含&#x200B;_更改数据值_ [操作节点](./action-nodes.md)时，您可以在&#x200B;**[!UICONTROL 新值]**&#x200B;字段中输入`{{`以显示令牌&#x200B;_自动建议_&#x200B;菜单。 显示的列表显示了受支持的命名空间和各个令牌。 仅列出兼容数据类型的令牌。

对于&#x200B;_我的令牌_，将显示带有令牌名称的令牌值预览，以便更轻松地选择正确的值。

![新值字段中的语法以显示令牌的自动优化菜单](./assets/program-tokens-change-data-value-autosuggest.png){width="500" zoomable="yes"}

<!--

## Use custom tokens in your content

When you are authoring email content for your programs, you can use any of the tokens from the _My Tokens_ list when you use the personalization tools in the visual design space.

1. Select the text component and click the _Add personalization_ ( ![Add personalization icon](../assets/do-not-localize/icon-personalization-field.svg) ) icon in the toolbar.

   ![Click the Add personalization icon](assets/email-personalize-text.png){width="600"}

   This action opens the _Edit Personalization_ dialog. The dialog includes a _[!UICONTROL My tokens]_ folder in the _[!UICONTROL Personalization Tokens]_ library if there are custom tokens defined for the account journey.

1. To add one of your custom tokens to the blank space, expand the **[!UICONTROL My tokens]** folder, then click **+** or **...**.

   You can add any additional static text as needed.

   ![Construct personalized text using My tokens](assets/personalization-edit-dialog-my-tokens.png){width="700" zoomable="yes"}

1. Click **[!UICONTROL Save]**.

-->
