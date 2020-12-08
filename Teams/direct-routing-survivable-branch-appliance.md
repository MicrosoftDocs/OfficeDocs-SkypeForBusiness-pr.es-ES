---
title: Enrutamiento directo SBA
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
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
description: Obtenga más información sobre el enrutamiento directo, como la configuración, las decisiones básicas de implementación necesarias y las consideraciones de enrutamiento de voz.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: a9e64dc908bafdd63b17e22716e76c4f04df1409
ms.sourcegitcommit: f122c078b6458754500f3cc68086d6ccfa62d183
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/08/2020
ms.locfileid: "49588608"
---
# <a name="survivable-branch-appliance-sba-for-direct-routing---public-preview"></a><span data-ttu-id="389f0-103">Dispositivo de rama superviviente (SBA) para enrutamiento directo: vista previa pública</span><span class="sxs-lookup"><span data-stu-id="389f0-103">Survivable Branch Appliance (SBA) for Direct Routing - Public Preview</span></span>


> [!NOTE]
> <span data-ttu-id="389f0-104">Esta es una versión preliminar pública.</span><span class="sxs-lookup"><span data-stu-id="389f0-104">This is a public preview release.</span></span>

<span data-ttu-id="389f0-105">Ocasionalmente, un sitio del cliente que usa enrutamiento directo para conectarse a Microsoft Phone System puede experimentar una interrupción de Internet.</span><span class="sxs-lookup"><span data-stu-id="389f0-105">Occasionally, a customer site using Direct Routing to connect to Microsoft Phone System may experience an internet outage.</span></span>

<span data-ttu-id="389f0-106">Supongamos que el sitio del cliente, denominado una rama, no puede conectarse temporalmente a la nube de Microsoft a través del enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="389f0-106">Assume that the customer site--called a branch--temporarily cannot connect to the Microsoft cloud through Direct Routing.</span></span> <span data-ttu-id="389f0-107">Sin embargo, la intranet dentro de la rama sigue siendo plenamente funcional y los usuarios pueden conectarse al controlador de borde (SBC) de sesión que proporciona conectividad RTC.</span><span class="sxs-lookup"><span data-stu-id="389f0-107">However, the intranet inside the branch is still fully functional and users can connect to the Session Border Controller (SBC) that is providing PSTN connectivity.</span></span>

<span data-ttu-id="389f0-108">En este artículo se describe cómo usar un dispositivo de rama con la supervivencia (SBA) para habilitar el sistema de teléfono de Microsoft para seguir realizando y recibiendo llamadas de red telefónica conmutada (RTC) en caso de interrupción.</span><span class="sxs-lookup"><span data-stu-id="389f0-108">This article describes how to use a Survivable Branch Appliance (SBA) to enable Microsoft Phone System to continue to make and receive Public Switched Telephone Network (PSTN) calls in the case of an outage.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="389f0-109">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="389f0-109">Prerequisites</span></span>

<span data-ttu-id="389f0-110">SBA es un código distribuible proporcionado por Microsoft a los proveedores de SBC que, a continuación, Incruste el código en el firmware de su SBCs.</span><span class="sxs-lookup"><span data-stu-id="389f0-110">The SBA is distributable code provided by Microsoft to SBC vendors who then embed the code into the firmware of their SBCs.</span></span> 

<span data-ttu-id="389f0-111">Para obtener el firmware más reciente del controlador de borde de la sesión con el dispositivo de sucursal insertado, póngase en contacto con el proveedor de SBC.</span><span class="sxs-lookup"><span data-stu-id="389f0-111">To get the latest Session Border Controller firmware with the embedded Survivable Branch Appliance,  contact your SBC vendor.</span></span> <span data-ttu-id="389f0-112">Además, se requiere lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="389f0-112">In addition, the following is required:</span></span>

