---
title: Implementación de omisión de medios en Cloud Connector Edition
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
description: Lea este tema para obtener información sobre los pasos para implementar los elementos multimedia con la versión 2,0 y posteriores de Cloud Connector Edition.
ms.openlocfilehash: 771d3a7294fde38b032e4cd9a281f70156280d3a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802350"
---
# <a name="deploy-media-bypass-in-cloud-connector-edition"></a><span data-ttu-id="60986-103">Implementación de omisión de medios en Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="60986-103">Deploy media bypass in Cloud Connector Edition</span></span>
 
<span data-ttu-id="60986-104">Lea este tema para obtener información sobre los pasos para implementar los elementos multimedia con la versión 2,0 y posteriores de Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="60986-104">Read this topic to learn about steps to deploy media bypass with Cloud Connector Edition version 2.0 and later.</span></span> 
  
<span data-ttu-id="60986-105">La omisión de elementos multimedia permite a un cliente enviar archivos directamente al próximo salto de la red telefónica conmutada (RTC), una puerta de enlace o un controlador de borde de sesión (SBC), y eliminar el componente Cloud Connector Edition de la ruta multimedia.</span><span class="sxs-lookup"><span data-stu-id="60986-105">Media bypass allows a client to send media directly to the Public Switched Telephone Network (PSTN) next hop—a gateway or Session Border Controller (SBC)—and eliminate the Cloud Connector Edition component from the media path.</span></span> <span data-ttu-id="60986-106">Consulte también el [plan de omisión de medios en Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md).</span><span class="sxs-lookup"><span data-stu-id="60986-106">See also [Plan for media bypass in Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md).</span></span>
  
## <a name="enable-media-bypass"></a><span data-ttu-id="60986-107">Habilitar omisión de medios</span><span class="sxs-lookup"><span data-stu-id="60986-107">Enable media bypass</span></span>

<span data-ttu-id="60986-108">Para habilitar la omisión de medios, debe configurar el nombre DNS del servicio web de omisión de medios y activar la omisión de medios en la configuración de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="60986-108">To enable media bypass, you must configure the DNS name of the media bypass web service and turn on media bypass in the tenant configuration.</span></span> <span data-ttu-id="60986-109">El servicio web de omisión de medios se implementa automáticamente en cada servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="60986-109">The media bypass web service deploys automatically on every Mediation Server.</span></span> <span data-ttu-id="60986-110">Un administrador de inquilinos debe elegir un nombre para un servicio de voz híbrida (sitio) y este nombre debe provenir de un dominio SIP registrado para la voz híbrida.</span><span class="sxs-lookup"><span data-stu-id="60986-110">A tenant administrator must pick a name for a hybrid voice service (site), and this name should be from a SIP domain registered for hybrid voice.</span></span> <span data-ttu-id="60986-111">El nombre del servicio debe ser el mismo en todos los dispositivos de conexión en la nube y en todos los sitios RTC, independientemente de la ubicación del cliente.</span><span class="sxs-lookup"><span data-stu-id="60986-111">The service name should be the same across all Cloud Connector appliances and all PSTN sites regardless of the client location.</span></span> <span data-ttu-id="60986-112">El servicio web solo debe estar disponible internamente en la red.</span><span class="sxs-lookup"><span data-stu-id="60986-112">The web service should only be available internally on the network.</span></span>
  
