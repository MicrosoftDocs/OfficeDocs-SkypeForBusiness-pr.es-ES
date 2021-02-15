---
title: Enrutamiento directo SBA
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 12/08/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: Obtenga más información sobre enrutamiento directo, como la configuración, las decisiones básicas de implementación necesarias y las consideraciones de enrutamiento de voz.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9fb8812fd025317eb9c6e3c67ce1f5fcea094978
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196494"
---
# <a name="survivable-branch-appliance-sba-for-direct-routing"></a><span data-ttu-id="e0642-103">Dispositivo de rama intercambiable (SBA) para enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="e0642-103">Survivable Branch Appliance (SBA) for Direct Routing</span></span>


<span data-ttu-id="e0642-104">En ocasiones, un sitio de cliente que usa enrutamiento directo para conectarse a Microsoft Phone System puede experimentar una interrupción de Internet.</span><span class="sxs-lookup"><span data-stu-id="e0642-104">Occasionally, a customer site using Direct Routing to connect to Microsoft Phone System may experience an internet outage.</span></span>

<span data-ttu-id="e0642-105">Suponga que el sitio del cliente (denominado una rama) no puede conectarse temporalmente a la nube de Microsoft a través del enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="e0642-105">Assume that the customer site--called a branch--temporarily cannot connect to the Microsoft cloud through Direct Routing.</span></span> <span data-ttu-id="e0642-106">Sin embargo, la intranet dentro de la rama sigue siendo completamente funcional y los usuarios pueden conectarse al controlador de borde de sesión (SBC) que proporciona conectividad RTC.</span><span class="sxs-lookup"><span data-stu-id="e0642-106">However, the intranet inside the branch is still fully functional and users can connect to the Session Border Controller (SBC) that is providing PSTN connectivity.</span></span>

<span data-ttu-id="e0642-107">En este artículo se describe cómo usar un dispositivo de sucursal fácilmente (SBA) para permitir que Microsoft Phone System siga haciendo y recibiendo llamadas de red telefónica conmutada (RTC) públicas en caso de interrupción.</span><span class="sxs-lookup"><span data-stu-id="e0642-107">This article describes how to use a Survivable Branch Appliance (SBA) to enable Microsoft Phone System to continue to make and receive Public Switched Telephone Network (PSTN) calls in the case of an outage.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e0642-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="e0642-108">Prerequisites</span></span>

<span data-ttu-id="e0642-109">Microsoft distribuye el código SBA a los proveedores de SBC que después insertan código en su firmware o lo distribuyen por separado para que SBA se ejecute en una máquina virtual o hardware independiente.</span><span class="sxs-lookup"><span data-stu-id="e0642-109">The SBA is distributable code provided by Microsoft to SBC vendors who then embed code into their firmware or distribute it separately to have SBA run on a separate VM or hardware.</span></span> 

<span data-ttu-id="e0642-110">Para obtener el firmware más reciente del controlador de borde de sesión con el dispositivo de rama intercambiable insertado, póngase en contacto con su proveedor de SBC.</span><span class="sxs-lookup"><span data-stu-id="e0642-110">To get the latest Session Border Controller firmware with the embedded Survivable Branch Appliance,  contact your SBC vendor.</span></span> <span data-ttu-id="e0642-111">Además, es necesario lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e0642-111">In addition, the following is required:</span></span>

- <span data-ttu-id="e0642-112">Es necesario configurar SBC para omitir medios para asegurarse de que el cliente de Microsoft Teams en el sitio de rama puede tener medios que fluyen directamente con la SBC.</span><span class="sxs-lookup"><span data-stu-id="e0642-112">The SBC needs to be configured for Media Bypass to ensure that the Microsoft Teams client in the branch site can have media flowing directly with the SBC.</span></span> 

- <span data-ttu-id="e0642-113">TLS1.2 debe estar habilitado en el sistema operativo SBA VM.</span><span class="sxs-lookup"><span data-stu-id="e0642-113">TLS1.2 should be enabled on the SBA VM OS.</span></span>

## <a name="supported-teams-clients"></a><span data-ttu-id="e0642-114">Clientes de Teams compatibles</span><span class="sxs-lookup"><span data-stu-id="e0642-114">Supported Teams clients</span></span>

<span data-ttu-id="e0642-115">La característica SBA es compatible con los siguientes clientes de Microsoft Teams:</span><span class="sxs-lookup"><span data-stu-id="e0642-115">The SBA feature is supported on the following Microsoft Teams clients:</span></span> 