- <span data-ttu-id="389f0-113">Es necesario configurar la SBC para la omisión de medios para asegurarse de que el cliente de Microsoft Teams del sitio de la sucursal pueda hacer que el contenido multimedia fluya directamente con el SBC.</span><span class="sxs-lookup"><span data-stu-id="389f0-113">The SBC needs to be configured for Media Bypass to ensure that the Microsoft Teams client in the branch site can have media flowing directly with the SBC.</span></span> 

- <span data-ttu-id="389f0-114">TLS 1.2 debe estar habilitado en el sistema operativo VM de SBA.</span><span class="sxs-lookup"><span data-stu-id="389f0-114">TLS1.2 should be enabled on the SBA VM OS.</span></span>

## <a name="supported-teams-clients"></a><span data-ttu-id="389f0-115">Clientes de equipos compatibles</span><span class="sxs-lookup"><span data-stu-id="389f0-115">Supported Teams clients</span></span>

<span data-ttu-id="389f0-116">La característica SBA se admite en los siguientes clientes de Microsoft Teams:</span><span class="sxs-lookup"><span data-stu-id="389f0-116">The SBA feature is supported on the following Microsoft Teams clients:</span></span> 

- <span data-ttu-id="389f0-117">Microsoft Teams escritorio de Windows</span><span class="sxs-lookup"><span data-stu-id="389f0-117">Microsoft Teams Windows desktop</span></span> 

- <span data-ttu-id="389f0-118">Escritorio de Microsoft Teams macOS</span><span class="sxs-lookup"><span data-stu-id="389f0-118">Microsoft Teams macOS desktop</span></span> 

## <a name="how-it-works"></a><span data-ttu-id="389f0-119">Cómo funciona</span><span class="sxs-lookup"><span data-stu-id="389f0-119">How it works</span></span>

<span data-ttu-id="389f0-120">Durante una interrupción de Internet, el cliente de Teams debe cambiar a SBA automáticamente y las llamadas en curso deben continuar sin interrupciones.</span><span class="sxs-lookup"><span data-stu-id="389f0-120">During an internet outage, the Teams client should switch to the SBA automatically, and ongoing calls should continue with no interruptions.</span></span> <span data-ttu-id="389f0-121">El usuario no necesita realizar ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="389f0-121">No action is required from the user.</span></span> <span data-ttu-id="389f0-122">En cuanto el cliente del equipo detecte que Internet está en marcha y que se han finalizado las llamadas salientes, el cliente revertirá al modo de funcionamiento normal y se conectará a otros servicios de Teams.</span><span class="sxs-lookup"><span data-stu-id="389f0-122">As soon as the Teams client detects that the internet is up and any outgoing calls are finished, the client will fall back to normal operation mode and connect to other Teams services.</span></span> <span data-ttu-id="389f0-123">SBA cargará los registros de datos de llamadas recopilados en la nube y el historial de llamadas se actualizará para que esta información esté disponible para su revisión por el administrador de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="389f0-123">The SBA will upload collected Call Data Records to the cloud and call history will be updated so that this information is available for review by the tenant administrator.</span></span> 

<span data-ttu-id="389f0-124">Cuando el cliente de Microsoft Teams está en modo sin conexión, están disponibles las siguientes funciones relacionadas con la llamada:</span><span class="sxs-lookup"><span data-stu-id="389f0-124">When the Microsoft Teams client is in offline mode, the following calling-related functionality is available:</span></span> 

- <span data-ttu-id="389f0-125">Hacer llamadas RTC a través de SBA/SBC local con el flujo de medios a través de SBC.</span><span class="sxs-lookup"><span data-stu-id="389f0-125">Making PSTN calls via local SBA/SBC with media flowing through the SBC.</span></span>

- <span data-ttu-id="389f0-126">Recepción de llamadas RTC a través de SBA/SBC local con contenido multimedia que fluye por el SBC.</span><span class="sxs-lookup"><span data-stu-id="389f0-126">Receiving PSTN calls via local SBA/SBC with media flowing through the SBC.</span></span> 

