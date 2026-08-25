---
title: 隐私管理
description: 了解如何在Marketo Optimizer中遵守GDPR、CCPA和其他隐私法规，并使用Adobe Privacy Service提交请求。
feature: Setup
role: Admin
topic_v2:
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 75b481faf0d66210329f95c8afabdfa59e7bcb79
workflow-type: tm+mt
source-wordcount: 630
ht-degree: 5%

---


# 隐私管理 {#privacy-management}

[Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/privacy/home){target="_blank"}提供RESTful API和用户界面，帮助您管理客户数据请求。 借助[!DNL Adobe Privacy Service]，您可以提交访问和删除Adobe CX Enterprise应用程序中的个人客户数据的请求，从而促进自动遵守法律和组织隐私法规。

[!DNL Adobe Marketo Optimizer]提供了这些隐私工具，以便您满足全局数据保护要求。 使用[!DNL Privacy Service]提交和管理[!DNL Marketo Optimizer]收集和存储的数据的访问和删除请求。

您可以通过两种方式提交单个请求以从[!DNL Adobe Marketo Optimizer]访问和删除使用者数据：

* [!DNL Privacy Service] UI
* [!DNL Privacy Service] API

## 支持的隐私法规 {#regulations}

[!DNL Marketo Optimizer]隐私工具通过[!DNL Privacy Service]帮助您遵守法规。 如果您保留的是相关区域中居住人员的数据，则每个法规都适用。

有关受支持法规的最新列表，请参阅Privacy Service文档中的&#x200B;[_隐私法规概述_](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/privacy/regulations/overview){target="_blank"}。

## 请求类型 {#access-and-delete-requests}

[!DNL Marketo Optimizer]支持两种隐私请求类型：

* **数据访问** — 个人可以请求确认其个人数据正在处理，并接收该数据的免费电子副本。
* **数据删除** — 也称为&#x200B;_被遗忘权_，用户可请求您擦除其个人数据并停止进一步处理。

## 查看和管理隐私请求 {#view-manage-requests}

>[!BEGINSHADEBOX]

![AEP权限图标](../assets/do-not-localize/icon_permissions-outline.svg)这些步骤要求在Experience Platform中分配的用户角色具有[!DNL Privacy Service]产品配置文件和以下[权限](../start/user-management.md#permissions)：

* **[!UICONTROL Privacy Service权限]** - `Privacy Read Permission`和`Privacy Write Permission`
* **[!UICONTROL 数据管理]** - `View Privacy Console`

有关更多详细信息，请参阅“[!DNL Privacy Service]”指南中的&#x200B;[_管理Privacy Service的权限_](https://experienceleague.adobe.com/en/docs/experience-platform/privacy/permissions){target="_blank"}。

>[!ENDSHADEBOX]

要在[!DNL Marketo Optimizer]中查看隐私请求作业，请展开&#x200B;**[!UICONTROL 隐私]**&#x200B;并选择&#x200B;**[!UICONTROL 请求]**。

使用右上角的&#x200B;**[!UICONTROL 法规类型]**&#x200B;选项，更改显示的要管理作业或提交请求的法规页面。

![隐私请求作业，请选择法规类型](./assets/privacy-requests.png){width="800" zoomable="yes"}

### 提交请求 {#submit-a-request}

1. 单击&#x200B;**[!UICONTROL 创建请求]**。

1. 对于&#x200B;**[!UICONTROL 作业类型]**，选择请求类型：

   * **[!UICONTROL 访问]**

     当您提交包含[!DNL Marketo Optimizer]的&#x200B;**_访问_**&#x200B;请求时，[!DNL Privacy Service]返回：

     * 与潜在客户关联的[!DNL Marketo Engage]活动。
     * 与人员或帐户关联的[!DNL Marketo Optimizer]活动。

   * **[!UICONTROL 删除]**

     当您提交[!DNL Marketo Engage]和[!DNL Marketo Optimizer]的&#x200B;**删除**&#x200B;请求时，将删除以下记录：

     * [!DNL Marketo Engage]中的关联潜在客户。
     * 在[!DNL Marketo Optimizer]中创建的人员和帐户记录。
     * 引用个人信息的同事对话历史记录。

1. 对于&#x200B;**[!UICONTROL 产品]**，请选择&#x200B;**[!UICONTROL Marketo]**。

   ![为Marketo Engage和Marketo Optimizer创建GDPR访问隐私请求](./assets/privacy-request-create-gdpr.png){width="450" zoomable="yes"}

   此选择包括来自[!DNL Marketo Optimizer]和您的[!DNL Marketo Engage]实例的数据。

1. 滚动到对话框的底部，输入要访问或删除其数据的人员的电子邮件地址。

1. 要提交请求，请单击&#x200B;**[!UICONTROL 创建]**。

   [!DNL Privacy Service]返回可用于检查您的请求状态的请求ID。

### API请求 {#api-requests}

您还可以使用[!DNL Privacy Service] API提交隐私请求。 有关常规API参考，请参阅[Privacy Service API文档](https://developer.adobe.com/experience-platform-apis/references/privacy-service){target="_blank"}。

>[!PREREQUISITES]
>
>在提交请求之前收集以下信息：
>
>* 您组织的IMS组织ID（以`@AdobeOrg`结尾的24个字符的数字字母字符串）。 如果您不知道自己的IMS组织ID，请通过`gdprsupport@adobe.com`联系Adobe支持人员。
>* 要访问或删除其数据的人员的电子邮件地址。

在请求中使用以下字段值：

| 字段 | 值 |
|---|---|
| `companyContexts.namespace` | `imsOrgID` |
| `companyContexts.value` | 您的IMS组织ID |
| `users.action` | `access` 或 `delete` |
| `users.userIDs.namespace` | `Email` |
| `include` | `marketo`以包括[!DNL Marketo Optimizer]和[!DNL Marketo Engage]数据 |
| `regulation` | 示例： `ccpa` <br/>某些法规值正在更改为包含州缩写（例如，`ucpa_ut_usa`）。 较旧的值在过渡期间仍然有效。 在针对这些值生成集成之前，请查看当前列表的[隐私法规概述](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/privacy/regulations/overview){target="_blank"}。 |

以下示例提交了一个包含[!DNL Marketo Optimizer]数据的GDPR删除请求。

```json
{
  "companyContexts": [
    {
      "namespace": "imsOrgID",
      "value": "1231659F56A68A8B7F000101@AdobeOrg"
    }
  ],
  "users": [
    {
      "action": ["delete"],
      "userIDs": [
        {
          "namespace": "Email",
          "type": "standard",
          "value": "john.doe@adobe.com"
        }
      ]
    }
  ],
  "include": ["marketo"],
  "regulation": "gdpr"
}
```

[!DNL Privacy Service]返回类似于以下内容的响应。

```json
{
  "requestId": "16331241037112570RX-245",
  "totalRecords": 1,
  "jobs": [
    {
      "jobId": "997b01e3-9568-402c-904b-b4e60a437875",
      "customer": {
        "user": {
          "action": ["delete"],
          "userIDs": [
            {
              "namespace": "Email",
              "value": "john.doe@adobe.com",
              "type": "standard",
              "namespaceId": 6,
              "isDeletedClientSide": false
            }
          ]
        }
      }
    }
  ]
}
```