- <span data-ttu-id="e0642-116">Escritorio de Microsoft Teams para Windows</span><span class="sxs-lookup"><span data-stu-id="e0642-116">Microsoft Teams Windows desktop</span></span> 

- <span data-ttu-id="e0642-117">Escritorio de Microsoft Teams para macOS</span><span class="sxs-lookup"><span data-stu-id="e0642-117">Microsoft Teams macOS desktop</span></span> 

## <a name="how-it-works"></a><span data-ttu-id="e0642-118">Cómo funciona</span><span class="sxs-lookup"><span data-stu-id="e0642-118">How it works</span></span>

<span data-ttu-id="e0642-119">Durante una interrupción de Internet, el cliente de Teams debe cambiar al SBA automáticamente y las llamadas en curso deberían continuar sin interrupciones.</span><span class="sxs-lookup"><span data-stu-id="e0642-119">During an internet outage, the Teams client should switch to the SBA automatically, and ongoing calls should continue with no interruptions.</span></span> <span data-ttu-id="e0642-120">El usuario no necesita realizar ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="e0642-120">No action is required from the user.</span></span> <span data-ttu-id="e0642-121">Tan pronto como el cliente de Teams detecta que Internet está listo y las llamadas salientes han finalizado, el cliente volverá al modo de funcionamiento normal y se conectará a otros servicios de Teams.</span><span class="sxs-lookup"><span data-stu-id="e0642-121">As soon as the Teams client detects that the internet is up and any outgoing calls are finished, the client will fall back to normal operation mode and connect to other Teams services.</span></span> <span data-ttu-id="e0642-122">El SBA cargará los registros de datos de llamadas recopilados en la nube y el historial de llamadas se actualizará para que el administrador de inquilinos pueda revisar esta información.</span><span class="sxs-lookup"><span data-stu-id="e0642-122">The SBA will upload collected Call Data Records to the cloud and call history will be updated so that this information is available for review by the tenant administrator.</span></span> 

<span data-ttu-id="e0642-123">Cuando el cliente de Microsoft Teams está en modo sin conexión, está disponible la siguiente funcionalidad relacionada con las llamadas:</span><span class="sxs-lookup"><span data-stu-id="e0642-123">When the Microsoft Teams client is in offline mode, the following calling-related functionality is available:</span></span> 

- <span data-ttu-id="e0642-124">Realizar llamadas RTC a través de SBA/SBC local con medios que fluyen por la SBC.</span><span class="sxs-lookup"><span data-stu-id="e0642-124">Making PSTN calls via local SBA/SBC with media flowing through the SBC.</span></span>

- <span data-ttu-id="e0642-125">Recibir llamadas RTC a través de SBA/SBC local con medios que fluyen por la SBC.</span><span class="sxs-lookup"><span data-stu-id="e0642-125">Receiving PSTN calls via local SBA/SBC with media flowing through the SBC.</span></span> 

- <span data-ttu-id="e0642-126">Retenciones y reanudación de llamadas RTC.</span><span class="sxs-lookup"><span data-stu-id="e0642-126">Hold and Resume of PSTN calls.</span></span>

## <a name="configuration"></a><span data-ttu-id="e0642-127">Configuración</span><span class="sxs-lookup"><span data-stu-id="e0642-127">Configuration</span></span>

<span data-ttu-id="e0642-128">Para que la característica SBA funcione, el cliente de Teams necesita saber qué SBA están disponibles en cada sitio de rama y qué SBA se asignan a los usuarios en ese sitio.</span><span class="sxs-lookup"><span data-stu-id="e0642-128">For the SBA feature to work, the Teams client needs to know which SBAs are available in each branch site, and which SBAs are assigned to the users in that site.</span></span> <span data-ttu-id="e0642-129">Los pasos de configuración son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="e0642-129">The configuration steps are as follows:</span></span>

1. <span data-ttu-id="e0642-130">Crear las OSN.</span><span class="sxs-lookup"><span data-stu-id="e0642-130">Create the SBAs.</span></span>
2. <span data-ttu-id="e0642-131">Cree la directiva de capacidad de ampliación de la rama de Teams.</span><span class="sxs-lookup"><span data-stu-id="e0642-131">Create the Teams branch survivability policy.</span></span>
3. <span data-ttu-id="e0642-132">Asigne la directiva a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="e0642-132">Assign the policy to users.</span></span>
4. <span data-ttu-id="e0642-133">Registrar una aplicación para el SBA con Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e0642-133">Register an application for the SBA with Azure Active Directory.</span></span>

