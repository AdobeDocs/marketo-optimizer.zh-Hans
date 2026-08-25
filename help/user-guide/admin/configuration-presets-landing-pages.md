---
title: 登陆页面配置
description: 占位符
source-git-commit: c7d3546d075f5a58923134231217b2fd10fe4aca
workflow-type: tm+mt
source-wordcount: '971'
ht-degree: 21%

---


# 登陆页面配置

管理员应确保为创作和发布这些页面的营销人员配置了登陆页面配置。 有两种配置类型可用于精心编制反映品牌和有效跟踪参与情况的登陆页面：

* **_子域_** — 设置登陆页面的托管位置。 管理登陆页面子域以委派、配置或取消委派域设置。
* **_预设_** — 定义可重用的配置（包括子域和其他渠道设置），以便营销人员能够一致地创建和管理登陆页面。

## 子域 {#lp-subdomains}

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_admin_subdomain_lp_header"
>title="委派登陆页面子域"
>abstract="设置用于登陆页面的子域。 可使用已委派给 Adobe 的子域或配置另一子域。"

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_admin_subdomain_lp"
>title="委派登陆页面子域"
>abstract="在创建登陆页面预设之前，必须先配置登陆页面子域。 可使用已委派给 Adobe 的子域或配置新的子域。"

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_admin_config_lp_subdomain"
>title="创建登陆页面预设"
>abstract="要创建登陆页面预设，请确保您已至少配置一个登陆页面子域，以便从“子域名称”列表中进行选择。"

若要查看配置的登陆页面子域，请转到&#x200B;**[!UICONTROL 管理]** > **[!UICONTROL 渠道]**。 在导航窗格中的&#x200B;_[!UICONTROL 登陆页面]_&#x200B;下，选择&#x200B;**[!UICONTROL 登陆页面子域]**。

<!-- ![Channel configurations - landing page subdomains](./assets/config-channels-landing-pages-subdomains.png){width="800" zoomable="yes"} -->

**状态**&#x200B;列提供有关子域创建和委派过程的信息：

* _[!UICONTROL 草稿]_：将子域委派另存为草稿。 单击子域名可继续创建过程。
* _[!UICONTROL 正在处理]_：子域正在通过几个配置检查进行中，在使用它之前需要这些配置检查。
* _[!UICONTROL 成功]_：已成功通过检查的子域，该子域可用于传递消息。
* _[!UICONTROL 失败]_：提交子域委派后，一个或多个检查失败。

