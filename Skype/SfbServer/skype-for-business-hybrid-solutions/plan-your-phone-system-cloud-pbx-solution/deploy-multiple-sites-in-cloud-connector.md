---
title: Implementar varios sitios en Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e62413fd-f68e-4825-8384-c983076bdf23
description: Obtenga información sobre la implementación de varios sitios de RTC en la nube conector Edition.
ms.openlocfilehash: 194eaf0b68489b37a5ab1fc2d5d501177edd0b35
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32227904"
---
# <a name="deploy-multiple-sites-in-cloud-connector"></a><span data-ttu-id="d68b1-103">Implementar varios sitios en Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="d68b1-103">Deploy multiple sites in Cloud Connector</span></span>
 
<span data-ttu-id="d68b1-104">Obtenga información sobre la implementación de varios sitios de RTC en la nube conector Edition.</span><span class="sxs-lookup"><span data-stu-id="d68b1-104">Learn about deploying multiple PSTN sites in Cloud Connector Edition.</span></span>
  
<span data-ttu-id="d68b1-p101">En esta sección se describe cómo implementar varios sitios de red telefónica conmutada (RTC). Los sitios se implementan de uno en uno siguiendo los mismos pasos que para la implementación de un único sitio. En este tema se describen las consideraciones para los sitios y las diferencias entre ellos en una implementación de varios sitios. </span><span class="sxs-lookup"><span data-stu-id="d68b1-p101">This section describes how to deploy multiple Public Switched Telephone Network (PSTN) sites. Sites are deployed one at a time using the same steps as deploying a single site. This topic describes the considerations for and differences between sites in a multiple site deployment.</span></span> 
  
## <a name="multiple-public-switched-telephone-network-pstn-sites"></a><span data-ttu-id="d68b1-108">Varios sitios de red telefónica conmutada (RTC)</span><span class="sxs-lookup"><span data-stu-id="d68b1-108">Multiple Public Switched Telephone Network (PSTN) Sites</span></span>

<span data-ttu-id="d68b1-109">A continuación muestra un ejemplo de configuración para implementar Skype para Business Edition de conector en la nube para distintos sitios de RTC.</span><span class="sxs-lookup"><span data-stu-id="d68b1-109">The following shows an example configuration to deploy Skype for Business Cloud Connector Edition for different PSTN sites.</span></span> <span data-ttu-id="d68b1-110">Asegúrese de que los parámetros de configuración sean correctos antes de comenzar con una implementación.</span><span class="sxs-lookup"><span data-stu-id="d68b1-110">Make sure your configuration settings are correct before you start a deployment.</span></span>
  
<span data-ttu-id="d68b1-111">Sitio de RTC 1</span><span class="sxs-lookup"><span data-stu-id="d68b1-111">PSTN Site 1</span></span>
  
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

<span data-ttu-id="d68b1-112">Sitio de RTC 2</span><span class="sxs-lookup"><span data-stu-id="d68b1-112">PSTN Site 2</span></span>
  
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