<span data-ttu-id="e0642-134">Toda la configuración se realiza con los cmdlets de PowerShell de Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="e0642-134">All configuration is done by using Skype for Business Online PowerShell cmdlets.</span></span> <span data-ttu-id="e0642-135">(El Centro de administración de Teams aún no admite la característica de enrutamiento directo SBA).</span><span class="sxs-lookup"><span data-stu-id="e0642-135">(The Teams admin center does not yet support the Direct Routing SBA feature.)</span></span> 

<span data-ttu-id="e0642-136">(Para obtener información sobre cómo configurar el SBC, con vínculos a la documentación del proveedor de SBC, consulte la configuración del controlador de borde de sesión al final de este artículo).</span><span class="sxs-lookup"><span data-stu-id="e0642-136">(For information on configuring the SBC, with links to SBC vendor documentation, see Session Border Controller configuration at the end of this article.)</span></span>

### <a name="create-the-sbas"></a><span data-ttu-id="e0642-137">Crear las OSN</span><span class="sxs-lookup"><span data-stu-id="e0642-137">Create the SBAs</span></span>

<span data-ttu-id="e0642-138">Para crear los SBA, usará el cmdlet New-CsTeamsSurvivableBranchAppliance específico.</span><span class="sxs-lookup"><span data-stu-id="e0642-138">To create the SBAs, you will use the New-CsTeamsSurvivableBranchAppliance cmdlet.</span></span> <span data-ttu-id="e0642-139">Este cmdlet tiene los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="e0642-139">This cmdlet has has the following parameters:</span></span>

| <span data-ttu-id="e0642-140">Parámetro</span><span class="sxs-lookup"><span data-stu-id="e0642-140">Parameter</span></span>| <span data-ttu-id="e0642-141">Descripción</span><span class="sxs-lookup"><span data-stu-id="e0642-141">Description</span></span> |
| :------------|:-------|
| <span data-ttu-id="e0642-142">Identity</span><span class="sxs-lookup"><span data-stu-id="e0642-142">Identity</span></span>  | <span data-ttu-id="e0642-143">La identidad del SBA</span><span class="sxs-lookup"><span data-stu-id="e0642-143">The identity of the SBA</span></span>  |
| <span data-ttu-id="e0642-144">Fqdn</span><span class="sxs-lookup"><span data-stu-id="e0642-144">Fqdn</span></span> | <span data-ttu-id="e0642-145">El FQDN del SBA</span><span class="sxs-lookup"><span data-stu-id="e0642-145">The FQDN of the SBA</span></span> |
| <span data-ttu-id="e0642-146">Sitio</span><span class="sxs-lookup"><span data-stu-id="e0642-146">Site</span></span> | <span data-ttu-id="e0642-147">El sitio tenantNetworksite donde se encuentra el SBA</span><span class="sxs-lookup"><span data-stu-id="e0642-147">The TenantNetworkSite where the SBA is located</span></span> |
| <span data-ttu-id="e0642-148">Descripción</span><span class="sxs-lookup"><span data-stu-id="e0642-148">Description</span></span> | <span data-ttu-id="e0642-149">Texto con formato gratuito</span><span class="sxs-lookup"><span data-stu-id="e0642-149">Free format text</span></span> |
|||

<span data-ttu-id="e0642-150">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e0642-150">For example:</span></span>

``` powershell
C:\> New-CsTeamsSurvivableBranchAppliance  -Fqdn sba1.contoso.com -Description "SBA 1" 
Identity    : sba1.contoso.com 
Fqdn        : sba1.contoso.com 
Site        : 
Description : SBA 1 
```

### <a name="create-the-teams-branch-survivability-policy"></a><span data-ttu-id="e0642-151">Crear la directiva de idoneidad de la rama de Teams</span><span class="sxs-lookup"><span data-stu-id="e0642-151">Create the Teams Branch Survivability Policy</span></span> 

<span data-ttu-id="e0642-152">Para crear una directiva, use el cmdlet New-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e0642-152">To create a policy, you use the New-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span></span> <span data-ttu-id="e0642-153">Este cmdlet tiene los parámetros siguientes.</span><span class="sxs-lookup"><span data-stu-id="e0642-153">This cmdlet has the following parameters.</span></span> <span data-ttu-id="e0642-154">Tenga en cuenta que la directiva puede contener uno o varios SBA.</span><span class="sxs-lookup"><span data-stu-id="e0642-154">Note that the policy can contain one or more SBAs.</span></span>

