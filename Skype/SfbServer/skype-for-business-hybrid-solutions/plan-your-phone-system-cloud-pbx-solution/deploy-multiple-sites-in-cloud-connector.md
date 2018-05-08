---
title: Implementar varios sitios en Cloud Connector
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e62413fd-f68e-4825-8384-c983076bdf23
description: Obtenga información sobre la implementación de varios sitios de RTC en la nube conector Edition.
ms.openlocfilehash: 2bc56f2cdff3f852bf2557fc3ae98e1a2f8fa854
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="deploy-multiple-sites-in-cloud-connector"></a><span data-ttu-id="c9d2f-103">Implementar varios sitios en Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="c9d2f-103">Deploy multiple sites in Cloud Connector</span></span>
 
<span data-ttu-id="c9d2f-104">Obtenga información sobre la implementación de varios sitios de RTC en la nube conector Edition.</span><span class="sxs-lookup"><span data-stu-id="c9d2f-104">Learn about deploying multiple PSTN sites in Cloud Connector Edition.</span></span>
  
<span data-ttu-id="c9d2f-p101">En esta sección se describe cómo implementar varios sitios de red telefónica conmutada (RTC). Los sitios se implementan de uno en uno siguiendo los mismos pasos que para la implementación de un único sitio. En este tema se describen las consideraciones para los sitios y las diferencias entre ellos en una implementación de varios sitios. </span><span class="sxs-lookup"><span data-stu-id="c9d2f-p101">This section describes how to deploy multiple Public Switched Telephone Network (PSTN) sites. Sites are deployed one at a time using the same steps as deploying a single site. This topic describes the considerations for and differences between sites in a multiple site deployment.</span></span> 
  
## <a name="multiple-public-switched-telephone-network-pstn-sites"></a><span data-ttu-id="c9d2f-108">Varios sitios de red telefónica conmutada (RTC)</span><span class="sxs-lookup"><span data-stu-id="c9d2f-108">Multiple Public Switched Telephone Network (PSTN) Sites</span></span>

<span data-ttu-id="c9d2f-109">A continuación muestra un ejemplo de configuración para implementar Skype para Business Edition de conector en la nube para distintos sitios de RTC.</span><span class="sxs-lookup"><span data-stu-id="c9d2f-109">The following shows an example configuration to deploy Skype for Business Cloud Connector Edition for different PSTN sites.</span></span> <span data-ttu-id="c9d2f-110">Asegúrese de que los parámetros de configuración sean correctos antes de comenzar con una implementación.</span><span class="sxs-lookup"><span data-stu-id="c9d2f-110">Make sure your configuration settings are correct before you start a deployment.</span></span>
  
<span data-ttu-id="c9d2f-111">Sitio de RTC 1</span><span class="sxs-lookup"><span data-stu-id="c9d2f-111">PSTN Site 1</span></span>
  
```
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

<span data-ttu-id="c9d2f-112">Sitio RTC 2</span><span class="sxs-lookup"><span data-stu-id="c9d2f-112">PSTN Site 2</span></span>
  
```
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

