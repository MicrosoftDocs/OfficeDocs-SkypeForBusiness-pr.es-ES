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
description: Obtenga información sobre cómo implementar varios sitios RTC en Cloud Connector Edition.
ms.openlocfilehash: 059b9a39a082e876b1dd9cd772a235c384a29107
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098406"
---
# <a name="deploy-multiple-sites-in-cloud-connector"></a><span data-ttu-id="18b61-103">Implementar varios sitios en Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="18b61-103">Deploy multiple sites in Cloud Connector</span></span>

> [!Important] 
> <span data-ttu-id="18b61-104">Cloud Connector Edition se retirará el 31 de julio de 2021 junto con Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="18b61-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="18b61-105">Una vez que la organización haya actualizado a Teams, obtenga información sobre cómo conectar la red de telefonía local a Teams mediante [enrutamiento directo.](/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="18b61-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="18b61-106">Obtenga información sobre cómo implementar varios sitios RTC en Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="18b61-106">Learn about deploying multiple PSTN sites in Cloud Connector Edition.</span></span>
  
<span data-ttu-id="18b61-107">En esta sección se describe cómo implementar varios sitios de red telefónica conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="18b61-107">This section describes how to deploy multiple Public Switched Telephone Network (PSTN) sites.</span></span> <span data-ttu-id="18b61-108">Los sitios se implementan de uno en uno con los mismos pasos que la implementación de un solo sitio.</span><span class="sxs-lookup"><span data-stu-id="18b61-108">Sites are deployed one at a time using the same steps as deploying a single site.</span></span> <span data-ttu-id="18b61-109">En este tema se describen las consideraciones y las diferencias entre los sitios de una implementación de varios sitios.</span><span class="sxs-lookup"><span data-stu-id="18b61-109">This topic describes the considerations for and differences between sites in a multiple site deployment.</span></span> 
  
## <a name="multiple-public-switched-telephone-network-pstn-sites"></a><span data-ttu-id="18b61-110">Varios sitios de red telefónica conmutada (RTC)</span><span class="sxs-lookup"><span data-stu-id="18b61-110">Multiple Public Switched Telephone Network (PSTN) Sites</span></span>

<span data-ttu-id="18b61-111">A continuación se muestra un ejemplo de configuración para implementar Skype Empresarial Cloud Connector Edition para diferentes sitios RTC.</span><span class="sxs-lookup"><span data-stu-id="18b61-111">The following shows an example configuration to deploy Skype for Business Cloud Connector Edition for different PSTN sites.</span></span> <span data-ttu-id="18b61-112">Asegúrese de que las opciones de configuración son correctas antes de iniciar una implementación.</span><span class="sxs-lookup"><span data-stu-id="18b61-112">Make sure your configuration settings are correct before you start a deployment.</span></span>
  
<span data-ttu-id="18b61-113">Sitio RTC 1</span><span class="sxs-lookup"><span data-stu-id="18b61-113">PSTN Site 1</span></span>
  
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

<span data-ttu-id="18b61-114">Sitio RTC 2</span><span class="sxs-lookup"><span data-stu-id="18b61-114">PSTN Site 2</span></span>
  
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

