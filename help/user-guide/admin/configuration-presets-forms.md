---
title: Forms配置
description: 占位符
source-git-commit: c7d3546d075f5a58923134231217b2fd10fe4aca
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 16%

---

# Forms配置

产品管理员必须先创建一个或多个专用预设，然后营销人员才能创建和发布要在其登陆页面中使用的表单。 每个预设定义用于发送表单提交数据的连接端点，以及用于存储捕获的数据的数据集。

当数据登陆流端点时，它会与数据集信息相关联。 然后，使用生成的源/目标连接和源流量，将数据推送到数据集中。

>[!BEGINSHADEBOX]

## 先决条件

要使用Web窗体，您必须在Adobe Experience Platform中定义一个或多个&#x200B;_&#x200B;**HTTP API流连接**&#x200B;_。 确保要使用的每个连接都满足以下要求：

* 数据类型必须设置为XDM（不是原始数据）
* 必须禁用身份验证（非身份验证连接）

有关创建流源连接的详细信息，请参阅&#x200B;[_Experience Platform文档_](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/sources/ui-tutorials/create/streaming/http)。

<!-- 
permissions coming in GA

Forms channel configuration in Journey Optimizer B2B Edition requires the following [permissions](../start/user-management.md#b2b-product-permissions):

* _[!UICONTROL B2B Channel Configurations]_ > _[!UICONTROL View Forms Presets]_ - Required to view forms preset configurations.
* _[!UICONTROL B2B Channel Configurations]_ > _[!UICONTROL Manage Forms Presets]_ - Required to create, update, and delete forms preset configurations.
* _[!UICONTROL B2B Channel Configurations]_ > _[!UICONTROL Publish Forms Presets]_ - Required to publish forms preset configurations.
-->

>[!ENDSHADEBOX]

## 表单预设配置准则

创建预设时：

* 您可以使用不同的数据集和流连接组合来设置多个预设。

* 您可以跨多个预设重用相同的数据集或流连接。

* 每个流连接都会自动生成资源，例如：

  * _Source连接_ — 数据来源。
  * _目标连接_ — 存储或使用数据的位置。
  * _Source流_ — 将数据从源连接移入Experience Platform的管道。 它处理映射、转换和验证。

## 创建表单预设 {#create-preset}

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_lp_form_connection"
>title="选择要使用的端点"
>abstract="定义表单提交时用于发送数据的流式端点。"
>additional-url="https://experienceleague.adobe.com/zh-hans/docs/experience-platform/sources/ui-tutorials/create/streaming/http" text="创建 HTTP API 流式连接"

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_lp_form_dataset"
>title="选择数据集"
>abstract="定义用于存储和反映表单响应的数据集。 输入文本以搜索特定数据集，或从列表中选择数据集。"

1. 在左侧导航中，转到&#x200B;**[!UICONTROL 管理]** > **[!UICONTROL 渠道]**。

1. 在导航面板中的&#x200B;_[!UICONTROL 表单设置]_&#x200B;下，选择&#x200B;**[!UICONTROL 表单预设]**。

   <!-- ![Access the form configurations](./assets/config-channels-forms.png){width="800" zoomable="yes"} -->

1. 单击&#x200B;**[!UICONTROL 创建表单预设]**。

1. 输入配置的唯一&#x200B;**[!UICONTROL Name]**（必需）和&#x200B;**[!UICONTROL Description]**（可选）。

   >[!NOTE]
   >
   >名称必须以字母(A-Z)开头，并且只能包含字母数字字符。 您还可以使用下划线`_`、点`.`和连字符`-`字符。

1. 选择&#x200B;**[!UICONTROL 流连接]**。

   此连接是Web查看器提交表单时用于发送数据的流端点。 如果列表中未显示所需的流连接，请验证是否满足要求。

1. 单击&#x200B;_选择数据集_ （ ![选择数据集图标](../assets/do-not-localize/icon-select-data.svg) ）图标可将数据集与表单关联。

   数据集是存储和反映表单响应的位置。 您可以输入文本字符串以搜索特定数据集，或从列表中选择该数据集。

   <!-- ![Select datasets dialog](./assets/config-channel-forms-select-datasets.png){width="500" zoomable="yes"} -->

   >[!NOTE]
   >
   >当前只能选择启用配置文件和未启用配置文件的[Adobe Experience Platform数据集](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/catalog/datasets/overview)。 您可以一次选择一个数据集。 系统数据集不能用于保存表单数据。

   选中数据集的复选框，然后单击&#x200B;**[!UICONTROL 选择]**。

1. 单击&#x200B;**[!UICONTROL 另存为草稿]**。

## 发布表单预设

1. 单击表单预设名称以打开配置页面。

   如果需要，您可以对草稿进行任何调整。

1. 单击&#x200B;**[!UICONTROL 发布]**。

   当以&#x200B;_已发布_&#x200B;状态列出表单预设时，可用于创建表单。
