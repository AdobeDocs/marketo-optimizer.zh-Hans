---
title: 历程流量控制
description: 了解Marketo Optimizer中的历程流量控制如何在受众重叠时，跨七个加权维度使用AI得分将每个人注册到其单一的最佳拟合历程中。
source-git-commit: c7d3546d075f5a58923134231217b2fd10fe4aca
workflow-type: tm+mt
source-wordcount: '1543'
ht-degree: 0%

---

# 历程流量控制

当受众重叠时，历程流量控制(JTC)会优先考虑人员的最佳旅程。 当一个人符合多个支持JTC的历程的资格时，AI模型会针对每个候选人评估他们，并将他们添加到最适合的历程中，将它们挡在其他候选人之外。

>[!NOTE]
>
>历程流量控制对[!DNL Journey Optimizer B2B Edition]和[!DNL Marketo Optimizer]的工作方式相同。 功能和逻辑相同；各层之间只有细微的UI差异。 此页面中的信息反映了[!DNL Marketo Optimizer]体验。

人员完成历程后，将为其仍符合条件的剩余历程重新评估他们。 然后，JTC将它们添加到下一个最合适的历程中，以此类推。 这样可以防止将同一人同时分配到多个重叠的历程，并确保每个联系人首先获得最相关的体验。

>[!NOTE]
>
>目前，一次只能将人员置于一个JTC选择的历程中。 计划在未来版本中提供一个管理员配置选项，以允许人员同时注册多个历程。

## 评分维度 {#scoring-dimensions}

模型跨七个评分维度评估每个人的历程组合。 每个维度单独评分，然后根据您配置的权重进行组合，以生成该人员和旅程的最终匹配概率。 选择具有最强匹配的历程。

| 维度 | 评估内容 |
|---|---|
| 意图对齐 | 行为意图信号：关键词搜索、产品页面访问、内容下载、电子邮件打开/点进和定价页面活动。 |
| 受众适合 | 人员与历程的[目标受众](./person-audience-node.md)匹配的程度。 |
| 角色适合 | 人员的角色/[角色](../audiences/personas.md)和历程之间的对齐方式。 |
| 首次匹配 | 公司级别的属性（如行业、规模和收入）。 |
| 人口统计匹配 | 人员级别的人口统计属性。 |
| 心理对齐 | 基于态度/偏好的对齐。 |
| 参与度适合 | 人员的[参与](../audiences/engagement-scores.md)的回访间隔和深度。 |

系统会自动跳过人员没有数据的维度，因此永远不会因缺少属性而惩罚评分。

>[!IMPORTANT]
>
>必须至少为两个历程启用JTC，才能执行任何有意义的操作。 在单个历程中启用它没有效果，因为不存在要仲裁的竞争性历程。 仅当两个或多个历程启用了JTC时，模型才会开始解决冲突。

## 先决条件 {#prerequisites}

在旅程流量控制产生结果之前，请牢记以下几点：

* **报告需要一个已发布、支持JTC的历程。** 在至少发布一个启用了历程流量控制的历程之前，_[!UICONTROL 报告]_&#x200B;选项卡不显示任何数据。
* **模拟在实例中至少需要一个已发布的历程。** 模拟会评估实时历程中已存在的[用户档案](../audiences/people-lists.md)，因此它需要在实例中至少有一个已发布历程才能从中提取用户档案。 模拟本身不需要启用JTC（请参阅&#x200B;[_模拟评分_](#simulate-scoring)）。

## 快速入门 {#get-started}

在左侧导航中选择&#x200B;**[!UICONTROL 历程流量控制]**。 显示的页面有两个选项卡：

* **[!UICONTROL 报告]** — 查看流量控制运行的结果（仅在JTC在实时历程上运行后填充）。
* **[!UICONTROL 配置]** — 调整评分维度，模拟结果，并选择哪些历程参与。

>[!IMPORTANT]
>
>对于从未使用历程流量控制的全新客户，_[!UICONTROL 报告]_&#x200B;选项卡为空。 报表仅反映已应用并运行流量控制的历程。 从&#x200B;_[!UICONTROL 配置]_&#x200B;选项卡开始。

## “配置”选项卡 {#configuration-tab}

_[!UICONTROL 配置]_&#x200B;选项卡包含两个部分：**[!UICONTROL 调整维度得分]**&#x200B;和&#x200B;**[!UICONTROL 选择历程]**。

