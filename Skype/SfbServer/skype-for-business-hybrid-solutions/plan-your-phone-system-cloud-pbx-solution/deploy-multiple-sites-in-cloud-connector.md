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
ms.openlocfilehash: 98890bb3ffe53497c5e915acba5c073c4316f3b7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799700"
---
# <a name="deploy-multiple-sites-in-cloud-connector"></a><span data-ttu-id="9925c-103">Implementar varios sitios en Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="9925c-103">Deploy multiple sites in Cloud Connector</span></span>
 
<span data-ttu-id="9925c-104">Obtenga más información sobre cómo implementar varios sitios de RTC en Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="9925c-104">Learn about deploying multiple PSTN sites in Cloud Connector Edition.</span></span>
  
<span data-ttu-id="9925c-p101">En esta sección se describe cómo implementar varios sitios de red telefónica conmutada (RTC). Los sitios se implementan de uno en uno siguiendo los mismos pasos que para la implementación de un único sitio. En este tema se describen las consideraciones para los sitios y las diferencias entre ellos en una implementación de varios sitios. </span><span class="sxs-lookup"><span data-stu-id="9925c-p101">This section describes how to deploy multiple Public Switched Telephone Network (PSTN) sites. Sites are deployed one at a time using the same steps as deploying a single site. This topic describes the considerations for and differences between sites in a multiple site deployment.</span></span> 
  
## <a name="multiple-public-switched-telephone-network-pstn-sites"></a><span data-ttu-id="9925c-108">Varios sitios de red telefónica conmutada (RTC)</span><span class="sxs-lookup"><span data-stu-id="9925c-108">Multiple Public Switched Telephone Network (PSTN) Sites</span></span>

<span data-ttu-id="9925c-109">A continuación se muestra un ejemplo de configuración para implementar Skype empresarial Cloud Connector Edition para diferentes sitios de RTC.</span><span class="sxs-lookup"><span data-stu-id="9925c-109">The following shows an example configuration to deploy Skype for Business Cloud Connector Edition for different PSTN sites.</span></span> <span data-ttu-id="9925c-110">Asegúrese de que los parámetros de configuración sean correctos antes de comenzar con una implementación.</span><span class="sxs-lookup"><span data-stu-id="9925c-110">Make sure your configuration settings are correct before you start a deployment.</span></span>
  
<span data-ttu-id="9925c-111">Sitio de RTC 1</span><span class="sxs-lookup"><span data-stu-id="9925c-111">PSTN Site 1</span></span>
  
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

<span data-ttu-id="9925c-112">Sitio de RTC 2</span><span class="sxs-lookup"><span data-stu-id="9925c-112">PSTN Site 2</span></span>
  
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