<span data-ttu-id="18b61-115">Para cada sitio RTC que desee agregar, siga los pasos descritos en [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="18b61-115">For each PSTN site that you want to add, follow the steps in [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="18b61-116">La carpeta compartida para preparar la alta disponibilidad (HA) es por sitio RTC.</span><span class="sxs-lookup"><span data-stu-id="18b61-116">The shared folder for preparing High Availability (HA) is per PSTN site.</span></span> <span data-ttu-id="18b61-117">La carpeta compartida **debe ser** diferente entre sitios RTC.</span><span class="sxs-lookup"><span data-stu-id="18b61-117">The shared folder **must** be different between PSTN sites.</span></span> <span data-ttu-id="18b61-118">No use la misma carpeta compartida para varios sites.></span><span class="sxs-lookup"><span data-stu-id="18b61-118">Do not use the same shared folder for multiple sites.></span></span> 
  
## <a name="single-site-with-high-availability-ha-compared-to-multi-site-deployments"></a><span data-ttu-id="18b61-119">Sitio único con alta disponibilidad (HA) en comparación con las implementaciones de varios sitios</span><span class="sxs-lookup"><span data-stu-id="18b61-119">Single site with High Availability (HA) compared to multi-site deployments</span></span>
<span data-ttu-id="18b61-120"><a name="BKMK_SingleSitecomparedtomulti-site"> </a></span><span class="sxs-lookup"><span data-stu-id="18b61-120"><a name="BKMK_SingleSitecomparedtomulti-site"> </a></span></span>

<span data-ttu-id="18b61-121">En la tabla siguiente se enumeran las diferencias entre un solo sitio con compatibilidad con HA y una implementación de varios sitios.</span><span class="sxs-lookup"><span data-stu-id="18b61-121">The following table lists the differences between single site with HA support and a multiple site deployment.</span></span>
  
|<span data-ttu-id="18b61-122">**Categoría**</span><span class="sxs-lookup"><span data-stu-id="18b61-122">**Category**</span></span>|<span data-ttu-id="18b61-123">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="18b61-123">**Item**</span></span>|<span data-ttu-id="18b61-124">**Sitio único con HA**</span><span class="sxs-lookup"><span data-stu-id="18b61-124">**Single-Site with HA**</span></span>|<span data-ttu-id="18b61-125">**Multi-Site**</span><span class="sxs-lookup"><span data-stu-id="18b61-125">**Multi-Site**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="18b61-126">Configurar</span><span class="sxs-lookup"><span data-stu-id="18b61-126">Configure</span></span>  <br/> |<span data-ttu-id="18b61-127">Nombre de host del dispositivo</span><span class="sxs-lookup"><span data-stu-id="18b61-127">Appliance Host Name</span></span> <br/> |<span data-ttu-id="18b61-128">**Diferentes** entre dispositivos</span><span class="sxs-lookup"><span data-stu-id="18b61-128">**Different** across appliances</span></span> <br/> |<span data-ttu-id="18b61-129">**Diferente** entre sitios RTC</span><span class="sxs-lookup"><span data-stu-id="18b61-129">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="18b61-130">Configuración</span><span class="sxs-lookup"><span data-stu-id="18b61-130">Setup</span></span>  <br/> |<span data-ttu-id="18b61-131">Carpeta compartida</span><span class="sxs-lookup"><span data-stu-id="18b61-131">Shared folder</span></span>  <br/> |<span data-ttu-id="18b61-132">Requiere la **misma carpeta** compartida en todos los dispositivos</span><span class="sxs-lookup"><span data-stu-id="18b61-132">Requires the **same** shared folder across appliances</span></span> <br/> |<span data-ttu-id="18b61-133">Requiere una **carpeta** compartida diferente en todos los dispositivos</span><span class="sxs-lookup"><span data-stu-id="18b61-133">Requires a **different** shared folder across appliances</span></span> <br/> |
|<span data-ttu-id="18b61-134">Configurar</span><span class="sxs-lookup"><span data-stu-id="18b61-134">Configure</span></span>  <br/> |<span data-ttu-id="18b61-135">VirtualMachineDomain</span><span class="sxs-lookup"><span data-stu-id="18b61-135">VirtualMachineDomain</span></span>  <br/> |<span data-ttu-id="18b61-136">Requiere el **mismo dominio** en todos los dispositivos</span><span class="sxs-lookup"><span data-stu-id="18b61-136">Requires the **same** domain across appliances</span></span> <br/> |<span data-ttu-id="18b61-137">Requiere el **mismo dominio** entre sitios RTC</span><span class="sxs-lookup"><span data-stu-id="18b61-137">Requires the **same** domain across PSTN sites</span></span> <br/> |
|<span data-ttu-id="18b61-138">Configurar</span><span class="sxs-lookup"><span data-stu-id="18b61-138">Configure</span></span>  <br/> |<span data-ttu-id="18b61-139">SIPDomains</span><span class="sxs-lookup"><span data-stu-id="18b61-139">SIPDomains</span></span>  <br/> |<span data-ttu-id="18b61-140">Los nombres de dominio y el orden deben ser **los mismos en** todos los dispositivos</span><span class="sxs-lookup"><span data-stu-id="18b61-140">Domain names and order should be the **same** across appliances</span></span> <br/> |<span data-ttu-id="18b61-141">Los nombres de dominio y el orden deben ser **los mismos** en los sitios RTC</span><span class="sxs-lookup"><span data-stu-id="18b61-141">Domain names and order should be the **same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="18b61-142">Configurar</span><span class="sxs-lookup"><span data-stu-id="18b61-142">Configure</span></span>  <br/> |<span data-ttu-id="18b61-143">Nombre del sitio</span><span class="sxs-lookup"><span data-stu-id="18b61-143">Site name</span></span>  <br/> |<span data-ttu-id="18b61-144">**Igual** Nombre del sitio en todos los dispositivos</span><span class="sxs-lookup"><span data-stu-id="18b61-144">**Same** Site Name across appliances</span></span> <br/> |<span data-ttu-id="18b61-145">**Diferente** Nombre de sitio en sitios RTC</span><span class="sxs-lookup"><span data-stu-id="18b61-145">**Different** Site Name across PSTN sites</span></span> <br/> |
|<span data-ttu-id="18b61-146">Configurar</span><span class="sxs-lookup"><span data-stu-id="18b61-146">Configure</span></span>  <br/> |<span data-ttu-id="18b61-147">Nombres de servidor</span><span class="sxs-lookup"><span data-stu-id="18b61-147">Server names</span></span>  <br/> |<span data-ttu-id="18b61-148">**Diferentes** entre dispositivos</span><span class="sxs-lookup"><span data-stu-id="18b61-148">**Different** across appliances</span></span> <br/> |<span data-ttu-id="18b61-149">**Diferente** entre sitios RTC</span><span class="sxs-lookup"><span data-stu-id="18b61-149">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="18b61-150">Configurar</span><span class="sxs-lookup"><span data-stu-id="18b61-150">Configure</span></span>  <br/> |<span data-ttu-id="18b61-151">FQDN de grupo interno</span><span class="sxs-lookup"><span data-stu-id="18b61-151">Internal pool FQDNs</span></span>  <br/> |<span data-ttu-id="18b61-152">**Igual en** todos los dispositivos</span><span class="sxs-lookup"><span data-stu-id="18b61-152">**Same** across appliances</span></span> <br/> |<span data-ttu-id="18b61-153">**Lo mismo** en los sitios RTC</span><span class="sxs-lookup"><span data-stu-id="18b61-153">**Same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="18b61-154">Configurar</span><span class="sxs-lookup"><span data-stu-id="18b61-154">Configure</span></span>  <br/> |<span data-ttu-id="18b61-155">IP internas</span><span class="sxs-lookup"><span data-stu-id="18b61-155">Internal IPs</span></span>  <br/> |<span data-ttu-id="18b61-156">**Diferentes** entre dispositivos</span><span class="sxs-lookup"><span data-stu-id="18b61-156">**Different** across appliances</span></span> <br/> |<span data-ttu-id="18b61-157">**Diferente** entre sitios RTC</span><span class="sxs-lookup"><span data-stu-id="18b61-157">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="18b61-158">Configurar</span><span class="sxs-lookup"><span data-stu-id="18b61-158">Configure</span></span>  <br/> |<span data-ttu-id="18b61-159">FQDN externo</span><span class="sxs-lookup"><span data-stu-id="18b61-159">External FQDN</span></span>  <br/> |<span data-ttu-id="18b61-160">**Igual en** todos los dispositivos</span><span class="sxs-lookup"><span data-stu-id="18b61-160">**Same** across appliances</span></span> <br/> |<span data-ttu-id="18b61-161">**Diferente** entre sitios RTC</span><span class="sxs-lookup"><span data-stu-id="18b61-161">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="18b61-162">Configurar</span><span class="sxs-lookup"><span data-stu-id="18b61-162">Configure</span></span>  <br/> |<span data-ttu-id="18b61-163">IP externas</span><span class="sxs-lookup"><span data-stu-id="18b61-163">External IPs</span></span>  <br/> |<span data-ttu-id="18b61-164">**Diferentes** entre dispositivos</span><span class="sxs-lookup"><span data-stu-id="18b61-164">**Different** across appliances</span></span> <br/> |<span data-ttu-id="18b61-165">**Diferente** entre sitios RTC</span><span class="sxs-lookup"><span data-stu-id="18b61-165">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="18b61-166">Configurar</span><span class="sxs-lookup"><span data-stu-id="18b61-166">Configure</span></span>  <br/> |<span data-ttu-id="18b61-167">Configuración de RTC GW</span><span class="sxs-lookup"><span data-stu-id="18b61-167">PSTN GW settings</span></span>  <br/> |<span data-ttu-id="18b61-168">**Igual en** todos los dispositivos</span><span class="sxs-lookup"><span data-stu-id="18b61-168">**Same** across appliances</span></span> <br/> |<span data-ttu-id="18b61-169">**Diferente** entre sitios RTC</span><span class="sxs-lookup"><span data-stu-id="18b61-169">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="18b61-170">Configurar</span><span class="sxs-lookup"><span data-stu-id="18b61-170">Configure</span></span>  <br/> |<span data-ttu-id="18b61-171">Registro DNS</span><span class="sxs-lookup"><span data-stu-id="18b61-171">DNS record</span></span>  <br/> |<span data-ttu-id="18b61-172">Agregar registros con los **mismos** FQDN de acceso externo y **diferentes direcciones** IP</span><span class="sxs-lookup"><span data-stu-id="18b61-172">Add records with the **same** External Access FQDNs and **different** IP addresses</span></span> <br/> |<span data-ttu-id="18b61-173">Agregar registros con **diferentes** FQDN de acceso externo y **distintas** direcciones IP</span><span class="sxs-lookup"><span data-stu-id="18b61-173">Add records with **different** External Access FQDNs and **different** IP addresses</span></span> <br/> |
|<span data-ttu-id="18b61-174">Configuración</span><span class="sxs-lookup"><span data-stu-id="18b61-174">Setup</span></span>  <br/> |<span data-ttu-id="18b61-175">Inquilino híbrido</span><span class="sxs-lookup"><span data-stu-id="18b61-175">Hybrid tenant</span></span>  <br/> |<span data-ttu-id="18b61-176">Establecer HybridPSTNSite</span><span class="sxs-lookup"><span data-stu-id="18b61-176">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="18b61-177">Establecer PeerDestination para reserva</span><span class="sxs-lookup"><span data-stu-id="18b61-177">Set PeerDestination for fallback</span></span>  <br/> |<span data-ttu-id="18b61-178">Establecer HybridPSTNSite</span><span class="sxs-lookup"><span data-stu-id="18b61-178">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="18b61-179">Establecer PeerDestination para reserva</span><span class="sxs-lookup"><span data-stu-id="18b61-179">Set PeerDestination for fallback</span></span>  <br/> |
|<span data-ttu-id="18b61-180">Configuración</span><span class="sxs-lookup"><span data-stu-id="18b61-180">Setup</span></span>  <br/> |<span data-ttu-id="18b61-181">Puerta de enlace</span><span class="sxs-lookup"><span data-stu-id="18b61-181">Gateway</span></span>  <br/> |<span data-ttu-id="18b61-182">Asignación **MS GW M:N** en este sitio</span><span class="sxs-lookup"><span data-stu-id="18b61-182">MS GW **M:N** mapping in this site</span></span> <br/> |<span data-ttu-id="18b61-183">Las puertas de enlace RTC en cada sitio RTC solo deben conectarse a los servidores de mediación del mismo sitio</span><span class="sxs-lookup"><span data-stu-id="18b61-183">PSTN gateway(s) in each PSTN site should only connect to the Mediation Server(s) in the same site</span></span>  <br/> |
|<span data-ttu-id="18b61-184">Configuración</span><span class="sxs-lookup"><span data-stu-id="18b61-184">Setup</span></span>  <br/> |<span data-ttu-id="18b61-185">Usuario</span><span class="sxs-lookup"><span data-stu-id="18b61-185">User</span></span>  <br/> |<span data-ttu-id="18b61-186">Establecer UserPSTNSettings</span><span class="sxs-lookup"><span data-stu-id="18b61-186">Set UserPSTNSettings</span></span>  <br/> |<span data-ttu-id="18b61-187">Establecer UserPSTNSettings</span><span class="sxs-lookup"><span data-stu-id="18b61-187">Set UserPSTNSettings</span></span>  <br/> |
