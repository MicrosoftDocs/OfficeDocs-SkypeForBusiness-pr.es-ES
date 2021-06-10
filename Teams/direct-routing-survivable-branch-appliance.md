---
title: Direct Routing SBA
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
description: Obtenga más información sobre enrutamiento directo, como configuración, decisiones básicas de implementación necesarias y consideraciones de enrutamiento de voz.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6d6342f41b3cd4bfad690794c0b6474ca45e78c8
ms.sourcegitcommit: bdd9901db1fc741aaec9c7ddcf5ee1caaca4d777
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2021
ms.locfileid: "52589244"
---
# <a name="survivable-branch-appliance-sba-for-direct-routing"></a><span data-ttu-id="42764-103">Dispositivo de sucursal con funciones de supervivencia (SBA) para enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="42764-103">Survivable Branch Appliance (SBA) for Direct Routing</span></span>


<span data-ttu-id="42764-104">En ocasiones, un sitio de cliente que usa Enrutamiento directo para conectarse a Teléfono Microsoft sistema puede experimentar una interrupción de Internet.</span><span class="sxs-lookup"><span data-stu-id="42764-104">Occasionally, a customer site using Direct Routing to connect to Microsoft Phone System may experience an internet outage.</span></span>

<span data-ttu-id="42764-105">Suponga que el sitio del cliente (denominado rama) no puede conectarse temporalmente a la nube de Microsoft a través del enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="42764-105">Assume that the customer site--called a branch--temporarily cannot connect to the Microsoft cloud through Direct Routing.</span></span> <span data-ttu-id="42764-106">Sin embargo, la intranet dentro de la rama sigue siendo totalmente funcional y los usuarios pueden conectarse al controlador de borde de sesión (SBC) que proporciona conectividad RTC.</span><span class="sxs-lookup"><span data-stu-id="42764-106">However, the intranet inside the branch is still fully functional and users can connect to the Session Border Controller (SBC) that is providing PSTN connectivity.</span></span>

<span data-ttu-id="42764-107">En este artículo se describe cómo usar un dispositivo de sucursal con funciones de supervivencia (SBA) para permitir que Teléfono Microsoft System siga haciendo y recibiendo llamadas de red telefónica conmutada (RTC) en caso de interrupción.</span><span class="sxs-lookup"><span data-stu-id="42764-107">This article describes how to use a Survivable Branch Appliance (SBA) to enable Microsoft Phone System to continue to make and receive Public Switched Telephone Network (PSTN) calls in the case of an outage.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="42764-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="42764-108">Prerequisites</span></span>

<span data-ttu-id="42764-109">El SBA es un código distribuible proporcionado por Microsoft a los proveedores de SBC que, a continuación, insertan código en su firmware o lo distribuyen por separado para que SBA se ejecute en una máquina virtual o hardware independiente.</span><span class="sxs-lookup"><span data-stu-id="42764-109">The SBA is distributable code provided by Microsoft to SBC vendors who then embed code into their firmware or distribute it separately to have SBA run on a separate VM or hardware.</span></span> 

<span data-ttu-id="42764-110">Para obtener el firmware más reciente del controlador de borde de sesión con el dispositivo de sucursal con supervivencia incrustado, póngase en contacto con su proveedor de SBC.</span><span class="sxs-lookup"><span data-stu-id="42764-110">To get the latest Session Border Controller firmware with the embedded Survivable Branch Appliance,  contact your SBC vendor.</span></span> <span data-ttu-id="42764-111">Además, se requiere lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="42764-111">In addition, the following is required:</span></span>

- <span data-ttu-id="42764-112">El SBC debe configurarse para la omisión de medios para asegurarse de que el cliente Microsoft Teams en el sitio de sucursal puede tener los medios fluyendo directamente con el SBC.</span><span class="sxs-lookup"><span data-stu-id="42764-112">The SBC needs to be configured for Media Bypass to ensure that the Microsoft Teams client in the branch site can have media flowing directly with the SBC.</span></span> 

- <span data-ttu-id="42764-113">TLS1.2 debe estar habilitado en el sistema operativo de máquina virtual de SBA.</span><span class="sxs-lookup"><span data-stu-id="42764-113">TLS1.2 should be enabled on the SBA VM OS.</span></span>

## <a name="supported-teams-clients"></a><span data-ttu-id="42764-114">Clientes Teams compatibles</span><span class="sxs-lookup"><span data-stu-id="42764-114">Supported Teams clients</span></span>

