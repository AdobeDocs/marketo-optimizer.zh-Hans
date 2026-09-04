---
title: 监控和调试历程进程
description: 了解如何在同事聊天中使用历程可观察性技能来调试和监测人员和潜在客户如何在旅程、拆分路径决策和时间中移动。
source-git-commit: 9db94582512d95f6c07d4e978a0a27291b471900
workflow-type: tm+mt
source-wordcount: '634'
ht-degree: 0%

---

# 监控和调试历程进度

[!DNL Adobe Marketo Optimizer]中的&#x200B;[_历程可观察性_&#x200B;技能](./skills.md#journeys)回答有关人员和潜在客户如何在旅程中移动的自然语言问题。 在[同事聊天界面](./chat-interface.md)中使用它来跟踪进度、了解拆分路径决策、分析历程节点中的人员并检查计时量度。 您还可以询问历程中的行为模式。

* **技能** - `journey-observability`
* **调用** — 以自然语言提问，或使用斜杠命令运行历程可观察性技能。 例如： _“demo_ lead_24@company.com如何通过LeadNurtureJourney？”_
* **从**&#x200B;读取 — [!DNL Marketo Optimizer]历程数据；读取[!DNL Marketo Engage]静态列表以检查列表成员资格

## 查看人员或潜在客户详细信息 {#person-details}

在调查人员或潜在客户历程之前，询问有关人员或潜在客户的基本只读详细信息，以建立上下文。 提供人员的电子邮件地址、潜在客户ID或潜在客户名称。

* _“给我有关潜在客户demo_ lead_24@company.com的基本信息。”_
* _“配置文件john.doe@company.com的工作标题和国家/地区是什么？”_
* _“显示lead_ 01的电子邮件和角色。”_

## 跟踪历程的进度 {#journey-progression}

询问人员或商机如何在历程中移动，以了解节点级别的登入、退出、持续时间以及他们采用的路径。 提供人员的电子邮件地址或商机ID以及历程名称。

* _“demo_ lead_24@company.com是如何通过LeadNurtureJourney的？”_
* _“john.doe@company.com在产品演示历程中通过了哪些节点？”_

## 了解拆分路径决策 {#split-path-analysis}

询问人员或潜在客户为什么在拆分节点选择或不选择特定路径。 历程可观察性使用该时间点计算的属性值解释该决策。 提供人员的电子邮件地址或商机ID、历程名称和拆分节点ID。

* _“为什么demo_ lead_24@company.com在拆分节点c764a9处转到‘高度参与’路径？”_
* _“为什么john.doe@company.com没有在LeadNurtureJourney的节点ab123f处采用限定路径？”_
* _“比较为什么lead_ 01和lead_02在拆分节点x99f3b处采用不同的路径。”_

## 分析历程节点中的人员 {#node-analysis}

在历程节点或拆分路径中询问人员或商机计数和详细信息。 按角色、角色、位置或参与级别过滤结果。 提供节点ID。

* _“给我当前处于节点459c7c的‘高参与度’路径中的所有人员。”_
* _“演示培训历程的资格节点中有多少潜在客户？”_
* _“显示按角色（营销经理）筛选的‘低意图’拆分路径中的潜在客户。”_

## 识别历程中的模式 {#pattern-recognition}

要求历程可观察性识别历程中的常见路径、流失点和重复行为。 提供历程名称，并（可选）提供时间范围、角色、产品或帐户以缩小结果范围。

* _“SDR在产品演示历程中最常用的路径是什么？”_
* _“潜在客户通常在LeadNurtureJourney中的哪个位置流失？”_
* _“Q1培养历程中是否有任何异常延迟或意外的路径？”_

## 检查时间和操作量度 {#operational-metrics}

询问历程的进入时间、等待持续时间、过渡延迟和停滞进度。 提供历程名称，以及（可选）节点ID或人员标识符。

* _“john.doe@company.com何时进入演示跟进历程？”_
* _“潜在客户通常在LeadNurtureJourney中的资格节点等待多长时间？”_
* _“哪些潜在客户在演示跟进历程中停止了七天以上？”_

## 限制 {#limitations}

| 限制 | 详细信息 |
|---|---|
| 编辑人员或潜在客户属性 | 不支持。 直接在[!DNL Marketo Engage]或[!DNL Marketo Optimizer]中更新人员和潜在客户记录。 |
| 创建、编辑、暂停或恢复历程 | 不支持。 请改用[历程画布](../marketing/person-journeys.md)或[同事技能](./skills.md#journeys)中的历程编辑技能。 |
| 更改拆分逻辑或历程配置 | 不支持。 直接在[历程画布](../marketing/split-merge-paths-nodes.md)中编辑拆分路径。 |
| 购买组组合或帐户级别汇总 | 超出范围。 仅人员和潜在客户级别的历程可观察性报表。 |
| 更改历程计划或时间 | 不支持。 |