| <span data-ttu-id="e0642-155">Parámetro</span><span class="sxs-lookup"><span data-stu-id="e0642-155">Parameter</span></span>| <span data-ttu-id="e0642-156">Descripción</span><span class="sxs-lookup"><span data-stu-id="e0642-156">Description</span></span> |
| :------------|:-------|
| <span data-ttu-id="e0642-157">Identity</span><span class="sxs-lookup"><span data-stu-id="e0642-157">Identity</span></span> | <span data-ttu-id="e0642-158">La identidad de la directiva</span><span class="sxs-lookup"><span data-stu-id="e0642-158">The identity of the policy</span></span> |
| <span data-ttu-id="e0642-159">BranchApplianceFqdns</span><span class="sxs-lookup"><span data-stu-id="e0642-159">BranchApplianceFqdns</span></span>  | <span data-ttu-id="e0642-160">El FQDN de los SBA en el sitio</span><span class="sxs-lookup"><span data-stu-id="e0642-160">The FQDN of the SBA(s) in the site</span></span> |
||

<span data-ttu-id="e0642-161">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e0642-161">For example:</span></span>

``` powershell
C:\> new-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns "sba1.contoso.com","sba2.contoso.com" 
Identity             : Tag:CPH 
BranchApplianceFqdns : {sba1.contoso.com, sba2.contoso.com} 
```

<span data-ttu-id="e0642-162">Puede agregar o quitar OSBA de una directiva mediante el Set-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e0642-162">You can add or remove SBAs from a policy by using the Set-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span></span> <span data-ttu-id="e0642-163">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e0642-163">For example:</span></span> 

``` powershell
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{remove="sba1.contoso.com"} 
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{add="sba1.contoso.com"} 
```

### <a name="assign-a-policy-to-a-user"></a><span data-ttu-id="e0642-164">Asignar una directiva a un usuario</span><span class="sxs-lookup"><span data-stu-id="e0642-164">Assign a policy to a user</span></span>

<span data-ttu-id="e0642-165">Para asignar la directiva a usuarios individuales, usará el cmdlet Grant-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e0642-165">To assign the policy to individual users, you will use the Grant-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span></span> <span data-ttu-id="e0642-166">Este cmdlet tiene los parámetros siguientes:</span><span class="sxs-lookup"><span data-stu-id="e0642-166">This cmdlet has the following parameters:</span></span>

| <span data-ttu-id="e0642-167">Parámetro</span><span class="sxs-lookup"><span data-stu-id="e0642-167">Parameter</span></span>| <span data-ttu-id="e0642-168">Descripción</span><span class="sxs-lookup"><span data-stu-id="e0642-168">Description</span></span> |
| :------------|:-------|
| <span data-ttu-id="e0642-169">Identity</span><span class="sxs-lookup"><span data-stu-id="e0642-169">Identity</span></span> | <span data-ttu-id="e0642-170">La identidad del usuario</span><span class="sxs-lookup"><span data-stu-id="e0642-170">The identity of the user</span></span> |
| <span data-ttu-id="e0642-171">PolicyName</span><span class="sxs-lookup"><span data-stu-id="e0642-171">PolicyName</span></span> | <span data-ttu-id="e0642-172">La identidad de la directiva</span><span class="sxs-lookup"><span data-stu-id="e0642-172">The identity of the policy</span></span> |
||

<span data-ttu-id="e0642-173">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e0642-173">For example:</span></span>

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName CPH -Identity user@contoso.com 
```

<span data-ttu-id="e0642-174">Puede quitar una directiva a un usuario concediendo $Null directiva de directiva de usuario como se muestra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e0642-174">You can remove a policy from a user by granting the $Null policy as shown in the next example:</span></span>

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName $Null -Identity user@contoso.com 
```

### <a name="register-an-application-for-the-sba-with-azure-active-directory"></a><span data-ttu-id="e0642-175">Registrar una aplicación para el SBA con Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="e0642-175">Register an application for the SBA with Azure Active Directory</span></span>

<span data-ttu-id="e0642-176">Para permitir que diferentes SBA que se usan en su espacio empresarial puedan leer los datos necesarios de Microsoft 365, debe registrar una aplicación para el SBA en Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e0642-176">To allow different SBAs used within your tenant to read required data from Microsoft 365, you need to register an application for the SBA with Azure Active Directory.</span></span> 

