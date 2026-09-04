---
title: 同事技能
description: 查看Marketo Optimizer中的CX Enterprise Co-worker技能 — 为计划、历程、受众、评分、内容和发送时间优化打包的工作流。
source-git-commit: 9db94582512d95f6c07d4e978a0a27291b471900
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 5%

---

# 同事技能

_技能_&#x200B;是同事知道如何运行的打包工作流 — `/`菜单和自然语言请求背后的构建块。 每个技能都捆绑了分步说明和一个工作所需的特定工具（例如，“发布历程”、“比较两个人列表”、“构建评分模型”）。

>[!NOTE]
>
>每个技能都根据技能是否改变[!DNL Marketo Optimizer]或[!DNL Marketo Engage]状态（**写入**）、是否只查询/分析/生成（**读取**）或是否具有同等的查询+变异函数（**读取+写入**）进行分类。

## 方案和规划 {#programs-planning}

| 技能 | 作用 | 访问 | 产品表面 | 影响/数据流 |
|---|---|---|---|---|
| `falco-program-creation` | 端到端[!DNL Marketo Optimizer]项目创建 — 项目、子文件夹、令牌、列表、历程。 <p>请参阅&#x200B;_[根据简报创建项目](./program-from-brief.md)_。 | 写入 | [!DNL Marketo Optimizer] | 读取+写入[!DNL Marketo Optimizer]。 |
| `adapt-program` | 从[!DNL Marketo Engage]项目生成迁移故事以进行[!DNL Marketo Optimizer]适应。 | 读取 | [!DNL Marketo Optimizer] | 读取[!DNL Marketo Engage]，写入[!DNL Marketo Optimizer] |
| `folder-creation` | 在资产树中创建组织文件夹。 | 写入 | [!DNL Marketo Optimizer] | 读取+写入[!DNL Marketo Optimizer] |
| `program-creation` *（生成程序）* | 从营销活动简报创建Marketo项目。 | 写入 | [!DNL Marketo Engage] | 读取+写入[!DNL Marketo Engage] |
| `program-planning` *（计划营销活动）* | 将简报转换为设置/实施文档。 | 读取 | [!DNL Marketo Engage] | 读取[!DNL Marketo Engage] |
| `program-qa` *（验证程序）* | 验证/审核程序（仅限规则、测试计划或简要）。 | 读取 | [!DNL Marketo Engage] | 读取[!DNL Marketo Engage] |

## 历程 {#journeys}

| 技能 | 作用 | 访问 | 产品 | 后端（数据流） |
|---|---|---|---|---|
| `journey-creation` | 从自然语言创建和编辑人员历程。 | 写入 | [!DNL Marketo Optimizer] | 读取+写入[!DNL Marketo Optimizer] |
| `journey-edit-dates` | 在不发布的情况下更改历程的开始/结束日期。 | 写入 | [!DNL Marketo Optimizer] | 读取+写入[!DNL Marketo Optimizer] |
| `journey-publish` | 发布/启动/计划人员历程。 | 写入 | [!DNL Marketo Optimizer] | 读取+写入[!DNL Marketo Optimizer] |
| `journey-stop` | 中止、关闭、停止、停止或终止历程。 | 写入 | [!DNL Marketo Optimizer] | 读取+写入[!DNL Marketo Optimizer] |
| `journey-reentry` | 配置重新进入：允许/不允许、关闭、最大条目数。 | 写入 | [!DNL Marketo Optimizer] | 读取+写入[!DNL Marketo Optimizer] |
| `journey-trafficcontrol` | 运行显示配置文件路由的流量控制模拟。 | 读取 | [!DNL Marketo Optimizer] | 读取[!DNL Marketo Optimizer]（模拟） |
| `journey-observability` | 调试/监控进度 — 路径、计时、拆分、停顿、停顿。 <p>查看&#x200B;_[调试和监视旅程Progression](./journey-observability.md)_。 | 读取 | [!DNL Marketo Optimizer] | 读取[!DNL Marketo Optimizer] + [!DNL Marketo Engage]（静态列表检查） |

## 受众和人员 {#audiences-people}

