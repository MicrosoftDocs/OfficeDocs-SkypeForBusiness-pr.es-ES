---
title: Implementar el desvío de medios en la nube conector Edition
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0ebba3a4-6124-434c-84aa-32b1cc3345bc
description: Lea este tema para obtener información acerca de los pasos para implementar el desvío de medios con la nube conector Edition versión 2.0 y versiones posterior.
ms.openlocfilehash: 0d147cbd1f6497757aa73e380ebeca0c03f1de7b
ms.sourcegitcommit: a5b8b0a1e5ae5eb718e296ca6df6687368ee9174
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2018
ms.locfileid: "19505198"
---
# <a name="deploy-media-bypass-in-cloud-connector-edition"></a><span data-ttu-id="5a0db-103">Implementar el desvío de medios en la nube conector Edition</span><span class="sxs-lookup"><span data-stu-id="5a0db-103">Deploy media bypass in Cloud Connector Edition</span></span>
 
<span data-ttu-id="5a0db-104">Lea este tema para obtener información acerca de los pasos para implementar el desvío de medios con la nube conector Edition versión 2.0 y versiones posterior.</span><span class="sxs-lookup"><span data-stu-id="5a0db-104">Read this topic to learn about steps to deploy media bypass with Cloud Connector Edition version 2.0 and later.</span></span> 
  
<span data-ttu-id="5a0db-105">Desvío de medios permite que un cliente enviar medios directamente en el próximo salto pública red de telefónica conmutada (RTC): una puerta de enlace o el controlador de borde de sesión (SBC) — y eliminar el componente de edición de conector en la nube desde la ruta de acceso de medios.</span><span class="sxs-lookup"><span data-stu-id="5a0db-105">Media bypass allows a client to send media directly to the Public Switched Telephone Network (PSTN) next hop—a gateway or Session Border Controller (SBC)—and eliminate the Cloud Connector Edition component from the media path.</span></span> <span data-ttu-id="5a0db-106">Vea también [Plan para los medios de desvío en la nube conector Edition](plan-for-media-bypass-in-cloud-connector-edition.md).</span><span class="sxs-lookup"><span data-stu-id="5a0db-106">See also [Plan for media bypass in Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md).</span></span>
  
## <a name="enable-media-bypass"></a><span data-ttu-id="5a0db-107">Habilitar omisión de medios</span><span class="sxs-lookup"><span data-stu-id="5a0db-107">Enable media bypass</span></span>

<span data-ttu-id="5a0db-108">Para habilitar el desvío de medios, debe configurar el nombre DNS del servicio web de desvío de medios y activar el desvío de medios en la configuración del inquilino.</span><span class="sxs-lookup"><span data-stu-id="5a0db-108">To enable media bypass, you must configure the DNS name of the media bypass web service and turn on media bypass in the tenant configuration.</span></span> <span data-ttu-id="5a0db-109">El servicio web de desvío de medios se implementa automáticamente en cada servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="5a0db-109">The media bypass web service deploys automatically on every Mediation Server.</span></span> <span data-ttu-id="5a0db-110">Un administrador de inquilinos debe elegir un nombre para un servicio de voz híbrida (sitio) y este nombre debe ser de un dominio SIP registrado para voz híbrida.</span><span class="sxs-lookup"><span data-stu-id="5a0db-110">A tenant administrator must pick a name for a hybrid voice service (site), and this name should be from a SIP domain registered for hybrid voice.</span></span> <span data-ttu-id="5a0db-111">El nombre del servicio debe ser el mismo en todos los dispositivos de conector en la nube y todos los sitios de RTC, independientemente de la ubicación del cliente.</span><span class="sxs-lookup"><span data-stu-id="5a0db-111">The service name should be the same across all Cloud Connector appliances and all PSTN sites regardless of the client location.</span></span> <span data-ttu-id="5a0db-112">El servicio web sólo debe estar disponible internamente en la red.</span><span class="sxs-lookup"><span data-stu-id="5a0db-112">The web service should only be available internally on the network.</span></span>
  