- <span data-ttu-id="389f0-127">Suspensión y reanudación de llamadas RTC.</span><span class="sxs-lookup"><span data-stu-id="389f0-127">Hold and Resume of PSTN calls.</span></span>

## <a name="configuration"></a><span data-ttu-id="389f0-128">Configuración</span><span class="sxs-lookup"><span data-stu-id="389f0-128">Configuration</span></span>

<span data-ttu-id="389f0-129">Para que la característica SBA funcione, el cliente de Teams debe saber qué SBAs están disponibles en cada sitio de la sucursal y qué SBAs están asignados a los usuarios de ese sitio.</span><span class="sxs-lookup"><span data-stu-id="389f0-129">For the SBA feature to work, the Teams client needs to know which SBAs are available in each branch site, and which SBAs are assigned to the users in that site.</span></span> <span data-ttu-id="389f0-130">Los pasos de configuración son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="389f0-130">The configuration steps are as follows:</span></span>

1. <span data-ttu-id="389f0-131">Cree el SBAs.</span><span class="sxs-lookup"><span data-stu-id="389f0-131">Create the SBAs.</span></span>
2. <span data-ttu-id="389f0-132">Crear la política de superviviente de las sucursales de Teams.</span><span class="sxs-lookup"><span data-stu-id="389f0-132">Create the Teams branch survivability policy.</span></span>
3. <span data-ttu-id="389f0-133">Asignar la Directiva a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="389f0-133">Assign the policy to users.</span></span>
4. <span data-ttu-id="389f0-134">Registre una aplicación para SBA con Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="389f0-134">Register an application for the SBA with Azure Active Directory.</span></span>

<span data-ttu-id="389f0-135">Toda la configuración se realiza con los cmdlets de PowerShell de Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="389f0-135">All configuration is done by using Skype for Business Online PowerShell cmdlets.</span></span> <span data-ttu-id="389f0-136">(El centro de administración de equipos aún no admite la característica de enrutamiento directo de SBA).</span><span class="sxs-lookup"><span data-stu-id="389f0-136">(The Teams admin center does not yet support the Direct Routing SBA feature.)</span></span> 

<span data-ttu-id="389f0-137">Para obtener información sobre la configuración de SBC, con vínculos a la documentación de proveedores de SBC, consulte Configuración del controlador de borde de sesión al final de este artículo.</span><span class="sxs-lookup"><span data-stu-id="389f0-137">(For information on configuring the SBC, with links to SBC vendor documentation, see Session Border Controller configuration at the end of this article.)</span></span>

### <a name="create-the-sbas"></a><span data-ttu-id="389f0-138">Crear la SBAs</span><span class="sxs-lookup"><span data-stu-id="389f0-138">Create the SBAs</span></span>

<span data-ttu-id="389f0-139">Para crear la SBAs, usará el cmdlet New-CsTeamsSurvivableBranchAppliance.</span><span class="sxs-lookup"><span data-stu-id="389f0-139">To create the SBAs, you will use the New-CsTeamsSurvivableBranchAppliance cmdlet.</span></span> <span data-ttu-id="389f0-140">Este cmdlet tiene los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="389f0-140">This cmdlet has has the following parameters:</span></span>