<span data-ttu-id="9925c-113">Para cada sitio PSTN que desee agregar, siga los pasos que se indican en [implementar un único sitio en la nube Connector](deploy-a-single-site-in-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="9925c-113">For each PSTN site that you want to add, follow the steps in [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="9925c-114">La carpeta compartida para preparar la alta disponibilidad (HA) es por cada sitio RTC.</span><span class="sxs-lookup"><span data-stu-id="9925c-114">The shared folder for preparing High Availability (HA) is per PSTN site.</span></span> <span data-ttu-id="9925c-115">La carpeta compartida **debe** ser diferente en cada sitio RTC.</span><span class="sxs-lookup"><span data-stu-id="9925c-115">The shared folder **must** be different between PSTN sites.</span></span> <span data-ttu-id="9925c-116">No use la misma carpeta compartida para varios sitios. ></span><span class="sxs-lookup"><span data-stu-id="9925c-116">Do not use the same shared folder for multiple sites.></span></span> 
  
## <a name="single-site-with-high-availability-ha-compared-to-multi-site-deployments"></a><span data-ttu-id="9925c-117">Sitio único con alta disponibilidad (HA) comparado con implementaciones de varios sitios</span><span class="sxs-lookup"><span data-stu-id="9925c-117">Single site with High Availability (HA) compared to multi-site deployments</span></span>
<span data-ttu-id="9925c-118"><a name="BKMK_SingleSitecomparedtomulti-site"> </a></span><span class="sxs-lookup"><span data-stu-id="9925c-118"><a name="BKMK_SingleSitecomparedtomulti-site"> </a></span></span>

<span data-ttu-id="9925c-119">En la siguiente tabla se muestran las diferencias entre un sitio único compatible con HA y una implementación de varios sitios.</span><span class="sxs-lookup"><span data-stu-id="9925c-119">The following table lists the differences between single site with HA support and a multiple site deployment.</span></span>
  
|<span data-ttu-id="9925c-120">**Categoría**</span><span class="sxs-lookup"><span data-stu-id="9925c-120">**Category**</span></span>|<span data-ttu-id="9925c-121">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="9925c-121">**Item**</span></span>|<span data-ttu-id="9925c-122">**Sitio único con HA**</span><span class="sxs-lookup"><span data-stu-id="9925c-122">**Single-Site with HA**</span></span>|<span data-ttu-id="9925c-123">**Varios sitios**</span><span class="sxs-lookup"><span data-stu-id="9925c-123">**Multi-Site**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9925c-124">Configuración</span><span class="sxs-lookup"><span data-stu-id="9925c-124">Configure</span></span>  <br/> |<span data-ttu-id="9925c-125">Nombre de host del dispositivo</span><span class="sxs-lookup"><span data-stu-id="9925c-125">Appliance Host Name</span></span> <br/> |<span data-ttu-id="9925c-126">**Diferentes** en todos los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="9925c-126">**Different** across appliances</span></span> <br/> |<span data-ttu-id="9925c-127">**Diferentes** en todos los sitios de RTC.</span><span class="sxs-lookup"><span data-stu-id="9925c-127">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="9925c-128">Configuración</span><span class="sxs-lookup"><span data-stu-id="9925c-128">Setup</span></span>  <br/> |<span data-ttu-id="9925c-129">Carpeta compartida</span><span class="sxs-lookup"><span data-stu-id="9925c-129">Shared folder</span></span>  <br/> |<span data-ttu-id="9925c-130">Requiere la **misma** carpeta compartida en todos los dispositivos</span><span class="sxs-lookup"><span data-stu-id="9925c-130">Requires the **same** shared folder across appliances</span></span> <br/> |<span data-ttu-id="9925c-131">Requiere una carpeta compartida **distinta** en cada dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9925c-131">Requires a **different** shared folder across appliances</span></span> <br/> |
|<span data-ttu-id="9925c-132">Configuración</span><span class="sxs-lookup"><span data-stu-id="9925c-132">Configure</span></span>  <br/> |<span data-ttu-id="9925c-133">VirtualMachineDomain</span><span class="sxs-lookup"><span data-stu-id="9925c-133">VirtualMachineDomain</span></span>  <br/> |<span data-ttu-id="9925c-134">Requiere el **mismo** dominio en todos los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="9925c-134">Requires the **same** domain across appliances</span></span> <br/> |<span data-ttu-id="9925c-135">Requiere el **mismo** dominio en todos los sitios de RTC.</span><span class="sxs-lookup"><span data-stu-id="9925c-135">Requires the **same** domain across PSTN sites</span></span> <br/> |
|<span data-ttu-id="9925c-136">Configuración</span><span class="sxs-lookup"><span data-stu-id="9925c-136">Configure</span></span>  <br/> |<span data-ttu-id="9925c-137">SIPDomains</span><span class="sxs-lookup"><span data-stu-id="9925c-137">SIPDomains</span></span>  <br/> |<span data-ttu-id="9925c-138">Los nombres de dominio y el orden deben ser los **mismos** en todos los dispositivos</span><span class="sxs-lookup"><span data-stu-id="9925c-138">Domain names and order should be the **same** across appliances</span></span> <br/> |<span data-ttu-id="9925c-139">Los nombres de dominio y el orden deben ser **iguales** en sitios de la RTC</span><span class="sxs-lookup"><span data-stu-id="9925c-139">Domain names and order should be the **same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="9925c-140">Configuración</span><span class="sxs-lookup"><span data-stu-id="9925c-140">Configure</span></span>  <br/> |<span data-ttu-id="9925c-141">Nombre del sitio</span><span class="sxs-lookup"><span data-stu-id="9925c-141">Site name</span></span>  <br/> |<span data-ttu-id="9925c-142">Un nombre del sitio **igual** en todos los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="9925c-142">**Same** Site Name across appliances</span></span> <br/> |<span data-ttu-id="9925c-143">Un nombre del sitio **diferente** en todos los sitios de RTC.</span><span class="sxs-lookup"><span data-stu-id="9925c-143">**Different** Site Name across PSTN sites</span></span> <br/> |
|<span data-ttu-id="9925c-144">Configuración</span><span class="sxs-lookup"><span data-stu-id="9925c-144">Configure</span></span>  <br/> |<span data-ttu-id="9925c-145">Nombres de servidores</span><span class="sxs-lookup"><span data-stu-id="9925c-145">Server names</span></span>  <br/> |<span data-ttu-id="9925c-146">**Diferentes** en todos los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="9925c-146">**Different** across appliances</span></span> <br/> |<span data-ttu-id="9925c-147">**Diferentes** en todos los sitios de RTC.</span><span class="sxs-lookup"><span data-stu-id="9925c-147">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="9925c-148">Configuración</span><span class="sxs-lookup"><span data-stu-id="9925c-148">Configure</span></span>  <br/> |<span data-ttu-id="9925c-149">FQDN del grupo interno</span><span class="sxs-lookup"><span data-stu-id="9925c-149">Internal pool FQDNs</span></span>  <br/> |<span data-ttu-id="9925c-150">**Iguales** en todos los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="9925c-150">**Same** across appliances</span></span> <br/> |<span data-ttu-id="9925c-151">**Iguales** en todos los sitios de RTC.</span><span class="sxs-lookup"><span data-stu-id="9925c-151">**Same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="9925c-152">Configuración</span><span class="sxs-lookup"><span data-stu-id="9925c-152">Configure</span></span>  <br/> |<span data-ttu-id="9925c-153">IP internas</span><span class="sxs-lookup"><span data-stu-id="9925c-153">Internal IPs</span></span>  <br/> |<span data-ttu-id="9925c-154">**Diferentes** en todos los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="9925c-154">**Different** across appliances</span></span> <br/> |<span data-ttu-id="9925c-155">**Diferentes** en todos los sitios de RTC.</span><span class="sxs-lookup"><span data-stu-id="9925c-155">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="9925c-156">Configuración</span><span class="sxs-lookup"><span data-stu-id="9925c-156">Configure</span></span>  <br/> |<span data-ttu-id="9925c-157">FQDN externo</span><span class="sxs-lookup"><span data-stu-id="9925c-157">External FQDN</span></span>  <br/> |<span data-ttu-id="9925c-158">**Igual** en todos los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="9925c-158">**Same** across appliances</span></span> <br/> |<span data-ttu-id="9925c-159">**Diferente** en todos los sitios de RTC.</span><span class="sxs-lookup"><span data-stu-id="9925c-159">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="9925c-160">Configuración</span><span class="sxs-lookup"><span data-stu-id="9925c-160">Configure</span></span>  <br/> |<span data-ttu-id="9925c-161">IP externas</span><span class="sxs-lookup"><span data-stu-id="9925c-161">External IPs</span></span>  <br/> |<span data-ttu-id="9925c-162">**Diferentes** en todos los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="9925c-162">**Different** across appliances</span></span> <br/> |<span data-ttu-id="9925c-163">**Diferentes** en todos los sitios de RTC.</span><span class="sxs-lookup"><span data-stu-id="9925c-163">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="9925c-164">Configuración</span><span class="sxs-lookup"><span data-stu-id="9925c-164">Configure</span></span>  <br/> |<span data-ttu-id="9925c-165">Configuración de la puerta de enlace RTC</span><span class="sxs-lookup"><span data-stu-id="9925c-165">PSTN GW settings</span></span>  <br/> |<span data-ttu-id="9925c-166">**Igual** en todos los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="9925c-166">**Same** across appliances</span></span> <br/> |<span data-ttu-id="9925c-167">**Diferente** en todos los sitios de RTC.</span><span class="sxs-lookup"><span data-stu-id="9925c-167">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="9925c-168">Configuración</span><span class="sxs-lookup"><span data-stu-id="9925c-168">Configure</span></span>  <br/> |<span data-ttu-id="9925c-169">Registro DNS</span><span class="sxs-lookup"><span data-stu-id="9925c-169">DNS record</span></span>  <br/> |<span data-ttu-id="9925c-170">Agregar registros con los **mismos** FQDN de acceso externo y **diferentes** direcciones IP</span><span class="sxs-lookup"><span data-stu-id="9925c-170">Add records with the **same** External Access FQDNs and **different** IP addresses</span></span> <br/> |<span data-ttu-id="9925c-171">Agregar registros con **diferentes** FQDN de acceso externo y **diferentes** direcciones IP</span><span class="sxs-lookup"><span data-stu-id="9925c-171">Add records with **different** External Access FQDNs and **different** IP addresses</span></span> <br/> |
|<span data-ttu-id="9925c-172">Configuración</span><span class="sxs-lookup"><span data-stu-id="9925c-172">Setup</span></span>  <br/> |<span data-ttu-id="9925c-173">Inquilino híbrido</span><span class="sxs-lookup"><span data-stu-id="9925c-173">Hybrid tenant</span></span>  <br/> |<span data-ttu-id="9925c-174">Configurar HybridPSTNSite</span><span class="sxs-lookup"><span data-stu-id="9925c-174">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="9925c-175">Configurar PeerDestination para la reserva</span><span class="sxs-lookup"><span data-stu-id="9925c-175">Set PeerDestination for fallback</span></span>  <br/> |<span data-ttu-id="9925c-176">Configurar HybridPSTNSite</span><span class="sxs-lookup"><span data-stu-id="9925c-176">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="9925c-177">Configurar PeerDestination para la reserva</span><span class="sxs-lookup"><span data-stu-id="9925c-177">Set PeerDestination for fallback</span></span>  <br/> |
|<span data-ttu-id="9925c-178">Configuración</span><span class="sxs-lookup"><span data-stu-id="9925c-178">Setup</span></span>  <br/> |<span data-ttu-id="9925c-179">Puerta</span><span class="sxs-lookup"><span data-stu-id="9925c-179">Gateway</span></span>  <br/> |<span data-ttu-id="9925c-180">Asignación de MS GW **M:N** en este sitio</span><span class="sxs-lookup"><span data-stu-id="9925c-180">MS GW **M:N** mapping in this site</span></span> <br/> |<span data-ttu-id="9925c-181">Las puertas de enlace RTC en cada sitio RTC deben conectarse solamente a los servidores de mediación en el mismo sitio.</span><span class="sxs-lookup"><span data-stu-id="9925c-181">PSTN gateway(s) in each PSTN site should only connect to the Mediation Server(s) in the same site</span></span>  <br/> |
|<span data-ttu-id="9925c-182">Configuración</span><span class="sxs-lookup"><span data-stu-id="9925c-182">Setup</span></span>  <br/> |<span data-ttu-id="9925c-183">Usuario</span><span class="sxs-lookup"><span data-stu-id="9925c-183">User</span></span>  <br/> |<span data-ttu-id="9925c-184">Configurar UserPSTNSettings</span><span class="sxs-lookup"><span data-stu-id="9925c-184">Set UserPSTNSettings</span></span>  <br/> |<span data-ttu-id="9925c-185">Configurar UserPSTNSettings</span><span class="sxs-lookup"><span data-stu-id="9925c-185">Set UserPSTNSettings</span></span>  <br/> |
   

