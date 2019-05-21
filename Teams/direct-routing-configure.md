---
title: Configurar el enrutamiento directo
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
appliesto:
- Microsoft Teams
description: Aprenda a configurar el enrutamiento directo de Microsoft Phone System.
ms.openlocfilehash: ce3fff5205a2cb78c1d409ae8595a50c73f70aaf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34290448"
---
# <a name="configure-direct-routing"></a><span data-ttu-id="dd70f-103">Configurar el enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="dd70f-103">Configure Direct Routing</span></span>

> [!Tip]
> <span data-ttu-id="dd70f-104">Vea la siguiente sesión para obtener información sobre las ventajas del enrutamiento directo, cómo planearlo y cómo implementarlo: [enrutamiento directo en Microsoft Teams](https://aka.ms/teams-direct-routing)</span><span class="sxs-lookup"><span data-stu-id="dd70f-104">Watch the following session to learn about the benefits of Direct Routing, how to plan for it, and how to deploy it: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing)</span></span>

<span data-ttu-id="dd70f-105">Si aún no lo ha hecho, lea [planear el enrutamiento directo](direct-routing-plan.md) de los requisitos previos y revisar otros pasos que debe realizar antes de configurar la red del sistema de Microsoft Phone.</span><span class="sxs-lookup"><span data-stu-id="dd70f-105">If you have not already done so, read [Plan Direct Routing](direct-routing-plan.md) for prerequisites and to review other steps you’ll need to take before you configure your Microsoft Phone System network.</span></span> 

<span data-ttu-id="dd70f-106">En este artículo se describe cómo configurar el enrutamiento directo de Microsoft Phone System.</span><span class="sxs-lookup"><span data-stu-id="dd70f-106">This article describes how to configure Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="dd70f-107">Explica cómo emparejar un controlador de borde de sesión (SBC) compatible con el enrutamiento directo y cómo configurar los usuarios de Microsoft Teams para que usen el enrutamiento directo para conectarse a la red de telefonía pública conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="dd70f-107">It details how to pair a supported Session Border Controller (SBC) to Direct Routing and how to configure Microsoft Teams users to use Direct Routing to connect to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="dd70f-108">Para completar los pasos que se explican en este artículo, los administradores deben estar familiarizados con los cmdlets de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dd70f-108">To complete the steps explained in this article, administrators need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="dd70f-109">Para obtener más información sobre cómo usar PowerShell, consulte [configurar el equipo para Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="dd70f-109">For more information about using PowerShell, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 

<span data-ttu-id="dd70f-110">Le recomendamos que confirme que su SBC ya se ha configurado tal y como recomienda su proveedor de SBC:</span><span class="sxs-lookup"><span data-stu-id="dd70f-110">We recommend that you confirm that your SBC has already been configured as recommended by your SBC vendor:</span></span> 

- [<span data-ttu-id="dd70f-111">Documentación de la implementación de AudioCodes</span><span class="sxs-lookup"><span data-stu-id="dd70f-111">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="dd70f-112">Documentación de implementación de comunicaciones de la cinta</span><span class="sxs-lookup"><span data-stu-id="dd70f-112">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)

<span data-ttu-id="dd70f-113">Puede configurar el sistema de Microsoft Phone y permitir que los usuarios usen el enrutamiento directo y, a continuación, configurar Microsoft Teams como el cliente de llamadas preferido completando los siguientes procedimientos:</span><span class="sxs-lookup"><span data-stu-id="dd70f-113">You can configure your Microsoft Phone System and enable users to use Direct Routing, then set up Microsoft Teams as the preferred calling client by completing the following procedures:</span></span> 

- [<span data-ttu-id="dd70f-114">Emparejar el SBC con un sistema telefónico de Microsoft y validar el emparejamiento</span><span class="sxs-lookup"><span data-stu-id="dd70f-114">Pair the SBC with a Microsoft Phone System and validate the pairing</span></span>](#pair-the-sbc-to-direct-routing-service-of-phone-system)
- [<span data-ttu-id="dd70f-115">Habilitar a los usuarios para el servicio de enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="dd70f-115">Enable users for Direct Routing Service</span></span>](#enable-users-for-direct-routing-service)
- [<span data-ttu-id="dd70f-116">Asegúrese de que Microsoft Teams es el cliente de llamadas preferido para los usuarios</span><span class="sxs-lookup"><span data-stu-id="dd70f-116">Ensure that Microsoft Teams is the preferred calling client for the users</span></span>](#set-microsoft-teams-as-the-preferred-calling-client-for-users) 

## <a name="pair-the-sbc-to-the-direct-routing-service-of-phone-system"></a><span data-ttu-id="dd70f-117">Emparejar la SBC al servicio de enrutamiento directo del sistema telefónico</span><span class="sxs-lookup"><span data-stu-id="dd70f-117">Pair the SBC to the Direct Routing Service of Phone System</span></span> 

<span data-ttu-id="dd70f-118">Estos son los tres pasos de alto nivel que permiten conectar, o emparejar, la SBC a la interfaz de enrutamiento directo:</span><span class="sxs-lookup"><span data-stu-id="dd70f-118">The following are the three high-level steps to let you connect, or pair, the SBC to the Direct Routing interface:</span></span> 

- <span data-ttu-id="dd70f-119">Conectarse al centro **de administración de Skype empresarial online** con PowerShell</span><span class="sxs-lookup"><span data-stu-id="dd70f-119">Connect to **Skype for Business Online** admin center using PowerShell</span></span> 
- <span data-ttu-id="dd70f-120">Emparejar la SBC</span><span class="sxs-lookup"><span data-stu-id="dd70f-120">Pair the SBC</span></span> 
- <span data-ttu-id="dd70f-121">Validar el emparejamiento</span><span class="sxs-lookup"><span data-stu-id="dd70f-121">Validate the pairing</span></span> 

### <a name="connect-to-skype-for-business-online-by-using-powershell"></a><span data-ttu-id="dd70f-122">Conectarse a Skype empresarial online con PowerShell</span><span class="sxs-lookup"><span data-stu-id="dd70f-122">Connect to Skype for Business Online by using PowerShell</span></span> 

<span data-ttu-id="dd70f-123">Puede usar una sesión de PowerShell conectada al espacio empresarial para emparejar el SBC a la interfaz de enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="dd70f-123">You can use a PowerShell session connected to the tenant to pair the SBC to the Direct Routing interface.</span></span> <span data-ttu-id="dd70f-124">Para abrir una sesión de PowerShell, siga los pasos descritos en [configurar el equipo para Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="dd70f-124">To open a PowerShell session, please follow the steps outlined in [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 
 
<span data-ttu-id="dd70f-125">Después de establecer una sesión de PowerShell remota, compruebe que puede ver los comandos para administrar la SBC.</span><span class="sxs-lookup"><span data-stu-id="dd70f-125">After you establish a remote PowerShell session, please validate that you can see the commands to manage the SBC.</span></span> <span data-ttu-id="dd70f-126">Para validar los comandos, escriba o copie y pegue lo siguiente en la sesión de PowerShell y presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="dd70f-126">To validate the commands, type or copy/paste in the following in the PowerShell session and press Enter:</span></span> 

```
Get-Command *onlinePSTNGateway*
```

<span data-ttu-id="dd70f-127">El comando devolverá las cuatro funciones mostradas aquí que le permitirán administrar el SBC.</span><span class="sxs-lookup"><span data-stu-id="dd70f-127">Your command will return the four functions shown here that will let you manage the SBC.</span></span> 

<pre>
CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
</pre>   


### <a name="pair-the-sbc-to-the-tenant"></a><span data-ttu-id="dd70f-128">Emparejar el SBC con el inquilino</span><span class="sxs-lookup"><span data-stu-id="dd70f-128">Pair the SBC to the tenant</span></span> 

<span data-ttu-id="dd70f-129">Para emparejar el SBC con el inquilino, en la sesión de PowerShell escriba lo siguiente y presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="dd70f-129">To pair the SBC to the tenant, in the PowerShell session type the following and press Enter:</span></span> 

```
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignallingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true 
```
  > [!NOTE]
  > 1. <span data-ttu-id="dd70f-130">Se recomienda establecer un límite máximo de llamadas en la SBC mediante la información que se puede encontrar en la documentación de SBC.</span><span class="sxs-lookup"><span data-stu-id="dd70f-130">We highly recommend setting a maximum call limit in the SBC, using information that can be found in the SBC documentation.</span></span> <span data-ttu-id="dd70f-131">El límite desencadenará una notificación si el SBC está en el nivel de capacidad.</span><span class="sxs-lookup"><span data-stu-id="dd70f-131">The limit will trigger a notification if the SBC is at the capacity level.</span></span>
  > 2. <span data-ttu-id="dd70f-132">Solo puede emparejar el SBC si la parte de dominio de su FQDN coincide con uno de los dominios registrados en su inquilino \*, excepto. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="dd70f-132">You can only pair the SBC if the domain portion of its FQDN matches one of the domains registered in your tenant, except \*.onmicrosoft.com.</span></span> <span data-ttu-id="dd70f-133">No \*se admite el uso de nombres de dominio. onmicrosoft.com para el nombre FQDN de SBC.</span><span class="sxs-lookup"><span data-stu-id="dd70f-133">Using \*.onmicrosoft.com domain names is not supported for the SBC FQDN name.</span></span> <span data-ttu-id="dd70f-134">Por ejemplo, si tiene dos nombres de dominio:</span><span class="sxs-lookup"><span data-stu-id="dd70f-134">For example, if you have two domain names:</span></span><br/><br/>
  > <span data-ttu-id="dd70f-135">**contoso**. com</span><span class="sxs-lookup"><span data-stu-id="dd70f-135">**contoso**.com</span></span><br/><span data-ttu-id="dd70f-136">**contoso**. onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="dd70f-136">**contoso**.onmicrosoft.com</span></span><br/><br/>
  > <span data-ttu-id="dd70f-137">Para el nombre de SBC, puede usar el nombre sbc.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="dd70f-137">For the SBC name, you can use the name sbc.contoso.com.</span></span> <span data-ttu-id="dd70f-138">Si intenta emparejar la SBC con un nombre SBC. contoso. ABC, el sistema no le permitirá, ya que el dominio no pertenece a este inquilino.</span><span class="sxs-lookup"><span data-stu-id="dd70f-138">If you try to pair the SBC with a name sbc.contoso.abc, the system will not let you, as the domain is not owned by this tenant.</span></span>

```
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignallingPort 5067 -MaxConcurrentSessions 100 
```
<span data-ttu-id="dd70f-139">Devuelve</span><span class="sxs-lookup"><span data-stu-id="dd70f-139">Returns:</span></span>
<pre>
Identity              : sbc.contoso.com 
Fqdn                  : sbc.contoso.com 
SipSignallingPort     : 5067 
FailoverTimeSeconds   : 10 
ForwardCallHistory    : False 
ForwardPai            : False 
SendSipOptions        : True 
MaxConcurrentSessions : 100 
Enabled               : True   
</pre>
<span data-ttu-id="dd70f-140">Hay opciones adicionales que se pueden establecer durante el proceso de emparejamiento.</span><span class="sxs-lookup"><span data-stu-id="dd70f-140">There are additional options that can be set during the pairing process.</span></span> <span data-ttu-id="dd70f-141">En el ejemplo anterior, sin embargo, solo se muestran los parámetros mínimos necesarios.</span><span class="sxs-lookup"><span data-stu-id="dd70f-141">In the previous example, however, only the minimum required parameters are shown.</span></span> 
 
<span data-ttu-id="dd70f-142">En la tabla siguiente se enumeran los parámetros adicionales que se pueden usar en la configuración de parámetros para`New-CsOnlinePstnGateway`</span><span class="sxs-lookup"><span data-stu-id="dd70f-142">The following table lists the additional parameters that you can use in setting parameters for `New-CsOnlinePstnGateway`</span></span>

|<span data-ttu-id="dd70f-143">¿Obligatorio?</span><span class="sxs-lookup"><span data-stu-id="dd70f-143">Required?</span></span>|<span data-ttu-id="dd70f-144">Nombre</span><span class="sxs-lookup"><span data-stu-id="dd70f-144">Name</span></span>|<span data-ttu-id="dd70f-145">Descripción</span><span class="sxs-lookup"><span data-stu-id="dd70f-145">Description</span></span>|<span data-ttu-id="dd70f-146">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="dd70f-146">Default</span></span>|<span data-ttu-id="dd70f-147">Valores posibles</span><span class="sxs-lookup"><span data-stu-id="dd70f-147">Possible values</span></span>|<span data-ttu-id="dd70f-148">Tipo y restricciones</span><span class="sxs-lookup"><span data-stu-id="dd70f-148">Type and restrictions</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="dd70f-149">Sí</span><span class="sxs-lookup"><span data-stu-id="dd70f-149">Yes</span></span>|<span data-ttu-id="dd70f-150">FQDN</span><span class="sxs-lookup"><span data-stu-id="dd70f-150">FQDN</span></span>|<span data-ttu-id="dd70f-151">El nombre FQDN de SBC</span><span class="sxs-lookup"><span data-stu-id="dd70f-151">The FQDN name of the SBC</span></span> |<span data-ttu-id="dd70f-152">Ninguna</span><span class="sxs-lookup"><span data-stu-id="dd70f-152">None</span></span>|<span data-ttu-id="dd70f-153">NoneFQDN nombre, limitar 63 caracteres</span><span class="sxs-lookup"><span data-stu-id="dd70f-153">NoneFQDN name, limit 63 characters</span></span>|<span data-ttu-id="dd70f-154">Cadena, lista de caracteres permitidos y no permitidos en las [convenciones de nomenclatura de Active Directory para equipos, dominios, sitios y unidades organizativas](https://support.microsoft.com/help/909264)</span><span class="sxs-lookup"><span data-stu-id="dd70f-154">String, list of allowed and disallowed characters on [Naming conventions in Active Directory for computers, domains, sites, and OUs](https://support.microsoft.com/help/909264)</span></span>|
|<span data-ttu-id="dd70f-155">No</span><span class="sxs-lookup"><span data-stu-id="dd70f-155">No</span></span>|<span data-ttu-id="dd70f-156">MediaBypass</span><span class="sxs-lookup"><span data-stu-id="dd70f-156">MediaBypass</span></span> |<span data-ttu-id="dd70f-157">El parámetro reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="dd70f-157">The parameter reserved for future use.</span></span> <span data-ttu-id="dd70f-158">El parámetro indicado para SBC admite la omisión de medios y el administrador quiere usarlo.</span><span class="sxs-lookup"><span data-stu-id="dd70f-158">Parameter indicated of the SBC supports Media Bypass and the administrator wants to use it.</span></span>|<span data-ttu-id="dd70f-159">Ninguna</span><span class="sxs-lookup"><span data-stu-id="dd70f-159">None</span></span>|<span data-ttu-id="dd70f-160">True</span><span class="sxs-lookup"><span data-stu-id="dd70f-160">True</span></span><br/><span data-ttu-id="dd70f-161">False</span><span class="sxs-lookup"><span data-stu-id="dd70f-161">False</span></span>|<span data-ttu-id="dd70f-162">Boolean</span><span class="sxs-lookup"><span data-stu-id="dd70f-162">Boolean</span></span>|
|<span data-ttu-id="dd70f-163">Sí</span><span class="sxs-lookup"><span data-stu-id="dd70f-163">Yes</span></span>|<span data-ttu-id="dd70f-164">SipSignallingPort</span><span class="sxs-lookup"><span data-stu-id="dd70f-164">SipSignallingPort</span></span> |<span data-ttu-id="dd70f-165">Puerto de escucha usado para comunicarse con los servicios de enrutamiento directo mediante el protocolo seguridad de la capa de transporte (TLS).</span><span class="sxs-lookup"><span data-stu-id="dd70f-165">Listening port used for communicating with Direct Routing services by using the Transport Layer Security (TLS) protocol.</span></span>|<span data-ttu-id="dd70f-166">Ninguna</span><span class="sxs-lookup"><span data-stu-id="dd70f-166">None</span></span>|<span data-ttu-id="dd70f-167">Cualquier puerto</span><span class="sxs-lookup"><span data-stu-id="dd70f-167">Any port</span></span>|<span data-ttu-id="dd70f-168">0 a 65535</span><span class="sxs-lookup"><span data-stu-id="dd70f-168">0 to 65535</span></span> |
|<span data-ttu-id="dd70f-169">No</span><span class="sxs-lookup"><span data-stu-id="dd70f-169">No</span></span>|<span data-ttu-id="dd70f-170">FailoverTimeSeconds</span><span class="sxs-lookup"><span data-stu-id="dd70f-170">FailoverTimeSeconds</span></span> |<span data-ttu-id="dd70f-171">Cuando se establece en 10 (valor predeterminado), las llamadas salientes que no responden a la puerta de enlace en 10 segundos se enrutan al siguiente tronco disponible; Si no hay más troncos, la llamada se elimina automáticamente.</span><span class="sxs-lookup"><span data-stu-id="dd70f-171">When set to 10 (default value), outbound calls that are not answered by the gateway within 10 seconds are routed to the next available trunk; if there are no additional trunks, then the call is automatically dropped.</span></span> <span data-ttu-id="dd70f-172">En una organización con redes y respuestas de puerta de enlace lentas, esto puede tener como resultado que las llamadas se pierdan innecesariamente.</span><span class="sxs-lookup"><span data-stu-id="dd70f-172">In an organization with slow networks and gateway responses, that could potentially result in calls being dropped unnecessarily.</span></span> <span data-ttu-id="dd70f-173">El valor predeterminado es 10.</span><span class="sxs-lookup"><span data-stu-id="dd70f-173">The default value is 10.</span></span>|<span data-ttu-id="dd70f-174">base10</span><span class="sxs-lookup"><span data-stu-id="dd70f-174">10</span></span>|<span data-ttu-id="dd70f-175">Número</span><span class="sxs-lookup"><span data-stu-id="dd70f-175">Number</span></span>|<span data-ttu-id="dd70f-176">ENT</span><span class="sxs-lookup"><span data-stu-id="dd70f-176">Int</span></span>|
|<span data-ttu-id="dd70f-177">No</span><span class="sxs-lookup"><span data-stu-id="dd70f-177">No</span></span>|<span data-ttu-id="dd70f-178">ForwardCallHistory</span><span class="sxs-lookup"><span data-stu-id="dd70f-178">ForwardCallHistory</span></span> |<span data-ttu-id="dd70f-179">Indica si la información del historial de llamadas se reenviará a través del tronco.</span><span class="sxs-lookup"><span data-stu-id="dd70f-179">Indicates whether call history information will be forwarded through the trunk.</span></span> <span data-ttu-id="dd70f-180">Si está habilitado, el proxy RTC de Office 365 envía dos encabezados: historial-información y referencia.</span><span class="sxs-lookup"><span data-stu-id="dd70f-180">If enabled, the Office 365 PSTN Proxy sends two headers: History-info and Referred-By.</span></span> <span data-ttu-id="dd70f-181">El valor predeterminado es **false** ($false).</span><span class="sxs-lookup"><span data-stu-id="dd70f-181">The default value is **False** ($False).</span></span> |<span data-ttu-id="dd70f-182">False</span><span class="sxs-lookup"><span data-stu-id="dd70f-182">False</span></span>|<span data-ttu-id="dd70f-183">True</span><span class="sxs-lookup"><span data-stu-id="dd70f-183">True</span></span><br/><span data-ttu-id="dd70f-184">False</span><span class="sxs-lookup"><span data-stu-id="dd70f-184">False</span></span>|<span data-ttu-id="dd70f-185">Boolean</span><span class="sxs-lookup"><span data-stu-id="dd70f-185">Boolean</span></span>|
|<span data-ttu-id="dd70f-186">No</span><span class="sxs-lookup"><span data-stu-id="dd70f-186">No</span></span>|<span data-ttu-id="dd70f-187">ForwardPAI</span><span class="sxs-lookup"><span data-stu-id="dd70f-187">ForwardPAI</span></span>|<span data-ttu-id="dd70f-188">Indica si el encabezado P-Asserted-Identity (PAI) se reenviará junto con la llamada.</span><span class="sxs-lookup"><span data-stu-id="dd70f-188">Indicates whether the P-Asserted-Identity (PAI) header will be forwarded along with the call.</span></span> <span data-ttu-id="dd70f-189">El encabezado PAI proporciona un método para comprobar la identidad de la persona que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="dd70f-189">The PAI header provides a way to verify the identity of the caller.</span></span> <span data-ttu-id="dd70f-190">Si Habilitaste, también se enviará el encabezado privacidad: ID.</span><span class="sxs-lookup"><span data-stu-id="dd70f-190">If enabled the Privacy:ID header will also be sent.</span></span> <span data-ttu-id="dd70f-191">El valor predeterminado es **false** ($false).</span><span class="sxs-lookup"><span data-stu-id="dd70f-191">The default value is **False** ($False).</span></span>|<span data-ttu-id="dd70f-192">False</span><span class="sxs-lookup"><span data-stu-id="dd70f-192">False</span></span>|<span data-ttu-id="dd70f-193">True</span><span class="sxs-lookup"><span data-stu-id="dd70f-193">True</span></span><br/><span data-ttu-id="dd70f-194">False</span><span class="sxs-lookup"><span data-stu-id="dd70f-194">False</span></span>|<span data-ttu-id="dd70f-195">Boolean</span><span class="sxs-lookup"><span data-stu-id="dd70f-195">Boolean</span></span>|
|<span data-ttu-id="dd70f-196">No</span><span class="sxs-lookup"><span data-stu-id="dd70f-196">No</span></span>|<span data-ttu-id="dd70f-197">SendSIPOptions</span><span class="sxs-lookup"><span data-stu-id="dd70f-197">SendSIPOptions</span></span> |<span data-ttu-id="dd70f-198">Define si un SBC o no enviará las opciones de SIP.</span><span class="sxs-lookup"><span data-stu-id="dd70f-198">Defines if an SBC will or will not send the SIP options.</span></span> <span data-ttu-id="dd70f-199">Si se deshabilita, la SBC se excluirá del sistema de supervisión y alertas.</span><span class="sxs-lookup"><span data-stu-id="dd70f-199">If disabled, the SBC will be excluded from Monitoring and Alerting system.</span></span> <span data-ttu-id="dd70f-200">Le recomendamos encarecidamente que habilite las opciones de SIP.</span><span class="sxs-lookup"><span data-stu-id="dd70f-200">We highly recommend that you enable SIP options.</span></span> <span data-ttu-id="dd70f-201">El valor predeterminado es **true**.</span><span class="sxs-lookup"><span data-stu-id="dd70f-201">Default value is **True**.</span></span> |<span data-ttu-id="dd70f-202">True</span><span class="sxs-lookup"><span data-stu-id="dd70f-202">True</span></span>|<span data-ttu-id="dd70f-203">True</span><span class="sxs-lookup"><span data-stu-id="dd70f-203">True</span></span><br/><span data-ttu-id="dd70f-204">False</span><span class="sxs-lookup"><span data-stu-id="dd70f-204">False</span></span>|<span data-ttu-id="dd70f-205">Boolean</span><span class="sxs-lookup"><span data-stu-id="dd70f-205">Boolean</span></span>|
|<span data-ttu-id="dd70f-206">No</span><span class="sxs-lookup"><span data-stu-id="dd70f-206">No</span></span>|<span data-ttu-id="dd70f-207">MaxConcurrentSessions</span><span class="sxs-lookup"><span data-stu-id="dd70f-207">MaxConcurrentSessions</span></span> |<span data-ttu-id="dd70f-208">Utilizado por el sistema de alertas.</span><span class="sxs-lookup"><span data-stu-id="dd70f-208">Used by alerting system.</span></span> <span data-ttu-id="dd70f-209">Cuando se establece un valor, el sistema de alertas generará una alerta para el administrador de inquilinos cuando el número de sesión simultánea sea 90% o superior a este valor.</span><span class="sxs-lookup"><span data-stu-id="dd70f-209">When any value is set, the alerting system will generate an alert to the tenant administrator when the number of concurrent session is 90% or higher than this value.</span></span> <span data-ttu-id="dd70f-210">Si el parámetro no se establece, no se generan alertas.</span><span class="sxs-lookup"><span data-stu-id="dd70f-210">If parameter is not set, the alerts are not generated.</span></span> <span data-ttu-id="dd70f-211">Sin embargo, el sistema de supervisión informará de la cantidad de sesiones simultáneas cada 24 horas.</span><span class="sxs-lookup"><span data-stu-id="dd70f-211">However, the monitoring system will report number of concurrent session every 24 hours.</span></span> |<span data-ttu-id="dd70f-212">Valor</span><span class="sxs-lookup"><span data-stu-id="dd70f-212">Null</span></span>|<span data-ttu-id="dd70f-213">Valor</span><span class="sxs-lookup"><span data-stu-id="dd70f-213">Null</span></span><br/><span data-ttu-id="dd70f-214">de 1 a 100.000</span><span class="sxs-lookup"><span data-stu-id="dd70f-214">1 to 100,000</span></span> ||
|<span data-ttu-id="dd70f-215">No</span><span class="sxs-lookup"><span data-stu-id="dd70f-215">No</span></span>|<span data-ttu-id="dd70f-216">Habilitado</span><span class="sxs-lookup"><span data-stu-id="dd70f-216">Enabled\*</span></span>|<span data-ttu-id="dd70f-217">Permite habilitar esta SBC para llamadas salientes.</span><span class="sxs-lookup"><span data-stu-id="dd70f-217">Used to enable this SBC for outbound calls.</span></span> <span data-ttu-id="dd70f-218">Puede usarse para quitar temporalmente el SBC, mientras se actualiza o durante el mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="dd70f-218">Can be used to temporarily remove the SBC, while it is being updated or during maintenance.</span></span> |<span data-ttu-id="dd70f-219">False</span><span class="sxs-lookup"><span data-stu-id="dd70f-219">False</span></span>|<span data-ttu-id="dd70f-220">True</span><span class="sxs-lookup"><span data-stu-id="dd70f-220">True</span></span><br/><span data-ttu-id="dd70f-221">False</span><span class="sxs-lookup"><span data-stu-id="dd70f-221">False</span></span>|<span data-ttu-id="dd70f-222">Boolean</span><span class="sxs-lookup"><span data-stu-id="dd70f-222">Boolean</span></span>|
 
### <a name="verify-the-sbc-pairing"></a><span data-ttu-id="dd70f-223">Comprobar el emparejamiento de SBC</span><span class="sxs-lookup"><span data-stu-id="dd70f-223">Verify the SBC pairing</span></span> 

<span data-ttu-id="dd70f-224">Compruebe la conexión:</span><span class="sxs-lookup"><span data-stu-id="dd70f-224">Verify the connection:</span></span> 
- <span data-ttu-id="dd70f-225">Compruebe si la SBC está en la lista de SBCs emparejado.</span><span class="sxs-lookup"><span data-stu-id="dd70f-225">Check if the SBC is on the list of paired SBCs.</span></span> 
- <span data-ttu-id="dd70f-226">Validar las opciones del SIP.</span><span class="sxs-lookup"><span data-stu-id="dd70f-226">Validate SIP Options.</span></span> 
 
#### <a name="validate-if-the-sbc-is-on-the-list-of-paired-sbcs"></a><span data-ttu-id="dd70f-227">Validar si el SBC está en la lista de SBCs emparejado</span><span class="sxs-lookup"><span data-stu-id="dd70f-227">Validate if the SBC is on the list of paired SBCs</span></span> 

<span data-ttu-id="dd70f-228">Después de emparejar el SBC, valide que la SBC esté presente en la lista de SBCs emparejada ejecutando el siguiente comando en una sesión remota de PowerShell:`Get-CSOnlinePSTNGateway`</span><span class="sxs-lookup"><span data-stu-id="dd70f-228">After you pair the SBC, validate that the SBC is present in the list of paired SBCs by running the following command in a remote PowerShell session: `Get-CSOnlinePSTNGateway`</span></span>

<span data-ttu-id="dd70f-229">La puerta de enlace emparejada debe aparecer en la lista, tal y como se muestra en el ejemplo siguiente, y comprobar que el parámetro *Enabled* muestra el valor **true**.</span><span class="sxs-lookup"><span data-stu-id="dd70f-229">The paired gateway should appear in the list as shown in the example below, and verify that the parameter *Enabled* displays the value **True**.</span></span> <span data-ttu-id="dd70f-230">Introducir</span><span class="sxs-lookup"><span data-stu-id="dd70f-230">Enter:</span></span>

```
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```
<span data-ttu-id="dd70f-231">Que devuelve:</span><span class="sxs-lookup"><span data-stu-id="dd70f-231">Which returns:</span></span>
<pre>
Identity              : sbc.contoso.com  
Fqdn                  : sbc.contoso.com 
SipSignallingPort     : 5067 
CodecPriority         : SILKWB,SILKNB,PCMU,PCMA 
ExcludedCodecs        :  
FailoverTimeSeconds   : 10 
ForwardCallHistory    : False 
ForwardPai            : False 
SendSipOptions        : True 
MaxConcurrentSessions : 100 
Enabled               : True 
</pre>

#### <a name="validate-sip-options-flow"></a><span data-ttu-id="dd70f-232">Validar el flujo de opciones del SIP</span><span class="sxs-lookup"><span data-stu-id="dd70f-232">Validate SIP Options flow</span></span> 

<span data-ttu-id="dd70f-233">Para validar el emparejamiento mediante las opciones de SIP salientes, use la interfaz de administración de SBC y confirme que el SBC recibe 200 respuestas correctas a sus mensajes de opciones salientes.</span><span class="sxs-lookup"><span data-stu-id="dd70f-233">To validate the pairing using outgoing SIP Options, use the SBC management interface and confirm that the SBC receives 200 OK responses to its outgoing OPTIONS messages.</span></span>

<span data-ttu-id="dd70f-234">Cuando el enrutamiento directo ve opciones entrantes, empezará a enviar mensajes de opciones SIP salientes al FQDN de SBC configurado en el campo de encabezado de contacto en el mensaje opciones de entrada.</span><span class="sxs-lookup"><span data-stu-id="dd70f-234">When Direct Routing sees incoming OPTIONS, it will start sending outgoing SIP Options messages to the SBC FQDN configured in the Contact header field in the incoming OPTIONS message.</span></span> 

<span data-ttu-id="dd70f-235">Para validar el emparejamiento con las opciones del SIP entrante, use la interfaz de administración de SBC y vea que el SBC envía una respuesta a las opciones mensajes entrantes desde el enrutamiento directo y que el código de respuesta que envía es 200 aceptar.</span><span class="sxs-lookup"><span data-stu-id="dd70f-235">To validate the pairing using incoming SIP Options, use the SBC management interface and see that the SBC sends a reply to the OPTIONS messages coming in from Direct Routing and that the response code it sends is 200 OK.</span></span>

## <a name="enable-users-for-direct-routing-service"></a><span data-ttu-id="dd70f-236">Habilitar a los usuarios para el servicio de enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="dd70f-236">Enable users for Direct Routing Service</span></span> 

<span data-ttu-id="dd70f-237">Cuando esté listo para habilitar a los usuarios para el servicio de enrutamiento directo, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="dd70f-237">When you are ready to enable users for the Direct Routing Service, follow these steps:</span></span> 

1. <span data-ttu-id="dd70f-238">Cree un usuario en Office 365 y asigne una licencia de sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="dd70f-238">Create a user in Office 365 and assign a phone system license.</span></span> 
2. <span data-ttu-id="dd70f-239">Asegúrese de que el usuario se ha alojado en Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="dd70f-239">Ensure that the user is homed in Skype for Business Online.</span></span> 
3. <span data-ttu-id="dd70f-240">Configure el número de teléfono y habilite la telefonía IP empresarial y el buzón de voz.</span><span class="sxs-lookup"><span data-stu-id="dd70f-240">Configure the phone number and enable enterprise voice and voicemail.</span></span> 
4. <span data-ttu-id="dd70f-241">Configurar el enrutamiento de voz.</span><span class="sxs-lookup"><span data-stu-id="dd70f-241">Configure voice routing.</span></span> <span data-ttu-id="dd70f-242">La ruta se valida automáticamente.</span><span class="sxs-lookup"><span data-stu-id="dd70f-242">The route is automatically validated.</span></span>

### <a name="create-a-user-in-office-365-and-assign-the-license"></a><span data-ttu-id="dd70f-243">Crear un usuario en Office 365 y asignar la licencia</span><span class="sxs-lookup"><span data-stu-id="dd70f-243">Create a user in Office 365 and assign the license</span></span> 

<span data-ttu-id="dd70f-244">Hay dos opciones para crear un nuevo usuario en Office 365.</span><span class="sxs-lookup"><span data-stu-id="dd70f-244">There are two options for creating a new user in Office 365.</span></span> <span data-ttu-id="dd70f-245">Sin embargo, recomendamos que su organización seleccione y use una opción para evitar problemas de enrutamiento:</span><span class="sxs-lookup"><span data-stu-id="dd70f-245">However, we recommend that your organization select and use one option to avoid routing issues:</span></span> 

- <span data-ttu-id="dd70f-246">Crear el usuario en Active Directory local y sincronizar el usuario con la nube.</span><span class="sxs-lookup"><span data-stu-id="dd70f-246">Create the user in on-premises Active Directory and sync the user to the cloud.</span></span> <span data-ttu-id="dd70f-247">Consulte [integrar los directorios locales con Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span><span class="sxs-lookup"><span data-stu-id="dd70f-247">See [Integrate your on-premises directories with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span></span>
- <span data-ttu-id="dd70f-248">Cree el usuario directamente en el portal de administrador de Office 365.</span><span class="sxs-lookup"><span data-stu-id="dd70f-248">Create the user directly in the Office 365 Administrator Portal.</span></span> <span data-ttu-id="dd70f-249">Consulte [Agregar usuarios individualmente o de forma masiva a Office 365: ayuda de administración](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span><span class="sxs-lookup"><span data-stu-id="dd70f-249">See [Add users individually or in bulk to Office 365 - Admin Help](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span> 

<span data-ttu-id="dd70f-250">Si su implementación de Skype empresarial online coexiste con Skype empresarial 2015 o Lync 2010/2013 local, la única opción admitida es crear el usuario en Active Directory local y sincronizar el usuario con la nube (opción 1).</span><span class="sxs-lookup"><span data-stu-id="dd70f-250">If your Skype for Business Online deployment co-exists with Skype for Business 2015 or Lync 2010/2013 on-premises, the only supported option is to create the user in on-premises Active Directory and sync the user to the cloud (Option 1).</span></span> 

<span data-ttu-id="dd70f-251">Licencias requeridas:</span><span class="sxs-lookup"><span data-stu-id="dd70f-251">Required licenses:</span></span> 

- <span data-ttu-id="dd70f-252">Office 365 Enterprise E3 (incluidos SfB Plan2, Exchange Plan2 y Teams) + sistema telefónico</span><span class="sxs-lookup"><span data-stu-id="dd70f-252">Office 365 Enterprise E3 (including SfB Plan2, Exchange Plan2, and Teams) + Phone System</span></span>
- <span data-ttu-id="dd70f-253">Office 365 Enterprise E5 (incluidos SfB Plan2, Exchange Plan2, Teams y el sistema telefónico)</span><span class="sxs-lookup"><span data-stu-id="dd70f-253">Office 365 Enterprise E5 (including SfB Plan2, Exchange Plan2, Teams, and Phone System)</span></span> 

<span data-ttu-id="dd70f-254">Licencias opcionales:</span><span class="sxs-lookup"><span data-stu-id="dd70f-254">Optional licenses:</span></span> 

- <span data-ttu-id="dd70f-255">Plan de llamadas</span><span class="sxs-lookup"><span data-stu-id="dd70f-255">Calling Plan</span></span> 
- <span data-ttu-id="dd70f-256">Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="dd70f-256">Audio Conferencing</span></span> 

### <a name="ensure-that-the-user-is-homed-in-skype-for-business-online"></a><span data-ttu-id="dd70f-257">Comprobar que el usuario se ha alojado en Skype empresarial online</span><span class="sxs-lookup"><span data-stu-id="dd70f-257">Ensure that the user is homed in Skype for Business Online</span></span> 

<span data-ttu-id="dd70f-258">El enrutamiento directo requiere que el usuario se base en Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="dd70f-258">Direct Routing requires the user to be homed in Skype for Business Online.</span></span> <span data-ttu-id="dd70f-259">Para comprobarlo, consulta el parámetro RegistrarPool.</span><span class="sxs-lookup"><span data-stu-id="dd70f-259">You can check this by looking at the RegistrarPool parameter.</span></span> <span data-ttu-id="dd70f-260">Debe tener un valor en el dominio infra.lync.com.</span><span class="sxs-lookup"><span data-stu-id="dd70f-260">It needs to have a value in the infra.lync.com domain.</span></span>

1. <span data-ttu-id="dd70f-261">Conéctese a PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="dd70f-261">Connect to remote PowerShell.</span></span>
2. <span data-ttu-id="dd70f-262">Emita el comando:</span><span class="sxs-lookup"><span data-stu-id="dd70f-262">Issue the command:</span></span> 

```
Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool
``` 

### <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a><span data-ttu-id="dd70f-263">Configurar el número de teléfono y habilitar la telefonía IP empresarial y el buzón de voz</span><span class="sxs-lookup"><span data-stu-id="dd70f-263">Configure the phone number and enable enterprise voice and voicemail</span></span> 

<span data-ttu-id="dd70f-264">Una vez que haya creado el usuario y le haya asignado una licencia, el siguiente paso es configurar su número de teléfono y el buzón de voz.</span><span class="sxs-lookup"><span data-stu-id="dd70f-264">After you have created the user and assigned a license, the next step is to configure their phone number and voicemail.</span></span> <span data-ttu-id="dd70f-265">Esto se puede hacer en un solo paso.</span><span class="sxs-lookup"><span data-stu-id="dd70f-265">This can be done in one step.</span></span> 

<span data-ttu-id="dd70f-266">Para agregar el número de teléfono y habilitar el buzón de voz:</span><span class="sxs-lookup"><span data-stu-id="dd70f-266">To add the phone number and enable for voicemail:</span></span>
 
1. <span data-ttu-id="dd70f-267">Conectarse a una sesión de PowerShell remota.</span><span class="sxs-lookup"><span data-stu-id="dd70f-267">Connect to a remote PowerShell session.</span></span> 
2. <span data-ttu-id="dd70f-268">Escribe el comando:</span><span class="sxs-lookup"><span data-stu-id="dd70f-268">Enter the command:</span></span> 
 
```
Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<E.164 phone number>
```

<span data-ttu-id="dd70f-269">Por ejemplo, para añadir un número de teléfono para el usuario "Spencer Low", tendría que escribir lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="dd70f-269">For example, to add a phone number for user "Spencer Low," you would enter the following:</span></span> 

```
Set-CsUser -Identity "Spencer Low" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
```

<span data-ttu-id="dd70f-270">El número de teléfono usado debe configurarse como un número de teléfono E. 164 completo con prefijo internacional.</span><span class="sxs-lookup"><span data-stu-id="dd70f-270">The phone number used has to be configured as a full E.164 phone number with country code.</span></span> 

  > [!NOTE]
  > <span data-ttu-id="dd70f-271">Si el número de teléfono del usuario se administra localmente, use el shell local de administración de Skype empresarial o el panel de control para configurar el número de teléfono del usuario.</span><span class="sxs-lookup"><span data-stu-id="dd70f-271">If the user’s phone number is managed on premises, use on-premises Skype for Business Management Shell or Control Panel to configure the user's phone number.</span></span> 

### <a name="configure-voice-routing"></a><span data-ttu-id="dd70f-272">Configurar el enrutamiento de voz</span><span class="sxs-lookup"><span data-stu-id="dd70f-272">Configure Voice Routing</span></span> 

<span data-ttu-id="dd70f-273">Microsoft Phone System tiene un mecanismo de enrutamiento que permite que se envíe una llamada a un SBC específico en función de lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="dd70f-273">Microsoft Phone System has a routing mechanism that allows a call to be sent to a specific SBC based on:</span></span> 

- <span data-ttu-id="dd70f-274">Patrón de número denominado</span><span class="sxs-lookup"><span data-stu-id="dd70f-274">Called number pattern</span></span> 
- <span data-ttu-id="dd70f-275">Se denomina patrón de números + usuario específico que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="dd70f-275">Called number pattern + Specific User who makes the call</span></span>
 
<span data-ttu-id="dd70f-276">SBCs puede designarse como activo y como backup.</span><span class="sxs-lookup"><span data-stu-id="dd70f-276">SBCs can be designated as active and backup.</span></span> <span data-ttu-id="dd70f-277">Eso significa que cuando el SBC configurado como activo para este patrón de número o patrón de número + usuario específico, no está disponible, las llamadas se enrutarán a un SBC de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="dd70f-277">That means when the SBC that is configured as active for this number pattern, or number pattern + specific user, is not available, then the calls will be routed to a backup SBC.</span></span>
 
<span data-ttu-id="dd70f-278">El enrutamiento de llamadas consta de los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="dd70f-278">Call routing is made up of the following elements:</span></span> 
- <span data-ttu-id="dd70f-279">Directiva de enrutamiento de voz: contenedor para usos de RTC; puede asignarse a un usuario o a varios usuarios</span><span class="sxs-lookup"><span data-stu-id="dd70f-279">Voice Routing Policy – container for PSTN Usages; can be assigned to a user or to multiple users</span></span> 
- <span data-ttu-id="dd70f-280">Usos de RTC: contenedor de rutas de voz y usos de RTC; puede compartirse en diferentes directivas de enrutamiento de voz</span><span class="sxs-lookup"><span data-stu-id="dd70f-280">PSTN Usages – container for Voice Routes and PSTN Usages; can be shared in different Voice Routing Policies</span></span> 
- <span data-ttu-id="dd70f-281">Rutas de voz: patrón de número y conjunto de puertas de enlace RTC en línea para usarlas en las llamadas en las que el número de llamada coincide con el patrón</span><span class="sxs-lookup"><span data-stu-id="dd70f-281">Voice Routes – number pattern and set of Online PSTN Gateways to use for calls where calling number matches the pattern</span></span> 
- <span data-ttu-id="dd70f-282">Un puntero de puerta de enlace RTC en línea a un SBC también almacena la configuración que se aplica cuando la llamada se coloca a través de SBC, como reenvío de identidad de aserción de P (PAI) o códecs preferidos; se puede Agregar a las rutas de voz</span><span class="sxs-lookup"><span data-stu-id="dd70f-282">Online PSTN Gateway - pointer to an SBC, also stores the configuration that is applied when call is placed via the SBC, such as forward P-Asserted-Identity (PAI) or Preferred Codecs; can be added to Voice Routes</span></span> 

#### <a name="creating-a-voice-routing-policy-with-one-pstn-usage"></a><span data-ttu-id="dd70f-283">Crear una directiva de enrutamiento de voz con un uso de RTC</span><span class="sxs-lookup"><span data-stu-id="dd70f-283">Creating a voice routing policy with one PSTN Usage</span></span> 

<span data-ttu-id="dd70f-284">En el siguiente diagrama se muestran dos ejemplos de directivas de enrutamiento de voz en el flujo de llamadas.</span><span class="sxs-lookup"><span data-stu-id="dd70f-284">The following diagram shows two examples of voice routing policies in call flow.</span></span>

<span data-ttu-id="dd70f-285">**Flujo de llamadas 1 (a la izquierda):** Si un usuario hace una llamada a + 1 425 XXX XX XX ó + 1 206 XXX XX XX, la llamada se dirige a SBC sbc1.contoso.biz o sbc2.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="dd70f-285">**Call Flow 1 (on the left):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="dd70f-286">Si ni sbc1.contoso.biz ni sbc2.contoso.biz están disponibles, la llamada se interrumpe.</span><span class="sxs-lookup"><span data-stu-id="dd70f-286">If neither sbc1.contoso.biz nor sbc2.contoso.biz are available, the call is dropped.</span></span> 

<span data-ttu-id="dd70f-287">**Flujo de llamadas 2 (a la derecha):** Si un usuario hace una llamada a + 1 425 XXX XX XX ó + 1 206 XXX XX XX, la llamada se enruta primero a SBC sbc1.contoso.biz o sbc2.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="dd70f-287">**Call Flow 2 (on the right):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is first routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="dd70f-288">Si no hay ninguna SBC disponible, se intentará la ruta con prioridad más baja (sbc3.contoso.biz y sbc4.contoso.biz).</span><span class="sxs-lookup"><span data-stu-id="dd70f-288">If neither SBC is available, the route with lower priority will be tried (sbc3.contoso.biz and sbc4.contoso.biz).</span></span> <span data-ttu-id="dd70f-289">Si ninguno de los SBCs está disponible, la llamada se corta.</span><span class="sxs-lookup"><span data-stu-id="dd70f-289">If none of the SBCs are available, the call is dropped.</span></span> 

![Muestra ejemplos de directiva de enrutamiento de voz](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

<span data-ttu-id="dd70f-291">En ambos ejemplos, mientras se asignan prioridades a la ruta de voz, se prueba el SBCs en las rutas en orden aleatorio.</span><span class="sxs-lookup"><span data-stu-id="dd70f-291">In both examples, while the Voice Route is assigned priorities, the SBCs in the routes are tried in random order.</span></span>

  > [!NOTE]
  > <span data-ttu-id="dd70f-292">A menos que el usuario también tenga una licencia de plan de llamadas de Microsoft, las llamadas a cualquier número excepto los números que coincidan con los patrones + 1 425 XXX XX XX o + 1 206 XXX XX XX en la configuración de ejemplo se eliminan.</span><span class="sxs-lookup"><span data-stu-id="dd70f-292">Unless the user also has a Microsoft Calling Plan license, calls to any number except numbers matching the patterns +1 425 XXX XX XX or +1 206 XXX XX XX in the example configuration are dropped.</span></span> <span data-ttu-id="dd70f-293">Si el usuario tiene una licencia de plan de llamadas, la llamada se redirige automáticamente según las directivas del plan de llamadas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="dd70f-293">If the user has a Calling Plan license, the call is automatically routed according to the policies of the Microsoft Calling Plan.</span></span> 

<span data-ttu-id="dd70f-294">El plan de llamadas de Microsoft se aplica automáticamente como la última ruta a todos los usuarios con la licencia de plan de llamadas de Microsoft y no requiere configuración de enrutamiento de llamadas adicional.</span><span class="sxs-lookup"><span data-stu-id="dd70f-294">The Microsoft Calling Plan applies automatically as the last route to all users with the Microsoft Calling Plan license and does not require additional call routing configuration.</span></span>

<span data-ttu-id="dd70f-295">En el ejemplo que se muestra en el siguiente diagrama, se agrega una ruta de voz para enviar llamadas a todos los demás números de Estados Unidos y Canadá (llamadas que van a denominarse patrón de números + 1 XXX XXX XX XX).</span><span class="sxs-lookup"><span data-stu-id="dd70f-295">In the example shown in the following diagram, a voice route is added to send calls to all other US and Canadian number (calls that go to called number pattern +1 XXX XXX XX XX).</span></span>

![Muestra la Directiva de enrutamiento de voz con una tercera ruta](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

<span data-ttu-id="dd70f-297">Para todas las demás llamadas, si un usuario tiene ambas licencias (Microsoft Phone System y Microsoft Call plan), se usa la ruta automática.</span><span class="sxs-lookup"><span data-stu-id="dd70f-297">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), Automatic Route is used.</span></span> <span data-ttu-id="dd70f-298">Si nada coincide con los patrones de número de las rutas de voz en línea creadas por el administrador, enrutar a través del plan de llamadas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="dd70f-298">If nothing matches the number patterns in the administrator-created online voice routes, route via Microsoft Calling Plan.</span></span>

<span data-ttu-id="dd70f-299">Si el usuario solo tiene Microsoft Phone System, la llamada se elimina porque no hay disponibles reglas coincidentes.</span><span class="sxs-lookup"><span data-stu-id="dd70f-299">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

  > [!NOTE]
  > <span data-ttu-id="dd70f-300">El valor de prioridad para la ruta "otros + 1" no importa en este caso, ya que hay una sola ruta que coincide con el patrón + 1 XXX XXX XX XX.</span><span class="sxs-lookup"><span data-stu-id="dd70f-300">The Priority value for route "Other +1" doesn’t matter in this case, as there is only one route that matches the pattern +1 XXX XXX XX XX.</span></span> <span data-ttu-id="dd70f-301">Si un usuario llama a + 1 324 567 89 89 y tanto sbc5.contoso.biz como sbc6.contoso.biz no están disponibles, la llamada se cancela.</span><span class="sxs-lookup"><span data-stu-id="dd70f-301">If a user makes a call to +1 324 567 89 89 and both sbc5.contoso.biz and sbc6.contoso.biz are unavailable, the call is dropped.</span></span>

<span data-ttu-id="dd70f-302">En la tabla siguiente se resume la configuración mediante tres rutas de voz.</span><span class="sxs-lookup"><span data-stu-id="dd70f-302">The following table summarizes the configuration using three voice routes.</span></span> <span data-ttu-id="dd70f-303">En este ejemplo, las tres rutas forman parte del mismo uso de la RTC "Estados Unidos y Canadá".</span><span class="sxs-lookup"><span data-stu-id="dd70f-303">In this example, all three routes are part of the same PSTN Usage "US and Canada".</span></span>

|<span data-ttu-id="dd70f-304">**Uso de RTC**</span><span class="sxs-lookup"><span data-stu-id="dd70f-304">**PSTN usage**</span></span>|<span data-ttu-id="dd70f-305">**Ruta de voz**</span><span class="sxs-lookup"><span data-stu-id="dd70f-305">**Voice route**</span></span>|<span data-ttu-id="dd70f-306">**Patrón de números**</span><span class="sxs-lookup"><span data-stu-id="dd70f-306">**Number pattern**</span></span>|<span data-ttu-id="dd70f-307">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="dd70f-307">**Priority**</span></span>|<span data-ttu-id="dd70f-308">**SBC**</span><span class="sxs-lookup"><span data-stu-id="dd70f-308">**SBC**</span></span>|<span data-ttu-id="dd70f-309">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="dd70f-309">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="dd70f-310">Solo para Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="dd70f-310">US only</span></span>|<span data-ttu-id="dd70f-311">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="dd70f-311">"Redmond 1"</span></span>|<span data-ttu-id="dd70f-312">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="dd70f-312">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="dd70f-313">1</span><span class="sxs-lookup"><span data-stu-id="dd70f-313">1</span></span>|<span data-ttu-id="dd70f-314">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="dd70f-314">sbc1.contoso.biz</span></span><br/><span data-ttu-id="dd70f-315">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="dd70f-315">sbc2.contoso.biz</span></span>|<span data-ttu-id="dd70f-316">Ruta activa para números llamados + 1 425 XXX XX XX o + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="dd70f-316">Active route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="dd70f-317">Solo para Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="dd70f-317">US only</span></span>|<span data-ttu-id="dd70f-318">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="dd70f-318">"Redmond 2"</span></span>|<span data-ttu-id="dd70f-319">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="dd70f-319">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="dd70f-320">2</span><span class="sxs-lookup"><span data-stu-id="dd70f-320">2</span></span>|<span data-ttu-id="dd70f-321">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="dd70f-321">sbc3.contoso.biz</span></span><br/><span data-ttu-id="dd70f-322">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="dd70f-322">sbc4.contoso.biz</span></span>|<span data-ttu-id="dd70f-323">Ruta de copia de seguridad para los números + 1 425 XXX XX XX ó + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="dd70f-323">Backup route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="dd70f-324">Solo para Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="dd70f-324">US only</span></span>|<span data-ttu-id="dd70f-325">"Otros + 1"</span><span class="sxs-lookup"><span data-stu-id="dd70f-325">"Other +1"</span></span>|<span data-ttu-id="dd70f-326">^\\+ 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="dd70f-326">^\\+1(\d{10})$</span></span>|<span data-ttu-id="dd70f-327">3</span><span class="sxs-lookup"><span data-stu-id="dd70f-327">3</span></span>|<span data-ttu-id="dd70f-328">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="dd70f-328">sbc5.contoso.biz</span></span><br/><span data-ttu-id="dd70f-329">sbc6.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="dd70f-329">sbc6.contoso.biz</span></span>|<span data-ttu-id="dd70f-330">Ruta de números llamados + 1 XXX XXX XX XX (excepto + 1 425 XXX XX XX o + 1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="dd70f-330">Route for called numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|||||||

<span data-ttu-id="dd70f-331">Todas las rutas se asocian con el uso de la RTC "Estados Unidos y Canadá" y el uso de RTC está asociado a la Directiva de enrutamiento de voz "solo para EE. UU.".</span><span class="sxs-lookup"><span data-stu-id="dd70f-331">All routes are associated with the PSTN Usage "US and Canada" and the PSTN Usage is associated with the Voice Routing Policy "US Only."</span></span> <span data-ttu-id="dd70f-332">En este ejemplo, la Directiva de enrutamiento de voz se asigna a User Spencer Low.</span><span class="sxs-lookup"><span data-stu-id="dd70f-332">In this example, the voice routing policy is assigned to user Spencer Low.</span></span>

#### <a name="examples-of-call-routes"></a><span data-ttu-id="dd70f-333">Ejemplos de rutas de llamadas</span><span class="sxs-lookup"><span data-stu-id="dd70f-333">Examples of call routes</span></span>

<span data-ttu-id="dd70f-334">En el siguiente ejemplo, se muestra cómo configurar rutas, usos de RTC y directivas de enrutamiento, y asignamos la Directiva al usuario.</span><span class="sxs-lookup"><span data-stu-id="dd70f-334">In the following example, we demonstrate how to configure Routes, PSTN Usages, and Routing policies, and we assign the policy to the user.</span></span>

<span data-ttu-id="dd70f-335">**Paso 1:** Crear el uso de RTC "Estados Unidos y Canadá".</span><span class="sxs-lookup"><span data-stu-id="dd70f-335">**Step 1:** Create the PSTN Usage "US and Canada".</span></span>

<span data-ttu-id="dd70f-336">En una sesión de PowerShell remoto de Skype empresarial, escriba:</span><span class="sxs-lookup"><span data-stu-id="dd70f-336">In a Skype for Business Remote PowerShell session, type:</span></span>

```
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

<span data-ttu-id="dd70f-337">Valide que el uso se haya creado especificando:</span><span class="sxs-lookup"><span data-stu-id="dd70f-337">Validate that the usage was created by entering:</span></span> 
```
Get-CSOnlinePSTNUsage
``` 
<span data-ttu-id="dd70f-338">Que devuelve una lista de los nombres que se pueden truncar:</span><span class="sxs-lookup"><span data-stu-id="dd70f-338">Which returns a list of names that may be truncated:</span></span>
```
  Identity  : Global
  Usage     : {testusage, US and Canada, International, karlUsage. . .}
```
<span data-ttu-id="dd70f-339">En el ejemplo siguiente, puede ver el resultado de ejecutar el comando `(Get-CSOnlinePSTNUsage).usage` de PowerShell para mostrar nombres completos (no truncados).</span><span class="sxs-lookup"><span data-stu-id="dd70f-339">In the example below, you can see the result of the running the PowerShell command `(Get-CSOnlinePSTNUsage).usage` to display full names (not truncated).</span></span> 
<pre>
 testusage
 US and Canada
 International
 karlUsage
 New test env
 Tallinn Lab Sonus
 karlUsage2
 Unrestricted
 Two trunks
</pre>

<span data-ttu-id="dd70f-340">**Paso 2:** En una sesión de PowerShell de Skype empresarial online, cree tres rutas: Redmond 1, Redmond 2 y otros + 1, tal y como se detalla en la tabla anterior.</span><span class="sxs-lookup"><span data-stu-id="dd70f-340">**Step 2:** In a PowerShell session in Skype for Business Online, create three routes: Redmond 1, Redmond 2, and Other +1, as detailed in the previous table.</span></span> 

<span data-ttu-id="dd70f-341">Para crear la ruta de "Redmond 1", escriba:</span><span class="sxs-lookup"><span data-stu-id="dd70f-341">To create the "Redmond 1" route, enter:</span></span>

  ```
  New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
  (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
  ```

<span data-ttu-id="dd70f-342">Que devuelve:</span><span class="sxs-lookup"><span data-stu-id="dd70f-342">Which returns:</span></span>
<pre>
Identity                : Redmond 1
Priority            : 1
Description         :
NumberPattern       : ^\+1(425|206) (\d{7})$
OnlinePstnUsages    : {US and Canada}
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name            : Redmond 1
SuppressCallerId    :
AlternateCallerId   :
</pre>
<span data-ttu-id="dd70f-343">Para crear la ruta de Redmond 2, escriba:</span><span class="sxs-lookup"><span data-stu-id="dd70f-343">To create the Redmond 2 route, enter:</span></span>

```
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="dd70f-344">Para crear la ruta otra + 1, escriba:</span><span class="sxs-lookup"><span data-stu-id="dd70f-344">To create the Other +1 route, enter:</span></span>

```
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > <span data-ttu-id="dd70f-345">Asegúrese de que la expresión regular en el atributo NumberPattern es una expresión válida.</span><span class="sxs-lookup"><span data-stu-id="dd70f-345">Make sure that your regular expression in the NumberPattern attribute is a valid expression.</span></span> <span data-ttu-id="dd70f-346">Puede probarla con este sitio web:[https://www.regexpal.com](https://www.regexpal.com)</span><span class="sxs-lookup"><span data-stu-id="dd70f-346">You can test it using this website: [https://www.regexpal.com](https://www.regexpal.com)</span></span>

<span data-ttu-id="dd70f-347">En algunos casos, es necesario enrutar todas las llamadas a la misma SBC; Use-NumberPattern ". \*"</span><span class="sxs-lookup"><span data-stu-id="dd70f-347">In some cases there is a need to route all calls to the same SBC; please use -NumberPattern ".\*"</span></span>

- <span data-ttu-id="dd70f-348">Enrutar todas las llamadas al mismo SBC</span><span class="sxs-lookup"><span data-stu-id="dd70f-348">Route all calls to same SBC</span></span>

    ```
    Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" 
     -OnlinePstnGatewayList sbc1.contoso.biz
    ```

<span data-ttu-id="dd70f-349">Confirme que ha configurado correctamente la ruta ejecutando el `Get-CSOnlineVoiceRoute` comando PowerShell con las opciones que se muestran:</span><span class="sxs-lookup"><span data-stu-id="dd70f-349">Validate that you’ve correctly configured the route by running the `Get-CSOnlineVoiceRoute` PowerShell command using options as shown:</span></span> 

```
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
<span data-ttu-id="dd70f-350">Que debería devolver:</span><span class="sxs-lookup"><span data-stu-id="dd70f-350">Which should return:</span></span>
<pre>
Identity            : Redmond 1 
Priority            : 1
Description     : 
NumberPattern       : ^\+1(425|206) (\d{7})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name            : Redmond 1
Identity        : Redmond 2 
Priority            : 2
Description     : 
NumberPattern       : ^\+1(425|206) (\d{7})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc3.contoso.biz, sbc4.contoso.biz}
Name            : Redmond 2
    
Identity        : Other +1 
Priority            : 4
Description     : 
NumberPattern       : ^\+1(\d{10})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc5.contoso.biz, sbc6.contoso.biz}
Name            : Other +1
</pre>

<span data-ttu-id="dd70f-351">En el ejemplo, se asignó automáticamente la prioridad 4 a la ruta "otros + 1".</span><span class="sxs-lookup"><span data-stu-id="dd70f-351">In the example, the route "Other +1" was automatically assigned priority 4.</span></span> 

<span data-ttu-id="dd70f-352">**Paso 3:** Crear una directiva de enrutamiento de voz "solo para EE. UU." y agregar a la directiva el uso de la RTC "Estados Unidos y Canadá".</span><span class="sxs-lookup"><span data-stu-id="dd70f-352">**Step 3:** Create a Voice Routing Policy "US Only" and add to the policy the PSTN Usage "US and Canada."</span></span>

<span data-ttu-id="dd70f-353">En una sesión de PowerShell en Skype empresarial online, escriba:</span><span class="sxs-lookup"><span data-stu-id="dd70f-353">In a PowerShell session in Skype for Business Online, type:</span></span>

```
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="dd70f-354">El resultado se muestra en este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="dd70f-354">The result is shown in this example:</span></span>

<pre>
Identity        : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
</pre>

<span data-ttu-id="dd70f-355">**Paso 4:** Conceder al usuario Spencer bajo una directiva de enrutamiento de voz con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dd70f-355">**Step 4:** Grant to user Spencer Low a voice routing policy by using PowerShell.</span></span>

- <span data-ttu-id="dd70f-356">En una sesión de PowerShell en Skype empresarial online, escriba:</span><span class="sxs-lookup"><span data-stu-id="dd70f-356">In a PowerShell session in Skype for Business Online, type:</span></span>

    ```Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"```

- <span data-ttu-id="dd70f-357">Valide la asignación de directiva escribiendo este comando:</span><span class="sxs-lookup"><span data-stu-id="dd70f-357">Validate the policy assignment by entering this command:</span></span>

```
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```
<span data-ttu-id="dd70f-358">Que devuelve:</span><span class="sxs-lookup"><span data-stu-id="dd70f-358">Which returns:</span></span>
<pre>
    OnlineVoiceRoutingPolicy
    ---------------------
    US Only
</pre>

#### <a name="creating-a-voice-routing-policy-with-several-pstn-usages"></a><span data-ttu-id="dd70f-359">Crear una directiva de enrutamiento de voz con varios usos de RTC</span><span class="sxs-lookup"><span data-stu-id="dd70f-359">Creating a Voice Routing Policy with several PSTN Usages</span></span>

<span data-ttu-id="dd70f-360">La Directiva de enrutamiento de voz creada anteriormente solo permite llamadas a números de teléfono en Estados Unidos y Canadá, a menos que la licencia del plan de llamadas de Microsoft también esté asignada al usuario.</span><span class="sxs-lookup"><span data-stu-id="dd70f-360">The Voice Routing Policy created previously only allows calls to phone numbers in the US and Canada--unless the Microsoft Calling Plan license is also assigned to the user.</span></span>

<span data-ttu-id="dd70f-361">En el ejemplo siguiente, puede crear la Directiva de enrutamiento de voz "sin restricciones".</span><span class="sxs-lookup"><span data-stu-id="dd70f-361">In the example that follows, you can create the Voice Routing Policy "No Restrictions."</span></span> <span data-ttu-id="dd70f-362">La Directiva reutiliza el uso de la RTC "Estados Unidos y Canadá" creado en el ejemplo anterior, así como el nuevo uso de RTC "internacional".</span><span class="sxs-lookup"><span data-stu-id="dd70f-362">The policy reuses the PSTN Usage "US and Canada" created in the previous example, as well as the new PSTN Usage "International."</span></span> 

<span data-ttu-id="dd70f-363">Esto enruta todas las demás llamadas a los sbc2.contoso.biz y sbc5.contoso.biz de SBCs.</span><span class="sxs-lookup"><span data-stu-id="dd70f-363">This routes all other calls to the SBCs sbc2.contoso.biz and sbc5.contoso.biz.</span></span> <span data-ttu-id="dd70f-364">Los ejemplos que se muestran asignan la Directiva solo para usuarios de "Spencer Low", sin restricciones para el usuario "John Woods".</span><span class="sxs-lookup"><span data-stu-id="dd70f-364">The examples that are shown assign the US Only policy to user "Spencer Low," and No Restrictions to the user "John Woods."</span></span>

<span data-ttu-id="dd70f-365">Spencer Low: las llamadas se permiten solo a números de Estados Unidos y Canadá.</span><span class="sxs-lookup"><span data-stu-id="dd70f-365">Spencer Low – Calls allowed only to US and Canadian numbers.</span></span> <span data-ttu-id="dd70f-366">Al llamar al intervalo de números de Redmond, debe usarse el conjunto específico de SBC.</span><span class="sxs-lookup"><span data-stu-id="dd70f-366">When calling to the Redmond number range, the specific set of SBC must be used.</span></span> <span data-ttu-id="dd70f-367">Los números que no son de Estados Unidos no se enrutan a menos que la licencia del plan de llamadas se asigne al usuario.</span><span class="sxs-lookup"><span data-stu-id="dd70f-367">Non-US numbers will not be routed unless the Calling Plan license is assigned to the user.</span></span>

<span data-ttu-id="dd70f-368">John Woods: permite realizar llamadas a cualquier número.</span><span class="sxs-lookup"><span data-stu-id="dd70f-368">John Woods – Calls allowed to any number.</span></span> <span data-ttu-id="dd70f-369">Al llamar al intervalo de números de Redmond, debe usarse el conjunto específico de SBC.</span><span class="sxs-lookup"><span data-stu-id="dd70f-369">When calling to the Redmond number range, the specific set of SBC must be used.</span></span> <span data-ttu-id="dd70f-370">Los números que no sean de Estados Unidos se enrutarán a través de sbc2.contoso.biz y sbc5.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="dd70f-370">Non-US numbers will be routed via sbc2.contoso.biz and sbc5.contoso.biz.</span></span>

![Muestra la Directiva de enrutamiento de voz asignada al usuario Spencer Low](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

<span data-ttu-id="dd70f-372">Para todas las demás llamadas, si un usuario tiene ambas licencias (Microsoft Phone System y Microsoft Call plan), se usa la ruta automática.</span><span class="sxs-lookup"><span data-stu-id="dd70f-372">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), Automatic Route is used.</span></span> <span data-ttu-id="dd70f-373">Si nada coincide con los patrones de número de las rutas de voz en línea creadas por el administrador, enrutar a través del plan de llamadas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="dd70f-373">If nothing matches the number patterns in the administrator-created online voice routes, route via Microsoft Calling Plan.</span></span>

<span data-ttu-id="dd70f-374">Si el usuario solo tiene Microsoft Phone System, la llamada se elimina porque no hay disponibles reglas coincidentes.</span><span class="sxs-lookup"><span data-stu-id="dd70f-374">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

![Muestra la Directiva de enrutamiento de voz asignada al usuario John Woods](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

<span data-ttu-id="dd70f-376">En la siguiente tabla se resumen las denominaciones de uso y las rutas de voz de directivas de enrutamiento "sin restricciones".</span><span class="sxs-lookup"><span data-stu-id="dd70f-376">The following table summarizes routing policy "No Restrictions" usage designations and voice routes.</span></span> 

|<span data-ttu-id="dd70f-377">**Uso de RTC**</span><span class="sxs-lookup"><span data-stu-id="dd70f-377">**PSTN usage**</span></span>|<span data-ttu-id="dd70f-378">**Ruta de voz**</span><span class="sxs-lookup"><span data-stu-id="dd70f-378">**Voice route**</span></span>|<span data-ttu-id="dd70f-379">**Patrón de números**</span><span class="sxs-lookup"><span data-stu-id="dd70f-379">**Number pattern**</span></span>|<span data-ttu-id="dd70f-380">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="dd70f-380">**Priority**</span></span>|<span data-ttu-id="dd70f-381">**SBC**</span><span class="sxs-lookup"><span data-stu-id="dd70f-381">**SBC**</span></span>|<span data-ttu-id="dd70f-382">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="dd70f-382">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="dd70f-383">Solo para Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="dd70f-383">US Only</span></span>|<span data-ttu-id="dd70f-384">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="dd70f-384">"Redmond 1"</span></span>|<span data-ttu-id="dd70f-385">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="dd70f-385">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="dd70f-386">1</span><span class="sxs-lookup"><span data-stu-id="dd70f-386">1</span></span>|<span data-ttu-id="dd70f-387">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="dd70f-387">sbc1.contoso.biz</span></span><br/><span data-ttu-id="dd70f-388">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="dd70f-388">sbc2.contoso.biz</span></span>|<span data-ttu-id="dd70f-389">Ruta activa para números de destinatarios + 1 425 XXX XX XX o + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="dd70f-389">Active route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="dd70f-390">Solo para Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="dd70f-390">US Only</span></span>|<span data-ttu-id="dd70f-391">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="dd70f-391">"Redmond 2"</span></span>|<span data-ttu-id="dd70f-392">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="dd70f-392">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="dd70f-393">2</span><span class="sxs-lookup"><span data-stu-id="dd70f-393">2</span></span>|<span data-ttu-id="dd70f-394">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="dd70f-394">sbc3.contoso.biz</span></span><br/><span data-ttu-id="dd70f-395">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="dd70f-395">sbc4.contoso.biz</span></span>|<span data-ttu-id="dd70f-396">Ruta de reserva para números de destinatarios + 1 425 XXX XX XX o + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="dd70f-396">Backup route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="dd70f-397">Solo para Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="dd70f-397">US Only</span></span>|<span data-ttu-id="dd70f-398">"Otros + 1"</span><span class="sxs-lookup"><span data-stu-id="dd70f-398">"Other +1"</span></span>|<span data-ttu-id="dd70f-399">^\\+ 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="dd70f-399">^\\+1(\d{10})$</span></span>|<span data-ttu-id="dd70f-400">3</span><span class="sxs-lookup"><span data-stu-id="dd70f-400">3</span></span>|<span data-ttu-id="dd70f-401">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="dd70f-401">sbc5.contoso.biz</span></span><br/><span data-ttu-id="dd70f-402">sbc6>. contoso. BIZ</span><span class="sxs-lookup"><span data-stu-id="dd70f-402">sbc6>.contoso.biz</span></span>|<span data-ttu-id="dd70f-403">Ruta para números de la llamada + 1 XXX XXX XX XX (excepto + 1 425 XXX XX XX o + 1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="dd70f-403">Route for callee numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|<span data-ttu-id="dd70f-404">International</span><span class="sxs-lookup"><span data-stu-id="dd70f-404">International</span></span>|<span data-ttu-id="dd70f-405">International</span><span class="sxs-lookup"><span data-stu-id="dd70f-405">International</span></span>|<span data-ttu-id="dd70f-406">\d +</span><span class="sxs-lookup"><span data-stu-id="dd70f-406">\d+</span></span>|<span data-ttu-id="dd70f-407">4</span><span class="sxs-lookup"><span data-stu-id="dd70f-407">4</span></span>|<span data-ttu-id="dd70f-408">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="dd70f-408">sbc2.contoso.biz</span></span><br/><span data-ttu-id="dd70f-409">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="dd70f-409">sbc5.contoso.biz</span></span>|<span data-ttu-id="dd70f-410">Ruta para cualquier patrón de números</span><span class="sxs-lookup"><span data-stu-id="dd70f-410">Route for any number pattern</span></span> |


  > [!NOTE]
  > - <span data-ttu-id="dd70f-411">El orden de los usos de RTC en las directivas de enrutamiento de voz es fundamental.</span><span class="sxs-lookup"><span data-stu-id="dd70f-411">The order of PSTN Usages in Voice Routing Policies is critical.</span></span> <span data-ttu-id="dd70f-412">Los usos se aplican en orden y, si se encuentra una coincidencia en el primer uso, no se evalúan otros usos.</span><span class="sxs-lookup"><span data-stu-id="dd70f-412">The usages are applied in order, and if a match is found in the first usage, then other usages are never evaluated.</span></span> <span data-ttu-id="dd70f-413">El uso de RTC "internacional" debe situarse después del uso de RTC "solo para EE. UU.".</span><span class="sxs-lookup"><span data-stu-id="dd70f-413">The PSTN Usage "International" must be placed after the PSTN Usage "US Only."</span></span> <span data-ttu-id="dd70f-414">Para cambiar el orden de los usos de RTC, ejecute el `Set-CSOnlineVoiceRoutingPolicy` comando.</span><span class="sxs-lookup"><span data-stu-id="dd70f-414">To change the order of the PSTN Usages, run the `Set-CSOnlineVoiceRoutingPolicy` command.</span></span> <br/><span data-ttu-id="dd70f-415">Por ejemplo, para cambiar el orden de "Estados Unidos y Canadá" primero por "internacional" y el segundo al orden invertido:</span><span class="sxs-lookup"><span data-stu-id="dd70f-415">For example, to change the order from "US and Canada" first and "International" second to the reverse order run:</span></span><br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - <span data-ttu-id="dd70f-416">La prioridad de las rutas de voz "otras + 1" y "internacionales" se asigna automáticamente.</span><span class="sxs-lookup"><span data-stu-id="dd70f-416">The priority for "Other +1" and "International" Voice routes are assigned automatically.</span></span> <span data-ttu-id="dd70f-417">No importa siempre que tengan prioridades más bajas que "Redmond 1" y "Redmond 2".</span><span class="sxs-lookup"><span data-stu-id="dd70f-417">They don’t matter as long as they have lower priorities than "Redmond 1" and "Redmond 2."</span></span>

#### <a name="example-of-voice-routing-policy-for-user-john-woods"></a><span data-ttu-id="dd70f-418">Ejemplo de directiva de enrutamiento de voz para el usuario John Woods</span><span class="sxs-lookup"><span data-stu-id="dd70f-418">Example of Voice Routing Policy for user John Woods</span></span>

<span data-ttu-id="dd70f-419">A continuación, se indican los pasos para crear el uso de RTC "internacional", la ruta de voz "internacional", la Directiva de enrutamiento de voz "sin restricciones" y, a continuación, asignarlo al usuario "John Woods".</span><span class="sxs-lookup"><span data-stu-id="dd70f-419">The steps to create PSTN Usage "International", voice route "International," Voice Routing Policy "No Restrictions," and then assigning it to the user "John Woods" are as follows.</span></span>


1. <span data-ttu-id="dd70f-420">En primer lugar, cree el uso de RTC "internacional".</span><span class="sxs-lookup"><span data-stu-id="dd70f-420">First, create the PSTN Usage "International."</span></span> <span data-ttu-id="dd70f-421">En una sesión de PowerShell remoto en Skype empresarial online, escriba:</span><span class="sxs-lookup"><span data-stu-id="dd70f-421">In a remote PowerShell session in Skype for Business Online, enter:</span></span>

   ```
   Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
   ```

2. <span data-ttu-id="dd70f-422">Después, cree la nueva ruta de voz "internacional".</span><span class="sxs-lookup"><span data-stu-id="dd70f-422">Next, create the new voice route "International."</span></span>

   ```
   New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
   ```
   <span data-ttu-id="dd70f-423">Que devuelve:</span><span class="sxs-lookup"><span data-stu-id="dd70f-423">Which returns:</span></span>

   <pre>
   Identity                  : International 
   Priority                      : 5
   Description                   : 
   NumberPattern                 : .*
   OnlinePstnUsages          : {International} 
   OnlinePstnGatewayList           : {sbc2.contoso.biz, sbc5.contoso.biz}
   Name                            : International
   SuppressCallerId          :
   AlternateCallerId         :
   </pre>
3. <span data-ttu-id="dd70f-424">A continuación, cree una directiva de enrutamiento de voz "sin restricciones".</span><span class="sxs-lookup"><span data-stu-id="dd70f-424">Next, create a Voice Routing Policy "No Restrictions".</span></span> <span data-ttu-id="dd70f-425">El uso de RTC "Redmond 1" y "Redmond" se reutiliza en esta directiva de enrutamiento de voz para mantener un control especial de las llamadas al número "+ 1 425 XXX XX XX" y "+ 1 206 XXX XX XX" como llamadas locales o locales.</span><span class="sxs-lookup"><span data-stu-id="dd70f-425">The PSTN Usage "Redmond 1" and "Redmond" are reused in this voice routing policy to preserve special handling for calls to number "+1 425 XXX XX XX" and "+1 206 XXX XX XX" as local or on-premises calls.</span></span>

```
New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
```

    Take note of the order of PSTN Usages:

    a. If a call made to number "+1 425 XXX XX XX" with the usages configured as in the following example, the call follows the route set in "US and Canada" usage and the special routing logic is applied. That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes. 

    b.  If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic. Enter the command:

    ```New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"```

   <span data-ttu-id="dd70f-426">Que devuelve</span><span class="sxs-lookup"><span data-stu-id="dd70f-426">Which returns</span></span>

  <pre>
   Identity     : International 
   OnlinePstnUsages     : {US and Canada, International}     
   Description      :  
   RouteType        : BYOT
  </pre>

4. <span data-ttu-id="dd70f-427">Asigne la Directiva de enrutamiento de voz al usuario "John Woods" con el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="dd70f-427">Assign the voice routing policy to the user "John Woods" using the following command.</span></span>

   ```
   Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions”
   ```

   <span data-ttu-id="dd70f-428">A continuación, verifique la asignación con el comando:</span><span class="sxs-lookup"><span data-stu-id="dd70f-428">Then verify the assignment using the command:</span></span> 

   ```
   Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
   ```
   <span data-ttu-id="dd70f-429">Que devuelve:</span><span class="sxs-lookup"><span data-stu-id="dd70f-429">Which returns:</span></span>

<pre>
    OnlineVoiceRoutingPolicy
    ------------------------
    No Restrictions
</pre>

<span data-ttu-id="dd70f-430">El resultado es que la política de voz aplicada a las llamadas de John Woods no tiene restricciones, y seguirá la lógica de enrutamiento de llamadas disponible para las llamadas de Estados Unidos, Canadá e internacionales.</span><span class="sxs-lookup"><span data-stu-id="dd70f-430">The result is that the voice policy applied to John Woods’ calls is unrestricted, and will follow the logic of call routing available for US, Canada, and International calling.</span></span>

## <a name="set-microsoft-teams-as-the-preferred-calling-client-for-users"></a><span data-ttu-id="dd70f-431">Establecer Microsoft Teams como el cliente de llamadas preferido para los usuarios</span><span class="sxs-lookup"><span data-stu-id="dd70f-431">Set Microsoft Teams as the preferred calling client for users</span></span>

<span data-ttu-id="dd70f-432">El enrutamiento directo solo enruta las llamadas a y desde los usuarios si usan el cliente de Teams.</span><span class="sxs-lookup"><span data-stu-id="dd70f-432">Direct Routing only routes calls to and from users if they use the Teams client.</span></span> <span data-ttu-id="dd70f-433">Si su organización solo usa Teams, se recomienda establecer el modo "solo equipos" en la Directiva de actualización.</span><span class="sxs-lookup"><span data-stu-id="dd70f-433">If your organization only uses Teams, setting "Teams Only" mode in upgrade policy is recommended.</span></span> <span data-ttu-id="dd70f-434">Si su organización usa Skype empresarial Server o Skype empresarial online, consulte el artículo siguiente para obtener más información y seleccione la opción adecuada: comprender el viaje de coexistencia [y actualización de Skype empresarial y Teams](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span><span class="sxs-lookup"><span data-stu-id="dd70f-434">If you organization uses Skype for Business Server or Skype for Business Online, see the following article for more information and select the appropriate option: [Understand coexistence and upgrade journey for Skype for Business and Teams](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span></span> 


## <a name="see-also"></a><span data-ttu-id="dd70f-435">Vea también</span><span class="sxs-lookup"><span data-stu-id="dd70f-435">See also</span></span>

[<span data-ttu-id="dd70f-436">Planear el enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="dd70f-436">Plan Direct Routing</span></span>](direct-routing-plan.md)
