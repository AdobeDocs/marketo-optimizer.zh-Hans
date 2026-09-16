---
title: Experience Platform数据集
description: 了解Marketo Optimizer写入Adobe Experience Platform以支持Customer Journey Analytics报表和临时查询的数据集。
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 3c1de303-7a7c-59a6-abca-8c534730e19c
    internal-label: Reporting
source-git-commit: 1ebb0036699252c50f33ba6c0f4a56e8e670aacd
workflow-type: tm+mt
source-wordcount: '314'
ht-degree: 4%
---

# Experience Platform数据集

[!DNL Adobe Marketo Optimizer]将潜在客户、历程和活动数据复制到[!DNL Adobe Experience Platform]数据集。 这些数据集支持[!UICONTROL 报表]页面和嵌入的[!DNL Adobe Customer Journey Analytics]报表体验。 您还可以使用[!DNL Query Service]直接查询它们以进行Ad Hoc分析。

数据集由系统管理。 [!DNL Customer Journey Analytics]中的连接将它们链接到[!DNL Marketo Optimizer]报告使用的数据视图，因此您不需要自己构建此连接。 此连接与您在报表节上选择&#x200B;**[!UICONTROL 在CJA中分析]**&#x200B;时建立的连接相同。 请参阅[在Customer Journey Analytics中分析报表](./reports-overview.md#analyze-a-report-in-cja)。

## 可用数据集 {#available-datasets}

为每个[!DNL Marketo Optimizer]实例填充以下数据集。

>[!NOTE]
>
>每个数据集名称都使用前缀`AJOB2B`，该前缀表示[!DNL Marketo Optimizer]数据的系统名称。 这是正常行为，您可以使用这些名称在[!DNL Experience Platform]沙盒中查找数据集。

| 数据集 | 架构 | 描述 |
| --- | --- | --- |
| `AJOB2B - Person` | 人员 | 标准潜在客户属性。 |
| `AJOB2B - PersonActivity` | 人员活动 | 与人员关联的活动事件。 |
| `AJOB2B - PersonActivityType` | 人员活动类型 | 与人员关联的活动类型。 |
| `AJOB2B - PersonActivityTypeEngagementMapping` | 人员活动类型参与映射 | 将活动类型映射到其参与分类、渠道事件和方向性。 |
| `AJOB2B - Journey` | 历程 | 历程及其生命周期元数据的列表。 |
| `AJOB2B - JourneyNode` | 历程节点 | 历程中的节点及其关联元数据的列表。 |
| `AJOB2B - EngagementAsset` | 参与资产 | 跨参与资产类型的参与资产ID和显示名称的统一查找。 |

## 使用查询服务查询数据集 {#query-service}

当您需要在[!DNL Customer Journey Analytics]报告之外进行分析时，可使用[!DNL Query Service]对这些数据集运行临时SQL查询。 查询访问要求您的沙盒具有适当的[!DNL Experience Platform]权限。 有关一般查询语法和设置，请参阅[查询服务](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/query/home){target="_blank"}。

![查询服务编辑器显示针对ajob2b_journey数据集的SELECT查询以及结果历程记录的表。](./assets/aep-query-service.png){width="800" zoomable="yes"}

>[!NOTE]
>
>这些数据集是只读的。 要更改[!DNL Marketo Optimizer]捕获的数据，请在[!DNL Marketo Optimizer]或[!DNL Marketo Engage]中更新源数据，而不是直接编辑数据集。