<span data-ttu-id="42764-115">La característica SBA es compatible con los siguientes Microsoft Teams cliente:</span><span class="sxs-lookup"><span data-stu-id="42764-115">The SBA feature is supported on the following Microsoft Teams clients:</span></span> 

- <span data-ttu-id="42764-116">Microsoft Teams Windows escritorio</span><span class="sxs-lookup"><span data-stu-id="42764-116">Microsoft Teams Windows desktop</span></span> 

- <span data-ttu-id="42764-117">Microsoft Teams escritorio de macOS</span><span class="sxs-lookup"><span data-stu-id="42764-117">Microsoft Teams macOS desktop</span></span> 

## <a name="how-it-works"></a><span data-ttu-id="42764-118">Cómo funciona</span><span class="sxs-lookup"><span data-stu-id="42764-118">How it works</span></span>

<span data-ttu-id="42764-119">Durante una interrupción de Internet, el Teams debe cambiar al SBA automáticamente y las llamadas en curso deben continuar sin interrupciones.</span><span class="sxs-lookup"><span data-stu-id="42764-119">During an internet outage, the Teams client should switch to the SBA automatically, and ongoing calls should continue with no interruptions.</span></span> <span data-ttu-id="42764-120">No se requiere ninguna acción del usuario.</span><span class="sxs-lookup"><span data-stu-id="42764-120">No action is required from the user.</span></span> <span data-ttu-id="42764-121">Tan pronto como el cliente Teams detecta que Internet está listo y las llamadas salientes han finalizado, el cliente volverá al modo de funcionamiento normal y se conectará a otros Teams servicios.</span><span class="sxs-lookup"><span data-stu-id="42764-121">As soon as the Teams client detects that the internet is up and any outgoing calls are finished, the client will fall back to normal operation mode and connect to other Teams services.</span></span> <span data-ttu-id="42764-122">El SBA cargará los registros de datos de llamadas recopilados en la nube y el historial de llamadas se actualizará para que esta información esté disponible para su revisión por el administrador de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="42764-122">The SBA will upload collected Call Data Records to the cloud and call history will be updated so that this information is available for review by the tenant administrator.</span></span> 

<span data-ttu-id="42764-123">Cuando el Microsoft Teams está en modo sin conexión, está disponible la siguiente funcionalidad relacionada con las llamadas:</span><span class="sxs-lookup"><span data-stu-id="42764-123">When the Microsoft Teams client is in offline mode, the following calling-related functionality is available:</span></span> 

- <span data-ttu-id="42764-124">Realizar llamadas RTC a través de SBA/SBC local con los medios que fluyen por el SBC.</span><span class="sxs-lookup"><span data-stu-id="42764-124">Making PSTN calls via local SBA/SBC with media flowing through the SBC.</span></span>

- <span data-ttu-id="42764-125">Recibir llamadas RTC a través de SBA/SBC local con los medios que fluyen por el SBC.</span><span class="sxs-lookup"><span data-stu-id="42764-125">Receiving PSTN calls via local SBA/SBC with media flowing through the SBC.</span></span> 

- <span data-ttu-id="42764-126">Retener y reanudar llamadas RTC.</span><span class="sxs-lookup"><span data-stu-id="42764-126">Hold and Resume of PSTN calls.</span></span>

## <a name="configuration"></a><span data-ttu-id="42764-127">Configuración</span><span class="sxs-lookup"><span data-stu-id="42764-127">Configuration</span></span>

<span data-ttu-id="42764-128">Para que la característica SBA funcione, el cliente de Teams debe saber qué SBA están disponibles en cada sitio de sucursal y qué SBA están asignados a los usuarios de ese sitio.</span><span class="sxs-lookup"><span data-stu-id="42764-128">For the SBA feature to work, the Teams client needs to know which SBAs are available in each branch site, and which SBAs are assigned to the users in that site.</span></span> <span data-ttu-id="42764-129">Los pasos de configuración son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="42764-129">The configuration steps are as follows:</span></span>

1. <span data-ttu-id="42764-130">Cree los SBA.</span><span class="sxs-lookup"><span data-stu-id="42764-130">Create the SBAs.</span></span>
2. <span data-ttu-id="42764-131">Cree la directiva Teams de supervivencia de la rama.</span><span class="sxs-lookup"><span data-stu-id="42764-131">Create the Teams branch survivability policy.</span></span>
3. <span data-ttu-id="42764-132">Asigne la directiva a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="42764-132">Assign the policy to users.</span></span>
4. <span data-ttu-id="42764-133">Registre una aplicación para el SBA con Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="42764-133">Register an application for the SBA with Azure Active Directory.</span></span>