<span data-ttu-id="e0642-177">Para obtener más información sobre el registro de aplicaciones, vea lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e0642-177">For more information about application registration, see the following:</span></span>

- [<span data-ttu-id="e0642-178">Desarrollo de aplicaciones de línea de negocio para Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="e0642-178">Develop line-of-business apps for Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/manage-apps/developer-guidance-for-integrating-applications)

- <span data-ttu-id="e0642-179">[Registra una aplicación en la plataforma de identidad de Microsoft.](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app)</span><span class="sxs-lookup"><span data-stu-id="e0642-179">[Register an application with the Microsoft identity platform](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).</span></span>  

<span data-ttu-id="e0642-180">Solo necesita registrar una solicitud para que la usen todos los OBA de su inquilino.</span><span class="sxs-lookup"><span data-stu-id="e0642-180">You only need to register one application for use by all the SBAs in your tenant.</span></span> 

<span data-ttu-id="e0642-181">Para el registro SBA, necesita los siguientes valores creados por el registro:</span><span class="sxs-lookup"><span data-stu-id="e0642-181">For the SBA registration, you need the following values created by the registration:</span></span> 

- <span data-ttu-id="e0642-182">Id. de aplicación (cliente)</span><span class="sxs-lookup"><span data-stu-id="e0642-182">Application (client) ID</span></span> 
- <span data-ttu-id="e0642-183">Secreto de cliente</span><span class="sxs-lookup"><span data-stu-id="e0642-183">Client secret</span></span> 

<span data-ttu-id="e0642-184">Para la aplicación SBA, ten en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e0642-184">For the SBA application, keep the following in mind:</span></span> 

- <span data-ttu-id="e0642-185">El nombre puede ser el que decida.</span><span class="sxs-lookup"><span data-stu-id="e0642-185">The name can be whatever you decide.</span></span>  
- <span data-ttu-id="e0642-186">Tipos de cuenta compatibles = Solo cuenta en este directorio de la organización.</span><span class="sxs-lookup"><span data-stu-id="e0642-186">Supported account types = Account in this organizational directory only.</span></span> 
- <span data-ttu-id="e0642-187">El Uri de redirección web = https://login.microsoftonline.com/common/oauth2/nativeclient .</span><span class="sxs-lookup"><span data-stu-id="e0642-187">The Web Redirect Uri = https://login.microsoftonline.com/common/oauth2/nativeclient.</span></span>
- <span data-ttu-id="e0642-188">Tokens de concesión implícita = tokens de acceso e identificador.</span><span class="sxs-lookup"><span data-stu-id="e0642-188">Implicit grant tokens = Access tokens and ID tokens.</span></span> 
- <span data-ttu-id="e0642-189">Permisos de API = Acceso para administradores de inquilinos de Skype > -> application_access_custom_sba_appliance.</span><span class="sxs-lookup"><span data-stu-id="e0642-189">API permissions = Skype and Teams Tenant Admin Access -> Application permissions -> application_access_custom_sba_appliance.</span></span>
- <span data-ttu-id="e0642-190">Secreto de cliente: puede usar cualquier descripción y expiración.</span><span class="sxs-lookup"><span data-stu-id="e0642-190">Client secret: you can use any description and expiration.</span></span> 
- <span data-ttu-id="e0642-191">Recuerde copiar el secreto de cliente inmediatamente después de crearlo.</span><span class="sxs-lookup"><span data-stu-id="e0642-191">Remember to copy the client secret immediately after creating it.</span></span> 
- <span data-ttu-id="e0642-192">El Id. de la aplicación (cliente) se muestra en la pestaña Descripción general.</span><span class="sxs-lookup"><span data-stu-id="e0642-192">The Application (client) ID is shown on the Overview tab.</span></span>

<span data-ttu-id="e0642-193">A continuación, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="e0642-193">Then follow these steps:</span></span>

1. <span data-ttu-id="e0642-194">Registre la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e0642-194">Register the application.</span></span>
2. <span data-ttu-id="e0642-195">Establecer los tokens de concesión implícita.</span><span class="sxs-lookup"><span data-stu-id="e0642-195">Set the implicit grant tokens.</span></span>
3. <span data-ttu-id="e0642-196">Establezca los permisos de la API.</span><span class="sxs-lookup"><span data-stu-id="e0642-196">Set the API permissions.</span></span>
4. <span data-ttu-id="e0642-197">Cree el secreto de cliente.</span><span class="sxs-lookup"><span data-stu-id="e0642-197">Create the client secret.</span></span>


