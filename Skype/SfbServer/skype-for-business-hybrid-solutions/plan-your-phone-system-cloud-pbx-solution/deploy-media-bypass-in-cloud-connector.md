---
title: Implementar la omisión de medios en Cloud Connector Edition
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
description: Lea este tema para obtener información sobre los pasos para implementar la omisión de medios con Cloud Connector Edition versión 2.0 y versiones posteriores.
ms.openlocfilehash: c9dc79a3079fd27e8901d31abf1a27310d18ed28
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119369"
---
# <a name="deploy-media-bypass-in-cloud-connector-edition"></a><span data-ttu-id="831fd-103">Implementar la omisión de medios en Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="831fd-103">Deploy media bypass in Cloud Connector Edition</span></span>
 
> [!Important]
> <span data-ttu-id="831fd-104">Cloud Connector Edition se retirará el 31 de julio de 2021 junto con Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="831fd-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="831fd-105">Una vez que la organización haya actualizado a Teams, obtenga información sobre cómo conectar la red de telefonía local a Teams mediante [enrutamiento directo.](/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="831fd-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="831fd-106">Lea este tema para obtener información sobre los pasos para implementar la omisión de medios con Cloud Connector Edition versión 2.0 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="831fd-106">Read this topic to learn about steps to deploy media bypass with Cloud Connector Edition version 2.0 and later.</span></span> 
  
<span data-ttu-id="831fd-107">La omisión de medios permite a un cliente enviar medios directamente al próximo salto de la Red telefónica conmutada (RTC), una puerta de enlace o un controlador de borde de sesión (SBC) y eliminar el componente Cloud Connector Edition de la ruta de acceso multimedia.</span><span class="sxs-lookup"><span data-stu-id="831fd-107">Media bypass allows a client to send media directly to the Public Switched Telephone Network (PSTN) next hop—a gateway or Session Border Controller (SBC)—and eliminate the Cloud Connector Edition component from the media path.</span></span> <span data-ttu-id="831fd-108">Vea también [Plan for media bypass in Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md).</span><span class="sxs-lookup"><span data-stu-id="831fd-108">See also [Plan for media bypass in Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md).</span></span>
  
## <a name="enable-media-bypass"></a><span data-ttu-id="831fd-109">Habilitar el desvío de medios</span><span class="sxs-lookup"><span data-stu-id="831fd-109">Enable media bypass</span></span>

<span data-ttu-id="831fd-110">Para habilitar la omisión de medios, debe configurar el nombre DNS del servicio web de desvío de medios y activar la omisión de medios en la configuración del espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="831fd-110">To enable media bypass, you must configure the DNS name of the media bypass web service and turn on media bypass in the tenant configuration.</span></span> <span data-ttu-id="831fd-111">El servicio web de desvío de medios se implementa automáticamente en cada servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="831fd-111">The media bypass web service deploys automatically on every Mediation Server.</span></span> <span data-ttu-id="831fd-112">Un administrador de inquilinos debe elegir un nombre para un servicio de voz híbrido (sitio) y este nombre debe ser de un dominio SIP registrado para la voz híbrida.</span><span class="sxs-lookup"><span data-stu-id="831fd-112">A tenant administrator must pick a name for a hybrid voice service (site), and this name should be from a SIP domain registered for hybrid voice.</span></span> <span data-ttu-id="831fd-113">El nombre del servicio debe ser el mismo en todos los dispositivos de Cloud Connector y en todos los sitios RTC, independientemente de la ubicación del cliente.</span><span class="sxs-lookup"><span data-stu-id="831fd-113">The service name should be the same across all Cloud Connector appliances and all PSTN sites regardless of the client location.</span></span> <span data-ttu-id="831fd-114">El servicio web solo debe estar disponible internamente en la red.</span><span class="sxs-lookup"><span data-stu-id="831fd-114">The web service should only be available internally on the network.</span></span>
  
