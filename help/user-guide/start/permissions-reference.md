---
title: 产品权限
description: 控制对Experience Platform功能访问权限的Marketo Optimizer权限参考列表，包括说明以及针对管理员、完全访问和只读用户的建议权限。
TQID: https://experienceleague.adobe.com/Q4HnGxPkiE0dsZUjIgPvVJHgs0dPwLJiOKVSL1edS4Y
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 3cf5f37e-e87e-5179-812b-53ce05d7eebb
    internal-label: Setup
  - id: a659ad61-de21-559d-a901-02e2fb329ff5
    internal-label: Administration
subfeature_v2:
  - id: b6434e31-d7bb-5416-960c-1c77bb1a2e8d
    internal-label: User Access
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
    internal-label: Governance
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
autotag-review: '2026-10-20T17:03:48.312Z'
source-git-commit: e80513284d179a9b27d0505463d07d5e15facabb
workflow-type: tm+mt
source-wordcount: '1577'
ht-degree: 3%
---
# 产品权限

以下权限控制对[!DNL Adobe Marketo Optimizer]中各项功能的访问。 将它们添加到[!DNL Adobe Experience Platform]的&#x200B;_[!UICONTROL 权限]_&#x200B;区域中的角色。 有关创建角色并将其分配给用户的详细信息，请参阅&#x200B;[_用户访问和权限_](./user-management.md)。

