---
title: 交互式网络研讨会
description: 了解Marketo Optimizer中交互式网络研讨会背后的概念，包括网络研讨会资源模型、成员国、令牌和活动。
keywords: 
role: User
feature: Channels
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 75b481faf0d66210329f95c8afabdfa59e7bcb79
workflow-type: tm+mt
source-wordcount: 1085
ht-degree: 2%

---


# 交互式网络研讨会

交互式网络研讨会允许您在不离开[!DNL Adobe Marketo Optimizer]的情况下规划、提升、交付和跟进直播或模拟直播网络研讨会。 传递在[!DNL Adobe Connect]上自动运行，因此您无需将产品切换为设计注册页面、托管实时会话或拉取出席数据。

>[!NOTE]
>
>此功能需要许可证并受其他条款和条件的约束。 要查询其他条款和条件，请查看您的合同或联系Adobe。

您可以通过两种方式创建网络研讨会：

* **对话体验** — 要求同事以自然语言安排、推广和报告网络研讨会。 请参阅[与同事一起创建网络研讨会](../agents/webinar-creation.md)。

* **点击式** — 使用&#x200B;_[!UICONTROL 程序]_&#x200B;工作区添加网络研讨会资源、设计该资源、添加联合主持人和演示者、构建促销活动和跟进历程，以及查看报告。 查看[创建和设计网络研讨会](create-webinar.md)和[网络研讨会促销和后续历程](webinar-journeys.md)。

## 将网络研讨会作为资产