| <span data-ttu-id="389f0-141">Parámetro</span><span class="sxs-lookup"><span data-stu-id="389f0-141">Parameter</span></span>| <span data-ttu-id="389f0-142">Descripción</span><span class="sxs-lookup"><span data-stu-id="389f0-142">Description</span></span> |
| :------------|:-------|
| <span data-ttu-id="389f0-143">Identity</span><span class="sxs-lookup"><span data-stu-id="389f0-143">Identity</span></span>  | <span data-ttu-id="389f0-144">FQDN de la SBA</span><span class="sxs-lookup"><span data-stu-id="389f0-144">The FQDN of the SBA</span></span>  |
| <span data-ttu-id="389f0-145">Fqdn</span><span class="sxs-lookup"><span data-stu-id="389f0-145">Fqdn</span></span> | <span data-ttu-id="389f0-146">FQDN de la SBA</span><span class="sxs-lookup"><span data-stu-id="389f0-146">The FQDN of the SBA</span></span> |
| <span data-ttu-id="389f0-147">Sitio</span><span class="sxs-lookup"><span data-stu-id="389f0-147">Site</span></span> | <span data-ttu-id="389f0-148">El TenantNetworkSite donde se encuentra la SBA</span><span class="sxs-lookup"><span data-stu-id="389f0-148">The TenantNetworkSite where the SBA is located</span></span> |
| <span data-ttu-id="389f0-149">Descripción</span><span class="sxs-lookup"><span data-stu-id="389f0-149">Description</span></span> | <span data-ttu-id="389f0-150">Formato de texto libre</span><span class="sxs-lookup"><span data-stu-id="389f0-150">Free format text</span></span> |
|||

<span data-ttu-id="389f0-151">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="389f0-151">For example:</span></span>

``` powershell
C:\> New-CsTeamsSurvivableBranchAppliance  -Fqdn sba1.contoso.dk -Description "SBA 1" 
Identity    : sba1.contoso.com 
Fqdn        : sba1.contoso.com 
Site        : 
Description : SBA 1 
```

### <a name="create-the-teams-branch-survivability-policy"></a><span data-ttu-id="389f0-152">Crear la política de la supervivencia de las sucursales de Teams</span><span class="sxs-lookup"><span data-stu-id="389f0-152">Create the Teams Branch Survivability Policy</span></span> 

<span data-ttu-id="389f0-153">Para crear una directiva, use el cmdlet New-CsTeamsSurvivableBranchAppliancePolicy.</span><span class="sxs-lookup"><span data-stu-id="389f0-153">To create a policy, you use the New-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span></span> <span data-ttu-id="389f0-154">Este cmdlet tiene los siguientes parámetros.</span><span class="sxs-lookup"><span data-stu-id="389f0-154">This cmdlet has the following parameters.</span></span> <span data-ttu-id="389f0-155">Tenga en cuenta que la Directiva puede contener uno o varios SBAs.</span><span class="sxs-lookup"><span data-stu-id="389f0-155">Note that the policy can contain one or more SBAs.</span></span>

| <span data-ttu-id="389f0-156">Parámetro</span><span class="sxs-lookup"><span data-stu-id="389f0-156">Parameter</span></span>| <span data-ttu-id="389f0-157">Descripción</span><span class="sxs-lookup"><span data-stu-id="389f0-157">Description</span></span> |
| :------------|:-------|
| <span data-ttu-id="389f0-158">Identity</span><span class="sxs-lookup"><span data-stu-id="389f0-158">Identity</span></span> | <span data-ttu-id="389f0-159">La identidad de la Directiva</span><span class="sxs-lookup"><span data-stu-id="389f0-159">The identity of the policy</span></span> |
| <span data-ttu-id="389f0-160">BranchApplianceFqdns</span><span class="sxs-lookup"><span data-stu-id="389f0-160">BranchApplianceFqdns</span></span>  | <span data-ttu-id="389f0-161">El FQDN de la SBA (s) del sitio</span><span class="sxs-lookup"><span data-stu-id="389f0-161">The FQDN of the SBA(s) in the site</span></span> |
||

<span data-ttu-id="389f0-162">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="389f0-162">For example:</span></span>

``` powershell
C:\> new-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns "sba1.contoso.com","sba2.contoso.com" 
Identity             : Tag:CPH 
BranchApplianceFqdns : {sba1.contoso.dk, sba2.contoso.com} 
```

<span data-ttu-id="389f0-163">Puede Agregar o quitar SBAs de una Directiva mediante el cmdlet Set-CsTeamsSurvivableBranchAppliancePolicy.</span><span class="sxs-lookup"><span data-stu-id="389f0-163">You can add or remove SBAs from a policy by using the Set-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span></span> <span data-ttu-id="389f0-164">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="389f0-164">For example:</span></span> 