| 技能 | 作用 | 访问 | 产品 | 后端（数据流） |
|---|---|---|---|---|
| `audience-creation` | 调整[!DNL Marketo Engage]智能列表、创建人员列表或添加/更新规则。 <p>请参阅&#x200B;_[为项目创建受众](./audience-creation.md)_。 | 写入 | [!DNL Marketo Optimizer] | 读取[!DNL Marketo Engage] +读取/写入[!DNL Marketo Optimizer]。 |
| `people-list-comparison` | 比较两个人员列表并显示重叠的成员。 | 读取 | [!DNL Marketo Optimizer] | 读取[!DNL Marketo Optimizer] |
| `import-leads` | 检查CSV数据质量并将导入提交到[!DNL Marketo Engage]。 | 读+写 | 两者 | 读取+写入[!DNL Marketo Engage] |
| `lead-investigation` *（调查潜在客户）* | 调查商机的活动、评分、资格鉴定和生命周期。 | 读取 | [!DNL Marketo Engage] | 读取[!DNL Marketo Engage] |

## 内容和渠道 {#content-channels}

| 技能 | 作用 | 访问 | 产品 | 后端（数据流） |
|---|---|---|---|---|
| `content-personalization` | 浏览/预览模板和编辑内容/生成变体。 | 读+写 | [!DNL Marketo Optimizer] | 读取+写入[!DNL Marketo Optimizer]。 查看&#x200B;_[按角色个性化电子邮件内容](./personalize-content.md)_。 |
| `asset-tokens` | 程序/文件夹/历程中的完整令牌CRUD。 | 读+写 | [!DNL Marketo Optimizer] | 读取+写入[!DNL Marketo Optimizer] |
| `fcs-channels` | 渠道查找和CRUD +发布/停止/删除。 | 读+写 | [!DNL Marketo Optimizer] | 读取+写入[!DNL Marketo Optimizer] |

## 评分和信号 {#scoring-signals}

| 技能 | 作用 | 访问 | 产品 | 后端（数据流） |
|---|---|---|---|---|
| `scoring-studio` | 列出/获取评分模型并构建/发布它们。 <p>请参阅&#x200B;_[创建自定义评分模型](./lead-scoring-model.md)_。 | 读+写 | [!DNL Marketo Optimizer] | 读取+写入[!DNL Marketo Optimizer] （评分服务）；读取[!DNL Marketo Engage]潜在客户字段/活动类型。 |
| `engagementconfiguration` | 显示参与配置和编辑/更新权重。 | 读+写 | [!DNL Marketo Optimizer] | 读取+写入[!DNL Marketo Optimizer] |
| `intentconfiguration` | 显示意图配置和设置/更新权重。 | 读+写 | [!DNL Marketo Optimizer] | 读取+写入[!DNL Marketo Optimizer] |
| `intent-query` | 按人员/区段/列表查询和解释意图分数。 | 读取 | [!DNL Marketo Optimizer] | 读取[!DNL Marketo Optimizer] |

## 发送时间优化 {#sto}

| 技能 | 作用 | 访问 | 产品 | 后端（数据流） |
|---|---|---|---|---|
| `send-time-optimization` | 检查STO状态并在电子邮件节点上启用/禁用。 | 读+写 | [!DNL Marketo Optimizer] | 读取+写入[!DNL Marketo Optimizer] |
| `send-time-report` | 获取/显示STO性能报告。 | 读取 | [!DNL Marketo Optimizer] | 读取[!DNL Marketo Optimizer] |

## 知识 {#knowledge}

| 技能 | 作用 | 访问 | 产品 | 后端（数据流） |
|---|---|---|---|---|
| `product-knowledge` | 回答有关Experience League的[!DNL Marketo Optimizer]文档中的操作方法/概念问题。 | 读取 | 两者 | 读取外部文档 — 无产品数据 |

## 跨后端 {#cross-backend}

这些技能跨越多个后端：

- **`adapt-program`** — `gather_program_assets`读取[!DNL Marketo Engage] (`get_program`， `get_smart_campaign`， `list_emails`)，然后通过`falcomcp_create_journey`写入 — 经典跨后端。
- **`audience-creation`** — 读取[!DNL Marketo Engage]个智能列表(`get_smart_list` / `get_smart_campaign`)，然后写入[!DNL Marketo Optimizer]个人列表。
- **`journey-observability`** — [!DNL Marketo Optimizer]读取加上`check_lead_in_marketo_static_list` [!DNL Marketo Engage]读取。
- **`scoring-studio`** — 与[!DNL Marketo Optimizer]评分服务一起读取[!DNL Marketo Engage]潜在客户字段/活动类型。

所有`falco-mcp_*`和journey/token/scoring/STO/FCS工具点击[!DNL Marketo Optimizer]服务；CSV/program/lead工具点击[!DNL Marketo Engage]。
