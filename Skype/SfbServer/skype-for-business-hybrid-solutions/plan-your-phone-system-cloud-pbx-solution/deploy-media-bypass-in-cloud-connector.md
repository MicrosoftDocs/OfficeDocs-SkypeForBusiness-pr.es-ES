---
title: Implementación de la omisión de medios en Cloud Connector Edition
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0ebba3a4-6124-434c-84aa-32b1cc3345bc
description: Lea este tema para obtener información sobre los pasos necesarios para implementar la omisión de medios con Cloud Connector Edition, versión 2,0 y posteriores.
ms.openlocfilehash: eeb566e2a1a16e235813c077d4e4bf6903a467d7
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359316"
---
# <a name="deploy-media-bypass-in-cloud-connector-edition"></a><span data-ttu-id="c6a9a-103">Implementación de la omisión de medios en Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="c6a9a-103">Deploy media bypass in Cloud Connector Edition</span></span>
 
> [!Important]
> <span data-ttu-id="c6a9a-104">Cloud Connector Edition se retirará del 31 de julio de 2021 junto con Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="c6a9a-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="c6a9a-105">Una vez que la organización haya actualizado a Teams, obtenga información sobre cómo conectar la red de telefonía local a Microsoft Teams mediante el [enrutamiento directo](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span><span class="sxs-lookup"><span data-stu-id="c6a9a-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="c6a9a-106">Lea este tema para obtener información sobre los pasos necesarios para implementar la omisión de medios con Cloud Connector Edition, versión 2,0 y posteriores.</span><span class="sxs-lookup"><span data-stu-id="c6a9a-106">Read this topic to learn about steps to deploy media bypass with Cloud Connector Edition version 2.0 and later.</span></span> 
  
<span data-ttu-id="c6a9a-107">La omisión de medios permite a un cliente enviar medios directamente al próximo salto de la red telefónica conmutada (RTC), una puerta de enlace o un controlador de borde de sesión (SBC), y eliminar el componente de Cloud Connector Edition de la ruta de medios.</span><span class="sxs-lookup"><span data-stu-id="c6a9a-107">Media bypass allows a client to send media directly to the Public Switched Telephone Network (PSTN) next hop—a gateway or Session Border Controller (SBC)—and eliminate the Cloud Connector Edition component from the media path.</span></span> <span data-ttu-id="c6a9a-108">Consulte también [Plan for Media bypass in Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md).</span><span class="sxs-lookup"><span data-stu-id="c6a9a-108">See also [Plan for media bypass in Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md).</span></span>
  
## <a name="enable-media-bypass"></a><span data-ttu-id="c6a9a-109">Habilitar el desvío de medios</span><span class="sxs-lookup"><span data-stu-id="c6a9a-109">Enable media bypass</span></span>

<span data-ttu-id="c6a9a-110">Para habilitar la omisión de medios, debe configurar el nombre DNS del servicio Web de omisión de medios y activar la omisión de medios en la configuración del espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="c6a9a-110">To enable media bypass, you must configure the DNS name of the media bypass web service and turn on media bypass in the tenant configuration.</span></span> <span data-ttu-id="c6a9a-111">El servicio Web de omisión de medios se implementa automáticamente en cada servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="c6a9a-111">The media bypass web service deploys automatically on every Mediation Server.</span></span> <span data-ttu-id="c6a9a-112">Un administrador de inquilinos debe elegir un nombre para un servicio de voz híbrida (sitio) y este nombre debe pertenecer a un dominio SIP registrado para la voz híbrida.</span><span class="sxs-lookup"><span data-stu-id="c6a9a-112">A tenant administrator must pick a name for a hybrid voice service (site), and this name should be from a SIP domain registered for hybrid voice.</span></span> <span data-ttu-id="c6a9a-113">El nombre del servicio debe ser el mismo en todos los dispositivos de Cloud Connector y en todos los sitios RTC, independientemente de la ubicación del cliente.</span><span class="sxs-lookup"><span data-stu-id="c6a9a-113">The service name should be the same across all Cloud Connector appliances and all PSTN sites regardless of the client location.</span></span> <span data-ttu-id="c6a9a-114">El servicio web solo debe estar disponible internamente en la red.</span><span class="sxs-lookup"><span data-stu-id="c6a9a-114">The web service should only be available internally on the network.</span></span>
  