网络研讨会是[项目](https://experienceleague.adobe.com/en/docs/journey-optimizer-b2b/prime/marketing-management/programs/programs)所拥有的资产，与电子邮件或登陆页面相同。 将网络研讨会添加到项目中可在其中注册该研讨会，并使其令牌、属性和活动可用于该计划中的每个历程和资产。

>[!IMPORTANT]
>
>项目目前可以拥有一项网络研讨会资产。 计划在未来的版本中，每个项目支持多个网络研讨会。

## 会员国

对于包含网络研讨会的计划成员中的任何个人，应同时申请3个独立国家/地区。 每个变量都可以在受众和历程条件中单独引用。

| 州 | 所有者 | 值 |
|---|---|---|
| 项目群成员状态 | 项目 | 可按[程序类型](https://experienceleague.adobe.com/en/docs/journey-optimizer-b2b/prime/admin/program-types)配置 |
| 网络研讨会状态 | 网络研讨会资产 | 邀请、注册、已参加、不显示、按要求参加 |
| 历程状态 | 历程 | 当前节点、已暂停、已完成和其他历程运行时状态 |

### 网络研讨会状态

网络研讨会状态包含五个值。 [!DNL Adobe Connect]通常会自动设置值，但如果您需要覆盖该值，您还可以通过历程操作设置状态。 例如，要反映在另一个系统中记录的出勤情况，您可以在历程中设置状态。

| 状态 | 设置方式 | 源 |
|---|---|---|
| 已邀请 | _执行操作_&#x200B;历程节点，通常在发送邀请电子邮件时 | 作者控制 |
| 已注册 | 人员注册时&#x200B;_执行操作_&#x200B;历程节点。 这还会触发[!DNL Adobe Connect]生成人员的加入URL | 作者控制 |
| 已参加 | 实时网络研讨会运行后来自[!DNL Adobe Connect]的事件 | 系统控制，可通过历程覆盖创作 |
| 不显示 | 实时网络研讨会运行后来自[!DNL Adobe Connect]的事件 | 系统控制，可通过历程覆盖创作 |
| 按需参加 | 来自[!DNL Adobe Connect]的事件，未参加的人稍后会现场观看录制 | 系统控制，可通过历程覆盖创作 |

>[!IMPORTANT]
>
>无论是通过自动设置还是通过历程设置，网络研讨会状态都只沿一个方向移动，与[项目状态](./programs.md#statuses)相同。 人员可以移动到较晚的状态（例如，_已注册_&#x200B;到&#x200B;_已参加_），但不能返回到较早的状态。 规划任何作者覆盖，并考虑此线性进展。

若要从历程在状态之间移动人员，请使用&#x200B;**[!UICONTROL 更改网络研讨会成员状态]**&#x200B;操作。 查看[网络研讨会推广和后续历程](webinar-journeys.md)。

## 网络研讨会令牌

网络研讨会令牌可在您个性化电子邮件内容的任意位置使用（主题、正文、邮件引文和发件人）。 在&#x200B;**_上下文>网络研讨会_**&#x200B;下的个性化编辑器中查找它们。

资产级别的令牌直接位于网络研讨会文件夹中：

- 标题
- 描述
- 开始日期时间，结束日期时间
- 持续时间
- 时区
- 演示者
- 录制URL

>[!NOTE]
>
>联合主机会显示在网络研讨会页面的“网络研讨会团队”部分中，但不能作为个性化令牌使用。

每个收件人的令牌位于&#x200B;**Member**&#x200B;子文件夹中：

- **状态** — 收件人的当前网络研讨会状态（已邀请、已注册、已参加、不显示或按需）。 查看[网络研讨会状态](#webinar-status)。
- **正在加入URL** — 收件人的个人[!DNL Adobe Connect]链接。 只有在收件人的网络研讨会状态为“已注册”或稍后版本之后，才会解决此问题。 对于早期阶段的任何人，它都会解析为空白。
- **录制URL** — 在录制发布到实时会话之后解析，在此之前保持为空。 有条件地在网络研讨会后电子邮件中使用它，以便在要显示录制之前不会显示链接。

>[!NOTE]
>
>网络研讨会令牌当前仅呈现在电子邮件内容中（主题、正文、预编译头和发件人）。 计划在未来的版本中，支持登陆页面和表单中的网络研讨会令牌。
>
>由于这些令牌解析为空而不是引发错误，因此引用它们的电子邮件或页面会在网络研讨会生命周期的任何时间点安全地呈现。 在值可用之前和之后预览内容，以确认布局朝任一方向看起来都正确。

## 网络研讨会活动

每个网络研讨会都会自动报告可用作&#x200B;_侦听事件_&#x200B;触发器、_拆分路径_&#x200B;条件、受众筛选器和报告量度的活动：

* 提出问题
* 响应轮询
* 单击链接
* 下载资产
* 举手

>[!NOTE]
>
>网络研讨会状态更改（“已邀请”、“已注册”、“已参加”、“不显示”、“已参加”按需）当前不作为他们自己的&#x200B;_侦听事件_&#x200B;触发器或活动过滤器提供。 要在网络研讨会状态上分支历程，请直接在网络研讨会状态上使用&#x200B;_拆分路径_&#x200B;条件（在&#x200B;[_构建网络研讨会后历程_](webinar-journeys.md#build-post-webinar-journey)&#x200B;中介绍），而不是侦听状态更改活动。

在现场活动后观看录像的人员参与将被摄取为相同的活动，并标记为按需模式。 与活动不同，点播参与确实会创建单独的网络研讨会状态：未参加实时活动但后来观看了录像的人员从&#x200B;**无节目**&#x200B;移至&#x200B;**点播参加**。

## 先决条件

在开始构建网络研讨会之前，请确保已准备好。

| 先决条件 | 详情 |
|---|---|
| 程序 | 该网络研讨会添加到现有项目中。 营销运营分析人员通常首先创建项目。 |
| 网络研讨会许可证（容量） | 在安排网络研讨会之前，必须提供网络研讨会许可证（也称为能力权利）。 您可在安装时选择容量，并且可能提供更高容量的插件。 要增加可用容量，请联系您的Adobe客户团队。 |
| [!DNL Adobe Connect] | 传递在[!DNL Adobe Connect]中运行。 在后台自动进行配置。 您无需离开[!DNL Marketo Optimizer]即可创作或主持网络研讨会。 |

### 权限

网络研讨会功能的访问权限取决于您分配的网络研讨会权限。

| 角色 | 授予的内容 |
|---|---|
| 查看B2B网络研讨会 | 查看网络研讨会列表和网络研讨会配置、详细信息和报告。 创建、设计、编辑和输入控件无法通过此权限使用，并且不能将您指定为网络研讨会的联合主持人或演示者。 |

<!-- 
| Manage B2B webinars | Full lifecycle access: create, design, configure, schedule, edit, deliver, host, and delete a webinar. The Create, Design, Edit, and Manage controls are available only for users with this role. |
| Webinar co-host | After you are added as a co-host, this permission enables you to design and enter that webinar with co-host controls. |
| Webinar presenter | After you are added as a presenter, this permission enables you to view and enter that webinar with presenter capabilities. It grants no authoring or design access on its own. |

>[!NOTE]
>
>Co-hosts and presenters are currently defined by entering a name and email rather than selected from a picker of role-eligible users — see [Add co-hosts and presenters](create-webinar.md#add-co-hosts-and-presenters). The _Webinar co-host_ and _Webinar presenter_**_ roles still govern what that person can do when they are added as a co-host or presenter.

-->
