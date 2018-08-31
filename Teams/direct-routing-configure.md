---
title: Configurar el enrutamiento directo
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Obtenga información sobre cómo configurar el enrutamiento directo de Microsoft teléfono del sistema.
ms.openlocfilehash: c84e8b28d6a13e3dca64a08a63aa516556357dde
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2018
ms.locfileid: "23779774"
---
# <a name="configure-direct-routing"></a><span data-ttu-id="172c3-103">Configurar el enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="172c3-103">Configure Direct Routing</span></span>

<span data-ttu-id="172c3-104">Si no lo ha hecho ya, lea [Planear el enrutamiento directo](direct-routing-plan.md) para los requisitos previos y para revisar otros pasos debe realizar antes de configurar la red del sistema de teléfono de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="172c3-104">If you have not already done so, read [Plan Direct Routing](direct-routing-plan.md) for prerequisites and to review  other steps you’ll need to take before you configure your Microsoft Phone System network.</span></span> 

<span data-ttu-id="172c3-105">En este artículo se describe cómo configurar el enrutamiento directo de Microsoft teléfono del sistema.</span><span class="sxs-lookup"><span data-stu-id="172c3-105">This article describes how to configure Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="172c3-106">Detalla cómo emparejar un controlador de borde de sesión (SBC) admitidos para el enrutamiento directo y cómo configurar los usuarios de Microsoft Teams para usar el enrutamiento directo para conectarse a la red telefónica pública conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="172c3-106">It details how to pair a supported Session Border Controller (SBC) to Direct Routing and how to configure Microsoft Teams users to use Direct Routing to connect to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="172c3-107">Para completar los pasos que se explican en este artículo, los administradores necesitan un poco familiarizado con los cmdlets de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="172c3-107">To complete the steps explained in this article, administrators need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="172c3-108">Para obtener más información acerca del uso de PowerShell, vea [Configurar el equipo de Windows PowerShell](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="172c3-108">For more information about using PowerShell, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 

<span data-ttu-id="172c3-109">Se recomienda que confirme que ya se ha configurado la SBC recomendada por su proveedor SBC:</span><span class="sxs-lookup"><span data-stu-id="172c3-109">We recommend that you confirm that your SBC has already been configured as recommended by your SBC vendor's:</span></span> 

- <span data-ttu-id="172c3-110">Documentación de implementación de AudioCodes</span><span class="sxs-lookup"><span data-stu-id="172c3-110">AudioCodes deployment documentation</span></span> 
- <span data-ttu-id="172c3-111">Documentación de implementación de la cinta de opciones</span><span class="sxs-lookup"><span data-stu-id="172c3-111">Ribbon deployment documentation</span></span>

<span data-ttu-id="172c3-112">Puede configurar el sistema de teléfono de Microsoft y permiten a los usuarios usar el enrutamiento directo, a continuación, configurar Microsoft Teams como el cliente preferido de la llamada al completar los procedimientos siguientes:</span><span class="sxs-lookup"><span data-stu-id="172c3-112">You can configure your Microsoft Phone System and enable  users to use Direct Routing, then set up Microsoft Teams as the preferred calling client by completing the following procedures:</span></span> 

- [<span data-ttu-id="172c3-113">Empareje la SBC con un sistema de teléfono de Microsoft y validar el emparejamiento</span><span class="sxs-lookup"><span data-stu-id="172c3-113">Pair the SBC with a Microsoft Phone System and validate the pairing</span></span>](#pair-the-sbc-to-direct-routing-service-of-phone-system)
- [<span data-ttu-id="172c3-114">Habilitar a usuarios para el servicio de enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="172c3-114">Enable users for Direct Routing Service</span></span>](#enable-users-for-direct-routing-service)
- [<span data-ttu-id="172c3-115">Asegúrese de que Microsoft Teams es el cliente llamado preferido para los usuarios</span><span class="sxs-lookup"><span data-stu-id="172c3-115">Ensure that Microsoft Teams is the preferred calling client for the users</span></span>](#set-microsoft-teams-as-the-preferred-calling-client-for-users) 

## <a name="pair-the-sbc-to-direct-routing-service-of-phone-system"></a><span data-ttu-id="172c3-116">Empareje la SBC para dirigir el servicio de enrutamiento del sistema de teléfono</span><span class="sxs-lookup"><span data-stu-id="172c3-116">Pair the SBC to Direct Routing Service of Phone System</span></span> 

<span data-ttu-id="172c3-117">Los siguientes son los tres pasos de alto nivel para permitirle conectarse o emparejar la SBC a la interfaz de enrutamiento directo:</span><span class="sxs-lookup"><span data-stu-id="172c3-117">The following are the three high-level steps to let you connect, or pair, the SBC to the Direct Routing interface:</span></span> 

- <span data-ttu-id="172c3-118">Conectarse al centro de administración de **Skype para profesionales en línea** con PowerShell</span><span class="sxs-lookup"><span data-stu-id="172c3-118">Connect to **Skype for Business Online** admin center using PowerShell</span></span> 
- <span data-ttu-id="172c3-119">Par el SBC</span><span class="sxs-lookup"><span data-stu-id="172c3-119">Pair the SBC</span></span> 
- <span data-ttu-id="172c3-120">Validar el emparejamiento</span><span class="sxs-lookup"><span data-stu-id="172c3-120">Validate the pairing</span></span> 

### <a name="connect-to--skype-for-business-online-by-using-powershell"></a><span data-ttu-id="172c3-121">Conectarse a Skype para profesionales en línea mediante el uso de PowerShell</span><span class="sxs-lookup"><span data-stu-id="172c3-121">Connect to  Skype for Business Online by using PowerShell</span></span> 

<span data-ttu-id="172c3-122">Puede usar una sesión de PowerShell conectado a los inquilinos para emparejar la SBC a la interfaz de enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="172c3-122">You can use a PowerShell session connected to the tenant to pair the SBC to the Direct Routing interface.</span></span> <span data-ttu-id="172c3-123">Para abrir una sesión de PowerShell, siga los pasos descritos en [Configurar el equipo de Windows PowerShell](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="172c3-123">To open a PowerShell session, please follow the steps outlined in [Set up your computer for Windows PowerShell](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 
 
<span data-ttu-id="172c3-124">Después de establecer una sesión remota de PowerShell, compruebe que puede ver los comandos para administrar la SBC.</span><span class="sxs-lookup"><span data-stu-id="172c3-124">After you establish a remote PowerShell session, please validate that you can see the commands to manage the SBC.</span></span> <span data-ttu-id="172c3-125">Para validar los comandos, escriba o copiar y pegar en las siguientes opciones en la sesión de PowerShell y presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="172c3-125">To validate the commands, type or copy/paste in the following in the PowerShell session and press Enter:</span></span> 

```
gcm *onlinePSTNGateway*
```

<span data-ttu-id="172c3-126">El comando devolverá las cuatro funciones que se muestra aquí que le permiten administrar el SBCs.</span><span class="sxs-lookup"><span data-stu-id="172c3-126">Your command will return the four functions shown here that will let you manage the SBCs.</span></span> 

<pre>
CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
</pre>   


### <a name="pair-the-sbc-to-the-tenant"></a><span data-ttu-id="172c3-127">Par la SBC para el inquilino</span><span class="sxs-lookup"><span data-stu-id="172c3-127">Pair the SBC to the tenant</span></span> 

<span data-ttu-id="172c3-128">Para emparejar la SBC para el inquilino, en la sesión de PowerShell, escriba lo siguiente y presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="172c3-128">To pair the SBC to the tenant, in the PowerShell session type the following and press Enter:</span></span> 

```
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignallingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true 
```
  > [!NOTE]
  > 1. <span data-ttu-id="172c3-129">Se recomienda establecer un límite para el SBC, uso de la información que se encuentra en la documentación de SBC.</span><span class="sxs-lookup"><span data-stu-id="172c3-129">We highly recommend setting a limit for the SBC, using information that can be found in the SBC documentation.</span></span> <span data-ttu-id="172c3-130">El límite activará una notificación si SBC está en el nivel de capacidad.</span><span class="sxs-lookup"><span data-stu-id="172c3-130">The limit will trigger a notification if SBC is at the capacity level.</span></span>
  > 2. <span data-ttu-id="172c3-131">Sólo puede emparejar la SBC con FQDN, donde la parte del dominio del nombre coincide con uno de los dominios registrados en el inquilino, excepto \*. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="172c3-131">You can only pair the SBC with FQDN, where the domain portion of the name matches one of the domains registered in your tenant, except \*.onmicrosoft.com.</span></span> <span data-ttu-id="172c3-132">Uso de \*. omicrosoft.com los nombres de dominio no es compatible con los nombres de SBC FQDN.</span><span class="sxs-lookup"><span data-stu-id="172c3-132">Using \*.omicrosoft.com domain names is not supported for the SBC FQDN names.</span></span> <span data-ttu-id="172c3-133">Por ejemplo, si tiene dos nombres de dominio:</span><span class="sxs-lookup"><span data-stu-id="172c3-133">For example, if you have two domain names:</span></span><br/><br/>
  > <span data-ttu-id="172c3-134">.xyz **ABC**</span><span class="sxs-lookup"><span data-stu-id="172c3-134">**abc**.xyz</span></span><br/><span data-ttu-id="172c3-135">**ABC**. onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="172c3-135">**abc**.onmicrosoft.com</span></span><br/><br/>
  > <span data-ttu-id="172c3-136">Para el nombre SBC, puede usar el nombre sbc.abc.xyz.</span><span class="sxs-lookup"><span data-stu-id="172c3-136">For the SBC name, you can use the name sbc.abc.xyz.</span></span> <span data-ttu-id="172c3-137">Si se intenta emparejar la SBC con un nombre sbc.xyz.abc, el sistema no le, como el dominio no pertenece a este inquilino.</span><span class="sxs-lookup"><span data-stu-id="172c3-137">If you try to pair the SBC with a name sbc.xyz.abc, the system will not let you, as the domain is not owned by this tenant.</span></span>

```
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignallingPort 5067 -MaxConcurrentSessions 100 
```
<span data-ttu-id="172c3-138">Devuelve:</span><span class="sxs-lookup"><span data-stu-id="172c3-138">Returns:</span></span>
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
<span data-ttu-id="172c3-139">Existen opciones adicionales que se pueden establecer durante el emparejamiento.</span><span class="sxs-lookup"><span data-stu-id="172c3-139">There are additional options that can be set during the pairing.</span></span> <span data-ttu-id="172c3-140">En el ejemplo anterior, sin embargo, solo la mínima necesaria se muestran los parámetros.</span><span class="sxs-lookup"><span data-stu-id="172c3-140">In the previous example, however, only the minimum required parameters are shown.</span></span> 
 
<span data-ttu-id="172c3-141">En la siguiente tabla se enumera los parámetros adicionales que puede usar en la configuración de parámetros para *New-CsOnlinePstnGateway*.</span><span class="sxs-lookup"><span data-stu-id="172c3-141">The following table lists the additional parameters that you can use in setting parameters for *New-CsOnlinePstnGateway*.</span></span> 

|<span data-ttu-id="172c3-142">¿Obligatorio?</span><span class="sxs-lookup"><span data-stu-id="172c3-142">Required?</span></span>|<span data-ttu-id="172c3-143">Nombre</span><span class="sxs-lookup"><span data-stu-id="172c3-143">Name</span></span>|<span data-ttu-id="172c3-144">Descripción</span><span class="sxs-lookup"><span data-stu-id="172c3-144">Description</span></span>|<span data-ttu-id="172c3-145">Predeterminado</span><span class="sxs-lookup"><span data-stu-id="172c3-145">Default</span></span>|<span data-ttu-id="172c3-146">Valores posibles</span><span class="sxs-lookup"><span data-stu-id="172c3-146">Possible values</span></span>|<span data-ttu-id="172c3-147">Tipo y restricciones</span><span class="sxs-lookup"><span data-stu-id="172c3-147">Type and restrictions</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="172c3-148">Sí</span><span class="sxs-lookup"><span data-stu-id="172c3-148">Yes</span></span>|<span data-ttu-id="172c3-149">FQDN</span><span class="sxs-lookup"><span data-stu-id="172c3-149">FQDN</span></span>|<span data-ttu-id="172c3-150">El nombre FQDN de la SBC</span><span class="sxs-lookup"><span data-stu-id="172c3-150">The FQDN name of the SBC</span></span> |<span data-ttu-id="172c3-151">Ninguna</span><span class="sxs-lookup"><span data-stu-id="172c3-151">None</span></span>|<span data-ttu-id="172c3-152">Nombre de NoneFQDN, límite 63 caracteres</span><span class="sxs-lookup"><span data-stu-id="172c3-152">NoneFQDN name, limit 63 characters</span></span>|<span data-ttu-id="172c3-153">Cadena, lista de caracteres permitidos y no permitidos en [las convenciones de nomenclatura en Active Directory para equipos, dominios, sitios y unidades organizativas](https://support.microsoft.com/en-us/help/909264)</span><span class="sxs-lookup"><span data-stu-id="172c3-153">String,  list of allowed and disallowed characters on [Naming conventions in Active Directory for computers, domains, sites, and OUs](https://support.microsoft.com/en-us/help/909264)</span></span>|
|<span data-ttu-id="172c3-154">No</span><span class="sxs-lookup"><span data-stu-id="172c3-154">No</span></span>|<span data-ttu-id="172c3-155">MediaBypass</span><span class="sxs-lookup"><span data-stu-id="172c3-155">MediaBypass</span></span> |<span data-ttu-id="172c3-156">El parámetro reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="172c3-156">The parameter reserved for future use.</span></span> <span data-ttu-id="172c3-157">Parámetro indicado de la SBC admite el desvío de medios y el administrador desea usarlo.</span><span class="sxs-lookup"><span data-stu-id="172c3-157">Parameter indicated of the SBC supports Media Bypass and the administrator wants to use it.</span></span>|<span data-ttu-id="172c3-158">Ninguna</span><span class="sxs-lookup"><span data-stu-id="172c3-158">None</span></span>|<span data-ttu-id="172c3-159">Verdadero</span><span class="sxs-lookup"><span data-stu-id="172c3-159">True</span></span><br/><span data-ttu-id="172c3-160">Falso</span><span class="sxs-lookup"><span data-stu-id="172c3-160">False</span></span>|<span data-ttu-id="172c3-161">Booleano</span><span class="sxs-lookup"><span data-stu-id="172c3-161">Boolean</span></span>|
|<span data-ttu-id="172c3-162">Sí</span><span class="sxs-lookup"><span data-stu-id="172c3-162">Yes</span></span>|<span data-ttu-id="172c3-163">SipSignallingPort</span><span class="sxs-lookup"><span data-stu-id="172c3-163">SipSignallingPort</span></span> |<span data-ttu-id="172c3-164">Puerto de escucha usado para la comunicación con los servicios de enrutamiento directa mediante el protocolo de seguridad de capa de transporte (TLS).</span><span class="sxs-lookup"><span data-stu-id="172c3-164">Listening port used for communicating with Direct Routing services by using the Transport Layer Security (TLS) protocol.</span></span>|<span data-ttu-id="172c3-165">Ninguna</span><span class="sxs-lookup"><span data-stu-id="172c3-165">None</span></span>|<span data-ttu-id="172c3-166">Cualquier puerto</span><span class="sxs-lookup"><span data-stu-id="172c3-166">Any port</span></span>|<span data-ttu-id="172c3-167">0 a 65535</span><span class="sxs-lookup"><span data-stu-id="172c3-167">0 to 65535</span></span> |
|<span data-ttu-id="172c3-168">No</span><span class="sxs-lookup"><span data-stu-id="172c3-168">No</span></span>|<span data-ttu-id="172c3-169">FailoverTimeSeconds</span><span class="sxs-lookup"><span data-stu-id="172c3-169">FailoverTimeSeconds</span></span> |<span data-ttu-id="172c3-170">Cuando se establece en 10 (valor predeterminado), las llamadas salientes que no hay respondidas por la puerta de enlace dentro de 10 segundos se enrutan al siguiente tronco disponible; Si no hay ningún troncos adicionales, automáticamente se interrumpe la llamada.</span><span class="sxs-lookup"><span data-stu-id="172c3-170">When set to 10 (default value), outbound calls that are not answered by the gateway within 10 seconds are routed to the next available trunk; if there are no additional trunks, then the call is automatically dropped.</span></span> <span data-ttu-id="172c3-171">En una organización con redes lentas y respuestas a las puertas de enlace, puede tener como resultado interrupciones innecesarias de las llamadas.</span><span class="sxs-lookup"><span data-stu-id="172c3-171">In an organization with slow networks and gateway responses, that could potentially result in calls being dropped unnecessarily.</span></span> <span data-ttu-id="172c3-172">El valor predeterminado es 10.</span><span class="sxs-lookup"><span data-stu-id="172c3-172">The default value is 10.</span></span>|<span data-ttu-id="172c3-173">10</span><span class="sxs-lookup"><span data-stu-id="172c3-173">10</span></span>|<span data-ttu-id="172c3-174">Número</span><span class="sxs-lookup"><span data-stu-id="172c3-174">Number</span></span>|<span data-ttu-id="172c3-175">Int</span><span class="sxs-lookup"><span data-stu-id="172c3-175">Int</span></span>|
|<span data-ttu-id="172c3-176">No</span><span class="sxs-lookup"><span data-stu-id="172c3-176">No</span></span>|<span data-ttu-id="172c3-177">ForwardCallHistory</span><span class="sxs-lookup"><span data-stu-id="172c3-177">ForwardCallHistory</span></span> |<span data-ttu-id="172c3-178">Indica si la información del historial de llamadas se reenviará a través del tronco.</span><span class="sxs-lookup"><span data-stu-id="172c3-178">Indicates whether call history information will be forwarded through the trunk.</span></span> <span data-ttu-id="172c3-179">Si se habilita, el Proxy de RTC de Office 365 envía dos encabezados: información de historial y remitido por.</span><span class="sxs-lookup"><span data-stu-id="172c3-179">If enabled, the Office 365 PSTN Proxy sends two headers: History-info and Referred-By.</span></span> <span data-ttu-id="172c3-180">El valor predeterminado es **False** ($False).</span><span class="sxs-lookup"><span data-stu-id="172c3-180">The default value is **False** ($False).</span></span> |<span data-ttu-id="172c3-181">Falso</span><span class="sxs-lookup"><span data-stu-id="172c3-181">False</span></span>|<span data-ttu-id="172c3-182">Verdadero</span><span class="sxs-lookup"><span data-stu-id="172c3-182">True</span></span><br/><span data-ttu-id="172c3-183">Falso</span><span class="sxs-lookup"><span data-stu-id="172c3-183">False</span></span>|<span data-ttu-id="172c3-184">Booleano</span><span class="sxs-lookup"><span data-stu-id="172c3-184">Boolean</span></span>|
|<span data-ttu-id="172c3-185">No</span><span class="sxs-lookup"><span data-stu-id="172c3-185">No</span></span>|<span data-ttu-id="172c3-186">ForwardPAI</span><span class="sxs-lookup"><span data-stu-id="172c3-186">ForwardPAI</span></span>|<span data-ttu-id="172c3-187">Indica si el encabezado P-Asserted-Identity (PAI) se reenviará junto con la llamada.</span><span class="sxs-lookup"><span data-stu-id="172c3-187">Indicates whether the P-Asserted-Identity (PAI) header will be forwarded along with the call.</span></span> <span data-ttu-id="172c3-188">El encabezado PAI proporciona una forma de verificar la identidad del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="172c3-188">The PAI header provides a way to verify the identity of the caller.</span></span> <span data-ttu-id="172c3-189">El valor predeterminado es **False** ($False).</span><span class="sxs-lookup"><span data-stu-id="172c3-189">The default value is **False** ($False).</span></span>|<span data-ttu-id="172c3-190">Falso</span><span class="sxs-lookup"><span data-stu-id="172c3-190">False</span></span>|<span data-ttu-id="172c3-191">Verdadero</span><span class="sxs-lookup"><span data-stu-id="172c3-191">True</span></span><br/><span data-ttu-id="172c3-192">Falso</span><span class="sxs-lookup"><span data-stu-id="172c3-192">False</span></span>|<span data-ttu-id="172c3-193">Booleano</span><span class="sxs-lookup"><span data-stu-id="172c3-193">Boolean</span></span>|
|<span data-ttu-id="172c3-194">No</span><span class="sxs-lookup"><span data-stu-id="172c3-194">No</span></span>|<span data-ttu-id="172c3-195">SendSIPOptions</span><span class="sxs-lookup"><span data-stu-id="172c3-195">SendSIPOptions</span></span> |<span data-ttu-id="172c3-196">Define si un SBC se o no enviará las opciones de SIP.</span><span class="sxs-lookup"><span data-stu-id="172c3-196">Defines if an SBC will or will not send the SIP options.</span></span> <span data-ttu-id="172c3-197">Si deshabilita esta opción, la SBC se excluirán del sistema de supervisión y alertas.</span><span class="sxs-lookup"><span data-stu-id="172c3-197">If disabled, the SBC will be excluded from Monitoring and Alerting system.</span></span> <span data-ttu-id="172c3-198">Se recomienda encarecidamente que habilite las opciones de SIP.</span><span class="sxs-lookup"><span data-stu-id="172c3-198">We highly recommend that you enable SIP options.</span></span> <span data-ttu-id="172c3-199">Valor predeterminado es **True**.</span><span class="sxs-lookup"><span data-stu-id="172c3-199">Default value is **True**.</span></span> |<span data-ttu-id="172c3-200">True</span><span class="sxs-lookup"><span data-stu-id="172c3-200">True</span></span>|<span data-ttu-id="172c3-201">True</span><span class="sxs-lookup"><span data-stu-id="172c3-201">True</span></span><br/><span data-ttu-id="172c3-202">Falso</span><span class="sxs-lookup"><span data-stu-id="172c3-202">False</span></span>|<span data-ttu-id="172c3-203">Booleano</span><span class="sxs-lookup"><span data-stu-id="172c3-203">Boolean</span></span>|
|<span data-ttu-id="172c3-204">No</span><span class="sxs-lookup"><span data-stu-id="172c3-204">No</span></span>|<span data-ttu-id="172c3-205">MaxConcurrentSessions</span><span class="sxs-lookup"><span data-stu-id="172c3-205">MaxConcurrentSessions</span></span> |<span data-ttu-id="172c3-206">Usada por el sistema de alertas.</span><span class="sxs-lookup"><span data-stu-id="172c3-206">Used by alerting system.</span></span> <span data-ttu-id="172c3-207">Cuando se establece ningún valor, el sistema de alertas generará una alerta para el Administrador de inquilinos cuando el número de sesión simultáneo es 90% o mayor que este valor.</span><span class="sxs-lookup"><span data-stu-id="172c3-207">When any value is set, the alerting system will generate an alert to the tenant administrator when the number of concurrent session is 90% or higher than this value.</span></span> <span data-ttu-id="172c3-208">Si no se establece el parámetro, no se generan las alertas.</span><span class="sxs-lookup"><span data-stu-id="172c3-208">If parameter is not set, the alerts are not generated.</span></span> <span data-ttu-id="172c3-209">Sin embargo, el sistema de supervisión informará número de sesiones simultáneas cada 24 horas.</span><span class="sxs-lookup"><span data-stu-id="172c3-209">However, the monitoring system will report number of concurrent session every 24 hours.</span></span> |<span data-ttu-id="172c3-210">Null</span><span class="sxs-lookup"><span data-stu-id="172c3-210">Null</span></span>|<span data-ttu-id="172c3-211">Null</span><span class="sxs-lookup"><span data-stu-id="172c3-211">Null</span></span><br/><span data-ttu-id="172c3-212">1 y 100.000.</span><span class="sxs-lookup"><span data-stu-id="172c3-212">1 to 100,000</span></span> ||
|<span data-ttu-id="172c3-213">No</span><span class="sxs-lookup"><span data-stu-id="172c3-213">No</span></span>|<span data-ttu-id="172c3-214">Habilitado \*</span><span class="sxs-lookup"><span data-stu-id="172c3-214">Enabled\*</span></span>|<span data-ttu-id="172c3-215">Se usa para habilitar este SBC para las llamadas salientes.</span><span class="sxs-lookup"><span data-stu-id="172c3-215">Used to enable this SBC for outbound calls.</span></span> <span data-ttu-id="172c3-216">Puede usarse para quitar temporalmente el SBC, mientras se está actualizando o durante el mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="172c3-216">Can be used to temporarily remove the SBC, while it is being updated or during maintenance.</span></span> |<span data-ttu-id="172c3-217">Falso</span><span class="sxs-lookup"><span data-stu-id="172c3-217">False</span></span>|<span data-ttu-id="172c3-218">Verdadero</span><span class="sxs-lookup"><span data-stu-id="172c3-218">True</span></span><br/><span data-ttu-id="172c3-219">Falso</span><span class="sxs-lookup"><span data-stu-id="172c3-219">False</span></span>|<span data-ttu-id="172c3-220">Booleano</span><span class="sxs-lookup"><span data-stu-id="172c3-220">Boolean</span></span>|
 
### <a name="verify-the-sbc-pairing"></a><span data-ttu-id="172c3-221">Compruebe el emparejamiento de SBC</span><span class="sxs-lookup"><span data-stu-id="172c3-221">Verify the SBC pairing</span></span> 

<span data-ttu-id="172c3-222">Compruebe la conexión:</span><span class="sxs-lookup"><span data-stu-id="172c3-222">Verify the connection:</span></span> 
- <span data-ttu-id="172c3-223">Compruebe si la SBC está en la lista de SBCs emparejados.</span><span class="sxs-lookup"><span data-stu-id="172c3-223">Check if the SBC is on the list of paired SBCs.</span></span> 
- <span data-ttu-id="172c3-224">Validar las opciones de SIP.</span><span class="sxs-lookup"><span data-stu-id="172c3-224">Validate SIP Options.</span></span> 
 
#### <a name="validate-if-sbc-is-on-the-list-of-paired-sbcs"></a><span data-ttu-id="172c3-225">Validar si SBC está en la lista de SBCs emparejados</span><span class="sxs-lookup"><span data-stu-id="172c3-225">Validate if SBC is on the list of paired SBCs</span></span> 

<span data-ttu-id="172c3-226">Después de par el SBC, validar que el SBC está presente en la lista de SBCs emparejados ejecutando el siguiente comando en una sesión remota de PowerShell:`Get-CSOnlinePSTNGateway`</span><span class="sxs-lookup"><span data-stu-id="172c3-226">After you pair the SBC, validate that the SBC is present in the list of paired SBCs by running the following command  in a remote PowerShell session: `Get-CSOnlinePSTNGateway`</span></span>

<span data-ttu-id="172c3-227">La puerta de enlace emparejado debe aparecer en la lista tal como se muestra en el ejemplo siguiente y compruebe que el parámetro *Enabled* muestra el valor **True**.</span><span class="sxs-lookup"><span data-stu-id="172c3-227">The paired gateway should appear in the list as shown in the example below, and verify that the parameter *Enabled* displays the value **True**.</span></span> <span data-ttu-id="172c3-228">Escriba:</span><span class="sxs-lookup"><span data-stu-id="172c3-228">Enter:</span></span>

```
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```
<span data-ttu-id="172c3-229">Que devuelve:</span><span class="sxs-lookup"><span data-stu-id="172c3-229">Which returns:</span></span>
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

#### <a name="validate-sip-options-flow"></a><span data-ttu-id="172c3-230">Validar flujo de opciones de SIP</span><span class="sxs-lookup"><span data-stu-id="172c3-230">Validate SIP Options flow</span></span> 

<span data-ttu-id="172c3-231">Para validar el uso de las opciones de SIP saliente emparejamiento, usar la interfaz de administración de SBC y ver que la SBC obtener 200 respuestas Aceptar a las opciones de salida.</span><span class="sxs-lookup"><span data-stu-id="172c3-231">To validate the pairing using outgoing SIP Options, use the SBC management interface and see that the SBC get 200 OK responses to the outgoing OPTIONS.</span></span>
  
<span data-ttu-id="172c3-232">Cuando el enrutamiento directo ve opciones entrantes, se iniciará salientes opciones de envío para el FQDN de SBC configurado en el campo de encabezado de contacto en el mensaje entrante de opciones.</span><span class="sxs-lookup"><span data-stu-id="172c3-232">When Direct Routing sees incoming OPTIONS, it will start sending outgoing options to the SBC FQDN configured in the Contact header field in the incoming OPTIONS message.</span></span> 

<span data-ttu-id="172c3-233">Para validar el uso de las opciones de SIP entrantes de emparejamiento, usar la interfaz de administración de SBC y ver que la SBC Obtiene la respuesta en los mensajes de las opciones que provienen de enrutamiento directo y que el código de respuesta es 200 Aceptar.</span><span class="sxs-lookup"><span data-stu-id="172c3-233">To validate the pairing using incoming SIP Options, use the SBC management interface and see that the SBC gets reply on the OPTIONS messages coming in from Direct Routing and that the response code is 200 OK.</span></span>  

## <a name="enable-users-for-direct-routing-service"></a><span data-ttu-id="172c3-234">Habilitar a usuarios para el servicio de enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="172c3-234">Enable users for Direct Routing Service</span></span> 

<span data-ttu-id="172c3-235">Cuando esté listo para habilitar a los usuarios para el servicio de enrutamiento directa, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="172c3-235">When you are ready to enable users for the Direct Routing Service, follow these steps:</span></span> 

1. <span data-ttu-id="172c3-236">Crear un usuario en Office 365 y asigna una licencia de sistema de teléfono.</span><span class="sxs-lookup"><span data-stu-id="172c3-236">Create a user in Office 365 and assign a phone system license.</span></span> 
2. <span data-ttu-id="172c3-237">Asegúrese de que el usuario está hospedado en Skype para profesionales en línea.</span><span class="sxs-lookup"><span data-stu-id="172c3-237">Ensure that the user is homed in Skype for Business Online.</span></span> 
3. <span data-ttu-id="172c3-238">Configurar el número de teléfono y habilitar correo de voz y enterprise voice.</span><span class="sxs-lookup"><span data-stu-id="172c3-238">Configure the phone number and enable enterprise voice and voicemail.</span></span> 
4. <span data-ttu-id="172c3-239">Configurar enrutamiento de voz.</span><span class="sxs-lookup"><span data-stu-id="172c3-239">Configure voice routing.</span></span> <span data-ttu-id="172c3-240">La ruta se validará automáticamente.</span><span class="sxs-lookup"><span data-stu-id="172c3-240">The route is automatically validated.</span></span>  

### <a name="create-a-user-in-office-365-and-assign-the-license"></a><span data-ttu-id="172c3-241">Crear un usuario en Office 365 y asignar la licencia</span><span class="sxs-lookup"><span data-stu-id="172c3-241">Create a user in Office 365 and assign the license</span></span> 

<span data-ttu-id="172c3-242">Hay dos opciones para crear un nuevo usuario en Office 365.</span><span class="sxs-lookup"><span data-stu-id="172c3-242">There are two options for creating a new user in Office 365.</span></span> <span data-ttu-id="172c3-243">Sin embargo, se recomienda que la organización, seleccione y utilice una opción para evitar problemas de enrutamiento:</span><span class="sxs-lookup"><span data-stu-id="172c3-243">However, we recommend that your organization select and use one option to avoid routing issues:</span></span> 

- <span data-ttu-id="172c3-244">Crear el usuario en Active Directory local y sincronizar el usuario a la nube.</span><span class="sxs-lookup"><span data-stu-id="172c3-244">Create the user in on-premise Active Directory and sync the user to the cloud.</span></span> <span data-ttu-id="172c3-245">Vea [directorios de integrar su local con Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect).</span><span class="sxs-lookup"><span data-stu-id="172c3-245">See [Integrate your on-premises directories with Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect).</span></span>  
- <span data-ttu-id="172c3-246">Crear el usuario directamente en el Portal de administrador de Office 365.</span><span class="sxs-lookup"><span data-stu-id="172c3-246">Create the user directly in the Office 365 Administrator Portal.</span></span> <span data-ttu-id="172c3-247">Vea [Agregar usuarios individualmente o de forma masiva a Office 365 - ayuda de administración](https://support.office.com/en-us/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span><span class="sxs-lookup"><span data-stu-id="172c3-247">See [Add users individually or in bulk to Office 365 - Admin Help](https://support.office.com/en-us/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span> 

  <span data-ttu-id="172c3-248">Si se elabora el sistema que coexiste con Skype para 2015 empresarial o Lync 2010 o 2013 local, la única opción compatible es crear el usuario en Active Directory local y sincronizar el usuario a la nube (opción 1).</span><span class="sxs-lookup"><span data-stu-id="172c3-248">If you build the system that co-exists with Skype for Business 2015 or Lync 2010/2013 on-premises, the only supported option is to create the user in on-premises Active Directory and sync the user to the cloud (Option 1).</span></span> 

<span data-ttu-id="172c3-249">Licencias necesarias:</span><span class="sxs-lookup"><span data-stu-id="172c3-249">Required licenses:</span></span> 

- <span data-ttu-id="172c3-250">Office 365 E3 de empresa (incluidos SfB Plan2, Exchange Plan2 y equipos) + del sistema de teléfono</span><span class="sxs-lookup"><span data-stu-id="172c3-250">Office 365 Enterprise E3 (including SfB Plan2, Exchange Plan2, and Teams) + Phone System</span></span>  
- <span data-ttu-id="172c3-251">Office 365 Enterprise E5 (incluidos SfB Plan2, Plan2 de Exchange, los equipos y del sistema de teléfono)</span><span class="sxs-lookup"><span data-stu-id="172c3-251">Office 365 Enterprise E5  (including SfB Plan2, Exchange Plan2, Teams, and Phone System)</span></span> 

<span data-ttu-id="172c3-252">Licencias opcionales:</span><span class="sxs-lookup"><span data-stu-id="172c3-252">Optional licenses:</span></span> 

- <span data-ttu-id="172c3-253">Plan de llamada</span><span class="sxs-lookup"><span data-stu-id="172c3-253">Calling Plan</span></span> 
- <span data-ttu-id="172c3-254">Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="172c3-254">Audio Conferencing</span></span> 

### <a name="ensure-that-the-user-is-homed-in-skype-for-business-online"></a><span data-ttu-id="172c3-255">Asegúrese de que el usuario está hospedado en Skype para profesionales en línea</span><span class="sxs-lookup"><span data-stu-id="172c3-255">Ensure that the user is homed in Skype for Business Online</span></span> 

<span data-ttu-id="172c3-256">Enrutamiento directo requiere que el usuario a estar alojado en Skype para profesionales en línea.</span><span class="sxs-lookup"><span data-stu-id="172c3-256">Direct Routing requires the user to be homed in Skype for Business Online.</span></span> <span data-ttu-id="172c3-257">Puede comprobarlo mirando el parámetro RegistrarPool.</span><span class="sxs-lookup"><span data-stu-id="172c3-257">You can check this by looking at the RegistrarPool parameter.</span></span> <span data-ttu-id="172c3-258">Debe tener un valor en el dominio infra.lync.com.</span><span class="sxs-lookup"><span data-stu-id="172c3-258">It needs to have a value in the infra.lync.com domain.</span></span>

1. <span data-ttu-id="172c3-259">Conectar con PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="172c3-259">Connect to remote PowerShell.</span></span>
2. <span data-ttu-id="172c3-260">Problema el comando:</span><span class="sxs-lookup"><span data-stu-id="172c3-260">Issue the command:</span></span> 

```
Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool
``` 

### <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a><span data-ttu-id="172c3-261">Configurar el número de teléfono y habilitar correo de voz y telefonía IP empresarial</span><span class="sxs-lookup"><span data-stu-id="172c3-261">Configure the phone number and enable enterprise voice and voicemail</span></span> 

<span data-ttu-id="172c3-262">Una vez que haya creado el usuario y asigna una licencia, el siguiente paso es configurar su número de teléfono y correo de voz.</span><span class="sxs-lookup"><span data-stu-id="172c3-262">After you have created the user and assigned a license, the next step is to configure their phone number and voicemail.</span></span> <span data-ttu-id="172c3-263">Esto puede realizarse en un solo paso.</span><span class="sxs-lookup"><span data-stu-id="172c3-263">This can be done in one step.</span></span> 

<span data-ttu-id="172c3-264">Para agregar el número de teléfono y habilitar para correo de voz:</span><span class="sxs-lookup"><span data-stu-id="172c3-264">To add the phone number and enable for voicemail:</span></span>
 
1. <span data-ttu-id="172c3-265">Conectarse a una sesión remota de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="172c3-265">Connect to a remote PowerShell session.</span></span> 
2. <span data-ttu-id="172c3-266">Escriba el comando:</span><span class="sxs-lookup"><span data-stu-id="172c3-266">Enter the command:</span></span> 
    
```
Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:+ phone number
```

<span data-ttu-id="172c3-267">Por ejemplo, para agregar un número de teléfono para el usuario "Sergio bajo", escribiría lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="172c3-267">For example, to add a phone number for user “Spencer Low,” you would enter the following:</span></span> 

```
Set-CsUser - “Spencer Low" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
```

<span data-ttu-id="172c3-268">El número de teléfono utilizado debe configurarse como un número de teléfono E.164 completo con el código de país.</span><span class="sxs-lookup"><span data-stu-id="172c3-268">The phone number used has to be configured as a full E.164 phone number with country code.</span></span> 

  > [!NOTE]
  > <span data-ttu-id="172c3-269">Si el número de teléfono del usuario se administra en local, use local Skype para Shell de administración de negocio o Panel de Control para configurar el número de teléfono del usuario.</span><span class="sxs-lookup"><span data-stu-id="172c3-269">If the user’s phone number is managed on premises, use on-premises Skype for Business Management Shell or Control Panel to configure the user's phone number.</span></span> 

### <a name="configure-voice-routing"></a><span data-ttu-id="172c3-270">Configurar enrutamiento de voz</span><span class="sxs-lookup"><span data-stu-id="172c3-270">Configure Voice Routing</span></span> 

<span data-ttu-id="172c3-271">Microsoft Phone System tiene un mecanismo de enrutamiento que permite que una llamada se envíen a un SBC específico en función de:</span><span class="sxs-lookup"><span data-stu-id="172c3-271">Microsoft Phone System has a routing mechanism that allows a call to be sent to a specific SBC based on:</span></span> 

- <span data-ttu-id="172c3-272">Patrón de número llamado</span><span class="sxs-lookup"><span data-stu-id="172c3-272">Called number pattern</span></span> 
- <span data-ttu-id="172c3-273">Patrón de número llamado + usuario específico que realiza la llamada</span><span class="sxs-lookup"><span data-stu-id="172c3-273">Called number pattern + Specific User who makes the call</span></span>
 
<span data-ttu-id="172c3-274">SBCs se pueden designar como activo y copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="172c3-274">SBCs can be designated as active and backup.</span></span> <span data-ttu-id="172c3-275">Es decir, cuando la SBC que está configurado como activo para este patrón de número, o patrón de número + usuario específico, no está disponible y, a continuación, se van a enrutar las llamadas a un SBC copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="172c3-275">That means when the SBC that is configured as active for this number pattern, or number pattern + specific user, is not available, then the calls will be routed to a backup SBC.</span></span>
 
<span data-ttu-id="172c3-276">Enrutamiento de llamadas se compone de los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="172c3-276">Call routing is made up of the following elements:</span></span> 
- <span data-ttu-id="172c3-277">Directiva de enrutamiento de voz: contenedor de usos de RTC; se pueden asignar a un usuario o a varios usuarios</span><span class="sxs-lookup"><span data-stu-id="172c3-277">Voice Routing Policy – container for PSTN Usages; can be assigned to a user or to multiple users</span></span> 
- <span data-ttu-id="172c3-278">Usos de RTC: contenedor de rutas de voz y los usos de RTC; se pueden compartir en diferentes directivas de enrutamiento de voz</span><span class="sxs-lookup"><span data-stu-id="172c3-278">PSTN Usages – container for Voice Routes and PSTN Usages; can be shared in different Voice Routing Policies</span></span> 
- <span data-ttu-id="172c3-279">Rutas: patrón de número y un conjunto de puertas de enlace RTC en línea que se usará para las llamadas donde número de llamada coincide con el patrón de voz</span><span class="sxs-lookup"><span data-stu-id="172c3-279">Voice Routes – number pattern and set of Online PSTN Gateways to use for calls where calling number matches the pattern</span></span> 
- <span data-ttu-id="172c3-280">Puerta de enlace de RTC Online - puntero en SBC, también almacena la configuración que se aplica cuando se llama a través de SBC, como hacia delante P-Asserted-Identity (PAI) o códecs preferido; se pueden agregar a las rutas de voz</span><span class="sxs-lookup"><span data-stu-id="172c3-280">Online PSTN Gateway - pointer at SBC, also stores the configuration that is applied when call is placed via the SBC, such as forward P-Asserted-Identity (PAI) or Preferred Codecs; can be added to Voice Routes</span></span> 

#### <a name="creating-a-voice-routing-policy-with-one-pstn-usage"></a><span data-ttu-id="172c3-281">Creación de una directiva de enrutamiento de voz con un uso de RTC</span><span class="sxs-lookup"><span data-stu-id="172c3-281">Creating a voice routing policy with one PSTN Usage</span></span> 

<span data-ttu-id="172c3-282">En el siguiente diagrama se muestra dos ejemplos de las directivas de enrutamiento de voz en el flujo de la llamada.</span><span class="sxs-lookup"><span data-stu-id="172c3-282">The following diagram shows two examples of voice routing policies in call flow.</span></span>

<span data-ttu-id="172c3-283">**Llamar al flujo de 1 (a la izquierda):** Si un usuario realiza una llamada a +1 425 XXX XX XX o +1 206 XXX XX XX, la llamada se enruta a SBC sbc1<span></span>. contoso.biz o sbc2<span></span>. contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="172c3-283">**Call Flow 1 (on the left):** If a user makes a call to  +1 425 XXX XX XX or +1 206 XXX XX XX, the call is routed  to SBC sbc1<span></span>.contoso.biz or sbc2<span></span>.contoso.biz.</span></span> <span data-ttu-id="172c3-284">Si ninguno de los dos sbc1<span></span>. contoso.biz ni sbc2<span></span>. contoso.biz están disponibles, se interrumpe la llamada.</span><span class="sxs-lookup"><span data-stu-id="172c3-284">If neither sbc1<span></span>.contoso.biz nor sbc2<span></span>.contoso.biz are available, the call is dropped.</span></span> 

<span data-ttu-id="172c3-285">**2 de flujo de llamadas (a la derecha):** Si un usuario realiza una llamada a +1 425 XXX XX XX o +1 206 XXX XX XX, la llamada se enruta primero a SBC sbc1<span></span>. contoso.biz o sbc2<span></span>. contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="172c3-285">**Call Flow 2 (on the right):** If a user makes a call to  +1 425 XXX XX XX or +1 206 XXX XX XX, the call is first routed to SBC sbc1<span></span>.contoso.biz or sbc2<span></span>.contoso.biz.</span></span> <span data-ttu-id="172c3-286">Si ninguno de los dos SBC está disponible, se intentará la ruta con la prioridad más baja (sbc3<span></span>. contoso.biz y sbc4<span></span>. contoso.biz).</span><span class="sxs-lookup"><span data-stu-id="172c3-286">If neither SBC is available, the route with lower priority will be tried (sbc3<span></span>.contoso.biz and sbc4<span></span>.contoso.biz).</span></span> <span data-ttu-id="172c3-287">Si ninguno de los SBCs están disponible, se interrumpe la llamada.</span><span class="sxs-lookup"><span data-stu-id="172c3-287">If none of the SBCs are available, the call is dropped.</span></span> 

![Se muestran ejemplos de directiva de enrutamiento de voz](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

<span data-ttu-id="172c3-289">En ambos ejemplos, mientras que la ruta de voz se asigna prioridades, el SBCs en las rutas se intentan en orden aleatorio.</span><span class="sxs-lookup"><span data-stu-id="172c3-289">In both examples, while the Voice Route is assigned priorities, the SBCs in the routes are tried in random order.</span></span>

  > [!NOTE]
  > <span data-ttu-id="172c3-290">A menos que el usuario también dispone de una licencia de llamar a planeación de Microsoft, se quitan las llamadas a cualquier número excepto los números que coincidan con los patrones de + +1 425 XXX XX XX o +1 206 XXX XX XX en el ejemplo de configuración.</span><span class="sxs-lookup"><span data-stu-id="172c3-290">Unless the user also has a Microsoft Calling Plan license, calls to any number except numbers matching the patterns + +1 425 XXX XX XX or +1 206 XXX XX XX in the example configuration are dropped.</span></span> <span data-ttu-id="172c3-291">Si el usuario tiene una licencia de planeación de la llamada, la llamada se enruta automáticamente según las directivas de la planeación de una llamada a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="172c3-291">If the user has a Calling Plan license, the call is automatically routed according to the policies of  the Microsoft Calling Plan.</span></span> 

<span data-ttu-id="172c3-292">La planeación de una llamada a Microsoft se aplica automáticamente como la última ruta a todos los usuarios con la licencia de llamar a planeación de Microsoft y no requiere la configuración de enrutamiento de llamada adicionales.</span><span class="sxs-lookup"><span data-stu-id="172c3-292">The Microsoft Calling Plan applies automatically as the last route to all users with the Microsoft Calling Plan license and does not require additional call routing configuration.</span></span>

<span data-ttu-id="172c3-293">En el ejemplo que se muestra en el diagrama siguiente, se agrega una ruta de voz para enviar las llamadas a todos los demás Estados Unidos y Canadá número (llamadas que vaya a patrón de número llamado + 1 XXX XXX XX XX).</span><span class="sxs-lookup"><span data-stu-id="172c3-293">In the example shown in the following diagram, a voice route is added to send calls to all other US and Canadian number (calls that go to called number pattern +1 XXX XXX XX XX).</span></span>

![Directiva de enrutamiento con una tercera ruta de voz de muestra](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

<span data-ttu-id="172c3-295">Para todas las llamadas, si un usuario tiene dos licencias (sistema de teléfono de Microsoft y llamar a planeación de Microsoft), se usa ruta automático.</span><span class="sxs-lookup"><span data-stu-id="172c3-295">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), Automatic Route is used.</span></span> <span data-ttu-id="172c3-296">Si no hay nada coincide con los patrones de números en las rutas de voz en línea creadas por el administrador, se enruta a través de una llamada a planeación de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="172c3-296">If nothing matches the number patterns in the administrator-created online voice routes, route via Microsoft Calling Plan.</span></span>

<span data-ttu-id="172c3-297">Si el usuario tiene sólo del sistema de teléfono de Microsoft, se interrumpe la llamada porque no hay reglas de coincidencia están disponibles.</span><span class="sxs-lookup"><span data-stu-id="172c3-297">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

  > [!NOTE]
  > <span data-ttu-id="172c3-298">El valor de la prioridad de ruta "Otros + 1" no importa en este caso, como hay sólo una ruta que coincide con el patrón + 1 XXX XXX XX XX.</span><span class="sxs-lookup"><span data-stu-id="172c3-298">The Priority value for route “Other +1” doesn’t matter in this case, as there is only one route that matches the pattern +1 XXX XXX XX XX.</span></span> <span data-ttu-id="172c3-299">Si un usuario realiza una llamada a + 1 324 567 89 89 y sbc5.contoso.biz y sbc6.contoso.biz no están disponibles, se interrumpe la llamada.</span><span class="sxs-lookup"><span data-stu-id="172c3-299">If a user makes a call to +1 324 567 89 89 and both sbc5.contoso.biz and sbc6.contoso.biz are unavailable, the call is dropped.</span></span>

<span data-ttu-id="172c3-300">La tabla siguiente resume la configuración con tres rutas de voz.</span><span class="sxs-lookup"><span data-stu-id="172c3-300">The following table summarizes the configuration using three voice routes.</span></span> <span data-ttu-id="172c3-301">En este ejemplo, todas las rutas de tres forman parte de la misma uso de RTC "Nosotros y Canadá".</span><span class="sxs-lookup"><span data-stu-id="172c3-301">In this example, all three routes are part of the same PSTN Usage “US and Canada”.</span></span>

|<span data-ttu-id="172c3-302">**Uso de RTC**</span><span class="sxs-lookup"><span data-stu-id="172c3-302">**PSTN usage**</span></span>|<span data-ttu-id="172c3-303">**Ruta de voz**</span><span class="sxs-lookup"><span data-stu-id="172c3-303">**Voice route**</span></span>|<span data-ttu-id="172c3-304">**Patrón de números**</span><span class="sxs-lookup"><span data-stu-id="172c3-304">**Number pattern**</span></span>|<span data-ttu-id="172c3-305">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="172c3-305">**Priority**</span></span>|<span data-ttu-id="172c3-306">**SBC**</span><span class="sxs-lookup"><span data-stu-id="172c3-306">**SBC**</span></span>|<span data-ttu-id="172c3-307">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="172c3-307">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="172c3-308">NOSOTROS solo</span><span class="sxs-lookup"><span data-stu-id="172c3-308">US only</span></span>|<span data-ttu-id="172c3-309">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="172c3-309">“Redmond 1”</span></span>|<span data-ttu-id="172c3-310">^\\+ 1 (425\|206)(\d{7})$</span><span class="sxs-lookup"><span data-stu-id="172c3-310">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="172c3-311">1</span><span class="sxs-lookup"><span data-stu-id="172c3-311">1</span></span>|<span data-ttu-id="172c3-312">sbc1<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="172c3-312">sbc1<span></span>.contoso.biz</span></span><br/><span data-ttu-id="172c3-313">sbc2<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="172c3-313">sbc2<span></span>.contoso.biz</span></span>|<span data-ttu-id="172c3-314">Ruta activa para números de llamada +1 425 XXX XX XX o +1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="172c3-314">Active route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="172c3-315">NOSOTROS solo</span><span class="sxs-lookup"><span data-stu-id="172c3-315">US only</span></span>|<span data-ttu-id="172c3-316">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="172c3-316">“Redmond 2”</span></span>|<span data-ttu-id="172c3-317">^\\+ 1 (425\|206)(\d{7})$</span><span class="sxs-lookup"><span data-stu-id="172c3-317">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="172c3-318">2</span><span class="sxs-lookup"><span data-stu-id="172c3-318">2</span></span>|<span data-ttu-id="172c3-319">sbc3<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="172c3-319">sbc3<span></span>.contoso.biz</span></span><br/><span data-ttu-id="172c3-320">sbc4<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="172c3-320">sbc4<span></span>.contoso.biz</span></span>|<span data-ttu-id="172c3-321">Ruta de reserva para los números llamados +1 425 XXX XX XX o +1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="172c3-321">Backup route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="172c3-322">NOSOTROS solo</span><span class="sxs-lookup"><span data-stu-id="172c3-322">US only</span></span>|<span data-ttu-id="172c3-323">"Otros + 1"</span><span class="sxs-lookup"><span data-stu-id="172c3-323">"Other +1”</span></span>|<span data-ttu-id="172c3-324">^\\+ 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="172c3-324">^\\+1(\d{10})$</span></span>|<span data-ttu-id="172c3-325">3</span><span class="sxs-lookup"><span data-stu-id="172c3-325">3</span></span>|<span data-ttu-id="172c3-326">sbc5<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="172c3-326">sbc5<span></span>.contoso.biz</span></span><br/><span data-ttu-id="172c3-327">sbc6<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="172c3-327">sbc6<span></span>.contoso.biz</span></span>|<span data-ttu-id="172c3-328">Enrutar para números de llamada + 1 XXX XXX XX XX (excepto +1 425 XXX XX XX o +1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="172c3-328">Route for called numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|||||||

<span data-ttu-id="172c3-329">Todas las rutas se asocian con el uso de RTC "Nosotros y Canadá" y el uso de RTC está asociado con la directiva de enrutamiento de voz "Sólo en Estados Unidos."</span><span class="sxs-lookup"><span data-stu-id="172c3-329">All routes are associated with the PSTN Usage “US and Canada” and the PSTN Usage is associated with the Voice Routing Policy “US Only.”</span></span> <span data-ttu-id="172c3-330">En este ejemplo, se asigna la directiva de enrutamiento de voz al usuario Spencer Low.</span><span class="sxs-lookup"><span data-stu-id="172c3-330">In this example, the voice routing policy is assigned to user Spencer Low.</span></span>

#### <a name="examples-of-call-routes"></a><span data-ttu-id="172c3-331">Ejemplos de rutas de llamadas</span><span class="sxs-lookup"><span data-stu-id="172c3-331">Examples of call routes</span></span>

<span data-ttu-id="172c3-332">En el siguiente ejemplo, demostraremos cómo configurar rutas, usos de RTC y las directivas de enrutamiento y se asigne la directiva para el usuario.</span><span class="sxs-lookup"><span data-stu-id="172c3-332">In the following example,  we demonstrate how to configure Routes, PSTN Usages, and Routing policies, and we assign the policy to the user.</span></span>

<span data-ttu-id="172c3-333">**Paso 1:** Crear el uso de RTC "Estados Unidos y Canadá".</span><span class="sxs-lookup"><span data-stu-id="172c3-333">**Step 1:** Create the PSTN Usage “US and Canada.”</span></span>

<span data-ttu-id="172c3-334">En un Skype para la sesión de PowerShell remoto empresarial, escriba:</span><span class="sxs-lookup"><span data-stu-id="172c3-334">In a  Skype for Business Remote PowerShell session, type:</span></span>

```
Set-CsOnlinePstnUsage  -Identity Global -Usage @{Add="US and Canada"}
```

<span data-ttu-id="172c3-335">Validar que el uso se ha creado escribiendo:</span><span class="sxs-lookup"><span data-stu-id="172c3-335">Validate that the usage was created by entering:</span></span> 
```
Get-CSOnlinePSTNUsage
``` 
<span data-ttu-id="172c3-336">Que devuelve una lista de nombres que es posible que esté truncada:</span><span class="sxs-lookup"><span data-stu-id="172c3-336">Which returns a list of names that may be truncated:</span></span>
```
  Identity  : Global
  Usage     : {testusage, US and Canada, International, karlUsage. . .}
```
<span data-ttu-id="172c3-337">En el ejemplo siguiente, puede ver el resultado de la ejecución del comando de PowerShell *`(Get-CSOnlinePSTNUsage).usage`* para mostrar los nombres completos (no truncados).</span><span class="sxs-lookup"><span data-stu-id="172c3-337">In the example below, you can see the result of the running the PowerShell command *`(Get-CSOnlinePSTNUsage).usage`* to display full names (not truncated).</span></span>    
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

<span data-ttu-id="172c3-338">**Paso 2:** En una sesión de PowerShell en Skype para profesionales en línea, cree tres rutas: Redmond 1, Redmond 2 y otros + 1, como se detalla en la tabla anterior.</span><span class="sxs-lookup"><span data-stu-id="172c3-338">**Step 2:** In a PowerShell session in Skype for Business Online, create three routes: Redmond 1, Redmond 2, and Other+1, as detailed in the previous table.</span></span> 

<span data-ttu-id="172c3-339">Para crear la ruta de "Redmond 1", escriba:</span><span class="sxs-lookup"><span data-stu-id="172c3-339">To create the “Redmond 1” route, enter:</span></span>

  ```
  New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^+1(425|206)
  (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
  ```

<span data-ttu-id="172c3-340">Que devuelve:</span><span class="sxs-lookup"><span data-stu-id="172c3-340">Which returns:</span></span>
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
<span data-ttu-id="172c3-341">Para crear la ruta de Redmond 2, escriba:</span><span class="sxs-lookup"><span data-stu-id="172c3-341">To create the Redmond 2 route, enter:</span></span>

```
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="172c3-342">Para crear la ruta de otra + 1, escriba:</span><span class="sxs-lookup"><span data-stu-id="172c3-342">To create the Other +1 route, enter:</span></span>

```
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > <span data-ttu-id="172c3-343">Asegúrese de que la expresión regular en el atributo NumberPattern es una expresión válida.</span><span class="sxs-lookup"><span data-stu-id="172c3-343">Make sure that your regular expression in the NumberPattern attribute is a valid expression.</span></span> <span data-ttu-id="172c3-344">Puede probarla con este sitio Web:[https://www.regexpal.com](https://www.regexpal.com)</span><span class="sxs-lookup"><span data-stu-id="172c3-344">You can test it using this website: [https://www.regexpal.com](https://www.regexpal.com)</span></span>

<span data-ttu-id="172c3-345">En algunos casos es necesario para enrutar todas las llamadas a la misma SBC; Por favor, use - NumberPattern ". \*"</span><span class="sxs-lookup"><span data-stu-id="172c3-345">In some cases there is a need to route all calls to the same SBC; please use -NumberPattern “.\*”</span></span>

- <span data-ttu-id="172c3-346">Enrutar todas las llamadas a la misma SBC</span><span class="sxs-lookup"><span data-stu-id="172c3-346">Route all calls to same SBC</span></span>

    ```
    Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" 
     -OnlinePstnGatewayList sbc1.contoso.biz
    ```

<span data-ttu-id="172c3-347">Validar que ha configurado correctamente la ruta mediante la ejecución de la `Get-CSOnlineVoiceRoute` comando de Powershell mediante las opciones tal como se muestra:</span><span class="sxs-lookup"><span data-stu-id="172c3-347">Validate that you’ve correctly configured the route by running the `Get-CSOnlineVoiceRoute` Powershell command using options as shown:</span></span> 

```
New-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
<span data-ttu-id="172c3-348">Que se debe devolver:</span><span class="sxs-lookup"><span data-stu-id="172c3-348">Which should return:</span></span>
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
NumberPattern       : ^\\+1(\d{10})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc5.contoso.biz, sbc6.contoso.biz}
Name            : Other +1
</pre>

<span data-ttu-id="172c3-349">En el ejemplo, la ruta "Otros + 1" automáticamente se asignó prioridad.</span><span class="sxs-lookup"><span data-stu-id="172c3-349">In the example, the route “Other +1” was automatically assigned priority.</span></span> 

<span data-ttu-id="172c3-350">**Paso 3:** Crear una directiva de enrutamiento de voz "Nosotros solo" y agregar a la directiva el uso de RTC "Estados Unidos y Canadá".</span><span class="sxs-lookup"><span data-stu-id="172c3-350">**Step 3:** Create a Voice Routing Policy  “US Only” and add to the policy the PSTN Usage “US and Canada.”</span></span>

<span data-ttu-id="172c3-351">En una sesión de PowerShell en Skype para profesionales en línea, escriba:</span><span class="sxs-lookup"><span data-stu-id="172c3-351">In a PowerShell session in Skype for Business Online, type:</span></span>

```
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="172c3-352">En este ejemplo, se muestra el resultado:</span><span class="sxs-lookup"><span data-stu-id="172c3-352">The result is shown in this example:</span></span>

<pre>
Identity        : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
</pre>

<span data-ttu-id="172c3-353">**Paso 4:** Conceder al usuario Spence Low una directiva de enrutamiento de voz mediante el uso de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="172c3-353">**Step 4:** Grant to user Spence Low a voice routing policy by using PowerShell.</span></span>

- <span data-ttu-id="172c3-354">En una sesión de Powershell en Skype para profesionales en línea, escriba:</span><span class="sxs-lookup"><span data-stu-id="172c3-354">In a Powershell session in Skype for Business Online, type:</span></span>

    ```Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"```

- <span data-ttu-id="172c3-355">Validar la asignación de directiva, escriba este comando:</span><span class="sxs-lookup"><span data-stu-id="172c3-355">Validate the policy assignment by entering this command:</span></span>

```
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```
<span data-ttu-id="172c3-356">Que devuelve:</span><span class="sxs-lookup"><span data-stu-id="172c3-356">Which returns:</span></span>
<pre>
    OnlineVoiceRoutingPolicy
    ---------------------
    US Only
</pre>

#### <a name="creating-a-voice-routing-policy-with-several-pstn-usages"></a><span data-ttu-id="172c3-357">Creación de una directiva de enrutamiento de voz con varios usos de RTC</span><span class="sxs-lookup"><span data-stu-id="172c3-357">Creating a Voice Routing Policy with several PSTN Usages</span></span>

<span data-ttu-id="172c3-358">La directiva de enrutamiento de voz creada anteriormente sólo permite las llamadas a números de teléfono en Estados Unidos y Canadá--a menos que la licencia de llamar a planeación de Microsoft también está asignada al usuario.</span><span class="sxs-lookup"><span data-stu-id="172c3-358">The Voice Routing Policy created previously only allows calls to phone numbers in the US and Canada--unless the Microsoft Calling Plan license is also assigned to the user.</span></span>

<span data-ttu-id="172c3-359">En el ejemplo siguiente, puede crear la directiva de enrutamiento de voz "No hay restricciones".</span><span class="sxs-lookup"><span data-stu-id="172c3-359">In the example that follows, you can create the Voice Routing Policy “No Restrictions.”</span></span> <span data-ttu-id="172c3-360">La directiva vuelve a usar el uso de RTC "Nosotros y Canadá" creado en el ejemplo anterior, así como el uso de RTC nuevo "Internacional".</span><span class="sxs-lookup"><span data-stu-id="172c3-360">The policy reuses the PSTN Usage “US and Canada” created in the previous example, as well as the new PSTN Usage “International.”</span></span> 

<span data-ttu-id="172c3-361">Esto distribuye todas las demás llamadas a la sbc2 SBCs<span></span>. contoso.biz y sbc5<span></span>. contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="172c3-361">This routes all other calls to the SBCs sbc2<span></span>.contoso.biz and sbc5<span></span>.contoso.biz.</span></span> <span data-ttu-id="172c3-362">Los ejemplos que se muestran asignan directiva de nosotros solo al usuario "Sergio bajo" y sin restricciones al usuario "John Woods."</span><span class="sxs-lookup"><span data-stu-id="172c3-362">The examples that are shown assign US Only policy to user “Spencer Low,” and No Restrictions to the user “John Woods.”</span></span>

<span data-ttu-id="172c3-363">Sergio baja – permiten llamadas sólo a los números de Estados Unidos y Canadá.</span><span class="sxs-lookup"><span data-stu-id="172c3-363">Spencer Low – Calls allowed only to US and Canadian numbers.</span></span> <span data-ttu-id="172c3-364">Cuando se llama al intervalo de números de Redmond, se debe usar el conjunto específico de SBC.</span><span class="sxs-lookup"><span data-stu-id="172c3-364">When calling to Redmond number range, the specific set of SBC must be used.</span></span> <span data-ttu-id="172c3-365">Los números que no son-US no se enrutarán a menos que la licencia de planeación de la llamada se asigna al usuario.</span><span class="sxs-lookup"><span data-stu-id="172c3-365">Non-US numbers will not be routed unless the Calling Plan license is assigned to the user.</span></span>

<span data-ttu-id="172c3-366">John Woods – permitidas a cualquier número de llamadas.</span><span class="sxs-lookup"><span data-stu-id="172c3-366">John Woods – Calls allowed to any number.</span></span> <span data-ttu-id="172c3-367">Cuando se llama al intervalo de números de Redmond, se debe usar el conjunto específico de SBC.</span><span class="sxs-lookup"><span data-stu-id="172c3-367">When calling to Redmond number range, the specific set of SBC must be used.</span></span> <span data-ttu-id="172c3-368">Los números que no son-US se enrutarán a través de sbc2<span></span>. contoso.biz y sbc5<span></span>. contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="172c3-368">Non-US numbers will be routed via sbc2<span></span>.contoso.biz and sbc5<span></span>.contoso.biz.</span></span>

![Muestra la directiva de enrutamiento de voz asignada a usuario Spencer Low](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

<span data-ttu-id="172c3-370">Para todas las llamadas, si un usuario tiene dos licencias (sistema de teléfono de Microsoft y llamar a planeación de Microsoft), se usa ruta automático.</span><span class="sxs-lookup"><span data-stu-id="172c3-370">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), Automatic Route is used.</span></span> <span data-ttu-id="172c3-371">Si no hay nada coincide con los patrones de números en las rutas de voz en línea creadas por el administrador, se enruta a través de una llamada a planeación de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="172c3-371">If nothing matches the number patterns in the administrator-created online voice routes, route via Microsoft Calling Plan.</span></span>

<span data-ttu-id="172c3-372">Si el usuario tiene sólo del sistema de teléfono de Microsoft, se interrumpe la llamada porque no hay reglas de coincidencia están disponibles.</span><span class="sxs-lookup"><span data-stu-id="172c3-372">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

![Muestra la directiva de enrutamiento de voz asignada a usuario John Woods](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

<span data-ttu-id="172c3-374">En la siguiente tabla se resume denominación de uso de enrutamiento directiva "Sin restricciones" y rutas de voz.</span><span class="sxs-lookup"><span data-stu-id="172c3-374">The following table  summarizes routing policy “No Restrictions” usage designations and voice routes.</span></span> 

|<span data-ttu-id="172c3-375">**Uso de RTC**</span><span class="sxs-lookup"><span data-stu-id="172c3-375">**PSTN usage**</span></span>|<span data-ttu-id="172c3-376">**Ruta de voz**</span><span class="sxs-lookup"><span data-stu-id="172c3-376">**Voice route**</span></span>|<span data-ttu-id="172c3-377">**Patrón de números**</span><span class="sxs-lookup"><span data-stu-id="172c3-377">**Number pattern**</span></span>|<span data-ttu-id="172c3-378">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="172c3-378">**Priority**</span></span>|<span data-ttu-id="172c3-379">**SBC**</span><span class="sxs-lookup"><span data-stu-id="172c3-379">**SBC**</span></span>|<span data-ttu-id="172c3-380">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="172c3-380">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="172c3-381">NOSOTROS solo</span><span class="sxs-lookup"><span data-stu-id="172c3-381">US Only</span></span>|<span data-ttu-id="172c3-382">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="172c3-382">“Redmond 1”</span></span>|<span data-ttu-id="172c3-383">^ + 1 (425\|206)(\d{7})$</span><span class="sxs-lookup"><span data-stu-id="172c3-383">^+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="172c3-384">1</span><span class="sxs-lookup"><span data-stu-id="172c3-384">1</span></span>|<span data-ttu-id="172c3-385">sbc1<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="172c3-385">sbc1<span></span>.contoso.biz</span></span><br/><span data-ttu-id="172c3-386">sbc2<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="172c3-386">sbc2<span></span>.contoso.biz</span></span>|<span data-ttu-id="172c3-387">Ruta activa para los números del destinatario de la llamada +1 425 XXX XX XX o +1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="172c3-387">Active route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="172c3-388">NOSOTROS solo</span><span class="sxs-lookup"><span data-stu-id="172c3-388">US Only</span></span>|<span data-ttu-id="172c3-389">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="172c3-389">“Redmond 2”</span></span>|<span data-ttu-id="172c3-390">^ + 1 (425\|206)(\d{7})$</span><span class="sxs-lookup"><span data-stu-id="172c3-390">^+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="172c3-391">2</span><span class="sxs-lookup"><span data-stu-id="172c3-391">2</span></span>|<span data-ttu-id="172c3-392">sbc3<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="172c3-392">sbc3<span></span>.contoso.biz</span></span><br/><span data-ttu-id="172c3-393">sbc4<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="172c3-393">sbc4<span></span>.contoso.biz</span></span>|<span data-ttu-id="172c3-394">Ruta de reserva para los números del destinatario de la llamada +1 425 XXX XX XX o +1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="172c3-394">Backup route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="172c3-395">NOSOTROS solo</span><span class="sxs-lookup"><span data-stu-id="172c3-395">US Only</span></span>|<span data-ttu-id="172c3-396">"Otros + 1"</span><span class="sxs-lookup"><span data-stu-id="172c3-396">“Other +1”</span></span>|<span data-ttu-id="172c3-397">^ + 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="172c3-397">^+1(\d{10})$</span></span>|<span data-ttu-id="172c3-398">3</span><span class="sxs-lookup"><span data-stu-id="172c3-398">3</span></span>|<span data-ttu-id="172c3-399">sbc5<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="172c3-399">sbc5<span></span>.contoso.biz</span></span><br/><span data-ttu-id="172c3-400">sbc6<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="172c3-400">sbc6<span></span>.contoso.biz</span></span>|<span data-ttu-id="172c3-401">+ 1 XXX XXX XX XX (excepto +1 425 XXX XX XX o +1 206 XXX XX XX) los números de ruta para el destinatario de la llamada</span><span class="sxs-lookup"><span data-stu-id="172c3-401">Route for callee numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|<span data-ttu-id="172c3-402">International</span><span class="sxs-lookup"><span data-stu-id="172c3-402">International</span></span>|<span data-ttu-id="172c3-403">International</span><span class="sxs-lookup"><span data-stu-id="172c3-403">International</span></span>|<span data-ttu-id="172c3-404">\d+</span><span class="sxs-lookup"><span data-stu-id="172c3-404">\d+</span></span>|<span data-ttu-id="172c3-405">4</span><span class="sxs-lookup"><span data-stu-id="172c3-405">4</span></span>|<span data-ttu-id="172c3-406">sbc2<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="172c3-406">sbc2<span></span>.contoso.biz</span></span><br/><span data-ttu-id="172c3-407">sbc5<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="172c3-407">sbc5<span></span>.contoso.biz</span></span>|<span data-ttu-id="172c3-408">Ruta para cualquier patrón de número</span><span class="sxs-lookup"><span data-stu-id="172c3-408">Route for any number pattern</span></span> |


  > [!NOTE]
  > - <span data-ttu-id="172c3-409">El orden de los usos de RTC en las directivas de enrutamiento de voz es fundamental.</span><span class="sxs-lookup"><span data-stu-id="172c3-409">The order of PSTN Usages in Voice Routing Policies is critical.</span></span> <span data-ttu-id="172c3-410">Los usos se aplican en orden, y si se encuentra una coincidencia en el primer uso, a continuación, otros usos no se evaluarán nunca.</span><span class="sxs-lookup"><span data-stu-id="172c3-410">The usages are applied in order, and if a match is found in the first usage, then other usages are never evaluated.</span></span> <span data-ttu-id="172c3-411">El uso de RTC "Internacional" se debe colocar después el uso de RTC "Sólo en EE."</span><span class="sxs-lookup"><span data-stu-id="172c3-411">The PSTN Usage “International” must be placed after the PSTN Usage “US Only.”</span></span> <span data-ttu-id="172c3-412">Para cambiar el orden de los usos de RTC, vuelva a ejecutar la `Set-CSOnlineRouteRoutingPolicy` comando.</span><span class="sxs-lookup"><span data-stu-id="172c3-412">To change the order of the PSTN Usages, please run the `Set-CSOnlineRouteRoutingPolicy` command.</span></span> <br/><span data-ttu-id="172c3-413">Por ejemplo, para cambiar el orden de "Nosotros y Canadá" ejecutar "Internacional" y el segundo para el orden inverso:</span><span class="sxs-lookup"><span data-stu-id="172c3-413">For example, to change the order from “US and Canada” first and “International” second to the reverse order run:</span></span><br/>   `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - <span data-ttu-id="172c3-414">La prioridad de las rutas de voz de "caracteres International" y "Otros + 1" se asignan automáticamente.</span><span class="sxs-lookup"><span data-stu-id="172c3-414">The priority for  “Other +1” and “International” Voice routes are assigned automatically.</span></span> <span data-ttu-id="172c3-415">Éstos no importan como que tienen una prioridad inferior que "Redmond 1" y "Redmond 2".</span><span class="sxs-lookup"><span data-stu-id="172c3-415">They don’t matter as long as they have lower priorities than “Redmond 1” and “Redmond 2.”</span></span>

#### <a name="example-of-voice-routing-policy-for-user-john-woods"></a><span data-ttu-id="172c3-416">Ejemplo de directiva de enrutamiento de voz para el usuario John Woods</span><span class="sxs-lookup"><span data-stu-id="172c3-416">Example of Voice Routing Policy for user John Woods</span></span>

<span data-ttu-id="172c3-417">Los pasos para crear el uso de RTC "Internacional", "Internacional", de la ruta de voz "Sin restricciones," Directiva de enrutamiento de voz y, a continuación, se asigna al usuario "John Woods" son los siguientes.</span><span class="sxs-lookup"><span data-stu-id="172c3-417">The steps to create PSTN Usage “International”, voice route “International,” Voice Routing Policy “No Restrictions,” and then assigning it to the user “John Woods” are as follows.</span></span>


1.  <span data-ttu-id="172c3-418">En primer lugar, cree el uso de RTC "Internacional".</span><span class="sxs-lookup"><span data-stu-id="172c3-418">First, create the PSTN Usage “International."</span></span> <span data-ttu-id="172c3-419">En una sesión remota de PowerShell en Skype para profesionales en línea, escriba:</span><span class="sxs-lookup"><span data-stu-id="172c3-419">In a remote PowerShell session in Skype for Business Online, enter:</span></span>

  ```
  Set-CsOnlinePstnUsage  -Identity Global -Usage @{Add="International"}
  ```

2.  <span data-ttu-id="172c3-420">A continuación, cree la nueva ruta de voz "Internacional".</span><span class="sxs-lookup"><span data-stu-id="172c3-420">Next, create the new voice route “International.”</span></span>

  ```
  New-CsOnlineVoiceRoute -Identity "International" -NumberPattern "\d+" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
  ```
  <span data-ttu-id="172c3-421">Que devuelve:</span><span class="sxs-lookup"><span data-stu-id="172c3-421">Which returns:</span></span>

  <pre>
  Identity                  : International 
  Priority                      : 5
  Description                   : 
  NumberPattern                 : \d+
  OnlinePstnUsages          : {International}    
  OnlinePstnGatewayList           : {sbc2.contoso.biz, sbc5.contoso.biz}
  Name                            : International
  SupressCallerId           :
  AlternateCallerId         :
</pre>
3.  <span data-ttu-id="172c3-422">A continuación, no cree una directiva de enrutamiento de voz "restricciones".</span><span class="sxs-lookup"><span data-stu-id="172c3-422">Next, create a Voice Routing Policy “No Restrictions”.</span></span> <span data-ttu-id="172c3-423">El uso de RTC "Redmond 1" y "Redmond" volver a usar en esta directiva de enrutamiento de voz para conservar un tratamiento especial para las llamadas al número "XX XX de XXX +1 425" y "XX XX de XXX +1 206" como llamadas locales o local.</span><span class="sxs-lookup"><span data-stu-id="172c3-423">The PSTN Usage “Redmond 1” and “Redmond “ are reused in this voice routing policy to preserve special handling for calls to number “+1 425 XXX XX XX” and “+1 206 XXX XX XX” as local or on-premise calls.</span></span>

```
New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", ”International”
```

    Take note of the order of PSTN Usages:

    a. If a call made to number “+1425 XXX XX XX” with the usages configured as in the following example, the call follows the route set in “US and Canada” usage and the special routing logic is applied. That is, the call is routed using  sbc1<span></span>.contoso.biz and sbc2<span></span>.contoso.biz first, and then  sbc3<span></span>.contoso.biz and sbc4<span></span>.contoso.biz as the backup routes. 

    b.  If “International” PSTN usage is before “US and Canada,” calls to + 1425 XXX XX XX are routed to sbc2<span></span>.contoso.biz and sbc5<span></span>.contoso.biz as part of the routing logic. Enter the command:

    ```New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", ”International”```

   <span data-ttu-id="172c3-424">Que devuelve</span><span class="sxs-lookup"><span data-stu-id="172c3-424">Which returns</span></span>

  <pre>
   Identity     : International 
   OnlinePstnUsages     : {US and Canada, International}     
   Description      :  
   RouteType        : BYOT
  </pre>

4.  <span data-ttu-id="172c3-425">Asignar la directiva de enrutamiento de voz para el usuario "John Woods" mediante el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="172c3-425">Assign the voice routing policy to the user “John Woods” using the following command.</span></span>

  ```
  Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions”
  ```

  <span data-ttu-id="172c3-426">A continuación, compruebe la asignación mediante el comando:</span><span class="sxs-lookup"><span data-stu-id="172c3-426">Then verify the assignment using the command:</span></span>   

  ```
  Get CsOnlineUser “John Woods” | Select OnlineVoiceRoutingPolicy
  ```
  <span data-ttu-id="172c3-427">Que devuelve:</span><span class="sxs-lookup"><span data-stu-id="172c3-427">Which returns:</span></span>

<pre>
    OnlineVoiceRoutingPolicy
    ------------------------
    No Restrictions
</pre>

<span data-ttu-id="172c3-428">El resultado es que la directiva de voz que se aplican a las llamadas de John Woods se sin restricciones y va a seguir la lógica de enrutamiento de llamadas disponible para llamadas de Estados Unidos, Canadá e internacional.</span><span class="sxs-lookup"><span data-stu-id="172c3-428">The result is that the voice policy applied to John Woods’ calls are unrestricted, and will follow the logic of call routing available for US, Canada, and International calling.</span></span>

## <a name="set-microsoft-teams-as-the-preferred-calling-client-for-users"></a><span data-ttu-id="172c3-429">Establecer Teams Microsoft como cliente llamado preferido para los usuarios</span><span class="sxs-lookup"><span data-stu-id="172c3-429">Set Microsoft Teams as the preferred calling client for users</span></span>

<span data-ttu-id="172c3-430">Sólo enrutamiento directa enruta las llamadas a y desde los usuarios si utilizan al cliente de los equipos.</span><span class="sxs-lookup"><span data-stu-id="172c3-430">Direct Routing only routes calls to and from users if they use the Teams client.</span></span> <span data-ttu-id="172c3-431">Si su organización sólo usa los equipos, "Equipos sólo" modo en la directiva de actualización se recomienda establecer.</span><span class="sxs-lookup"><span data-stu-id="172c3-431">If your organization only uses Teams, setting "Teams Only" mode in upgrade policy is recommended.</span></span> <span data-ttu-id="172c3-432">Si su organización usa Skype para Business Server o Skype para profesionales en línea, consulte el siguiente artículo para obtener más información y seleccione la opción adecuada: [comprender la coexistencia y actualización de viaje para Skype para profesionales y los equipos](https://docs.microsoft.com/en-us/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span><span class="sxs-lookup"><span data-stu-id="172c3-432">If you organization uses Skype for Business Server or Skype for Business Online, see the following article for more information and select the appropriate option:  [Understand coexistence and upgrade journey for Skype for Business and Teams](https://docs.microsoft.com/en-us/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span></span> 


## <a name="see-also"></a><span data-ttu-id="172c3-433">Vea también</span><span class="sxs-lookup"><span data-stu-id="172c3-433">See also</span></span>

[<span data-ttu-id="172c3-434">Planeación de enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="172c3-434">Plan Direct Routing</span></span>](direct-routing-plan.md)