<span data-ttu-id="42764-134">Toda la configuración se realiza Skype Empresarial cmdlets de PowerShell en línea.</span><span class="sxs-lookup"><span data-stu-id="42764-134">All configuration is done by using Skype for Business Online PowerShell cmdlets.</span></span> <span data-ttu-id="42764-135">(El Teams de administración de enrutamiento directo aún no es compatible con la característica SBA de enrutamiento directo).</span><span class="sxs-lookup"><span data-stu-id="42764-135">(The Teams admin center does not yet support the Direct Routing SBA feature.)</span></span> 

<span data-ttu-id="42764-136">(Para obtener información sobre cómo configurar el SBC, con vínculos a la documentación del proveedor de SBC, vea Configuración del controlador de borde de sesión al final de este artículo).</span><span class="sxs-lookup"><span data-stu-id="42764-136">(For information on configuring the SBC, with links to SBC vendor documentation, see Session Border Controller configuration at the end of this article.)</span></span>

### <a name="create-the-sbas"></a><span data-ttu-id="42764-137">Crear los SBA</span><span class="sxs-lookup"><span data-stu-id="42764-137">Create the SBAs</span></span>

<span data-ttu-id="42764-138">Para crear los SBA, usará el cmdlet New-CsTeamsSurvivableBranchAppliance.</span><span class="sxs-lookup"><span data-stu-id="42764-138">To create the SBAs, you will use the New-CsTeamsSurvivableBranchAppliance cmdlet.</span></span> <span data-ttu-id="42764-139">Este cmdlet tiene los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="42764-139">This cmdlet has the following parameters:</span></span>

| <span data-ttu-id="42764-140">Parámetro</span><span class="sxs-lookup"><span data-stu-id="42764-140">Parameter</span></span>| <span data-ttu-id="42764-141">Descripción</span><span class="sxs-lookup"><span data-stu-id="42764-141">Description</span></span> |
| :------------|:-------|
| <span data-ttu-id="42764-142">Identity</span><span class="sxs-lookup"><span data-stu-id="42764-142">Identity</span></span>  | <span data-ttu-id="42764-143">La identidad del SBA</span><span class="sxs-lookup"><span data-stu-id="42764-143">The identity of the SBA</span></span>  |
| <span data-ttu-id="42764-144">Fqdn</span><span class="sxs-lookup"><span data-stu-id="42764-144">Fqdn</span></span> | <span data-ttu-id="42764-145">El FQDN del SBA</span><span class="sxs-lookup"><span data-stu-id="42764-145">The FQDN of the SBA</span></span> |
| <span data-ttu-id="42764-146">Sitio</span><span class="sxs-lookup"><span data-stu-id="42764-146">Site</span></span> | <span data-ttu-id="42764-147">El TenantNetworkSite donde se encuentra el SBA</span><span class="sxs-lookup"><span data-stu-id="42764-147">The TenantNetworkSite where the SBA is located</span></span> |
| <span data-ttu-id="42764-148">Descripción</span><span class="sxs-lookup"><span data-stu-id="42764-148">Description</span></span> | <span data-ttu-id="42764-149">Texto con formato libre</span><span class="sxs-lookup"><span data-stu-id="42764-149">Free format text</span></span> |
|||

<span data-ttu-id="42764-150">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="42764-150">For example:</span></span>

``` powershell
C:\> New-CsTeamsSurvivableBranchAppliance  -Fqdn sba1.contoso.com -Description "SBA 1" 
Identity    : sba1.contoso.com 
Fqdn        : sba1.contoso.com 
Site        : 
Description : SBA 1 
```

### <a name="create-the-teams-branch-survivability-policy"></a><span data-ttu-id="42764-151">Crear la directiva de Teams de supervivencia de la rama</span><span class="sxs-lookup"><span data-stu-id="42764-151">Create the Teams Branch Survivability Policy</span></span> 