<span data-ttu-id="c9d2f-113">Para cada sitio de RTC que desee agregar, siga los pasos de [implementar un sitio de conector en la nube](deploy-a-single-site-in-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="c9d2f-113">For each PSTN site that you want to add, follow the steps in [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="c9d2f-114">La carpeta compartida para preparar la alta disponibilidad (HA) es por cada sitio RTC.</span><span class="sxs-lookup"><span data-stu-id="c9d2f-114">The shared folder for preparing High Availability (HA) is per PSTN site.</span></span> <span data-ttu-id="c9d2f-115">La carpeta compartida **debe** ser diferente en cada sitio RTC.</span><span class="sxs-lookup"><span data-stu-id="c9d2f-115">The shared folder **must** be different between PSTN sites.</span></span> <span data-ttu-id="c9d2f-116">No use la misma carpeta compartida para varios sitios. ></span><span class="sxs-lookup"><span data-stu-id="c9d2f-116">Do not use the same shared folder for multiple sites.></span></span> 
  
## <a name="single-site-with-high-availability-ha-compared-to-multi-site-deployments"></a><span data-ttu-id="c9d2f-117">Sitio único con alta disponibilidad (HA) comparado con implementaciones de varios sitios</span><span class="sxs-lookup"><span data-stu-id="c9d2f-117">Single site with High Availability (HA) compared to multi-site deployments</span></span>
<span data-ttu-id="c9d2f-118"><a name="BKMK_SingleSitecomparedtomulti-site"> </a></span><span class="sxs-lookup"><span data-stu-id="c9d2f-118"></span></span>

<span data-ttu-id="c9d2f-119">En la siguiente tabla se muestran las diferencias entre un sitio único compatible con HA y una implementación de varios sitios.</span><span class="sxs-lookup"><span data-stu-id="c9d2f-119">The following table lists the differences between single site with HA support and a multiple site deployment.</span></span>
  
|<span data-ttu-id="c9d2f-120">**Categoría**</span><span class="sxs-lookup"><span data-stu-id="c9d2f-120">**Category**</span></span>|<span data-ttu-id="c9d2f-121">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="c9d2f-121">**Item**</span></span>|<span data-ttu-id="c9d2f-122">**Sitio único con alta disponibilidad**</span><span class="sxs-lookup"><span data-stu-id="c9d2f-122">**Single-Site with HA**</span></span>|<span data-ttu-id="c9d2f-123">**Múltiples sitios**</span><span class="sxs-lookup"><span data-stu-id="c9d2f-123">**Multi-Site**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c9d2f-124">Configuración</span><span class="sxs-lookup"><span data-stu-id="c9d2f-124">Setup</span></span>  <br/> |<span data-ttu-id="c9d2f-125">Carpeta compartida</span><span class="sxs-lookup"><span data-stu-id="c9d2f-125">Shared folder</span></span>  <br/> |<span data-ttu-id="c9d2f-126">Requiere la **misma** carpeta compartida a través de dispositivos</span><span class="sxs-lookup"><span data-stu-id="c9d2f-126">Requires the **same** shared folder across appliances</span></span> <br/> |<span data-ttu-id="c9d2f-127">Requiere una carpeta compartida **distinta** en cada dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c9d2f-127">Requires a **different** shared folder across appliances</span></span> <br/> |
|<span data-ttu-id="c9d2f-128">Configuración</span><span class="sxs-lookup"><span data-stu-id="c9d2f-128">Configure</span></span>  <br/> |<span data-ttu-id="c9d2f-129">VirtualMachineDomain</span><span class="sxs-lookup"><span data-stu-id="c9d2f-129">VirtualMachineDomain</span></span>  <br/> |<span data-ttu-id="c9d2f-130">Requiere el **mismo** dominio en todos los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="c9d2f-130">Requires the **same** domain across appliances</span></span> <br/> |<span data-ttu-id="c9d2f-131">Requiere el **mismo** dominio en todos los sitios de RTC.</span><span class="sxs-lookup"><span data-stu-id="c9d2f-131">Requires the **same** domain across PSTN sites</span></span> <br/> |
|<span data-ttu-id="c9d2f-132">Configurar</span><span class="sxs-lookup"><span data-stu-id="c9d2f-132">Configure</span></span>  <br/> |<span data-ttu-id="c9d2f-133">SIPDomains</span><span class="sxs-lookup"><span data-stu-id="c9d2f-133">SIPDomains</span></span>  <br/> |<span data-ttu-id="c9d2f-134">Orden y nombres de dominio deben ser el **mismo** a través de dispositivos</span><span class="sxs-lookup"><span data-stu-id="c9d2f-134">Domain names and order should be the **same** across appliances</span></span> <br/> |<span data-ttu-id="c9d2f-135">Orden y nombres de dominio deben ser el **mismo** en todos los sitios de RTC</span><span class="sxs-lookup"><span data-stu-id="c9d2f-135">Domain names and order should be the **same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="c9d2f-136">Configurar</span><span class="sxs-lookup"><span data-stu-id="c9d2f-136">Configure</span></span>  <br/> |<span data-ttu-id="c9d2f-137">Nombre del sitio</span><span class="sxs-lookup"><span data-stu-id="c9d2f-137">Site name</span></span>  <br/> |<span data-ttu-id="c9d2f-138">Un nombre del sitio **igual** en todos los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="c9d2f-138">**Same** Site Name across appliances</span></span> <br/> |<span data-ttu-id="c9d2f-139">Un nombre del sitio **diferente** en todos los sitios de RTC.</span><span class="sxs-lookup"><span data-stu-id="c9d2f-139">**Different** Site Name across PSTN sites</span></span> <br/> |
|<span data-ttu-id="c9d2f-140">Configurar</span><span class="sxs-lookup"><span data-stu-id="c9d2f-140">Configure</span></span>  <br/> |<span data-ttu-id="c9d2f-141">Nombres de servidores</span><span class="sxs-lookup"><span data-stu-id="c9d2f-141">Server names</span></span>  <br/> |<span data-ttu-id="c9d2f-142">**Diferentes** en todos los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="c9d2f-142">**Different** across appliances</span></span> <br/> |<span data-ttu-id="c9d2f-143">**Diferentes** en todos los sitios de RTC.</span><span class="sxs-lookup"><span data-stu-id="c9d2f-143">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="c9d2f-144">Configurar</span><span class="sxs-lookup"><span data-stu-id="c9d2f-144">Configure</span></span>  <br/> |<span data-ttu-id="c9d2f-145">FQDN del grupo interno</span><span class="sxs-lookup"><span data-stu-id="c9d2f-145">Internal pool FQDNs</span></span>  <br/> |<span data-ttu-id="c9d2f-146">**Iguales** en todos los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="c9d2f-146">**Same** across appliances</span></span> <br/> |<span data-ttu-id="c9d2f-147">**Iguales** en todos los sitios de RTC.</span><span class="sxs-lookup"><span data-stu-id="c9d2f-147">**Same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="c9d2f-148">Configurar</span><span class="sxs-lookup"><span data-stu-id="c9d2f-148">Configure</span></span>  <br/> |<span data-ttu-id="c9d2f-149">IP internas</span><span class="sxs-lookup"><span data-stu-id="c9d2f-149">Internal IPs</span></span>  <br/> |<span data-ttu-id="c9d2f-150">**Diferentes** en todos los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="c9d2f-150">**Different** across appliances</span></span> <br/> |<span data-ttu-id="c9d2f-151">**Diferentes** en todos los sitios de RTC.</span><span class="sxs-lookup"><span data-stu-id="c9d2f-151">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="c9d2f-152">Configurar</span><span class="sxs-lookup"><span data-stu-id="c9d2f-152">Configure</span></span>  <br/> |<span data-ttu-id="c9d2f-153">FQDN externo</span><span class="sxs-lookup"><span data-stu-id="c9d2f-153">External FQDN</span></span>  <br/> |<span data-ttu-id="c9d2f-154">**Igual** en todos los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="c9d2f-154">**Same** across appliances</span></span> <br/> |<span data-ttu-id="c9d2f-155">**Diferente** en todos los sitios de RTC.</span><span class="sxs-lookup"><span data-stu-id="c9d2f-155">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="c9d2f-156">Configurar</span><span class="sxs-lookup"><span data-stu-id="c9d2f-156">Configure</span></span>  <br/> |<span data-ttu-id="c9d2f-157">IP externas</span><span class="sxs-lookup"><span data-stu-id="c9d2f-157">External IPs</span></span>  <br/> |<span data-ttu-id="c9d2f-158">**Diferentes** en todos los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="c9d2f-158">**Different** across appliances</span></span> <br/> |<span data-ttu-id="c9d2f-159">**Diferentes** en todos los sitios de RTC.</span><span class="sxs-lookup"><span data-stu-id="c9d2f-159">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="c9d2f-160">Configurar</span><span class="sxs-lookup"><span data-stu-id="c9d2f-160">Configure</span></span>  <br/> |<span data-ttu-id="c9d2f-161">Configuración de la puerta de enlace RTC</span><span class="sxs-lookup"><span data-stu-id="c9d2f-161">PSTN GW settings</span></span>  <br/> |<span data-ttu-id="c9d2f-162">**Igual** en todos los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="c9d2f-162">**Same** across appliances</span></span> <br/> |<span data-ttu-id="c9d2f-163">**Diferente** en todos los sitios de RTC.</span><span class="sxs-lookup"><span data-stu-id="c9d2f-163">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="c9d2f-164">Configurar</span><span class="sxs-lookup"><span data-stu-id="c9d2f-164">Configure</span></span>  <br/> |<span data-ttu-id="c9d2f-165">Registro DNS</span><span class="sxs-lookup"><span data-stu-id="c9d2f-165">DNS record</span></span>  <br/> |<span data-ttu-id="c9d2f-166">Agregar registros con el **mismo** FQDN externos de acceso y direcciones IP **diferentes**</span><span class="sxs-lookup"><span data-stu-id="c9d2f-166">Add records with the **same** External Access FQDNs and **different** IP addresses</span></span> <br/> |<span data-ttu-id="c9d2f-167">Agregar registros con **diferentes** FQDN de acceso externo y **diferentes** direcciones IP</span><span class="sxs-lookup"><span data-stu-id="c9d2f-167">Add records with **different** External Access FQDNs and **different** IP addresses</span></span> <br/> |
|<span data-ttu-id="c9d2f-168">Configuración</span><span class="sxs-lookup"><span data-stu-id="c9d2f-168">Setup</span></span>  <br/> |<span data-ttu-id="c9d2f-169">Inquilino híbrida</span><span class="sxs-lookup"><span data-stu-id="c9d2f-169">Hybrid tenant</span></span>  <br/> |<span data-ttu-id="c9d2f-170">Configurar HybridPSTNSite</span><span class="sxs-lookup"><span data-stu-id="c9d2f-170">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="c9d2f-171">Configurar PeerDestination para la reserva</span><span class="sxs-lookup"><span data-stu-id="c9d2f-171">Set PeerDestination for fallback</span></span>  <br/> |<span data-ttu-id="c9d2f-172">Configurar HybridPSTNSite</span><span class="sxs-lookup"><span data-stu-id="c9d2f-172">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="c9d2f-173">Configurar PeerDestination para la reserva</span><span class="sxs-lookup"><span data-stu-id="c9d2f-173">Set PeerDestination for fallback</span></span>  <br/> |
|<span data-ttu-id="c9d2f-174">Configuración</span><span class="sxs-lookup"><span data-stu-id="c9d2f-174">Setup</span></span>  <br/> |<span data-ttu-id="c9d2f-175">Puerta de enlace</span><span class="sxs-lookup"><span data-stu-id="c9d2f-175">Gateway</span></span>  <br/> |<span data-ttu-id="c9d2f-176">Asignación de MS GW **M:N** en este sitio</span><span class="sxs-lookup"><span data-stu-id="c9d2f-176">MS GW **M:N** mapping in this site</span></span> <br/> |<span data-ttu-id="c9d2f-177">Las puertas de enlace RTC en cada sitio RTC deben conectarse solamente a los servidores de mediación en el mismo sitio.</span><span class="sxs-lookup"><span data-stu-id="c9d2f-177">PSTN gateway(s) in each PSTN site should only connect to the Mediation Server(s) in the same site</span></span>  <br/> |
|<span data-ttu-id="c9d2f-178">Configuración</span><span class="sxs-lookup"><span data-stu-id="c9d2f-178">Setup</span></span>  <br/> |<span data-ttu-id="c9d2f-179">Usuario</span><span class="sxs-lookup"><span data-stu-id="c9d2f-179">User</span></span>  <br/> |<span data-ttu-id="c9d2f-180">Configurar UserPSTNSettings</span><span class="sxs-lookup"><span data-stu-id="c9d2f-180">Set UserPSTNSettings</span></span>  <br/> |<span data-ttu-id="c9d2f-181">Configurar UserPSTNSettings</span><span class="sxs-lookup"><span data-stu-id="c9d2f-181">Set UserPSTNSettings</span></span>  <br/> |
   

