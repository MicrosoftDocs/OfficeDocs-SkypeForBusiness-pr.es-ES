---
title: Integración entre Skype para profesionales Online y Exchange server
ms.reviewer: cbland
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/2/2019
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ffe4c3ba-7bab-49f1-b229-5142a87f94e6
description: Configuración de OAuth autenticación entre Exchange local y Skype para profesionales en línea permite la Skype para características empresariales y de integración de Exchange que se describen en compatibilidad con la característica.
ms.openlocfilehash: c6a3819c9ec6ae0c207307a23f67bf04e4f07ac0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33894242"
---
# <a name="configure-integration-between-skype-for-business-online-or-microsoft-teams-and-exchange-server"></a><span data-ttu-id="03dce-103">Configurar la integración entre Skype para la empresa en línea o los equipos de Microsoft y Exchange Server</span><span class="sxs-lookup"><span data-stu-id="03dce-103">Configure Integration between Skype for Business Online or Microsoft Teams and Exchange Server</span></span> 

<span data-ttu-id="03dce-104">Configuración de la integración entre Exchange server y Skype para profesionales en línea permite la Skype para características empresariales y de integración de Exchange que se describen en [función de soporte técnico](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).</span><span class="sxs-lookup"><span data-stu-id="03dce-104">Configuring integration between Exchange server and Skype for Business Online enables the Skype for Business and Exchange Integration features described in [Feature support](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).</span></span>

<span data-ttu-id="03dce-105">En este tema se aplica a la integración con Exchange Server 2013 a través de 2019.</span><span class="sxs-lookup"><span data-stu-id="03dce-105">This topic applies to integration with Exchange Server 2013 through 2019.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="03dce-106">¿Qué necesita saber antes de empezar?</span><span class="sxs-lookup"><span data-stu-id="03dce-106">What do you need to know before you begin?</span></span>

- <span data-ttu-id="03dce-107">Tiempo estimado para finalizar esta tarea: 15 minutos</span><span class="sxs-lookup"><span data-stu-id="03dce-107">Estimated time to complete this task: 15 minutes</span></span>