<span data-ttu-id="42764-152">Para crear una directiva, use el cmdlet New-CsTeamsSurvivableBranchAppliancePolicy datos.</span><span class="sxs-lookup"><span data-stu-id="42764-152">To create a policy, you use the New-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span></span> <span data-ttu-id="42764-153">Este cmdlet tiene los siguientes parámetros.</span><span class="sxs-lookup"><span data-stu-id="42764-153">This cmdlet has the following parameters.</span></span> <span data-ttu-id="42764-154">Tenga en cuenta que la directiva puede contener uno o varios SBA.</span><span class="sxs-lookup"><span data-stu-id="42764-154">Note that the policy can contain one or more SBAs.</span></span>

| <span data-ttu-id="42764-155">Parámetro</span><span class="sxs-lookup"><span data-stu-id="42764-155">Parameter</span></span>| <span data-ttu-id="42764-156">Descripción</span><span class="sxs-lookup"><span data-stu-id="42764-156">Description</span></span> |
| :------------|:-------|
| <span data-ttu-id="42764-157">Identity</span><span class="sxs-lookup"><span data-stu-id="42764-157">Identity</span></span> | <span data-ttu-id="42764-158">La identidad de la directiva</span><span class="sxs-lookup"><span data-stu-id="42764-158">The identity of the policy</span></span> |
| <span data-ttu-id="42764-159">BranchApplianceFqdns</span><span class="sxs-lookup"><span data-stu-id="42764-159">BranchApplianceFqdns</span></span>  | <span data-ttu-id="42764-160">El FQDN de los SBA del sitio</span><span class="sxs-lookup"><span data-stu-id="42764-160">The FQDN of the SBA(s) in the site</span></span> |
||

<span data-ttu-id="42764-161">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="42764-161">For example:</span></span>

``` powershell
C:\> new-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns "sba1.contoso.com","sba2.contoso.com" 
Identity             : Tag:CPH 
BranchApplianceFqdns : {sba1.contoso.com, sba2.contoso.com} 
```

<span data-ttu-id="42764-162">Puede agregar o quitar SBA de una directiva mediante el cmdlet Set-CsTeamsSurvivableBranchAppliancePolicy directiva.</span><span class="sxs-lookup"><span data-stu-id="42764-162">You can add or remove SBAs from a policy by using the Set-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span></span> <span data-ttu-id="42764-163">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="42764-163">For example:</span></span> 

``` powershell
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{remove="sba1.contoso.com"} 
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{add="sba1.contoso.com"} 
```

### <a name="assign-a-policy-to-a-user"></a><span data-ttu-id="42764-164">Asignar una directiva a un usuario</span><span class="sxs-lookup"><span data-stu-id="42764-164">Assign a policy to a user</span></span>

<span data-ttu-id="42764-165">Para asignar la directiva a usuarios individuales, usará el cmdlet Grant-CsTeamsSurvivableBranchAppliancePolicy usuario.</span><span class="sxs-lookup"><span data-stu-id="42764-165">To assign the policy to individual users, you will use the Grant-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span></span> <span data-ttu-id="42764-166">Este cmdlet tiene los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="42764-166">This cmdlet has the following parameters:</span></span>

| <span data-ttu-id="42764-167">Parámetro</span><span class="sxs-lookup"><span data-stu-id="42764-167">Parameter</span></span>| <span data-ttu-id="42764-168">Descripción</span><span class="sxs-lookup"><span data-stu-id="42764-168">Description</span></span> |
| :------------|:-------|
| <span data-ttu-id="42764-169">Identity</span><span class="sxs-lookup"><span data-stu-id="42764-169">Identity</span></span> | <span data-ttu-id="42764-170">La identidad del usuario</span><span class="sxs-lookup"><span data-stu-id="42764-170">The identity of the user</span></span> |
| <span data-ttu-id="42764-171">PolicyName</span><span class="sxs-lookup"><span data-stu-id="42764-171">PolicyName</span></span> | <span data-ttu-id="42764-172">La identidad de la directiva</span><span class="sxs-lookup"><span data-stu-id="42764-172">The identity of the policy</span></span> |
||

<span data-ttu-id="42764-173">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="42764-173">For example:</span></span>

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName CPH -Identity user@contoso.com 
```

<span data-ttu-id="42764-174">Puede quitar una directiva de un usuario concediendo la $Null directiva como se muestra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="42764-174">You can remove a policy from a user by granting the $Null policy as shown in the next example:</span></span>

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName $Null -Identity user@contoso.com 
```

### <a name="register-an-application-for-the-sba-with-azure-active-directory"></a><span data-ttu-id="42764-175">Registrar una aplicación para el SBA con Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="42764-175">Register an application for the SBA with Azure Active Directory</span></span>