<span data-ttu-id="831fd-115">Un administrador de inquilinos debe configurar un registro DNS A en la producción interna de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="831fd-115">A tenant administrator must configure a DNS A record in the internal production Active Directory.</span></span> <span data-ttu-id="831fd-116">Si tiene un entorno complejo de varios sitios, vea el ejemplo de Ejemplo: registros DNS de sitios web de omisión de medios [en entornos complejos de varios sitios](deploy-media-bypass-in-cloud-connector.md#Example).</span><span class="sxs-lookup"><span data-stu-id="831fd-116">If you have a complex multi-site environment, see the example in [Example: media bypass web site DNS records in complex multi-site environments](deploy-media-bypass-in-cloud-connector.md#Example).</span></span> <span data-ttu-id="831fd-117">El registro DNS solo debe resolverse para clientes de red internos; no debe resolverse para clientes de red externos.</span><span class="sxs-lookup"><span data-stu-id="831fd-117">The DNS record should only resolve for internal network clients; it should not resolve for external network clients.</span></span>
  
<span data-ttu-id="831fd-118">Después de configurar DNS, conéctese a Skype Empresarial Online mediante PowerShell remoto con credenciales de administrador de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="831fd-118">After configuring DNS, connect to Skype for Business Online by using remote PowerShell with Skype for Business Administrator credentials.</span></span> <span data-ttu-id="831fd-119">Para obtener más información, [vea Configurar el equipo para Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md) .</span><span class="sxs-lookup"><span data-stu-id="831fd-119">For more information, see [Set up your computer for Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md) .</span></span>
  
<span data-ttu-id="831fd-120">En la sesión de PowerShell, escriba los siguientes comandos para habilitar la omisión de medios:</span><span class="sxs-lookup"><span data-stu-id="831fd-120">In the PowerShell session, enter the following commands to enable media bypass:</span></span>
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
$mediabypass = New-CsNetworkMediaBypassConfiguration -AlwaysBypass $true -Enabled $true
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

<span data-ttu-id="831fd-121">Habilitar la omisión de medios es un proceso de dos pasos.</span><span class="sxs-lookup"><span data-stu-id="831fd-121">Enabling media bypass is a two-step process.</span></span> <span data-ttu-id="831fd-122">El cmdlet New-CsNetworkMedia no guarda inmediatamente la nueva configuración; solo crea la configuración en la memoria.</span><span class="sxs-lookup"><span data-stu-id="831fd-122">The New-CsNetworkMedia cmdlet does not immediately save the new configuration; it only creates the settings in memory.</span></span> <span data-ttu-id="831fd-123">El objeto creado por este cmdlet debe guardarse en una variable y, a continuación, asignarse a la propiedad MediaBypassSettings de la configuración de red.</span><span class="sxs-lookup"><span data-stu-id="831fd-123">The object created by this cmdlet must be saved to a variable, and then assigned to the MediaBypassSettings property of the network configuration.</span></span> <span data-ttu-id="831fd-124">Para obtener más información, vea [Example: media bypass web site DNS records in complex multi-site environments](deploy-media-bypass-in-cloud-connector.md#Example).</span><span class="sxs-lookup"><span data-stu-id="831fd-124">For more information, see [Example: media bypass web site DNS records in complex multi-site environments](deploy-media-bypass-in-cloud-connector.md#Example).</span></span>
  
<span data-ttu-id="831fd-125">La replicación entre los componentes locales y en línea puede tardar hasta 24 horas, por lo que Microsoft recomienda ejecutar los comandos necesarios antes de habilitar a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="831fd-125">The replication between the on-premises and online components can take up to 24 hours, so Microsoft recommends that you run the necessary commands before enabling users.</span></span>
  
## <a name="confirm-media-bypass-settings"></a><span data-ttu-id="831fd-126">Confirmar la configuración de desvío de medios</span><span class="sxs-lookup"><span data-stu-id="831fd-126">Confirm media bypass settings</span></span>

<span data-ttu-id="831fd-127">Puede comprobar la configuración de desvío de medios de la siguiente manera.</span><span class="sxs-lookup"><span data-stu-id="831fd-127">You can check the media bypass settings as follows.</span></span> 
  
<span data-ttu-id="831fd-128">Para comprobar la replicación en línea en el grupo de inquilinos, ejecute el siguiente comando en PowerShell remoto:</span><span class="sxs-lookup"><span data-stu-id="831fd-128">To check online replication to your tenant pool, run the following command in remote PowerShell:</span></span>
  
```powershell
Get-CsTenantHybridConfiguration -LocalStore
Get-CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="831fd-129">Para comprobar la replicación local, conéctese a los servidores de mediación de Cloud Connector, ejecute el siguiente comando en PowerShell y confirme que Enabled=True y AlwaysBypass=True</span><span class="sxs-lookup"><span data-stu-id="831fd-129">To check the on-premises replication, connect to the Cloud Connector Mediation servers, run the following command in PowerShell, and confirm that Enabled=True and AlwaysBypass=True</span></span>
  
```powershell
Get-CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="831fd-130">Para comprobar la configuración del cliente, salga del cliente de Skype Empresarial, vuelva a iniciar sesión y confirme que el cliente ha recibido la dirección URL del servicio de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="831fd-130">To check the client settings, sign out of the Skype for Business client, sign back in, and confirm that the client has received the service URL as follows:</span></span>
  
1. <span data-ttu-id="831fd-131">Abra %appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog.</span><span class="sxs-lookup"><span data-stu-id="831fd-131">Open %appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog.</span></span> 
    
2. <span data-ttu-id="831fd-132">Busque hybridconfigserviceinternalurl y confirme que la dirección URL coincida con la definida.</span><span class="sxs-lookup"><span data-stu-id="831fd-132">Search for hybridconfigserviceinternalurl and confirm the URL matches the one you defined.</span></span>
    
## <a name="change-media-bypass-parameters"></a><span data-ttu-id="831fd-133">Cambiar parámetros de omisión de medios</span><span class="sxs-lookup"><span data-stu-id="831fd-133">Change media bypass parameters</span></span>

<span data-ttu-id="831fd-134">Los administradores de inquilinos pueden cambiar el nombre DNS del servicio web ejecutando el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="831fd-134">Tenant administrators are able to change the DNS name of the web service by running the following cmdlet:</span></span>
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
```

> [!IMPORTANT]
> <span data-ttu-id="831fd-135">Los clientes deben cerrar sesión e iniciar sesión para obtener el nuevo nombre de servicio y reconocer el cambio.</span><span class="sxs-lookup"><span data-stu-id="831fd-135">Clients need to sign out and sign in to get the new service name and recognize the change.</span></span> 
  
## <a name="temporarily-disable-media-bypass"></a><span data-ttu-id="831fd-136">Deshabilitar temporalmente la omisión de medios</span><span class="sxs-lookup"><span data-stu-id="831fd-136">Temporarily disable media bypass</span></span>

<span data-ttu-id="831fd-137">Este escenario puede ser útil para la solución de problemas o el mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="831fd-137">This scenario might be useful for troubleshooting or maintenance.</span></span> <span data-ttu-id="831fd-138">Para deshabilitar el servicio, ejecute los cmdlets siguientes:</span><span class="sxs-lookup"><span data-stu-id="831fd-138">To disable the service, run the following cmdlets:</span></span>
  
```powershell
$mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

<span data-ttu-id="831fd-139">Después de realizar el cambio, los cambios podrían tardar algún tiempo en replicarse en todos los conectores de nube.</span><span class="sxs-lookup"><span data-stu-id="831fd-139">After making the change, it could take some time for changes to replicate to all Cloud Connectors.</span></span> <span data-ttu-id="831fd-140">Para comprobar el estado de replicación, ejecute el siguiente cmdlet en PowerShell en los servidores de mediación de Cloud Connector:</span><span class="sxs-lookup"><span data-stu-id="831fd-140">To check the status of replication, run the following cmdlet in PowerShell on Cloud Connector Mediation servers:</span></span> 
  
```powershell
Get- CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="831fd-141">Después de replicar los cambios, el servicio web del servidor de mediación empezará a rechazar las solicitudes de cliente para el servicio de omisión de medios.</span><span class="sxs-lookup"><span data-stu-id="831fd-141">After the changes replicate, the web service on the Mediation Server will start rejecting client requests for the media bypass service.</span></span>
  
## <a name="disable-media-bypass-permanently"></a><span data-ttu-id="831fd-142">Deshabilitar la omisión de medios de forma permanente</span><span class="sxs-lookup"><span data-stu-id="831fd-142">Disable media bypass permanently</span></span>

<span data-ttu-id="831fd-143">Para deshabilitar permanentemente la omisión de medios, un administrador de inquilinos debe ejecutar los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="831fd-143">To permanently disable media bypass, a tenant administrator needs to run the following commands:</span></span> 
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl  $null
    $mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false 
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass 
```

<span data-ttu-id="831fd-144">Un administrador también tendrá que quitar las direcciones web para la omisión de medios de los servidores DNS internos.</span><span class="sxs-lookup"><span data-stu-id="831fd-144">An administrator will also need to remove the web addresses for media bypass from internal DNS servers.</span></span> <span data-ttu-id="831fd-145">Después de realizar el cambio, los cambios podrían tardar algún tiempo en replicarse en todos los dispositivos de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="831fd-145">After making the change, it could take some time for changes to replicate to all Cloud Connector appliances.</span></span> 
  
## <a name="example-media-bypass-web-site-dns-records-in-complex-multi-site-environments"></a><span data-ttu-id="831fd-146">Ejemplo: registros DNS de sitios web de desvío de medios en entornos complejos de varios sitios</span><span class="sxs-lookup"><span data-stu-id="831fd-146">Example: media bypass web site DNS records in complex multi-site environments</span></span>
<span data-ttu-id="831fd-147"><a name="Example"> </a></span><span class="sxs-lookup"><span data-stu-id="831fd-147"><a name="Example"> </a></span></span>

<span data-ttu-id="831fd-148">Los clientes recibirán la dirección web del servicio web de desvío de medios desde un servidor DNS interno.</span><span class="sxs-lookup"><span data-stu-id="831fd-148">Clients will receive the web address of the media bypass web service from an internal DNS server.</span></span> <span data-ttu-id="831fd-149">El nombre del servicio web será el mismo en todos los dispositivos de Cloud Connector y en los sitios RTC de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="831fd-149">The name of the web service will be the same across all Cloud Connector appliances and Cloud Connector PSTN sites.</span></span> <span data-ttu-id="831fd-150">En un entorno complejo de varios sitios, se recomienda usar la directiva DNS de Windows 2016 para la administración de tráfico basada en Geo-Location, para que los clientes se puedan redirigir al servicio web que es local para su red.</span><span class="sxs-lookup"><span data-stu-id="831fd-150">In a complex multi-site environment, we recommend using the Windows 2016 DNS Policy for Geo-Location Based Traffic Management, so clients can be redirected to the web service which is local for their network.</span></span> 
  
<span data-ttu-id="831fd-151">Fore more information about Windows 2016 DNS Policies, see [Use DNS Policy for Geo-Location Based Traffic Management with Primary Servers](/windows-server/networking/dns/deploy/primary-geo-location).</span><span class="sxs-lookup"><span data-stu-id="831fd-151">Fore more information about Windows 2016 DNS Policies, see [Use DNS Policy for Geo-Location Based Traffic Management with Primary Servers](/windows-server/networking/dns/deploy/primary-geo-location).</span></span>
  
<span data-ttu-id="831fd-152">A continuación se muestra un ejemplo de configuración para una empresa con varios sitios que usan la directiva DNS de Windows 2016 para la administración Geo-Location de tráfico basado en aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="831fd-152">The following is an example of configuration for a company with several sites using Windows 2016 DNS Policy for Geo-Location Based Traffic Management.</span></span>
  
<span data-ttu-id="831fd-153">El nombre del servicio de omisión es "hybridvoice.adatum.biz".</span><span class="sxs-lookup"><span data-stu-id="831fd-153">The name for the bypass service is 'hybridvoice.adatum.biz'.</span></span>
  
<span data-ttu-id="831fd-154">El sitio de Ámsterdam tiene cuatro dispositivos cloud Connector implementados con las siguientes direcciones IP del servidor de mediación:</span><span class="sxs-lookup"><span data-stu-id="831fd-154">The site in Amsterdam has four Cloud Connector appliances deployed with the following Mediation Server IP addresses:</span></span>
  
- <span data-ttu-id="831fd-155">192.168.1.45</span><span class="sxs-lookup"><span data-stu-id="831fd-155">192.168.1.45</span></span>
    
- <span data-ttu-id="831fd-156">192.168.1.46</span><span class="sxs-lookup"><span data-stu-id="831fd-156">192.168.1.46</span></span>
    
- <span data-ttu-id="831fd-157">192.168.1.47</span><span class="sxs-lookup"><span data-stu-id="831fd-157">192.168.1.47</span></span>
    
- <span data-ttu-id="831fd-158">192.168.1.48</span><span class="sxs-lookup"><span data-stu-id="831fd-158">192.168.1.48</span></span>
    
<span data-ttu-id="831fd-159">El sitio de Seattle tiene tres dispositivos cloud Connector implementados con las siguientes direcciones IP del servidor de mediación:</span><span class="sxs-lookup"><span data-stu-id="831fd-159">The site in Seattle has three Cloud Connector appliances deployed with the following Mediation Server IP addresses:</span></span>
  
- <span data-ttu-id="831fd-160">10.10.1.8</span><span class="sxs-lookup"><span data-stu-id="831fd-160">10.10.1.8</span></span>
    
- <span data-ttu-id="831fd-161">10.10.1.9</span><span class="sxs-lookup"><span data-stu-id="831fd-161">10.10.1.9</span></span>
    
- <span data-ttu-id="831fd-162">10.10.1.10</span><span class="sxs-lookup"><span data-stu-id="831fd-162">10.10.1.10</span></span>
    
<span data-ttu-id="831fd-163">Con Geo-Location de tráfico basado en servidores, los servidores DNS se configurarían de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="831fd-163">Using Geo-Location Based Traffic Management, the DNS servers would be configured as follows:</span></span>
  
1. <span data-ttu-id="831fd-164">Cree subredes de cliente DNS para las subredes de Ámsterdam y Seattle.</span><span class="sxs-lookup"><span data-stu-id="831fd-164">Create DNS Client Subnets for both the Amsterdam and Seattle subnets.</span></span>
    
2. <span data-ttu-id="831fd-165">Cree ámbitos de zona DNS para adatum.biz para Ámsterdam y Seattle.</span><span class="sxs-lookup"><span data-stu-id="831fd-165">Create DNS Zone Scopes for adatum.biz for both Amsterdam and Seattle.</span></span>
    
3. <span data-ttu-id="831fd-166">Cree registros DNS en cada ámbito de zona DNS.</span><span class="sxs-lookup"><span data-stu-id="831fd-166">Create DNS records in each DNS Zone Scope.</span></span>
    
    <span data-ttu-id="831fd-167">Ámsterdam</span><span class="sxs-lookup"><span data-stu-id="831fd-167">Amsterdam</span></span>
    
   - <span data-ttu-id="831fd-168">Tipo A;</span><span class="sxs-lookup"><span data-stu-id="831fd-168">Type A;</span></span>
    
   - <span data-ttu-id="831fd-169">Nombre : hybridvoice en la zona ADATUM.BIZ DNS</span><span class="sxs-lookup"><span data-stu-id="831fd-169">Name : hybridvoice in the adatum.biz DNS zone</span></span>
    
   - <span data-ttu-id="831fd-170">Objetivo: 192.168.1.45</span><span class="sxs-lookup"><span data-stu-id="831fd-170">Target: 192.168.1.45</span></span>
    
     <span data-ttu-id="831fd-171">Crear registros adicionales para servidores de mediación adicionales</span><span class="sxs-lookup"><span data-stu-id="831fd-171">Create additional records for additional mediation servers</span></span>
    
   - <span data-ttu-id="831fd-172">192.168.1.46</span><span class="sxs-lookup"><span data-stu-id="831fd-172">192.168.1.46</span></span>
    
   - <span data-ttu-id="831fd-173">192.168.1.47</span><span class="sxs-lookup"><span data-stu-id="831fd-173">192.168.1.47</span></span>
    
   - <span data-ttu-id="831fd-174">192.168.1.48</span><span class="sxs-lookup"><span data-stu-id="831fd-174">192.168.1.48</span></span>
    
     <span data-ttu-id="831fd-175">Seattle</span><span class="sxs-lookup"><span data-stu-id="831fd-175">Seattle</span></span>
    
   - <span data-ttu-id="831fd-176">Tipo A</span><span class="sxs-lookup"><span data-stu-id="831fd-176">Type A</span></span>
    
   - <span data-ttu-id="831fd-177">Nombre : hybridvoice en adatum.biz zona DNS</span><span class="sxs-lookup"><span data-stu-id="831fd-177">Name : hybridvoice in adatum.biz DNS zone</span></span>
    
   - <span data-ttu-id="831fd-178">Objetivo: 10.10.1.8</span><span class="sxs-lookup"><span data-stu-id="831fd-178">Target: 10.10.1.8</span></span>
    
     <span data-ttu-id="831fd-179">Crear registros adicionales para servidores de mediación adicionales</span><span class="sxs-lookup"><span data-stu-id="831fd-179">Create additional records for additional mediation servers</span></span>
    
   - <span data-ttu-id="831fd-180">10.10.1.9</span><span class="sxs-lookup"><span data-stu-id="831fd-180">10.10.1.9</span></span>
    
   - <span data-ttu-id="831fd-181">10.10.1.10</span><span class="sxs-lookup"><span data-stu-id="831fd-181">10.10.1.10</span></span>
    
4. <span data-ttu-id="831fd-182">Cree la directiva DNS que conecte las subredes de cliente a los ámbitos de zona adecuados para garantizar la resolución de DNS deseada.</span><span class="sxs-lookup"><span data-stu-id="831fd-182">Create the DNS policy that connects the client subnets to the appropriate zone scopes to ensure desired DNS resolution.</span></span>
    
<span data-ttu-id="831fd-183">En este momento, los clientes que hacen consultas DNS desde la subred de Ámsterdam para hybridvoice.adatum.biz devolverán el 192.168.1.45, 192.168.1.46, 192.168.1.47 y 192.168.1.48, mientras que los clientes que hacen el mismo formulario de consulta Seattle devolverán 10.10.1.8, 10.10.1.9 y 10.10.10.</span><span class="sxs-lookup"><span data-stu-id="831fd-183">At this point, clients making DNS queries from the Amsterdam subnet for hybridvoice.adatum.biz will return the 192.168.1.45, 192.168.1.46, 192.168.1.47 and 192.168.1.48 addresses, while clients making the same query form Seattle will return 10.10.1.8, 10.10.1.9 and 10.10.1.10.</span></span>

> [!NOTE]
> <span data-ttu-id="831fd-184">Si el dispositivo CCE no parece obtener la configuración actualizada, compruebe si el dispositivo puede ponerse en contacto con el inquilino a través de PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="831fd-184">If the CCE appliance doesn't seem to be getting the updated settings, check to see if the appliance is able to contact the tenant via remote PowerShell.</span></span> <span data-ttu-id="831fd-185">Puede usar PowerShell remoto para comprobar el estado del dispositivo con Get-CsHybridPSTNAppliance o usar PowerShell en el host CCE para comprobar el estado con Get-CcApplianceStatus.</span><span class="sxs-lookup"><span data-stu-id="831fd-185">You can use Remote PowerShell to check appliance status with Get-CsHybridPSTNAppliance or use PowerShell on the CCE host to check status with Get-CcApplianceStatus.</span></span>

  
## <a name="see-also"></a><span data-ttu-id="831fd-186">Ver también</span><span class="sxs-lookup"><span data-stu-id="831fd-186">See also</span></span>
<span data-ttu-id="831fd-187"><a name="Example"> </a></span><span class="sxs-lookup"><span data-stu-id="831fd-187"><a name="Example"> </a></span></span>

[<span data-ttu-id="831fd-188">Plan para la omisión de medios en Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="831fd-188">Plan for media bypass in Cloud Connector Edition</span></span>](plan-for-media-bypass-in-cloud-connector-edition.md)