-  <span data-ttu-id="03dce-108">Necesita tener permisos asignados antes de poder realizar los siguientes procedimientos.</span><span class="sxs-lookup"><span data-stu-id="03dce-108">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="03dce-109">Para ver qué permisos necesita, vea el tema de [permisos de infraestructura de Exchange y el Shell](https://go.microsoft.com/fwlink/p/?LinkId=746511) .</span><span class="sxs-lookup"><span data-stu-id="03dce-109">To see what permissions you need, see the [Exchange and Shell infrastructure permissions](https://go.microsoft.com/fwlink/p/?LinkId=746511) topic.</span></span>

- <span data-ttu-id="03dce-110">Para obtener información sobre los métodos abreviados de teclado que se pueden aplicar a los procedimientos descritos en este tema, vea [métodos abreviados de teclado en el centro de administración de Exchange]( https://go.microsoft.com/fwlink/p/?LinkId=746512).</span><span class="sxs-lookup"><span data-stu-id="03dce-110">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts in the Exchange admin center]( https://go.microsoft.com/fwlink/p/?LinkId=746512).</span></span>

## <a name="configure-integration-between-exchange-server-and-o365"></a><span data-ttu-id="03dce-111">Configurar la integración entre Exchange Server y Office 365</span><span class="sxs-lookup"><span data-stu-id="03dce-111">Configure integration between Exchange Server and O365</span></span>

### <a name="step-1-configure-oauth-authentication-between-exchange-server-and-o365"></a><span data-ttu-id="03dce-112">Paso 1: Configurar la autenticación de OAuth entre Exchange Server y Office 365</span><span class="sxs-lookup"><span data-stu-id="03dce-112">Step 1: Configure OAuth authentication between Exchange Server and O365</span></span>

<span data-ttu-id="03dce-113">Realice los pasos en el siguiente artículo:</span><span class="sxs-lookup"><span data-stu-id="03dce-113">Perform the steps in the following article:</span></span>

[<span data-ttu-id="03dce-114">Configurar la autenticación de OAuth entre organizaciones de Exchange y Exchange Online</span><span class="sxs-lookup"><span data-stu-id="03dce-114">Configure OAuth authentication between Exchange and Exchange Online organizations</span></span>](https://docs.microsoft.com/en-us/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

### <a name="step-2-create-a-new-mail-user-account-for-the-skype-for-business-online-or-teams-partner-application"></a><span data-ttu-id="03dce-115">Paso 2: Crear una nueva cuenta de usuario de correo para la Skype para profesionales en línea o de la aplicación de socio de equipos</span><span class="sxs-lookup"><span data-stu-id="03dce-115">Step 2: Create a new Mail User account for the Skype for Business Online or Teams Partner Application</span></span>

<span data-ttu-id="03dce-116">En este paso se realiza en el servidor de Exchange.</span><span class="sxs-lookup"><span data-stu-id="03dce-116">This step is done on the Exchange server.</span></span> <span data-ttu-id="03dce-117">Creará un usuario de correo y le asignará los derechos de roles de administración apropiados.</span><span class="sxs-lookup"><span data-stu-id="03dce-117">It will create a mail user and assign it the appropriate management role rights.</span></span> <span data-ttu-id="03dce-118">Esta cuenta se usará en el siguiente paso.</span><span class="sxs-lookup"><span data-stu-id="03dce-118">This account will then be used in the next step.</span></span>

<span data-ttu-id="03dce-119">Especifique un dominio comprobado para la organización de Exchange.</span><span class="sxs-lookup"><span data-stu-id="03dce-119">Specify a verified domain for your Exchange organization.</span></span> <span data-ttu-id="03dce-120">Este dominio debe ser el mismo dominio que se utiliza como el dominio SMTP principal que se utiliza para las cuentas de Exchange local.</span><span class="sxs-lookup"><span data-stu-id="03dce-120">This domain should be the same domain used as the primary SMTP domain used for the on-premises Exchange accounts.</span></span> <span data-ttu-id="03dce-121">Este dominio se conoce como \<su dominio comprobado\> en el siguiente procedimiento.</span><span class="sxs-lookup"><span data-stu-id="03dce-121">This domain is referred as \<your Verified Domain\> in the following procedure.</span></span> <span data-ttu-id="03dce-122">Además, el \<DomainControllerFQDN\> debe ser el FQDN de un controlador de dominio.</span><span class="sxs-lookup"><span data-stu-id="03dce-122">Also, the \<DomainControllerFQDN\> should be the FQDN of a domain controller.</span></span>

``` Powershell
$user = New-MailUser -Name O365-ApplicationAccount -ExternalEmailAddress O365-ApplicationAccount@<your Verified Domain> -DomainController <DomainControllerFQDN>
```

<span data-ttu-id="03dce-123">Este comando ocultará al nuevo usuario de correo de las listas de direcciones.</span><span class="sxs-lookup"><span data-stu-id="03dce-123">This command will hide the new mail user from address lists.</span></span>

``` Powershell
Set-MailUser -Identity $user.Identity -HiddenFromAddressListsEnabled $True -DomainController <DomainControllerFQDN>
```

<span data-ttu-id="03dce-124">Los dos comandos siguientes asignarán los roles de administración UserApplication y ArchiveApplication a esta nueva cuenta.</span><span class="sxs-lookup"><span data-stu-id="03dce-124">These next two commands will assign the UserApplication and ArchiveApplication management role to this new account.</span></span>

``` Powershell
New-ManagementRoleAssignment -Role UserApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

``` Powershell
New-ManagementRoleAssignment -Role ArchiveApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

### <a name="step-3-create-and-enable-a-partner-application-for-skype-for-business-online-or-teams"></a><span data-ttu-id="03dce-125">Paso 3: Crear y habilitar una aplicación de socio de Skype para profesionales en línea o equipos</span><span class="sxs-lookup"><span data-stu-id="03dce-125">Step 3: Create and enable a Partner Application for Skype for Business Online or Teams</span></span>

<span data-ttu-id="03dce-126">Cree una aplicación de socio y use la cuenta que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="03dce-126">Create a new partner application and will use the account you just created.</span></span> <span data-ttu-id="03dce-127">Ejecute el siguiente comando en Exchange PowerShell en sus instalaciones de organización de Exchange.</span><span class="sxs-lookup"><span data-stu-id="03dce-127">Run the following command in the Exchange PowerShell in your on-premises Exchange organization.</span></span>

``` Powershell
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="verify-your-success"></a><span data-ttu-id="03dce-128">Comprobar que realizó todo correctamente</span><span class="sxs-lookup"><span data-stu-id="03dce-128">Verify your success</span></span>

<span data-ttu-id="03dce-129">Compruebe que la configuración es correcta mediante la comprobación de que algunas de las características funcionan correctamente.</span><span class="sxs-lookup"><span data-stu-id="03dce-129">Verify that the configuration is correct by verifying some of the features are working successfully.</span></span> 

1. <span data-ttu-id="03dce-130">Confirmar la delegación de calendario de Outlook funciona comprendido entre dos usuarios de los equipos con Exchange Server 2016 o buzones 2019.</span><span class="sxs-lookup"><span data-stu-id="03dce-130">Confirm Outlook Calendar delegation works betweeen two Teams users with Exchange Server 2016 or 2019 mailboxes.</span></span>

2. <span data-ttu-id="03dce-131">Confirme el historial de conversaciones para clientes móviles está visible en la carpeta Historial de conversaciones de Outlook.</span><span class="sxs-lookup"><span data-stu-id="03dce-131">Confirm conversation history for mobile clients is visible in the Outlook Conversation History folder.</span></span>

<span data-ttu-id="03dce-132">Como alternativa, examine el tráfico.</span><span class="sxs-lookup"><span data-stu-id="03dce-132">Alternately, look at your traffic.</span></span> <span data-ttu-id="03dce-133">El tráfico en un protocolo de enlace de OAuth es realmente distintivo (y no el aspecto de la autenticación básica), especialmente alrededor de dominios, donde podrá comenzar a ver el tráfico de emisor que tiene este aspecto: 00000004-0000-0ff1-ce00-000000000000 @ (a veces con una / antes de el signo @), en los tokens que se pasan.</span><span class="sxs-lookup"><span data-stu-id="03dce-133">The traffic in an OAuth handshake is really distinctive (and doesn't look like Basic authentication), particularly around realms, where you’ll begin to see issuer traffic that looks like this: 00000004-0000-0ff1-ce00-000000000000@ (sometimes with a / before the @ sign), in the tokens that are being passed.</span></span> <span data-ttu-id="03dce-134">No podrá ver un nombre de usuario o contraseña, que es el punto de OAuth.</span><span class="sxs-lookup"><span data-stu-id="03dce-134">You won’t see a username or password, which is the point of OAuth.</span></span> <span data-ttu-id="03dce-135">Pero se verá al emisor 'Office': en este caso '4' es Skype para empresas – y el dominio Kerberos de su suscripción.</span><span class="sxs-lookup"><span data-stu-id="03dce-135">But you will see   the ‘Office’ issuer – in this case ‘4’ is Skype for Business – and the realm of your subscription.</span></span>

<span data-ttu-id="03dce-136">Si desea estar seguro de que ya está utilizando OAuth, asegúrese de que saber qué esperar y saber lo que el tráfico debe ser similar.</span><span class="sxs-lookup"><span data-stu-id="03dce-136">If you want to be sure you’re successfully using OAuth, make certain you know what to expect and know what the traffic should look like.</span></span> <span data-ttu-id="03dce-137">Es así [aquí es qué esperar](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34), aquí es bastante estándar de [ejemplo de tráfico de OAuth en una aplicación de Microsoft](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf) (realmente útil para leer, aunque no utilice tokens de actualización) y hay extensiones de Fiddler que le permiten buscar en su OAuth JWT (JSON Token de Web).</span><span class="sxs-lookup"><span data-stu-id="03dce-137">So [here’s what to expect](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34), here’s a pretty standard [example of OAuth traffic in a Microsoft application](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf)  (really helpful to read, though it doesn't use Refresh tokens), and there are Fiddler extensions that will let you look into your OAuth JWT (JSON Web Token).</span></span>

<span data-ttu-id="03dce-138">Este es un [ejemplo de configuración de una copia de seguridad](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/), pero se puede usar cualquier herramienta de seguimiento de red que desee para llevar a cabo este proceso.</span><span class="sxs-lookup"><span data-stu-id="03dce-138">Here's an [example of setting one up](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/), but you can use any network tracing tool you like to undertake this process.</span></span>

## <a name="related-topics"></a><span data-ttu-id="03dce-139">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="03dce-139">Related topics</span></span>

[<span data-ttu-id="03dce-140">Configurar la autenticación de OAuth entre organizaciones de Exchange y Exchange Online</span><span class="sxs-lookup"><span data-stu-id="03dce-140">Configure OAuth authentication between Exchange and Exchange Online organizations</span></span>](https://docs.microsoft.com/en-us/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)