### 调整维度评分 {#adjust-dimension-scoring}

在本节中，您可以设置七个维度中的每一个对最终比赛分数的贡献大小。 每个维度都可以设置为&#x200B;**[!UICONTROL 关]**、**[!UICONTROL 低]**、**[!UICONTROL Medium]**&#x200B;或&#x200B;**[!UICONTROL 高]**&#x200B;重要性。 每张卡片上显示的百分比是该维度在合并所有选择后的标准化贡献 — 七个权重总和为100%。 提升一个维度会自动使其他维度重新正常化，以使总维度保持在100%。

单击&#x200B;**[!UICONTROL 重置为等于]**&#x200B;可将所有维度恢复为均等权重。

![历程流量控制 — 在“配置”选项卡上调整维度记分卡](./assets/journey-traffic-control-configuration.png){width="800" zoomable="yes"}

### 模拟评分 {#simulate-scoring}

在将权重提交到生产环境之前，您可以模拟流量控制在这些更改下的行为。 模拟不需要启用历程流量控制。 它会评估您实时历程中已有的用户档案，并将流量控制逻辑应用于这些用户档案，这样您就可以判断结果是否适合您选择的权重。

1. 选择要模拟的配置文件数。

1. 单击&#x200B;**[!UICONTROL 模拟评分]**。

结果标题汇总了运行：

* **已评估用户档案** — 已评分的用户档案数以及历程数。
* **平均冲突/配置文件** — 每个配置文件的平均竞争历程数。
* **平均匹配得分** — 所选历程的平均置信度。

![历程流量控制 — “配置”选项卡 — 模拟评分结果](./assets/journey-traffic-control-configuration-simulate-scoring.png){width="700" zoomable="yes"}

在摘要下方，每个评估的配置文件都显示为一个卡片，其中显示了选定的历程、关键原理、意图信号和匹配分数。 选择配置文件以打开详细信息视图，方法：

* **匹配得分** — 整体匹配，按维度进行颜色编码的划分。
* **决策** — 此人员符合条件的历程、选择的历程以及原因。
* **按权重排列的Dimension得分** — 推动决策的按维度得分，可展开以显示基础信号。

![历程流量控制 — 模拟评分结果 — 配置文件详细信息](./assets/journey-traffic-control-configuration-simulate-scoring-profile-details.png){width="450" zoomable="yes"}

如果对结果满意，您可以：

* 调整维度权重，然后单击&#x200B;**[!UICONTROL 再次运行]**&#x200B;以重新运行模拟。

* 单击&#x200B;**[!UICONTROL 应用到生产]**&#x200B;以提交权重。

  新的流量控制决策会立即使用新设置；过去的决策不会受到影响。 您测试的权重显示在主&#x200B;_[!UICONTROL 配置]_&#x200B;选项卡上，并用于实时环境中正在评估的任何历程流量控制。

也可以不应用权重而离开页面。

<!--

This section does not appear in the staging environment

### Select journeys {#select-journeys}

The _[!UICONTROL Select journeys]_ section is where you choose which journeys participate in traffic control.

>[!IMPORTANT]
>
>Only draft journeys are available for selection. Traffic control cannot be enabled for a journey that is already live. When JTC is enabled for a journey and then that journey is published, it cannot be disabled.

-->

## 为历程启用流量控制 {#enable-traffic-control-journey}

当两个或更多历程启用并发布历程流量控制时：

* 系统会根据其用户档案和历程元数据评估符合一个或多个历程条件的任何人。
* 如果人员同时符合多个支持JTC的历程（例如，五个）的条件，则模型会确定哪一个是当下最佳历程，并将人员仅注册到该历程。 他们被挡在别人门外。
* 该人员继续该历程，直到历程完成。
* 完成后，将针对其余仍然符合条件的历程重新评估它们并将其添加到下一个最佳历程，重复直到没有符合条件的历程剩余为止。

### 为草稿历程启用JTC {#enable-traffic-control-draft-journey}

当单个历程处于&#x200B;_草稿_&#x200B;状态时，可以直接在该历程上启用历程流量控制。<!-- This is the same setting surfaced from the admin/configuration flow — enabling it in either place keeps the two in sync. -->