<span data-ttu-id="60986-113">Un administrador de inquilinos debe configurar un registro DNS A en el Active Directory de producción interna.</span><span class="sxs-lookup"><span data-stu-id="60986-113">A tenant administrator must configure a DNS A record in the internal production Active Directory.</span></span> <span data-ttu-id="60986-114">Si tiene un entorno complejo con varios sitios, vea el ejemplo en [ejemplo: multimedia omitir los registros DNS de un sitio web en entornos complejos con varios sitios](deploy-media-bypass-in-cloud-connector.md#Example).</span><span class="sxs-lookup"><span data-stu-id="60986-114">If you have a complex multi-site environment, see the example in [Example: media bypass web site DNS records in complex multi-site environments](deploy-media-bypass-in-cloud-connector.md#Example).</span></span> <span data-ttu-id="60986-115">El registro DNS solo debe resolver la situación en el caso de clientes de red internos, no para clientes de red externos.</span><span class="sxs-lookup"><span data-stu-id="60986-115">The DNS record should only resolve for internal network clients; it should not resolve for external network clients.</span></span>
  
<span data-ttu-id="60986-116">Tras configurar DNS, conecte Skype Empresarial Online mediante el PowerShell remoto con las credenciales del administrador de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="60986-116">After configuring DNS, connect to Skype for Business Online by using remote PowerShell with Skype for Business Administrator credentials.</span></span> <span data-ttu-id="60986-117">Para obtener más información, vea [configurar el equipo para Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md) .</span><span class="sxs-lookup"><span data-stu-id="60986-117">For more information, see [Set up your computer for Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md) .</span></span>
  
<span data-ttu-id="60986-118">En la sesión de PowerShell, introduzca los siguientes comandos para habilitar la omisión de medios:</span><span class="sxs-lookup"><span data-stu-id="60986-118">In the PowerShell session, enter the following commands to enable media bypass:</span></span>
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
$mediabypass = New-CsNetworkMediaBypassConfiguration -AlwaysBypass $true -Enabled $true
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

<span data-ttu-id="60986-119">El proceso para habilitar la omisión de medios consta de dos pasos.</span><span class="sxs-lookup"><span data-stu-id="60986-119">Enabling media bypass is a two-step process.</span></span> <span data-ttu-id="60986-120">El cmdlet New-CsNetworkMedia no guarda la nueva configuración inmediatamente; solo la crea en la memoria.</span><span class="sxs-lookup"><span data-stu-id="60986-120">The New-CsNetworkMedia cmdlet does not immediately save the new configuration; it only creates the settings in memory.</span></span> <span data-ttu-id="60986-121">El objeto que crea este cmdlet se debe guardar en una variable y después se debe asignar a la propiedad MediaBypassSettings de la configuración de red.</span><span class="sxs-lookup"><span data-stu-id="60986-121">The object created by this cmdlet must be saved to a variable, and then assigned to the MediaBypassSettings property of the network configuration.</span></span> <span data-ttu-id="60986-122">Para obtener más información, vea [ejemplo: multimedia omitir los registros DNS de un sitio web en entornos complejos con varios sitios](deploy-media-bypass-in-cloud-connector.md#Example).</span><span class="sxs-lookup"><span data-stu-id="60986-122">For more information, see [Example: media bypass web site DNS records in complex multi-site environments](deploy-media-bypass-in-cloud-connector.md#Example).</span></span>
  
<span data-ttu-id="60986-123">La replicación entre los componentes locales y en línea puede tardar hasta 24 horas, por lo que Microsoft recomienda que ejecute los comandos necesarios antes de habilitar usuarios.</span><span class="sxs-lookup"><span data-stu-id="60986-123">The replication between the on-premises and online components can take up to 24 hours, so Microsoft recommends that you run the necessary commands before enabling users.</span></span>
  
## <a name="confirm-media-bypass-settings"></a><span data-ttu-id="60986-124">Confirmar la configuración de la omisión de medios</span><span class="sxs-lookup"><span data-stu-id="60986-124">Confirm media bypass settings</span></span>

<span data-ttu-id="60986-125">La configuración de la omisión de medios se puede comprobar de la siguiente manera. </span><span class="sxs-lookup"><span data-stu-id="60986-125">You can check the media bypass settings as follows.</span></span> 
  
<span data-ttu-id="60986-126">Para comprobar la replicación en línea en el grupo de inquilinos, ejecute el siguiente comando en PowerShell remoto:</span><span class="sxs-lookup"><span data-stu-id="60986-126">To check online replication to your tenant pool, run the following command in remote PowerShell:</span></span>
  
```powershell
Get-CsTenantHybridConfiguration -LocalStore
Get-CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="60986-127">Para comprobar la replicación local, conéctese a los servidores de media de los conectores de nube, ejecute el siguiente comando en PowerShell y confirme que Enabled = true y AlwaysBypass = true</span><span class="sxs-lookup"><span data-stu-id="60986-127">To check the on-premises replication, connect to the Cloud Connector Mediation servers, run the following command in PowerShell, and confirm that Enabled=True and AlwaysBypass=True</span></span>
  
```powershell
Get-CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="60986-128">Para comprobar la configuración del cliente, cierre sesión en el cliente de Skype empresarial, vuelva a iniciar sesión y confirme que el cliente ha recibido la dirección URL del servicio de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="60986-128">To check the client settings, sign out of the Skype for Business client, sign back in, and confirm that the client has received the service URL as follows:</span></span>
  
1. <span data-ttu-id="60986-129">Abra %appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog.</span><span class="sxs-lookup"><span data-stu-id="60986-129">Open %appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog.</span></span> 
    
2. <span data-ttu-id="60986-130">Busque hybridconfigserviceinternalurl y confirme que la dirección URL coincida con la que ha definido.</span><span class="sxs-lookup"><span data-stu-id="60986-130">Search for hybridconfigserviceinternalurl and confirm the URL matches the one you defined.</span></span>
    
## <a name="change-media-bypass-parameters"></a><span data-ttu-id="60986-131">Cambiar los parámetros de la omisión de medios</span><span class="sxs-lookup"><span data-stu-id="60986-131">Change media bypass parameters</span></span>

<span data-ttu-id="60986-132">Los administradores de inquilinos pueden modificar el nombre DNS del servicio web mediante la ejecución del siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="60986-132">Tenant administrators are able to change the DNS name of the web service by running the following cmdlet:</span></span>
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
```

> [!IMPORTANT]
> <span data-ttu-id="60986-133">Los clientes tienen que cerrar la sesión y volver a iniciarla para obtener el nombre nuevo del servicio y reconocer el cambio. </span><span class="sxs-lookup"><span data-stu-id="60986-133">Clients need to sign out and sign in to get the new service name and recognize the change.</span></span> 
  
## <a name="temporarily-disable-media-bypass"></a><span data-ttu-id="60986-134">Deshabilitar temporalmente la omisión de medios</span><span class="sxs-lookup"><span data-stu-id="60986-134">Temporarily disable media bypass</span></span>

<span data-ttu-id="60986-p106">Este escenario puede ser útil para solucionar problemas o como mantenimiento. Para deshabilitar el servicio, ejecute los siguientes cmdlet:</span><span class="sxs-lookup"><span data-stu-id="60986-p106">This scenario might be useful for troubleshooting or maintenance. To disable the service, run the following cmdlets:</span></span>
  
```powershell
$mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

<span data-ttu-id="60986-137">Tras hacer el cambio, es posible que pase algún tiempo hasta que los cambios se repliquen en todas las instancias de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="60986-137">After making the change, it could take some time for changes to replicate to all Cloud Connectors.</span></span> <span data-ttu-id="60986-138">Para comprobar el estado de la replicación, ejecute el siguiente cmdlet en PowerShell en los servidores de mediación del conector en la nube:</span><span class="sxs-lookup"><span data-stu-id="60986-138">To check the status of replication, run the following cmdlet in PowerShell on Cloud Connector Mediation servers:</span></span> 
  
```powershell
Get- CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="60986-139">Una vez que se repliquen los cambios, el servicio web del servidor de mediación comenzará a rechazar las solicitudes del cliente para el servicio de omisión de medios.</span><span class="sxs-lookup"><span data-stu-id="60986-139">After the changes replicate, the web service on the Mediation Server will start rejecting client requests for the media bypass service.</span></span>
  
## <a name="disable-media-bypass-permanently"></a><span data-ttu-id="60986-140">Deshabilitar permanentemente la omisión de medios</span><span class="sxs-lookup"><span data-stu-id="60986-140">Disable media bypass permanently</span></span>

<span data-ttu-id="60986-141">Para deshabilitar permanentemente la omisión de medios, un administrador de inquilinos debe ejecutar los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="60986-141">To permanently disable media bypass, a tenant administrator needs to run the following commands:</span></span> 
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl  $null
    $mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false 
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass 
```

<span data-ttu-id="60986-142">Un administrador también tendrá que quitar las direcciones web para la omisión de medios de los servidores DNS internos.</span><span class="sxs-lookup"><span data-stu-id="60986-142">An administrator will also need to remove the web addresses for media bypass from internal DNS servers.</span></span> <span data-ttu-id="60986-143">Después de realizar el cambio, los cambios pueden tardar algún tiempo en replicarse en todos los dispositivos de conexión en la nube.</span><span class="sxs-lookup"><span data-stu-id="60986-143">After making the change, it could take some time for changes to replicate to all Cloud Connector appliances.</span></span> 
  
## <a name="example-media-bypass-web-site-dns-records-in-complex-multi-site-environments"></a><span data-ttu-id="60986-144">Ejemplo: Los registros DNS del sitio web de omisión de medios en entornos complejos de varios sitios</span><span class="sxs-lookup"><span data-stu-id="60986-144">Example: media bypass web site DNS records in complex multi-site environments</span></span>
<span data-ttu-id="60986-145"><a name="Example"> </a></span><span class="sxs-lookup"><span data-stu-id="60986-145"><a name="Example"> </a></span></span>

<span data-ttu-id="60986-146">Los clientes recibirán la dirección web del servicio web de omisión de medios desde un servidor DNS interno.</span><span class="sxs-lookup"><span data-stu-id="60986-146">Clients will receive the web address of the media bypass web service from an internal DNS server.</span></span> <span data-ttu-id="60986-147">El nombre del servicio Web será el mismo en todos los equipos conector de nube y en los sitios RTC del conector de nube.</span><span class="sxs-lookup"><span data-stu-id="60986-147">The name of the web service will be the same across all Cloud Connector appliances and Cloud Connector PSTN sites.</span></span> <span data-ttu-id="60986-148">En un entorno complejo de varios sitios, recomendamos que utilice la directiva DNS de Windows 2016 para la administración del tráfico basado en la geolocalización, de manera que se pueda redirigir a los clientes al servicio web que sea local para la red.</span><span class="sxs-lookup"><span data-stu-id="60986-148">In a complex multi-site environment, we recommend using the Windows 2016 DNS Policy for Geo-Location Based Traffic Management, so clients can be redirected to the web service which is local for their network.</span></span> 
  
<span data-ttu-id="60986-149">Para obtener más información sobre las directivas DNS de Windows 2016, consulte [usar la Directiva DNS para la administración de tráfico basada en la ubicación geográfica con los servidores principales](https://docs.microsoft.com/windows-server/networking/dns/deploy/primary-geo-location).</span><span class="sxs-lookup"><span data-stu-id="60986-149">Fore more information about Windows 2016 DNS Policies, see [Use DNS Policy for Geo-Location Based Traffic Management with Primary Servers](https://docs.microsoft.com/windows-server/networking/dns/deploy/primary-geo-location).</span></span>
  
<span data-ttu-id="60986-150">A continuación se muestra un ejemplo de configuración para un empresa con varios sitios mediante la directiva DNS de Windows 2016 para la geolocalización basada en la administración del tráfico.</span><span class="sxs-lookup"><span data-stu-id="60986-150">The following is an example of configuration for a company with several sites using Windows 2016 DNS Policy for Geo-Location Based Traffic Management.</span></span>
  
<span data-ttu-id="60986-151">El nombre del servicio de derivación es ' hybridvoice.adatum.biz '.</span><span class="sxs-lookup"><span data-stu-id="60986-151">The name for the bypass service is 'hybridvoice.adatum.biz'.</span></span>
  
<span data-ttu-id="60986-152">El sitio de Amsterdam tiene cuatro dispositivos de conexión de nube implementados con las siguientes direcciones IP de servidor de mediación:</span><span class="sxs-lookup"><span data-stu-id="60986-152">The site in Amsterdam has four Cloud Connector appliances deployed with the following Mediation Server IP addresses:</span></span>
  
- <span data-ttu-id="60986-153">192.168.1.45</span><span class="sxs-lookup"><span data-stu-id="60986-153">192.168.1.45</span></span>
    
- <span data-ttu-id="60986-154">192.168.1.46</span><span class="sxs-lookup"><span data-stu-id="60986-154">192.168.1.46</span></span>
    
- <span data-ttu-id="60986-155">192.168.1.47</span><span class="sxs-lookup"><span data-stu-id="60986-155">192.168.1.47</span></span>
    
- <span data-ttu-id="60986-156">192.168.1.48</span><span class="sxs-lookup"><span data-stu-id="60986-156">192.168.1.48</span></span>
    
<span data-ttu-id="60986-157">El sitio de Seattle tiene tres dispositivos de conexión en la nube implementados con las siguientes direcciones IP del servidor de mediación:</span><span class="sxs-lookup"><span data-stu-id="60986-157">The site in Seattle has three Cloud Connector appliances deployed with the following Mediation Server IP addresses:</span></span>
  
- <span data-ttu-id="60986-158">10.10.1.8</span><span class="sxs-lookup"><span data-stu-id="60986-158">10.10.1.8</span></span>
    
- <span data-ttu-id="60986-159">10.10.1.9</span><span class="sxs-lookup"><span data-stu-id="60986-159">10.10.1.9</span></span>
    
- <span data-ttu-id="60986-160">10.10.1.10</span><span class="sxs-lookup"><span data-stu-id="60986-160">10.10.1.10</span></span>
    
<span data-ttu-id="60986-161">Con la geolocalización basada en la administración del tráfico, los servidores DNS se configurarían del siguiente modo:</span><span class="sxs-lookup"><span data-stu-id="60986-161">Using Geo-Location Based Traffic Management, the DNS servers would be configured as follows:</span></span>
  
1. <span data-ttu-id="60986-162">Cree subredes de clientes DNS para las subredes de Ámsterdam y Seattle.</span><span class="sxs-lookup"><span data-stu-id="60986-162">Create DNS Client Subnets for both the Amsterdam and Seattle subnets.</span></span>
    
2. <span data-ttu-id="60986-163">Cree los ámbitos de zona DNS para adatum.biz para Ámsterdam y Seattle.</span><span class="sxs-lookup"><span data-stu-id="60986-163">Create DNS Zone Scopes for adatum.biz for both Amsterdam and Seattle.</span></span>
    
3. <span data-ttu-id="60986-164">Cree los registros DNS en cada ámbito de zona DNS.</span><span class="sxs-lookup"><span data-stu-id="60986-164">Create DNS records in each DNS Zone Scope.</span></span>
    
    <span data-ttu-id="60986-165">Ámsterdam</span><span class="sxs-lookup"><span data-stu-id="60986-165">Amsterdam</span></span>
    
   - <span data-ttu-id="60986-166">Tipo A</span><span class="sxs-lookup"><span data-stu-id="60986-166">Type A;</span></span>
    
   - <span data-ttu-id="60986-167">Nombre: hybridvoice en la zona DNS adatum.biz</span><span class="sxs-lookup"><span data-stu-id="60986-167">Name : hybridvoice in the adatum.biz DNS zone</span></span>
    
   - <span data-ttu-id="60986-168">Destino: 192.168.1.45</span><span class="sxs-lookup"><span data-stu-id="60986-168">Target: 192.168.1.45</span></span>
    
     <span data-ttu-id="60986-169">Cree registros adicionales para los servidores de mediación adicionales</span><span class="sxs-lookup"><span data-stu-id="60986-169">Create additional records for additional mediation servers</span></span>
    
   - <span data-ttu-id="60986-170">192.168.1.46</span><span class="sxs-lookup"><span data-stu-id="60986-170">192.168.1.46</span></span>
    
   - <span data-ttu-id="60986-171">192.168.1.47</span><span class="sxs-lookup"><span data-stu-id="60986-171">192.168.1.47</span></span>
    
   - <span data-ttu-id="60986-172">192.168.1.48</span><span class="sxs-lookup"><span data-stu-id="60986-172">192.168.1.48</span></span>
    
     <span data-ttu-id="60986-173">Seattle</span><span class="sxs-lookup"><span data-stu-id="60986-173">Seattle</span></span>
    
   - <span data-ttu-id="60986-174">Tipo A</span><span class="sxs-lookup"><span data-stu-id="60986-174">Type A</span></span>
    
   - <span data-ttu-id="60986-175">Nombre: hybridvoice en la zona DNS adatum.biz</span><span class="sxs-lookup"><span data-stu-id="60986-175">Name : hybridvoice in adatum.biz DNS zone</span></span>
    
   - <span data-ttu-id="60986-176">Destino: 10.10.1.8</span><span class="sxs-lookup"><span data-stu-id="60986-176">Target: 10.10.1.8</span></span>
    
     <span data-ttu-id="60986-177">Cree registros adicionales para los servidores de mediación adicionales</span><span class="sxs-lookup"><span data-stu-id="60986-177">Create additional records for additional mediation servers</span></span>
    
   - <span data-ttu-id="60986-178">10.10.1.9</span><span class="sxs-lookup"><span data-stu-id="60986-178">10.10.1.9</span></span>
    
   - <span data-ttu-id="60986-179">10.10.1.10</span><span class="sxs-lookup"><span data-stu-id="60986-179">10.10.1.10</span></span>
    
4. <span data-ttu-id="60986-180">Cree la directiva DNS que conecta las subredes del cliente con los ámbitos de zona apropiados para garantizar la resolución DNS que desea.</span><span class="sxs-lookup"><span data-stu-id="60986-180">Create the DNS policy that connects the client subnets to the appropriate zone scopes to ensure desired DNS resolution.</span></span>
    
<span data-ttu-id="60986-181">En este punto, los clientes que hagan consultas de DNS desde la subred de Ámsterdam para hybridvoice.adatum.biz devolverán las direcciones 192.168.1.45, 192.168.1.46, 192.168.1.47 y 192.168.1.48, mientras que los clientes que hagan la misma consulta desde Seattle devolverán 10.10.1.8, 10.10.1.9 y 10.10.1.10.</span><span class="sxs-lookup"><span data-stu-id="60986-181">At this point, clients making DNS queries from the Amsterdam subnet for hybridvoice.adatum.biz will return the 192.168.1.45, 192.168.1.46, 192.168.1.47 and 192.168.1.48 addresses, while clients making the same query form Seattle will return 10.10.1.8, 10.10.1.9 and 10.10.1.10.</span></span>

> [!NOTE]
> <span data-ttu-id="60986-182">Si el dispositivo de CCE no parece estar recibiendo la configuración actualizada, compruebe si el dispositivo puede ponerse en contacto con el inquilino a través de PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="60986-182">If the CCE appliance doesn't seem to be getting the updated settings, check to see if the appliance is able to contact the tenant via remote PowerShell.</span></span> <span data-ttu-id="60986-183">Puede usar PowerShell remoto para comprobar el estado del equipo con get-CsHybridPSTNAppliance o usar PowerShell en el host de CCE para comprobar el estado con get-CcApplianceStatus.</span><span class="sxs-lookup"><span data-stu-id="60986-183">You can use Remote PowerShell to check appliance status with Get-CsHybridPSTNAppliance or use PowerShell on the CCE host to check status with Get-CcApplianceStatus.</span></span>

  
## <a name="see-also"></a><span data-ttu-id="60986-184">Vea también</span><span class="sxs-lookup"><span data-stu-id="60986-184">See also</span></span>
<span data-ttu-id="60986-185"><a name="Example"> </a></span><span class="sxs-lookup"><span data-stu-id="60986-185"><a name="Example"> </a></span></span>

[<span data-ttu-id="60986-186">Plan para la omisión de medios en Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="60986-186">Plan for media bypass in Cloud Connector Edition</span></span>](plan-for-media-bypass-in-cloud-connector-edition.md)