## <a name="session-border-controller-configuration"></a><span data-ttu-id="e0642-198">Configuración del controlador de borde de sesión</span><span class="sxs-lookup"><span data-stu-id="e0642-198">Session Border Controller configuration</span></span> 

<span data-ttu-id="e0642-199">Para obtener instrucciones paso a paso sobre cómo configurar el controlador de borde de sesión con el dispositivo de rama intercambiable insertado, consulte la documentación proporcionada por su proveedor de SBC:</span><span class="sxs-lookup"><span data-stu-id="e0642-199">For step-by-step guidance on how to configure your Session Border Controller with the embedded Survivable Branch Appliance, see the documentation provided by your SBC vendor:</span></span> 

- [<span data-ttu-id="e0642-200">AudioCodes</span><span class="sxs-lookup"><span data-stu-id="e0642-200">AudioCodes</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-survivable-branch-appliances)

- [<span data-ttu-id="e0642-201">Cinta de opciones</span><span class="sxs-lookup"><span data-stu-id="e0642-201">Ribbon</span></span>](https://support.sonus.net/pages/viewpage.action?pageId=248644034)

- [<span data-ttu-id="e0642-202">Oracle</span><span class="sxs-lookup"><span data-stu-id="e0642-202">Oracle</span></span>](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams) 

- [<span data-ttu-id="e0642-203">TE-Systems</span><span class="sxs-lookup"><span data-stu-id="e0642-203">TE-Systems</span></span>](https://www.anynode.de/microsoft-teams-sba/)

## <a name="reporting-issues"></a><span data-ttu-id="e0642-204">Informar de problemas</span><span class="sxs-lookup"><span data-stu-id="e0642-204">Reporting issues</span></span>

<span data-ttu-id="e0642-205">Informe de cualquier problema a la organización de soporte técnico de su proveedor de SBC.</span><span class="sxs-lookup"><span data-stu-id="e0642-205">Report any issues to your SBC vendor's support organization.</span></span> <span data-ttu-id="e0642-206">Al informar del problema, indica que tienes configurado un dispositivo de rama manejable.</span><span class="sxs-lookup"><span data-stu-id="e0642-206">When reporting the issue, indicate that you have a configured Survivable Branch Appliance.</span></span>

## <a name="known-issues"></a><span data-ttu-id="e0642-207">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="e0642-207">Known issues</span></span>

- <span data-ttu-id="e0642-208">Al agregar nuevos dispositivos de rama intercambiables, es posible que deba tardar algún tiempo antes de poder usarlos en directivas de aplicaciones de sucursal fáciles de usar.</span><span class="sxs-lookup"><span data-stu-id="e0642-208">When you add new Survivable Branch Appliances, it might take some time before you can use them in Survivable Branch Appliance policies.</span></span>

- <span data-ttu-id="e0642-209">Al asignar una directiva de aplicación de bifurcación intercambiable a un usuario, puede tardar algún tiempo antes de que se muestra el SBA en la salida de Get-CsOnlineUser.</span><span class="sxs-lookup"><span data-stu-id="e0642-209">When you assign a Survivable Branch Appliance policy to a user, it might take some time before the SBA is shown in the output of Get-CsOnlineUser.</span></span> 

- <span data-ttu-id="e0642-210">No se realiza la búsqueda inversa de números en los contactos de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="e0642-210">Reverse number lookup against Azure AD Contacts is not performed.</span></span> 

- <span data-ttu-id="e0642-211">El SBA no admite la configuración de reenvío de llamadas.</span><span class="sxs-lookup"><span data-stu-id="e0642-211">The SBA does not support call forwarding settings.</span></span> 

- <span data-ttu-id="e0642-212">No se admite realizar una llamada de emergencia a un número de emergencia configurado para llamadas de emergencia dinámicas (E911).</span><span class="sxs-lookup"><span data-stu-id="e0642-212">Making an emergency call to an emergency number configured for dynamic emergency calling (E911) is not supported.</span></span>

- <span data-ttu-id="e0642-213">El resultado del Get-CsOnlineUser muestra TeamsBranchSur inteligenciabilityPolicy.</span><span class="sxs-lookup"><span data-stu-id="e0642-213">The output of Get-CsOnlineUser shows TeamsBranchSurvivabilityPolicy.</span></span>
