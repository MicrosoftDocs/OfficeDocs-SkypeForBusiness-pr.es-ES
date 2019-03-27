---
title: Configurar el enrutamiento directo
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
appliesto: Microsoft Teams
description: Obtenga información sobre cómo configurar el enrutamiento directo de Microsoft teléfono del sistema.
ms.openlocfilehash: 20bd29bdd2ba83050bd83513f513732ce646cbbe
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30883570"
---
# <a name="configure-direct-routing"></a><span data-ttu-id="697dd-103">Configurar el enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="697dd-103">Configure Direct Routing</span></span>

> [!Tip]
> <span data-ttu-id="697dd-104">Vea la sesión para obtener información sobre las ventajas de Direct enrutamiento, cómo planear para él y cómo implementarlo siguiente: [El enrutamiento directo en los equipos de Microsoft](https://aka.ms/teams-direct-routing)</span><span class="sxs-lookup"><span data-stu-id="697dd-104">Watch the following session to learn about the benefits of Direct Routing, how to plan for it, and how to deploy it: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing)</span></span>

<span data-ttu-id="697dd-105">Si no lo ha hecho ya, lea [Planear el enrutamiento directo](direct-routing-plan.md) para los requisitos previos y para revisar otros pasos debe realizar antes de configurar la red del sistema de teléfono de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="697dd-105">If you have not already done so, read [Plan Direct Routing](direct-routing-plan.md) for prerequisites and to review other steps you’ll need to take before you configure your Microsoft Phone System network.</span></span> 

<span data-ttu-id="697dd-106">En este artículo se describe cómo configurar el enrutamiento directo de Microsoft teléfono del sistema.</span><span class="sxs-lookup"><span data-stu-id="697dd-106">This article describes how to configure Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="697dd-107">Detalla cómo emparejar un controlador de borde de sesión (SBC) admitidos para el enrutamiento directo y cómo configurar los usuarios de Microsoft Teams para usar el enrutamiento directo para conectarse a la red telefónica pública conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="697dd-107">It details how to pair a supported Session Border Controller (SBC) to Direct Routing and how to configure Microsoft Teams users to use Direct Routing to connect to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="697dd-108">Para completar los pasos que se explican en este artículo, los administradores necesitan un poco familiarizado con los cmdlets de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="697dd-108">To complete the steps explained in this article, administrators need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="697dd-109">Para obtener más información acerca del uso de PowerShell, vea [Configurar el equipo de Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="697dd-109">For more information about using PowerShell, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 

<span data-ttu-id="697dd-110">Se recomienda que confirme que ya se ha configurado la SBC recomendada por su proveedor de SBC:</span><span class="sxs-lookup"><span data-stu-id="697dd-110">We recommend that you confirm that your SBC has already been configured as recommended by your SBC vendor:</span></span> 

- [<span data-ttu-id="697dd-111">Documentación de implementación de AudioCodes</span><span class="sxs-lookup"><span data-stu-id="697dd-111">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="697dd-112">Documentación de implementación de comunicaciones de la cinta de opciones</span><span class="sxs-lookup"><span data-stu-id="697dd-112">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)

<span data-ttu-id="697dd-113">Puede configurar el sistema de teléfono de Microsoft y permiten a los usuarios usar el enrutamiento directo, a continuación, configurar Microsoft Teams como el cliente preferido de la llamada al completar los procedimientos siguientes:</span><span class="sxs-lookup"><span data-stu-id="697dd-113">You can configure your Microsoft Phone System and enable users to use Direct Routing, then set up Microsoft Teams as the preferred calling client by completing the following procedures:</span></span> 

- [<span data-ttu-id="697dd-114">Empareje la SBC con un sistema de teléfono de Microsoft y validar el emparejamiento</span><span class="sxs-lookup"><span data-stu-id="697dd-114">Pair the SBC with a Microsoft Phone System and validate the pairing</span></span>](#pair-the-sbc-to-direct-routing-service-of-phone-system)
- [<span data-ttu-id="697dd-115">Habilitar a usuarios para el servicio de enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="697dd-115">Enable users for Direct Routing Service</span></span>](#enable-users-for-direct-routing-service)
- [<span data-ttu-id="697dd-116">Asegúrese de que Microsoft Teams es el cliente llamado preferido para los usuarios</span><span class="sxs-lookup"><span data-stu-id="697dd-116">Ensure that Microsoft Teams is the preferred calling client for the users</span></span>](#set-microsoft-teams-as-the-preferred-calling-client-for-users) 

## <a name="pair-the-sbc-to-the-direct-routing-service-of-phone-system"></a><span data-ttu-id="697dd-117">Empareje la SBC para el servicio de enrutamiento directo del sistema de teléfono</span><span class="sxs-lookup"><span data-stu-id="697dd-117">Pair the SBC to the Direct Routing Service of Phone System</span></span> 

<span data-ttu-id="697dd-118">Los siguientes son los tres pasos de alto nivel para permitirle conectarse o emparejar la SBC a la interfaz de enrutamiento directo:</span><span class="sxs-lookup"><span data-stu-id="697dd-118">The following are the three high-level steps to let you connect, or pair, the SBC to the Direct Routing interface:</span></span> 

- <span data-ttu-id="697dd-119">Conectarse al centro de administración de **Skype para profesionales en línea** con PowerShell</span><span class="sxs-lookup"><span data-stu-id="697dd-119">Connect to **Skype for Business Online** admin center using PowerShell</span></span> 
- <span data-ttu-id="697dd-120">Par el SBC</span><span class="sxs-lookup"><span data-stu-id="697dd-120">Pair the SBC</span></span> 
- <span data-ttu-id="697dd-121">Validar el emparejamiento</span><span class="sxs-lookup"><span data-stu-id="697dd-121">Validate the pairing</span></span> 

### <a name="connect-to-skype-for-business-online-by-using-powershell"></a><span data-ttu-id="697dd-122">Conectarse a Skype para profesionales en línea mediante el uso de PowerShell</span><span class="sxs-lookup"><span data-stu-id="697dd-122">Connect to Skype for Business Online by using PowerShell</span></span> 

<span data-ttu-id="697dd-123">Puede usar una sesión de PowerShell conectado a los inquilinos para emparejar la SBC a la interfaz de enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="697dd-123">You can use a PowerShell session connected to the tenant to pair the SBC to the Direct Routing interface.</span></span> <span data-ttu-id="697dd-124">Para abrir una sesión de PowerShell, siga los pasos descritos en [Configurar el equipo de Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="697dd-124">To open a PowerShell session, please follow the steps outlined in [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 
 
<span data-ttu-id="697dd-125">Después de establecer una sesión remota de PowerShell, compruebe que puede ver los comandos para administrar la SBC.</span><span class="sxs-lookup"><span data-stu-id="697dd-125">After you establish a remote PowerShell session, please validate that you can see the commands to manage the SBC.</span></span> <span data-ttu-id="697dd-126">Para validar los comandos, escriba o copiar y pegar en las siguientes opciones en la sesión de PowerShell y presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="697dd-126">To validate the commands, type or copy/paste in the following in the PowerShell session and press Enter:</span></span> 

```
Get-Command *onlinePSTNGateway*
```

<span data-ttu-id="697dd-127">El comando devolverá las cuatro funciones que se muestra aquí que le permiten administrar el SBC.</span><span class="sxs-lookup"><span data-stu-id="697dd-127">Your command will return the four functions shown here that will let you manage the SBC.</span></span> 

<pre>
CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
</pre>   


### <a name="pair-the-sbc-to-the-tenant"></a><span data-ttu-id="697dd-128">Par la SBC para el inquilino</span><span class="sxs-lookup"><span data-stu-id="697dd-128">Pair the SBC to the tenant</span></span> 

<span data-ttu-id="697dd-129">Para emparejar la SBC para el inquilino, en la sesión de PowerShell, escriba lo siguiente y presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="697dd-129">To pair the SBC to the tenant, in the PowerShell session type the following and press Enter:</span></span> 

```
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignallingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true 
```
  > [!NOTE]
  > 1. <span data-ttu-id="697dd-130">Se recomienda establecer un límite máximo de llamadas en la SBC, uso de la información que se encuentra en la documentación de SBC.</span><span class="sxs-lookup"><span data-stu-id="697dd-130">We highly recommend setting a maximum call limit in the SBC, using information that can be found in the SBC documentation.</span></span> <span data-ttu-id="697dd-131">El límite activará una notificación si la SBC está en el nivel de capacidad.</span><span class="sxs-lookup"><span data-stu-id="697dd-131">The limit will trigger a notification if the SBC is at the capacity level.</span></span>
  > 2. <span data-ttu-id="697dd-132">Sólo puede emparejar la SBC si la parte del dominio de su FQDN coincide con uno de los dominios registrados en el inquilino, excepto \*. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="697dd-132">You can only pair the SBC if the domain portion of its FQDN matches one of the domains registered in your tenant, except \*.onmicrosoft.com.</span></span> <span data-ttu-id="697dd-133">Uso de \*. onmicrosoft.com los nombres de dominio no es compatible con el nombre FQDN SBC.</span><span class="sxs-lookup"><span data-stu-id="697dd-133">Using \*.onmicrosoft.com domain names is not supported for the SBC FQDN name.</span></span> <span data-ttu-id="697dd-134">Por ejemplo, si tiene dos nombres de dominio:</span><span class="sxs-lookup"><span data-stu-id="697dd-134">For example, if you have two domain names:</span></span><br/><br/>
  > <span data-ttu-id="697dd-135">**Contoso**.com</span><span class="sxs-lookup"><span data-stu-id="697dd-135">**contoso**.com</span></span><br/><span data-ttu-id="697dd-136">**Contoso**. onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="697dd-136">**contoso**.onmicrosoft.com</span></span><br/><br/>
  > <span data-ttu-id="697dd-137">Para el nombre SBC, puede usar el nombre sbc.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="697dd-137">For the SBC name, you can use the name sbc.contoso.com.</span></span> <span data-ttu-id="697dd-138">Si se intenta emparejar la SBC con un nombre sbc.contoso.abc, el sistema no le, como el dominio no pertenece a este inquilino.</span><span class="sxs-lookup"><span data-stu-id="697dd-138">If you try to pair the SBC with a name sbc.contoso.abc, the system will not let you, as the domain is not owned by this tenant.</span></span>

```
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignallingPort 5067 -MaxConcurrentSessions 100 
```
<span data-ttu-id="697dd-139">Devuelve:</span><span class="sxs-lookup"><span data-stu-id="697dd-139">Returns:</span></span>
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
<span data-ttu-id="697dd-140">Existen opciones adicionales que se pueden establecer durante el proceso de emparejamiento.</span><span class="sxs-lookup"><span data-stu-id="697dd-140">There are additional options that can be set during the pairing process.</span></span> <span data-ttu-id="697dd-141">En el ejemplo anterior, sin embargo, solo la mínima necesaria se muestran los parámetros.</span><span class="sxs-lookup"><span data-stu-id="697dd-141">In the previous example, however, only the minimum required parameters are shown.</span></span> 
 
<span data-ttu-id="697dd-142">En la siguiente tabla se enumera los parámetros adicionales que puede usar en la configuración de parámetros para`New-CsOnlinePstnGateway`</span><span class="sxs-lookup"><span data-stu-id="697dd-142">The following table lists the additional parameters that you can use in setting parameters for `New-CsOnlinePstnGateway`</span></span>

|<span data-ttu-id="697dd-143">¿Obligatorio?</span><span class="sxs-lookup"><span data-stu-id="697dd-143">Required?</span></span>|<span data-ttu-id="697dd-144">Nombre</span><span class="sxs-lookup"><span data-stu-id="697dd-144">Name</span></span>|<span data-ttu-id="697dd-145">Descripción</span><span class="sxs-lookup"><span data-stu-id="697dd-145">Description</span></span>|<span data-ttu-id="697dd-146">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="697dd-146">Default</span></span>|<span data-ttu-id="697dd-147">Valores posibles</span><span class="sxs-lookup"><span data-stu-id="697dd-147">Possible values</span></span>|<span data-ttu-id="697dd-148">Tipo y restricciones</span><span class="sxs-lookup"><span data-stu-id="697dd-148">Type and restrictions</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="697dd-149">Sí</span><span class="sxs-lookup"><span data-stu-id="697dd-149">Yes</span></span>|<span data-ttu-id="697dd-150">FQDN</span><span class="sxs-lookup"><span data-stu-id="697dd-150">FQDN</span></span>|<span data-ttu-id="697dd-151">El nombre FQDN de la SBC</span><span class="sxs-lookup"><span data-stu-id="697dd-151">The FQDN name of the SBC</span></span> |<span data-ttu-id="697dd-152">Ninguno</span><span class="sxs-lookup"><span data-stu-id="697dd-152">None</span></span>|<span data-ttu-id="697dd-153">Nombre de NoneFQDN, límite 63 caracteres</span><span class="sxs-lookup"><span data-stu-id="697dd-153">NoneFQDN name, limit 63 characters</span></span>|<span data-ttu-id="697dd-154">Cadena, lista de caracteres permitidos y no permitidos en [las convenciones de nomenclatura en Active Directory para equipos, dominios, sitios y unidades organizativas](https://support.microsoft.com/help/909264)</span><span class="sxs-lookup"><span data-stu-id="697dd-154">String, list of allowed and disallowed characters on [Naming conventions in Active Directory for computers, domains, sites, and OUs](https://support.microsoft.com/help/909264)</span></span>|
|<span data-ttu-id="697dd-155">No</span><span class="sxs-lookup"><span data-stu-id="697dd-155">No</span></span>|<span data-ttu-id="697dd-156">MediaBypass</span><span class="sxs-lookup"><span data-stu-id="697dd-156">MediaBypass</span></span> |<span data-ttu-id="697dd-157">El parámetro reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="697dd-157">The parameter reserved for future use.</span></span> <span data-ttu-id="697dd-158">Parámetro indicado de la SBC admite el desvío de medios y el administrador desea usarlo.</span><span class="sxs-lookup"><span data-stu-id="697dd-158">Parameter indicated of the SBC supports Media Bypass and the administrator wants to use it.</span></span>|<span data-ttu-id="697dd-159">Ninguno</span><span class="sxs-lookup"><span data-stu-id="697dd-159">None</span></span>|<span data-ttu-id="697dd-160">True</span><span class="sxs-lookup"><span data-stu-id="697dd-160">True</span></span><br/><span data-ttu-id="697dd-161">False</span><span class="sxs-lookup"><span data-stu-id="697dd-161">False</span></span>|<span data-ttu-id="697dd-162">Boolean</span><span class="sxs-lookup"><span data-stu-id="697dd-162">Boolean</span></span>|
|<span data-ttu-id="697dd-163">Sí</span><span class="sxs-lookup"><span data-stu-id="697dd-163">Yes</span></span>|<span data-ttu-id="697dd-164">SipSignallingPort</span><span class="sxs-lookup"><span data-stu-id="697dd-164">SipSignallingPort</span></span> |<span data-ttu-id="697dd-165">Puerto de escucha usado para la comunicación con los servicios de enrutamiento directa mediante el protocolo de seguridad de capa de transporte (TLS).</span><span class="sxs-lookup"><span data-stu-id="697dd-165">Listening port used for communicating with Direct Routing services by using the Transport Layer Security (TLS) protocol.</span></span>|<span data-ttu-id="697dd-166">Ninguno</span><span class="sxs-lookup"><span data-stu-id="697dd-166">None</span></span>|<span data-ttu-id="697dd-167">Cualquier puerto</span><span class="sxs-lookup"><span data-stu-id="697dd-167">Any port</span></span>|<span data-ttu-id="697dd-168">0 a 65535</span><span class="sxs-lookup"><span data-stu-id="697dd-168">0 to 65535</span></span> |
|<span data-ttu-id="697dd-169">No</span><span class="sxs-lookup"><span data-stu-id="697dd-169">No</span></span>|<span data-ttu-id="697dd-170">FailoverTimeSeconds</span><span class="sxs-lookup"><span data-stu-id="697dd-170">FailoverTimeSeconds</span></span> |<span data-ttu-id="697dd-171">Cuando se establece en 10 (valor predeterminado), las llamadas salientes que no hay respondidas por la puerta de enlace dentro de 10 segundos se enrutan al siguiente tronco disponible; Si no hay ningún troncos adicionales, automáticamente se interrumpe la llamada.</span><span class="sxs-lookup"><span data-stu-id="697dd-171">When set to 10 (default value), outbound calls that are not answered by the gateway within 10 seconds are routed to the next available trunk; if there are no additional trunks, then the call is automatically dropped.</span></span> <span data-ttu-id="697dd-172">En una organización con redes y respuestas de puerta de enlace lentas, esto puede tener como resultado que las llamadas se pierdan innecesariamente.</span><span class="sxs-lookup"><span data-stu-id="697dd-172">In an organization with slow networks and gateway responses, that could potentially result in calls being dropped unnecessarily.</span></span> <span data-ttu-id="697dd-173">El valor predeterminado es 10.</span><span class="sxs-lookup"><span data-stu-id="697dd-173">The default value is 10.</span></span>|<span data-ttu-id="697dd-174">10</span><span class="sxs-lookup"><span data-stu-id="697dd-174">10</span></span>|<span data-ttu-id="697dd-175">Número</span><span class="sxs-lookup"><span data-stu-id="697dd-175">Number</span></span>|<span data-ttu-id="697dd-176">Int</span><span class="sxs-lookup"><span data-stu-id="697dd-176">Int</span></span>|
|<span data-ttu-id="697dd-177">No</span><span class="sxs-lookup"><span data-stu-id="697dd-177">No</span></span>|<span data-ttu-id="697dd-178">ForwardCallHistory</span><span class="sxs-lookup"><span data-stu-id="697dd-178">ForwardCallHistory</span></span> |<span data-ttu-id="697dd-179">Indica si la información del historial de llamadas se reenviará a través del tronco.</span><span class="sxs-lookup"><span data-stu-id="697dd-179">Indicates whether call history information will be forwarded through the trunk.</span></span> <span data-ttu-id="697dd-180">Si se habilita, el Proxy de RTC de Office 365 envía dos encabezados: información de historial y remitido por.</span><span class="sxs-lookup"><span data-stu-id="697dd-180">If enabled, the Office 365 PSTN Proxy sends two headers: History-info and Referred-By.</span></span> <span data-ttu-id="697dd-181">El valor predeterminado es **False** ($False).</span><span class="sxs-lookup"><span data-stu-id="697dd-181">The default value is **False** ($False).</span></span> |<span data-ttu-id="697dd-182">False</span><span class="sxs-lookup"><span data-stu-id="697dd-182">False</span></span>|<span data-ttu-id="697dd-183">True</span><span class="sxs-lookup"><span data-stu-id="697dd-183">True</span></span><br/><span data-ttu-id="697dd-184">False</span><span class="sxs-lookup"><span data-stu-id="697dd-184">False</span></span>|<span data-ttu-id="697dd-185">Boolean</span><span class="sxs-lookup"><span data-stu-id="697dd-185">Boolean</span></span>|
|<span data-ttu-id="697dd-186">No</span><span class="sxs-lookup"><span data-stu-id="697dd-186">No</span></span>|<span data-ttu-id="697dd-187">ForwardPAI</span><span class="sxs-lookup"><span data-stu-id="697dd-187">ForwardPAI</span></span>|<span data-ttu-id="697dd-188">Indica si el encabezado P-Asserted-Identity (PAI) se reenviará junto con la llamada.</span><span class="sxs-lookup"><span data-stu-id="697dd-188">Indicates whether the P-Asserted-Identity (PAI) header will be forwarded along with the call.</span></span> <span data-ttu-id="697dd-189">El encabezado PAI proporciona un método para comprobar la identidad de la persona que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="697dd-189">The PAI header provides a way to verify the identity of the caller.</span></span> <span data-ttu-id="697dd-190">Si se habilita la privacidad: identificador también se enviará el encabezado.</span><span class="sxs-lookup"><span data-stu-id="697dd-190">If enabled the Privacy:ID header will also be sent.</span></span> <span data-ttu-id="697dd-191">El valor predeterminado es **False** ($False).</span><span class="sxs-lookup"><span data-stu-id="697dd-191">The default value is **False** ($False).</span></span>|<span data-ttu-id="697dd-192">False</span><span class="sxs-lookup"><span data-stu-id="697dd-192">False</span></span>|<span data-ttu-id="697dd-193">True</span><span class="sxs-lookup"><span data-stu-id="697dd-193">True</span></span><br/><span data-ttu-id="697dd-194">False</span><span class="sxs-lookup"><span data-stu-id="697dd-194">False</span></span>|<span data-ttu-id="697dd-195">Boolean</span><span class="sxs-lookup"><span data-stu-id="697dd-195">Boolean</span></span>|
|<span data-ttu-id="697dd-196">No</span><span class="sxs-lookup"><span data-stu-id="697dd-196">No</span></span>|<span data-ttu-id="697dd-197">SendSIPOptions</span><span class="sxs-lookup"><span data-stu-id="697dd-197">SendSIPOptions</span></span> |<span data-ttu-id="697dd-198">Define si un SBC se o no enviará las opciones de SIP.</span><span class="sxs-lookup"><span data-stu-id="697dd-198">Defines if an SBC will or will not send the SIP options.</span></span> <span data-ttu-id="697dd-199">Si deshabilita esta opción, la SBC se excluirán del sistema de supervisión y alertas.</span><span class="sxs-lookup"><span data-stu-id="697dd-199">If disabled, the SBC will be excluded from Monitoring and Alerting system.</span></span> <span data-ttu-id="697dd-200">Se recomienda encarecidamente que habilite las opciones de SIP.</span><span class="sxs-lookup"><span data-stu-id="697dd-200">We highly recommend that you enable SIP options.</span></span> <span data-ttu-id="697dd-201">Valor predeterminado es **True**.</span><span class="sxs-lookup"><span data-stu-id="697dd-201">Default value is **True**.</span></span> |<span data-ttu-id="697dd-202">True</span><span class="sxs-lookup"><span data-stu-id="697dd-202">True</span></span>|<span data-ttu-id="697dd-203">True</span><span class="sxs-lookup"><span data-stu-id="697dd-203">True</span></span><br/><span data-ttu-id="697dd-204">False</span><span class="sxs-lookup"><span data-stu-id="697dd-204">False</span></span>|<span data-ttu-id="697dd-205">Boolean</span><span class="sxs-lookup"><span data-stu-id="697dd-205">Boolean</span></span>|
|<span data-ttu-id="697dd-206">No</span><span class="sxs-lookup"><span data-stu-id="697dd-206">No</span></span>|<span data-ttu-id="697dd-207">MaxConcurrentSessions</span><span class="sxs-lookup"><span data-stu-id="697dd-207">MaxConcurrentSessions</span></span> |<span data-ttu-id="697dd-208">Usada por el sistema de alertas.</span><span class="sxs-lookup"><span data-stu-id="697dd-208">Used by alerting system.</span></span> <span data-ttu-id="697dd-209">Cuando se establece ningún valor, el sistema de alertas generará una alerta para el Administrador de inquilinos cuando el número de sesión simultáneo es 90% o mayor que este valor.</span><span class="sxs-lookup"><span data-stu-id="697dd-209">When any value is set, the alerting system will generate an alert to the tenant administrator when the number of concurrent session is 90% or higher than this value.</span></span> <span data-ttu-id="697dd-210">Si no se establece el parámetro, no se generan las alertas.</span><span class="sxs-lookup"><span data-stu-id="697dd-210">If parameter is not set, the alerts are not generated.</span></span> <span data-ttu-id="697dd-211">Sin embargo, el sistema de supervisión informará número de sesiones simultáneas cada 24 horas.</span><span class="sxs-lookup"><span data-stu-id="697dd-211">However, the monitoring system will report number of concurrent session every 24 hours.</span></span> |<span data-ttu-id="697dd-212">Null</span><span class="sxs-lookup"><span data-stu-id="697dd-212">Null</span></span>|<span data-ttu-id="697dd-213">Null</span><span class="sxs-lookup"><span data-stu-id="697dd-213">Null</span></span><br/><span data-ttu-id="697dd-214">1 y 100.000.</span><span class="sxs-lookup"><span data-stu-id="697dd-214">1 to 100,000</span></span> ||
|<span data-ttu-id="697dd-215">No</span><span class="sxs-lookup"><span data-stu-id="697dd-215">No</span></span>|<span data-ttu-id="697dd-216">Habilitado \*</span><span class="sxs-lookup"><span data-stu-id="697dd-216">Enabled\*</span></span>|<span data-ttu-id="697dd-217">Se usa para habilitar este SBC para las llamadas salientes.</span><span class="sxs-lookup"><span data-stu-id="697dd-217">Used to enable this SBC for outbound calls.</span></span> <span data-ttu-id="697dd-218">Puede usarse para quitar temporalmente el SBC, mientras se está actualizando o durante el mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="697dd-218">Can be used to temporarily remove the SBC, while it is being updated or during maintenance.</span></span> |<span data-ttu-id="697dd-219">False</span><span class="sxs-lookup"><span data-stu-id="697dd-219">False</span></span>|<span data-ttu-id="697dd-220">True</span><span class="sxs-lookup"><span data-stu-id="697dd-220">True</span></span><br/><span data-ttu-id="697dd-221">False</span><span class="sxs-lookup"><span data-stu-id="697dd-221">False</span></span>|<span data-ttu-id="697dd-222">Boolean</span><span class="sxs-lookup"><span data-stu-id="697dd-222">Boolean</span></span>|
 
### <a name="verify-the-sbc-pairing"></a><span data-ttu-id="697dd-223">Compruebe el emparejamiento de SBC</span><span class="sxs-lookup"><span data-stu-id="697dd-223">Verify the SBC pairing</span></span> 

<span data-ttu-id="697dd-224">Compruebe la conexión:</span><span class="sxs-lookup"><span data-stu-id="697dd-224">Verify the connection:</span></span> 
- <span data-ttu-id="697dd-225">Compruebe si la SBC está en la lista de SBCs emparejados.</span><span class="sxs-lookup"><span data-stu-id="697dd-225">Check if the SBC is on the list of paired SBCs.</span></span> 
- <span data-ttu-id="697dd-226">Validar las opciones de SIP.</span><span class="sxs-lookup"><span data-stu-id="697dd-226">Validate SIP Options.</span></span> 
 
#### <a name="validate-if-the-sbc-is-on-the-list-of-paired-sbcs"></a><span data-ttu-id="697dd-227">Validar si la SBC está en la lista de SBCs emparejados</span><span class="sxs-lookup"><span data-stu-id="697dd-227">Validate if the SBC is on the list of paired SBCs</span></span> 

<span data-ttu-id="697dd-228">Después de par el SBC, validar que el SBC está presente en la lista de SBCs emparejados ejecutando el siguiente comando en una sesión remota de PowerShell:`Get-CSOnlinePSTNGateway`</span><span class="sxs-lookup"><span data-stu-id="697dd-228">After you pair the SBC, validate that the SBC is present in the list of paired SBCs by running the following command in a remote PowerShell session: `Get-CSOnlinePSTNGateway`</span></span>

<span data-ttu-id="697dd-229">La puerta de enlace emparejado debe aparecer en la lista tal como se muestra en el ejemplo siguiente y compruebe que el parámetro *Enabled* muestra el valor **True**.</span><span class="sxs-lookup"><span data-stu-id="697dd-229">The paired gateway should appear in the list as shown in the example below, and verify that the parameter *Enabled* displays the value **True**.</span></span> <span data-ttu-id="697dd-230">Escriba:</span><span class="sxs-lookup"><span data-stu-id="697dd-230">Enter:</span></span>

```
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```
<span data-ttu-id="697dd-231">Que devuelve:</span><span class="sxs-lookup"><span data-stu-id="697dd-231">Which returns:</span></span>
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

#### <a name="validate-sip-options-flow"></a><span data-ttu-id="697dd-232">Validar flujo de opciones de SIP</span><span class="sxs-lookup"><span data-stu-id="697dd-232">Validate SIP Options flow</span></span> 

<span data-ttu-id="697dd-233">Para validar el emparejamiento con opciones de SIP saliente, use la interfaz de administración de SBC y confirme que la SBC recibe 200 respuestas Aceptar a sus mensajes salientes de opciones.</span><span class="sxs-lookup"><span data-stu-id="697dd-233">To validate the pairing using outgoing SIP Options, use the SBC management interface and confirm that the SBC receives 200 OK responses to its outgoing OPTIONS messages.</span></span>

<span data-ttu-id="697dd-234">Cuando el enrutamiento directo ve opciones entrantes, se iniciará opciones salientes SIP mensajes al FQDN SBC configurados en el campo de encabezado de contacto en el mensaje entrante de las opciones de envío.</span><span class="sxs-lookup"><span data-stu-id="697dd-234">When Direct Routing sees incoming OPTIONS, it will start sending outgoing SIP Options messages to the SBC FQDN configured in the Contact header field in the incoming OPTIONS message.</span></span> 

<span data-ttu-id="697dd-235">Para validar el uso de las opciones de SIP entrantes de emparejamiento, usar la interfaz de administración de SBC y ver que la SBC envía una respuesta a los mensajes de las opciones que provienen de enrutamiento directo y que el código de respuesta que se envía es 200 Aceptar.</span><span class="sxs-lookup"><span data-stu-id="697dd-235">To validate the pairing using incoming SIP Options, use the SBC management interface and see that the SBC sends a reply to the OPTIONS messages coming in from Direct Routing and that the response code it sends is 200 OK.</span></span>

## <a name="enable-users-for-direct-routing-service"></a><span data-ttu-id="697dd-236">Habilitar a usuarios para el servicio de enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="697dd-236">Enable users for Direct Routing Service</span></span> 

<span data-ttu-id="697dd-237">Cuando esté listo para habilitar a los usuarios para el servicio de enrutamiento directa, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="697dd-237">When you are ready to enable users for the Direct Routing Service, follow these steps:</span></span> 

1. <span data-ttu-id="697dd-238">Crear un usuario en Office 365 y asigna una licencia de sistema de teléfono.</span><span class="sxs-lookup"><span data-stu-id="697dd-238">Create a user in Office 365 and assign a phone system license.</span></span> 
2. <span data-ttu-id="697dd-239">Asegúrese de que el usuario está hospedado en Skype para profesionales en línea.</span><span class="sxs-lookup"><span data-stu-id="697dd-239">Ensure that the user is homed in Skype for Business Online.</span></span> 
3. <span data-ttu-id="697dd-240">Configurar el número de teléfono y habilitar correo de voz y enterprise voice.</span><span class="sxs-lookup"><span data-stu-id="697dd-240">Configure the phone number and enable enterprise voice and voicemail.</span></span> 
4. <span data-ttu-id="697dd-241">Configurar enrutamiento de voz.</span><span class="sxs-lookup"><span data-stu-id="697dd-241">Configure voice routing.</span></span> <span data-ttu-id="697dd-242">La ruta se validará automáticamente.</span><span class="sxs-lookup"><span data-stu-id="697dd-242">The route is automatically validated.</span></span>

### <a name="create-a-user-in-office-365-and-assign-the-license"></a><span data-ttu-id="697dd-243">Crear un usuario en Office 365 y asignar la licencia</span><span class="sxs-lookup"><span data-stu-id="697dd-243">Create a user in Office 365 and assign the license</span></span> 

<span data-ttu-id="697dd-244">Hay dos opciones para crear un nuevo usuario en Office 365.</span><span class="sxs-lookup"><span data-stu-id="697dd-244">There are two options for creating a new user in Office 365.</span></span> <span data-ttu-id="697dd-245">Sin embargo, se recomienda que la organización, seleccione y utilice una opción para evitar problemas de enrutamiento:</span><span class="sxs-lookup"><span data-stu-id="697dd-245">However, we recommend that your organization select and use one option to avoid routing issues:</span></span> 

- <span data-ttu-id="697dd-246">Crear el usuario en Active Directory local y sincronizar el usuario a la nube.</span><span class="sxs-lookup"><span data-stu-id="697dd-246">Create the user in on-premises Active Directory and sync the user to the cloud.</span></span> <span data-ttu-id="697dd-247">Vea [directorios de integrar su local con Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span><span class="sxs-lookup"><span data-stu-id="697dd-247">See [Integrate your on-premises directories with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span></span>
- <span data-ttu-id="697dd-248">Crear el usuario directamente en el Portal de administrador de Office 365.</span><span class="sxs-lookup"><span data-stu-id="697dd-248">Create the user directly in the Office 365 Administrator Portal.</span></span> <span data-ttu-id="697dd-249">Vea [Agregar usuarios individualmente o de forma masiva a Office 365 - ayuda de administración](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span><span class="sxs-lookup"><span data-stu-id="697dd-249">See [Add users individually or in bulk to Office 365 - Admin Help](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span> 

<span data-ttu-id="697dd-250">Si su Skype para la implementación empresarial Online coexiste con Skype para 2015 empresarial o Lync 2010 o 2013 local, la única opción compatible es crear el usuario en Active Directory local y sincronizar el usuario a la nube (opción 1).</span><span class="sxs-lookup"><span data-stu-id="697dd-250">If your Skype for Business Online deployment co-exists with Skype for Business 2015 or Lync 2010/2013 on-premises, the only supported option is to create the user in on-premises Active Directory and sync the user to the cloud (Option 1).</span></span> 

<span data-ttu-id="697dd-251">Licencias necesarias:</span><span class="sxs-lookup"><span data-stu-id="697dd-251">Required licenses:</span></span> 

- <span data-ttu-id="697dd-252">Office 365 E3 de empresa (incluidos SfB Plan2, Exchange Plan2 y equipos) + del sistema de teléfono</span><span class="sxs-lookup"><span data-stu-id="697dd-252">Office 365 Enterprise E3 (including SfB Plan2, Exchange Plan2, and Teams) + Phone System</span></span>
- <span data-ttu-id="697dd-253">Office 365 Enterprise E5 (incluidos SfB Plan2, Plan2 de Exchange, los equipos y del sistema de teléfono)</span><span class="sxs-lookup"><span data-stu-id="697dd-253">Office 365 Enterprise E5 (including SfB Plan2, Exchange Plan2, Teams, and Phone System)</span></span> 

<span data-ttu-id="697dd-254">Licencias opcionales:</span><span class="sxs-lookup"><span data-stu-id="697dd-254">Optional licenses:</span></span> 

- <span data-ttu-id="697dd-255">Plan de llamada</span><span class="sxs-lookup"><span data-stu-id="697dd-255">Calling Plan</span></span> 
- <span data-ttu-id="697dd-256">Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="697dd-256">Audio Conferencing</span></span> 

### <a name="ensure-that-the-user-is-homed-in-skype-for-business-online"></a><span data-ttu-id="697dd-257">Asegúrese de que el usuario está hospedado en Skype para profesionales en línea</span><span class="sxs-lookup"><span data-stu-id="697dd-257">Ensure that the user is homed in Skype for Business Online</span></span> 

<span data-ttu-id="697dd-258">Enrutamiento directo requiere que el usuario a estar alojado en Skype para profesionales en línea.</span><span class="sxs-lookup"><span data-stu-id="697dd-258">Direct Routing requires the user to be homed in Skype for Business Online.</span></span> <span data-ttu-id="697dd-259">Puede comprobarlo mirando el parámetro RegistrarPool.</span><span class="sxs-lookup"><span data-stu-id="697dd-259">You can check this by looking at the RegistrarPool parameter.</span></span> <span data-ttu-id="697dd-260">Debe tener un valor en el dominio infra.lync.com.</span><span class="sxs-lookup"><span data-stu-id="697dd-260">It needs to have a value in the infra.lync.com domain.</span></span>

1. <span data-ttu-id="697dd-261">Conectar con PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="697dd-261">Connect to remote PowerShell.</span></span>
2. <span data-ttu-id="697dd-262">Problema el comando:</span><span class="sxs-lookup"><span data-stu-id="697dd-262">Issue the command:</span></span> 

```
Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool
``` 

### <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a><span data-ttu-id="697dd-263">Configurar el número de teléfono y habilitar correo de voz y telefonía IP empresarial</span><span class="sxs-lookup"><span data-stu-id="697dd-263">Configure the phone number and enable enterprise voice and voicemail</span></span> 

<span data-ttu-id="697dd-264">Una vez que haya creado el usuario y asigna una licencia, el siguiente paso es configurar su número de teléfono y correo de voz.</span><span class="sxs-lookup"><span data-stu-id="697dd-264">After you have created the user and assigned a license, the next step is to configure their phone number and voicemail.</span></span> <span data-ttu-id="697dd-265">Esto puede realizarse en un solo paso.</span><span class="sxs-lookup"><span data-stu-id="697dd-265">This can be done in one step.</span></span> 

<span data-ttu-id="697dd-266">Para agregar el número de teléfono y habilitar para correo de voz:</span><span class="sxs-lookup"><span data-stu-id="697dd-266">To add the phone number and enable for voicemail:</span></span>
 
1. <span data-ttu-id="697dd-267">Conectarse a una sesión remota de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="697dd-267">Connect to a remote PowerShell session.</span></span> 
2. <span data-ttu-id="697dd-268">Escriba el comando:</span><span class="sxs-lookup"><span data-stu-id="697dd-268">Enter the command:</span></span> 
 
```
Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<E.164 phone number>
```

<span data-ttu-id="697dd-269">Por ejemplo, para agregar un número de teléfono para el usuario "Sergio bajo", escribiría lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="697dd-269">For example, to add a phone number for user "Spencer Low," you would enter the following:</span></span> 

```
Set-CsUser -Identity "Spencer Low" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
```

<span data-ttu-id="697dd-270">El número de teléfono utilizado debe configurarse como un número de teléfono E.164 completo con el código de país.</span><span class="sxs-lookup"><span data-stu-id="697dd-270">The phone number used has to be configured as a full E.164 phone number with country code.</span></span> 

  > [!NOTE]
  > <span data-ttu-id="697dd-271">Si el número de teléfono del usuario se administra en local, use local Skype para Shell de administración de negocio o Panel de Control para configurar el número de teléfono del usuario.</span><span class="sxs-lookup"><span data-stu-id="697dd-271">If the user’s phone number is managed on premises, use on-premises Skype for Business Management Shell or Control Panel to configure the user's phone number.</span></span> 

### <a name="configure-voice-routing"></a><span data-ttu-id="697dd-272">Configurar enrutamiento de voz</span><span class="sxs-lookup"><span data-stu-id="697dd-272">Configure Voice Routing</span></span> 

<span data-ttu-id="697dd-273">Microsoft Phone System tiene un mecanismo de enrutamiento que permite que una llamada se envíen a un SBC específico en función de:</span><span class="sxs-lookup"><span data-stu-id="697dd-273">Microsoft Phone System has a routing mechanism that allows a call to be sent to a specific SBC based on:</span></span> 

- <span data-ttu-id="697dd-274">Patrón de número llamado</span><span class="sxs-lookup"><span data-stu-id="697dd-274">Called number pattern</span></span> 
- <span data-ttu-id="697dd-275">Patrón de número llamado + usuario específico que realiza la llamada</span><span class="sxs-lookup"><span data-stu-id="697dd-275">Called number pattern + Specific User who makes the call</span></span>
 
<span data-ttu-id="697dd-276">SBCs se pueden designar como activo y copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="697dd-276">SBCs can be designated as active and backup.</span></span> <span data-ttu-id="697dd-277">Es decir, cuando la SBC que está configurado como activo para este patrón de número, o patrón de número + usuario específico, no está disponible y, a continuación, se van a enrutar las llamadas a un SBC copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="697dd-277">That means when the SBC that is configured as active for this number pattern, or number pattern + specific user, is not available, then the calls will be routed to a backup SBC.</span></span>
 
<span data-ttu-id="697dd-278">Enrutamiento de llamadas se compone de los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="697dd-278">Call routing is made up of the following elements:</span></span> 
- <span data-ttu-id="697dd-279">Directiva de enrutamiento de voz: contenedor de usos de RTC; se pueden asignar a un usuario o a varios usuarios</span><span class="sxs-lookup"><span data-stu-id="697dd-279">Voice Routing Policy – container for PSTN Usages; can be assigned to a user or to multiple users</span></span> 
- <span data-ttu-id="697dd-280">Usos de RTC: contenedor de rutas de voz y los usos de RTC; se pueden compartir en diferentes directivas de enrutamiento de voz</span><span class="sxs-lookup"><span data-stu-id="697dd-280">PSTN Usages – container for Voice Routes and PSTN Usages; can be shared in different Voice Routing Policies</span></span> 
- <span data-ttu-id="697dd-281">Rutas: patrón de número y un conjunto de puertas de enlace RTC en línea que se usará para las llamadas donde número de llamada coincide con el patrón de voz</span><span class="sxs-lookup"><span data-stu-id="697dd-281">Voice Routes – number pattern and set of Online PSTN Gateways to use for calls where calling number matches the pattern</span></span> 
- <span data-ttu-id="697dd-282">Puerta de enlace de RTC Online - puntero a un SBC, también almacena la configuración que se aplica cuando se llama a través de SBC, como hacia delante P-Asserted-Identity (PAI) o códecs preferido; se pueden agregar a las rutas de voz</span><span class="sxs-lookup"><span data-stu-id="697dd-282">Online PSTN Gateway - pointer to an SBC, also stores the configuration that is applied when call is placed via the SBC, such as forward P-Asserted-Identity (PAI) or Preferred Codecs; can be added to Voice Routes</span></span> 

#### <a name="creating-a-voice-routing-policy-with-one-pstn-usage"></a><span data-ttu-id="697dd-283">Creación de una directiva de enrutamiento de voz con un uso de RTC</span><span class="sxs-lookup"><span data-stu-id="697dd-283">Creating a voice routing policy with one PSTN Usage</span></span> 

<span data-ttu-id="697dd-284">En el siguiente diagrama se muestra dos ejemplos de las directivas de enrutamiento de voz en el flujo de la llamada.</span><span class="sxs-lookup"><span data-stu-id="697dd-284">The following diagram shows two examples of voice routing policies in call flow.</span></span>

<span data-ttu-id="697dd-285">**Llamar al flujo de 1 (a la izquierda):** Si un usuario realiza una llamada a +1 425 XXX XX XX o +1 206 XXX XX XX, la llamada se enruta a SBC sbc1.contoso.biz o sbc2.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="697dd-285">**Call Flow 1 (on the left):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="697dd-286">Si ni sbc1.contoso.biz ni sbc2.contoso.biz están disponibles, se interrumpe la llamada.</span><span class="sxs-lookup"><span data-stu-id="697dd-286">If neither sbc1.contoso.biz nor sbc2.contoso.biz are available, the call is dropped.</span></span> 

<span data-ttu-id="697dd-287">**2 de flujo de llamadas (a la derecha):** Si un usuario realiza una llamada a +1 425 XXX XX XX o +1 206 XXX XX XX, la llamada se enruta primero a SBC sbc1.contoso.biz o sbc2.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="697dd-287">**Call Flow 2 (on the right):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is first routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="697dd-288">Si ninguno de los dos SBC está disponible, la ruta con la prioridad más baja será intentado (sbc3.contoso.biz y sbc4.contoso.biz).</span><span class="sxs-lookup"><span data-stu-id="697dd-288">If neither SBC is available, the route with lower priority will be tried (sbc3.contoso.biz and sbc4.contoso.biz).</span></span> <span data-ttu-id="697dd-289">Si ninguno de los SBCs están disponible, se interrumpe la llamada.</span><span class="sxs-lookup"><span data-stu-id="697dd-289">If none of the SBCs are available, the call is dropped.</span></span> 

![Se muestran ejemplos de directiva de enrutamiento de voz](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

<span data-ttu-id="697dd-291">En ambos ejemplos, mientras que la ruta de voz se asigna prioridades, el SBCs en las rutas se intentan en orden aleatorio.</span><span class="sxs-lookup"><span data-stu-id="697dd-291">In both examples, while the Voice Route is assigned priorities, the SBCs in the routes are tried in random order.</span></span>

  > [!NOTE]
  > <span data-ttu-id="697dd-292">A menos que el usuario también dispone de una licencia de llamar a planeación de Microsoft, se quitan las llamadas a cualquier número excepto los números que coincidan con los patrones de +1 425 XXX XX XX o +1 206 XXX XX XX en el ejemplo de configuración.</span><span class="sxs-lookup"><span data-stu-id="697dd-292">Unless the user also has a Microsoft Calling Plan license, calls to any number except numbers matching the patterns +1 425 XXX XX XX or +1 206 XXX XX XX in the example configuration are dropped.</span></span> <span data-ttu-id="697dd-293">Si el usuario tiene una licencia de planeación de la llamada, la llamada se enruta automáticamente según las directivas de la planeación de una llamada a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="697dd-293">If the user has a Calling Plan license, the call is automatically routed according to the policies of the Microsoft Calling Plan.</span></span> 

<span data-ttu-id="697dd-294">La planeación de una llamada a Microsoft se aplica automáticamente como la última ruta a todos los usuarios con la licencia de llamar a planeación de Microsoft y no requiere la configuración de enrutamiento de llamada adicionales.</span><span class="sxs-lookup"><span data-stu-id="697dd-294">The Microsoft Calling Plan applies automatically as the last route to all users with the Microsoft Calling Plan license and does not require additional call routing configuration.</span></span>

<span data-ttu-id="697dd-295">En el ejemplo que se muestra en el diagrama siguiente, se agrega una ruta de voz para enviar las llamadas a todos los demás Estados Unidos y Canadá número (llamadas que vaya a patrón de número llamado + 1 XXX XXX XX XX).</span><span class="sxs-lookup"><span data-stu-id="697dd-295">In the example shown in the following diagram, a voice route is added to send calls to all other US and Canadian number (calls that go to called number pattern +1 XXX XXX XX XX).</span></span>

![Directiva de enrutamiento con una tercera ruta de voz de muestra](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

<span data-ttu-id="697dd-297">Para todas las llamadas, si un usuario tiene dos licencias (sistema de teléfono de Microsoft y llamar a planeación de Microsoft), se usa ruta automático.</span><span class="sxs-lookup"><span data-stu-id="697dd-297">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), Automatic Route is used.</span></span> <span data-ttu-id="697dd-298">Si no hay nada coincide con los patrones de números en las rutas de voz en línea creadas por el administrador, se enruta a través de una llamada a planeación de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="697dd-298">If nothing matches the number patterns in the administrator-created online voice routes, route via Microsoft Calling Plan.</span></span>

<span data-ttu-id="697dd-299">Si el usuario tiene sólo del sistema de teléfono de Microsoft, se interrumpe la llamada porque no hay reglas de coincidencia están disponibles.</span><span class="sxs-lookup"><span data-stu-id="697dd-299">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

  > [!NOTE]
  > <span data-ttu-id="697dd-300">El valor de la prioridad de ruta "Otros + 1" no importa en este caso, como hay sólo una ruta que coincide con el patrón + 1 XXX XXX XX XX.</span><span class="sxs-lookup"><span data-stu-id="697dd-300">The Priority value for route "Other +1" doesn’t matter in this case, as there is only one route that matches the pattern +1 XXX XXX XX XX.</span></span> <span data-ttu-id="697dd-301">Si un usuario realiza una llamada a + 1 324 567 89 89 y sbc5.contoso.biz y sbc6.contoso.biz no están disponibles, se interrumpe la llamada.</span><span class="sxs-lookup"><span data-stu-id="697dd-301">If a user makes a call to +1 324 567 89 89 and both sbc5.contoso.biz and sbc6.contoso.biz are unavailable, the call is dropped.</span></span>

<span data-ttu-id="697dd-302">La tabla siguiente resume la configuración con tres rutas de voz.</span><span class="sxs-lookup"><span data-stu-id="697dd-302">The following table summarizes the configuration using three voice routes.</span></span> <span data-ttu-id="697dd-303">En este ejemplo, todas las rutas de tres forman parte de la misma uso de RTC "Nosotros y Canadá".</span><span class="sxs-lookup"><span data-stu-id="697dd-303">In this example, all three routes are part of the same PSTN Usage "US and Canada".</span></span>

|<span data-ttu-id="697dd-304">**Uso de RTC**</span><span class="sxs-lookup"><span data-stu-id="697dd-304">**PSTN usage**</span></span>|<span data-ttu-id="697dd-305">**Ruta de voz**</span><span class="sxs-lookup"><span data-stu-id="697dd-305">**Voice route**</span></span>|<span data-ttu-id="697dd-306">**Patrón de números**</span><span class="sxs-lookup"><span data-stu-id="697dd-306">**Number pattern**</span></span>|<span data-ttu-id="697dd-307">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="697dd-307">**Priority**</span></span>|<span data-ttu-id="697dd-308">**SBC**</span><span class="sxs-lookup"><span data-stu-id="697dd-308">**SBC**</span></span>|<span data-ttu-id="697dd-309">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="697dd-309">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="697dd-310">NOSOTROS solo</span><span class="sxs-lookup"><span data-stu-id="697dd-310">US only</span></span>|<span data-ttu-id="697dd-311">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="697dd-311">"Redmond 1"</span></span>|<span data-ttu-id="697dd-312">^\\+ 1 (425\|206)(\d{7})$</span><span class="sxs-lookup"><span data-stu-id="697dd-312">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="697dd-313">1</span><span class="sxs-lookup"><span data-stu-id="697dd-313">1</span></span>|<span data-ttu-id="697dd-314">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="697dd-314">sbc1.contoso.biz</span></span><br/><span data-ttu-id="697dd-315">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="697dd-315">sbc2.contoso.biz</span></span>|<span data-ttu-id="697dd-316">Ruta activa para números de llamada +1 425 XXX XX XX o +1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="697dd-316">Active route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="697dd-317">NOSOTROS solo</span><span class="sxs-lookup"><span data-stu-id="697dd-317">US only</span></span>|<span data-ttu-id="697dd-318">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="697dd-318">"Redmond 2"</span></span>|<span data-ttu-id="697dd-319">^\\+ 1 (425\|206)(\d{7})$</span><span class="sxs-lookup"><span data-stu-id="697dd-319">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="697dd-320">2</span><span class="sxs-lookup"><span data-stu-id="697dd-320">2</span></span>|<span data-ttu-id="697dd-321">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="697dd-321">sbc3.contoso.biz</span></span><br/><span data-ttu-id="697dd-322">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="697dd-322">sbc4.contoso.biz</span></span>|<span data-ttu-id="697dd-323">Ruta de reserva para los números llamados +1 425 XXX XX XX o +1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="697dd-323">Backup route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="697dd-324">NOSOTROS solo</span><span class="sxs-lookup"><span data-stu-id="697dd-324">US only</span></span>|<span data-ttu-id="697dd-325">"Otros + 1"</span><span class="sxs-lookup"><span data-stu-id="697dd-325">"Other +1"</span></span>|<span data-ttu-id="697dd-326">^\\+ 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="697dd-326">^\\+1(\d{10})$</span></span>|<span data-ttu-id="697dd-327">3</span><span class="sxs-lookup"><span data-stu-id="697dd-327">3</span></span>|<span data-ttu-id="697dd-328">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="697dd-328">sbc5.contoso.biz</span></span><br/><span data-ttu-id="697dd-329">sbc6.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="697dd-329">sbc6.contoso.biz</span></span>|<span data-ttu-id="697dd-330">Enrutar para números de llamada + 1 XXX XXX XX XX (excepto +1 425 XXX XX XX o +1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="697dd-330">Route for called numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|||||||

<span data-ttu-id="697dd-331">Todas las rutas se asocian con el uso de RTC "Nosotros y Canadá" y el uso de RTC está asociado con la directiva de enrutamiento de voz "Sólo en Estados Unidos."</span><span class="sxs-lookup"><span data-stu-id="697dd-331">All routes are associated with the PSTN Usage "US and Canada" and the PSTN Usage is associated with the Voice Routing Policy "US Only."</span></span> <span data-ttu-id="697dd-332">En este ejemplo, se asigna la directiva de enrutamiento de voz al usuario Spencer Low.</span><span class="sxs-lookup"><span data-stu-id="697dd-332">In this example, the voice routing policy is assigned to user Spencer Low.</span></span>

#### <a name="examples-of-call-routes"></a><span data-ttu-id="697dd-333">Ejemplos de rutas de llamadas</span><span class="sxs-lookup"><span data-stu-id="697dd-333">Examples of call routes</span></span>

<span data-ttu-id="697dd-334">En el siguiente ejemplo, demostraremos cómo configurar rutas, usos de RTC y las directivas de enrutamiento y se asigne la directiva para el usuario.</span><span class="sxs-lookup"><span data-stu-id="697dd-334">In the following example, we demonstrate how to configure Routes, PSTN Usages, and Routing policies, and we assign the policy to the user.</span></span>

<span data-ttu-id="697dd-335">**Paso 1:** Crear el uso de RTC "Estados Unidos y Canadá".</span><span class="sxs-lookup"><span data-stu-id="697dd-335">**Step 1:** Create the PSTN Usage "US and Canada".</span></span>

<span data-ttu-id="697dd-336">En un Skype para la sesión de PowerShell remoto empresarial, escriba:</span><span class="sxs-lookup"><span data-stu-id="697dd-336">In a Skype for Business Remote PowerShell session, type:</span></span>

```
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

<span data-ttu-id="697dd-337">Validar que el uso se ha creado escribiendo:</span><span class="sxs-lookup"><span data-stu-id="697dd-337">Validate that the usage was created by entering:</span></span> 
```
Get-CSOnlinePSTNUsage
``` 
<span data-ttu-id="697dd-338">Que devuelve una lista de nombres que es posible que esté truncada:</span><span class="sxs-lookup"><span data-stu-id="697dd-338">Which returns a list of names that may be truncated:</span></span>
```
  Identity  : Global
  Usage     : {testusage, US and Canada, International, karlUsage. . .}
```
<span data-ttu-id="697dd-339">En el ejemplo siguiente, puede ver el resultado de la ejecución del comando de PowerShell `(Get-CSOnlinePSTNUsage).usage` para mostrar los nombres completos (no truncados).</span><span class="sxs-lookup"><span data-stu-id="697dd-339">In the example below, you can see the result of the running the PowerShell command `(Get-CSOnlinePSTNUsage).usage` to display full names (not truncated).</span></span> 
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

<span data-ttu-id="697dd-340">**Paso 2:** En una sesión de PowerShell en Skype para profesionales en línea, cree tres rutas: Redmond 1, Redmond 2 y otros + 1, como se detalla en la tabla anterior.</span><span class="sxs-lookup"><span data-stu-id="697dd-340">**Step 2:** In a PowerShell session in Skype for Business Online, create three routes: Redmond 1, Redmond 2, and Other +1, as detailed in the previous table.</span></span> 

<span data-ttu-id="697dd-341">Para crear la ruta de "Redmond 1", escriba:</span><span class="sxs-lookup"><span data-stu-id="697dd-341">To create the "Redmond 1" route, enter:</span></span>

  ```
  New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
  (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
  ```

<span data-ttu-id="697dd-342">Que devuelve:</span><span class="sxs-lookup"><span data-stu-id="697dd-342">Which returns:</span></span>
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
<span data-ttu-id="697dd-343">Para crear la ruta de Redmond 2, escriba:</span><span class="sxs-lookup"><span data-stu-id="697dd-343">To create the Redmond 2 route, enter:</span></span>

```
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="697dd-344">Para crear la ruta de otra + 1, escriba:</span><span class="sxs-lookup"><span data-stu-id="697dd-344">To create the Other +1 route, enter:</span></span>

```
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > <span data-ttu-id="697dd-345">Asegúrese de que la expresión regular en el atributo NumberPattern es una expresión válida.</span><span class="sxs-lookup"><span data-stu-id="697dd-345">Make sure that your regular expression in the NumberPattern attribute is a valid expression.</span></span> <span data-ttu-id="697dd-346">Puede probarla con este sitio Web:[https://www.regexpal.com](https://www.regexpal.com)</span><span class="sxs-lookup"><span data-stu-id="697dd-346">You can test it using this website: [https://www.regexpal.com](https://www.regexpal.com)</span></span>

<span data-ttu-id="697dd-347">En algunos casos es necesario para enrutar todas las llamadas a la misma SBC; Por favor, use - NumberPattern ". \*"</span><span class="sxs-lookup"><span data-stu-id="697dd-347">In some cases there is a need to route all calls to the same SBC; please use -NumberPattern ".\*"</span></span>

- <span data-ttu-id="697dd-348">Enrutar todas las llamadas a la misma SBC</span><span class="sxs-lookup"><span data-stu-id="697dd-348">Route all calls to same SBC</span></span>

    ```
    Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" 
     -OnlinePstnGatewayList sbc1.contoso.biz
    ```

<span data-ttu-id="697dd-349">Validar que ha configurado correctamente la ruta mediante la ejecución de la `Get-CSOnlineVoiceRoute` comando de PowerShell mediante las opciones tal como se muestra:</span><span class="sxs-lookup"><span data-stu-id="697dd-349">Validate that you’ve correctly configured the route by running the `Get-CSOnlineVoiceRoute` PowerShell command using options as shown:</span></span> 

```
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
<span data-ttu-id="697dd-350">Que se debe devolver:</span><span class="sxs-lookup"><span data-stu-id="697dd-350">Which should return:</span></span>
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

<span data-ttu-id="697dd-351">En el ejemplo, la ruta "Otros + 1" automáticamente se asignó prioridad 4.</span><span class="sxs-lookup"><span data-stu-id="697dd-351">In the example, the route "Other +1" was automatically assigned priority 4.</span></span> 

<span data-ttu-id="697dd-352">**Paso 3:** Crear una directiva de enrutamiento de voz "Nosotros solo" y agregar a la directiva el uso de RTC "Estados Unidos y Canadá".</span><span class="sxs-lookup"><span data-stu-id="697dd-352">**Step 3:** Create a Voice Routing Policy "US Only" and add to the policy the PSTN Usage "US and Canada."</span></span>

<span data-ttu-id="697dd-353">En una sesión de PowerShell en Skype para profesionales en línea, escriba:</span><span class="sxs-lookup"><span data-stu-id="697dd-353">In a PowerShell session in Skype for Business Online, type:</span></span>

```
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="697dd-354">En este ejemplo, se muestra el resultado:</span><span class="sxs-lookup"><span data-stu-id="697dd-354">The result is shown in this example:</span></span>

<pre>
Identity        : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
</pre>

<span data-ttu-id="697dd-355">**Paso 4:** Conceder al usuario Spencer Low una directiva de enrutamiento de voz mediante el uso de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="697dd-355">**Step 4:** Grant to user Spencer Low a voice routing policy by using PowerShell.</span></span>

- <span data-ttu-id="697dd-356">En una sesión de PowerShell en Skype para profesionales en línea, escriba:</span><span class="sxs-lookup"><span data-stu-id="697dd-356">In a PowerShell session in Skype for Business Online, type:</span></span>

    ```Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"```

- <span data-ttu-id="697dd-357">Validar la asignación de directiva, escriba este comando:</span><span class="sxs-lookup"><span data-stu-id="697dd-357">Validate the policy assignment by entering this command:</span></span>

```
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```
<span data-ttu-id="697dd-358">Que devuelve:</span><span class="sxs-lookup"><span data-stu-id="697dd-358">Which returns:</span></span>
<pre>
    OnlineVoiceRoutingPolicy
    ---------------------
    US Only
</pre>

#### <a name="creating-a-voice-routing-policy-with-several-pstn-usages"></a><span data-ttu-id="697dd-359">Creación de una directiva de enrutamiento de voz con varios usos de RTC</span><span class="sxs-lookup"><span data-stu-id="697dd-359">Creating a Voice Routing Policy with several PSTN Usages</span></span>

<span data-ttu-id="697dd-360">La directiva de enrutamiento de voz creada anteriormente sólo permite las llamadas a números de teléfono en Estados Unidos y Canadá--a menos que la licencia de llamar a planeación de Microsoft también está asignada al usuario.</span><span class="sxs-lookup"><span data-stu-id="697dd-360">The Voice Routing Policy created previously only allows calls to phone numbers in the US and Canada--unless the Microsoft Calling Plan license is also assigned to the user.</span></span>

<span data-ttu-id="697dd-361">En el ejemplo siguiente, puede crear la directiva de enrutamiento de voz "No hay restricciones".</span><span class="sxs-lookup"><span data-stu-id="697dd-361">In the example that follows, you can create the Voice Routing Policy "No Restrictions."</span></span> <span data-ttu-id="697dd-362">La directiva vuelve a usar el uso de RTC "Nosotros y Canadá" creado en el ejemplo anterior, así como el uso de RTC nuevo "Internacional".</span><span class="sxs-lookup"><span data-stu-id="697dd-362">The policy reuses the PSTN Usage "US and Canada" created in the previous example, as well as the new PSTN Usage "International."</span></span> 

<span data-ttu-id="697dd-363">Esto enruta todas las llamadas a la SBCs sbc2.contoso.biz y sbc5.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="697dd-363">This routes all other calls to the SBCs sbc2.contoso.biz and sbc5.contoso.biz.</span></span> <span data-ttu-id="697dd-364">Los ejemplos que se muestran asignan la directiva de nosotros solo al usuario "Sergio bajo" y sin restricciones al usuario "John Woods."</span><span class="sxs-lookup"><span data-stu-id="697dd-364">The examples that are shown assign the US Only policy to user "Spencer Low," and No Restrictions to the user "John Woods."</span></span>

<span data-ttu-id="697dd-365">Sergio baja – permiten llamadas sólo a los números de Estados Unidos y Canadá.</span><span class="sxs-lookup"><span data-stu-id="697dd-365">Spencer Low – Calls allowed only to US and Canadian numbers.</span></span> <span data-ttu-id="697dd-366">Cuando se llama a para el intervalo de números de Redmond, se debe usar el conjunto específico de SBC.</span><span class="sxs-lookup"><span data-stu-id="697dd-366">When calling to the Redmond number range, the specific set of SBC must be used.</span></span> <span data-ttu-id="697dd-367">Los números que no son-US no se enrutarán a menos que la licencia de planeación de la llamada se asigna al usuario.</span><span class="sxs-lookup"><span data-stu-id="697dd-367">Non-US numbers will not be routed unless the Calling Plan license is assigned to the user.</span></span>

<span data-ttu-id="697dd-368">John Woods – permitidas a cualquier número de llamadas.</span><span class="sxs-lookup"><span data-stu-id="697dd-368">John Woods – Calls allowed to any number.</span></span> <span data-ttu-id="697dd-369">Cuando se llama a para el intervalo de números de Redmond, se debe usar el conjunto específico de SBC.</span><span class="sxs-lookup"><span data-stu-id="697dd-369">When calling to the Redmond number range, the specific set of SBC must be used.</span></span> <span data-ttu-id="697dd-370">Los números que no son-US se enrutarán a través de sbc2.contoso.biz y sbc5.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="697dd-370">Non-US numbers will be routed via sbc2.contoso.biz and sbc5.contoso.biz.</span></span>

![Muestra la directiva de enrutamiento de voz asignada a usuario Spencer Low](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

<span data-ttu-id="697dd-372">Para todas las llamadas, si un usuario tiene dos licencias (sistema de teléfono de Microsoft y llamar a planeación de Microsoft), se usa ruta automático.</span><span class="sxs-lookup"><span data-stu-id="697dd-372">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), Automatic Route is used.</span></span> <span data-ttu-id="697dd-373">Si no hay nada coincide con los patrones de números en las rutas de voz en línea creadas por el administrador, se enruta a través de una llamada a planeación de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="697dd-373">If nothing matches the number patterns in the administrator-created online voice routes, route via Microsoft Calling Plan.</span></span>

<span data-ttu-id="697dd-374">Si el usuario tiene sólo del sistema de teléfono de Microsoft, se interrumpe la llamada porque no hay reglas de coincidencia están disponibles.</span><span class="sxs-lookup"><span data-stu-id="697dd-374">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

![Muestra la directiva de enrutamiento de voz asignada a usuario John Woods](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

<span data-ttu-id="697dd-376">En la siguiente tabla se resume denominación de uso de enrutamiento directiva "Sin restricciones" y rutas de voz.</span><span class="sxs-lookup"><span data-stu-id="697dd-376">The following table summarizes routing policy "No Restrictions" usage designations and voice routes.</span></span> 

|<span data-ttu-id="697dd-377">**Uso de RTC**</span><span class="sxs-lookup"><span data-stu-id="697dd-377">**PSTN usage**</span></span>|<span data-ttu-id="697dd-378">**Ruta de voz**</span><span class="sxs-lookup"><span data-stu-id="697dd-378">**Voice route**</span></span>|<span data-ttu-id="697dd-379">**Patrón de números**</span><span class="sxs-lookup"><span data-stu-id="697dd-379">**Number pattern**</span></span>|<span data-ttu-id="697dd-380">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="697dd-380">**Priority**</span></span>|<span data-ttu-id="697dd-381">**SBC**</span><span class="sxs-lookup"><span data-stu-id="697dd-381">**SBC**</span></span>|<span data-ttu-id="697dd-382">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="697dd-382">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="697dd-383">NOSOTROS solo</span><span class="sxs-lookup"><span data-stu-id="697dd-383">US Only</span></span>|<span data-ttu-id="697dd-384">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="697dd-384">"Redmond 1"</span></span>|<span data-ttu-id="697dd-385">^\\+ 1 (425\|206)(\d{7})$</span><span class="sxs-lookup"><span data-stu-id="697dd-385">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="697dd-386">1</span><span class="sxs-lookup"><span data-stu-id="697dd-386">1</span></span>|<span data-ttu-id="697dd-387">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="697dd-387">sbc1.contoso.biz</span></span><br/><span data-ttu-id="697dd-388">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="697dd-388">sbc2.contoso.biz</span></span>|<span data-ttu-id="697dd-389">Ruta activa para los números del destinatario de la llamada +1 425 XXX XX XX o +1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="697dd-389">Active route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="697dd-390">NOSOTROS solo</span><span class="sxs-lookup"><span data-stu-id="697dd-390">US Only</span></span>|<span data-ttu-id="697dd-391">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="697dd-391">"Redmond 2"</span></span>|<span data-ttu-id="697dd-392">^\\+ 1 (425\|206)(\d{7})$</span><span class="sxs-lookup"><span data-stu-id="697dd-392">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="697dd-393">2</span><span class="sxs-lookup"><span data-stu-id="697dd-393">2</span></span>|<span data-ttu-id="697dd-394">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="697dd-394">sbc3.contoso.biz</span></span><br/><span data-ttu-id="697dd-395">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="697dd-395">sbc4.contoso.biz</span></span>|<span data-ttu-id="697dd-396">Ruta de reserva para los números del destinatario de la llamada +1 425 XXX XX XX o +1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="697dd-396">Backup route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="697dd-397">NOSOTROS solo</span><span class="sxs-lookup"><span data-stu-id="697dd-397">US Only</span></span>|<span data-ttu-id="697dd-398">"Otros + 1"</span><span class="sxs-lookup"><span data-stu-id="697dd-398">"Other +1"</span></span>|<span data-ttu-id="697dd-399">^\\+ 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="697dd-399">^\\+1(\d{10})$</span></span>|<span data-ttu-id="697dd-400">3</span><span class="sxs-lookup"><span data-stu-id="697dd-400">3</span></span>|<span data-ttu-id="697dd-401">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="697dd-401">sbc5.contoso.biz</span></span><br/><span data-ttu-id="697dd-402">sbc6>.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="697dd-402">sbc6>.contoso.biz</span></span>|<span data-ttu-id="697dd-403">+ 1 XXX XXX XX XX (excepto +1 425 XXX XX XX o +1 206 XXX XX XX) los números de ruta para el destinatario de la llamada</span><span class="sxs-lookup"><span data-stu-id="697dd-403">Route for callee numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|<span data-ttu-id="697dd-404">International</span><span class="sxs-lookup"><span data-stu-id="697dd-404">International</span></span>|<span data-ttu-id="697dd-405">International</span><span class="sxs-lookup"><span data-stu-id="697dd-405">International</span></span>|<span data-ttu-id="697dd-406">\d+</span><span class="sxs-lookup"><span data-stu-id="697dd-406">\d+</span></span>|<span data-ttu-id="697dd-407">4</span><span class="sxs-lookup"><span data-stu-id="697dd-407">4</span></span>|<span data-ttu-id="697dd-408">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="697dd-408">sbc2.contoso.biz</span></span><br/><span data-ttu-id="697dd-409">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="697dd-409">sbc5.contoso.biz</span></span>|<span data-ttu-id="697dd-410">Ruta para cualquier patrón de número</span><span class="sxs-lookup"><span data-stu-id="697dd-410">Route for any number pattern</span></span> |


  > [!NOTE]
  > - <span data-ttu-id="697dd-411">El orden de los usos de RTC en las directivas de enrutamiento de voz es fundamental.</span><span class="sxs-lookup"><span data-stu-id="697dd-411">The order of PSTN Usages in Voice Routing Policies is critical.</span></span> <span data-ttu-id="697dd-412">Los usos se aplican en orden, y si se encuentra una coincidencia en el primer uso, a continuación, otros usos no se evaluarán nunca.</span><span class="sxs-lookup"><span data-stu-id="697dd-412">The usages are applied in order, and if a match is found in the first usage, then other usages are never evaluated.</span></span> <span data-ttu-id="697dd-413">El uso de RTC "Internacional" se debe colocar después el uso de RTC "Sólo en EE."</span><span class="sxs-lookup"><span data-stu-id="697dd-413">The PSTN Usage "International" must be placed after the PSTN Usage "US Only."</span></span> <span data-ttu-id="697dd-414">Para cambiar el orden de los usos de RTC, ejecute el `Set-CSOnlineVoiceRoutingPolicy` comando.</span><span class="sxs-lookup"><span data-stu-id="697dd-414">To change the order of the PSTN Usages, run the `Set-CSOnlineVoiceRoutingPolicy` command.</span></span> <br/><span data-ttu-id="697dd-415">Por ejemplo, para cambiar el orden de "Nosotros y Canadá" ejecutar "Internacional" y el segundo para el orden inverso:</span><span class="sxs-lookup"><span data-stu-id="697dd-415">For example, to change the order from "US and Canada" first and "International" second to the reverse order run:</span></span><br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - <span data-ttu-id="697dd-416">La prioridad de las rutas de voz de "caracteres International" y "Otros + 1" se asignan automáticamente.</span><span class="sxs-lookup"><span data-stu-id="697dd-416">The priority for "Other +1" and "International" Voice routes are assigned automatically.</span></span> <span data-ttu-id="697dd-417">Éstos no importan como que tienen una prioridad inferior que "Redmond 1" y "Redmond 2".</span><span class="sxs-lookup"><span data-stu-id="697dd-417">They don’t matter as long as they have lower priorities than "Redmond 1" and "Redmond 2."</span></span>

#### <a name="example-of-voice-routing-policy-for-user-john-woods"></a><span data-ttu-id="697dd-418">Ejemplo de directiva de enrutamiento de voz para el usuario John Woods</span><span class="sxs-lookup"><span data-stu-id="697dd-418">Example of Voice Routing Policy for user John Woods</span></span>

<span data-ttu-id="697dd-419">Los pasos para crear el uso de RTC "Internacional", "Internacional", de la ruta de voz "Sin restricciones," Directiva de enrutamiento de voz y, a continuación, se asigna al usuario "John Woods" son los siguientes.</span><span class="sxs-lookup"><span data-stu-id="697dd-419">The steps to create PSTN Usage "International", voice route "International," Voice Routing Policy "No Restrictions," and then assigning it to the user "John Woods" are as follows.</span></span>


1. <span data-ttu-id="697dd-420">En primer lugar, cree el uso de RTC "Internacional".</span><span class="sxs-lookup"><span data-stu-id="697dd-420">First, create the PSTN Usage "International."</span></span> <span data-ttu-id="697dd-421">En una sesión remota de PowerShell en Skype para profesionales en línea, escriba:</span><span class="sxs-lookup"><span data-stu-id="697dd-421">In a remote PowerShell session in Skype for Business Online, enter:</span></span>

   ```
   Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
   ```

2. <span data-ttu-id="697dd-422">A continuación, cree la nueva ruta de voz "Internacional".</span><span class="sxs-lookup"><span data-stu-id="697dd-422">Next, create the new voice route "International."</span></span>

   ```
   New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
   ```
   <span data-ttu-id="697dd-423">Que devuelve:</span><span class="sxs-lookup"><span data-stu-id="697dd-423">Which returns:</span></span>

   <pre>
   Identity                  : International 
   Priority                      : 5
   Description                   : 
   NumberPattern                 : .*
   OnlinePstnUsages          : {International} 
   OnlinePstnGatewayList           : {sbc2.contoso.biz, sbc5.contoso.biz}
   Name                            : International
   SupressCallerId           :
   AlternateCallerId         :
   </pre>
3. <span data-ttu-id="697dd-424">A continuación, no cree una directiva de enrutamiento de voz "restricciones".</span><span class="sxs-lookup"><span data-stu-id="697dd-424">Next, create a Voice Routing Policy "No Restrictions".</span></span> <span data-ttu-id="697dd-425">El uso de RTC "Redmond 1" y "Redmond" volver a usar en esta directiva de enrutamiento de voz para conservar un tratamiento especial para las llamadas al número "XX XX de XXX +1 425" y "XX XX de XXX +1 206" como local o llamadas locales.</span><span class="sxs-lookup"><span data-stu-id="697dd-425">The PSTN Usage "Redmond 1" and "Redmond" are reused in this voice routing policy to preserve special handling for calls to number "+1 425 XXX XX XX" and "+1 206 XXX XX XX" as local or on-premises calls.</span></span>

```
New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
```

    Take note of the order of PSTN Usages:

    a. If a call made to number "+1 425 XXX XX XX" with the usages configured as in the following example, the call follows the route set in "US and Canada" usage and the special routing logic is applied. That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes. 

    b.  If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic. Enter the command:

    ```New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"```

   <span data-ttu-id="697dd-426">Que devuelve</span><span class="sxs-lookup"><span data-stu-id="697dd-426">Which returns</span></span>

  <pre>
   Identity     : International 
   OnlinePstnUsages     : {US and Canada, International}     
   Description      :  
   RouteType        : BYOT
  </pre>

4. <span data-ttu-id="697dd-427">Asignar la directiva de enrutamiento de voz para el usuario "John Woods" mediante el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="697dd-427">Assign the voice routing policy to the user "John Woods" using the following command.</span></span>

   ```
   Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions”
   ```

   <span data-ttu-id="697dd-428">A continuación, compruebe la asignación mediante el comando:</span><span class="sxs-lookup"><span data-stu-id="697dd-428">Then verify the assignment using the command:</span></span> 

   ```
   Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
   ```
   <span data-ttu-id="697dd-429">Que devuelve:</span><span class="sxs-lookup"><span data-stu-id="697dd-429">Which returns:</span></span>

<pre>
    OnlineVoiceRoutingPolicy
    ------------------------
    No Restrictions
</pre>

<span data-ttu-id="697dd-430">El resultado es que la directiva de voz que se aplican a las llamadas de John Woods está restringida y seguir la lógica de enrutamiento de llamadas disponibles para llamadas de Estados Unidos, Canadá e internacional.</span><span class="sxs-lookup"><span data-stu-id="697dd-430">The result is that the voice policy applied to John Woods’ calls is unrestricted, and will follow the logic of call routing available for US, Canada, and International calling.</span></span>

## <a name="set-microsoft-teams-as-the-preferred-calling-client-for-users"></a><span data-ttu-id="697dd-431">Establecer Teams Microsoft como cliente llamado preferido para los usuarios</span><span class="sxs-lookup"><span data-stu-id="697dd-431">Set Microsoft Teams as the preferred calling client for users</span></span>

<span data-ttu-id="697dd-432">Sólo enrutamiento directa enruta las llamadas a y desde los usuarios si utilizan al cliente de los equipos.</span><span class="sxs-lookup"><span data-stu-id="697dd-432">Direct Routing only routes calls to and from users if they use the Teams client.</span></span> <span data-ttu-id="697dd-433">Si su organización sólo usa los equipos, "Equipos sólo" modo en la directiva de actualización se recomienda establecer.</span><span class="sxs-lookup"><span data-stu-id="697dd-433">If your organization only uses Teams, setting "Teams Only" mode in upgrade policy is recommended.</span></span> <span data-ttu-id="697dd-434">Si su organización usa Skype para Business Server o Skype para profesionales en línea, consulte el siguiente artículo para obtener más información y seleccione la opción adecuada: [comprender la coexistencia y actualización de viaje para Skype para profesionales y los equipos](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span><span class="sxs-lookup"><span data-stu-id="697dd-434">If you organization uses Skype for Business Server or Skype for Business Online, see the following article for more information and select the appropriate option: [Understand coexistence and upgrade journey for Skype for Business and Teams](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span></span> 


## <a name="see-also"></a><span data-ttu-id="697dd-435">Consulte también</span><span class="sxs-lookup"><span data-stu-id="697dd-435">See also</span></span>

[<span data-ttu-id="697dd-436">Planear el enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="697dd-436">Plan Direct Routing</span></span>](direct-routing-plan.md)
