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
description: Obtenga información sobre la implementación de varios sitios RTC en Cloud Connector Edition.
ms.openlocfilehash: 3c777c54690b1eb31671f71cff915f1bb4854a0d
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358926"
---
# <a name="deploy-multiple-sites-in-cloud-connector"></a><span data-ttu-id="fcd4e-103">Implementar varios sitios en Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="fcd4e-103">Deploy multiple sites in Cloud Connector</span></span>

> [!Important] 
> <span data-ttu-id="fcd4e-104">Cloud Connector Edition se retirará del 31 de julio de 2021 junto con Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="fcd4e-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="fcd4e-105">Una vez que la organización haya actualizado a Teams, obtenga información sobre cómo conectar la red de telefonía local a Microsoft Teams mediante el [enrutamiento directo](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span><span class="sxs-lookup"><span data-stu-id="fcd4e-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="fcd4e-106">Obtenga información sobre la implementación de varios sitios RTC en Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="fcd4e-106">Learn about deploying multiple PSTN sites in Cloud Connector Edition.</span></span>
  
<span data-ttu-id="fcd4e-107">En esta sección se describe cómo implementar varios sitios de red telefónica conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="fcd4e-107">This section describes how to deploy multiple Public Switched Telephone Network (PSTN) sites.</span></span> <span data-ttu-id="fcd4e-108">Los sitios se implementan uno por vez con los mismos pasos que en la implementación de un único sitio.</span><span class="sxs-lookup"><span data-stu-id="fcd4e-108">Sites are deployed one at a time using the same steps as deploying a single site.</span></span> <span data-ttu-id="fcd4e-109">En este tema se describen las consideraciones y las diferencias entre los sitios en una implementación de varios sitios.</span><span class="sxs-lookup"><span data-stu-id="fcd4e-109">This topic describes the considerations for and differences between sites in a multiple site deployment.</span></span> 
  
## <a name="multiple-public-switched-telephone-network-pstn-sites"></a><span data-ttu-id="fcd4e-110">Varios sitios de red telefónica conmutada (RTC)</span><span class="sxs-lookup"><span data-stu-id="fcd4e-110">Multiple Public Switched Telephone Network (PSTN) Sites</span></span>

<span data-ttu-id="fcd4e-111">A continuación se muestra un ejemplo de configuración para implementar Skype empresarial Cloud Connector Edition para diferentes sitios RTC.</span><span class="sxs-lookup"><span data-stu-id="fcd4e-111">The following shows an example configuration to deploy Skype for Business Cloud Connector Edition for different PSTN sites.</span></span> <span data-ttu-id="fcd4e-112">Asegúrese de que las opciones de configuración son correctas antes de iniciar una implementación.</span><span class="sxs-lookup"><span data-stu-id="fcd4e-112">Make sure your configuration settings are correct before you start a deployment.</span></span>
  
<span data-ttu-id="fcd4e-113">Sitio RTC 1</span><span class="sxs-lookup"><span data-stu-id="fcd4e-113">PSTN Site 1</span></span>
  
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

<span data-ttu-id="fcd4e-114">Sitio RTC 2</span><span class="sxs-lookup"><span data-stu-id="fcd4e-114">PSTN Site 2</span></span>
  
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

