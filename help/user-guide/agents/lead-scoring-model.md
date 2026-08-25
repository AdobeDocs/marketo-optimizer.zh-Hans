---
title: 创建自定义评分模型
description: 在同事聊天界面中使用Scoring Studio技能在Marketo Optimizer中构建、预览和发布自定义潜在客户评分模型。
source-git-commit: 75b481faf0d66210329f95c8afabdfa59e7bcb79
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 1%

---

# 创建自定义评分模型

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_scoring_studio"
>title="Scoring Studio"
>abstract="使用Scoring Studio技能通过同事聊天界面创建、配置和发布自定义潜在客户评分模型。"

[!DNL Adobe Marketo Optimizer]中的&#x200B;[_Scoring Studio_&#x200B;技能](./skills.md#scoring-signals)提供了AI本机潜在客户评分解决方案，允许您创建、配置和发布潜在客户评分模型。 Studio将代理驱动的工作流与可视化UI相结合 — 您可以通过[同事聊天界面](./chat-interface.md)中的自然语言提示或直接与UI控件交互来构建评分模型。

* **技能** - `scoring-studio`
* **调用** — 使用斜杠命令打开Scoring Studio。 例如： _“打开评分工作室”_。
* **从**&#x200B;读取/写入 — [!DNL Marketo Optimizer]评分服务；读取[!DNL Marketo Engage]潜在客户字段和活动类型

在启动时，同事会自动获取相关上下文（包括活动类型、潜在客户字段、人员列表和现有得分列表），以便在您的数据中提供其建议。

在同事聊天界面中启动了![评分工作室](./assets/scoring-studio.png){width="700" zoomable="yes"}

## 创建评分模型 {#create-model}

在打开Scoring Studio时，Co-worker会建议一个相关的示例评分模型，该模型预先填充了一个静态列表和一组已评分的活动。 您可以接受这个建议的起点，或提供自己的提示来定义自定义模型。

### 预览模型 {#preview-model}

提供提示后，Co-worker会在进行任何更改之前生成模型预览。 预览曲面：

* 评分维度正在使用中
* 要评分的属性和活动
* 作为区段应用的静态列表或智能列表
* 模型目标、目标区段和主要信号的摘要

您可以查看预览并选择根据它创建模型，或者在最终确定之前继续通过聊天进行优化。

### 模型结构 {#model-structure}

已创建的模型已组织为&#x200B;_维度_&#x200B;和&#x200B;_信号_。 您可以使用UI中的属性面板配置每个信号：

* **信号类型** — 基于活动或基于属性
* **活动或属性** — 要评分的特定项目
* **信号参数** — 信号的可调整设置

您可以使用自然语言完全通过Co-worker构建和配置模型，或直接与UI控件交互。

## 发布评分模型 {#publish-model}

模型最终完成后，指示同事发布模型。 发布过程会自动处理以下内容：

| 步骤 | 发生什么情况 |
|---|---|
| **规则编译** | 编译并验证所有评分规则 |
| **得分任务创建** | 创建并配置计划得分任务以每天运行 |

发布后，您还可以选择触发手动运行以立即处理得分。

## 查看评分结果 {#view-results}

评分运行完成后，评分将通过商机导入过程回写到[!DNL Marketo Engage]。 导入完成后，可以直接在[!DNL Marketo Engage]中验证更新的得分。

在每次运行后，您可以查看结果摘要，其中显示：

* 有多少人得分
* 每个人的个人分数发生变化

审核日志可用于审核其他运行详细信息。
