---
title: Implementar la omisión de medios en nube conector Edition
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Hybrid
ms.assetid: 0ebba3a4-6124-434c-84aa-32b1cc3345bc
description: Lea este tema para conocer los pasos para implementar omisión de medios con conector de nube Edition versión 2.0 y versiones posterior.
ms.openlocfilehash: a9f03d1d83d398a6aa78f90a4741d0010ea50392
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-media-bypass-in-cloud-connector-edition"></a><span data-ttu-id="7ec6f-103">Implementar la omisión de medios en nube conector Edition</span><span class="sxs-lookup"><span data-stu-id="7ec6f-103">Deploy media bypass in Cloud Connector Edition</span></span>
 
<span data-ttu-id="7ec6f-104">Lea este tema para conocer los pasos para implementar omisión de medios con conector de nube Edition versión 2.0 y versiones posterior.</span><span class="sxs-lookup"><span data-stu-id="7ec6f-104">Read this topic to learn about steps to deploy media bypass with Cloud Connector Edition version 2.0 and later.</span></span> 
  
<span data-ttu-id="7ec6f-105">Omisión de medios permite que un cliente envíe medios directamente en el próximo salto de red pública de telefónica conmutada (PSTN), un gateway o un controlador de borde de sesión (SBC) y eliminar el componente de edición de conector de nube desde la ruta de acceso de medios.</span><span class="sxs-lookup"><span data-stu-id="7ec6f-105">Media bypass allows a client to send media directly to the Public Switched Telephone Network (PSTN) next hop—a gateway or Session Border Controller (SBC)—and eliminate the Cloud Connector Edition component from the media path.</span></span> <span data-ttu-id="7ec6f-106">Vea también [Plan para medios de derivación en nube conector Edition](plan-for-media-bypass-in-cloud-connector-edition.md).</span><span class="sxs-lookup"><span data-stu-id="7ec6f-106">See also [Plan for media bypass in Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md).</span></span>
  
## <a name="enable-media-bypass"></a><span data-ttu-id="7ec6f-107">Habilitar omisión de medios</span><span class="sxs-lookup"><span data-stu-id="7ec6f-107">Enable media bypass</span></span>

<span data-ttu-id="7ec6f-108">Para habilitar la omisión de medios, debe configurar el nombre DNS del servicio web de omisión de los medios de comunicación y activar la omisión de medios en la configuración de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="7ec6f-108">To enable media bypass, you must configure the DNS name of the media bypass web service and turn on media bypass in the tenant configuration.</span></span> <span data-ttu-id="7ec6f-109">El servicio web de omisión de medios se despliega automáticamente en cada servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="7ec6f-109">The media bypass web service deploys automatically on every Mediation Server.</span></span> <span data-ttu-id="7ec6f-110">Un administrador de inquilinos debe elegir un nombre para un servicio de voz híbrida (sitio) y este nombre debe ser de un dominio SIP registrado para voz híbrida.</span><span class="sxs-lookup"><span data-stu-id="7ec6f-110">A tenant administrator must pick a name for a hybrid voice service (site), and this name should be from a SIP domain registered for hybrid voice.</span></span> <span data-ttu-id="7ec6f-111">El nombre del servicio debe ser el mismo en todos los dispositivos de conector de nube y todos los sitios PSTN independientemente de la ubicación del cliente.</span><span class="sxs-lookup"><span data-stu-id="7ec6f-111">The service name should be the same across all Cloud Connector appliances and all PSTN sites regardless of the client location.</span></span> <span data-ttu-id="7ec6f-112">El servicio web sólo debe estar disponible internamente en la red.</span><span class="sxs-lookup"><span data-stu-id="7ec6f-112">The web service should only be available internally on the network.</span></span>
  