>[!NOTE]
>
>在[创建登陆页面预设](#lp-presets)之前，必须设置用于登陆页面的子域。 您可以使用已委派给Adobe的子域，也可以配置其他子域。

登陆页面子域配置对所有环境&#x200B;**都是**&#x200B;通用的。 因此：

* 要访问和编辑登陆页面子域，您必须对生产沙盒具有&#x200B;**[!UICONTROL 管理登陆页面子域]**&#x200B;权限。

* 对登陆页面子域的任何修改也会影响生产沙箱。

<!-- 
### Use an existing subdomain {#lp-existing-subdomain}

To use a subdomain that is already delegated to Adobe:

1. Click **[!UICONTROL Set up landing page subdomain]**.

    ![](assets/lp_set-up-subdomain.png)

1. For _[!UICONTROL Configuration type]_, choose **[!UICONTROL Use delegated domain]**.

    ![](assets/lp_use-delegated-subdomain.png)

1. Enter the prefix that you want to display in the landing page URL.

    Only alpha-numeric characters and hyphens are allowed.

    >[!CAUTION]
    >
    >Do not use `cdn` or `data` prefixes as these are reserved for internal use. You should also avoid other restricted or reserved prefixes, such as `dmarc` or `spf`.

1. Select a delegated subdomain from the list.

    You cannot select a subdomain that is already used as landing page subdomain.
    
    ![](assets/lp_prefix-and-subdomain.png)

    You cannot use multiple delegated subdomains of the same parent domain. For example, if 'marketing1.yourcompany.com' is already delegated to Adobe for your landing pages, you cannot use 'marketing2.yourcompany.com'. However, when multi-level subdomains are supported for landing pages, you may proceed using a subdomain of 'marketing1.yourcompany.com' (such as 'email.marketing1.yourcompany.com'), or a different parent domain.

    >[!CAUTION]
    >
    >If you select a domain that was delegated to Adobe using the [CNAME method](../configuration/delegate-subdomain.md#cname-subdomain-setup), you must create the DNS record on your hosting platform. To generate the DNS record, the process is the same as when you configure a new landing page subdomain.

1. Click **[!UICONTROL Submit]**.

   The subdomain is displayed in the list with the _[!UICONTROL Processing]_ status. For more on subdomains' statuses, see TBD.

    ![](assets/lp_subdomain-processing.png)

   >[!IMPORTANT]
   >
   >The subdomain is not ready for use until Adobe performs the required checks, which can take **_up to 4 hours_**.

   When the checks are successful, the subdomain is listed with the _[!UICONTROL Success]_ status and it is ready to use for creating landing page presets.
-->

### 配置新的子域 {#lp-new-subdomain}

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_admin_lp_subdomain_dns"
>title="生成匹配的 DNS 记录"
>abstract="要配置新的登陆页面子域，您需要复制 Journey Optimizer B2B 界面中显示的 Adobe 名称服务器信息，将其粘贴到您的域托管解决方案中，以生成匹配的 DNS 记录。 检查成功后，子域就可以用来创建登陆页面预设了。"

1. 单击&#x200B;**[!UICONTROL 设置登陆页子域]**。

1. 对于&#x200B;_[!UICONTROL 配置类型]_，请选择&#x200B;**[!UICONTROL 添加您自己的域]**。

1. 指定要委派的子域。

   >[!IMPORTANT]
   >
   >* 您无法使用现有的登陆页面子域。
   >
   >* 子域中不允许使用大写字母。

   <!-- ![Landing page subdomain set up](./assets/config-channels-landing-pages-subdomain-setup.png){width="500" zoomable="yes"} -->

   不允许将无效子域委派给Adobe。 确保输入贵组织拥有的有效子域，如marketing.yourcompany.com。

   对于登陆页面，支持多级子域。 例如，您可以使用`email.marketing.yourcompany.com`。

1. 复制显示的记录或下载CSV文件，然后导航到您的域托管解决方案以生成匹配的DNS记录。

   将显示要放置在DNS服务器上的记录。

1. 确保将DNS记录生成到域托管解决方案中。

   如果一切配置正确，请选中确认复选框，然后单击&#x200B;**[!UICONTROL 提交]**。

   <!-- ![Landing page subdomain set up with DNS records](./assets/config-channels-landing-pages-subdomain-setup-dns.png){width="500" zoomable="yes"} -->

   配置新登陆页面子域时，它始终指向CNAME记录。

   提交子域委派后，子域将显示在状态为&#x200B;_[!UICONTROL 正在处理]_&#x200B;的列表中。

   >[!IMPORTANT]
   >
   >在Adobe执行所需的检查之前，子域无法准备使用，检查可能需要&#x200B;**_长达4小时_**。

   检查成功后，子域将以&#x200B;_[!UICONTROL Success]_&#x200B;状态列出，并且可用于创建登陆页面预设。

   如果未在托管解决方案上创建验证记录，则子域被标记为&#x200B;_[!UICONTROL 失败]_。

### 取消委派子域 {#undelegate-subdomain}

1. 在[!DNL Journey Optimizer]中，取消发布与子域关联的所有登陆页面。

1. 如果登陆页面子域指向CNAME记录，请从托管解决方案中删除CNAME记录（不删除原始电子邮件子域，如有）。

   <!--
    >[!NOTE]
    >
    >A landing page subdomain can point to a CNAME record because it was either an [existing subdomain](#lp-use-existing-subdomain) delegated to Adobe using the [CNAME method](../configuration/delegate-subdomain.md#cname-subdomain-setup), or a [new landing page subdomain](#lp-configure-new-subdomain) that you configured. 
    -->

1. 请联系您的Adobe代表，并提供要取消委派的子域。

Adobe处理您的请求后，子域清单页面不再显示未委派域。

<!-- 
old marketo way for Prime?

A landing page subdomain should help to identify the content type, product name, or campaign, and reinforce the page authenticity. Before you configure the subdomains, define one or more CNAMEs to use for your landing pages. For example:

* **product**.[CompanyDomain].com
* **go**.[CompanyDomain].com
* **signup**.[CompanyDomain].com

In these examples, the first part (in bold) is the `LandingPageCNAME`.

Add a new subdomain for each unique brand URL that you want to host on Adobe Journey Optimizer B2B Edition. You can add a maximum number of 50 subdomains.

>[!IMPORTANT]
>
>Delegating an invalid subdomain to Adobe is not allowed. Make sure you enter a valid subdomain that your organization owns, such as _marketing.yourcompany.com_.

To review your subdomains and add new ones, go to **[!UICONTROL Administration]** > **[!UICONTROL Channels]**. Under _[!UICONTROL Landing Pages]_ in the navigation panel, select **[!UICONTROL Subdomains]**.

![Landing page subdomains](./assets/config-landing-pages-settings.png){width="800" zoomable="yes"}

_To add a landing page subdomain:_

1. Click **[!UICONTROL Add subdomain]** at the top right.

1. In the _[!UICONTROL Subdomain details]_, enter the subdomain information:

   * **[!UICONTROL Subdomain]** - The subdomain URL to use, such as `marketing.yourcompany.com`
   * **[!UICONTROL Default page]** - The URL for the default subdomain page, such as `marketing.yourcompany.com/products`
   * **[!UICONTROL Fallback page]** - The URL for the fallback page to be used if a landing page on the subdomain is not active, such as `marketing.yourcompany.com/expired`

   ![Add landing page subdomain](./assets/config-landing-pages-add-subdomain.png){width="700" zoomable="yes"}

1. Click **[!UICONTROL Save]**.

-->

## 预设 {#lp-presets}

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_admin_config_lp_subdomain_header"
>title="创建登陆页面预设"
>abstract="为了生成登陆页面并通过 Journey Optimizer B2B Edition 使用它，您必须创建一个登陆页面预设，在其中包含要使用的子域。"

营销人员在创建登陆页面时，必须选择登陆页面预设，才能构建登陆页面并通过[!DNL Journey Optimizer B2B Edition]利用它。 预设包括用于登陆页面的子域。

在配置预设之前，请确保至少有一个已配置的登陆页面子域具有&#x200B;_[!UICONTROL 成功]_&#x200B;状态。

若要查看已配置的登陆页面预设，请转到&#x200B;**[!UICONTROL 管理]** > **[!UICONTROL 渠道]**。 在导航窗格中的&#x200B;_[!UICONTROL 登陆页面]_&#x200B;下，选择&#x200B;**[!UICONTROL 登陆页面预设]**。

<!-- ![Channel configurations - landing page presets](./assets/config-channels-landing-pages-presets.png){width="800" zoomable="yes"} -->

单击任何预设名称可访问登陆页面预设详细信息。

### 创建登陆页面预设 {#lp-create-preset}

1. 单击&#x200B;**[!UICONTROL 创建登陆页面预设]**。

1. 输入预设的名称和描述。

   名称必须以字母(A-Z)开头，并且只包含字母数字字符、下划线`_`、点`.`和连字符`-`字符。

1. 选择登陆页面子域。

   <!-- ![Landing page preset with name, description, and subdomain](./assets/config-channels-landing-pages-preset-create.png){width="500" zoomable="yes"} -->

   >[!NOTE]
   >
   >要能够选择子域，请确保您之前已配置至少一个登陆页面子域。

   此时将显示与所选子域对应的设置。

1. 通过选中&#x200B;**[!UICONTROL 与登陆页面子域]**&#x200B;相同选项，可以为&#x200B;**[!UICONTROL 跟踪URL]**&#x200B;选择登陆页面子域。

   <!-- [Learn more about tracking](../email/message-tracking.md) -->

   <!-- ![Landing page preset with subdomain settings](./assets/config-channels-landing-pages-preset-subdomain-settings.png){width="500" zoomable="yes"} -->

   例如，如果登陆页面URL为`pages.mail.luma.com`，而跟踪URL为`data.mail.luma.com`，则可以选择`pages.mail.luma.com`用作跟踪子域。

   <!-- 
    >[!CAUTION]
    >
    >The selected landing page subdomain is used to specify the **[!UICONTROL Tracking URL]**and **[!UICONTROL Image Delivery URL]** if that subdomain was created using an [existing subdomain](#use-an-existing-subdomain).
    >
    >If the subdomain was created using the [Add your own domain](#configure-a-new-subdomain) option, the primary subdomain (such as the first delegated subdomain) is used instead. We don't have the existing option right now.
    -->

1. 单击&#x200B;**[!UICONTROL 提交]**&#x200B;以确认创建登陆页面预设。

   <!--You can also save the preset as draft and resume its configuration later on.-->

   创建登陆页面预设后，该预设将显示在状态为&#x200B;_[!UICONTROL 活动]_&#x200B;的列表中，并准备好用于创建登陆页面。