<span data-ttu-id="c6a9a-115">Un administrador de inquilinos debe configurar un registro A de DNS en el Active Directory de producción interna.</span><span class="sxs-lookup"><span data-stu-id="c6a9a-115">A tenant administrator must configure a DNS A record in the internal production Active Directory.</span></span> <span data-ttu-id="c6a9a-116">Si tiene un entorno de varios sitios complejo, vea el ejemplo en el ejemplo [: registros DNS del sitio web de omisión de medios en entornos complejos de varios sitios](deploy-media-bypass-in-cloud-connector.md#Example).</span><span class="sxs-lookup"><span data-stu-id="c6a9a-116">If you have a complex multi-site environment, see the example in [Example: media bypass web site DNS records in complex multi-site environments](deploy-media-bypass-in-cloud-connector.md#Example).</span></span> <span data-ttu-id="c6a9a-117">El registro DNS solo debe resolverse para los clientes de la red interna; no debe resolverse para los clientes de red externos.</span><span class="sxs-lookup"><span data-stu-id="c6a9a-117">The DNS record should only resolve for internal network clients; it should not resolve for external network clients.</span></span>
  
<span data-ttu-id="c6a9a-118">Después de configurar DNS, conéctese a Skype empresarial online mediante PowerShell remoto con credenciales de administrador de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="c6a9a-118">After configuring DNS, connect to Skype for Business Online by using remote PowerShell with Skype for Business Administrator credentials.</span></span> <span data-ttu-id="c6a9a-119">Para obtener más información, consulte [configurar el equipo para Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md) .</span><span class="sxs-lookup"><span data-stu-id="c6a9a-119">For more information, see [Set up your computer for Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md) .</span></span>
  
<span data-ttu-id="c6a9a-120">En la sesión de PowerShell, escriba los siguientes comandos para habilitar la omisión de medios:</span><span class="sxs-lookup"><span data-stu-id="c6a9a-120">In the PowerShell session, enter the following commands to enable media bypass:</span></span>
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
$mediabypass = New-CsNetworkMediaBypassConfiguration -AlwaysBypass $true -Enabled $true
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

<span data-ttu-id="c6a9a-121">La habilitación de la omisión de medios es un proceso de dos pasos.</span><span class="sxs-lookup"><span data-stu-id="c6a9a-121">Enabling media bypass is a two-step process.</span></span> <span data-ttu-id="c6a9a-122">El cmdlet New-CsNetworkMedia no guarda inmediatamente la nueva configuración; solo crea la configuración en la memoria.</span><span class="sxs-lookup"><span data-stu-id="c6a9a-122">The New-CsNetworkMedia cmdlet does not immediately save the new configuration; it only creates the settings in memory.</span></span> <span data-ttu-id="c6a9a-123">El objeto creado por este cmdlet se debe guardar en una variable y, a continuación, asignarse a la propiedad MediaBypassSettings de la configuración de red.</span><span class="sxs-lookup"><span data-stu-id="c6a9a-123">The object created by this cmdlet must be saved to a variable, and then assigned to the MediaBypassSettings property of the network configuration.</span></span> <span data-ttu-id="c6a9a-124">Para obtener más información, consulte [ejemplo: registros DNS del sitio web de omisión de medios en entornos complejos de varios sitios](deploy-media-bypass-in-cloud-connector.md#Example).</span><span class="sxs-lookup"><span data-stu-id="c6a9a-124">For more information, see [Example: media bypass web site DNS records in complex multi-site environments](deploy-media-bypass-in-cloud-connector.md#Example).</span></span>
  
<span data-ttu-id="c6a9a-125">La replicación entre los componentes locales y en línea puede tardar hasta 24 horas, por lo que Microsoft recomienda que ejecute los comandos necesarios antes de habilitar a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="c6a9a-125">The replication between the on-premises and online components can take up to 24 hours, so Microsoft recommends that you run the necessary commands before enabling users.</span></span>
  
## <a name="confirm-media-bypass-settings"></a><span data-ttu-id="c6a9a-126">Confirmar la configuración de omisión de medios</span><span class="sxs-lookup"><span data-stu-id="c6a9a-126">Confirm media bypass settings</span></span>

<span data-ttu-id="c6a9a-127">Puede comprobar la configuración de la omisión de medios de la siguiente manera.</span><span class="sxs-lookup"><span data-stu-id="c6a9a-127">You can check the media bypass settings as follows.</span></span> 
  
<span data-ttu-id="c6a9a-128">Para comprobar la replicación en línea en el grupo de inquilinos, ejecute el siguiente comando en el PowerShell remoto:</span><span class="sxs-lookup"><span data-stu-id="c6a9a-128">To check online replication to your tenant pool, run the following command in remote PowerShell:</span></span>
  
```powershell
Get-CsTenantHybridConfiguration -LocalStore
Get-CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="c6a9a-129">Para comprobar la replicación local, conéctese a los servidores de mediación de Cloud Connector, ejecute el siguiente comando en PowerShell y confirme que Enabled = true y AlwaysBypass = true</span><span class="sxs-lookup"><span data-stu-id="c6a9a-129">To check the on-premises replication, connect to the Cloud Connector Mediation servers, run the following command in PowerShell, and confirm that Enabled=True and AlwaysBypass=True</span></span>
  
```powershell
Get-CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="c6a9a-130">Para comprobar la configuración del cliente, cierre la sesión del cliente de Skype empresarial, vuelva a iniciar sesión y confirme que el cliente haya recibido la dirección URL del servicio de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="c6a9a-130">To check the client settings, sign out of the Skype for Business client, sign back in, and confirm that the client has received the service URL as follows:</span></span>
  
1. <span data-ttu-id="c6a9a-131">Abrir%appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog.</span><span class="sxs-lookup"><span data-stu-id="c6a9a-131">Open %appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog.</span></span> 
    
2. <span data-ttu-id="c6a9a-132">Busque hybridconfigserviceinternalurl y confirme que la dirección URL coincida con la que ha definido.</span><span class="sxs-lookup"><span data-stu-id="c6a9a-132">Search for hybridconfigserviceinternalurl and confirm the URL matches the one you defined.</span></span>
    
## <a name="change-media-bypass-parameters"></a><span data-ttu-id="c6a9a-133">Cambiar los parámetros de omisión de medios</span><span class="sxs-lookup"><span data-stu-id="c6a9a-133">Change media bypass parameters</span></span>

<span data-ttu-id="c6a9a-134">Los administradores de espacios empresariales pueden cambiar el nombre DNS del servicio Web mediante la ejecución del siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="c6a9a-134">Tenant administrators are able to change the DNS name of the web service by running the following cmdlet:</span></span>
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
```

> [!IMPORTANT]
> <span data-ttu-id="c6a9a-135">Los clientes tienen que cerrar sesión e iniciar sesión para obtener el nuevo nombre del servicio y reconocer el cambio.</span><span class="sxs-lookup"><span data-stu-id="c6a9a-135">Clients need to sign out and sign in to get the new service name and recognize the change.</span></span> 
  
## <a name="temporarily-disable-media-bypass"></a><span data-ttu-id="c6a9a-136">Deshabilitar temporalmente el desvío de medios</span><span class="sxs-lookup"><span data-stu-id="c6a9a-136">Temporarily disable media bypass</span></span>

<span data-ttu-id="c6a9a-137">Este escenario puede ser útil para solucionar problemas o realizar el mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="c6a9a-137">This scenario might be useful for troubleshooting or maintenance.</span></span> <span data-ttu-id="c6a9a-138">Para deshabilitar el servicio, ejecute los cmdlets siguientes:</span><span class="sxs-lookup"><span data-stu-id="c6a9a-138">To disable the service, run the following cmdlets:</span></span>
  
```powershell
$mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

<span data-ttu-id="c6a9a-139">Tras realizar el cambio, los cambios podrían tardar algún tiempo en replicarse a todos los conectores en la nube.</span><span class="sxs-lookup"><span data-stu-id="c6a9a-139">After making the change, it could take some time for changes to replicate to all Cloud Connectors.</span></span> <span data-ttu-id="c6a9a-140">Para comprobar el estado de la replicación, ejecute el siguiente cmdlet en PowerShell en los servidores de mediación de Cloud Connector:</span><span class="sxs-lookup"><span data-stu-id="c6a9a-140">To check the status of replication, run the following cmdlet in PowerShell on Cloud Connector Mediation servers:</span></span> 
  
```powershell
Get- CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="c6a9a-141">Una vez que se replican los cambios, el servicio Web en el servidor de mediación iniciará el rechazo de solicitudes de cliente para el servicio de omisión de medios.</span><span class="sxs-lookup"><span data-stu-id="c6a9a-141">After the changes replicate, the web service on the Mediation Server will start rejecting client requests for the media bypass service.</span></span>
  
## <a name="disable-media-bypass-permanently"></a><span data-ttu-id="c6a9a-142">Deshabilitar la omisión de medios de forma permanente</span><span class="sxs-lookup"><span data-stu-id="c6a9a-142">Disable media bypass permanently</span></span>

<span data-ttu-id="c6a9a-143">Para deshabilitar permanentemente la omisión de medios, un administrador de inquilinos debe ejecutar los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="c6a9a-143">To permanently disable media bypass, a tenant administrator needs to run the following commands:</span></span> 
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl  $null
    $mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false 
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass 
```

<span data-ttu-id="c6a9a-144">Un administrador también tendrá que quitar las direcciones web de la omisión de medios de los servidores DNS internos.</span><span class="sxs-lookup"><span data-stu-id="c6a9a-144">An administrator will also need to remove the web addresses for media bypass from internal DNS servers.</span></span> <span data-ttu-id="c6a9a-145">Tras realizar el cambio, los cambios podrían tardar algún tiempo en replicarse a todos los dispositivos de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="c6a9a-145">After making the change, it could take some time for changes to replicate to all Cloud Connector appliances.</span></span> 
  
## <a name="example-media-bypass-web-site-dns-records-in-complex-multi-site-environments"></a><span data-ttu-id="c6a9a-146">Ejemplo: registros DNS del sitio web de omisión de medios en entornos complejos de varios sitios</span><span class="sxs-lookup"><span data-stu-id="c6a9a-146">Example: media bypass web site DNS records in complex multi-site environments</span></span>
<span data-ttu-id="c6a9a-147"><a name="Example"> </a></span><span class="sxs-lookup"><span data-stu-id="c6a9a-147"><a name="Example"> </a></span></span>

<span data-ttu-id="c6a9a-148">Los clientes recibirán la dirección web del servicio Web de omisión de medios de un servidor DNS interno.</span><span class="sxs-lookup"><span data-stu-id="c6a9a-148">Clients will receive the web address of the media bypass web service from an internal DNS server.</span></span> <span data-ttu-id="c6a9a-149">El nombre del servicio Web será el mismo en todos los equipos de Cloud Connector y los sitios RTC de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="c6a9a-149">The name of the web service will be the same across all Cloud Connector appliances and Cloud Connector PSTN sites.</span></span> <span data-ttu-id="c6a9a-150">En un entorno complejo con varios sitios, se recomienda usar la Directiva DNS de Windows 2016 para la administración de tráfico basada en la ubicación geográfica, de modo que los clientes se puedan redirigir al servicio Web local de su red.</span><span class="sxs-lookup"><span data-stu-id="c6a9a-150">In a complex multi-site environment, we recommend using the Windows 2016 DNS Policy for Geo-Location Based Traffic Management, so clients can be redirected to the web service which is local for their network.</span></span> 
  
<span data-ttu-id="c6a9a-151">Para obtener más información sobre las directivas DNS de Windows 2016, consulte [usar la Directiva DNS para la administración geográfica del tráfico basado en servidores principales](https://docs.microsoft.com/windows-server/networking/dns/deploy/primary-geo-location).</span><span class="sxs-lookup"><span data-stu-id="c6a9a-151">Fore more information about Windows 2016 DNS Policies, see [Use DNS Policy for Geo-Location Based Traffic Management with Primary Servers](https://docs.microsoft.com/windows-server/networking/dns/deploy/primary-geo-location).</span></span>
  
<span data-ttu-id="c6a9a-152">El siguiente es un ejemplo de configuración para una empresa con varios sitios que usan la Directiva DNS de Windows 2016 para la administración de tráfico basada en la ubicación geográfica.</span><span class="sxs-lookup"><span data-stu-id="c6a9a-152">The following is an example of configuration for a company with several sites using Windows 2016 DNS Policy for Geo-Location Based Traffic Management.</span></span>
  
<span data-ttu-id="c6a9a-153">El nombre del servicio de omisión es "hybridvoice.adatum.biz".</span><span class="sxs-lookup"><span data-stu-id="c6a9a-153">The name for the bypass service is 'hybridvoice.adatum.biz'.</span></span>
  
<span data-ttu-id="c6a9a-154">El sitio de Amsterdam tiene cuatro dispositivos de Cloud Connector implementados con las siguientes direcciones IP del servidor de mediación:</span><span class="sxs-lookup"><span data-stu-id="c6a9a-154">The site in Amsterdam has four Cloud Connector appliances deployed with the following Mediation Server IP addresses:</span></span>
  
- <span data-ttu-id="c6a9a-155">192.168.1.45</span><span class="sxs-lookup"><span data-stu-id="c6a9a-155">192.168.1.45</span></span>
    
- <span data-ttu-id="c6a9a-156">192.168.1.46</span><span class="sxs-lookup"><span data-stu-id="c6a9a-156">192.168.1.46</span></span>
    
- <span data-ttu-id="c6a9a-157">192.168.1.47</span><span class="sxs-lookup"><span data-stu-id="c6a9a-157">192.168.1.47</span></span>
    
- <span data-ttu-id="c6a9a-158">192.168.1.48</span><span class="sxs-lookup"><span data-stu-id="c6a9a-158">192.168.1.48</span></span>
    
<span data-ttu-id="c6a9a-159">El sitio de Seattle tiene tres dispositivos de Cloud Connector implementados con las siguientes direcciones IP del servidor de mediación:</span><span class="sxs-lookup"><span data-stu-id="c6a9a-159">The site in Seattle has three Cloud Connector appliances deployed with the following Mediation Server IP addresses:</span></span>
  
- <span data-ttu-id="c6a9a-160">10.10.1.8</span><span class="sxs-lookup"><span data-stu-id="c6a9a-160">10.10.1.8</span></span>
    
- <span data-ttu-id="c6a9a-161">10.10.1.9</span><span class="sxs-lookup"><span data-stu-id="c6a9a-161">10.10.1.9</span></span>
    
- <span data-ttu-id="c6a9a-162">10.10.1.10</span><span class="sxs-lookup"><span data-stu-id="c6a9a-162">10.10.1.10</span></span>
    
<span data-ttu-id="c6a9a-163">Mediante la administración geográfica del tráfico basada en la ubicación geográfica, los servidores DNS se configurarían de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="c6a9a-163">Using Geo-Location Based Traffic Management, the DNS servers would be configured as follows:</span></span>
  
1. <span data-ttu-id="c6a9a-164">Cree subredes de cliente DNS para las subredes de Amsterdam y Seattle.</span><span class="sxs-lookup"><span data-stu-id="c6a9a-164">Create DNS Client Subnets for both the Amsterdam and Seattle subnets.</span></span>
    
2. <span data-ttu-id="c6a9a-165">Cree ámbitos de zona DNS para adatum.biz tanto para Ámsterdam como para Seattle.</span><span class="sxs-lookup"><span data-stu-id="c6a9a-165">Create DNS Zone Scopes for adatum.biz for both Amsterdam and Seattle.</span></span>
    
3. <span data-ttu-id="c6a9a-166">Crear registros DNS en cada ámbito de zona DNS.</span><span class="sxs-lookup"><span data-stu-id="c6a9a-166">Create DNS records in each DNS Zone Scope.</span></span>
    
    <span data-ttu-id="c6a9a-167">Ámsterdam</span><span class="sxs-lookup"><span data-stu-id="c6a9a-167">Amsterdam</span></span>
    
   - <span data-ttu-id="c6a9a-168">Escriba A;</span><span class="sxs-lookup"><span data-stu-id="c6a9a-168">Type A;</span></span>
    
   - <span data-ttu-id="c6a9a-169">Nombre: hybridvoice en la zona DNS adatum.biz</span><span class="sxs-lookup"><span data-stu-id="c6a9a-169">Name : hybridvoice in the adatum.biz DNS zone</span></span>
    
   - <span data-ttu-id="c6a9a-170">Destino: 192.168.1.45</span><span class="sxs-lookup"><span data-stu-id="c6a9a-170">Target: 192.168.1.45</span></span>
    
     <span data-ttu-id="c6a9a-171">Crear registros adicionales para otros servidores de mediación</span><span class="sxs-lookup"><span data-stu-id="c6a9a-171">Create additional records for additional mediation servers</span></span>
    
   - <span data-ttu-id="c6a9a-172">192.168.1.46</span><span class="sxs-lookup"><span data-stu-id="c6a9a-172">192.168.1.46</span></span>
    
   - <span data-ttu-id="c6a9a-173">192.168.1.47</span><span class="sxs-lookup"><span data-stu-id="c6a9a-173">192.168.1.47</span></span>
    
   - <span data-ttu-id="c6a9a-174">192.168.1.48</span><span class="sxs-lookup"><span data-stu-id="c6a9a-174">192.168.1.48</span></span>
    
     <span data-ttu-id="c6a9a-175">Quito</span><span class="sxs-lookup"><span data-stu-id="c6a9a-175">Seattle</span></span>
    
   - <span data-ttu-id="c6a9a-176">Escriba un</span><span class="sxs-lookup"><span data-stu-id="c6a9a-176">Type A</span></span>
    
   - <span data-ttu-id="c6a9a-177">Nombre: hybridvoice en la zona DNS adatum.biz</span><span class="sxs-lookup"><span data-stu-id="c6a9a-177">Name : hybridvoice in adatum.biz DNS zone</span></span>
    
   - <span data-ttu-id="c6a9a-178">Destino: 10.10.1.8</span><span class="sxs-lookup"><span data-stu-id="c6a9a-178">Target: 10.10.1.8</span></span>
    
     <span data-ttu-id="c6a9a-179">Crear registros adicionales para otros servidores de mediación</span><span class="sxs-lookup"><span data-stu-id="c6a9a-179">Create additional records for additional mediation servers</span></span>
    
   - <span data-ttu-id="c6a9a-180">10.10.1.9</span><span class="sxs-lookup"><span data-stu-id="c6a9a-180">10.10.1.9</span></span>
    
   - <span data-ttu-id="c6a9a-181">10.10.1.10</span><span class="sxs-lookup"><span data-stu-id="c6a9a-181">10.10.1.10</span></span>
    
4. <span data-ttu-id="c6a9a-182">Cree la Directiva DNS que conecta las subredes del cliente con los ámbitos de zona apropiados para garantizar la resolución DNS deseada.</span><span class="sxs-lookup"><span data-stu-id="c6a9a-182">Create the DNS policy that connects the client subnets to the appropriate zone scopes to ensure desired DNS resolution.</span></span>
    
<span data-ttu-id="c6a9a-183">En este momento, los clientes que realizan consultas DNS desde la subred de Amsterdam para hybridvoice.adatum.biz devolverán las direcciones 192.168.1.45, 192.168.1.46, 192.168.1.47 y 192.168.1.48, mientras que los clientes que tengan el mismo formato de consulta Seattle devolverán 10.10.1.8, 10.10.1.9 y 10.10.1.10.</span><span class="sxs-lookup"><span data-stu-id="c6a9a-183">At this point, clients making DNS queries from the Amsterdam subnet for hybridvoice.adatum.biz will return the 192.168.1.45, 192.168.1.46, 192.168.1.47 and 192.168.1.48 addresses, while clients making the same query form Seattle will return 10.10.1.8, 10.10.1.9 and 10.10.1.10.</span></span>

> [!NOTE]
> <span data-ttu-id="c6a9a-184">Si el dispositivo CCE no parece que esté recibiendo la configuración actualizada, compruebe si el dispositivo puede ponerse en contacto con el inquilino a través de PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="c6a9a-184">If the CCE appliance doesn't seem to be getting the updated settings, check to see if the appliance is able to contact the tenant via remote PowerShell.</span></span> <span data-ttu-id="c6a9a-185">Puede usar PowerShell remoto para comprobar el estado del dispositivo con get-CsHybridPSTNAppliance o usar PowerShell en el host CCE para comprobar el estado con get-CcApplianceStatus.</span><span class="sxs-lookup"><span data-stu-id="c6a9a-185">You can use Remote PowerShell to check appliance status with Get-CsHybridPSTNAppliance or use PowerShell on the CCE host to check status with Get-CcApplianceStatus.</span></span>

  
## <a name="see-also"></a><span data-ttu-id="c6a9a-186">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="c6a9a-186">See also</span></span>
<span data-ttu-id="c6a9a-187"><a name="Example"> </a></span><span class="sxs-lookup"><span data-stu-id="c6a9a-187"><a name="Example"> </a></span></span>

[<span data-ttu-id="c6a9a-188">Plan para la omisión de medios en Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="c6a9a-188">Plan for media bypass in Cloud Connector Edition</span></span>](plan-for-media-bypass-in-cloud-connector-edition.md)