<span data-ttu-id="42764-176">Para permitir que los distintos SBA usados dentro del espacio empresarial puedan leer los datos necesarios de Microsoft 365, debe registrar una aplicación para el SBA con Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="42764-176">To allow different SBAs used within your tenant to read required data from Microsoft 365, you need to register an application for the SBA with Azure Active Directory.</span></span> 

<span data-ttu-id="42764-177">Para obtener más información sobre el registro de aplicaciones, vea lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="42764-177">For more information about application registration, see the following:</span></span>

- [<span data-ttu-id="42764-178">Desarrollar aplicaciones de línea de negocio para Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="42764-178">Develop line-of-business apps for Azure Active Directory</span></span>](/azure/active-directory/manage-apps/developer-guidance-for-integrating-applications)

- <span data-ttu-id="42764-179">[Registre una aplicación con la Plataforma de identidad de Microsoft](/azure/active-directory/develop/quickstart-register-app).</span><span class="sxs-lookup"><span data-stu-id="42764-179">[Register an application with the Microsoft identity platform](/azure/active-directory/develop/quickstart-register-app).</span></span>  

<span data-ttu-id="42764-180">Solo necesita registrar una aplicación para que la usen todos los SBA en el espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="42764-180">You only need to register one application for use by all the SBAs in your tenant.</span></span> 

<span data-ttu-id="42764-181">Para el registro de SBA, necesita los siguientes valores creados por el registro:</span><span class="sxs-lookup"><span data-stu-id="42764-181">For the SBA registration, you need the following values created by the registration:</span></span> 

- <span data-ttu-id="42764-182">Id. de aplicación (cliente)</span><span class="sxs-lookup"><span data-stu-id="42764-182">Application (client) ID</span></span> 
- <span data-ttu-id="42764-183">Secreto del cliente</span><span class="sxs-lookup"><span data-stu-id="42764-183">Client secret</span></span> 

<span data-ttu-id="42764-184">Para la aplicación SBA, tenga en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="42764-184">For the SBA application, keep the following in mind:</span></span> 

- <span data-ttu-id="42764-185">El nombre puede ser lo que decida.</span><span class="sxs-lookup"><span data-stu-id="42764-185">The name can be whatever you decide.</span></span>  
- <span data-ttu-id="42764-186">Tipos de cuenta admitidos = Solo cuenta en este directorio de la organización.</span><span class="sxs-lookup"><span data-stu-id="42764-186">Supported account types = Account in this organizational directory only.</span></span> 
- <span data-ttu-id="42764-187">Uri de redirección web = https://login.microsoftonline.com/common/oauth2/nativeclient .</span><span class="sxs-lookup"><span data-stu-id="42764-187">The Web Redirect Uri = https://login.microsoftonline.com/common/oauth2/nativeclient.</span></span>
- <span data-ttu-id="42764-188">Tokens de concesión implícitos = tokens de Access y tokens de id.</span><span class="sxs-lookup"><span data-stu-id="42764-188">Implicit grant tokens = Access tokens and ID tokens.</span></span> 
- <span data-ttu-id="42764-189">Permisos de api = Skype y Teams de acceso de administrador de inquilinos -> de aplicación de inquilinos -> application_access_custom_sba_appliance.</span><span class="sxs-lookup"><span data-stu-id="42764-189">API permissions = Skype and Teams Tenant Admin Access -> Application permissions -> application_access_custom_sba_appliance.</span></span>
- <span data-ttu-id="42764-190">Secreto del cliente: puede usar cualquier descripción y expiración.</span><span class="sxs-lookup"><span data-stu-id="42764-190">Client secret: you can use any description and expiration.</span></span> 
- <span data-ttu-id="42764-191">Recuerde copiar el secreto del cliente inmediatamente después de crearlo.</span><span class="sxs-lookup"><span data-stu-id="42764-191">Remember to copy the client secret immediately after creating it.</span></span> 
- <span data-ttu-id="42764-192">El id. de aplicación (cliente) se muestra en la pestaña Información general.</span><span class="sxs-lookup"><span data-stu-id="42764-192">The Application (client) ID is shown on the Overview tab.</span></span>

<span data-ttu-id="42764-193">A continuación, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="42764-193">Then follow these steps:</span></span>

