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
- M365-voice
appliesto:
- Microsoft Teams
description: Aprenda a configurar el enrutamiento directo de Microsoft Phone System.
ms.openlocfilehash: 8cdebcf9ae01a362c883ed5e51b0c883c4ea0d44
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992597"
---
# <a name="configure-direct-routing"></a><span data-ttu-id="8086d-103">Configurar el enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="8086d-103">Configure Direct Routing</span></span>

> [!Tip]
> <span data-ttu-id="8086d-104">Vea la siguiente sesión para obtener información sobre las ventajas del enrutamiento directo, cómo planearlo y cómo implementarlo: [enrutamiento directo en Microsoft Teams](https://aka.ms/teams-direct-routing)</span><span class="sxs-lookup"><span data-stu-id="8086d-104">Watch the following session to learn about the benefits of Direct Routing, how to plan for it, and how to deploy it: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing)</span></span>

<span data-ttu-id="8086d-105">Si aún no lo ha hecho, lea [planear el enrutamiento directo](direct-routing-plan.md) de los requisitos previos y revisar otros pasos que debe realizar antes de configurar la red del sistema de Microsoft Phone.</span><span class="sxs-lookup"><span data-stu-id="8086d-105">If you have not already done so, read [Plan Direct Routing](direct-routing-plan.md) for prerequisites and to review other steps you’ll need to take before you configure your Microsoft Phone System network.</span></span> 

<span data-ttu-id="8086d-106">En este artículo se describe cómo configurar el enrutamiento directo de Microsoft Phone System.</span><span class="sxs-lookup"><span data-stu-id="8086d-106">This article describes how to configure Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="8086d-107">Explica cómo emparejar un controlador de borde de sesión (SBC) compatible con el enrutamiento directo y cómo configurar los usuarios de Microsoft Teams para que usen el enrutamiento directo para conectarse a la red de telefonía pública conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="8086d-107">It details how to pair a supported Session Border Controller (SBC) to Direct Routing and how to configure Microsoft Teams users to use Direct Routing to connect to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="8086d-108">Para completar los pasos que se explican en este artículo, los administradores deben estar familiarizados con los cmdlets de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8086d-108">To complete the steps explained in this article, administrators need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="8086d-109">Para obtener más información sobre cómo usar PowerShell, consulte [configurar el equipo para Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="8086d-109">For more information about using PowerShell, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 

<span data-ttu-id="8086d-110">Le recomendamos que confirme que su SBC ya se ha configurado tal y como recomienda su proveedor de SBC:</span><span class="sxs-lookup"><span data-stu-id="8086d-110">We recommend that you confirm that your SBC has already been configured as recommended by your SBC vendor:</span></span> 

- [<span data-ttu-id="8086d-111">Documentación de la implementación de AudioCodes</span><span class="sxs-lookup"><span data-stu-id="8086d-111">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="8086d-112">Documentación de implementación de Oracle</span><span class="sxs-lookup"><span data-stu-id="8086d-112">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="8086d-113">Documentación de implementación de comunicaciones de la cinta</span><span class="sxs-lookup"><span data-stu-id="8086d-113">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="8086d-114">Documentación de la implementación de TE-Systems (anynode)</span><span class="sxs-lookup"><span data-stu-id="8086d-114">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)

<span data-ttu-id="8086d-115">Puede configurar el sistema de Microsoft Phone y permitir que los usuarios usen el enrutamiento directo y, a continuación, configurar Microsoft Teams como el cliente de llamadas preferido completando los siguientes procedimientos:</span><span class="sxs-lookup"><span data-stu-id="8086d-115">You can configure your Microsoft Phone System and enable users to use Direct Routing, then set up Microsoft Teams as the preferred calling client by completing the following procedures:</span></span> 

- [<span data-ttu-id="8086d-116">Emparejar el SBC con un sistema telefónico de Microsoft y validar el emparejamiento</span><span class="sxs-lookup"><span data-stu-id="8086d-116">Pair the SBC with a Microsoft Phone System and validate the pairing</span></span>](#pair-the-sbc-to-the-direct-routing-service-of-phone-system)
- [<span data-ttu-id="8086d-117">Habilitar a los usuarios para el servicio de enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="8086d-117">Enable users for Direct Routing Service</span></span>](#enable-users-for-direct-routing-service)
- <span data-ttu-id="8086d-118">Asegúrese de que Microsoft Teams es el cliente de llamadas preferido para los usuarios</span><span class="sxs-lookup"><span data-stu-id="8086d-118">Ensure that Microsoft Teams is the preferred calling client for the users</span></span>

## <a name="pair-the-sbc-to-the-direct-routing-service-of-phone-system"></a><span data-ttu-id="8086d-119">Emparejar la SBC al servicio de enrutamiento directo del sistema telefónico</span><span class="sxs-lookup"><span data-stu-id="8086d-119">Pair the SBC to the Direct Routing Service of Phone System</span></span> 

<span data-ttu-id="8086d-120">Estos son los tres pasos de alto nivel que permiten conectar, o emparejar, la SBC a la interfaz de enrutamiento directo:</span><span class="sxs-lookup"><span data-stu-id="8086d-120">The following are the three high-level steps to let you connect, or pair, the SBC to the Direct Routing interface:</span></span> 

- <span data-ttu-id="8086d-121">Conectarse al centro **de administración de Skype empresarial online** con PowerShell</span><span class="sxs-lookup"><span data-stu-id="8086d-121">Connect to **Skype for Business Online** admin center using PowerShell</span></span> 
- <span data-ttu-id="8086d-122">Emparejar la SBC</span><span class="sxs-lookup"><span data-stu-id="8086d-122">Pair the SBC</span></span> 
- <span data-ttu-id="8086d-123">Validar el emparejamiento</span><span class="sxs-lookup"><span data-stu-id="8086d-123">Validate the pairing</span></span> 

### <a name="connect-to-skype-for-business-online-by-using-powershell"></a><span data-ttu-id="8086d-124">Conectarse a Skype empresarial online con PowerShell</span><span class="sxs-lookup"><span data-stu-id="8086d-124">Connect to Skype for Business Online by using PowerShell</span></span> 

<span data-ttu-id="8086d-125">Puede usar una sesión de PowerShell conectada al espacio empresarial para emparejar el SBC a la interfaz de enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="8086d-125">You can use a PowerShell session connected to the tenant to pair the SBC to the Direct Routing interface.</span></span> <span data-ttu-id="8086d-126">Para abrir una sesión de PowerShell, siga los pasos descritos en [configurar el equipo para Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="8086d-126">To open a PowerShell session, please follow the steps outlined in [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 
 
<span data-ttu-id="8086d-127">Después de establecer una sesión de PowerShell remota, compruebe que puede ver los comandos para administrar la SBC.</span><span class="sxs-lookup"><span data-stu-id="8086d-127">After you establish a remote PowerShell session, please validate that you can see the commands to manage the SBC.</span></span> <span data-ttu-id="8086d-128">Para validar los comandos, escriba o copie y pegue lo siguiente en la sesión de PowerShell y presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="8086d-128">To validate the commands, type or copy/paste in the following in the PowerShell session and press Enter:</span></span> 

```PowerShell
Get-Command *onlinePSTNGateway*
```

<span data-ttu-id="8086d-129">El comando devolverá las cuatro funciones mostradas aquí que le permitirán administrar el SBC.</span><span class="sxs-lookup"><span data-stu-id="8086d-129">Your command will return the four functions shown here that will let you manage the SBC.</span></span> 

<pre>
CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
</pre>   


### <a name="pair-the-sbc-to-the-tenant"></a><span data-ttu-id="8086d-130">Emparejar el SBC con el inquilino</span><span class="sxs-lookup"><span data-stu-id="8086d-130">Pair the SBC to the tenant</span></span> 

<span data-ttu-id="8086d-131">Para emparejar el SBC con el inquilino, en la sesión de PowerShell escriba lo siguiente y presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="8086d-131">To pair the SBC to the tenant, in the PowerShell session type the following and press Enter:</span></span> 

```PowerShell
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignallingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true 
```
  > [!NOTE]
  > 1. <span data-ttu-id="8086d-132">Se recomienda establecer un límite máximo de llamadas en la SBC mediante la información que se puede encontrar en la documentación de SBC.</span><span class="sxs-lookup"><span data-stu-id="8086d-132">We highly recommend setting a maximum call limit in the SBC, using information that can be found in the SBC documentation.</span></span> <span data-ttu-id="8086d-133">El límite desencadenará una notificación si el SBC está en el nivel de capacidad.</span><span class="sxs-lookup"><span data-stu-id="8086d-133">The limit will trigger a notification if the SBC is at the capacity level.</span></span>
  > 2. <span data-ttu-id="8086d-134">Solo puede emparejar el SBC si la parte de dominio de su FQDN coincide con uno de los dominios registrados en su inquilino \*, excepto. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="8086d-134">You can only pair the SBC if the domain portion of its FQDN matches one of the domains registered in your tenant, except \*.onmicrosoft.com.</span></span> <span data-ttu-id="8086d-135">No \*se admite el uso de nombres de dominio. onmicrosoft.com para el nombre FQDN de SBC.</span><span class="sxs-lookup"><span data-stu-id="8086d-135">Using \*.onmicrosoft.com domain names is not supported for the SBC FQDN name.</span></span> <span data-ttu-id="8086d-136">Por ejemplo, si tiene dos nombres de dominio:</span><span class="sxs-lookup"><span data-stu-id="8086d-136">For example, if you have two domain names:</span></span><br/><br/>
  > <span data-ttu-id="8086d-137">**contoso**. com</span><span class="sxs-lookup"><span data-stu-id="8086d-137">**contoso**.com</span></span><br/><span data-ttu-id="8086d-138">**contoso**. onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="8086d-138">**contoso**.onmicrosoft.com</span></span><br/><br/>
  > <span data-ttu-id="8086d-139">Para el nombre de SBC, puede usar el nombre sbc.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="8086d-139">For the SBC name, you can use the name sbc.contoso.com.</span></span> <span data-ttu-id="8086d-140">Si intenta emparejar la SBC con un nombre SBC. contoso. ABC, el sistema no le permitirá, ya que el dominio no pertenece a este inquilino.</span><span class="sxs-lookup"><span data-stu-id="8086d-140">If you try to pair the SBC with a name sbc.contoso.abc, the system will not let you, as the domain is not owned by this tenant.</span></span><br/>
  > <span data-ttu-id="8086d-141">Además del dominio registrado en su inquilino, es importante que haya un usuario con ese dominio y una licencia de E3 o E5 asignada.</span><span class="sxs-lookup"><span data-stu-id="8086d-141">In addition to the domain registered in your tenant, it is important that there is a user with that domain and an assigned E3 or E5 license.</span></span> <span data-ttu-id="8086d-142">De lo contrario, recibirá el siguiente error:</span><span class="sxs-lookup"><span data-stu-id="8086d-142">If not, you will receive the following error:</span></span><br/>
  <span data-ttu-id="8086d-143">`Can not use the “sbc.contoso.com” domain as it was not configured for this tenant`.</span><span class="sxs-lookup"><span data-stu-id="8086d-143"></span></span>

```PowerShell
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignallingPort 5067 -MaxConcurrentSessions 100 
```
<span data-ttu-id="8086d-144">Devuelve</span><span class="sxs-lookup"><span data-stu-id="8086d-144">Returns:</span></span>
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
<span data-ttu-id="8086d-145">Hay opciones adicionales que se pueden establecer durante el proceso de emparejamiento.</span><span class="sxs-lookup"><span data-stu-id="8086d-145">There are additional options that can be set during the pairing process.</span></span> <span data-ttu-id="8086d-146">En el ejemplo anterior, sin embargo, solo se muestran los parámetros mínimos necesarios.</span><span class="sxs-lookup"><span data-stu-id="8086d-146">In the previous example, however, only the minimum required parameters are shown.</span></span> 
 
<span data-ttu-id="8086d-147">En la tabla siguiente se enumeran los parámetros adicionales que puede usar para establecer ```New-CsOnlinePstnGateway```parámetros para.</span><span class="sxs-lookup"><span data-stu-id="8086d-147">The following table lists the additional parameters that you can use in setting parameters for ```New-CsOnlinePstnGateway```.</span></span>

|<span data-ttu-id="8086d-148">¿Obligatorio?</span><span class="sxs-lookup"><span data-stu-id="8086d-148">Required?</span></span>|<span data-ttu-id="8086d-149">Nombre</span><span class="sxs-lookup"><span data-stu-id="8086d-149">Name</span></span>|<span data-ttu-id="8086d-150">Descripción</span><span class="sxs-lookup"><span data-stu-id="8086d-150">Description</span></span>|<span data-ttu-id="8086d-151">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="8086d-151">Default</span></span>|<span data-ttu-id="8086d-152">Valores posibles</span><span class="sxs-lookup"><span data-stu-id="8086d-152">Possible values</span></span>|<span data-ttu-id="8086d-153">Tipo y restricciones</span><span class="sxs-lookup"><span data-stu-id="8086d-153">Type and restrictions</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8086d-154">Sí</span><span class="sxs-lookup"><span data-stu-id="8086d-154">Yes</span></span>|<span data-ttu-id="8086d-155">FQDN</span><span class="sxs-lookup"><span data-stu-id="8086d-155">FQDN</span></span>|<span data-ttu-id="8086d-156">El nombre FQDN de SBC</span><span class="sxs-lookup"><span data-stu-id="8086d-156">The FQDN name of the SBC</span></span> |<span data-ttu-id="8086d-157">Ninguna</span><span class="sxs-lookup"><span data-stu-id="8086d-157">None</span></span>|<span data-ttu-id="8086d-158">NoneFQDN nombre, limitar 63 caracteres</span><span class="sxs-lookup"><span data-stu-id="8086d-158">NoneFQDN name, limit 63 characters</span></span>|<span data-ttu-id="8086d-159">Cadena, lista de caracteres permitidos y no permitidos en las [convenciones de nomenclatura de Active Directory para equipos, dominios, sitios y unidades organizativas](https://support.microsoft.com/help/909264)</span><span class="sxs-lookup"><span data-stu-id="8086d-159">String, list of allowed and disallowed characters on [Naming conventions in Active Directory for computers, domains, sites, and OUs](https://support.microsoft.com/help/909264)</span></span>|
|<span data-ttu-id="8086d-160">No</span><span class="sxs-lookup"><span data-stu-id="8086d-160">No</span></span>|<span data-ttu-id="8086d-161">MediaBypass</span><span class="sxs-lookup"><span data-stu-id="8086d-161">MediaBypass</span></span> |<span data-ttu-id="8086d-162">El parámetro indicado para SBC admite la omisión de medios y el administrador quiere usarlo.</span><span class="sxs-lookup"><span data-stu-id="8086d-162">Parameter indicated of the SBC supports Media Bypass and the administrator wants to use it.</span></span>|<span data-ttu-id="8086d-163">Ninguna</span><span class="sxs-lookup"><span data-stu-id="8086d-163">None</span></span>|<span data-ttu-id="8086d-164">Verdadero</span><span class="sxs-lookup"><span data-stu-id="8086d-164">True</span></span><br/><span data-ttu-id="8086d-165">Falso</span><span class="sxs-lookup"><span data-stu-id="8086d-165">False</span></span>|<span data-ttu-id="8086d-166">Boolean</span><span class="sxs-lookup"><span data-stu-id="8086d-166">Boolean</span></span>|
|<span data-ttu-id="8086d-167">Sí</span><span class="sxs-lookup"><span data-stu-id="8086d-167">Yes</span></span>|<span data-ttu-id="8086d-168">SipSignallingPort</span><span class="sxs-lookup"><span data-stu-id="8086d-168">SipSignallingPort</span></span> |<span data-ttu-id="8086d-169">Puerto de escucha usado para comunicarse con los servicios de enrutamiento directo mediante el protocolo seguridad de la capa de transporte (TLS).</span><span class="sxs-lookup"><span data-stu-id="8086d-169">Listening port used for communicating with Direct Routing services by using the Transport Layer Security (TLS) protocol.</span></span>|<span data-ttu-id="8086d-170">Ninguna</span><span class="sxs-lookup"><span data-stu-id="8086d-170">None</span></span>|<span data-ttu-id="8086d-171">Cualquier puerto</span><span class="sxs-lookup"><span data-stu-id="8086d-171">Any port</span></span>|<span data-ttu-id="8086d-172">0 a 65535</span><span class="sxs-lookup"><span data-stu-id="8086d-172">0 to 65535</span></span> |
|<span data-ttu-id="8086d-173">No</span><span class="sxs-lookup"><span data-stu-id="8086d-173">No</span></span>|<span data-ttu-id="8086d-174">FailoverTimeSeconds</span><span class="sxs-lookup"><span data-stu-id="8086d-174">FailoverTimeSeconds</span></span> |<span data-ttu-id="8086d-175">Cuando se establece en 10 (valor predeterminado), las llamadas salientes que no responden a la puerta de enlace en 10 segundos se enrutan al siguiente tronco disponible; Si no hay más troncos, la llamada se elimina automáticamente.</span><span class="sxs-lookup"><span data-stu-id="8086d-175">When set to 10 (default value), outbound calls that are not answered by the gateway within 10 seconds are routed to the next available trunk; if there are no additional trunks, then the call is automatically dropped.</span></span> <span data-ttu-id="8086d-176">En una organización con redes y respuestas de puerta de enlace lentas, esto puede tener como resultado que las llamadas se pierdan innecesariamente.</span><span class="sxs-lookup"><span data-stu-id="8086d-176">In an organization with slow networks and gateway responses, that could potentially result in calls being dropped unnecessarily.</span></span> <span data-ttu-id="8086d-177">El valor predeterminado es 10.</span><span class="sxs-lookup"><span data-stu-id="8086d-177">The default value is 10.</span></span>|<span data-ttu-id="8086d-178">base10</span><span class="sxs-lookup"><span data-stu-id="8086d-178">10</span></span>|<span data-ttu-id="8086d-179">Número</span><span class="sxs-lookup"><span data-stu-id="8086d-179">Number</span></span>|<span data-ttu-id="8086d-180">ENT</span><span class="sxs-lookup"><span data-stu-id="8086d-180">Int</span></span>|
|<span data-ttu-id="8086d-181">No</span><span class="sxs-lookup"><span data-stu-id="8086d-181">No</span></span>|<span data-ttu-id="8086d-182">ForwardCallHistory</span><span class="sxs-lookup"><span data-stu-id="8086d-182">ForwardCallHistory</span></span> |<span data-ttu-id="8086d-183">Indica si la información del historial de llamadas se reenviará a través del tronco.</span><span class="sxs-lookup"><span data-stu-id="8086d-183">Indicates whether call history information will be forwarded through the trunk.</span></span> <span data-ttu-id="8086d-184">Si está habilitado, el proxy RTC de Office 365 envía dos encabezados: historial-información y referencia.</span><span class="sxs-lookup"><span data-stu-id="8086d-184">If enabled, the Office 365 PSTN Proxy sends two headers: History-info and Referred-By.</span></span> <span data-ttu-id="8086d-185">El valor predeterminado es **false** ($false).</span><span class="sxs-lookup"><span data-stu-id="8086d-185">The default value is **False** ($False).</span></span> |<span data-ttu-id="8086d-186">Falso</span><span class="sxs-lookup"><span data-stu-id="8086d-186">False</span></span>|<span data-ttu-id="8086d-187">Verdadero</span><span class="sxs-lookup"><span data-stu-id="8086d-187">True</span></span><br/><span data-ttu-id="8086d-188">Falso</span><span class="sxs-lookup"><span data-stu-id="8086d-188">False</span></span>|<span data-ttu-id="8086d-189">Boolean</span><span class="sxs-lookup"><span data-stu-id="8086d-189">Boolean</span></span>|
|<span data-ttu-id="8086d-190">No</span><span class="sxs-lookup"><span data-stu-id="8086d-190">No</span></span>|<span data-ttu-id="8086d-191">ForwardPAI</span><span class="sxs-lookup"><span data-stu-id="8086d-191">ForwardPAI</span></span>|<span data-ttu-id="8086d-192">Indica si el encabezado P-Asserted-Identity (PAI) se reenviará junto con la llamada.</span><span class="sxs-lookup"><span data-stu-id="8086d-192">Indicates whether the P-Asserted-Identity (PAI) header will be forwarded along with the call.</span></span> <span data-ttu-id="8086d-193">El encabezado PAI proporciona un método para comprobar la identidad de la persona que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="8086d-193">The PAI header provides a way to verify the identity of the caller.</span></span> <span data-ttu-id="8086d-194">Si Habilitaste, también se enviará el encabezado privacidad: ID.</span><span class="sxs-lookup"><span data-stu-id="8086d-194">If enabled the Privacy:ID header will also be sent.</span></span> <span data-ttu-id="8086d-195">El valor predeterminado es **false** ($false).</span><span class="sxs-lookup"><span data-stu-id="8086d-195">The default value is **False** ($False).</span></span>|<span data-ttu-id="8086d-196">Falso</span><span class="sxs-lookup"><span data-stu-id="8086d-196">False</span></span>|<span data-ttu-id="8086d-197">Verdadero</span><span class="sxs-lookup"><span data-stu-id="8086d-197">True</span></span><br/><span data-ttu-id="8086d-198">Falso</span><span class="sxs-lookup"><span data-stu-id="8086d-198">False</span></span>|<span data-ttu-id="8086d-199">Boolean</span><span class="sxs-lookup"><span data-stu-id="8086d-199">Boolean</span></span>|
|<span data-ttu-id="8086d-200">No</span><span class="sxs-lookup"><span data-stu-id="8086d-200">No</span></span>|<span data-ttu-id="8086d-201">SendSIPOptions</span><span class="sxs-lookup"><span data-stu-id="8086d-201">SendSIPOptions</span></span> |<span data-ttu-id="8086d-202">Define si un SBC o no enviará las opciones de SIP.</span><span class="sxs-lookup"><span data-stu-id="8086d-202">Defines if an SBC will or will not send the SIP options.</span></span> <span data-ttu-id="8086d-203">Si se deshabilita, la SBC se excluirá del sistema de supervisión y alertas.</span><span class="sxs-lookup"><span data-stu-id="8086d-203">If disabled, the SBC will be excluded from Monitoring and Alerting system.</span></span> <span data-ttu-id="8086d-204">Le recomendamos encarecidamente que habilite las opciones de SIP.</span><span class="sxs-lookup"><span data-stu-id="8086d-204">We highly recommend that you enable SIP options.</span></span> <span data-ttu-id="8086d-205">El valor predeterminado es **true**.</span><span class="sxs-lookup"><span data-stu-id="8086d-205">Default value is **True**.</span></span> |<span data-ttu-id="8086d-206">True</span><span class="sxs-lookup"><span data-stu-id="8086d-206">True</span></span>|<span data-ttu-id="8086d-207">True</span><span class="sxs-lookup"><span data-stu-id="8086d-207">True</span></span><br/><span data-ttu-id="8086d-208">Falso</span><span class="sxs-lookup"><span data-stu-id="8086d-208">False</span></span>|<span data-ttu-id="8086d-209">Boolean</span><span class="sxs-lookup"><span data-stu-id="8086d-209">Boolean</span></span>|
|<span data-ttu-id="8086d-210">No</span><span class="sxs-lookup"><span data-stu-id="8086d-210">No</span></span>|<span data-ttu-id="8086d-211">MaxConcurrentSessions</span><span class="sxs-lookup"><span data-stu-id="8086d-211">MaxConcurrentSessions</span></span> |<span data-ttu-id="8086d-212">Utilizado por el sistema de alertas.</span><span class="sxs-lookup"><span data-stu-id="8086d-212">Used by alerting system.</span></span> <span data-ttu-id="8086d-213">Cuando se establece un valor, el sistema de alertas generará una alerta para el administrador de inquilinos cuando el número de sesión simultánea sea 90% o superior a este valor.</span><span class="sxs-lookup"><span data-stu-id="8086d-213">When any value is set, the alerting system will generate an alert to the tenant administrator when the number of concurrent session is 90% or higher than this value.</span></span> <span data-ttu-id="8086d-214">Si el parámetro no se establece, no se generan alertas.</span><span class="sxs-lookup"><span data-stu-id="8086d-214">If parameter is not set, the alerts are not generated.</span></span> <span data-ttu-id="8086d-215">Sin embargo, el sistema de supervisión informará de la cantidad de sesiones simultáneas cada 24 horas.</span><span class="sxs-lookup"><span data-stu-id="8086d-215">However, the monitoring system will report number of concurrent session every 24 hours.</span></span> |<span data-ttu-id="8086d-216">Valor</span><span class="sxs-lookup"><span data-stu-id="8086d-216">Null</span></span>|<span data-ttu-id="8086d-217">Valor</span><span class="sxs-lookup"><span data-stu-id="8086d-217">Null</span></span><br/><span data-ttu-id="8086d-218">de 1 a 100.000</span><span class="sxs-lookup"><span data-stu-id="8086d-218">1 to 100,000</span></span> ||
|<span data-ttu-id="8086d-219">No</span><span class="sxs-lookup"><span data-stu-id="8086d-219">No</span></span>|<span data-ttu-id="8086d-220">MediaRelayRoutingLocationOverride</span><span class="sxs-lookup"><span data-stu-id="8086d-220">MediaRelayRoutingLocationOverride</span></span> |<span data-ttu-id="8086d-221">Permite seleccionar la ruta de acceso para los medios de forma manual.</span><span class="sxs-lookup"><span data-stu-id="8086d-221">Allows selecting path for media manually.</span></span> <span data-ttu-id="8086d-222">El enrutamiento directo asigna un centro de recursos para la ruta de medios según la IP pública de SBC.</span><span class="sxs-lookup"><span data-stu-id="8086d-222">Direct Routing assigns a datacenter for media path based on the public IP of the SBC.</span></span> <span data-ttu-id="8086d-223">Siempre seleccionamos el centro de recursos de SBC más cercano.</span><span class="sxs-lookup"><span data-stu-id="8086d-223">We always select closest to the SBC datacenter.</span></span> <span data-ttu-id="8086d-224">Sin embargo, en algunos casos, una IP pública de, por ejemplo, un rango de Estados Unidos se puede asignar a un SBC ubicado en Europa.</span><span class="sxs-lookup"><span data-stu-id="8086d-224">However, in some cases a public IP from for example a US range can be assigned to an SBC located in Europe.</span></span> <span data-ttu-id="8086d-225">En este caso, usaremos una ruta de medios no óptima.</span><span class="sxs-lookup"><span data-stu-id="8086d-225">In this case we will be using not optimal media path.</span></span> <span data-ttu-id="8086d-226">Este parámetro permite establecer manualmente la región preferida para el tráfico de medios.</span><span class="sxs-lookup"><span data-stu-id="8086d-226">This parameter allows manually set the preferred region for media traffic.</span></span> <span data-ttu-id="8086d-227">Solo se recomienda establecer este parámetro si los registros de la llamada indican claramente que la asignación automática del centro de recursos para la ruta multimedia no asigna el más cercano al centro de recursos de SBC.</span><span class="sxs-lookup"><span data-stu-id="8086d-227">We only recommend setting this parameter if the call logs clearly indicate that automatic assignment of the datacenter for media path does not assign the closest to the SBC datacenter.</span></span> |<span data-ttu-id="8086d-228">Ninguna</span><span class="sxs-lookup"><span data-stu-id="8086d-228">None</span></span>|<span data-ttu-id="8086d-229">Códigos de países en formato ISO</span><span class="sxs-lookup"><span data-stu-id="8086d-229">Country codes in ISO format</span></span>||
|<span data-ttu-id="8086d-230">No</span><span class="sxs-lookup"><span data-stu-id="8086d-230">No</span></span>|<span data-ttu-id="8086d-231">Habilitado</span><span class="sxs-lookup"><span data-stu-id="8086d-231">Enabled</span></span>|<span data-ttu-id="8086d-232">Permite habilitar esta SBC para llamadas salientes.</span><span class="sxs-lookup"><span data-stu-id="8086d-232">Used to enable this SBC for outbound calls.</span></span> <span data-ttu-id="8086d-233">Puede usarse para quitar temporalmente el SBC, mientras se actualiza o durante el mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="8086d-233">Can be used to temporarily remove the SBC, while it is being updated or during maintenance.</span></span> |<span data-ttu-id="8086d-234">Falso</span><span class="sxs-lookup"><span data-stu-id="8086d-234">False</span></span>|<span data-ttu-id="8086d-235">Verdadero</span><span class="sxs-lookup"><span data-stu-id="8086d-235">True</span></span><br/><span data-ttu-id="8086d-236">Falso</span><span class="sxs-lookup"><span data-stu-id="8086d-236">False</span></span>|<span data-ttu-id="8086d-237">Boolean</span><span class="sxs-lookup"><span data-stu-id="8086d-237">Boolean</span></span>|
 
### <a name="verify-the-sbc-pairing"></a><span data-ttu-id="8086d-238">Comprobar el emparejamiento de SBC</span><span class="sxs-lookup"><span data-stu-id="8086d-238">Verify the SBC pairing</span></span> 

<span data-ttu-id="8086d-239">Compruebe la conexión:</span><span class="sxs-lookup"><span data-stu-id="8086d-239">Verify the connection:</span></span> 
- <span data-ttu-id="8086d-240">Compruebe si la SBC está en la lista de SBCs emparejado.</span><span class="sxs-lookup"><span data-stu-id="8086d-240">Check if the SBC is on the list of paired SBCs.</span></span> 
- <span data-ttu-id="8086d-241">Validar las opciones del SIP.</span><span class="sxs-lookup"><span data-stu-id="8086d-241">Validate SIP Options.</span></span> 
 
#### <a name="validate-if-the-sbc-is-on-the-list-of-paired-sbcs"></a><span data-ttu-id="8086d-242">Validar si el SBC está en la lista de SBCs emparejado</span><span class="sxs-lookup"><span data-stu-id="8086d-242">Validate if the SBC is on the list of paired SBCs</span></span> 

<span data-ttu-id="8086d-243">Después de emparejar el SBC, valide que la SBC esté presente en la lista de SBCs emparejada ejecutando el siguiente comando en una sesión remota de PowerShell:`Get-CSOnlinePSTNGateway`</span><span class="sxs-lookup"><span data-stu-id="8086d-243">After you pair the SBC, validate that the SBC is present in the list of paired SBCs by running the following command in a remote PowerShell session: `Get-CSOnlinePSTNGateway`</span></span>

<span data-ttu-id="8086d-244">La puerta de enlace emparejada debe aparecer en la lista, tal y como se muestra en el ejemplo siguiente, y comprobar que el parámetro **Enabled** muestra el valor **true**.</span><span class="sxs-lookup"><span data-stu-id="8086d-244">The paired gateway should appear in the list as shown in the example below, and verify that the **Enabled** parameter  displays a value of **True**.</span></span> <span data-ttu-id="8086d-245">Introducir</span><span class="sxs-lookup"><span data-stu-id="8086d-245">Enter:</span></span>

```PowerShell
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```
<span data-ttu-id="8086d-246">Que devuelve:</span><span class="sxs-lookup"><span data-stu-id="8086d-246">Which returns:</span></span>
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

#### <a name="validate-sip-options-flow"></a><span data-ttu-id="8086d-247">Validar el flujo de opciones del SIP</span><span class="sxs-lookup"><span data-stu-id="8086d-247">Validate SIP Options flow</span></span> 

<span data-ttu-id="8086d-248">Para validar el emparejamiento mediante las opciones de SIP salientes, use la interfaz de administración de SBC y confirme que el SBC recibe 200 respuestas correctas a sus mensajes de opciones salientes.</span><span class="sxs-lookup"><span data-stu-id="8086d-248">To validate the pairing using outgoing SIP Options, use the SBC management interface and confirm that the SBC receives 200 OK responses to its outgoing OPTIONS messages.</span></span>

<span data-ttu-id="8086d-249">Cuando el enrutamiento directo ve opciones entrantes, empezará a enviar mensajes de opciones SIP salientes al FQDN de SBC configurado en el campo de encabezado de contacto en el mensaje opciones de entrada.</span><span class="sxs-lookup"><span data-stu-id="8086d-249">When Direct Routing sees incoming OPTIONS, it will start sending outgoing SIP Options messages to the SBC FQDN configured in the Contact header field in the incoming OPTIONS message.</span></span> 

<span data-ttu-id="8086d-250">Para validar el emparejamiento con las opciones del SIP entrante, use la interfaz de administración de SBC y vea que el SBC envía una respuesta a las opciones mensajes entrantes desde el enrutamiento directo y que el código de respuesta que envía es 200 aceptar.</span><span class="sxs-lookup"><span data-stu-id="8086d-250">To validate the pairing using incoming SIP Options, use the SBC management interface and see that the SBC sends a reply to the OPTIONS messages coming in from Direct Routing and that the response code it sends is 200 OK.</span></span>

## <a name="enable-users-for-direct-routing-service"></a><span data-ttu-id="8086d-251">Habilitar a los usuarios para el servicio de enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="8086d-251">Enable users for Direct Routing Service</span></span> 

<span data-ttu-id="8086d-252">Cuando esté listo para habilitar a los usuarios para el servicio de enrutamiento directo, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="8086d-252">When you are ready to enable users for the Direct Routing Service, follow these steps:</span></span> 

1. <span data-ttu-id="8086d-253">Cree un usuario en Office 365 y asigne una licencia de sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="8086d-253">Create a user in Office 365 and assign a phone system license.</span></span> 
2. <span data-ttu-id="8086d-254">Asegúrese de que el usuario se ha alojado en Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="8086d-254">Ensure that the user is homed in Skype for Business Online.</span></span> 
3. <span data-ttu-id="8086d-255">Configure el número de teléfono y habilite la telefonía IP empresarial y el buzón de voz.</span><span class="sxs-lookup"><span data-stu-id="8086d-255">Configure the phone number and enable enterprise voice and voicemail.</span></span> 
4. <span data-ttu-id="8086d-256">Configurar el enrutamiento de voz.</span><span class="sxs-lookup"><span data-stu-id="8086d-256">Configure voice routing.</span></span> <span data-ttu-id="8086d-257">La ruta se valida automáticamente.</span><span class="sxs-lookup"><span data-stu-id="8086d-257">The route is automatically validated.</span></span>

### <a name="create-a-user-in-office-365-and-assign-the-license"></a><span data-ttu-id="8086d-258">Crear un usuario en Office 365 y asignar la licencia</span><span class="sxs-lookup"><span data-stu-id="8086d-258">Create a user in Office 365 and assign the license</span></span> 

<span data-ttu-id="8086d-259">Hay dos opciones para crear un nuevo usuario en Office 365.</span><span class="sxs-lookup"><span data-stu-id="8086d-259">There are two options for creating a new user in Office 365.</span></span> <span data-ttu-id="8086d-260">Sin embargo, recomendamos que su organización seleccione y use una opción para evitar problemas de enrutamiento:</span><span class="sxs-lookup"><span data-stu-id="8086d-260">However, we recommend that your organization select and use one option to avoid routing issues:</span></span> 

- <span data-ttu-id="8086d-261">Crear el usuario en Active Directory local y sincronizar el usuario con la nube.</span><span class="sxs-lookup"><span data-stu-id="8086d-261">Create the user in on-premises Active Directory and sync the user to the cloud.</span></span> <span data-ttu-id="8086d-262">Consulte [integrar los directorios locales con Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span><span class="sxs-lookup"><span data-stu-id="8086d-262">See [Integrate your on-premises directories with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span></span>
- <span data-ttu-id="8086d-263">Cree el usuario directamente en el portal de administrador de Office 365.</span><span class="sxs-lookup"><span data-stu-id="8086d-263">Create the user directly in the Office 365 Administrator Portal.</span></span> <span data-ttu-id="8086d-264">Consulte [Agregar usuarios individualmente o de forma masiva a Office 365: ayuda de administración](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span><span class="sxs-lookup"><span data-stu-id="8086d-264">See [Add users individually or in bulk to Office 365 - Admin Help](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span> 

<span data-ttu-id="8086d-265">Si su implementación de Skype empresarial online coexiste con Skype empresarial 2015 o Lync 2010/2013 local, la única opción admitida es crear el usuario en Active Directory local y sincronizar el usuario con la nube (opción 1).</span><span class="sxs-lookup"><span data-stu-id="8086d-265">If your Skype for Business Online deployment co-exists with Skype for Business 2015 or Lync 2010/2013 on-premises, the only supported option is to create the user in on-premises Active Directory and sync the user to the cloud (Option 1).</span></span> 

<span data-ttu-id="8086d-266">Licencias requeridas:</span><span class="sxs-lookup"><span data-stu-id="8086d-266">Required licenses:</span></span> 

- <span data-ttu-id="8086d-267">Office 365 Enterprise E3 (incluidos SfB Plan2, Exchange Plan2 y Teams) + sistema telefónico</span><span class="sxs-lookup"><span data-stu-id="8086d-267">Office 365 Enterprise E3 (including SfB Plan2, Exchange Plan2, and Teams) + Phone System</span></span>
- <span data-ttu-id="8086d-268">Office 365 Enterprise E5 (incluidos SfB Plan2, Exchange Plan2, Teams y el sistema telefónico)</span><span class="sxs-lookup"><span data-stu-id="8086d-268">Office 365 Enterprise E5 (including SfB Plan2, Exchange Plan2, Teams, and Phone System)</span></span> 

<span data-ttu-id="8086d-269">Licencias opcionales:</span><span class="sxs-lookup"><span data-stu-id="8086d-269">Optional licenses:</span></span> 

- <span data-ttu-id="8086d-270">Plan de llamadas</span><span class="sxs-lookup"><span data-stu-id="8086d-270">Calling Plan</span></span> 
- <span data-ttu-id="8086d-271">Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="8086d-271">Audio Conferencing</span></span> 

### <a name="ensure-that-the-user-is-homed-in-skype-for-business-online"></a><span data-ttu-id="8086d-272">Comprobar que el usuario se ha alojado en Skype empresarial online</span><span class="sxs-lookup"><span data-stu-id="8086d-272">Ensure that the user is homed in Skype for Business Online</span></span> 

<span data-ttu-id="8086d-273">El enrutamiento directo requiere que el usuario se base en Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="8086d-273">Direct Routing requires the user to be homed in Skype for Business Online.</span></span> <span data-ttu-id="8086d-274">Para comprobarlo, consulta el parámetro RegistrarPool.</span><span class="sxs-lookup"><span data-stu-id="8086d-274">You can check this by looking at the RegistrarPool parameter.</span></span> <span data-ttu-id="8086d-275">Debe tener un valor en el dominio infra.lync.com.</span><span class="sxs-lookup"><span data-stu-id="8086d-275">It needs to have a value in the infra.lync.com domain.</span></span>

1. <span data-ttu-id="8086d-276">Conéctese a PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="8086d-276">Connect to remote PowerShell.</span></span>
2. <span data-ttu-id="8086d-277">Emita el comando:</span><span class="sxs-lookup"><span data-stu-id="8086d-277">Issue the command:</span></span> 

```PowerShell
Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool
``` 

### <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a><span data-ttu-id="8086d-278">Configurar el número de teléfono y habilitar la telefonía IP empresarial y el buzón de voz</span><span class="sxs-lookup"><span data-stu-id="8086d-278">Configure the phone number and enable enterprise voice and voicemail</span></span> 

<span data-ttu-id="8086d-279">Una vez que haya creado el usuario y le haya asignado una licencia, el siguiente paso es configurar su número de teléfono y el buzón de voz.</span><span class="sxs-lookup"><span data-stu-id="8086d-279">After you have created the user and assigned a license, the next step is to configure their phone number and voicemail.</span></span> <span data-ttu-id="8086d-280">Esto se puede hacer en un solo paso.</span><span class="sxs-lookup"><span data-stu-id="8086d-280">This can be done in one step.</span></span> 

<span data-ttu-id="8086d-281">Para agregar el número de teléfono y habilitar el buzón de voz:</span><span class="sxs-lookup"><span data-stu-id="8086d-281">To add the phone number and enable for voicemail:</span></span>
 
1. <span data-ttu-id="8086d-282">Conectarse a una sesión de PowerShell remota.</span><span class="sxs-lookup"><span data-stu-id="8086d-282">Connect to a remote PowerShell session.</span></span> 
2. <span data-ttu-id="8086d-283">Escribe el comando:</span><span class="sxs-lookup"><span data-stu-id="8086d-283">Enter the command:</span></span> 
 
```PowerShell
Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<E.164 phone number>
```

<span data-ttu-id="8086d-284">Por ejemplo, para añadir un número de teléfono para el usuario "Spencer Low", tendría que escribir lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8086d-284">For example, to add a phone number for user "Spencer Low," you would enter the following:</span></span> 

```PowerShell
Set-CsUser -Identity "Spencer Low" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
```

<span data-ttu-id="8086d-285">El número de teléfono usado debe configurarse como un número de teléfono E. 164 completo con prefijo internacional.</span><span class="sxs-lookup"><span data-stu-id="8086d-285">The phone number used has to be configured as a full E.164 phone number with country code.</span></span> 

  > [!NOTE]
  > <span data-ttu-id="8086d-286">Si el número de teléfono del usuario se administra localmente, use el shell local de administración de Skype empresarial o el panel de control para configurar el número de teléfono del usuario.</span><span class="sxs-lookup"><span data-stu-id="8086d-286">If the user’s phone number is managed on premises, use on-premises Skype for Business Management Shell or Control Panel to configure the user's phone number.</span></span> 

### <a name="configure-voice-routing"></a><span data-ttu-id="8086d-287">Configurar el enrutamiento de voz</span><span class="sxs-lookup"><span data-stu-id="8086d-287">Configure Voice Routing</span></span> 

<span data-ttu-id="8086d-288">Microsoft Phone System tiene un mecanismo de enrutamiento que permite que se envíe una llamada a un SBC específico en función de lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8086d-288">Microsoft Phone System has a routing mechanism that allows a call to be sent to a specific SBC based on:</span></span> 

- <span data-ttu-id="8086d-289">Patrón de número denominado</span><span class="sxs-lookup"><span data-stu-id="8086d-289">Called number pattern</span></span> 
- <span data-ttu-id="8086d-290">Se denomina patrón de números + usuario específico que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="8086d-290">Called number pattern + Specific User who makes the call</span></span>
 
<span data-ttu-id="8086d-291">SBCs puede designarse como activo y como backup.</span><span class="sxs-lookup"><span data-stu-id="8086d-291">SBCs can be designated as active and backup.</span></span> <span data-ttu-id="8086d-292">Eso significa que cuando el SBC configurado como activo para este patrón de número o patrón de número + usuario específico, no está disponible, las llamadas se enrutarán a un SBC de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="8086d-292">That means when the SBC that is configured as active for this number pattern, or number pattern + specific user, is not available, then the calls will be routed to a backup SBC.</span></span>
 
<span data-ttu-id="8086d-293">El enrutamiento de llamadas consta de los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="8086d-293">Call routing is made up of the following elements:</span></span> 
- <span data-ttu-id="8086d-294">Directiva de enrutamiento de voz: contenedor para usos de RTC; puede asignarse a un usuario o a varios usuarios</span><span class="sxs-lookup"><span data-stu-id="8086d-294">Voice Routing Policy – container for PSTN Usages; can be assigned to a user or to multiple users</span></span> 
- <span data-ttu-id="8086d-295">Usos de RTC: contenedor de rutas de voz y usos de RTC; puede compartirse en diferentes directivas de enrutamiento de voz</span><span class="sxs-lookup"><span data-stu-id="8086d-295">PSTN Usages – container for Voice Routes and PSTN Usages; can be shared in different Voice Routing Policies</span></span> 
- <span data-ttu-id="8086d-296">Rutas de voz: patrón de número y conjunto de puertas de enlace RTC en línea para usarlas en las llamadas en las que el número de llamada coincide con el patrón</span><span class="sxs-lookup"><span data-stu-id="8086d-296">Voice Routes – number pattern and set of Online PSTN Gateways to use for calls where calling number matches the pattern</span></span> 
- <span data-ttu-id="8086d-297">Un puntero de puerta de enlace RTC en línea a un SBC también almacena la configuración que se aplica cuando la llamada se coloca a través de SBC, como reenvío de identidad de aserción de P (PAI) o códecs preferidos; se puede Agregar a las rutas de voz</span><span class="sxs-lookup"><span data-stu-id="8086d-297">Online PSTN Gateway - pointer to an SBC, also stores the configuration that is applied when call is placed via the SBC, such as forward P-Asserted-Identity (PAI) or Preferred Codecs; can be added to Voice Routes</span></span> 

#### <a name="creating-a-voice-routing-policy-with-one-pstn-usage"></a><span data-ttu-id="8086d-298">Crear una directiva de enrutamiento de voz con un uso de RTC</span><span class="sxs-lookup"><span data-stu-id="8086d-298">Creating a voice routing policy with one PSTN Usage</span></span> 

<span data-ttu-id="8086d-299">En el siguiente diagrama se muestran dos ejemplos de directivas de enrutamiento de voz en el flujo de llamadas.</span><span class="sxs-lookup"><span data-stu-id="8086d-299">The following diagram shows two examples of voice routing policies in call flow.</span></span>

<span data-ttu-id="8086d-300">**Flujo de llamadas 1 (a la izquierda):** Si un usuario hace una llamada a + 1 425 XXX XX XX ó + 1 206 XXX XX XX, la llamada se dirige a SBC sbc1.contoso.biz o sbc2.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="8086d-300">**Call Flow 1 (on the left):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="8086d-301">Si ni sbc1.contoso.biz ni sbc2.contoso.biz están disponibles, la llamada se interrumpe.</span><span class="sxs-lookup"><span data-stu-id="8086d-301">If neither sbc1.contoso.biz nor sbc2.contoso.biz are available, the call is dropped.</span></span> 

<span data-ttu-id="8086d-302">**Flujo de llamadas 2 (a la derecha):** Si un usuario hace una llamada a + 1 425 XXX XX XX ó + 1 206 XXX XX XX, la llamada se enruta primero a SBC sbc1.contoso.biz o sbc2.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="8086d-302">**Call Flow 2 (on the right):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is first routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="8086d-303">Si no hay ninguna SBC disponible, se intentará la ruta con prioridad más baja (sbc3.contoso.biz y sbc4.contoso.biz).</span><span class="sxs-lookup"><span data-stu-id="8086d-303">If neither SBC is available, the route with lower priority will be tried (sbc3.contoso.biz and sbc4.contoso.biz).</span></span> <span data-ttu-id="8086d-304">Si ninguno de los SBCs está disponible, la llamada se corta.</span><span class="sxs-lookup"><span data-stu-id="8086d-304">If none of the SBCs are available, the call is dropped.</span></span> 

![Muestra ejemplos de directiva de enrutamiento de voz](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

<span data-ttu-id="8086d-306">En ambos ejemplos, mientras se asignan prioridades a la ruta de voz, se prueba el SBCs en las rutas en orden aleatorio.</span><span class="sxs-lookup"><span data-stu-id="8086d-306">In both examples, while the Voice Route is assigned priorities, the SBCs in the routes are tried in random order.</span></span>

  > [!NOTE]
  > <span data-ttu-id="8086d-307">A menos que el usuario también tenga una licencia de plan de llamadas de Microsoft, las llamadas a cualquier número excepto los números que coincidan con los patrones + 1 425 XXX XX XX o + 1 206 XXX XX XX en la configuración de ejemplo se eliminan.</span><span class="sxs-lookup"><span data-stu-id="8086d-307">Unless the user also has a Microsoft Calling Plan license, calls to any number except numbers matching the patterns +1 425 XXX XX XX or +1 206 XXX XX XX in the example configuration are dropped.</span></span> <span data-ttu-id="8086d-308">Si el usuario tiene una licencia de plan de llamadas, la llamada se redirige automáticamente según las directivas del plan de llamadas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8086d-308">If the user has a Calling Plan license, the call is automatically routed according to the policies of the Microsoft Calling Plan.</span></span> 

<span data-ttu-id="8086d-309">El plan de llamadas de Microsoft se aplica automáticamente como la última ruta a todos los usuarios con la licencia de plan de llamadas de Microsoft y no requiere configuración de enrutamiento de llamadas adicional.</span><span class="sxs-lookup"><span data-stu-id="8086d-309">The Microsoft Calling Plan applies automatically as the last route to all users with the Microsoft Calling Plan license and does not require additional call routing configuration.</span></span>

<span data-ttu-id="8086d-310">En el ejemplo que se muestra en el siguiente diagrama, se agrega una ruta de voz para enviar llamadas a todos los demás números de Estados Unidos y Canadá (llamadas que van a denominarse patrón de números + 1 XXX XXX XX XX).</span><span class="sxs-lookup"><span data-stu-id="8086d-310">In the example shown in the following diagram, a voice route is added to send calls to all other US and Canadian number (calls that go to called number pattern +1 XXX XXX XX XX).</span></span>

![Muestra la Directiva de enrutamiento de voz con una tercera ruta](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

<span data-ttu-id="8086d-312">Para todas las demás llamadas, si un usuario tiene ambas licencias (Microsoft Phone System y Microsoft Call plan), se usa la ruta automática.</span><span class="sxs-lookup"><span data-stu-id="8086d-312">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), Automatic Route is used.</span></span> <span data-ttu-id="8086d-313">Si nada coincide con los patrones de número de las rutas de voz en línea creadas por el administrador, enrutar a través del plan de llamadas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8086d-313">If nothing matches the number patterns in the administrator-created online voice routes, route via Microsoft Calling Plan.</span></span>

<span data-ttu-id="8086d-314">Si el usuario solo tiene Microsoft Phone System, la llamada se elimina porque no hay disponibles reglas coincidentes.</span><span class="sxs-lookup"><span data-stu-id="8086d-314">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

  > [!NOTE]
  > <span data-ttu-id="8086d-315">El valor de prioridad para la ruta "otros + 1" no importa en este caso, ya que hay una sola ruta que coincide con el patrón + 1 XXX XXX XX XX.</span><span class="sxs-lookup"><span data-stu-id="8086d-315">The Priority value for route "Other +1" doesn’t matter in this case, as there is only one route that matches the pattern +1 XXX XXX XX XX.</span></span> <span data-ttu-id="8086d-316">Si un usuario llama a + 1 324 567 89 89 y tanto sbc5.contoso.biz como sbc6.contoso.biz no están disponibles, la llamada se cancela.</span><span class="sxs-lookup"><span data-stu-id="8086d-316">If a user makes a call to +1 324 567 89 89 and both sbc5.contoso.biz and sbc6.contoso.biz are unavailable, the call is dropped.</span></span>

<span data-ttu-id="8086d-317">En la tabla siguiente se resume la configuración mediante tres rutas de voz.</span><span class="sxs-lookup"><span data-stu-id="8086d-317">The following table summarizes the configuration using three voice routes.</span></span> <span data-ttu-id="8086d-318">En este ejemplo, las tres rutas forman parte del mismo uso de la RTC "Estados Unidos y Canadá".</span><span class="sxs-lookup"><span data-stu-id="8086d-318">In this example, all three routes are part of the same PSTN Usage "US and Canada".</span></span>

|<span data-ttu-id="8086d-319">**Uso de RTC**</span><span class="sxs-lookup"><span data-stu-id="8086d-319">**PSTN usage**</span></span>|<span data-ttu-id="8086d-320">**Ruta de voz**</span><span class="sxs-lookup"><span data-stu-id="8086d-320">**Voice route**</span></span>|<span data-ttu-id="8086d-321">**Patrón de números**</span><span class="sxs-lookup"><span data-stu-id="8086d-321">**Number pattern**</span></span>|<span data-ttu-id="8086d-322">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="8086d-322">**Priority**</span></span>|<span data-ttu-id="8086d-323">**SBC**</span><span class="sxs-lookup"><span data-stu-id="8086d-323">**SBC**</span></span>|<span data-ttu-id="8086d-324">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="8086d-324">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8086d-325">Solo para Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="8086d-325">US only</span></span>|<span data-ttu-id="8086d-326">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="8086d-326">"Redmond 1"</span></span>|<span data-ttu-id="8086d-327">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="8086d-327">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="8086d-328">1</span><span class="sxs-lookup"><span data-stu-id="8086d-328">1</span></span>|<span data-ttu-id="8086d-329">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="8086d-329">sbc1.contoso.biz</span></span><br/><span data-ttu-id="8086d-330">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="8086d-330">sbc2.contoso.biz</span></span>|<span data-ttu-id="8086d-331">Ruta activa para números llamados + 1 425 XXX XX XX o + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="8086d-331">Active route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="8086d-332">Solo para Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="8086d-332">US only</span></span>|<span data-ttu-id="8086d-333">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="8086d-333">"Redmond 2"</span></span>|<span data-ttu-id="8086d-334">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="8086d-334">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="8086d-335">1</span><span class="sxs-lookup"><span data-stu-id="8086d-335">2</span></span>|<span data-ttu-id="8086d-336">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="8086d-336">sbc3.contoso.biz</span></span><br/><span data-ttu-id="8086d-337">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="8086d-337">sbc4.contoso.biz</span></span>|<span data-ttu-id="8086d-338">Ruta de copia de seguridad para los números + 1 425 XXX XX XX ó + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="8086d-338">Backup route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="8086d-339">Solo para Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="8086d-339">US only</span></span>|<span data-ttu-id="8086d-340">"Otros + 1"</span><span class="sxs-lookup"><span data-stu-id="8086d-340">"Other +1"</span></span>|<span data-ttu-id="8086d-341">^\\+ 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="8086d-341">^\\+1(\d{10})$</span></span>|<span data-ttu-id="8086d-342">3</span><span class="sxs-lookup"><span data-stu-id="8086d-342">3</span></span>|<span data-ttu-id="8086d-343">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="8086d-343">sbc5.contoso.biz</span></span><br/><span data-ttu-id="8086d-344">sbc6.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="8086d-344">sbc6.contoso.biz</span></span>|<span data-ttu-id="8086d-345">Ruta de números llamados + 1 XXX XXX XX XX (excepto + 1 425 XXX XX XX o + 1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="8086d-345">Route for called numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|||||||

<span data-ttu-id="8086d-346">Todas las rutas se asocian con el uso de la RTC "Estados Unidos y Canadá" y el uso de RTC está asociado a la Directiva de enrutamiento de voz "solo para EE. UU.".</span><span class="sxs-lookup"><span data-stu-id="8086d-346">All routes are associated with the PSTN Usage "US and Canada" and the PSTN Usage is associated with the Voice Routing Policy "US Only."</span></span> <span data-ttu-id="8086d-347">En este ejemplo, la Directiva de enrutamiento de voz se asigna a User Spencer Low.</span><span class="sxs-lookup"><span data-stu-id="8086d-347">In this example, the voice routing policy is assigned to user Spencer Low.</span></span>

#### <a name="examples-of-call-routes"></a><span data-ttu-id="8086d-348">Ejemplos de rutas de llamadas</span><span class="sxs-lookup"><span data-stu-id="8086d-348">Examples of call routes</span></span>

<span data-ttu-id="8086d-349">En el siguiente ejemplo, se muestra cómo configurar rutas, usos de RTC y directivas de enrutamiento, y asignamos la Directiva al usuario.</span><span class="sxs-lookup"><span data-stu-id="8086d-349">In the following example, we demonstrate how to configure Routes, PSTN Usages, and Routing policies, and we assign the policy to the user.</span></span>

<span data-ttu-id="8086d-350">**Paso 1:** Crear el uso de RTC "Estados Unidos y Canadá".</span><span class="sxs-lookup"><span data-stu-id="8086d-350">**Step 1:** Create the PSTN Usage "US and Canada".</span></span>

<span data-ttu-id="8086d-351">En una sesión de PowerShell remoto de Skype empresarial, escriba:</span><span class="sxs-lookup"><span data-stu-id="8086d-351">In a Skype for Business Remote PowerShell session, type:</span></span>

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

<span data-ttu-id="8086d-352">Valide que el uso se haya creado especificando:</span><span class="sxs-lookup"><span data-stu-id="8086d-352">Validate that the usage was created by entering:</span></span> 
```PowerShell
Get-CSOnlinePSTNUsage
``` 
<span data-ttu-id="8086d-353">Que devuelve una lista de los nombres que se pueden truncar:</span><span class="sxs-lookup"><span data-stu-id="8086d-353">Which returns a list of names that may be truncated:</span></span>
```output
Identity    : Global
Usage       : {testusage, US and Canada, International, karlUsage. . .}
```
<span data-ttu-id="8086d-354">En el ejemplo siguiente, puede ver el resultado de ejecutar el comando `(Get-CSOnlinePSTNUsage).usage` de PowerShell para mostrar nombres completos (no truncados).</span><span class="sxs-lookup"><span data-stu-id="8086d-354">In the example below, you can see the result of the running the PowerShell command `(Get-CSOnlinePSTNUsage).usage` to display full names (not truncated).</span></span>

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

<span data-ttu-id="8086d-355">**Paso 2:** En una sesión de PowerShell de Skype empresarial online, cree tres rutas: Redmond 1, Redmond 2 y otros + 1, tal y como se detalla en la tabla anterior.</span><span class="sxs-lookup"><span data-stu-id="8086d-355">**Step 2:** In a PowerShell session in Skype for Business Online, create three routes: Redmond 1, Redmond 2, and Other +1, as detailed in the previous table.</span></span> 

<span data-ttu-id="8086d-356">Para crear la ruta de "Redmond 1", escriba:</span><span class="sxs-lookup"><span data-stu-id="8086d-356">To create the "Redmond 1" route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="8086d-357">Que devuelve:</span><span class="sxs-lookup"><span data-stu-id="8086d-357">Which returns:</span></span>
<pre>
Identity                : Redmond 1
Priority                : 1
Description             :
NumberPattern           : ^\+1(425|206) (\d{7})$
OnlinePstnUsages        : {US and Canada}
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name                    : Redmond 1
</pre>
<span data-ttu-id="8086d-358">Para crear la ruta de Redmond 2, escriba:</span><span class="sxs-lookup"><span data-stu-id="8086d-358">To create the Redmond 2 route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="8086d-359">Para crear la ruta otra + 1, escriba:</span><span class="sxs-lookup"><span data-stu-id="8086d-359">To create the Other +1 route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > <span data-ttu-id="8086d-360">Asegúrese de que la expresión regular en el atributo NumberPattern es una expresión válida.</span><span class="sxs-lookup"><span data-stu-id="8086d-360">Make sure that your regular expression in the NumberPattern attribute is a valid expression.</span></span> <span data-ttu-id="8086d-361">Puede probarla con este sitio web:[https://www.regexpal.com](https://www.regexpal.com)</span><span class="sxs-lookup"><span data-stu-id="8086d-361">You can test it using this website: [https://www.regexpal.com](https://www.regexpal.com)</span></span>

<span data-ttu-id="8086d-362">En algunos casos, es necesario enrutar todas las llamadas a la misma SBC; Use-NumberPattern ". \*"</span><span class="sxs-lookup"><span data-stu-id="8086d-362">In some cases there is a need to route all calls to the same SBC; please use -NumberPattern ".\*"</span></span>

<span data-ttu-id="8086d-363">Enrutar todas las llamadas al mismo SBC.</span><span class="sxs-lookup"><span data-stu-id="8086d-363">Route all calls to same SBC.</span></span>

```PowerShell
Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz
```

<span data-ttu-id="8086d-364">Confirme que ha configurado correctamente la ruta ejecutando el `Get-CSOnlineVoiceRoute` comando PowerShell con las opciones que se muestran:</span><span class="sxs-lookup"><span data-stu-id="8086d-364">Validate that you’ve correctly configured the route by running the `Get-CSOnlineVoiceRoute` PowerShell command using options as shown:</span></span>

```PowerShell
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
<span data-ttu-id="8086d-365">Que debería devolver:</span><span class="sxs-lookup"><span data-stu-id="8086d-365">Which should return:</span></span>
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

<span data-ttu-id="8086d-366">En el ejemplo, se asignó automáticamente la prioridad 4 a la ruta "otros + 1".</span><span class="sxs-lookup"><span data-stu-id="8086d-366">In the example, the route "Other +1" was automatically assigned priority 4.</span></span> 

<span data-ttu-id="8086d-367">**Paso 3:** Crear una directiva de enrutamiento de voz "solo para EE. UU." y agregar a la directiva el uso de la RTC "Estados Unidos y Canadá".</span><span class="sxs-lookup"><span data-stu-id="8086d-367">**Step 3:** Create a Voice Routing Policy "US Only" and add to the policy the PSTN Usage "US and Canada."</span></span>

<span data-ttu-id="8086d-368">En una sesión de PowerShell en Skype empresarial online, escriba:</span><span class="sxs-lookup"><span data-stu-id="8086d-368">In a PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="8086d-369">El resultado se muestra en este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8086d-369">The result is shown in this example:</span></span>

<pre>
Identity            : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
</pre>

<span data-ttu-id="8086d-370">**Paso 4:** Conceder al usuario Spencer bajo una directiva de enrutamiento de voz con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8086d-370">**Step 4:** Grant to user Spencer Low a voice routing policy by using PowerShell.</span></span>

<span data-ttu-id="8086d-371">En una sesión de PowerShell en Skype empresarial online, escriba:</span><span class="sxs-lookup"><span data-stu-id="8086d-371">In a PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"
```

<span data-ttu-id="8086d-372">Valide la asignación de directiva escribiendo este comando:</span><span class="sxs-lookup"><span data-stu-id="8086d-372">Validate the policy assignment by entering this command:</span></span>

```PowerShell
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```

<span data-ttu-id="8086d-373">Que devuelve:</span><span class="sxs-lookup"><span data-stu-id="8086d-373">Which returns:</span></span>
<pre>
OnlineVoiceRoutingPolicy
---------------------
US Only
</pre>

#### <a name="creating-a-voice-routing-policy-with-several-pstn-usages"></a><span data-ttu-id="8086d-374">Crear una directiva de enrutamiento de voz con varios usos de RTC</span><span class="sxs-lookup"><span data-stu-id="8086d-374">Creating a Voice Routing Policy with several PSTN Usages</span></span>

<span data-ttu-id="8086d-375">La Directiva de enrutamiento de voz creada anteriormente solo permite llamadas a números de teléfono en Estados Unidos y Canadá, a menos que la licencia del plan de llamadas de Microsoft también esté asignada al usuario.</span><span class="sxs-lookup"><span data-stu-id="8086d-375">The Voice Routing Policy created previously only allows calls to phone numbers in the US and Canada--unless the Microsoft Calling Plan license is also assigned to the user.</span></span>

<span data-ttu-id="8086d-376">En el ejemplo siguiente, puede crear la Directiva de enrutamiento de voz "sin restricciones".</span><span class="sxs-lookup"><span data-stu-id="8086d-376">In the example that follows, you can create the Voice Routing Policy "No Restrictions."</span></span> <span data-ttu-id="8086d-377">La Directiva reutiliza el uso de la RTC "Estados Unidos y Canadá" creado en el ejemplo anterior, así como el nuevo uso de RTC "internacional".</span><span class="sxs-lookup"><span data-stu-id="8086d-377">The policy reuses the PSTN Usage "US and Canada" created in the previous example, as well as the new PSTN Usage "International."</span></span> 

<span data-ttu-id="8086d-378">Esto enruta todas las demás llamadas a los sbc2.contoso.biz y sbc5.contoso.biz de SBCs.</span><span class="sxs-lookup"><span data-stu-id="8086d-378">This routes all other calls to the SBCs sbc2.contoso.biz and sbc5.contoso.biz.</span></span> <span data-ttu-id="8086d-379">Los ejemplos que se muestran asignan la Directiva solo para usuarios de "Spencer Low", sin restricciones para el usuario "John Woods".</span><span class="sxs-lookup"><span data-stu-id="8086d-379">The examples that are shown assign the US Only policy to user "Spencer Low," and No Restrictions to the user "John Woods."</span></span>

<span data-ttu-id="8086d-380">Spencer Low: las llamadas se permiten solo a números de Estados Unidos y Canadá.</span><span class="sxs-lookup"><span data-stu-id="8086d-380">Spencer Low – Calls allowed only to US and Canadian numbers.</span></span> <span data-ttu-id="8086d-381">Al llamar al intervalo de números de Redmond, debe usarse el conjunto específico de SBC.</span><span class="sxs-lookup"><span data-stu-id="8086d-381">When calling to the Redmond number range, the specific set of SBC must be used.</span></span> <span data-ttu-id="8086d-382">Los números que no son de Estados Unidos no se enrutan a menos que la licencia del plan de llamadas se asigne al usuario.</span><span class="sxs-lookup"><span data-stu-id="8086d-382">Non-US numbers will not be routed unless the Calling Plan license is assigned to the user.</span></span>

<span data-ttu-id="8086d-383">John Woods: permite realizar llamadas a cualquier número.</span><span class="sxs-lookup"><span data-stu-id="8086d-383">John Woods – Calls allowed to any number.</span></span> <span data-ttu-id="8086d-384">Al llamar al intervalo de números de Redmond, debe usarse el conjunto específico de SBC.</span><span class="sxs-lookup"><span data-stu-id="8086d-384">When calling to the Redmond number range, the specific set of SBC must be used.</span></span> <span data-ttu-id="8086d-385">Los números que no sean de Estados Unidos se enrutarán a través de sbc2.contoso.biz y sbc5.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="8086d-385">Non-US numbers will be routed via sbc2.contoso.biz and sbc5.contoso.biz.</span></span>

![Muestra la Directiva de enrutamiento de voz asignada al usuario Spencer Low](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

<span data-ttu-id="8086d-387">Para todas las demás llamadas, si un usuario tiene ambas licencias (Microsoft Phone System y Microsoft Call plan), se usa la ruta automática.</span><span class="sxs-lookup"><span data-stu-id="8086d-387">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), Automatic Route is used.</span></span> <span data-ttu-id="8086d-388">Si nada coincide con los patrones de número de las rutas de voz en línea creadas por el administrador, enrutar a través del plan de llamadas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8086d-388">If nothing matches the number patterns in the administrator-created online voice routes, route via Microsoft Calling Plan.</span></span>

<span data-ttu-id="8086d-389">Si el usuario solo tiene Microsoft Phone System, la llamada se elimina porque no hay disponibles reglas coincidentes.</span><span class="sxs-lookup"><span data-stu-id="8086d-389">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

![Muestra la Directiva de enrutamiento de voz asignada al usuario John Woods](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

<span data-ttu-id="8086d-391">En la siguiente tabla se resumen las denominaciones de uso y las rutas de voz de directivas de enrutamiento "sin restricciones".</span><span class="sxs-lookup"><span data-stu-id="8086d-391">The following table summarizes routing policy "No Restrictions" usage designations and voice routes.</span></span> 

|<span data-ttu-id="8086d-392">**Uso de RTC**</span><span class="sxs-lookup"><span data-stu-id="8086d-392">**PSTN usage**</span></span>|<span data-ttu-id="8086d-393">**Ruta de voz**</span><span class="sxs-lookup"><span data-stu-id="8086d-393">**Voice route**</span></span>|<span data-ttu-id="8086d-394">**Patrón de números**</span><span class="sxs-lookup"><span data-stu-id="8086d-394">**Number pattern**</span></span>|<span data-ttu-id="8086d-395">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="8086d-395">**Priority**</span></span>|<span data-ttu-id="8086d-396">**SBC**</span><span class="sxs-lookup"><span data-stu-id="8086d-396">**SBC**</span></span>|<span data-ttu-id="8086d-397">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="8086d-397">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8086d-398">Solo para Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="8086d-398">US Only</span></span>|<span data-ttu-id="8086d-399">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="8086d-399">"Redmond 1"</span></span>|<span data-ttu-id="8086d-400">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="8086d-400">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="8086d-401">1</span><span class="sxs-lookup"><span data-stu-id="8086d-401">1</span></span>|<span data-ttu-id="8086d-402">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="8086d-402">sbc1.contoso.biz</span></span><br/><span data-ttu-id="8086d-403">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="8086d-403">sbc2.contoso.biz</span></span>|<span data-ttu-id="8086d-404">Ruta activa para números de destinatarios + 1 425 XXX XX XX o + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="8086d-404">Active route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="8086d-405">Solo para Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="8086d-405">US Only</span></span>|<span data-ttu-id="8086d-406">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="8086d-406">"Redmond 2"</span></span>|<span data-ttu-id="8086d-407">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="8086d-407">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="8086d-408">1</span><span class="sxs-lookup"><span data-stu-id="8086d-408">2</span></span>|<span data-ttu-id="8086d-409">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="8086d-409">sbc3.contoso.biz</span></span><br/><span data-ttu-id="8086d-410">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="8086d-410">sbc4.contoso.biz</span></span>|<span data-ttu-id="8086d-411">Ruta de reserva para números de destinatarios + 1 425 XXX XX XX o + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="8086d-411">Backup route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="8086d-412">Solo para Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="8086d-412">US Only</span></span>|<span data-ttu-id="8086d-413">"Otros + 1"</span><span class="sxs-lookup"><span data-stu-id="8086d-413">"Other +1"</span></span>|<span data-ttu-id="8086d-414">^\\+ 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="8086d-414">^\\+1(\d{10})$</span></span>|<span data-ttu-id="8086d-415">3</span><span class="sxs-lookup"><span data-stu-id="8086d-415">3</span></span>|<span data-ttu-id="8086d-416">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="8086d-416">sbc5.contoso.biz</span></span><br/><span data-ttu-id="8086d-417">sbc6>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="8086d-417">sbc6>.contoso.biz</span></span>|<span data-ttu-id="8086d-418">Ruta para números de la llamada + 1 XXX XXX XX XX (excepto + 1 425 XXX XX XX o + 1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="8086d-418">Route for callee numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|<span data-ttu-id="8086d-419">International</span><span class="sxs-lookup"><span data-stu-id="8086d-419">International</span></span>|<span data-ttu-id="8086d-420">International</span><span class="sxs-lookup"><span data-stu-id="8086d-420">International</span></span>|<span data-ttu-id="8086d-421">\d +</span><span class="sxs-lookup"><span data-stu-id="8086d-421">\d+</span></span>|<span data-ttu-id="8086d-422">4</span><span class="sxs-lookup"><span data-stu-id="8086d-422">4</span></span>|<span data-ttu-id="8086d-423">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="8086d-423">sbc2.contoso.biz</span></span><br/><span data-ttu-id="8086d-424">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="8086d-424">sbc5.contoso.biz</span></span>|<span data-ttu-id="8086d-425">Ruta para cualquier patrón de números</span><span class="sxs-lookup"><span data-stu-id="8086d-425">Route for any number pattern</span></span> |


  > [!NOTE]
  > - <span data-ttu-id="8086d-426">El orden de los usos de RTC en las directivas de enrutamiento de voz es fundamental.</span><span class="sxs-lookup"><span data-stu-id="8086d-426">The order of PSTN Usages in Voice Routing Policies is critical.</span></span> <span data-ttu-id="8086d-427">Los usos se aplican en orden y, si se encuentra una coincidencia en el primer uso, no se evalúan otros usos.</span><span class="sxs-lookup"><span data-stu-id="8086d-427">The usages are applied in order, and if a match is found in the first usage, then other usages are never evaluated.</span></span> <span data-ttu-id="8086d-428">El uso de RTC "internacional" debe situarse después del uso de RTC "solo para EE. UU.".</span><span class="sxs-lookup"><span data-stu-id="8086d-428">The PSTN Usage "International" must be placed after the PSTN Usage "US Only."</span></span> <span data-ttu-id="8086d-429">Para cambiar el orden de los usos de RTC, ejecute el `Set-CSOnlineVoiceRoutingPolicy` comando.</span><span class="sxs-lookup"><span data-stu-id="8086d-429">To change the order of the PSTN Usages, run the `Set-CSOnlineVoiceRoutingPolicy` command.</span></span> <br/><span data-ttu-id="8086d-430">Por ejemplo, para cambiar el orden de "Estados Unidos y Canadá" primero por "internacional" y el segundo al orden invertido:</span><span class="sxs-lookup"><span data-stu-id="8086d-430">For example, to change the order from "US and Canada" first and "International" second to the reverse order run:</span></span><br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - <span data-ttu-id="8086d-431">La prioridad de las rutas de voz "otras + 1" y "internacionales" se asigna automáticamente.</span><span class="sxs-lookup"><span data-stu-id="8086d-431">The priority for "Other +1" and "International" Voice routes are assigned automatically.</span></span> <span data-ttu-id="8086d-432">No importa siempre que tengan prioridades más bajas que "Redmond 1" y "Redmond 2".</span><span class="sxs-lookup"><span data-stu-id="8086d-432">They don’t matter as long as they have lower priorities than "Redmond 1" and "Redmond 2."</span></span>

#### <a name="example-of-voice-routing-policy-for-user-john-woods"></a><span data-ttu-id="8086d-433">Ejemplo de directiva de enrutamiento de voz para el usuario John Woods</span><span class="sxs-lookup"><span data-stu-id="8086d-433">Example of Voice Routing Policy for user John Woods</span></span>

<span data-ttu-id="8086d-434">A continuación, se indican los pasos para crear el uso de RTC "internacional", la ruta de voz "internacional", la Directiva de enrutamiento de voz "sin restricciones" y, a continuación, asignarlo al usuario "John Woods".</span><span class="sxs-lookup"><span data-stu-id="8086d-434">The steps to create PSTN Usage "International", voice route "International," Voice Routing Policy "No Restrictions," and then assigning it to the user "John Woods" are as follows.</span></span>


<span data-ttu-id="8086d-435">**Paso 1**: crear el uso de RTC "internacional".</span><span class="sxs-lookup"><span data-stu-id="8086d-435">**Step 1**: Create the PSTN Usage "International."</span></span> 

<span data-ttu-id="8086d-436">En una sesión de PowerShell remoto en Skype empresarial online, escriba:</span><span class="sxs-lookup"><span data-stu-id="8086d-436">In a remote PowerShell session in Skype for Business Online, enter:</span></span>

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

<span data-ttu-id="8086d-437">**Paso 2**: crear la nueva ruta de voz "internacional".</span><span class="sxs-lookup"><span data-stu-id="8086d-437">**Step 2**:  Create the new voice route "International."</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
```
<span data-ttu-id="8086d-438">Que devuelve:</span><span class="sxs-lookup"><span data-stu-id="8086d-438">Which returns:</span></span>

<pre>
Identity                  : International
Priority                  : 5
Description               :
NumberPattern             : .*
OnlinePstnUsages          : {International}
OnlinePstnGatewayList     : {sbc2.contoso.biz, sbc5.contoso.biz}
Name                      : International
</pre>

<span data-ttu-id="8086d-439">**Paso 3**: crear una directiva de enrutamiento de voz "sin restricciones".</span><span class="sxs-lookup"><span data-stu-id="8086d-439">**Step 3**: Create a Voice Routing Policy "No Restrictions".</span></span> 

<span data-ttu-id="8086d-440">El uso de RTC "Redmond 1" y "Redmond" se reutiliza en esta directiva de enrutamiento de voz para mantener un control especial de las llamadas al número "+ 1 425 XXX XX XX" y "+ 1 206 XXX XX XX" como llamadas locales o locales.</span><span class="sxs-lookup"><span data-stu-id="8086d-440">The PSTN Usage "Redmond 1" and "Redmond" are reused in this voice routing policy to preserve special handling for calls to number "+1 425 XXX XX XX" and "+1 206 XXX XX XX" as local or on-premises calls.</span></span>

   ```PowerShell
   New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
   ```

<span data-ttu-id="8086d-441">Tome nota del orden de uso de RTC:</span><span class="sxs-lookup"><span data-stu-id="8086d-441">Take note of the order of PSTN Usages:</span></span>

<span data-ttu-id="8086d-442">a.</span><span class="sxs-lookup"><span data-stu-id="8086d-442">a.</span></span> <span data-ttu-id="8086d-443">Si una llamada se realiza en el número "+ 1 425 XXX XX XX" con los usos configurados como en el ejemplo siguiente, la llamada sigue el conjunto de rutas en "Estados Unidos y Canadá" y se aplica la lógica de enrutamiento especial.</span><span class="sxs-lookup"><span data-stu-id="8086d-443">If a call made to number "+1 425 XXX XX XX" with the usages configured as in the following example, the call follows the route set in "US and Canada" usage and the special routing logic is applied.</span></span> <span data-ttu-id="8086d-444">Es decir, la llamada se enruta usando sbc1.contoso.biz y sbc2.contoso.biz en primer lugar y, a continuación, sbc3.contoso.biz y sbc4.contoso.biz como rutas de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="8086d-444">That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes.</span></span>

<span data-ttu-id="8086d-445">b.</span><span class="sxs-lookup"><span data-stu-id="8086d-445">b.</span></span> <span data-ttu-id="8086d-446">Si el uso de RTC "internacional" es anterior a "Estados Unidos y Canadá", las llamadas a + 1 425 XXX XX XX se enrutan a sbc2.contoso.biz y sbc5.contoso.biz como parte de la lógica de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="8086d-446">If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic.</span></span> <span data-ttu-id="8086d-447">Escribe el comando:</span><span class="sxs-lookup"><span data-stu-id="8086d-447">Enter the command:</span></span>

```PowerShell
New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
```

<span data-ttu-id="8086d-448">Que devuelve</span><span class="sxs-lookup"><span data-stu-id="8086d-448">Which returns</span></span>

<pre>
Identity              : International 
OnlinePstnUsages : {US and Canada, International}    
Description      :  
RouteType             : BYOT
</pre>

<span data-ttu-id="8086d-449">**Paso 4**: asignar la Directiva de enrutamiento de voz al usuario "John Woods" con el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="8086d-449">**Step 4**: Assign the voice routing policy to the user "John Woods" using the following command.</span></span>

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions”
```

<span data-ttu-id="8086d-450">A continuación, verifique la asignación con el comando:</span><span class="sxs-lookup"><span data-stu-id="8086d-450">Then verify the assignment using the command:</span></span> 

```PowerShell
Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
```

<span data-ttu-id="8086d-451">Que devuelve:</span><span class="sxs-lookup"><span data-stu-id="8086d-451">Which returns:</span></span>

<pre>
OnlineVoiceRoutingPolicy
------------------------
No Restrictions
</pre>

<span data-ttu-id="8086d-452">El resultado es que la política de voz aplicada a las llamadas de John Woods no tiene restricciones, y seguirá la lógica de enrutamiento de llamadas disponible para las llamadas de Estados Unidos, Canadá e internacionales.</span><span class="sxs-lookup"><span data-stu-id="8086d-452">The result is that the voice policy applied to John Woods’ calls is unrestricted, and will follow the logic of call routing available for US, Canada, and International calling.</span></span>

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a><span data-ttu-id="8086d-453">Asignar el modo solo de Teams a los usuarios para garantizar la superficie de llamadas en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8086d-453">Assign Teams Only mode to users to ensure calls land in Microsoft Teams</span></span>

<span data-ttu-id="8086d-454">El enrutamiento directo requiere que los usuarios estén en el modo solo de equipos para garantizar las llamadas entrantes en el cliente de Teams.</span><span class="sxs-lookup"><span data-stu-id="8086d-454">Direct Routing requires that users be in Teams Only mode to ensure incoming calls land in the Teams client.</span></span> <span data-ttu-id="8086d-455">Para poner los usuarios en modo de solo equipos, asígnelos a la instancia "UpgradeToTeams" de TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="8086d-455">To put users in Teams Only mode, assign them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span> <span data-ttu-id="8086d-456">Si su organización usa Skype empresarial Server o Skype empresarial online, consulte el artículo siguiente para la interoperabilidad de información entre Skype y Teams: [Guía de migración e interoperabilidad para las organizaciones que usan Teams conjuntamente con Skype empresarial](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span><span class="sxs-lookup"><span data-stu-id="8086d-456">If your organization uses Skype for Business Server or Skype for Business Online, see the following article for information interoperability between Skype and Teams: [Migration and interoperability guidance for organizations using Teams together with Skype for Business](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span></span> 

## <a name="configuring-sending-calls-directly-to-voicemail"></a><span data-ttu-id="8086d-457">Configurar el envío de llamadas directamente al buzón de voz</span><span class="sxs-lookup"><span data-stu-id="8086d-457">Configuring sending calls directly to voicemail</span></span>

<span data-ttu-id="8086d-458">El enrutamiento directo le permite finalizar la llamada a un usuario y enviarlo directamente al buzón de voz de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="8086d-458">Direct Routing allows you to end the call to a user and send it directly to the users' voicemail.</span></span> <span data-ttu-id="8086d-459">Si deseas enviar la llamada directamente al buzón de voz, adjunta Opaque = App: el buzón de voz al encabezado URI de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="8086d-459">If you want to send the call directly to voicemail, please attach opaque=app:voicemail to the Request URI header.</span></span> <span data-ttu-id="8086d-460">Por ejemplo, "SIP: user@yourdomain. com; Opaque = App: buzón de voz".</span><span class="sxs-lookup"><span data-stu-id="8086d-460">For example, "sip:user@yourdomain.com;opaque=app:voicemail".</span></span>
<span data-ttu-id="8086d-461">En este caso, el usuario de Teams no recibirá la notificación de llamada, la llamada se conectará al buzón de voz del usuario directamente.</span><span class="sxs-lookup"><span data-stu-id="8086d-461">In this case the Teams user will not receive the calling notification, the call will be connected to the voicemail of the user directly.</span></span>

## <a name="translate-caller-and-callee-numbers-for-outbound-and-inbound-calls-to-an-alternate-format"></a><span data-ttu-id="8086d-462">Traducir números de llamador y destinatario para llamadas salientes y entrantes a un formato alternativo</span><span class="sxs-lookup"><span data-stu-id="8086d-462">Translate caller and callee numbers for outbound and inbound calls to an alternate format</span></span>

<span data-ttu-id="8086d-463">En ocasiones, es posible que los administradores de inquilinos deseen cambiar el número de la persona que llama o la persona que llama para las llamadas entrantes o salientes en función de los patrones creados para garantizar la interoperabilidad con SBCs.</span><span class="sxs-lookup"><span data-stu-id="8086d-463">Sometimes tenant administrators may want to change the callee or caller number for outbound and/or inbound calls based on the patterns they created to ensure interoperability with SBCs.</span></span> <span data-ttu-id="8086d-464">Puede configurar una directiva de reglas de traducción de números para traducir los números de llamadas o llamadas a un formato alternativo.</span><span class="sxs-lookup"><span data-stu-id="8086d-464">You can set a Number Translation Rules policy to translate callee or caller numbers to an alternate format.</span></span> <span data-ttu-id="8086d-465">Puede usar la Directiva para traducir números para lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8086d-465">You can use the policy to translate numbers for the following:</span></span>

- <span data-ttu-id="8086d-466">Llamadas entrantes: llamadas de un punto final de la RTC (llamador) a un cliente de Teams (destinatario).</span><span class="sxs-lookup"><span data-stu-id="8086d-466">Inbound calls: Calls from a PSTN endpoint (caller) to a Teams client (callee).</span></span>
- <span data-ttu-id="8086d-467">Llamadas salientes: llamadas de un cliente de Teams (llamador) a un punto final de RTC (destinatario).</span><span class="sxs-lookup"><span data-stu-id="8086d-467">Outbound calls: Calls from a Teams client (caller) to a PSTN endpoint (callee).</span></span>

<span data-ttu-id="8086d-468">La Directiva se aplica en el nivel de SBC.</span><span class="sxs-lookup"><span data-stu-id="8086d-468">The policy is applied at the SBC level.</span></span> <span data-ttu-id="8086d-469">Puede asignar varias reglas de traducción a un SBC, que se aplican en el orden en que aparecen cuando las lista en PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8086d-469">You can assign multiple translation rules to a SBC, which are applied in the order that they appear when you list them in PowerShell.</span></span> <span data-ttu-id="8086d-470">También puede cambiar el orden de las reglas en la Directiva.</span><span class="sxs-lookup"><span data-stu-id="8086d-470">You can also change the order of the rules in the policy.</span></span>

<span data-ttu-id="8086d-471">Para crear, modificar, ver y eliminar reglas de manipulación de números, use los cmdlets New-CsTeamsTranslationRule, Set-CsTeamsTranslationRule, Get-CsTeamsTranslationRule y Remove-CsTeamsTranslationRule.</span><span class="sxs-lookup"><span data-stu-id="8086d-471">To create, modify, view, and delete number manipulation rules, use the New-CsTeamsTranslationRule, Set-CsTeamsTranslationRule, Get-CsTeamsTranslationRule, and Remove-CsTeamsTranslationRule cmdlets.</span></span>

<span data-ttu-id="8086d-472">Para asignar, configurar y enumerar reglas de manipulación de números en SBCS, use los cmdlets [New-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) y [set-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) junto ```InboundTeamsNumberTranslationRules```con ```InboundPSTNNumberTranslationRules```los ```OutboundTeamsNumberTranslationRules```parámetros ```OutboundPSTNNumberTranslationRules```, ```InboundTeamsNumberTranslationRulesList```, ```InboundPSTNNumberTranslationRulesList```, ```OutboundTeamsNumberTranslationRulesList```,, ```OutboundPSTNNumberTranslationRulesList``` , y.</span><span class="sxs-lookup"><span data-stu-id="8086d-472">To assign, configure, and list number manipulation rules on SBCs, use the [New-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) and [Set-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) cmdlets together with the  ```InboundTeamsNumberTranslationRules```, ```InboundPSTNNumberTranslationRules```, ```OutboundTeamsNumberTranslationRules```, ```OutboundPSTNNumberTranslationRules```, ```InboundTeamsNumberTranslationRulesList```, ```InboundPSTNNumberTranslationRulesList```, ```OutboundTeamsNumberTranslationRulesList```, and ```OutboundPSTNNumberTranslationRulesList``` parameters.</span></span>

### <a name="examples"></a><span data-ttu-id="8086d-473">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="8086d-473">Examples</span></span>

#### <a name="example-sbc-configuration"></a><span data-ttu-id="8086d-474">Ejemplo de configuración de SBC</span><span class="sxs-lookup"><span data-stu-id="8086d-474">Example SBC configuration</span></span>

<span data-ttu-id="8086d-475">Para los escenarios de ejemplo, ejecutamos ```New-CsOnlinePSTNGateway``` el cmdlet para crear la siguiente configuración de SBC.</span><span class="sxs-lookup"><span data-stu-id="8086d-475">For the example scenarios, we run the ```New-CsOnlinePSTNGateway``` cmdlet to create the following SBC configuration.</span></span>

```PowerShell
New-CSOnlinePSTNGateway -Identity sbc1.contoso.com -SipSignallingPort 5061 –InboundTeamsNumberTranslationRulesList ‘AddPlus1’, ‘AddE164SeattleAreaCode’ -InboundPSTNNumberTranslationRulesList ‘AddPlus1’ -OnboundPSTNNumberTranslationRulesList ‘AddSeattleAreaCode’,  -OutboundTeamsNumberTranslationRulesList ‘StripPlus1’
```

<span data-ttu-id="8086d-476">Las reglas de traducción asignadas a SBC se resumen en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="8086d-476">The translation rules assigned to the SBC are summarized in the following table.</span></span>

|<span data-ttu-id="8086d-477">Nombre</span><span class="sxs-lookup"><span data-stu-id="8086d-477">Name</span></span>  |<span data-ttu-id="8086d-478">Patrón</span><span class="sxs-lookup"><span data-stu-id="8086d-478">Pattern</span></span> |<span data-ttu-id="8086d-479">Traducción</span><span class="sxs-lookup"><span data-stu-id="8086d-479">Translation</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="8086d-480">AddPlus1</span><span class="sxs-lookup"><span data-stu-id="8086d-480">AddPlus1</span></span>     |<span data-ttu-id="8086d-481">^ (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="8086d-481">^(\d{10})$</span></span>          |<span data-ttu-id="8086d-482">+1$1</span><span class="sxs-lookup"><span data-stu-id="8086d-482">+1$1</span></span>          |
|<span data-ttu-id="8086d-483">AddE164SeattleAreaCode</span><span class="sxs-lookup"><span data-stu-id="8086d-483">AddE164SeattleAreaCode</span></span>      |<span data-ttu-id="8086d-484">^ (\d{4}) $</span><span class="sxs-lookup"><span data-stu-id="8086d-484">^(\d{4})$</span></span>          | <span data-ttu-id="8086d-485">+ 1206555 $1</span><span class="sxs-lookup"><span data-stu-id="8086d-485">+1206555$1</span></span>         |
|<span data-ttu-id="8086d-486">AddSeattleAreaCode</span><span class="sxs-lookup"><span data-stu-id="8086d-486">AddSeattleAreaCode</span></span>    |<span data-ttu-id="8086d-487">^ (\d{4}) $</span><span class="sxs-lookup"><span data-stu-id="8086d-487">^(\d{4})$</span></span>          | <span data-ttu-id="8086d-488">425555 $1</span><span class="sxs-lookup"><span data-stu-id="8086d-488">425555$1</span></span>         |
|<span data-ttu-id="8086d-489">StripPlus1</span><span class="sxs-lookup"><span data-stu-id="8086d-489">StripPlus1</span></span>    |<span data-ttu-id="8086d-490">^ + 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="8086d-490">^+1(\d{10})$</span></span>          | <span data-ttu-id="8086d-491">$1</span><span class="sxs-lookup"><span data-stu-id="8086d-491">$1</span></span>         |

<span data-ttu-id="8086d-492">En estos casos de ejemplo, tenemos dos usuarios, Alice y Bob.</span><span class="sxs-lookup"><span data-stu-id="8086d-492">In these example scenarios, we have two users, Alice and Bob.</span></span> <span data-ttu-id="8086d-493">Alicia es un usuario de Teams y su número es + 1 206 555 0100.</span><span class="sxs-lookup"><span data-stu-id="8086d-493">Alice is a Teams user and her number is +1 206 555 0100.</span></span> <span data-ttu-id="8086d-494">Bob es un usuario de la RTC y su número es de + 1 425 555 0100.</span><span class="sxs-lookup"><span data-stu-id="8086d-494">Bob is a PSTN user and his number is +1 425 555 0100.</span></span>

#### <a name="example-1-inbound-call-to-a-ten-digit-number"></a><span data-ttu-id="8086d-495">Ejemplo 1: llamada entrante a un número de diez dígitos</span><span class="sxs-lookup"><span data-stu-id="8086d-495">Example 1: Inbound call to a ten-digit number</span></span>

<span data-ttu-id="8086d-496">Bob llama a Alice a través de un número de diez dígitos que no sea el E. 164.</span><span class="sxs-lookup"><span data-stu-id="8086d-496">Bob calls Alice using a non-E.164 ten-digit number.</span></span> <span data-ttu-id="8086d-497">Bob marca 2065550100 para comunicarse con Alice.</span><span class="sxs-lookup"><span data-stu-id="8086d-497">Bob dials 2065550100 to reach Alice.</span></span>
<span data-ttu-id="8086d-498">SBC usa 2065550100 en el RequestURI y en los encabezados y 4255550100 en el encabezado de.</span><span class="sxs-lookup"><span data-stu-id="8086d-498">SBC uses 2065550100 in the RequestURI and To headers and 4255550100 in the From header.</span></span>

|<span data-ttu-id="8086d-499">Encabezado</span><span class="sxs-lookup"><span data-stu-id="8086d-499">Header</span></span>  |<span data-ttu-id="8086d-500">Texto original en</span><span class="sxs-lookup"><span data-stu-id="8086d-500">Original</span></span> |<span data-ttu-id="8086d-501">Encabezado traducido</span><span class="sxs-lookup"><span data-stu-id="8086d-501">Translated header</span></span> |<span data-ttu-id="8086d-502">Parámetro y regla aplicados</span><span class="sxs-lookup"><span data-stu-id="8086d-502">Parameter and rule applied</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="8086d-503">RequestURI</span><span class="sxs-lookup"><span data-stu-id="8086d-503">RequestURI</span></span>  |<span data-ttu-id="8086d-504">INVITAr sip:2065550100@sbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8086d-504">INVITE sip:2065550100@sbc.contoso.com</span></span>|<span data-ttu-id="8086d-505">INVITAr sip:+12065550100@sbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8086d-505">INVITE sip:+12065550100@sbc.contoso.com</span></span>|<span data-ttu-id="8086d-506">InboundTeamsNumberTranslationRulesList 'AddPlus1'</span><span class="sxs-lookup"><span data-stu-id="8086d-506">InboundTeamsNumberTranslationRulesList ‘AddPlus1’</span></span>|
|<span data-ttu-id="8086d-507">Para</span><span class="sxs-lookup"><span data-stu-id="8086d-507">TO</span></span>    |<span data-ttu-id="8086d-508">PARA: \<SIP:2065550100@sbc.contoso.com></span><span class="sxs-lookup"><span data-stu-id="8086d-508">TO: \<sip:2065550100@sbc.contoso.com></span></span>|<span data-ttu-id="8086d-509">PARA: \<SIP:+12065550100@sbc.contoso.com></span><span class="sxs-lookup"><span data-stu-id="8086d-509">TO: \<sip:+12065550100@sbc.contoso.com></span></span>|<span data-ttu-id="8086d-510">InboundTeamsNumberTranlationRulesList 'AddPlus1'</span><span class="sxs-lookup"><span data-stu-id="8086d-510">InboundTeamsNumberTranlationRulesList ‘AddPlus1’</span></span>|
|<span data-ttu-id="8086d-511">De</span><span class="sxs-lookup"><span data-stu-id="8086d-511">FROM</span></span>   |<span data-ttu-id="8086d-512">DE: \<SIP:4255550100@sbc.contoso.com></span><span class="sxs-lookup"><span data-stu-id="8086d-512">FROM: \<sip:4255550100@sbc.contoso.com></span></span>|<span data-ttu-id="8086d-513">DE: \<SIP:+14255550100@sbc.contoso.com></span><span class="sxs-lookup"><span data-stu-id="8086d-513">FROM: \<sip:+14255550100@sbc.contoso.com></span></span>|<span data-ttu-id="8086d-514">InboundPSTNNumberTranslationRulesList 'AddPlus1'</span><span class="sxs-lookup"><span data-stu-id="8086d-514">InboundPSTNNumberTranslationRulesList ‘AddPlus1’</span></span>|

#### <a name="example-2-inbound-call-to-a-four-digit-number"></a><span data-ttu-id="8086d-515">Ejemplo 2: llamada entrante a un número de cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="8086d-515">Example 2: Inbound call to a four-digit number</span></span>

<span data-ttu-id="8086d-516">Bob llama a Alice con un número de cuatro dígitos.</span><span class="sxs-lookup"><span data-stu-id="8086d-516">Bob calls Alice using a four-digit number.</span></span> <span data-ttu-id="8086d-517">Bob marca 0100 para comunicarse con Alice.</span><span class="sxs-lookup"><span data-stu-id="8086d-517">Bob dials 0100 to reach Alice.</span></span>
<span data-ttu-id="8086d-518">SBC usa 0100 en el RequestURI y en los encabezados y 4255550100 en el encabezado de.</span><span class="sxs-lookup"><span data-stu-id="8086d-518">SBC uses 0100 in the RequestURI and To headers and 4255550100 in the From header.</span></span>

|<span data-ttu-id="8086d-519">Encabezado</span><span class="sxs-lookup"><span data-stu-id="8086d-519">Header</span></span>  |<span data-ttu-id="8086d-520">Texto original en</span><span class="sxs-lookup"><span data-stu-id="8086d-520">Original</span></span> |<span data-ttu-id="8086d-521">Encabezado traducido</span><span class="sxs-lookup"><span data-stu-id="8086d-521">Translated header</span></span> |<span data-ttu-id="8086d-522">Parámetro y regla aplicados</span><span class="sxs-lookup"><span data-stu-id="8086d-522">Parameter and rule applied</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="8086d-523">RequestURI</span><span class="sxs-lookup"><span data-stu-id="8086d-523">RequestURI</span></span>  |<span data-ttu-id="8086d-524">INVITAr sip:0100@sbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8086d-524">INVITE sip:0100@sbc.contoso.com</span></span>          |<span data-ttu-id="8086d-525">INVITAr sip:+12065550100@sbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8086d-525">INVITE sip:+12065550100@sbc.contoso.com</span></span>           |<span data-ttu-id="8086d-526">InboundTeamsNumberTranlationRulesList 'AddE164SeattleAreaCode'</span><span class="sxs-lookup"><span data-stu-id="8086d-526">InboundTeamsNumberTranlationRulesList ‘AddE164SeattleAreaCode’</span></span>        |
|<span data-ttu-id="8086d-527">Para</span><span class="sxs-lookup"><span data-stu-id="8086d-527">TO</span></span>    |<span data-ttu-id="8086d-528">PARA: \<SIP:0100@sbc.contoso.com></span><span class="sxs-lookup"><span data-stu-id="8086d-528">TO: \<sip:0100@sbc.contoso.com></span></span>|<span data-ttu-id="8086d-529">PARA: \<SIP:+12065550100@sbc.contoso.com></span><span class="sxs-lookup"><span data-stu-id="8086d-529">TO: \<sip:+12065550100@sbc.contoso.com></span></span>|<span data-ttu-id="8086d-530">InboundTeamsNumberTranlationRulesList 'AddE164SeattleAreaCode'</span><span class="sxs-lookup"><span data-stu-id="8086d-530">InboundTeamsNumberTranlationRulesList ‘AddE164SeattleAreaCode’</span></span>         |
|<span data-ttu-id="8086d-531">De</span><span class="sxs-lookup"><span data-stu-id="8086d-531">FROM</span></span>   |<span data-ttu-id="8086d-532">DE: \<SIP:4255550100@sbc.contoso.com></span><span class="sxs-lookup"><span data-stu-id="8086d-532">FROM: \<sip:4255550100@sbc.contoso.com></span></span>|<span data-ttu-id="8086d-533">DE: \<SIP:+14255550100@sbc.contoso.com></span><span class="sxs-lookup"><span data-stu-id="8086d-533">FROM: \<sip:+14255550100@sbc.contoso.com></span></span>|<span data-ttu-id="8086d-534">InboundPSTNNumberTranlationRulesList 'AddPlus1'</span><span class="sxs-lookup"><span data-stu-id="8086d-534">InboundPSTNNumberTranlationRulesList ‘AddPlus1’</span></span>        |

#### <a name="example-3-outbound-call-using-a-ten-digit-non-e164-number"></a><span data-ttu-id="8086d-535">Ejemplo 3: llamada saliente con un número de diez dígitos que no es E. 164 número</span><span class="sxs-lookup"><span data-stu-id="8086d-535">Example 3: Outbound call using a ten-digit non-E.164 number</span></span>

<span data-ttu-id="8086d-536">Alicia llama a Bob con un número de diez dígitos.</span><span class="sxs-lookup"><span data-stu-id="8086d-536">Alice calls Bob using a ten-digit number.</span></span> <span data-ttu-id="8086d-537">Alice marca 425 555 0100 para comunicarse con Bob.</span><span class="sxs-lookup"><span data-stu-id="8086d-537">Alice dials 425 555 0100 to reach Bob.</span></span>
<span data-ttu-id="8086d-538">SBC está configurado para usar números de diez dígitos no E. 164 para equipos y usuarios de la RTC.</span><span class="sxs-lookup"><span data-stu-id="8086d-538">SBC is configured to use non-E.164 ten-digit numbers for both Teams and PSTN users.</span></span>

<span data-ttu-id="8086d-539">En este escenario, un plan de marcado traduce el número antes de enviarlo a la interfaz de enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="8086d-539">In this scenario, a dial plan translates the number before sending it to the Direct Routing interface.</span></span> <span data-ttu-id="8086d-540">Cuando Alice escribe 425 555 0100 en el cliente de Teams, el número se traduce a + 14255550100 por el plan de marcado de país.</span><span class="sxs-lookup"><span data-stu-id="8086d-540">When Alice enters 425 555 0100 in the Teams client, the number is translated to +14255550100 by the country dial plan.</span></span> <span data-ttu-id="8086d-541">Los números resultantes son una normalización acumulativa de las reglas del plan de marcado y las reglas de traducción de equipos.</span><span class="sxs-lookup"><span data-stu-id="8086d-541">The resulting numbers are a cumulative normalization of the dial plan rules and Teams translation rules.</span></span> <span data-ttu-id="8086d-542">Las reglas de traducción de Teams quitan el "+ 1" que agregó el plan de marcado.</span><span class="sxs-lookup"><span data-stu-id="8086d-542">The Teams translation rules remove the "+1" that was added by the dial plan.</span></span>

|<span data-ttu-id="8086d-543">Encabezado</span><span class="sxs-lookup"><span data-stu-id="8086d-543">Header</span></span>  |<span data-ttu-id="8086d-544">Texto original en</span><span class="sxs-lookup"><span data-stu-id="8086d-544">Original</span></span> |<span data-ttu-id="8086d-545">Encabezado traducido</span><span class="sxs-lookup"><span data-stu-id="8086d-545">Translated header</span></span> |<span data-ttu-id="8086d-546">Parámetro y regla aplicados</span><span class="sxs-lookup"><span data-stu-id="8086d-546">Parameter and rule applied</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="8086d-547">RequestURI</span><span class="sxs-lookup"><span data-stu-id="8086d-547">RequestURI</span></span>  |<span data-ttu-id="8086d-548">INVITAr sip:+14255550100@sbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8086d-548">INVITE sip:+14255550100@sbc.contoso.com</span></span>          |<span data-ttu-id="8086d-549">INVITAr sip:4255550100@sbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8086d-549">INVITE sip:4255550100@sbc.contoso.com</span></span>       |<span data-ttu-id="8086d-550">OutboundPSTNNumberTranlationRulesList 'StripPlus1'</span><span class="sxs-lookup"><span data-stu-id="8086d-550">OutboundPSTNNumberTranlationRulesList ‘StripPlus1’</span></span>         |
|<span data-ttu-id="8086d-551">Para</span><span class="sxs-lookup"><span data-stu-id="8086d-551">TO</span></span>    |<span data-ttu-id="8086d-552">PARA: \<SIP:+14255550100@sbc.contoso.com></span><span class="sxs-lookup"><span data-stu-id="8086d-552">TO: \<sip:+14255550100@sbc.contoso.com></span></span>|<span data-ttu-id="8086d-553">PARA: \<SIP:4255555555@sbc.contoso.com></span><span class="sxs-lookup"><span data-stu-id="8086d-553">TO: \<sip:4255555555@sbc.contoso.com></span></span>|<span data-ttu-id="8086d-554">OutboundPSTNNumberTranlationRulesList 'StripPlus1'</span><span class="sxs-lookup"><span data-stu-id="8086d-554">OutboundPSTNNumberTranlationRulesList ‘StripPlus1’</span></span>       |
|<span data-ttu-id="8086d-555">De</span><span class="sxs-lookup"><span data-stu-id="8086d-555">FROM</span></span>   |<span data-ttu-id="8086d-556">DE: \<SIP:+12065550100@sbc.contoso.com></span><span class="sxs-lookup"><span data-stu-id="8086d-556">FROM: \<sip:+12065550100@sbc.contoso.com></span></span>|<span data-ttu-id="8086d-557">DE: \<SIP:2065550100@sbc.contoso.com></span><span class="sxs-lookup"><span data-stu-id="8086d-557">FROM: \<sip:2065550100@sbc.contoso.com></span></span>|<span data-ttu-id="8086d-558">OutboundTeamsNumberTranlationRulesList 'StripPlus1'</span><span class="sxs-lookup"><span data-stu-id="8086d-558">OutboundTeamsNumberTranlationRulesList ‘StripPlus1’</span></span>         |

#### <a name="example-4-outbound-call-using-a-four-digit-non-e164-number"></a><span data-ttu-id="8086d-559">Ejemplo 4: llamada saliente con un número de cuatro dígitos que no es E. 164 número</span><span class="sxs-lookup"><span data-stu-id="8086d-559">Example 4: Outbound call using a four-digit non-E.164 number</span></span>

<span data-ttu-id="8086d-560">Alicia llama a Bob con un número de cuatro dígitos.</span><span class="sxs-lookup"><span data-stu-id="8086d-560">Alice calls Bob using a four-digit number.</span></span> <span data-ttu-id="8086d-561">Alice usa 0100 para comunicarte con Bob desde llamadas o con un contacto.</span><span class="sxs-lookup"><span data-stu-id="8086d-561">Alice uses 0100 to reach Bob from Calls or by using a contact.</span></span>
<span data-ttu-id="8086d-562">SBC está configurado para usar números de cuatro dígitos que no son E. 164 para los usuarios de Teams y números de 10 dígitos para usuarios de la RTC.</span><span class="sxs-lookup"><span data-stu-id="8086d-562">SBC is configured to use non-E.164 four-digit numbers for Teams users and ten-digit numbers for PSTN users.</span></span> <span data-ttu-id="8086d-563">El plan de marcado no se aplica en este escenario.</span><span class="sxs-lookup"><span data-stu-id="8086d-563">The dial plan isn't applied in this scenario.</span></span>

|<span data-ttu-id="8086d-564">Encabezado</span><span class="sxs-lookup"><span data-stu-id="8086d-564">Header</span></span>  |<span data-ttu-id="8086d-565">Texto original en</span><span class="sxs-lookup"><span data-stu-id="8086d-565">Original</span></span> |<span data-ttu-id="8086d-566">Encabezado traducido</span><span class="sxs-lookup"><span data-stu-id="8086d-566">Translated header</span></span> |<span data-ttu-id="8086d-567">Parámetro y regla aplicados</span><span class="sxs-lookup"><span data-stu-id="8086d-567">Parameter and rule applied</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="8086d-568">RequestURI</span><span class="sxs-lookup"><span data-stu-id="8086d-568">RequestURI</span></span>  |<span data-ttu-id="8086d-569">INVITAr sip:0100@sbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8086d-569">INVITE sip:0100@sbc.contoso.com</span></span>           |<span data-ttu-id="8086d-570">INVITAr sip:4255550100@sbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8086d-570">INVITE sip:4255550100@sbc.contoso.com</span></span>       |<span data-ttu-id="8086d-571">InboundTeamsNumberTranlationRulesList 'AddSeattleAreaCode'</span><span class="sxs-lookup"><span data-stu-id="8086d-571">InboundTeamsNumberTranlationRulesList ‘AddSeattleAreaCode’</span></span>         |
|<span data-ttu-id="8086d-572">Para</span><span class="sxs-lookup"><span data-stu-id="8086d-572">TO</span></span>    |<span data-ttu-id="8086d-573">PARA: \<SIP:0100@sbc.contoso.com></span><span class="sxs-lookup"><span data-stu-id="8086d-573">TO: \<sip:0100@sbc.contoso.com></span></span>|<span data-ttu-id="8086d-574">PARA: \<SIP:4255555555@sbc.contoso.com></span><span class="sxs-lookup"><span data-stu-id="8086d-574">TO: \<sip:4255555555@sbc.contoso.com></span></span>|<span data-ttu-id="8086d-575">InboundTeamsNumberTranlationRulesList 'AddSeattleAreaCode'</span><span class="sxs-lookup"><span data-stu-id="8086d-575">InboundTeamsNumberTranlationRulesList ‘AddSeattleAreaCode’</span></span>       |
|<span data-ttu-id="8086d-576">De</span><span class="sxs-lookup"><span data-stu-id="8086d-576">FROM</span></span>   |<span data-ttu-id="8086d-577">DE: \<SIP:+12065550100@sbc.contoso.com></span><span class="sxs-lookup"><span data-stu-id="8086d-577">FROM: \<sip:+12065550100@sbc.contoso.com></span></span>|<span data-ttu-id="8086d-578">DE: \<SIP:2065550100@sbc.contoso.com></span><span class="sxs-lookup"><span data-stu-id="8086d-578">FROM: \<sip:2065550100@sbc.contoso.com></span></span>| <span data-ttu-id="8086d-579">InboundPSTNNumberTranlationRulesList 'StripPlus1'</span><span class="sxs-lookup"><span data-stu-id="8086d-579">InboundPSTNNumberTranlationRulesList ‘StripPlus1’</span></span> |

## <a name="see-also"></a><span data-ttu-id="8086d-580">Vea también</span><span class="sxs-lookup"><span data-stu-id="8086d-580">See also</span></span>

[<span data-ttu-id="8086d-581">Planear el enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="8086d-581">Plan Direct Routing</span></span>](direct-routing-plan.md)