1. 在左侧导航栏中，展开&#x200B;**[!UICONTROL 营销管理]**。

1. 在&#x200B;**[!UICONTROL 营销]**&#x200B;资源列表的右侧，选择&#x200B;**[!UICONTROL 人员历程]**。

1. 单击草稿人员历程的名称以将其打开。

1. 单击&#x200B;**[!UICONTROL ...更多位于右上角的]**，然后选择&#x200B;**[!UICONTROL 历程流量控制设置]**。

   ![历程流量控制 — 为草稿人员历程启用](./assets/journey-traffic-control-enable-journey.png){width="700" zoomable="yes"}

1. 在对话框中，启用&#x200B;**[!UICONTROL 启用历程流量控制]**&#x200B;选项。

   “设置”对话框将解释该行为：启用时，历程将成为候选人，模型将为符合多个活动历程资格的人评估并提出最合适的历程。

   ![历程流量控制 — 启用切换](./assets/journey-traffic-control-enable-dialog.png){width="380"}

1. 单击&#x200B;**[!UICONTROL 保存]**。

>[!IMPORTANT]
>
>当历程保持在&#x200B;_草稿_&#x200B;状态时，可以随时更改切换。<!-- If it was already enabled from the admin section (or previously enabled by someone else), the toggle appears on. --> 在启用JTC的情况下发布历程后，流量控制会评估进入该历程的条目，并且您无法再禁用设置。

### 优化历程描述 {#optimize-journey-description}

交通控制代理可以有效地利用历程的元数据（历程中的节点、受众名称以及类似的结构信号）来指导其决策。 但是，丰富的描述性历程描述可为其带来巨大益处，该描述清楚地说明了历程的宗旨和目标。

强有力的描述为模型提供了所需的环境，以便更好地判断一个人是否属于该历程，而不是属于竞争历程。 当旅程非常基本时，这一点最为重要。 例如，只有少数节点的历程提供的上下文有限，因此清楚地描述其目标和目标受众有助于模型正确选择。

>[!TIP]
>
>将历程描述视为决策模型的输入，而不仅仅是内部文档。 描述历程的目的（尝试实现的目标）、目标以及目标受众。 描述越清晰，当一个人符合多个重叠旅程的资格时，流量控制就能越准确地仲裁 — 尤其是对于节点较少的轻量级旅程。

## “报表”选项卡 {#reporting-tab}

为两个或多个运行已完成的历程启用流量控制后，_[!UICONTROL 报告]_&#x200B;选项卡会显示结果。 有两种视图：**[!UICONTROL 按运行]**&#x200B;和&#x200B;**[!UICONTROL 按历程]**。

### 按运行 {#by-run}

_[!UICONTROL By run]_&#x200B;视图列出了每次流量控制运行。 对于每次运行，您可以查看时间、触发器（计划或手动）、评估的活动历程、评估的人员、流量控制决策、处理时间和状态。 选择某个运行以打开包含该运行的这些关键量度的详细信息面板，以及在该运行中评估的历程列表。

![历程流量控制 — “报表”选项卡 — 按运行视图](./assets/journey-traffic-control-reporting-tab-by-run.png){width="700" zoomable="yes"}

### 按历程 {#by-journey}

使用&#x200B;_按历程_&#x200B;查看流量控制对任何给定历程有何影响。 该表按历程显示已评估、已注册此历程、已移至其他历程并已处于活动状态的人员数量。

![历程流量控制 — “报表”选项卡 — 按历程视图](./assets/journey-traffic-control-reporting-tab-by-journey.png){width="700" zoomable="yes"}

<!--
Selecting a journey opens a detail panel:

* **Summary** — Total people evaluated, broken down into _Enrolled in this journey_, _Moved to other journeys_, and _Already active_.
* **Competing journeys** — Every journey that had people competing with this one, and how many were enrolled in each.
* **People evaluated** — The individual people, each with an outcome (_Enrolled_, _Moved_, or _Already active_), competing journeys, and match score.

>[!TIP]
>
>The sum of enrolled people across all competing journeys always equals the _Moved to other journeys_ count in the summary. _Already active_ means the person was already in the journey when the evaluation occurred.

Selecting an individual person shows the same detail view as in simulation: the match score, the decision (competing journeys and which journey was selected and why), and the full dimension breakdown behind the selection.
-->