<span data-ttu-id="5a0db-113">Un administrador de inquilinos debe configurar un registro A DNS en Active Directory de producción interna.</span><span class="sxs-lookup"><span data-stu-id="5a0db-113">A tenant administrator must configure a DNS A record in the internal production Active Directory.</span></span> <span data-ttu-id="5a0db-114">Si tiene un entorno complejo de varios sitio, vea el ejemplo en [ejemplo: registros DNS del sitio web en entornos de varios sitios complejos de desvío de medios](deploy-media-bypass-in-cloud-connector.md#Example).</span><span class="sxs-lookup"><span data-stu-id="5a0db-114">If you have a complex multi-site environment, see the example in [Example: media bypass web site DNS records in complex multi-site environments](deploy-media-bypass-in-cloud-connector.md#Example).</span></span> <span data-ttu-id="5a0db-115">Sólo debe resolver el registro de DNS para los clientes de la red interna; no se debe resolver para los clientes de la red externa.</span><span class="sxs-lookup"><span data-stu-id="5a0db-115">The DNS record should only resolve for internal network clients; it should not resolve for external network clients.</span></span>
  
<span data-ttu-id="5a0db-116">Después de configurar DNS, conectarse a Skype para profesionales Online mediante PowerShell remoto con Skype las credenciales de administrador empresarial.</span><span class="sxs-lookup"><span data-stu-id="5a0db-116">After configuring DNS, connect to Skype for Business Online by using remote PowerShell with Skype for Business Administrator credentials.</span></span> <span data-ttu-id="5a0db-117">Para obtener más información, consulte [Connecting to Skype para profesionales en línea mediante Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="5a0db-117">For more information, see [Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>
  
<span data-ttu-id="5a0db-118">En la sesión de PowerShell, introduzca los siguientes comandos para habilitar la omisión de medios:</span><span class="sxs-lookup"><span data-stu-id="5a0db-118">In the PowerShell session, enter the following commands to enable media bypass:</span></span>
  
```
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
$mediabypass = New-CsNetworkMediaBypassConfiguration -AlwaysBypass $true -Enabled $true
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

<span data-ttu-id="5a0db-119">Habilitar desvío de medios es un proceso de dos pasos.</span><span class="sxs-lookup"><span data-stu-id="5a0db-119">Enabling media bypass is a two-step process.</span></span> <span data-ttu-id="5a0db-120">El cmdlet New-CsNetworkMedia no guardar inmediatamente la nueva configuración; sólo se crea la configuración en la memoria.</span><span class="sxs-lookup"><span data-stu-id="5a0db-120">The New-CsNetworkMedia cmdlet does not immediately save the new configuration; it only creates the settings in memory.</span></span> <span data-ttu-id="5a0db-121">El objeto creado por este cmdlet debe ser guardado en una variable y, a continuación, se asigna a la propiedad MediaBypassSettings de la configuración de red.</span><span class="sxs-lookup"><span data-stu-id="5a0db-121">The object created by this cmdlet must be saved to a variable, and then assigned to the MediaBypassSettings property of the network configuration.</span></span> <span data-ttu-id="5a0db-122">Para obtener más información, vea [ejemplo: registros DNS del sitio web en entornos de varios sitios complejos de desvío de medios](deploy-media-bypass-in-cloud-connector.md#Example).</span><span class="sxs-lookup"><span data-stu-id="5a0db-122">For more information, see [Example: media bypass web site DNS records in complex multi-site environments](deploy-media-bypass-in-cloud-connector.md#Example).</span></span>
  
<span data-ttu-id="5a0db-123">La replicación entre los componentes en línea y local puede tardar hasta 24 horas, por lo que Microsoft recomienda que ejecutar los comandos necesarios antes de habilitar a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="5a0db-123">The replication between the on-premises and online components can take up to 24 hours, so Microsoft recommends that you run the necessary commands before enabling users.</span></span>
  
## <a name="confirm-media-bypass-settings"></a><span data-ttu-id="5a0db-124">Confirmar la configuración de la omisión de medios</span><span class="sxs-lookup"><span data-stu-id="5a0db-124">Confirm media bypass settings</span></span>

<span data-ttu-id="5a0db-125">La configuración de la omisión de medios se puede comprobar de la siguiente manera. </span><span class="sxs-lookup"><span data-stu-id="5a0db-125">You can check the media bypass settings as follows.</span></span> 
  
<span data-ttu-id="5a0db-126">Para comprobar la replicación en línea al grupo de servidores de inquilinos, ejecute el siguiente comando en PowerShell remoto:</span><span class="sxs-lookup"><span data-stu-id="5a0db-126">To check online replication to your tenant pool, run the following command in remote PowerShell:</span></span>
  
```
Get-CsTenantHybridConfiguration -LocalStore
Get-CsNetworkConfiguration -LocalStore

```

<span data-ttu-id="5a0db-127">Para comprobar la replicación local, conectarse a los servidores de mediación de conector en la nube, ejecute el siguiente comando en PowerShell y confirme que Enabled = True y AlwaysBypass = True</span><span class="sxs-lookup"><span data-stu-id="5a0db-127">To check the on-premises replication, connect to the Cloud Connector Mediation servers, run the following command in PowerShell, and confirm that Enabled=True and AlwaysBypass=True</span></span>
  
```
Get-CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="5a0db-128">Para comprobar la configuración del cliente, desconectarse de la Skype para clientes empresariales, vuelva a iniciarla y confirme que el cliente ha recibido la dirección URL del servicio como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="5a0db-128">To check the client settings, sign out of the Skype for Business client, sign back in, and confirm that the client has received the service URL as follows:</span></span>
  
1. <span data-ttu-id="5a0db-129">Abra %appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog. </span><span class="sxs-lookup"><span data-stu-id="5a0db-129">Open %appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog.</span></span> 
    
2. <span data-ttu-id="5a0db-130">Buscar hybridconfigserviceinternalurl y confirme la dirección URL coincide con el que haya definido.</span><span class="sxs-lookup"><span data-stu-id="5a0db-130">Search for hybridconfigserviceinternalurl and confirm the URL matches the one you defined.</span></span>
    
## <a name="change-media-bypass-parameters"></a><span data-ttu-id="5a0db-131">Cambiar los parámetros de la omisión de medios</span><span class="sxs-lookup"><span data-stu-id="5a0db-131">Change media bypass parameters</span></span>

<span data-ttu-id="5a0db-132">Los administradores de inquilinos pueden modificar el nombre DNS del servicio web mediante la ejecución del siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="5a0db-132">Tenant administrators are able to change the DNS name of the web service by running the following cmdlet:</span></span>
  
```
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
```

> [!IMPORTANT]
> <span data-ttu-id="5a0db-133">Los clientes tienen que cerrar la sesión y volver a iniciarla para obtener el nombre nuevo del servicio y reconocer el cambio. </span><span class="sxs-lookup"><span data-stu-id="5a0db-133">Clients need to sign out and sign in to get the new service name and recognize the change.</span></span> 
  
## <a name="temporarily-disable-media-bypass"></a><span data-ttu-id="5a0db-134">Deshabilitar temporalmente la omisión de medios</span><span class="sxs-lookup"><span data-stu-id="5a0db-134">Temporarily disable media bypass</span></span>

<span data-ttu-id="5a0db-p106">Este escenario puede ser útil para solucionar problemas o como mantenimiento. Para deshabilitar el servicio, ejecute los siguientes cmdlet:</span><span class="sxs-lookup"><span data-stu-id="5a0db-p106">This scenario might be useful for troubleshooting or maintenance. To disable the service, run the following cmdlets:</span></span>
  
```
$mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

<span data-ttu-id="5a0db-137">Después de realizar el cambio, podría tardar algún tiempo para que los cambios en replicarse en todos los conectores de la nube.</span><span class="sxs-lookup"><span data-stu-id="5a0db-137">After making the change, it could take some time for changes to replicate to all Cloud Connectors.</span></span> <span data-ttu-id="5a0db-138">Para comprobar el estado de replicación, ejecute el siguiente cmdlet de PowerShell en los servidores de mediación de conector en la nube:</span><span class="sxs-lookup"><span data-stu-id="5a0db-138">To check the status of replication, run the following cmdlet in PowerShell on Cloud Connector Mediation servers:</span></span> 
  
```
Get- CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="5a0db-139">Una vez que se repliquen los cambios, el servicio web del servidor de mediación comenzará a rechazar las solicitudes del cliente para el servicio de omisión de medios.</span><span class="sxs-lookup"><span data-stu-id="5a0db-139">After the changes replicate, the web service on the Mediation Server will start rejecting client requests for the media bypass service.</span></span>
  
## <a name="disable-media-bypass-permanently"></a><span data-ttu-id="5a0db-140">Deshabilitar permanentemente la omisión de medios</span><span class="sxs-lookup"><span data-stu-id="5a0db-140">Disable media bypass permanently</span></span>

<span data-ttu-id="5a0db-141">Para deshabilitar permanentemente la omisión de medios, un administrador de inquilinos debe ejecutar los siguientes comandos: </span><span class="sxs-lookup"><span data-stu-id="5a0db-141">To permanently disable media bypass, a tenant administrator needs to run the following commands:</span></span> 
  
```
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl  $null
    $mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false 
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass 
```

<span data-ttu-id="5a0db-142">Un administrador también necesitará quitar las direcciones de web para el desvío de medios de servidores DNS internos.</span><span class="sxs-lookup"><span data-stu-id="5a0db-142">An administrator will also need to remove the web addresses for media bypass from internal DNS servers.</span></span> <span data-ttu-id="5a0db-143">Después de realizar el cambio, podría tardar algún tiempo para que los cambios en replicarse a todos los dispositivos de conector en la nube.</span><span class="sxs-lookup"><span data-stu-id="5a0db-143">After making the change, it could take some time for changes to replicate to all Cloud Connector appliances.</span></span> 
  
## <a name="example-media-bypass-web-site-dns-records-in-complex-multi-site-environments"></a><span data-ttu-id="5a0db-144">Ejemplo: Los registros DNS del sitio web de omisión de medios en entornos complejos de varios sitios</span><span class="sxs-lookup"><span data-stu-id="5a0db-144">Example: media bypass web site DNS records in complex multi-site environments</span></span>
<span data-ttu-id="5a0db-145"><a name="Example"> </a></span><span class="sxs-lookup"><span data-stu-id="5a0db-145"></span></span>

<span data-ttu-id="5a0db-146">Los clientes recibirán la dirección web del servicio web de desvío de medios desde un servidor DNS interno.</span><span class="sxs-lookup"><span data-stu-id="5a0db-146">Clients will receive the web address of the media bypass web service from an internal DNS server.</span></span> <span data-ttu-id="5a0db-147">El nombre del servicio web será el mismo en todos los dispositivos de conector en la nube y sitios de RTC de conector en la nube.</span><span class="sxs-lookup"><span data-stu-id="5a0db-147">The name of the web service will be the same across all Cloud Connector appliances and Cloud Connector PSTN sites.</span></span> <span data-ttu-id="5a0db-148">En un entorno complejo de varios sitio, se recomienda usar la directiva de DNS de 2016 de Windows para la administración de tráfico en función de ubicación geográfica, por lo que los clientes pueden redirigirse al servicio web que es local para su red.</span><span class="sxs-lookup"><span data-stu-id="5a0db-148">In a complex multi-site environment, we recommend using the Windows 2016 DNS Policy for Geo-Location Based Traffic Management, so clients can be redirected to the web service which is local for their network.</span></span> 
  
<span data-ttu-id="5a0db-149">Para obtener más información acerca de las directivas de DNS de Windows 2016, vea [Use la directiva de DNS para la administración de tráfico en función de ubicación geográfica con servidores principales](https://docs.microsoft.com/en-us/windows-server/networking/dns/deploy/primary-geo-location).</span><span class="sxs-lookup"><span data-stu-id="5a0db-149">Fore more information about Windows 2016 DNS Policies, see [Use DNS Policy for Geo-Location Based Traffic Management with Primary Servers](https://docs.microsoft.com/en-us/windows-server/networking/dns/deploy/primary-geo-location).</span></span>
  
<span data-ttu-id="5a0db-150">A continuación se muestra un ejemplo de configuración para un empresa con varios sitios mediante la directiva DNS de Windows 2016 para la geolocalización basada en la administración del tráfico.</span><span class="sxs-lookup"><span data-stu-id="5a0db-150">The following is an example of configuration for a company with several sites using Windows 2016 DNS Policy for Geo-Location Based Traffic Management.</span></span>
  
<span data-ttu-id="5a0db-151">El nombre para el servicio de desvío es 'hybridvoice.adatum.biz'.</span><span class="sxs-lookup"><span data-stu-id="5a0db-151">The name for the bypass service is 'hybridvoice.adatum.biz'.</span></span>
  
<span data-ttu-id="5a0db-152">El sitio en Ámsterdam tiene cuatro dispositivos de conector en la nube que se implementan con las siguientes direcciones IP de servidor de mediación:</span><span class="sxs-lookup"><span data-stu-id="5a0db-152">The site in Amsterdam has four Cloud Connector appliances deployed with the following Mediation Server IP addresses:</span></span>
  
- <span data-ttu-id="5a0db-153">192.168.1.45</span><span class="sxs-lookup"><span data-stu-id="5a0db-153">192.168.1.45</span></span>
    
- <span data-ttu-id="5a0db-154">192.168.1.46</span><span class="sxs-lookup"><span data-stu-id="5a0db-154">192.168.1.46</span></span>
    
- <span data-ttu-id="5a0db-155">192.168.1.47</span><span class="sxs-lookup"><span data-stu-id="5a0db-155">192.168.1.47</span></span>
    
- <span data-ttu-id="5a0db-156">192.168.1.48</span><span class="sxs-lookup"><span data-stu-id="5a0db-156">192.168.1.48</span></span>
    
<span data-ttu-id="5a0db-157">El sitio de Seattle tiene tres dispositivos de conector en la nube que implementan con las siguientes direcciones IP de servidor de mediación:</span><span class="sxs-lookup"><span data-stu-id="5a0db-157">The site in Seattle has three Cloud Connector appliances deployed with the following Mediation Server IP addresses:</span></span>
  
- <span data-ttu-id="5a0db-158">10.10.1.8</span><span class="sxs-lookup"><span data-stu-id="5a0db-158">10.10.1.8</span></span>
    
- <span data-ttu-id="5a0db-159">10.10.1.9</span><span class="sxs-lookup"><span data-stu-id="5a0db-159">10.10.1.9</span></span>
    
- <span data-ttu-id="5a0db-160">10.10.1.10</span><span class="sxs-lookup"><span data-stu-id="5a0db-160">10.10.1.10</span></span>
    
<span data-ttu-id="5a0db-161">Con la geolocalización basada en la administración del tráfico, los servidores DNS se configurarían del siguiente modo:</span><span class="sxs-lookup"><span data-stu-id="5a0db-161">Using Geo-Location Based Traffic Management, the DNS servers would be configured as follows:</span></span>
  
1. <span data-ttu-id="5a0db-162">Cree subredes de clientes DNS para las subredes de Ámsterdam y Seattle.</span><span class="sxs-lookup"><span data-stu-id="5a0db-162">Create DNS Client Subnets for both the Amsterdam and Seattle subnets.</span></span>
    
2. <span data-ttu-id="5a0db-163">Cree los ámbitos de zona DNS para adatum.biz para Ámsterdam y Seattle.</span><span class="sxs-lookup"><span data-stu-id="5a0db-163">Create DNS Zone Scopes for adatum.biz for both Amsterdam and Seattle.</span></span>
    
3. <span data-ttu-id="5a0db-164">Cree los registros DNS en cada ámbito de zona DNS.</span><span class="sxs-lookup"><span data-stu-id="5a0db-164">Create DNS records in each DNS Zone Scope.</span></span>
    
    <span data-ttu-id="5a0db-165">Ámsterdam</span><span class="sxs-lookup"><span data-stu-id="5a0db-165">Amsterdam</span></span>
    
  - <span data-ttu-id="5a0db-166">Tipo A</span><span class="sxs-lookup"><span data-stu-id="5a0db-166">Type A;</span></span>
    
  - <span data-ttu-id="5a0db-167">Nombre: hybridvoice en la zona DNS adatum.biz</span><span class="sxs-lookup"><span data-stu-id="5a0db-167">Name : hybridvoice in the adatum.biz DNS zone</span></span>
    
  - <span data-ttu-id="5a0db-168">Destino: 192.168.1.45</span><span class="sxs-lookup"><span data-stu-id="5a0db-168">Target: 192.168.1.45</span></span>
    
    <span data-ttu-id="5a0db-169">Cree registros adicionales para los servidores de mediación adicionales</span><span class="sxs-lookup"><span data-stu-id="5a0db-169">Create additional records for additional mediation servers</span></span>
    
  - <span data-ttu-id="5a0db-170">192.168.1.46</span><span class="sxs-lookup"><span data-stu-id="5a0db-170">192.168.1.46</span></span>
    
  - <span data-ttu-id="5a0db-171">192.168.1.47</span><span class="sxs-lookup"><span data-stu-id="5a0db-171">192.168.1.47</span></span>
    
  - <span data-ttu-id="5a0db-172">192.168.1.48</span><span class="sxs-lookup"><span data-stu-id="5a0db-172">192.168.1.48</span></span>
    
    <span data-ttu-id="5a0db-173">Seattle</span><span class="sxs-lookup"><span data-stu-id="5a0db-173">Seattle</span></span>
    
  - <span data-ttu-id="5a0db-174">Tipo A</span><span class="sxs-lookup"><span data-stu-id="5a0db-174">Type A</span></span>
    
  - <span data-ttu-id="5a0db-175">Nombre: hybridvoice en la zona DNS adatum.biz</span><span class="sxs-lookup"><span data-stu-id="5a0db-175">Name : hybridvoice in adatum.biz DNS zone</span></span>
    
  - <span data-ttu-id="5a0db-176">Destino: 10.10.1.8</span><span class="sxs-lookup"><span data-stu-id="5a0db-176">Target: 10.10.1.8</span></span>
    
    <span data-ttu-id="5a0db-177">Cree registros adicionales para los servidores de mediación adicionales</span><span class="sxs-lookup"><span data-stu-id="5a0db-177">Create additional records for additional mediation servers</span></span>
    
  - <span data-ttu-id="5a0db-178">10.10.1.9</span><span class="sxs-lookup"><span data-stu-id="5a0db-178">10.10.1.9</span></span>
    
  - <span data-ttu-id="5a0db-179">10.10.1.10</span><span class="sxs-lookup"><span data-stu-id="5a0db-179">10.10.1.10</span></span>
    
4. <span data-ttu-id="5a0db-180">Cree la directiva DNS que conecta las subredes del cliente con los ámbitos de zona apropiados para garantizar la resolución DNS que desea.</span><span class="sxs-lookup"><span data-stu-id="5a0db-180">Create the DNS policy that connects the client subnets to the appropriate zone scopes to ensure desired DNS resolution.</span></span>
    
<span data-ttu-id="5a0db-181">En este punto, los clientes que hagan consultas de DNS desde la subred de Ámsterdam para hybridvoice.adatum.biz devolverán las direcciones 192.168.1.45, 192.168.1.46, 192.168.1.47 y 192.168.1.48, mientras que los clientes que hagan la misma consulta desde Seattle devolverán 10.10.1.8, 10.10.1.9 y 10.10.1.10.</span><span class="sxs-lookup"><span data-stu-id="5a0db-181">At this point, clients making DNS queries from the Amsterdam subnet for hybridvoice.adatum.biz will return the 192.168.1.45, 192.168.1.46, 192.168.1.47 and 192.168.1.48 addresses, while clients making the same query form Seattle will return 10.10.1.8, 10.10.1.9 and 10.10.1.10.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5a0db-182">Vea también</span><span class="sxs-lookup"><span data-stu-id="5a0db-182">See also</span></span>
<span data-ttu-id="5a0db-183"><a name="Example"> </a></span><span class="sxs-lookup"><span data-stu-id="5a0db-183"></span></span>

[<span data-ttu-id="5a0db-184">Planeación de desvío de medios en la nube conector Edition</span><span class="sxs-lookup"><span data-stu-id="5a0db-184">Plan for media bypass in Cloud Connector Edition</span></span>](plan-for-media-bypass-in-cloud-connector-edition.md)