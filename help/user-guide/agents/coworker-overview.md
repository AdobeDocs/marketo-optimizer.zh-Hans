---
title: Adobe Marketo Optimizer中的CX Enterprise Coworker概述
description: 了解CX Enterprise Coworker如何使用Marketo Optimizer技能创建和调整项目、检查AI决策准备情况并调用MCP工具。
autotag-review: '2026-11-24T22:43:00.917Z'
TQID: https://experienceleague.adobe.com/V4Kww-NcdfbFxXqWrs7mPq7UYu8AREqDgyfvlMnlURM
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 1650dadf-b034-5ac9-a309-77ad1e2f5035
    internal-label: Chat Interface
  - id: 5229c72e-d79b-574f-a03e-5c4bf48172c3
    internal-label: AI Decisioning
  - id: a29661b8-f7a4-53d1-a9ac-fdec08c092e4
    internal-label: Programs
subfeature_v2:
  - id: b9e5c7f3-be30-563c-9e41-cc8ea76e2fee
    internal-label: Skills
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
  - id: bbbea26f-9621-49eb-9ab8-e06fb3bbce8c
    internal-label: Artificial intelligence
source-git-commit: 418b81a0a39eca0ca7b537c76da972df7eefd09f
workflow-type: tm+mt
source-wordcount: '1313'
ht-degree: 2%
---

# [!DNL Adobe Marketo Optimizer]中的[!DNL CX Enterprise Coworker] {#coworker-overview}

[!DNL CX Enterprise Coworker]聊天是一种用于在[!DNL Adobe Marketo Optimizer]中完成任务的对话界面。 以纯语言描述目标，[!DNL Coworker]规划任务，在[!DNL Marketo Optimizer]中执行这些任务，验证结果，并提供完成的工作以供您审批。

[!DNL Coworker]使用为[!DNL Marketo Optimizer]构建的技能引导您完成常见的营销操作任务：创建新项目、调整现有[!DNL Marketo Engage]项目，以及检查您的数据是否准备好进行AI决策。

[!DNL Coworker]尊重您组织的现有[[!DNL Marketo Optimizer] 权限](../start/permissions-reference.md)。 您只能执行已经允许您执行的操作，并且管理员会在您具有写入权限时控制您执行的操作。 [!DNL Coworker]是Adobe生态系统的一部分，不限于[!DNL Marketo Optimizer]。

有关更多信息，请参阅：