``` powershell
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{remove="sba1.contoso.com"} 
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{add="sba1.contoso.com"} 
```

### <a name="assign-a-policy-to-a-user"></a><span data-ttu-id="389f0-165">Asignar una directiva a un usuario</span><span class="sxs-lookup"><span data-stu-id="389f0-165">Assign a policy to a user</span></span>

<span data-ttu-id="389f0-166">Para asignar la Directiva a usuarios individuales, usará el cmdlet Grant-CsTeamsSurvivableBranchAppliancePolicy.</span><span class="sxs-lookup"><span data-stu-id="389f0-166">To assign the policy to individual users, you will use the Grant-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span></span> <span data-ttu-id="389f0-167">Este cmdlet tiene los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="389f0-167">This cmdlet has the following parameters:</span></span>

| <span data-ttu-id="389f0-168">Parámetro</span><span class="sxs-lookup"><span data-stu-id="389f0-168">Parameter</span></span>| <span data-ttu-id="389f0-169">Descripción</span><span class="sxs-lookup"><span data-stu-id="389f0-169">Description</span></span> |
| :------------|:-------|
| <span data-ttu-id="389f0-170">Identity</span><span class="sxs-lookup"><span data-stu-id="389f0-170">Identity</span></span> | <span data-ttu-id="389f0-171">La identidad del usuario</span><span class="sxs-lookup"><span data-stu-id="389f0-171">The identity of the user</span></span> |
| <span data-ttu-id="389f0-172">PolicyName</span><span class="sxs-lookup"><span data-stu-id="389f0-172">PolicyName</span></span> | <span data-ttu-id="389f0-173">La identidad de la Directiva</span><span class="sxs-lookup"><span data-stu-id="389f0-173">The identity of the policy</span></span> |
||

<span data-ttu-id="389f0-174">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="389f0-174">For example:</span></span>

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName CPH -Identity user@contoso.com 
```

<span data-ttu-id="389f0-175">Para quitar una directiva de un usuario, puede conceder la $Null Directiva tal como se muestra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="389f0-175">You can remove a policy from a user by granting the $Null policy as shown in the next example:</span></span>

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName $Null -Identity user@contoso.com 
```

### <a name="register-an-application-for-the-sba-with-azure-active-directory"></a><span data-ttu-id="389f0-176">Registrar una aplicación para SBA con Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="389f0-176">Register an application for the SBA with Azure Active Directory</span></span>

<span data-ttu-id="389f0-177">Para permitir que diferentes SBAs usen en su espacio empresarial para leer los datos necesarios de Microsoft 365, debe registrar una aplicación para SBA con Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="389f0-177">To allow different SBAs used within your tenant to read required data from Microsoft 365, you need to register an application for the SBA with Azure Active Directory.</span></span> 

<span data-ttu-id="389f0-178">Para obtener más información sobre el registro de aplicaciones, vea lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="389f0-178">For more information about application registration, see the following:</span></span>

- [<span data-ttu-id="389f0-179">Desarrollar aplicaciones de línea de negocio para Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="389f0-179">Develop line-of-business apps for Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/manage-apps/developer-guidance-for-integrating-applications)

- <span data-ttu-id="389f0-180">[Registrar una aplicación con la plataforma de identidades de Microsoft](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).</span><span class="sxs-lookup"><span data-stu-id="389f0-180">[Register an application with the Microsoft identity platform](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).</span></span>  

<span data-ttu-id="389f0-181">Solo necesita registrar una aplicación para que la usen todos los SBAs de su inquilino.</span><span class="sxs-lookup"><span data-stu-id="389f0-181">You only need to register one application for use by all the SBAs in your tenant.</span></span> 