1. <span data-ttu-id="42764-194">Registre la aplicación.</span><span class="sxs-lookup"><span data-stu-id="42764-194">Register the application.</span></span>
2. <span data-ttu-id="42764-195">Establezca los tokens de concesión implícitos.</span><span class="sxs-lookup"><span data-stu-id="42764-195">Set the implicit grant tokens.</span></span>
3. <span data-ttu-id="42764-196">Establezca los permisos de la API.</span><span class="sxs-lookup"><span data-stu-id="42764-196">Set the API permissions.</span></span>
4. <span data-ttu-id="42764-197">Cree el secreto del cliente.</span><span class="sxs-lookup"><span data-stu-id="42764-197">Create the client secret.</span></span>


## <a name="session-border-controller-configuration"></a><span data-ttu-id="42764-198">Configuración del controlador de borde de sesión</span><span class="sxs-lookup"><span data-stu-id="42764-198">Session Border Controller configuration</span></span> 

<span data-ttu-id="42764-199">Para obtener instrucciones paso a paso sobre cómo configurar el controlador de borde de sesión con el dispositivo de sucursal con supervivencia incrustado, consulte la documentación proporcionada por el proveedor de SBC:</span><span class="sxs-lookup"><span data-stu-id="42764-199">For step-by-step guidance on how to configure your Session Border Controller with the embedded Survivable Branch Appliance, see the documentation provided by your SBC vendor:</span></span> 

- [<span data-ttu-id="42764-200">AudioCodes</span><span class="sxs-lookup"><span data-stu-id="42764-200">AudioCodes</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-survivable-branch-appliances)

- [<span data-ttu-id="42764-201">Cinta de opciones</span><span class="sxs-lookup"><span data-stu-id="42764-201">Ribbon</span></span>](https://support.sonus.net/pages/viewpage.action?pageId=248644034)

- [<span data-ttu-id="42764-202">Oracle</span><span class="sxs-lookup"><span data-stu-id="42764-202">Oracle</span></span>](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams) 

- [<span data-ttu-id="42764-203">TE-Systems</span><span class="sxs-lookup"><span data-stu-id="42764-203">TE-Systems</span></span>](https://www.anynode.de/microsoft-teams-sba/)

## <a name="reporting-issues"></a><span data-ttu-id="42764-204">Problemas de informes</span><span class="sxs-lookup"><span data-stu-id="42764-204">Reporting issues</span></span>

<span data-ttu-id="42764-205">Informe de cualquier problema a la organización de soporte técnico de su proveedor de SBC.</span><span class="sxs-lookup"><span data-stu-id="42764-205">Report any issues to your SBC vendor's support organization.</span></span> <span data-ttu-id="42764-206">Al informar del problema, indique que tiene un dispositivo de sucursal con funciones de supervivencia configurado.</span><span class="sxs-lookup"><span data-stu-id="42764-206">When reporting the issue, indicate that you have a configured Survivable Branch Appliance.</span></span>

## <a name="known-issues"></a><span data-ttu-id="42764-207">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="42764-207">Known issues</span></span>

- <span data-ttu-id="42764-208">Al agregar nuevos dispositivos de sucursales con funciones de supervivencia, puede tardar algún tiempo antes de poder usarlos en directivas de aplicación de sucursal con funciones de supervivencia.</span><span class="sxs-lookup"><span data-stu-id="42764-208">When you add new Survivable Branch Appliances, it might take some time before you can use them in Survivable Branch Appliance policies.</span></span>

- <span data-ttu-id="42764-209">Al asignar una directiva de aplicación de sucursal con funciones de supervivencia a un usuario, puede que el SBA se muestra en el resultado de Get-CsOnlineUser.</span><span class="sxs-lookup"><span data-stu-id="42764-209">When you assign a Survivable Branch Appliance policy to a user, it might take some time before the SBA is shown in the output of Get-CsOnlineUser.</span></span> 

- <span data-ttu-id="42764-210">No se realiza la búsqueda inversa de números en contactos de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="42764-210">Reverse number lookup against Azure AD Contacts is not performed.</span></span> 

- <span data-ttu-id="42764-211">El SBA no admite la configuración de reenvío de llamadas.</span><span class="sxs-lookup"><span data-stu-id="42764-211">The SBA does not support call forwarding settings.</span></span> 

- <span data-ttu-id="42764-212">No se admite realizar una llamada de emergencia a un número de emergencia configurado para llamadas de emergencia dinámicas (E911).</span><span class="sxs-lookup"><span data-stu-id="42764-212">Making an emergency call to an emergency number configured for dynamic emergency calling (E911) is not supported.</span></span>