* [[!DNL Adobe CX Enterprise Coworker]聊天概述](https://experienceleague.adobe.com/zh-hans/docs/coworker/content/chat/overview)
* [&#x200B; [!DNL Marketo Optimizer]中的聊天界面](./chat-interface.md)
* [&#x200B; [!DNL Marketo Optimizer]中的[!DNL Coworker]技能](./skills.md)

## [!DNL CX Enterprise Coworker]中的[!DNL Marketo Optimizer]技能 {#skills}

使用以下产品特定的技能创建和调整项目或评估数据准备情况。

| 技能 | 它有助于您完成哪些工作 | 示例请求 |
| --- | --- | --- |
| `program-creation-marketo-optimizer` | 创建端到端的[!DNL Marketo Optimizer]营销计划。 [!DNL Coworker]引导您从目标完成到构建的计划。 | 上载促销活动简报，然后询问：_使用附加的简报创建程序。_ |
| `adapt-program-marketo-optimizer` | 调整、迁移或转换现有[!DNL Marketo Engage]程序为[!DNL Marketo Optimizer]程序。 | _将我们的第3季度企业网络研讨会培训计划从[!DNL Marketo Engage]调整为[!DNL Marketo Optimizer]。_ |
| `ai-decisioning-health-marketo-optimizer` | 报告租户的数据是否已准备好进行AI决策，包括故事覆盖、特征丰富度和角色覆盖。 | _哪些数据用于AI决策？_ |

### 示例程序创建提示 {#program-creation-prompt}

上传简介或直接描述项目。 包括您希望[!DNL Coworker]使用的受众、历程、内容和设置。

该图总结了以下示例中的提示部分。 它展示了如何组织请求，而不是组织人员在历程中的移动顺序。

![八个项目创建提示部分：项目目标、受众、具有基于意图的邀请的历程、电子邮件内容、LinkedIn激活、注册处理、事件后跟进和设置。](./assets/coworker-program-creation-prompts.svg){width="800" zoomable="yes"}

展开每个部分以查看示例提示。

+++项目目标

_使用电子邮件和LinkedIn创建一个名为Experience Cloud领导力论坛 — 由AI提供支持的Experience Summit的B2B营销计划，于8月3日至12月3日召开。 本次活动于上午9:00在湾区创新中心举行。 立即开始历程。_

+++

+++受众

_定位具有任何Experience Cloud产品意图且参与得分大于1的人员。 排除已取消订阅和营销暂停的用户档案。_

+++

+++历程

_使用“下一个最佳路径”按“高”、“Medium”和“低”Experience Cloud意图拆分受众。 发送针对每个意图级别定制的个性化电子邮件邀请。 合并路径并等待两天。 检查电子邮件打开、点击、内容参与和注册。 向参与成员发送日程预览；在LinkedIn上激活未参与成员并等待两天。 合并参与路径并在事件发生10天前发送最终注册提醒。 为所有电子邮件启用发送时间优化。_

+++

+++电子邮件内容

_创建三封电子邮件：执行邀请（活动前6周）、日程预览（活动前6周）和最终注册提醒（活动前10天）。 包括相关主题行、标题、行动要求（保留我的名额、查看议程、完成注册）和使用人员故事、角色分类、行业、解决方案兴趣、最近参与和Experience Cloud意图的AI个性化内容。 在邀请中包含地点图像，但在日程预览中没有横幅。_

+++

+++LinkedIn

_定位未参与的成员，这些成员具有促进客户体验转化和AI个性化的赞助内容。_

+++

+++注册

_立即从邀请历程中退出注册成员，并发送一封高管准备电子邮件，其中包含人工智能生成的讨论主题、个性化议程、地点详细信息、推荐的会议以及日历链接。_

+++

+++帖子事件

_通过回顾、录制、资源和销售资格审查，将与会者安排到Experience Cloud领导力跟进计划。 发送不显示峰会亮点、按需内容以及未来活动邀请。_

+++

+++设置

_将my.replyToEmail设置为`events@example.com`，将my.senderName设置为Experience Cloud事件。 使用仅更改城市、地点、主题演讲和行业重点的可重用模板。_

+++

有关准备简介的详细信息，请参阅[从简介创建程序](./program-from-brief.md)。

## 示例用例 {#use-cases}

### 在检查数据准备情况后创建项目 {#check-readiness-create-program}

营销运营负责人希望在构建新的基于帐户的项目之前，了解租户已准备好进行人工智能决策。

1. 若要查看故事覆盖、特征丰富度和角色覆盖，请运行[AI决策运行状况检查](./ai-decisioning-health.md)。 例如，询问：_向我显示用于AI决策的Marketo数据。_
1. 解决报告发现的任何缺口。
1. 上传促销活动简报，并询问：_创建包含所附简讯的程序。_
1. 在[!DNL Coworker]显示结果时审阅并批准程序。

其结果是编制一份准备情况报告，找出不足之处，然后制定一个基于数据的计划，以支持人工智能决策。

### 将现有[!DNL Marketo Engage]项目移入[!DNL Marketo Optimizer] {#adapt-program}

需求生成团队希望在[!DNL Marketo Optimizer]中运行一个经过验证的程序，而无需手动重建它。

1. 命名要改写的[!DNL Marketo Engage]程序。 例如：_将Q3企业网络研讨会培训计划从[!DNL Marketo Engage]调整为[!DNL Marketo Optimizer]。_
1. [!DNL Coworker]将程序映射到[!DNL Marketo Optimizer]构造并标记任何未转换的内容。
1. 审查结果并批准。

结果是一个转换后的项目群供您审阅，另外还有一个需要手动决策的项目列表。

## [!DNL Marketo Optimizer] MCP工具 {#mcp-tools}

[!DNL Coworker]技能在[!DNL Marketo Optimizer]模型上下文协议(MCP)服务器上调用以下37个工具。 每个工具名称都带有前缀`marketo-optimizer__`。

此参考涵盖由已注册技能记录的工具，包括在工作流中使用的支持技能。 它不指示部署状态或使用频率。 此表中的技能名称会遵循工具引用，并且可能与上面列出的产品特定技能名称不同。

| 工具 | 技能 | 用途 |
| --- | --- | --- |
| `marketo-optimizer__get_workspace_root_tree` | `program-creation-marketo-optimizer` | 为新项目查找工作区区域或命名子文件夹。 |
| `marketo-optimizer__create_program` | `program-creation-marketo-optimizer` | 在已确认的区域或文件夹中创建项目。 |
| `marketo-optimizer__list_programs` | `program-creation-marketo-optimizer`, `landing-page-authoring` | 浏览程序或查找登陆页面的归档位置。 |
| `marketo-optimizer__get_program` | `program-creation-marketo-optimizer` | 按ID读取项目。 |
| `marketo-optimizer__update_program` | `program-creation-marketo-optimizer` | 更新项目元数据，如项目名称。 |
| `marketo-optimizer__create_program_token` | `program-creation-marketo-optimizer` | 创建或更正已批准的程序令牌。 |
| `marketo-optimizer__list_program_tokens` | `program-creation-marketo-optimizer` | 读取项目的已解析令牌。 |
| `marketo-optimizer__create_dynamic_people_list_with_rules` | `program-creation-marketo-optimizer` | 创建与项目关联的人员列表，并根据描述生成受众规则。 |
| `marketo-optimizer__list_people_journeys` | `adapt-program`；渠道插件共享引用 | 检查目标历程名称冲突，在结果不明确后找到现有历程，或浏览历程以了解渠道工作。 |
| `marketo-optimizer__create_person_journey` | `program-creation-marketo-optimizer`, `adapt-program`, `channel-content-authoring` | 创建与项目关联的历程、开始自适应历程或为电子邮件渠道创建缺失历程。 |
| `marketo-optimizer__get_person_journey` | `program-creation-marketo-optimizer`，`adapt-program`；渠道插件共享引用 | 读取历程或其画布，验证暂存的编辑，或查找历程以了解渠道工作。 |
| `marketo-optimizer__update_person_journey` | `adapt-program` | 每次向目标历程附加一个批准的构建步骤。 |
| `marketo-optimizer__run_person_journey_simulation` | `program-creation-marketo-optimizer` | 在不发布的情况下验证历程流。 |
| `marketo-optimizer__run_program_qa` | `program-creation-marketo-optimizer` | 对程序及其历程运行只读准备情况检查。 |
| `marketo-optimizer__create_channel` | `channel-content-authoring`；`program-creation-marketo-optimizer`和`image-to-html`通过移交 | 创建并链接渠道。 对于电子邮件，第一个调用会列出模板；第二个调用使用选定的模板创建和链接电子邮件。 |
| `marketo-optimizer__get_channel` | `channel-content-authoring` | 读取渠道，可以选择包括其电子邮件主题和HTML。 |
| `marketo-optimizer__list_channels` | `channel-content-authoring` | 按类型浏览渠道（可以选择按名称过滤）。 |
| `marketo-optimizer__update_channel_content` | `channel-content-authoring`；`image-to-html`通过移交 | 更新电子邮件的主题或HTML，包括应用转换后的HTML。 |
| `marketo-optimizer__image_to_html` | `image-to-html` | 开始异步电子邮件设计转换并检索可编辑的HTML。 |
| `marketo-optimizer__list_asset_library_images` | `landing-page-authoring` | 搜索登陆页面版块的替换图像。 |
| `marketo-optimizer__add_asset_to_program_or_folder` | `landing-page-authoring` | 在选定的优化程序程序程序或文件夹中注册新的登陆页面。 |
| `marketo-optimizer__get_person_story` | `personalization-engine-health` | 按数值ID阅读某人的个性化故事。 |
| `marketo-optimizer__get_persona_story` | `personalization-engine-health` | 请阅读故事以了解确切的角色名称。 |
| `marketo-optimizer__run_arbitration` | `personalization-engine-health` | 在明确确认后，为符合条件的人员重新评分并重新选择历程。 |
| `marketo-optimizer__get_arbitration_summary` | `personalization-engine-health` | 读取最新仲裁运行的摘要统计信息。 |
| `marketo-optimizer__get_arbitration_decisions` | `personalization-engine-health` | 阅读最新仲裁运行中每个人的决定。 |
| `marketo-optimizer__get_ai_decisioning_health_summary` | `ai-decisioning-health` | 获取整体的租户就绪报告。 |
| `marketo-optimizer__get_persona_distribution` | `ai-decisioning-health` | 报表角色计数和百分比。 |
| `marketo-optimizer__get_people_without_personas` | `ai-decisioning-health` | 报告无角色的用户数量和份额。 |
| `marketo-optimizer__get_person_story_attribute_coverage` | `ai-decisioning-health` | 测量特征类别覆盖范围并确定填充的字段。 |
| `marketo-optimizer__get_person_story_data_completeness` | `ai-decisioning-health` | 按角色报告故事的丰富性、完整性和变化。 |
| `marketo-optimizer__get_person_story_coverage` | `ai-decisioning-health` | 报告故事覆盖率、趋势和待处理生成。 |
| `marketo-optimizer__get_personalization_story_pipeline_status` | `ai-decisioning-health` | 读取管道状态、运行历史记录和报告的持续时间。 |
| `marketo-optimizer__get_person_story_refresh_backlog` | `ai-decisioning-health` | 由于源数据已更改而等待刷新的故事计数。 |
| `marketo-optimizer__get_person_intent_signal_coverage` | `ai-decisioning-health` | 衡量产品意图、关键词意图和活动范围。 |
| `marketo-optimizer__get_person_story_activity_coverage` | `ai-decisioning-health` | 报告捕获的参与字段和汇总活动趋势。 |
| `marketo-optimizer__get_person_audience_membership_distribution` | `ai-decisioning-health` | 报告每个人的受众成员资格的平均值和分布情况。 |
