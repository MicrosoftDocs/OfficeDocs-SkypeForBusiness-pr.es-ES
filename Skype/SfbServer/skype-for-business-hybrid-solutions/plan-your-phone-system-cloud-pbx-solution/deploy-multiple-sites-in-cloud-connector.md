---
title: Implementar varios sitios en Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e62413fd-f68e-4825-8384-c983076bdf23
description: Obtenga más información sobre cómo implementar varios sitios de RTC en Cloud Connector Edition.
ms.openlocfilehash: 1276d436a05e5151bdc90c19bbf41b8e90d913bf
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2020
ms.locfileid: "41887639"
---
# <a name="deploy-multiple-sites-in-cloud-connector"></a><span data-ttu-id="1b59f-103">Implementar varios sitios en Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="1b59f-103">Deploy multiple sites in Cloud Connector</span></span>
 
<span data-ttu-id="1b59f-104">Obtenga más información sobre cómo implementar varios sitios de RTC en Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="1b59f-104">Learn about deploying multiple PSTN sites in Cloud Connector Edition.</span></span>
  
<span data-ttu-id="1b59f-p101">En esta sección se describe cómo implementar varios sitios de red telefónica conmutada (RTC). Los sitios se implementan de uno en uno siguiendo los mismos pasos que para la implementación de un único sitio. En este tema se describen las consideraciones para los sitios y las diferencias entre ellos en una implementación de varios sitios. </span><span class="sxs-lookup"><span data-stu-id="1b59f-p101">This section describes how to deploy multiple Public Switched Telephone Network (PSTN) sites. Sites are deployed one at a time using the same steps as deploying a single site. This topic describes the considerations for and differences between sites in a multiple site deployment.</span></span> 
  
## <a name="multiple-public-switched-telephone-network-pstn-sites"></a><span data-ttu-id="1b59f-108">Varios sitios de red telefónica conmutada (RTC)</span><span class="sxs-lookup"><span data-stu-id="1b59f-108">Multiple Public Switched Telephone Network (PSTN) Sites</span></span>

<span data-ttu-id="1b59f-109">A continuación se muestra un ejemplo de configuración para implementar Skype empresarial Cloud Connector Edition para diferentes sitios de RTC.</span><span class="sxs-lookup"><span data-stu-id="1b59f-109">The following shows an example configuration to deploy Skype for Business Cloud Connector Edition for different PSTN sites.</span></span> <span data-ttu-id="1b59f-110">Asegúrese de que los parámetros de configuración sean correctos antes de comenzar con una implementación.</span><span class="sxs-lookup"><span data-stu-id="1b59f-110">Make sure your configuration settings are correct before you start a deployment.</span></span>
  
<span data-ttu-id="1b59f-111">Sitio de RTC 1</span><span class="sxs-lookup"><span data-stu-id="1b59f-111">PSTN Site 1</span></span>
  
```console
[Common]
SiteName=Site1
[EdgeServer]
InternalMachineName= cc-edge1
InternalPoolName=cc-edgepool
InternalMachineIPs=192.168.0.241

ExternalSIPPoolName=access1
ExternalSIPIPs=192.168.1.4

ExternalMRFQDNPoolName=mr1
ExternalMRIPs=192.168.1.4
ExternalMRPublicIPs=23.99.115.35
```

<span data-ttu-id="1b59f-112">Sitio de RTC 2</span><span class="sxs-lookup"><span data-stu-id="1b59f-112">PSTN Site 2</span></span>
  
```console
[Common]
SiteName=Site2
[EdgeServer]
InternalMachineName= cc-edge2
InternalPoolName=cc-edgepool
InternalMachineIPs=192.168.0.242

ExternalSIPPoolName=access2
ExternalSIPIPs=192.168.1.5

ExternalMRFQDNPoolName=mr2
ExternalMRIPs=192.168.1.5
ExternalMRPublicIPs=104.42.226.134
```