<span data-ttu-id="fcd4e-115">Para cada sitio de RTC que quiera agregar, siga los pasos descritos en [deploy a Single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="fcd4e-115">For each PSTN site that you want to add, follow the steps in [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="fcd4e-116">La carpeta compartida para preparar la alta disponibilidad (HA) es por cada sitio RTC.</span><span class="sxs-lookup"><span data-stu-id="fcd4e-116">The shared folder for preparing High Availability (HA) is per PSTN site.</span></span> <span data-ttu-id="fcd4e-117">La carpeta compartida **debe** ser diferente entre los sitios RTC.</span><span class="sxs-lookup"><span data-stu-id="fcd4e-117">The shared folder **must** be different between PSTN sites.</span></span> <span data-ttu-id="fcd4e-118">No use la misma carpeta compartida para varios sitios. ></span><span class="sxs-lookup"><span data-stu-id="fcd4e-118">Do not use the same shared folder for multiple sites.></span></span> 
  
## <a name="single-site-with-high-availability-ha-compared-to-multi-site-deployments"></a><span data-ttu-id="fcd4e-119">Sitio único con alta disponibilidad (HA) comparado con implementaciones de varios sitios</span><span class="sxs-lookup"><span data-stu-id="fcd4e-119">Single site with High Availability (HA) compared to multi-site deployments</span></span>
<span data-ttu-id="fcd4e-120"><a name="BKMK_SingleSitecomparedtomulti-site"> </a></span><span class="sxs-lookup"><span data-stu-id="fcd4e-120"><a name="BKMK_SingleSitecomparedtomulti-site"> </a></span></span>

<span data-ttu-id="fcd4e-121">En la siguiente tabla se enumeran las diferencias entre un sitio único con soporte de HA y una implementación de varios sitios.</span><span class="sxs-lookup"><span data-stu-id="fcd4e-121">The following table lists the differences between single site with HA support and a multiple site deployment.</span></span>
  
|<span data-ttu-id="fcd4e-122">**Categoría**</span><span class="sxs-lookup"><span data-stu-id="fcd4e-122">**Category**</span></span>|<span data-ttu-id="fcd4e-123">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="fcd4e-123">**Item**</span></span>|<span data-ttu-id="fcd4e-124">**Sitio único con HA**</span><span class="sxs-lookup"><span data-stu-id="fcd4e-124">**Single-Site with HA**</span></span>|<span data-ttu-id="fcd4e-125">**Varios sitios**</span><span class="sxs-lookup"><span data-stu-id="fcd4e-125">**Multi-Site**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="fcd4e-126">Configurar</span><span class="sxs-lookup"><span data-stu-id="fcd4e-126">Configure</span></span>  <br/> |<span data-ttu-id="fcd4e-127">Nombre de host del dispositivo</span><span class="sxs-lookup"><span data-stu-id="fcd4e-127">Appliance Host Name</span></span> <br/> |<span data-ttu-id="fcd4e-128">**Diferente** en todos los dispositivos</span><span class="sxs-lookup"><span data-stu-id="fcd4e-128">**Different** across appliances</span></span> <br/> |<span data-ttu-id="fcd4e-129">**Diferente** en todos los sitios RTC</span><span class="sxs-lookup"><span data-stu-id="fcd4e-129">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="fcd4e-130">Instalación</span><span class="sxs-lookup"><span data-stu-id="fcd4e-130">Setup</span></span>  <br/> |<span data-ttu-id="fcd4e-131">Carpeta compartida</span><span class="sxs-lookup"><span data-stu-id="fcd4e-131">Shared folder</span></span>  <br/> |<span data-ttu-id="fcd4e-132">Requiere la **misma** carpeta compartida en todos los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="fcd4e-132">Requires the **same** shared folder across appliances</span></span> <br/> |<span data-ttu-id="fcd4e-133">Requiere una carpeta compartida **diferente** en los dispositivos</span><span class="sxs-lookup"><span data-stu-id="fcd4e-133">Requires a **different** shared folder across appliances</span></span> <br/> |
|<span data-ttu-id="fcd4e-134">Configurar</span><span class="sxs-lookup"><span data-stu-id="fcd4e-134">Configure</span></span>  <br/> |<span data-ttu-id="fcd4e-135">VirtualMachineDomain</span><span class="sxs-lookup"><span data-stu-id="fcd4e-135">VirtualMachineDomain</span></span>  <br/> |<span data-ttu-id="fcd4e-136">Requiere el **mismo** dominio en todos los dispositivos</span><span class="sxs-lookup"><span data-stu-id="fcd4e-136">Requires the **same** domain across appliances</span></span> <br/> |<span data-ttu-id="fcd4e-137">Requiere el **mismo** dominio en todos los sitios RTC</span><span class="sxs-lookup"><span data-stu-id="fcd4e-137">Requires the **same** domain across PSTN sites</span></span> <br/> |
|<span data-ttu-id="fcd4e-138">Configurar</span><span class="sxs-lookup"><span data-stu-id="fcd4e-138">Configure</span></span>  <br/> |<span data-ttu-id="fcd4e-139">SIPDomains</span><span class="sxs-lookup"><span data-stu-id="fcd4e-139">SIPDomains</span></span>  <br/> |<span data-ttu-id="fcd4e-140">Los nombres y el orden de los dominios deben ser los **mismos** en todos los dispositivos</span><span class="sxs-lookup"><span data-stu-id="fcd4e-140">Domain names and order should be the **same** across appliances</span></span> <br/> |<span data-ttu-id="fcd4e-141">Los nombres y el orden de los dominios deben ser los **mismos** en todos los sitios de RTC</span><span class="sxs-lookup"><span data-stu-id="fcd4e-141">Domain names and order should be the **same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="fcd4e-142">Configurar</span><span class="sxs-lookup"><span data-stu-id="fcd4e-142">Configure</span></span>  <br/> |<span data-ttu-id="fcd4e-143">Nombre del sitio</span><span class="sxs-lookup"><span data-stu-id="fcd4e-143">Site name</span></span>  <br/> |<span data-ttu-id="fcd4e-144">**Misma** Nombre del sitio en todos los dispositivos</span><span class="sxs-lookup"><span data-stu-id="fcd4e-144">**Same** Site Name across appliances</span></span> <br/> |<span data-ttu-id="fcd4e-145">**Diferentes** Nombre del sitio en todos los sitios RTC</span><span class="sxs-lookup"><span data-stu-id="fcd4e-145">**Different** Site Name across PSTN sites</span></span> <br/> |
|<span data-ttu-id="fcd4e-146">Configurar</span><span class="sxs-lookup"><span data-stu-id="fcd4e-146">Configure</span></span>  <br/> |<span data-ttu-id="fcd4e-147">Nombres de servidor</span><span class="sxs-lookup"><span data-stu-id="fcd4e-147">Server names</span></span>  <br/> |<span data-ttu-id="fcd4e-148">**Diferente** en todos los dispositivos</span><span class="sxs-lookup"><span data-stu-id="fcd4e-148">**Different** across appliances</span></span> <br/> |<span data-ttu-id="fcd4e-149">**Diferente** en todos los sitios RTC</span><span class="sxs-lookup"><span data-stu-id="fcd4e-149">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="fcd4e-150">Configurar</span><span class="sxs-lookup"><span data-stu-id="fcd4e-150">Configure</span></span>  <br/> |<span data-ttu-id="fcd4e-151">FQDN de grupo interno</span><span class="sxs-lookup"><span data-stu-id="fcd4e-151">Internal pool FQDNs</span></span>  <br/> |<span data-ttu-id="fcd4e-152">**Igual** en todos los dispositivos</span><span class="sxs-lookup"><span data-stu-id="fcd4e-152">**Same** across appliances</span></span> <br/> |<span data-ttu-id="fcd4e-153">**Igual** en todos los sitios RTC</span><span class="sxs-lookup"><span data-stu-id="fcd4e-153">**Same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="fcd4e-154">Configurar</span><span class="sxs-lookup"><span data-stu-id="fcd4e-154">Configure</span></span>  <br/> |<span data-ttu-id="fcd4e-155">IP internas</span><span class="sxs-lookup"><span data-stu-id="fcd4e-155">Internal IPs</span></span>  <br/> |<span data-ttu-id="fcd4e-156">**Diferente** en todos los dispositivos</span><span class="sxs-lookup"><span data-stu-id="fcd4e-156">**Different** across appliances</span></span> <br/> |<span data-ttu-id="fcd4e-157">**Diferente** en todos los sitios RTC</span><span class="sxs-lookup"><span data-stu-id="fcd4e-157">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="fcd4e-158">Configurar</span><span class="sxs-lookup"><span data-stu-id="fcd4e-158">Configure</span></span>  <br/> |<span data-ttu-id="fcd4e-159">FQDN externo</span><span class="sxs-lookup"><span data-stu-id="fcd4e-159">External FQDN</span></span>  <br/> |<span data-ttu-id="fcd4e-160">**Igual** en todos los dispositivos</span><span class="sxs-lookup"><span data-stu-id="fcd4e-160">**Same** across appliances</span></span> <br/> |<span data-ttu-id="fcd4e-161">**Diferente** en todos los sitios RTC</span><span class="sxs-lookup"><span data-stu-id="fcd4e-161">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="fcd4e-162">Configurar</span><span class="sxs-lookup"><span data-stu-id="fcd4e-162">Configure</span></span>  <br/> |<span data-ttu-id="fcd4e-163">IP externas</span><span class="sxs-lookup"><span data-stu-id="fcd4e-163">External IPs</span></span>  <br/> |<span data-ttu-id="fcd4e-164">**Diferente** en todos los dispositivos</span><span class="sxs-lookup"><span data-stu-id="fcd4e-164">**Different** across appliances</span></span> <br/> |<span data-ttu-id="fcd4e-165">**Diferente** en todos los sitios RTC</span><span class="sxs-lookup"><span data-stu-id="fcd4e-165">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="fcd4e-166">Configurar</span><span class="sxs-lookup"><span data-stu-id="fcd4e-166">Configure</span></span>  <br/> |<span data-ttu-id="fcd4e-167">Configuración de RTC GW</span><span class="sxs-lookup"><span data-stu-id="fcd4e-167">PSTN GW settings</span></span>  <br/> |<span data-ttu-id="fcd4e-168">**Igual** en todos los dispositivos</span><span class="sxs-lookup"><span data-stu-id="fcd4e-168">**Same** across appliances</span></span> <br/> |<span data-ttu-id="fcd4e-169">**Diferente** en todos los sitios RTC</span><span class="sxs-lookup"><span data-stu-id="fcd4e-169">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="fcd4e-170">Configurar</span><span class="sxs-lookup"><span data-stu-id="fcd4e-170">Configure</span></span>  <br/> |<span data-ttu-id="fcd4e-171">Registro DNS</span><span class="sxs-lookup"><span data-stu-id="fcd4e-171">DNS record</span></span>  <br/> |<span data-ttu-id="fcd4e-172">Agregar registros con los **mismos** FQDN de acceso externo y **diferentes** direcciones IP</span><span class="sxs-lookup"><span data-stu-id="fcd4e-172">Add records with the **same** External Access FQDNs and **different** IP addresses</span></span> <br/> |<span data-ttu-id="fcd4e-173">Agregar registros con **diferentes** FQDN de acceso externo y **diferentes** direcciones IP</span><span class="sxs-lookup"><span data-stu-id="fcd4e-173">Add records with **different** External Access FQDNs and **different** IP addresses</span></span> <br/> |
|<span data-ttu-id="fcd4e-174">Instalación</span><span class="sxs-lookup"><span data-stu-id="fcd4e-174">Setup</span></span>  <br/> |<span data-ttu-id="fcd4e-175">Inquilino híbrido</span><span class="sxs-lookup"><span data-stu-id="fcd4e-175">Hybrid tenant</span></span>  <br/> |<span data-ttu-id="fcd4e-176">Establecer HybridPSTNSite</span><span class="sxs-lookup"><span data-stu-id="fcd4e-176">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="fcd4e-177">Establecer PeerDestination para reserva</span><span class="sxs-lookup"><span data-stu-id="fcd4e-177">Set PeerDestination for fallback</span></span>  <br/> |<span data-ttu-id="fcd4e-178">Establecer HybridPSTNSite</span><span class="sxs-lookup"><span data-stu-id="fcd4e-178">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="fcd4e-179">Establecer PeerDestination para reserva</span><span class="sxs-lookup"><span data-stu-id="fcd4e-179">Set PeerDestination for fallback</span></span>  <br/> |
|<span data-ttu-id="fcd4e-180">Instalación</span><span class="sxs-lookup"><span data-stu-id="fcd4e-180">Setup</span></span>  <br/> |<span data-ttu-id="fcd4e-181">Puerta de enlace</span><span class="sxs-lookup"><span data-stu-id="fcd4e-181">Gateway</span></span>  <br/> |<span data-ttu-id="fcd4e-182">Asignación **M:N** de MS GW en este sitio</span><span class="sxs-lookup"><span data-stu-id="fcd4e-182">MS GW **M:N** mapping in this site</span></span> <br/> |<span data-ttu-id="fcd4e-183">Las puertas de enlace RTC en cada sitio RTC solo deben conectarse a los servidores de mediación en el mismo sitio.</span><span class="sxs-lookup"><span data-stu-id="fcd4e-183">PSTN gateway(s) in each PSTN site should only connect to the Mediation Server(s) in the same site</span></span>  <br/> |
|<span data-ttu-id="fcd4e-184">Instalación</span><span class="sxs-lookup"><span data-stu-id="fcd4e-184">Setup</span></span>  <br/> |<span data-ttu-id="fcd4e-185">Usuario</span><span class="sxs-lookup"><span data-stu-id="fcd4e-185">User</span></span>  <br/> |<span data-ttu-id="fcd4e-186">Establecer UserPSTNSettings</span><span class="sxs-lookup"><span data-stu-id="fcd4e-186">Set UserPSTNSettings</span></span>  <br/> |<span data-ttu-id="fcd4e-187">Establecer UserPSTNSettings</span><span class="sxs-lookup"><span data-stu-id="fcd4e-187">Set UserPSTNSettings</span></span>  <br/> |
   