<span data-ttu-id="7ec6f-113">Un administrador de inquilinos debe configurar un registro A DNS en Active Directory de producción interna.</span><span class="sxs-lookup"><span data-stu-id="7ec6f-113">A tenant administrator must configure a DNS A record in the internal production Active Directory.</span></span> <span data-ttu-id="7ec6f-114">Si tiene un entorno complejo de múltiples sitios, vea el ejemplo en [ejemplo: media omitir registros DNS del sitio web en entornos de múltiples sitios complejos](deploy-media-bypass-in-cloud-connector.md#Example).</span><span class="sxs-lookup"><span data-stu-id="7ec6f-114">If you have a complex multi-site environment, see the example in [Example: media bypass web site DNS records in complex multi-site environments](deploy-media-bypass-in-cloud-connector.md#Example).</span></span> <span data-ttu-id="7ec6f-115">Sólo debe resolver el registro DNS para los clientes de la red interna; no se deben resolver para los clientes de la red externa.</span><span class="sxs-lookup"><span data-stu-id="7ec6f-115">The DNS record should only resolve for internal network clients; it should not resolve for external network clients.</span></span>
  
<span data-ttu-id="7ec6f-116">Después de configurar DNS, conectarse a Skype para los negocios en línea mediante PowerShell remoto con Skype las credenciales de administrador de empresa.</span><span class="sxs-lookup"><span data-stu-id="7ec6f-116">After configuring DNS, connect to Skype for Business Online by using remote PowerShell with Skype for Business Administrator credentials.</span></span> <span data-ttu-id="7ec6f-117">Para obtener más información, vea [Conectar con Skype para los negocios en línea mediante el uso de Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="7ec6f-117">For more information, see [Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>
  
<span data-ttu-id="7ec6f-118">En la sesión de PowerShell, introduzca los siguientes comandos para habilitar la omisión de medios:</span><span class="sxs-lookup"><span data-stu-id="7ec6f-118">In the PowerShell session, enter the following commands to enable media bypass:</span></span>
  
```
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
$mediabypass = New-CsNetworkMediaBypassConfiguration -AlwaysBypass $true -Enabled $true
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

<span data-ttu-id="7ec6f-119">Habilitar omisión de medios es un proceso de dos pasos.</span><span class="sxs-lookup"><span data-stu-id="7ec6f-119">Enabling media bypass is a two-step process.</span></span> <span data-ttu-id="7ec6f-120">El cmdlet New-CsNetworkMedia no guardar inmediatamente la nueva configuración; sólo crea la configuración en la memoria.</span><span class="sxs-lookup"><span data-stu-id="7ec6f-120">The New-CsNetworkMedia cmdlet does not immediately save the new configuration; it only creates the settings in memory.</span></span> <span data-ttu-id="7ec6f-121">El objeto creado mediante este cmdlet debe guardar en una variable y, a continuación, se asigna a la propiedad MediaBypassSettings de la configuración de red.</span><span class="sxs-lookup"><span data-stu-id="7ec6f-121">The object created by this cmdlet must be saved to a variable, and then assigned to the MediaBypassSettings property of the network configuration.</span></span> <span data-ttu-id="7ec6f-122">Para obtener más información, consulte [ejemplo: media omitir registros DNS del sitio web en entornos de múltiples sitios complejos](deploy-media-bypass-in-cloud-connector.md#Example).</span><span class="sxs-lookup"><span data-stu-id="7ec6f-122">For more information, see [Example: media bypass web site DNS records in complex multi-site environments](deploy-media-bypass-in-cloud-connector.md#Example).</span></span>
  
<span data-ttu-id="7ec6f-123">La replicación entre el local y de los componentes en línea puede tardar hasta 24 horas, lo que Microsoft recomienda ejecutar los comandos necesarios antes de permitir a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="7ec6f-123">The replication between the on-premises and online components can take up to 24 hours, so Microsoft recommends that you run the necessary commands before enabling users.</span></span>
  
## <a name="confirm-media-bypass-settings"></a><span data-ttu-id="7ec6f-124">Confirmar la configuración de la omisión de medios</span><span class="sxs-lookup"><span data-stu-id="7ec6f-124">Confirm media bypass settings</span></span>

<span data-ttu-id="7ec6f-125">La configuración de la omisión de medios se puede comprobar de la siguiente manera. </span><span class="sxs-lookup"><span data-stu-id="7ec6f-125">You can check the media bypass settings as follows.</span></span> 
  
<span data-ttu-id="7ec6f-126">Para comprobar la replicación en línea de la agrupación de inquilinos, ejecute el siguiente comando en PowerShell remoto:</span><span class="sxs-lookup"><span data-stu-id="7ec6f-126">To check online replication to your tenant pool, run the following command in remote PowerShell:</span></span>
  
```
Get-CsTenantHybridConfiguration -LocalStore
Get-CsNetworkConfiguration -LocalStore

```

<span data-ttu-id="7ec6f-127">Para comprobar la replicación local, conectar a los servidores de mediación de conector de nube, ejecute el siguiente comando en PowerShell y confirmar que Enabled = True y AlwaysBypass = True</span><span class="sxs-lookup"><span data-stu-id="7ec6f-127">To check the on-premises replication, connect to the Cloud Connector Mediation servers, run the following command in PowerShell, and confirm that Enabled=True and AlwaysBypass=True</span></span>
  
```
Get-CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="7ec6f-128">Para comprobar la configuración del cliente, cerrar la sesión de la Skype para Business client, volver a iniciarla y confirme que el cliente ha recibido la dirección URL del servicio como sigue:</span><span class="sxs-lookup"><span data-stu-id="7ec6f-128">To check the client settings, sign out of the Skype for Business client, sign back in, and confirm that the client has received the service URL as follows:</span></span>
  
1. <span data-ttu-id="7ec6f-129">Abra %appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog. </span><span class="sxs-lookup"><span data-stu-id="7ec6f-129">Open %appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog.</span></span> 
    
2. <span data-ttu-id="7ec6f-130">Buscar hybridconfigserviceinternalurl y confirmar la dirección URL coincide con la que ha definido.</span><span class="sxs-lookup"><span data-stu-id="7ec6f-130">Search for hybridconfigserviceinternalurl and confirm the URL matches the one you defined.</span></span>
    
## <a name="change-media-bypass-parameters"></a><span data-ttu-id="7ec6f-131">Cambiar los parámetros de la omisión de medios</span><span class="sxs-lookup"><span data-stu-id="7ec6f-131">Change media bypass parameters</span></span>

<span data-ttu-id="7ec6f-132">Los administradores de inquilinos pueden modificar el nombre DNS del servicio web mediante la ejecución del siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="7ec6f-132">Tenant administrators are able to change the DNS name of the web service by running the following cmdlet:</span></span>
  
```
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
```

> [!IMPORTANT]
> <span data-ttu-id="7ec6f-133">Los clientes tienen que cerrar la sesión y volver a iniciarla para obtener el nombre nuevo del servicio y reconocer el cambio. </span><span class="sxs-lookup"><span data-stu-id="7ec6f-133">Clients need to sign out and sign in to get the new service name and recognize the change.</span></span> 
  
## <a name="temporarily-disable-media-bypass"></a><span data-ttu-id="7ec6f-134">Deshabilitar temporalmente la omisión de medios</span><span class="sxs-lookup"><span data-stu-id="7ec6f-134">Temporarily disable media bypass</span></span>

<span data-ttu-id="7ec6f-p106">Este escenario puede ser útil para solucionar problemas o como mantenimiento. Para deshabilitar el servicio, ejecute los siguientes cmdlet:</span><span class="sxs-lookup"><span data-stu-id="7ec6f-p106">This scenario might be useful for troubleshooting or maintenance. To disable the service, run the following cmdlets:</span></span>
  
```
$mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

<span data-ttu-id="7ec6f-137">Tras realizar el cambio, puede llevar algún tiempo para cambios en replicarse en todos los conectores de nube.</span><span class="sxs-lookup"><span data-stu-id="7ec6f-137">After making the change, it could take some time for changes to replicate to all Cloud Connectors.</span></span> <span data-ttu-id="7ec6f-138">Para comprobar el estado de la replicación, ejecute el siguiente cmdlet de PowerShell en servidores de mediación de conector de nube:</span><span class="sxs-lookup"><span data-stu-id="7ec6f-138">To check the status of replication, run the following cmdlet in PowerShell on Cloud Connector Mediation servers:</span></span> 
  
```
Get- CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="7ec6f-139">Una vez que se repliquen los cambios, el servicio web del servidor de mediación comenzará a rechazar las solicitudes del cliente para el servicio de omisión de medios.</span><span class="sxs-lookup"><span data-stu-id="7ec6f-139">After the changes replicate, the web service on the Mediation Server will start rejecting client requests for the media bypass service.</span></span>
  
## <a name="disable-media-bypass-permanently"></a><span data-ttu-id="7ec6f-140">Deshabilitar permanentemente la omisión de medios</span><span class="sxs-lookup"><span data-stu-id="7ec6f-140">Disable media bypass permanently</span></span>

<span data-ttu-id="7ec6f-141">Para deshabilitar permanentemente la omisión de medios, un administrador de inquilinos debe ejecutar los siguientes comandos: </span><span class="sxs-lookup"><span data-stu-id="7ec6f-141">To permanently disable media bypass, a tenant administrator needs to run the following commands:</span></span> 
  
```
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl  $null
    $mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false 
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass 
```

<span data-ttu-id="7ec6f-142">También será necesario un administrador quitar las direcciones web de omisión de medios de servidores DNS internos.</span><span class="sxs-lookup"><span data-stu-id="7ec6f-142">An administrator will also need to remove the web addresses for media bypass from internal DNS servers.</span></span> <span data-ttu-id="7ec6f-143">Tras realizar el cambio, puede llevar algún tiempo para cambios en replicarse en todos los dispositivos de conector de nube.</span><span class="sxs-lookup"><span data-stu-id="7ec6f-143">After making the change, it could take some time for changes to replicate to all Cloud Connector appliances.</span></span> 
  
## <a name="example-media-bypass-web-site-dns-records-in-complex-multi-site-environments"></a><span data-ttu-id="7ec6f-144">Ejemplo: Los registros DNS del sitio web de omisión de medios en entornos complejos de varios sitios</span><span class="sxs-lookup"><span data-stu-id="7ec6f-144">Example: media bypass web site DNS records in complex multi-site environments</span></span>
<span data-ttu-id="7ec6f-145"><a name="Example"> </a></span><span class="sxs-lookup"><span data-stu-id="7ec6f-145"></span></span>

<span data-ttu-id="7ec6f-146">Los clientes recibirán la dirección web del servicio web de omisión de medios desde un servidor DNS interno.</span><span class="sxs-lookup"><span data-stu-id="7ec6f-146">Clients will receive the web address of the media bypass web service from an internal DNS server.</span></span> <span data-ttu-id="7ec6f-147">El nombre del servicio web será el mismo en todos los dispositivos de conector de nube y sitios de nube conector PSTN.</span><span class="sxs-lookup"><span data-stu-id="7ec6f-147">The name of the web service will be the same across all Cloud Connector appliances and Cloud Connector PSTN sites.</span></span> <span data-ttu-id="7ec6f-148">En un entorno complejo de múltiples sitios, se recomienda utilizar Directiva de 2016 de DNS de Windows para gestionar el tráfico según ubicación geográfica, por lo que los clientes pueden redirigirse al servicio web que es para su red local.</span><span class="sxs-lookup"><span data-stu-id="7ec6f-148">In a complex multi-site environment, we recommend using the Windows 2016 DNS Policy for Geo-Location Based Traffic Management, so clients can be redirected to the web service which is local for their network.</span></span> 
  
<span data-ttu-id="7ec6f-149">Para obtener más información acerca de las directivas de Windows 2016 DNS, vea [Utilizar DNS directivas para gestionar el tráfico según ubicación geográfica con servidores principales](https://docs.microsoft.com/en-us/windows-server/networking/dns/deploy/primary-geo-location).</span><span class="sxs-lookup"><span data-stu-id="7ec6f-149">Fore more information about Windows 2016 DNS Policies, see [Use DNS Policy for Geo-Location Based Traffic Management with Primary Servers](https://docs.microsoft.com/en-us/windows-server/networking/dns/deploy/primary-geo-location).</span></span>
  
<span data-ttu-id="7ec6f-150">A continuación se muestra un ejemplo de configuración para un empresa con varios sitios mediante la directiva DNS de Windows 2016 para la geolocalización basada en la administración del tráfico.</span><span class="sxs-lookup"><span data-stu-id="7ec6f-150">The following is an example of configuration for a company with several sites using Windows 2016 DNS Policy for Geo-Location Based Traffic Management.</span></span>
  
<span data-ttu-id="7ec6f-151">El nombre del servicio de derivación es 'hybridvoice.adatum.biz'.</span><span class="sxs-lookup"><span data-stu-id="7ec6f-151">The name for the bypass service is 'hybridvoice.adatum.biz'.</span></span>
  
<span data-ttu-id="7ec6f-152">El sitio en Amsterdam tiene cuatro dispositivos de nube conector implementadas con las siguientes direcciones IP de servidor de mediación:</span><span class="sxs-lookup"><span data-stu-id="7ec6f-152">The site in Amsterdam has four Cloud Connector appliances deployed with the following Mediation Server IP addresses:</span></span>
  
- <span data-ttu-id="7ec6f-153">192.168.1.45</span><span class="sxs-lookup"><span data-stu-id="7ec6f-153">192.168.1.45</span></span>
    
- <span data-ttu-id="7ec6f-154">192.168.1.46</span><span class="sxs-lookup"><span data-stu-id="7ec6f-154">192.168.1.46</span></span>
    
- <span data-ttu-id="7ec6f-155">192.168.1.47</span><span class="sxs-lookup"><span data-stu-id="7ec6f-155">192.168.1.47</span></span>
    
- <span data-ttu-id="7ec6f-156">192.168.1.48</span><span class="sxs-lookup"><span data-stu-id="7ec6f-156">192.168.1.48</span></span>
    
<span data-ttu-id="7ec6f-157">El sitio de Seattle tiene tres dispositivos de nube conector implementadas con las siguientes direcciones IP de servidor de mediación:</span><span class="sxs-lookup"><span data-stu-id="7ec6f-157">The site in Seattle has three Cloud Connector appliances deployed with the following Mediation Server IP addresses:</span></span>
  
- <span data-ttu-id="7ec6f-158">10.10.1.8</span><span class="sxs-lookup"><span data-stu-id="7ec6f-158">10.10.1.8</span></span>
    
- <span data-ttu-id="7ec6f-159">10.10.1.9</span><span class="sxs-lookup"><span data-stu-id="7ec6f-159">10.10.1.9</span></span>
    
- <span data-ttu-id="7ec6f-160">10.10.1.10</span><span class="sxs-lookup"><span data-stu-id="7ec6f-160">10.10.1.10</span></span>
    
<span data-ttu-id="7ec6f-161">Con la geolocalización basada en la administración del tráfico, los servidores DNS se configurarían del siguiente modo:</span><span class="sxs-lookup"><span data-stu-id="7ec6f-161">Using Geo-Location Based Traffic Management, the DNS servers would be configured as follows:</span></span>
  
1. <span data-ttu-id="7ec6f-162">Cree subredes de clientes DNS para las subredes de Ámsterdam y Seattle.</span><span class="sxs-lookup"><span data-stu-id="7ec6f-162">Create DNS Client Subnets for both the Amsterdam and Seattle subnets.</span></span>
    
2. <span data-ttu-id="7ec6f-163">Cree los ámbitos de zona DNS para adatum.biz para Ámsterdam y Seattle.</span><span class="sxs-lookup"><span data-stu-id="7ec6f-163">Create DNS Zone Scopes for adatum.biz for both Amsterdam and Seattle.</span></span>
    
3. <span data-ttu-id="7ec6f-164">Cree los registros DNS en cada ámbito de zona DNS.</span><span class="sxs-lookup"><span data-stu-id="7ec6f-164">Create DNS records in each DNS Zone Scope.</span></span>
    
    <span data-ttu-id="7ec6f-165">Ámsterdam</span><span class="sxs-lookup"><span data-stu-id="7ec6f-165">Amsterdam</span></span>
    
  - <span data-ttu-id="7ec6f-166">Tipo A</span><span class="sxs-lookup"><span data-stu-id="7ec6f-166">Type A;</span></span>
    
  - <span data-ttu-id="7ec6f-167">Nombre: hybridvoice en la zona DNS adatum.biz</span><span class="sxs-lookup"><span data-stu-id="7ec6f-167">Name : hybridvoice in the adatum.biz DNS zone</span></span>
    
  - <span data-ttu-id="7ec6f-168">Destino: 192.168.1.45</span><span class="sxs-lookup"><span data-stu-id="7ec6f-168">Target: 192.168.1.45</span></span>
    
    <span data-ttu-id="7ec6f-169">Cree registros adicionales para los servidores de mediación adicionales</span><span class="sxs-lookup"><span data-stu-id="7ec6f-169">Create additional records for additional mediation servers</span></span>
    
  - <span data-ttu-id="7ec6f-170">192.168.1.46</span><span class="sxs-lookup"><span data-stu-id="7ec6f-170">192.168.1.46</span></span>
    
  - <span data-ttu-id="7ec6f-171">192.168.1.47</span><span class="sxs-lookup"><span data-stu-id="7ec6f-171">192.168.1.47</span></span>
    
  - <span data-ttu-id="7ec6f-172">192.168.1.48</span><span class="sxs-lookup"><span data-stu-id="7ec6f-172">192.168.1.48</span></span>
    
    <span data-ttu-id="7ec6f-173">Seattle</span><span class="sxs-lookup"><span data-stu-id="7ec6f-173">Seattle</span></span>
    
  - <span data-ttu-id="7ec6f-174">Tipo A</span><span class="sxs-lookup"><span data-stu-id="7ec6f-174">Type A</span></span>
    
  - <span data-ttu-id="7ec6f-175">Nombre: hybridvoice en la zona DNS adatum.biz</span><span class="sxs-lookup"><span data-stu-id="7ec6f-175">Name : hybridvoice in adatum.biz DNS zone</span></span>
    
  - <span data-ttu-id="7ec6f-176">Destino: 10.10.1.8</span><span class="sxs-lookup"><span data-stu-id="7ec6f-176">Target: 10.10.1.8</span></span>
    
    <span data-ttu-id="7ec6f-177">Cree registros adicionales para los servidores de mediación adicionales</span><span class="sxs-lookup"><span data-stu-id="7ec6f-177">Create additional records for additional mediation servers</span></span>
    
  - <span data-ttu-id="7ec6f-178">10.10.1.9</span><span class="sxs-lookup"><span data-stu-id="7ec6f-178">10.10.1.9</span></span>
    
  - <span data-ttu-id="7ec6f-179">10.10.1.10</span><span class="sxs-lookup"><span data-stu-id="7ec6f-179">10.10.1.10</span></span>
    
4. <span data-ttu-id="7ec6f-180">Cree la directiva DNS que conecta las subredes del cliente con los ámbitos de zona apropiados para garantizar la resolución DNS que desea.</span><span class="sxs-lookup"><span data-stu-id="7ec6f-180">Create the DNS policy that connects the client subnets to the appropriate zone scopes to ensure desired DNS resolution.</span></span>
    
<span data-ttu-id="7ec6f-181">En este punto, los clientes que hagan consultas de DNS desde la subred de Ámsterdam para hybridvoice.adatum.biz devolverán las direcciones 192.168.1.45, 192.168.1.46, 192.168.1.47 y 192.168.1.48, mientras que los clientes que hagan la misma consulta desde Seattle devolverán 10.10.1.8, 10.10.1.9 y 10.10.1.10.</span><span class="sxs-lookup"><span data-stu-id="7ec6f-181">At this point, clients making DNS queries from the Amsterdam subnet for hybridvoice.adatum.biz will return the 192.168.1.45, 192.168.1.46, 192.168.1.47 and 192.168.1.48 addresses, while clients making the same query form Seattle will return 10.10.1.8, 10.10.1.9 and 10.10.1.10.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7ec6f-182">Vea también</span><span class="sxs-lookup"><span data-stu-id="7ec6f-182">See also</span></span>
<span data-ttu-id="7ec6f-183"><a name="Example"> </a></span><span class="sxs-lookup"><span data-stu-id="7ec6f-183"></span></span>

#### 

[<span data-ttu-id="7ec6f-184">Planear la omisión de medios en nube conector Edition</span><span class="sxs-lookup"><span data-stu-id="7ec6f-184">Plan for media bypass in Cloud Connector Edition</span></span>](plan-for-media-bypass-in-cloud-connector-edition.md)