<span data-ttu-id="1b59f-113">Para cada sitio PSTN que desee agregar, siga los pasos que se indican en [implementar un único sitio en la nube Connector](deploy-a-single-site-in-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="1b59f-113">For each PSTN site that you want to add, follow the steps in [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="1b59f-114">La carpeta compartida para preparar la alta disponibilidad (HA) es por cada sitio RTC.</span><span class="sxs-lookup"><span data-stu-id="1b59f-114">The shared folder for preparing High Availability (HA) is per PSTN site.</span></span> <span data-ttu-id="1b59f-115">La carpeta compartida **debe** ser diferente en cada sitio RTC.</span><span class="sxs-lookup"><span data-stu-id="1b59f-115">The shared folder **must** be different between PSTN sites.</span></span> <span data-ttu-id="1b59f-116">No use la misma carpeta compartida para varios sitios. ></span><span class="sxs-lookup"><span data-stu-id="1b59f-116">Do not use the same shared folder for multiple sites.></span></span> 
  
## <a name="single-site-with-high-availability-ha-compared-to-multi-site-deployments"></a><span data-ttu-id="1b59f-117">Sitio único con alta disponibilidad (HA) comparado con implementaciones de varios sitios</span><span class="sxs-lookup"><span data-stu-id="1b59f-117">Single site with High Availability (HA) compared to multi-site deployments</span></span>
<span data-ttu-id="1b59f-118"><a name="BKMK_SingleSitecomparedtomulti-site"> </a></span><span class="sxs-lookup"><span data-stu-id="1b59f-118"><a name="BKMK_SingleSitecomparedtomulti-site"> </a></span></span>

<span data-ttu-id="1b59f-119">En la siguiente tabla se muestran las diferencias entre un sitio único compatible con HA y una implementación de varios sitios.</span><span class="sxs-lookup"><span data-stu-id="1b59f-119">The following table lists the differences between single site with HA support and a multiple site deployment.</span></span>
  
|<span data-ttu-id="1b59f-120">**Categoría**</span><span class="sxs-lookup"><span data-stu-id="1b59f-120">**Category**</span></span>|<span data-ttu-id="1b59f-121">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="1b59f-121">**Item**</span></span>|<span data-ttu-id="1b59f-122">**Sitio único con HA**</span><span class="sxs-lookup"><span data-stu-id="1b59f-122">**Single-Site with HA**</span></span>|<span data-ttu-id="1b59f-123">**Varios sitios**</span><span class="sxs-lookup"><span data-stu-id="1b59f-123">**Multi-Site**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1b59f-124">Configuración</span><span class="sxs-lookup"><span data-stu-id="1b59f-124">Configure</span></span>  <br/> |<span data-ttu-id="1b59f-125">Nombre de host del dispositivo</span><span class="sxs-lookup"><span data-stu-id="1b59f-125">Appliance Host Name</span></span> <br/> |<span data-ttu-id="1b59f-126">**Diferentes** en todos los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="1b59f-126">**Different** across appliances</span></span> <br/> |<span data-ttu-id="1b59f-127">**Diferentes** en todos los sitios de RTC.</span><span class="sxs-lookup"><span data-stu-id="1b59f-127">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="1b59f-128">Configuración</span><span class="sxs-lookup"><span data-stu-id="1b59f-128">Setup</span></span>  <br/> |<span data-ttu-id="1b59f-129">Carpeta compartida</span><span class="sxs-lookup"><span data-stu-id="1b59f-129">Shared folder</span></span>  <br/> |<span data-ttu-id="1b59f-130">Requiere la **misma** carpeta compartida en todos los dispositivos</span><span class="sxs-lookup"><span data-stu-id="1b59f-130">Requires the **same** shared folder across appliances</span></span> <br/> |<span data-ttu-id="1b59f-131">Requiere una carpeta compartida **distinta** en cada dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1b59f-131">Requires a **different** shared folder across appliances</span></span> <br/> |
|<span data-ttu-id="1b59f-132">Configuración</span><span class="sxs-lookup"><span data-stu-id="1b59f-132">Configure</span></span>  <br/> |<span data-ttu-id="1b59f-133">VirtualMachineDomain</span><span class="sxs-lookup"><span data-stu-id="1b59f-133">VirtualMachineDomain</span></span>  <br/> |<span data-ttu-id="1b59f-134">Requiere el **mismo** dominio en todos los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="1b59f-134">Requires the **same** domain across appliances</span></span> <br/> |<span data-ttu-id="1b59f-135">Requiere el **mismo** dominio en todos los sitios de RTC.</span><span class="sxs-lookup"><span data-stu-id="1b59f-135">Requires the **same** domain across PSTN sites</span></span> <br/> |
|<span data-ttu-id="1b59f-136">Configuración</span><span class="sxs-lookup"><span data-stu-id="1b59f-136">Configure</span></span>  <br/> |<span data-ttu-id="1b59f-137">SIPDomains</span><span class="sxs-lookup"><span data-stu-id="1b59f-137">SIPDomains</span></span>  <br/> |<span data-ttu-id="1b59f-138">Los nombres de dominio y el orden deben ser los **mismos** en todos los dispositivos</span><span class="sxs-lookup"><span data-stu-id="1b59f-138">Domain names and order should be the **same** across appliances</span></span> <br/> |<span data-ttu-id="1b59f-139">Los nombres de dominio y el orden deben ser **iguales** en sitios de la RTC</span><span class="sxs-lookup"><span data-stu-id="1b59f-139">Domain names and order should be the **same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="1b59f-140">Configuración</span><span class="sxs-lookup"><span data-stu-id="1b59f-140">Configure</span></span>  <br/> |<span data-ttu-id="1b59f-141">Nombre del sitio</span><span class="sxs-lookup"><span data-stu-id="1b59f-141">Site name</span></span>  <br/> |<span data-ttu-id="1b59f-142">Un nombre del sitio **igual** en todos los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="1b59f-142">**Same** Site Name across appliances</span></span> <br/> |<span data-ttu-id="1b59f-143">Un nombre del sitio **diferente** en todos los sitios de RTC.</span><span class="sxs-lookup"><span data-stu-id="1b59f-143">**Different** Site Name across PSTN sites</span></span> <br/> |
|<span data-ttu-id="1b59f-144">Configuración</span><span class="sxs-lookup"><span data-stu-id="1b59f-144">Configure</span></span>  <br/> |<span data-ttu-id="1b59f-145">Nombres de servidores</span><span class="sxs-lookup"><span data-stu-id="1b59f-145">Server names</span></span>  <br/> |<span data-ttu-id="1b59f-146">**Diferentes** en todos los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="1b59f-146">**Different** across appliances</span></span> <br/> |<span data-ttu-id="1b59f-147">**Diferentes** en todos los sitios de RTC.</span><span class="sxs-lookup"><span data-stu-id="1b59f-147">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="1b59f-148">Configuración</span><span class="sxs-lookup"><span data-stu-id="1b59f-148">Configure</span></span>  <br/> |<span data-ttu-id="1b59f-149">FQDN del grupo interno</span><span class="sxs-lookup"><span data-stu-id="1b59f-149">Internal pool FQDNs</span></span>  <br/> |<span data-ttu-id="1b59f-150">**Iguales** en todos los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="1b59f-150">**Same** across appliances</span></span> <br/> |<span data-ttu-id="1b59f-151">**Iguales** en todos los sitios de RTC.</span><span class="sxs-lookup"><span data-stu-id="1b59f-151">**Same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="1b59f-152">Configuración</span><span class="sxs-lookup"><span data-stu-id="1b59f-152">Configure</span></span>  <br/> |<span data-ttu-id="1b59f-153">IP internas</span><span class="sxs-lookup"><span data-stu-id="1b59f-153">Internal IPs</span></span>  <br/> |<span data-ttu-id="1b59f-154">**Diferentes** en todos los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="1b59f-154">**Different** across appliances</span></span> <br/> |<span data-ttu-id="1b59f-155">**Diferentes** en todos los sitios de RTC.</span><span class="sxs-lookup"><span data-stu-id="1b59f-155">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="1b59f-156">Configuración</span><span class="sxs-lookup"><span data-stu-id="1b59f-156">Configure</span></span>  <br/> |<span data-ttu-id="1b59f-157">FQDN externo</span><span class="sxs-lookup"><span data-stu-id="1b59f-157">External FQDN</span></span>  <br/> |<span data-ttu-id="1b59f-158">**Igual** en todos los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="1b59f-158">**Same** across appliances</span></span> <br/> |<span data-ttu-id="1b59f-159">**Diferente** en todos los sitios de RTC.</span><span class="sxs-lookup"><span data-stu-id="1b59f-159">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="1b59f-160">Configuración</span><span class="sxs-lookup"><span data-stu-id="1b59f-160">Configure</span></span>  <br/> |<span data-ttu-id="1b59f-161">IP externas</span><span class="sxs-lookup"><span data-stu-id="1b59f-161">External IPs</span></span>  <br/> |<span data-ttu-id="1b59f-162">**Diferentes** en todos los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="1b59f-162">**Different** across appliances</span></span> <br/> |<span data-ttu-id="1b59f-163">**Diferentes** en todos los sitios de RTC.</span><span class="sxs-lookup"><span data-stu-id="1b59f-163">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="1b59f-164">Configuración</span><span class="sxs-lookup"><span data-stu-id="1b59f-164">Configure</span></span>  <br/> |<span data-ttu-id="1b59f-165">Configuración de la puerta de enlace RTC</span><span class="sxs-lookup"><span data-stu-id="1b59f-165">PSTN GW settings</span></span>  <br/> |<span data-ttu-id="1b59f-166">**Igual** en todos los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="1b59f-166">**Same** across appliances</span></span> <br/> |<span data-ttu-id="1b59f-167">**Diferente** en todos los sitios de RTC.</span><span class="sxs-lookup"><span data-stu-id="1b59f-167">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="1b59f-168">Configuración</span><span class="sxs-lookup"><span data-stu-id="1b59f-168">Configure</span></span>  <br/> |<span data-ttu-id="1b59f-169">Registro DNS</span><span class="sxs-lookup"><span data-stu-id="1b59f-169">DNS record</span></span>  <br/> |<span data-ttu-id="1b59f-170">Agregar registros con los **mismos** FQDN de acceso externo y **diferentes** direcciones IP</span><span class="sxs-lookup"><span data-stu-id="1b59f-170">Add records with the **same** External Access FQDNs and **different** IP addresses</span></span> <br/> |<span data-ttu-id="1b59f-171">Agregar registros con **diferentes** FQDN de acceso externo y **diferentes** direcciones IP</span><span class="sxs-lookup"><span data-stu-id="1b59f-171">Add records with **different** External Access FQDNs and **different** IP addresses</span></span> <br/> |
|<span data-ttu-id="1b59f-172">Configuración</span><span class="sxs-lookup"><span data-stu-id="1b59f-172">Setup</span></span>  <br/> |<span data-ttu-id="1b59f-173">Inquilino híbrido</span><span class="sxs-lookup"><span data-stu-id="1b59f-173">Hybrid tenant</span></span>  <br/> |<span data-ttu-id="1b59f-174">Configurar HybridPSTNSite</span><span class="sxs-lookup"><span data-stu-id="1b59f-174">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="1b59f-175">Configurar PeerDestination para la reserva</span><span class="sxs-lookup"><span data-stu-id="1b59f-175">Set PeerDestination for fallback</span></span>  <br/> |<span data-ttu-id="1b59f-176">Configurar HybridPSTNSite</span><span class="sxs-lookup"><span data-stu-id="1b59f-176">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="1b59f-177">Configurar PeerDestination para la reserva</span><span class="sxs-lookup"><span data-stu-id="1b59f-177">Set PeerDestination for fallback</span></span>  <br/> |
|<span data-ttu-id="1b59f-178">Configuración</span><span class="sxs-lookup"><span data-stu-id="1b59f-178">Setup</span></span>  <br/> |<span data-ttu-id="1b59f-179">Puerta</span><span class="sxs-lookup"><span data-stu-id="1b59f-179">Gateway</span></span>  <br/> |<span data-ttu-id="1b59f-180">Asignación de MS GW **M:N** en este sitio</span><span class="sxs-lookup"><span data-stu-id="1b59f-180">MS GW **M:N** mapping in this site</span></span> <br/> |<span data-ttu-id="1b59f-181">Las puertas de enlace RTC en cada sitio RTC deben conectarse solamente a los servidores de mediación en el mismo sitio.</span><span class="sxs-lookup"><span data-stu-id="1b59f-181">PSTN gateway(s) in each PSTN site should only connect to the Mediation Server(s) in the same site</span></span>  <br/> |
|<span data-ttu-id="1b59f-182">Configuración</span><span class="sxs-lookup"><span data-stu-id="1b59f-182">Setup</span></span>  <br/> |<span data-ttu-id="1b59f-183">Usuario</span><span class="sxs-lookup"><span data-stu-id="1b59f-183">User</span></span>  <br/> |<span data-ttu-id="1b59f-184">Configurar UserPSTNSettings</span><span class="sxs-lookup"><span data-stu-id="1b59f-184">Set UserPSTNSettings</span></span>  <br/> |<span data-ttu-id="1b59f-185">Configurar UserPSTNSettings</span><span class="sxs-lookup"><span data-stu-id="1b59f-185">Set UserPSTNSettings</span></span>  <br/> |
   