<span data-ttu-id="d68b1-113">Para cada sitio de RTC que desee agregar, siga los pasos de [implementar un sitio de conector en la nube](deploy-a-single-site-in-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="d68b1-113">For each PSTN site that you want to add, follow the steps in [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d68b1-114">La carpeta compartida para preparar la alta disponibilidad (HA) es por cada sitio RTC.</span><span class="sxs-lookup"><span data-stu-id="d68b1-114">The shared folder for preparing High Availability (HA) is per PSTN site.</span></span> <span data-ttu-id="d68b1-115">La carpeta compartida **debe** ser diferente en cada sitio RTC.</span><span class="sxs-lookup"><span data-stu-id="d68b1-115">The shared folder **must** be different between PSTN sites.</span></span> <span data-ttu-id="d68b1-116">No use la misma carpeta compartida para varios sites.></span><span class="sxs-lookup"><span data-stu-id="d68b1-116">Do not use the same shared folder for multiple sites.></span></span> 
  
## <a name="single-site-with-high-availability-ha-compared-to-multi-site-deployments"></a><span data-ttu-id="d68b1-117">Sitio único con alta disponibilidad (HA) comparado con implementaciones de varios sitios</span><span class="sxs-lookup"><span data-stu-id="d68b1-117">Single site with High Availability (HA) compared to multi-site deployments</span></span>
<span data-ttu-id="d68b1-118"><a name="BKMK_SingleSitecomparedtomulti-site"> </a></span><span class="sxs-lookup"><span data-stu-id="d68b1-118"></span></span>

<span data-ttu-id="d68b1-119">En la siguiente tabla se muestran las diferencias entre un sitio único compatible con HA y una implementación de varios sitios.</span><span class="sxs-lookup"><span data-stu-id="d68b1-119">The following table lists the differences between single site with HA support and a multiple site deployment.</span></span>
  
|<span data-ttu-id="d68b1-120">**Categoría**</span><span class="sxs-lookup"><span data-stu-id="d68b1-120">**Category**</span></span>|<span data-ttu-id="d68b1-121">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="d68b1-121">**Item**</span></span>|<span data-ttu-id="d68b1-122">**Sitio único con HA**</span><span class="sxs-lookup"><span data-stu-id="d68b1-122">**Single-Site with HA**</span></span>|<span data-ttu-id="d68b1-123">**Varios sitios**</span><span class="sxs-lookup"><span data-stu-id="d68b1-123">**Multi-Site**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d68b1-124">Configuración</span><span class="sxs-lookup"><span data-stu-id="d68b1-124">Configure</span></span>  <br/> |<span data-ttu-id="d68b1-125">Nombre de Host del dispositivo</span><span class="sxs-lookup"><span data-stu-id="d68b1-125">Appliance Host Name</span></span> <br/> |<span data-ttu-id="d68b1-126">**Diferentes** en todos los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="d68b1-126">**Different** across appliances</span></span> <br/> |<span data-ttu-id="d68b1-127">**Diferentes** en todos los sitios de RTC.</span><span class="sxs-lookup"><span data-stu-id="d68b1-127">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="d68b1-128">Configuración</span><span class="sxs-lookup"><span data-stu-id="d68b1-128">Setup</span></span>  <br/> |<span data-ttu-id="d68b1-129">Carpeta compartida</span><span class="sxs-lookup"><span data-stu-id="d68b1-129">Shared folder</span></span>  <br/> |<span data-ttu-id="d68b1-130">Requiere la **misma** carpeta compartida a través de dispositivos</span><span class="sxs-lookup"><span data-stu-id="d68b1-130">Requires the **same** shared folder across appliances</span></span> <br/> |<span data-ttu-id="d68b1-131">Requiere una carpeta compartida **distinta** en cada dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d68b1-131">Requires a **different** shared folder across appliances</span></span> <br/> |
|<span data-ttu-id="d68b1-132">Configuración</span><span class="sxs-lookup"><span data-stu-id="d68b1-132">Configure</span></span>  <br/> |<span data-ttu-id="d68b1-133">VirtualMachineDomain</span><span class="sxs-lookup"><span data-stu-id="d68b1-133">VirtualMachineDomain</span></span>  <br/> |<span data-ttu-id="d68b1-134">Requiere el **mismo** dominio en todos los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="d68b1-134">Requires the **same** domain across appliances</span></span> <br/> |<span data-ttu-id="d68b1-135">Requiere el **mismo** dominio en todos los sitios de RTC.</span><span class="sxs-lookup"><span data-stu-id="d68b1-135">Requires the **same** domain across PSTN sites</span></span> <br/> |
|<span data-ttu-id="d68b1-136">Configuración</span><span class="sxs-lookup"><span data-stu-id="d68b1-136">Configure</span></span>  <br/> |<span data-ttu-id="d68b1-137">SIPDomains</span><span class="sxs-lookup"><span data-stu-id="d68b1-137">SIPDomains</span></span>  <br/> |<span data-ttu-id="d68b1-138">Orden y nombres de dominio deben ser el **mismo** a través de dispositivos</span><span class="sxs-lookup"><span data-stu-id="d68b1-138">Domain names and order should be the **same** across appliances</span></span> <br/> |<span data-ttu-id="d68b1-139">Orden y nombres de dominio deben ser el **mismo** en todos los sitios de RTC</span><span class="sxs-lookup"><span data-stu-id="d68b1-139">Domain names and order should be the **same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="d68b1-140">Configuración</span><span class="sxs-lookup"><span data-stu-id="d68b1-140">Configure</span></span>  <br/> |<span data-ttu-id="d68b1-141">Nombre del sitio</span><span class="sxs-lookup"><span data-stu-id="d68b1-141">Site name</span></span>  <br/> |<span data-ttu-id="d68b1-142">Un nombre del sitio **igual** en todos los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="d68b1-142">**Same** Site Name across appliances</span></span> <br/> |<span data-ttu-id="d68b1-143">Un nombre del sitio **diferente** en todos los sitios de RTC.</span><span class="sxs-lookup"><span data-stu-id="d68b1-143">**Different** Site Name across PSTN sites</span></span> <br/> |
|<span data-ttu-id="d68b1-144">Configuración</span><span class="sxs-lookup"><span data-stu-id="d68b1-144">Configure</span></span>  <br/> |<span data-ttu-id="d68b1-145">Nombres de servidores</span><span class="sxs-lookup"><span data-stu-id="d68b1-145">Server names</span></span>  <br/> |<span data-ttu-id="d68b1-146">**Diferentes** en todos los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="d68b1-146">**Different** across appliances</span></span> <br/> |<span data-ttu-id="d68b1-147">**Diferentes** en todos los sitios de RTC.</span><span class="sxs-lookup"><span data-stu-id="d68b1-147">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="d68b1-148">Configuración</span><span class="sxs-lookup"><span data-stu-id="d68b1-148">Configure</span></span>  <br/> |<span data-ttu-id="d68b1-149">FQDN del grupo interno</span><span class="sxs-lookup"><span data-stu-id="d68b1-149">Internal pool FQDNs</span></span>  <br/> |<span data-ttu-id="d68b1-150">**Iguales** en todos los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="d68b1-150">**Same** across appliances</span></span> <br/> |<span data-ttu-id="d68b1-151">**Iguales** en todos los sitios de RTC.</span><span class="sxs-lookup"><span data-stu-id="d68b1-151">**Same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="d68b1-152">Configuración</span><span class="sxs-lookup"><span data-stu-id="d68b1-152">Configure</span></span>  <br/> |<span data-ttu-id="d68b1-153">IP internas</span><span class="sxs-lookup"><span data-stu-id="d68b1-153">Internal IPs</span></span>  <br/> |<span data-ttu-id="d68b1-154">**Diferentes** en todos los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="d68b1-154">**Different** across appliances</span></span> <br/> |<span data-ttu-id="d68b1-155">**Diferentes** en todos los sitios de RTC.</span><span class="sxs-lookup"><span data-stu-id="d68b1-155">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="d68b1-156">Configuración</span><span class="sxs-lookup"><span data-stu-id="d68b1-156">Configure</span></span>  <br/> |<span data-ttu-id="d68b1-157">FQDN externo</span><span class="sxs-lookup"><span data-stu-id="d68b1-157">External FQDN</span></span>  <br/> |<span data-ttu-id="d68b1-158">**Igual** en todos los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="d68b1-158">**Same** across appliances</span></span> <br/> |<span data-ttu-id="d68b1-159">**Diferente** en todos los sitios de RTC.</span><span class="sxs-lookup"><span data-stu-id="d68b1-159">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="d68b1-160">Configuración</span><span class="sxs-lookup"><span data-stu-id="d68b1-160">Configure</span></span>  <br/> |<span data-ttu-id="d68b1-161">IP externas</span><span class="sxs-lookup"><span data-stu-id="d68b1-161">External IPs</span></span>  <br/> |<span data-ttu-id="d68b1-162">**Diferentes** en todos los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="d68b1-162">**Different** across appliances</span></span> <br/> |<span data-ttu-id="d68b1-163">**Diferentes** en todos los sitios de RTC.</span><span class="sxs-lookup"><span data-stu-id="d68b1-163">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="d68b1-164">Configuración</span><span class="sxs-lookup"><span data-stu-id="d68b1-164">Configure</span></span>  <br/> |<span data-ttu-id="d68b1-165">Configuración de la puerta de enlace RTC</span><span class="sxs-lookup"><span data-stu-id="d68b1-165">PSTN GW settings</span></span>  <br/> |<span data-ttu-id="d68b1-166">**Igual** en todos los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="d68b1-166">**Same** across appliances</span></span> <br/> |<span data-ttu-id="d68b1-167">**Diferente** en todos los sitios de RTC.</span><span class="sxs-lookup"><span data-stu-id="d68b1-167">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="d68b1-168">Configuración</span><span class="sxs-lookup"><span data-stu-id="d68b1-168">Configure</span></span>  <br/> |<span data-ttu-id="d68b1-169">Registro DNS</span><span class="sxs-lookup"><span data-stu-id="d68b1-169">DNS record</span></span>  <br/> |<span data-ttu-id="d68b1-170">Agregar registros con el **mismo** FQDN externos de acceso y direcciones IP **diferentes**</span><span class="sxs-lookup"><span data-stu-id="d68b1-170">Add records with the **same** External Access FQDNs and **different** IP addresses</span></span> <br/> |<span data-ttu-id="d68b1-171">Agregar registros con **diferentes** FQDN de acceso externo y **diferentes** direcciones IP</span><span class="sxs-lookup"><span data-stu-id="d68b1-171">Add records with **different** External Access FQDNs and **different** IP addresses</span></span> <br/> |
|<span data-ttu-id="d68b1-172">Configuración</span><span class="sxs-lookup"><span data-stu-id="d68b1-172">Setup</span></span>  <br/> |<span data-ttu-id="d68b1-173">Inquilino híbrida</span><span class="sxs-lookup"><span data-stu-id="d68b1-173">Hybrid tenant</span></span>  <br/> |<span data-ttu-id="d68b1-174">Configurar HybridPSTNSite</span><span class="sxs-lookup"><span data-stu-id="d68b1-174">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="d68b1-175">Configurar PeerDestination para la reserva</span><span class="sxs-lookup"><span data-stu-id="d68b1-175">Set PeerDestination for fallback</span></span>  <br/> |<span data-ttu-id="d68b1-176">Configurar HybridPSTNSite</span><span class="sxs-lookup"><span data-stu-id="d68b1-176">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="d68b1-177">Configurar PeerDestination para la reserva</span><span class="sxs-lookup"><span data-stu-id="d68b1-177">Set PeerDestination for fallback</span></span>  <br/> |
|<span data-ttu-id="d68b1-178">Configuración</span><span class="sxs-lookup"><span data-stu-id="d68b1-178">Setup</span></span>  <br/> |<span data-ttu-id="d68b1-179">Puerta de enlace</span><span class="sxs-lookup"><span data-stu-id="d68b1-179">Gateway</span></span>  <br/> |<span data-ttu-id="d68b1-180">Asignación de MS GW **M:N** en este sitio</span><span class="sxs-lookup"><span data-stu-id="d68b1-180">MS GW **M:N** mapping in this site</span></span> <br/> |<span data-ttu-id="d68b1-181">Las puertas de enlace RTC en cada sitio RTC deben conectarse solamente a los servidores de mediación en el mismo sitio.</span><span class="sxs-lookup"><span data-stu-id="d68b1-181">PSTN gateway(s) in each PSTN site should only connect to the Mediation Server(s) in the same site</span></span>  <br/> |
|<span data-ttu-id="d68b1-182">Configuración</span><span class="sxs-lookup"><span data-stu-id="d68b1-182">Setup</span></span>  <br/> |<span data-ttu-id="d68b1-183">Usuario</span><span class="sxs-lookup"><span data-stu-id="d68b1-183">User</span></span>  <br/> |<span data-ttu-id="d68b1-184">Configurar UserPSTNSettings</span><span class="sxs-lookup"><span data-stu-id="d68b1-184">Set UserPSTNSettings</span></span>  <br/> |<span data-ttu-id="d68b1-185">Configurar UserPSTNSettings</span><span class="sxs-lookup"><span data-stu-id="d68b1-185">Set UserPSTNSettings</span></span>  <br/> |
   

