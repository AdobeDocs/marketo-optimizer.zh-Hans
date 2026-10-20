---
title: 用户访问和权限
description: 在Adobe Admin Console中管理用户访问权限：创建Marketo Optimizer的用户组、分配产品配置文件以及设置基于角色的权限。
TQID: 'https://experienceleague.adobe.com/IY7Fvbk8GG2Xudh6vC4N9Bwk-sejvh-MMRIHHxvS-nc'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 3cf5f37e-e87e-5179-812b-53ce05d7eebb
    internal-label: Setup
  - id: 46e599c6-e20f-5f67-9824-93415016f66b
    internal-label: Audiences
topic_v2:
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
    internal-label: Governance
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: f65df8d5e83eca29ffaaabf51e7c80ed223d175a
workflow-type: tm+mt
source-wordcount: '2584'
ht-degree: 34%
---
# 用户访问和权限

配置完成并绑定沙盒后，请完成以下步骤为您的团队和用户提供[!DNL Marketo Optimizer]访问权限。

1. [在Admin Console中创建 [!DNL Marketo Optimizer] 产品配置文件](#create-profile)（仅限一次性/初始设置）。
1. 在Admin Console中[添加用户组](#add-user-group)。
1. [将产品配置文件](#assign-profile)分配给Admin Console中的用户组。
1. [在Admin Console中将用户添加到新组](#add-users)。
1. [编辑内置角色](#edit-role-permissions)或[在Experience Platform中创建具有产品权限和所需[!DNL Marketo Optimizer]沙盒的自定义角色](#create-a-custom-role)。
1. [将用户](#add-users-to-a-role)或[组](#add-user-groups-to-a-role)添加到Adobe Experience Platform中的角色。

要为管理员、所有访问权限的用户和只读用户设置推荐的用户组和角色，请参阅[推荐的用户类型](./permissions-reference.md#suggested-user-types)和[为推荐的用户类型创建用户组和角色](#create-suggested-roles)。

## 配置产品配置文件 {#config-profile}

作为管理员，您可以在[!DNL Adobe Admin Console]中完成这些任务，该位置是管理Adobe产品许可证和用户的中心位置。 在Admin Console中，您可以在单个位置而不是在各种单独的解决方案中创建和管理用户。 要了解有关其功能和功能的更多信息，请参阅[Admin Console概述](https://helpx.adobe.com/business/enterprise/deploy-apps-updates.html)页面。

### 访问Admin Console {#admin-console}

在使用Admin Console管理团队中的用户之前，您需要确保可以访问Admin Console并具有适当的权限。

1. 作为系统管理员，您应在载入流程中收到来自Adobe的多封电子邮件。

   找到欢迎电子邮件，其中提供了有关您已被授予访问权限的组织名称的信息。

1. 单击欢迎电子邮件中的&#x200B;**[!UICONTROL 开始使用]**&#x200B;链接以导航到Admin Console。

   如果找不到电子邮件，请直接打开浏览器访问Admin Console，网址为[https://adminconsole.adobe.com](https://adminconsole.adobe.com)。

1. 使用您的Adobe ID登录。

   成功登录后，您会看到Adobe Admin Console的&#x200B;_概述_&#x200B;页面。

1. 如果您有权访问多个组织，请确保您已登录到正确的组织。

   要更改您的组织，请单击右上角的组织名称，然后选择您需要访问的组织。

1. 从&#x200B;_[!UICONTROL 用户]_&#x200B;信息卡中选择&#x200B;**[!UICONTROL 管理员]**&#x200B;以验证您是系统管理员。

   ![Admin Console概述页面，其管理员从“用户”信息卡中选择。](./assets/admin-console-overview-administrators.png){width="800" zoomable="yes"}

1. 通过输入您的Adobe ID电子邮件、用户名、名字或姓氏进行搜索。

   * 如果您的访问权限配置正确，搜索将返回您的记录。

   * 如果&#x200B;**[!UICONTROL 管理员角色]**&#x200B;列中的值显示`System`，则表示您自己（或显示的用户）是系统管理员。

### 创建[!DNL Marketo Optimizer]产品配置文件 {#create-profile}

授予用户访问Adobe解决方案的权限时，您不一定要授予他们完全访问权限。 产品配置文件使每个解决方案都有自己的用户权限集。 使用Admin Console分配产品配置文件。

有关将产品配置文件用于用户权限的详细信息，请参阅Admin Console文档中的&#x200B;[_管理企业用户的产品配置文件_](https://helpx.adobe.com/business/enterprise/products-entitlements/manage-product-profiles/product-profiles.html){target="_blank"}。

![图标指示需要管理员访问权限才能完成此过程。](../assets/do-not-localize/icon-admin-user.svg){width="30"} 系统管理员或[!DNL Experience Platform]产品管理员可以从[https://adminconsole.adobe.com](https://adminconsole.adobe.com)中执行以下步骤。

1. 选择&#x200B;**[!UICONTROL 产品]**&#x200B;选项卡。

1. 打开要添加配置文件的[!DNL Marketo Optimizer]实例，然后单击&#x200B;**[!UICONTROL 新建配置文件]**。

1. 输入产品配置文件名称，如&#x200B;_访问_。

1. 单击&#x200B;**[!UICONTROL 下一步]**，然后单击&#x200B;**[!UICONTROL 保存]**。

### 添加用户群组 {#add-user-group}

用户组是获得一组共享权限的用户集合。 您可以在用户组中添加或删除用户。 当组内的用户发生更改时，组权限保持不变。

有关如何使用用户组管理权限的更多信息，请参阅Admin Console文档中的[管理用户组](https://helpx.adobe.com/business/enterprise/users/users-and-groups/user-groups.html){target="_blank"}。

![图标指示需要管理员访问权限才能完成此过程。](../assets/do-not-localize/icon-admin-user.svg){width="30"} 系统管理员可以从[https://adminconsole.adobe.com](https://adminconsole.adobe.com)执行以下步骤。

1. 选择&#x200B;**[!UICONTROL 用户]**&#x200B;选项卡。

1. 在左侧导航中选择&#x200B;**[!UICONTROL 用户组]**。

1. 单击右上方的&#x200B;**[!UICONTROL 新建用户组]**。

1. 输入用户组的名称，如&#x200B;_优化程序用户_，然后单击&#x200B;**[!UICONTROL 保存]**。

   ![在Admin Console中新用户组对话框，已输入组名。](./assets/admin-console-new-user-group.png){width="600" zoomable="yes"}

### 分配产品配置文件 {#assign-profile}

![图标指示需要管理员访问权限才能完成此过程。](../assets/do-not-localize/icon-admin-user.svg){width="30"} 产品管理员可以从[https://adminconsole.adobe.com](https://adminconsole.adobe.com)执行以下步骤。

1. 单击您创建的用户组。

1. 选择&#x200B;**[!UICONTROL 已分配的产品配置文件]**&#x200B;选项卡，然后单击&#x200B;**[!UICONTROL 分配配置文件]**。

1. 单击&#x200B;**+**&#x200B;并添加以下产品的每个实例：

   * [!UICONTROL Adobe Marketo Optimizer — 访问]
   * [!UICONTROL Adobe Experience Platform - AEP-Default-All-Users]
   * [!UICONTROL Adobe Experience Platform数据收集 — 默认数据收集所有访问]
   * [!UICONTROL Adobe Experience Platform — 默认的生产所有访问]

   ![Admin Console中的“已分配产品配置文件”选项卡显示已添加到用户组的配置文件。](./assets/admin-console-product-profiles.png){width="600" zoomable="yes"}

1. 单击&#x200B;**[!UICONTROL 保存]**。

### 将用户添加到新组 {#add-users}

有关用户管理的信息，请参阅Admin Console文档中的&#x200B;[_Adobe Admin Console用户_](https://helpx.adobe.com/business/enterprise/users/understand-user-management/user-management-overview.html){target="_blank"}。

![图标指示需要管理员访问权限才能完成此过程。](../assets/do-not-localize/icon-admin-user.svg){width="30"} 系统管理员或产品管理员可以从[https://adminconsole.adobe.com](https://adminconsole.adobe.com)执行以下步骤。 产品管理员只能添加其组织中已存在的用户。

1. 如果用户还不是您组织的成员，请添加每个用户：

   * 在&#x200B;_[!UICONTROL 快速链接]_&#x200B;下，单击&#x200B;**[!UICONTROL 添加用户]**。

   * 输入用户的电子邮件地址，然后单击&#x200B;**[!UICONTROL 添加为新用户]**。

     ![使用输入的电子邮件地址在Admin Console中添加新用户对话框。](./assets/admin-console-user-group-add-users.png){width="600" zoomable="yes"}

   * 输入名字和姓氏，然后单击&#x200B;**[!UICONTROL 保存]**。

1. 将每个用户添加到组：

   * 单击用户名。

   * 在用户详细信息页面中，滚动到&#x200B;**[!UICONTROL 用户组]**。

   * 单击左侧的&#x200B;_更多_ ( **...** )图标，然后选择&#x200B;**[!UICONTROL 编辑用户组]**。

   * 单击&#x200B;**[!UICONTROL 用户组]**&#x200B;下方的&#x200B;_添加_ (**+**)图标。

     ![Admin Console中的“编辑用户组”对话框，其中包含为用户选择的用户组。](./assets/admin-console-user-edit-user-groups.png){width="600" zoomable="yes"}

   * 选择您之前创建的用户组，然后单击&#x200B;**[!UICONTROL 应用]**。

   * 单击&#x200B;**[!UICONTROL 保存]**&#x200B;以查看用户更改。

## 分配产品权限 {#assign-product-permissions}

权限是单一的权利，可用于定义分配给产品配置文件的授权。 每个权限都分组在某个功能（如人员历程或内容）下，表示[!DNL Marketo Optimizer]中的功能。

在Adobe Experience Platform的&#x200B;_权限_&#x200B;区域，管理员可以定义用户角色和访问策略，以管理产品应用程序内功能和对象的访问权限。 在此应用程序中，您可以创建和管理角色，并为这些角色分配所需的资源权限。 权限还允许您管理与特定角色关联的沙盒和用户。

有关Experience Platform中角色权限的更多信息，请参阅Experience Platform文档中的[管理角色的权限](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/abac/permissions-ui/permissions){target="_blank"}。

1. 转到[experience.adobe.com](https://experience.adobe.com/)。

1. 在&#x200B;_[!UICONTROL 快速访问]_&#x200B;面板中，选择&#x200B;**[!UICONTROL 权限]**。

   >[!NOTE]
   >
   >如果您没有看到&#x200B;_[!UICONTROL 权限]_，您可能需要单击&#x200B;**[!UICONTROL 查看全部]**&#x200B;并从可用应用程序中选择它。

   从Experience Platform的“快速访问”面板中选择的![权限应用程序。](./assets/aep-permissions.png){width="700" zoomable="yes"}

### 权限资源 {#permissions}

有关控制对[!DNL Marketo Optimizer]功能访问权限的完整权限列表，包括说明和对每种类型用户推荐的权限，请参阅[产品权限](./permissions-reference.md)页面。

>[!IMPORTANT]
>
>[!DNL Marketo Optimizer]访问要求您启用使用以下命名约定配置的特定沙盒： `Mktoaep` + [!DNL Marketo Engage]订阅前缀。 例如，如果链接的[!DNL Marketo Engage]订阅前缀为&#x200B;_AcmeAssoc_，则访问[!DNL Marketo Optimizer]所需的沙盒为&#x200B;_MktoaepAcmeAssoc_。 将此沙盒添加到每个角色。

>[!NOTE]
>
>您必须是系统管理员才能在Experience Platform中看到&#x200B;_[!UICONTROL 权限]_&#x200B;磁贴。

### 编辑角色权限 {#edit-role-permissions}

对于内置或自定义角色，您可以随时决定添加或删除权限。 如果修改默认或自定义角色，则会影响分配给该角色的每个用户。

>[!IMPORTANT]
>
>[!DNL Marketo Optimizer]访问要求您启用使用以下命名约定配置的特定沙盒： `Mktoaep` + [!DNL Marketo Engage]订阅前缀。 例如，如果链接的[!DNL Marketo Engage]订阅前缀为&#x200B;_AcmeAssoc_，则访问[!DNL Marketo Optimizer]所需的沙盒为&#x200B;_MktoaepAcmeAssoc_。

>[!NOTE]
>
>有权访问Experience Platform权限的产品管理员可以执行这些步骤。

更改角色&#x200B;:_的权限(_T)

1. 在左侧导航中选择&#x200B;**[!UICONTROL 角色]**。

1. 单击&#x200B;**_优化程序用户_**&#x200B;角色名称。

1. 在详细信息页面中，单击右上方的&#x200B;**[!UICONTROL 编辑]**。

   在“Experience Platform权限”中，![角色详细信息页面选定了“编辑”。](./assets/aep-permissions-role-prime-edit.png){width="800" zoomable="yes"}

   在角色编辑器中，_[!UICONTROL 资源]_&#x200B;菜单显示应用于Experience Cloud - Platform支持的应用程序的资源列表。

1. 选择为[!DNL Marketo Optimizer]访问权限(`Mktoaep<Marketo subscription prefix>`)配置的沙盒。

   ![角色编辑器中的沙盒选择列表，显示可供添加的Marketo Optimizer沙盒。](./assets/aep-permissions-optimizer-sandbox.png){width="500" zoomable="yes"}

1. 单击每个功能资源的&#x200B;_添加_&#x200B;图标(**+**)。

   Experience Platform中的![角色编辑器显示添加的B2B历程资源以及列出的权限。](./assets/aep-permissions-b2b-list.png){width="700" zoomable="yes"}

1. 为每个资源添加特定权限，或选择&#x200B;**[!UICONTROL 全部添加]**。

1. 单击&#x200B;**[!UICONTROL 保存]**。

   <!-- ![Experience Platform - B2B Journeys permissions saved for Channel Manager role](assets/aep-permissions-role-edit-b2b-journeys-done.png){width="700" zoomable="yes"} -->

1. 单击&#x200B;**[!UICONTROL 关闭]**&#x200B;以返回详细信息页面。

### 将用户添加到角色 {#add-users-to-a-role}

![图标指示需要管理员访问权限才能完成此过程。](../assets/do-not-localize/icon-admin-user.svg){width="30"} 系统管理员或Experience Platform管理员可以执行以下步骤。

1. 打开角色详细信息并选择&#x200B;**[!UICONTROL 用户]**&#x200B;选项卡。

   此选项卡显示分配给该角色的所有用户的列表。

1. 单击&#x200B;**[!UICONTROL 添加用户]**。

   在Experience Platform的“角色详细信息”页面中，![已选择“添加用户”的“用户”选项卡。](./assets/aep-permissions-role-prime-add-users.png){width="800" zoomable="yes"}

1. 在&#x200B;_[!UICONTROL 添加用户]_&#x200B;对话框中，找到并选择要添加到该角色的用户。

   * 您可以使用搜索工具来筛选用户列表。

   * 选中每个用户的复选框。

   ![Experience Platform中的“添加用户”对话框，已选中要添加到角色的用户复选框。](assets/aep-permissions-role-add-users-dialog.png){width="600" zoomable="yes"}

1. 选择您要添加的所有用户后，单击&#x200B;**[!UICONTROL 保存]**。

### 将用户组添加到角色 {#add-user-groups-to-a-role}

有关用户管理的信息，请参阅Admin Console文档中的&#x200B;[_Adobe Admin Console用户_](https://helpx.adobe.com/business/enterprise/users/understand-user-management/user-management-overview.html){target="_blank"}。

![图标指示需要管理员访问权限才能完成此过程。](../assets/do-not-localize/icon-admin-user.svg){width="30"} 系统管理员或Experience Platform管理员可以执行以下步骤。

1. 打开角色详细信息并选择&#x200B;**[!UICONTROL 用户组]**&#x200B;选项卡。

   此选项卡显示分配给该角色的所有用户组的列表。

1. 单击&#x200B;**[!UICONTROL 添加群组]**。

   ![在Experience Platform的“角色详细信息”页面中，选择了“添加组”的“用户组”选项卡。](./assets/aep-permissions-role-prime-add-groups.png){width="800" zoomable="yes"}

1. 在&#x200B;_[!UICONTROL 添加组]_&#x200B;对话框中，找到并选择要添加到该角色的组。

   * 您可以使用搜索工具筛选用户组列表。

   * 选中每个用户组的复选框。

   ![Experience Platform中的“添加组”对话框，已选中要添加到角色的用户组复选框。](assets/aep-permissions-role-add-groups-dialog.png){width="600" zoomable="yes"}

1. 选择您要添加的所有组后，单击&#x200B;**[!UICONTROL 保存]**。

### 创建自定义角色 {#create-a-custom-role}

![图标指示需要管理员访问权限才能完成此过程。](../assets/do-not-localize/icon-admin-user.svg){width="30"} 系统管理员或Experience Platform管理员可以执行以下步骤。

1. 在左侧导航中选择&#x200B;**[!UICONTROL 角色]**，然后选择&#x200B;**[!UICONTROL 创建角色]**。

1. 在&#x200B;_[!UICONTROL 创建新角色]_&#x200B;对话框中，输入角色的名称和描述（可选），例如&#x200B;_B2B营销人员_。

1. 单击&#x200B;**[!UICONTROL 确认]**。

1. 选择为[!DNL Marketo Optimizer]访问权限(`Mktoaep<Marketo subscription prefix>`)配置的沙盒。

   ![角色编辑器中已选择Marketo Optimizer沙盒的沙盒选择列表。](./assets/aep-permissions-optimizer-sandbox.png){width="500" zoomable="yes"}

1. 添加产品权限：

   要确定您希望角色具有哪些产品功能，请参阅[产品权限](./permissions-reference.md)列表。

   在左侧的&#x200B;_[!UICONTROL 资源]_&#x200B;列表中，找到B2B项目并单击&#x200B;_添加_ (**+**)图标以添加要为该角色启用的每个属性。

   您可以在搜索工具中输入&#x200B;_B2B_，以筛选适用于[!DNL Marketo Optimizer]的许多与B2B相关的产品权限的列表。

   带有在搜索字段中过滤的B2B资源的Experience Platform中的![角色编辑器。](./assets/aep-permissions-b2b-list.png){width="700" zoomable="yes"}

1. 单击右上方的&#x200B;**[!UICONTROL 保存]**。

1. 转到角色详细信息并选择&#x200B;**[!UICONTROL 用户组]**&#x200B;选项卡。

1. 单击&#x200B;**[!UICONTROL 添加群组]**。

1. 选中您之前在Admin Console中创建的用户组旁边的复选框。

1. 单击&#x200B;**[!UICONTROL 保存]**。

您的自定义角色已配置，并且已分配组中的用户现在可以访问您选择的[!DNL Marketo Optimizer]权能。

### 为建议的用户类型创建用户组和角色 {#create-suggested-roles}

使用以下过程设置&#x200B;_管理员_、_所有访问用户_&#x200B;和&#x200B;_只读访问用户_ [建议的用户类型](./permissions-reference.md#suggested-user-types)。 对于每个用户类型，您需要在Admin Console中创建用户组，在Experience Platform中创建角色，然后将该组添加到该角色。 [_产品权限_](./permissions-reference.md)&#x200B;中列出了每种用户类型的建议权限。

#### 创建管理员用户组和角色 {#create-admin-group}

![图标指示需要管理员访问权限才能完成此过程。](../assets/do-not-localize/icon-admin-user.svg){width="30"} 系统管理员可以执行以下步骤。

1. 在Admin Console中，[添加名为&#x200B;_Marketo Optimizer管理员组_&#x200B;的用户组](#add-user-group)，并将[产品配置文件](#assign-profile)分配给该用户组。

1. 将设置和管理[!DNL Marketo Optimizer]的用户添加到该组。

1. 让用户成为产品管理员，以便他们可以管理用户和组。

1. 在[!UICONTROL Experience Platform] _[!UICONTROL 权限]_&#x200B;中，选择&#x200B;**[!UICONTROL 角色]** > **[!UICONTROL 创建角色]**

1. 输入名称，如&#x200B;_Marketo Optimizer管理员_，然后单击&#x200B;**[!UICONTROL 确认]**。

1. 选择为[!DNL Marketo Optimizer]访问权限(`Mktoaep<Marketo subscription prefix>`)配置的沙盒。

   >[!IMPORTANT]
   >
   >此步骤对于正确访问至关重要。

1. 对于以下每个类别，单击&#x200B;_添加_ (**+**)图标并选择&#x200B;**[!UICONTROL 全部添加]**：

   * _[!UICONTROL B2B管理配置]_
   * _[!UICONTROL B2B Assets]_
   * _[!UICONTROL B2B渠道配置]_
   * _[!UICONTROL B2B对话体验]_
   * _[!UICONTROL B2B目标]_
   * _[!UICONTROL B2B文件夹令牌]_
   * _[!UICONTROL B2B文件夹]_
   * _[!UICONTROL B2B意图配置]_
   * _[!UICONTROL B2B历程]_
   * _[!UICONTROL B2B Labs]_
   * _[!UICONTROL B2B组织规则]_
   * _[!UICONTROL B2B人员列表]_
   * _[!UICONTROL B2B项目令牌]_
   * _[!UICONTROL B2B程序类型]_
   * _[!UICONTROL B2B程序]_
   * _[!UICONTROL B2B报告]_
   * _[!UICONTROL 仪表板]_
   * _[!UICONTROL 目标]_
   * _[!UICONTROL 数据治理]_
   * _[!UICONTROL 数据获取]_
   * _[!UICONTROL 配置文件管理]_

   >[!TIP]
   >
   >仅对管理员角色使用&#x200B;**[!UICONTROL 全部添加]**。 发布新功能后，为其准备的权限将自动应用于管理员角色，因此您无需编辑角色。 对于其他用户类型，请在&#x200B;[_产品权限_](./permissions-reference.md)&#x200B;中仅选择该类型推荐的权限。

1. 单击&#x200B;**[!UICONTROL 保存]**。

1. 在角色详细信息中，选择&#x200B;**[!UICONTROL 用户组]**&#x200B;选项卡，单击&#x200B;**[!UICONTROL 添加组]**，选择&#x200B;_Marketo Optimizer管理员组_，然后单击&#x200B;**[!UICONTROL 保存]**。

#### 创建完全访问用户群组和角色 {#create-all-access-group}

![图标指示需要管理员访问权限才能完成此过程。](../assets/do-not-localize/icon-admin-user.svg){width="30"} 系统管理员可以执行以下步骤。

1. 在Admin Console中，[添加名为&#x200B;_Marketo Optimizer用户组_&#x200B;的用户组](#add-user-group)，[为其分配产品配置文件](#assign-profile)，并[将用户添加到该组](#add-users)。

1. 在Experience Platform权限中，[创建一个名为&#x200B;_Marketo Optimizer All Access User_&#x200B;的自定义角色](#create-a-custom-role)。

1. 选择为[!DNL Marketo Optimizer]访问权限(`Mktoaep<Marketo subscription prefix>`)配置的沙盒。

1. 对于[产品权限](./permissions-reference.md)中的每个类别，请单击&#x200B;_添加_ (**+**)图标，然后仅选择建议用于所有访问用户的权限。

   所有Access用户都可以每天在每种功能中工作，但他们不会获得管理员、渠道或设置权限。

1. 单击&#x200B;**[!UICONTROL 保存]**。

1. 在角色详细信息中，选择&#x200B;**[!UICONTROL 用户组]**&#x200B;选项卡，单击&#x200B;**[!UICONTROL 添加组]**，选择&#x200B;_Marketo Optimizer用户组_，然后单击&#x200B;**[!UICONTROL 保存]**。

#### 创建只读访问用户组和角色 {#create-read-only-group}

![图标指示需要管理员访问权限才能完成此过程。](../assets/do-not-localize/icon-admin-user.svg){width="30"} 系统管理员可以执行以下步骤。

1. 在Admin Console中，[添加名为&#x200B;_Marketo Optimizer只读用户组_&#x200B;的用户组](#add-user-group)，[为其分配产品配置文件](#assign-profile)，并[将用户](#add-users)添加到该组。

1. 在Experience Platform权限中，[创建一个名为&#x200B;_Marketo Optimizer只读访问用户_&#x200B;的自定义角色](#create-a-custom-role)。

1. 选择为[!DNL Marketo Optimizer]访问权限(`Mktoaep<Marketo subscription prefix>`)配置的沙盒。

1. 对于[产品权限](./permissions-reference.md)中的每个类别，请单击&#x200B;_添加_ (**+**)图标，然后仅选择为只读访问用户推荐的权限。

   只读访问用户只能查看功能。

1. 单击&#x200B;**[!UICONTROL 保存]**。

1. 在角色详细信息中，选择&#x200B;**[!UICONTROL 用户组]**&#x200B;选项卡，单击&#x200B;**[!UICONTROL 添加组]**，选择&#x200B;_Marketo Optimizer只读用户组_，然后单击&#x200B;**[!UICONTROL 保存]**。
