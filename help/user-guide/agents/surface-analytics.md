---
title: 生成Analytics报表
description: 了解如何在同事聊天中使用Surface Analytics技能从自然语言提示生成活动、电子邮件、潜在客户、区段和历程报告。
autotag-review: '2026-09-21T14:58:26.479Z'
TQID: 'https://experienceleague.adobe.com/BSDEihjdpz-YZjMWrYTmIuyjqtcjRHRrJdz4xPFZbHU'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 1650dadf-b034-5ac9-a309-77ad1e2f5035
    internal-label: Chat Interface
  - id: 3c1de303-7a7c-59a6-abca-8c534730e19c
    internal-label: Reporting
subfeature_v2:
  - id: b9e5c7f3-be30-563c-9e41-cc8ea76e2fee
    internal-label: Skills
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
source-git-commit: 1dcc3bcdc59114c7fc1e16178db8921ae173b955
workflow-type: tm+mt
source-wordcount: '419'
ht-degree: 0%
---
# 生成Analytics报表

[!DNL Adobe Marketo Optimizer]中的&#x200B;[_Surface Analytics_&#x200B;技能](./skills.md#analytics-reporting)回答有关您的数据的自然语言问题。 在[同事聊天界面](./chat-interface.md)中使用它来浏览活动趋势、电子邮件性能、潜在客户和帐户数据、区段和列表成员资格以及历程量度。 结果会以图表和表的形式返回，因此您无需手动构建查询或仪表板。

* **技能** - `surface-analytics`
* **调用** — 以自然语言提问，或使用斜杠命令来运行Surface Analytics技能。 例如：_“显示过去30天的每日活动计数。”_
* **从** - [!DNL Marketo Optimizer]分析数据中读取；读取[!DNL Marketo Engage]分析数据以了解跨两个产品的问题

>[!NOTE]
>
>报表数据每两小时刷新一次。 结果可能无法反映过去两小时的活动。

## 查看活动趋势 {#activity-trends}

询问每日或每周活动计数，并按活动类型或产品区域细分结果。

* _“显示过去30天的每日活动计数。”_
* _“本周的热门活动类型是什么？”_
* _“按应用程序区域划分上月的活动。”_

## 检查电子邮件性能 {#email-performance}

询问您的电子邮件程序的发送数量、打开和点击率、退信次数和取消订阅次数。

* _“按历程列出的电子邮件打开率是多少？”_
* _“显示过去90天的点击率。”_
* _“上周我们获得了多少个取消订阅？”_

## 分析潜在客户和帐户数据 {#lead-account-data}

询问有关商机得分分布、角色划分以及地理或行业汇总的信息。

* _“显示潜在客户之间的得分分布。”_
* _“每个帐户有多少人？”_
* _“按角色划分潜在客户。”_

## 审核区段并列出成员资格 {#segment-list-membership}

询问谁属于特定列表或区段。

* _“Q1培养名单中有多少人？”_
* _“哪个区段的成员最多？”_

## 浏览历程量度 {#journey-metrics}

询问旅程成员资格、完成率、节点遍历和funnel分析。

* _“演示跟进历程的完成率是多少？”_
* _“LeadNurtureJourney的每个节点有多少人？”_

## 跨产品提问 {#cross-product}

Surface Analytics可以在单个提示中回答同时包含[!DNL Marketo Engage]和[!DNL Marketo Optimizer]数据的问题。

* _“在LumaSecure和LumaStorage中，我表现最佳的电子邮件是什么？”_

## 限制 {#limitations}

| 限制 | 详细信息 |
|---|---|
| 编辑或创建记录 | 不支持。 Surface Analytics仅读取和报告现有数据。 |
| 结果中人工可读的名称 | 并不总是可用。 某些报表显示内部ID，例如历程或电子邮件ID，而不是名称。 |
| 复制报告卡 | 对于同一结果，单个问题有时可能返回多个报告卡。 |