最后三列显示每个[建议的用户类型](#suggested-user-types)所建议的权限： Admin、All Access User和Read Only Access User。 复选标记(✔)表示建议对该用户类型使用该权限，而短划线(-)表示不建议使用该权限。 调整推荐以适合您的组织。

>[!IMPORTANT]
>
>[!DNL Marketo Optimizer]访问要求您启用使用以下命名约定配置的特定沙盒： `Mktoaep` + [!DNL Marketo Engage]订阅前缀。 例如，如果链接的[!DNL Marketo Engage]订阅前缀为&#x200B;_AcmeAssoc_，则访问[!DNL Marketo Optimizer]所需的沙盒为&#x200B;_MktoaepAcmeAssoc_。 将此沙盒添加到每个角色。

>[!NOTE]
>
>您必须是系统管理员才能在Experience Platform中看到&#x200B;_[!UICONTROL 权限]_&#x200B;磁贴。

某些权限适用于产品中尚未提供的功能。 管理员现在可以添加这些权限，这样在功能可用时，用户就可以拥有相应的访问权限。

## 建议的用户类型 {#suggested-user-types}

使用此页上的表中的权限建议作为您创建的角色的起点。 这些是每种类型用户的建议。 调整它们以适合您的组织。

| 属性 | 管理员 | 全部访问用户 | 只读访问用户 |
| --- | ----- | --------------- | --------------------- |
| **代表谁** | 为您的团队设置和管理[!DNL Marketo Optimizer]的人员。 | 每天在[!DNL Marketo Optimizer]中工作的营销人员和操作员。 | 需要查看[!DNL Marketo Optimizer]但不更改任何内容的人员，例如高管、分析师和审计师。 |
| **他们能做什么** | 全部，包括设置和管理设置。 | 使用每个功能：历程、程序、内容、列表、报告和助手。 | 查看历程、程序、内容、列表和报告，并询问助理人员问题。 |
| **要分配的权限** | 此页面上的每个权限（在角色编辑器中选择&#x200B;**[!UICONTROL 添加所有]**）。 | 此页面上表的&#x200B;_所有访问_&#x200B;列中具有✔的权限。 | 此页面上表的&#x200B;_只读_&#x200B;列中具有✔的权限。 |
| **不包括** | – | <li>管理员配置<li>渠道配置，包括电子邮件设置、表单预设、登陆页面设置以及WhatsApp预设和设置<li>程序类型（查看和管理） | <li>创建、编辑、删除、发布或导出（所有&#x200B;_管理_&#x200B;和&#x200B;_发布_&#x200B;权限，聊天访问除外）<li>将受众激活到目标<li>管理员配置和渠道配置，包括查看电子邮件设置和表单预设<li>查看程序类型 |
| **建议的用户组** | Marketo Optimizer管理员组 | Marketo Optimizer用户组 | Marketo Optimizer只读用户组 |
| **建议的角色** | Marketo Optimizer管理员 | Marketo Optimizer完全访问用户 | Marketo Optimizer只读访问用户 |

有关创建这些组和角色的过程，请参阅[为建议的用户类型创建用户组和角色](./user-management.md#create-suggested-roles)。

## 内容和资产 {#content-assets}

| 类别 | 权限 | 描述 | 管理员 | 完全访问 | 只读 |
| -------- | ---------- | ----------- | :---: | :--------: | :-------: |
| B2B Assets | 管理B2B Assets | 创建、编辑和删除资源文件。 | ✔ | ✔ | – |
| | 管理B2B电子邮件 | 创建、编辑和删除电子邮件。 | ✔ | ✔ | – |
| | 管理B2B Forms | 创建、编辑和删除表单。 | ✔ | ✔ | – |
| | 管理B2B片段 | 创建、编辑和删除内容片段。 | ✔ | ✔ | – |
| | 管理B2B登陆页面 | 创建、编辑和删除登陆页面。 | ✔ | ✔ | – |
| | 管理B2B消息导出 | 导出&#x200B;_电子邮件_&#x200B;部分下的邮件报告。 | ✔ | ✔ | – |
| | 管理B2B模板 | 创建、编辑和删除内容模板。 | ✔ | ✔ | – |
| | 管理B2B网络研讨会 | 创建、编辑和删除交互式网络研讨会。 | ✔ | ✔ | – |
| | 发布B2B Forms | 发布用于登陆页面的表单。 | ✔ | ✔ | – |
| | 发布B2B片段 | 发布内容片段，以在模板、电子邮件和登陆页面中使用。 | ✔ | ✔ | – |
| | 发布B2B登陆页面 | 发布登陆页面。 | ✔ | ✔ | – |
| | 查看B2B Assets | 查看Assets库和资源文件详细信息。 | ✔ | ✔ | ✔ |
| | 查看B2B电子邮件 | 查看电子邮件。 | ✔ | ✔ | ✔ |
| | 查看B2B Forms | 查看表单。 | ✔ | ✔ | ✔ |
| | 查看B2B片段 | 查看内容片段列表和详细信息。 | ✔ | ✔ | ✔ |
| | 查看B2B登陆页面 | 查看登陆页面。 | ✔ | ✔ | ✔ |
| | 查看B2B模板 | 查看内容模板列表和详细信息。 | ✔ | ✔ | ✔ |
| | 查看B2B网络研讨会 | 观看交互式网络研讨会。 | ✔ | ✔ | ✔ |

## 渠道配置和管理 {#channels-admin}

| 类别 | 权限 | 描述 | 管理员 | 完全访问 | 只读 |
| -------- | ---------- | ----------- | :---: | :--------: | :-------: |
| B2B管理配置 | 管理B2B管理配置 | 配置管理设置，如数字资产管理连接、资产存储库和事件。 | ✔ | – | – |
| B2B渠道配置 | 管理 B2B 渠道配置 | 访问左侧导航中的&#x200B;_渠道_&#x200B;菜单项以及所有渠道配置操作。 | ✔ | – | – |
| | 管理B2B电子邮件设置 | 配置电子邮件设置。 用户发送电子邮件之前需要这些设置。 | ✔ | – | – |
| | 管理B2B Forms预设 | 创建、编辑和删除表单预设。 | ✔ | – | – |
| | 管理B2B登陆页面设置 | 配置登陆页面设置，如子域。 | ✔ | – | – |
| | 管理B2B WhatsApp预设 | 创建、查看和删除WhatsApp消息预设及关联的短信设置。 | ✔ | – | – |
| | 管理B2B WhatsApp设置 | 配置WhatsApp渠道设置。 | ✔ | – | – |
| | 发布B2B Forms预设 | 发布表单预设。 | ✔ | – | – |
| | 查看B2B电子邮件设置 | 查看电子邮件设置（子域、PTR记录、IP池、禁止列表、种子列表、IP预热计划）。 | ✔ | – | – |
| | 查看B2B Forms预设 | 查看表单预设。 | ✔ | – | – |

## 历程、程序和文件夹 {#journeys-programs}

| 类别 | 权限 | 描述 | 管理员 | 完全访问 | 只读 |
| -------- | ---------- | ----------- | :---: | :--------: | :-------: |
| B2B文件夹令牌 | 管理B2B文件夹令牌 | 创建、编辑和删除文件夹中的令牌。 更改将应用于文件夹中的所有内容，因此请将其与&#x200B;_管理B2B文件夹_&#x200B;分开分配。 | ✔ | ✔ | – |
| | 查看B2B文件夹令牌 | 查看文件夹上定义的令牌。 | ✔ | ✔ | ✔ |
| B2B文件夹 | 管理B2B文件夹 | 创建、编辑和删除文件夹。 | ✔ | ✔ | – |
| | 查看B2B文件夹 | 查看文件夹。 | ✔ | ✔ | ✔ |
| B2B历程 | 管理B2B历程流量控制 | 配置历程流量控制，包括模拟其效果。 | ✔ | ✔ | – |
| | 管理B2B人员历程 | 访问&#x200B;_人员历程_&#x200B;列表和所有人员历程操作。 | ✔ | ✔ | – |
| | 发布B2B人员历程 | 发布人员历程。 | ✔ | ✔ | – |
| | 查看B2B历程流量控制 | 查看历程流量控制设置。 | ✔ | ✔ | ✔ |
| | 查看B2B人员历程报表 | 查看人员历程报告，包括&#x200B;_人员历程个人_&#x200B;报告。 | ✔ | ✔ | ✔ |
| | 查看B2B人员历程 | 对&#x200B;_人员历程_&#x200B;列表和历程详细信息的只读访问权限。 | ✔ | ✔ | ✔ |
| B2B项目令牌 | 管理B2B项目令牌 | 创建、编辑和删除程序和程序类型上的令牌。 | ✔ | ✔ | – |
| | 查看B2B项目令牌 | 查看在程序和程序类型上定义的令牌。 | ✔ | ✔ | ✔ |
| B2B程序类型 | 管理B2B程序类型 | 创建、编辑和删除营销计划类型。 | ✔ | – | – |
| | 查看B2B程序类型 | 查看营销计划类型。 | ✔ | – | – |
| B2B程序 | 管理B2B程序 | 创建、编辑和删除营销项目。 | ✔ | ✔ | – |
| | 查看B2B程序 | 查看营销计划。 | ✔ | ✔ | ✔ |

## 受众、意图和目标 {#audiences-intent}

| 类别 | 权限 | 描述 | 管理员 | 完全访问 | 只读 |
| -------- | ---------- | ----------- | :---: | :--------: | :-------: |
| B2B目标 | 激活B2B目标 | 将受众激活到B2B目标。 | ✔ | ✔ | – |
| | 管理B2B目标 | 创建、编辑和删除B2B目标。 | ✔ | ✔ | – |
| | 查看B2B目标 | 对B2B目标的仅查看访问权限。 | ✔ | ✔ | ✔ |
| B2B意图配置 | 管理B2B意图配置 | 创建、编辑和删除目的配置。 | ✔ | ✔ | – |
| | 查看B2B意图配置 | 查看意图配置（意图加权模型）。 | ✔ | ✔ | ✔ |
| B2B组织规则 | 管理B2B组织规则 | 创建、编辑和删除组织规则。 | ✔ | ✔ | – |
| | 查看B2B组织规则 | 查看组织规则。 | ✔ | ✔ | ✔ |
| B2B人员列表 | 管理B2B人员列表 | 创建、编辑和删除人员列表，以及管理列表成员资格。 | ✔ | ✔ | – |
| | 查看B2B人员列表 | 查看静态和动态人员列表。 | ✔ | ✔ | ✔ |

## 报告、实验室和聊天 {#reports-labs-chat}

| 类别 | 权限 | 描述 | 管理员 | 完全访问 | 只读 |
| -------- | ---------- | ----------- | :---: | :--------: | :-------: |
| B2B对话体验 | 管理B2B对话体验 | 访问聊天面板和助手。 面板中的操作还需要具有匹配功能权限。 例如，创建历程需要&#x200B;_管理B2B人员历程_。 查看[聊天权限](#chat-permissions)。 | ✔ | ✔ | ✔ |
| B2B实验室 | 管理B2B实验室 | 启用和配置Labs功能。 | ✔ | ✔ | – |
| | 查看B2B Labs | 查看已启用的可用Labs功能。 | ✔ | ✔ | ✔ |
| B2B报告 | 查看B2B嵌入式报表 | 在&#x200B;_报告_&#x200B;选项卡中查看报告。 | ✔ | ✔ | ✔ |
| | 查看B2B意图报表 | 查看意图报表。 | ✔ | ✔ | ✔ |

## 聊天权限 {#chat-permissions}

聊天权限遵循功能级别的权限。 _管理B2B对话体验_&#x200B;允许访问[!DNL CX Coworker]聊天面板，但不授予对任何功能功能的访问权限。 同事根据功能在聊天外部所需的相同权限检查聊天中的每个技能或操作： _管理_&#x200B;创建、编辑或发布的权限，以及&#x200B;_查看_&#x200B;只读技能的权限。 如果用户缺少功能权限，[!DNL Coworker]无法为其执行该操作。 例如，创建历程需要&#x200B;_管理B2B人员历程_，而列出表单需要&#x200B;_查看B2B Forms_。

## 外部目标权限 {#external-destinations-permissions}

要为[!DNL Marketo Optimizer]中的用户提供外部目标访问权限，需要以下权限。 对于[建议的用户类型](#suggested-user-types)中描述的每种用户类型，列都遵循相同的建议。

| 类别 | 权限 | 描述 | 管理员 | 完全访问 | 只读 |
| -------- | ---------- | ----------- | :---: | :--------: | :-------: |
| 仪表板 | 管理标准仪表板 | 添加数据仓库中尚未存在的自定义属性。 | ✔ | ✔ | – |
| | 查看标准仪表板 | 对&#x200B;_配置文件_、_目标_&#x200B;和&#x200B;_区段_&#x200B;仪表板的仅查看访问权限。 还允许在左侧导航中访问&#x200B;_仪表板_。 | ✔ | ✔ | ✔ |
| 目标 | 激活目标 | 将数据激活到活动目标。 还需要&#x200B;_查看目标_&#x200B;或&#x200B;_管理目标_。 | ✔ | ✔ | – |
| | 激活没有映射的区段 | 无需映射步骤，即可将受众激活到现有目标。 用户可以在激活工作流中添加和删除受众，但无法添加或删除映射的属性或身份。 还需要&#x200B;_查看目标_。 | ✔ | ✔ | – |
| | 目标创作 | 使用Experience Platform Destination SDK创作目标。 | ✔ | ✔ | – |
| | 管理和激活数据集目标 | 查看、创建、编辑和禁用数据集导出流，以及激活数据集中的数据。 还需要&#x200B;_查看目标_。 | ✔ | ✔ | – |
| | 管理目标 | 查看、创建和删除目标连接和目标帐户。 | ✔ | ✔ | – |
| | 查看目标 | 查看&#x200B;_目录_&#x200B;选项卡中的可用目标和&#x200B;_浏览_&#x200B;选项卡中的已验证目标。 | ✔ | ✔ | ✔ |
| 数据监管 | 管理B2B删除使用标签 | 查看、创建和删除应用于数据集和架构的数据使用标签(DULE)。 | ✔ | ✔ | – |
| | 管理数据使用策略 | 查看、创建、编辑和删除数据使用策略。 | ✔ | ✔ | – |
| | 查看数据使用策略 | 对属于您组织的数据使用策略的仅查看访问权限。 | ✔ | ✔ | ✔ |
| 数据引入 | 管理源 | 查看、创建、编辑和禁用源。 | ✔ | ✔ | – |
| | 查看源 | 查看&#x200B;_目录_&#x200B;选项卡中的可用源和&#x200B;_浏览_&#x200B;选项卡中的已验证源。 | ✔ | ✔ | ✔ |
| 轮廓管理 | 管理配置文件设置 | 查看和编辑所有配置文件设置。 | ✔ | ✔ | – |
| | 查看配置文件设置 | 对所有配置文件设置的仅查看访问权限。 | ✔ | ✔ | ✔ |

<!-- 

## Planned permissions {#planned-permissions}

The following permissions are for features that are not yet available in [!DNL Marketo Optimizer]. Adobe Marketo Qualifier permissions are not currently enforced. The estimated enforcement date is November 2026. Accounts and buying groups are targeted for delivery in Q1 2027.

| Category | Permission | Description | Admin | All Access | Read Only |
| -------- | ---------- | ----------- | :---: | :--------: | :-------: |
| Marketo Qualifier Configurations | Manage Marketo Qualifier Configurations | Create, edit, and delete Marketo Qualifier configurations. | ✔ | – | – |
| | View Marketo Qualifier Configurations | View Marketo Qualifier configurations. | ✔ | ✔ | ✔ |
| Marketo Qualifier Outbound | View Marketo Qualifier Outbound | View Marketo Qualifier outbound workflows and outbound reporting. | ✔ | ✔ | ✔ |
| Marketo Qualifier Research | Manage Marketo Qualifier Research | Use and manage research capabilities. | ✔ | ✔ | – |
| | View Marketo Qualifier Research | View research: conversational interface, prospect view, and account and lead research. | ✔ | ✔ | ✔ |
| B2B Account Lists | Manage B2B Account Lists | Create, edit, and delete account lists, including adding, removing, and importing accounts. | ✔ | ✔ | – |
| B2B Buying Groups | Manage B2B Buying Groups | Create, edit, and delete buying groups. | ✔ | ✔ | – |
| | Manage B2B Role Templates | Manage the role templates used in buying groups. | ✔ | ✔ | – |
| | Manage B2B Solution Interests | Manage the solution interests used in buying groups. | ✔ | ✔ | – |
| | Manage B2B Stages | Manage buying group stages. | ✔ | ✔ | – |
| | View B2B Buying Groups | View buying groups. | ✔ | ✔ | ✔ |

-->