<span data-ttu-id="389f0-182">Para el registro de SBA, necesita los siguientes valores creados por el registro:</span><span class="sxs-lookup"><span data-stu-id="389f0-182">For the SBA registration, you need the following values created by the registration:</span></span> 

- <span data-ttu-id="389f0-183">IDENTIFICADOR de la aplicación (cliente)</span><span class="sxs-lookup"><span data-stu-id="389f0-183">Application (client) ID</span></span> 
- <span data-ttu-id="389f0-184">Secreto de cliente</span><span class="sxs-lookup"><span data-stu-id="389f0-184">Client secret</span></span> 

<span data-ttu-id="389f0-185">Para la aplicación SBA, tenga en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="389f0-185">For the SBA application, keep the following in mind:</span></span> 

- <span data-ttu-id="389f0-186">El nombre puede ser el que usted decida.</span><span class="sxs-lookup"><span data-stu-id="389f0-186">The name can be whatever you decide.</span></span>  
- <span data-ttu-id="389f0-187">Tipos de cuenta admitidos = cuenta solo en este directorio de organización.</span><span class="sxs-lookup"><span data-stu-id="389f0-187">Supported account types = Account in this organizational directory only.</span></span> 
- <span data-ttu-id="389f0-188">El URI de redireccionamiento web = https://login.microsoftonline.com/common/oauth2/nativeclient .</span><span class="sxs-lookup"><span data-stu-id="389f0-188">The Web Redirect Uri = https://login.microsoftonline.com/common/oauth2/nativeclient.</span></span>
- <span data-ttu-id="389f0-189">Tokens de concesión implícita = tokens de acceso y tokens de identificador.</span><span class="sxs-lookup"><span data-stu-id="389f0-189">Implicit grant tokens = Access tokens and ID tokens.</span></span> 
- <span data-ttu-id="389f0-190">Permisos de API = permisos de administrador de inquilinos de Skype y Teams-> de permisos de aplicaciones-> application_access_custom_sba_appliance.</span><span class="sxs-lookup"><span data-stu-id="389f0-190">API permissions = Skype and Teams Tenant Admin Access -> Application permissions -> application_access_custom_sba_appliance.</span></span>
- <span data-ttu-id="389f0-191">Secreto de cliente: puede usar la descripción y la expiración.</span><span class="sxs-lookup"><span data-stu-id="389f0-191">Client secret: you can use any description and expiration.</span></span> 
- <span data-ttu-id="389f0-192">Recuerde copiar el secreto de cliente inmediatamente después de crearlo.</span><span class="sxs-lookup"><span data-stu-id="389f0-192">Remember to copy the client secret immediately after creating it.</span></span> 
- <span data-ttu-id="389f0-193">El identificador de la aplicación (cliente) se muestra en la ficha Descripción general.</span><span class="sxs-lookup"><span data-stu-id="389f0-193">The Application (client) ID is shown on the Overview tab.</span></span>

<span data-ttu-id="389f0-194">A continuación, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="389f0-194">Then follow these steps:</span></span>

1. <span data-ttu-id="389f0-195">Registrar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="389f0-195">Register the application.</span></span>
2. <span data-ttu-id="389f0-196">Establezca los tokens de concesión implícitos.</span><span class="sxs-lookup"><span data-stu-id="389f0-196">Set the implicit grant tokens.</span></span>
3. <span data-ttu-id="389f0-197">Establezca los permisos de la API.</span><span class="sxs-lookup"><span data-stu-id="389f0-197">Set the API permissions.</span></span>
4. <span data-ttu-id="389f0-198">Crear el secreto de cliente.</span><span class="sxs-lookup"><span data-stu-id="389f0-198">Create the client secret.</span></span>


## <a name="session-border-controller-configuration"></a><span data-ttu-id="389f0-199">Configuración del controlador de borde de sesión</span><span class="sxs-lookup"><span data-stu-id="389f0-199">Session Border Controller configuration</span></span> 

<span data-ttu-id="389f0-200">Para obtener instrucciones paso a paso sobre cómo configurar el controlador de borde de sesión con el dispositivo de sucursal incrustado, consulte la documentación proporcionada por el proveedor de SBC:</span><span class="sxs-lookup"><span data-stu-id="389f0-200">For step-by-step guidance on how to configure your Session Border Controller with the embedded Survivable Branch Appliance, see the documentation provided by your SBC vendor:</span></span> 

- [<span data-ttu-id="389f0-201">AudioCodes</span><span class="sxs-lookup"><span data-stu-id="389f0-201">AudioCodes</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-survivable-branch-appliances)

- [<span data-ttu-id="389f0-202">Lazo</span><span class="sxs-lookup"><span data-stu-id="389f0-202">Ribbon</span></span>](https://support.sonus.net/pages/viewpage.action?pageId=248644034)

- [<span data-ttu-id="389f0-203">Oracle</span><span class="sxs-lookup"><span data-stu-id="389f0-203">Oracle</span></span>](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams) 

- [<span data-ttu-id="389f0-204">TE-sistemas</span><span class="sxs-lookup"><span data-stu-id="389f0-204">TE-Systems</span></span>](https://www.anynode.de/microsoft-teams-sba/)

## <a name="reporting-issues"></a><span data-ttu-id="389f0-205">Problemas de informes</span><span class="sxs-lookup"><span data-stu-id="389f0-205">Reporting issues</span></span>

<span data-ttu-id="389f0-206">Informe de cualquier problema a la organización de soporte técnico de su proveedor de SBC.</span><span class="sxs-lookup"><span data-stu-id="389f0-206">Report any issues to your SBC vendor's support organization.</span></span> <span data-ttu-id="389f0-207">Cuando informe sobre el problema, indique que tiene un equipo de sucursales configurado.</span><span class="sxs-lookup"><span data-stu-id="389f0-207">When reporting the issue, indicate that you have a configured Survivable Branch Appliance.</span></span>

## <a name="known-issues"></a><span data-ttu-id="389f0-208">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="389f0-208">Known issues</span></span>

- <span data-ttu-id="389f0-209">Cuando se agregan nuevos equipos de sucursales que se pueden llevar a cabo, es posible que tarden unos minutos en usarlos en directivas de los equipos supervivientes.</span><span class="sxs-lookup"><span data-stu-id="389f0-209">When you add new Survivable Branch Appliances, it might take some time before you can use them in Survivable Branch Appliance policies.</span></span>

- <span data-ttu-id="389f0-210">Cuando se asigna a un usuario una directiva de equipo de sucursal con la supervivencia, es posible que tarde un tiempo en mostrarse en el resultado de Get-CsOnlineUser.</span><span class="sxs-lookup"><span data-stu-id="389f0-210">When you assign a Survivable Branch Appliance policy to a user, it might take some time before the SBA is shown in the output of Get-CsOnlineUser.</span></span> 

- <span data-ttu-id="389f0-211">No se realiza la búsqueda de números invertidas con los contactos de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="389f0-211">Reverse number lookup against Azure AD Contacts is not performed.</span></span> 

- <span data-ttu-id="389f0-212">SBA no admite la configuración del desvío de llamadas.</span><span class="sxs-lookup"><span data-stu-id="389f0-212">The SBA does not support call forwarding settings.</span></span> 

- <span data-ttu-id="389f0-213">No es posible realizar una llamada de emergencia a un número de emergencia configurado para llamadas de emergencia dinámicas (E911).</span><span class="sxs-lookup"><span data-stu-id="389f0-213">Making an emergency call to an emergency number configured for dynamic emergency calling (E911) is not supported.</span></span>

- <span data-ttu-id="389f0-214">El resultado de Get-CsOnlineUser muestra TeamsBranchSurvivabilityPolicy.</span><span class="sxs-lookup"><span data-stu-id="389f0-214">The output of Get-CsOnlineUser shows TeamsBranchSurvivabilityPolicy.</span></span>
