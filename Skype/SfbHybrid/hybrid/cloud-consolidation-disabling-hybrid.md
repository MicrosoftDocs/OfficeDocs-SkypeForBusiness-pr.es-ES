---
title: Deshabilitar la migración híbrida para completar la nube
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.prod: skype-for-business-itpro
search.appverid: MET150
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
audience: ITPro
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: Este apéndice incluye pasos detallados para deshabilitar la implementación híbrida como parte de la consolidación en la nube para Teams y Skype empresarial.
ms.openlocfilehash: 805010aa16ca8159b5e274847ca7ca2b296f214d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "36160784"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud"></a><span data-ttu-id="17d0a-103">Deshabilitar la migración híbrida para completar la nube</span><span class="sxs-lookup"><span data-stu-id="17d0a-103">Disable hybrid to complete migration to the cloud</span></span>

<span data-ttu-id="17d0a-104">Una vez que haya movido a todos los usuarios de la nube local a la nube, puede retirar la implementación local de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="17d0a-104">After you have moved all users from on-premises to the cloud, you can decommission the on-premises Skype for Business deployment.</span></span> <span data-ttu-id="17d0a-105">Aparte de quitar el hardware, un paso crítico es separar lógicamente esa implementación local de Office 365 deshabilitando híbrido.</span><span class="sxs-lookup"><span data-stu-id="17d0a-105">Aside from removing any hardware, a critical step is to logically separate that on-premises deployment from Office 365 by disabling hybrid.</span></span> <span data-ttu-id="17d0a-106">La deshabilitación de un híbrido consta de tres pasos:</span><span class="sxs-lookup"><span data-stu-id="17d0a-106">Disabling hybrid consists of 3 steps:</span></span>

1. <span data-ttu-id="17d0a-107">Actualice los registros DNS para que apunten a Office 365.</span><span class="sxs-lookup"><span data-stu-id="17d0a-107">Update DNS records to point to Office 365.</span></span>
2. <span data-ttu-id="17d0a-108">Deshabilite el dominio dividido en el inquilino de Office 365.</span><span class="sxs-lookup"><span data-stu-id="17d0a-108">Disable split domain in the Office 365 tenant.</span></span>
3. <span data-ttu-id="17d0a-109">Deshabilite la capacidad local para comunicarse con Office 365.</span><span class="sxs-lookup"><span data-stu-id="17d0a-109">Disable ability in on-prem to communicate with Office 365.</span></span>


<span data-ttu-id="17d0a-110">Estos pasos deben realizarse juntos como una unidad.</span><span class="sxs-lookup"><span data-stu-id="17d0a-110">These steps should be done together as a unit.</span></span> <span data-ttu-id="17d0a-111">A continuación se proporcionan detalles.</span><span class="sxs-lookup"><span data-stu-id="17d0a-111">Details are provided below.</span></span>

> [!Note] 
> <span data-ttu-id="17d0a-112">En raras ocasiones, al cambiar el DNS de los locales a Office 365 para su organización, la Federación con otras organizaciones puede dejar de funcionar hasta que la otra organización actualice la configuración de la Federación:</span><span class="sxs-lookup"><span data-stu-id="17d0a-112">In rare cases, changing DNS from pointing on premises to Office 365 for your organization may cause federation with some other organizations to stop working until that other organization updates their federation configuration:</span></span><ul><li>
<span data-ttu-id="17d0a-113">Todas las organizaciones federadas que usen el modelo de Federación directa anterior (también conocido como servidor asociado permitido) tendrán que actualizar las entradas de dominio permitidas en su organización para quitar el FQDN del proxy.</span><span class="sxs-lookup"><span data-stu-id="17d0a-113">Any federated organizations that are using the older Direct Federation model (also known as Allowed Partner Server) will need to update their allowed domain entries for their organization to remove the proxy FQDN.</span></span> <span data-ttu-id="17d0a-114">Este modelo de Federación heredada no se basa en los registros SRV de DNS, por lo que dicha configuración quedará obsoleta una vez que la organización se traslade a la nube.</span><span class="sxs-lookup"><span data-stu-id="17d0a-114">This legacy federation model is not based on DNS SRV records, so such a configuration will become out of date once your organization moves to the cloud.</span></span> </li><li><span data-ttu-id="17d0a-115">Cualquier organización federada que no tenga un proveedor de hospedaje habilitado para sipfed. online. Lync. <span>com tendrá que actualizar su configuración para habilitarlo.</span><span class="sxs-lookup"><span data-stu-id="17d0a-115">Any federated organization that does not have an enabled hosting provider for sipfed.online.lync.<span>com will need to update their configuration to enable that.</span></span> <span data-ttu-id="17d0a-116">Esta situación solo es posible si la organización federada se encuentra exclusivamente local y nunca se ha federado con ningún inquilino híbrido o en línea.</span><span class="sxs-lookup"><span data-stu-id="17d0a-116">This situation is only possible if the federated organization is purely on premises and has never federated with any hybrid or online tenant.</span></span> <span data-ttu-id="17d0a-117">En tal caso, la Federación con estas organizaciones no funcionará hasta que habilite su proveedor de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="17d0a-117">In such a case, federation with these organizations will not work until they enable their hosting provider.</span></span></li></ul><span data-ttu-id="17d0a-118">Si sospecha que cualquiera de sus socios federados puede usar Federación directa o que se ha federado con una organización en línea o híbrida, le sugerimos que les envíe una comunicación sobre esto cuando se prepare para completar la migración a la nube.</span><span class="sxs-lookup"><span data-stu-id="17d0a-118">If you suspect that any of your federated partners may be using Direct Federation or have federated with any online or hybrid organization, we suggest you send them a communication about this as you prepare to complete your migration to the cloud.</span></span>

1.  <span data-ttu-id="17d0a-119">*Actualice DNS para que apunte a Office 365.*</span><span class="sxs-lookup"><span data-stu-id="17d0a-119">*Update DNS to point to Office 365.*</span></span>
<span data-ttu-id="17d0a-120">El DNS externo de la organización para la organización local debe actualizarse para que los registros de Skype empresarial apunten a Office 365 en lugar de a la implementación local.</span><span class="sxs-lookup"><span data-stu-id="17d0a-120">The organization’s external DNS for the on-premises organization needs to be updated so that Skype for Business records point to Office 365 instead of the on-premises deployment.</span></span> <span data-ttu-id="17d0a-121">En particular:</span><span class="sxs-lookup"><span data-stu-id="17d0a-121">Specifically:</span></span>

    |<span data-ttu-id="17d0a-122">Tipo de registro</span><span class="sxs-lookup"><span data-stu-id="17d0a-122">Record type</span></span>|<span data-ttu-id="17d0a-123">Nombre</span><span class="sxs-lookup"><span data-stu-id="17d0a-123">Name</span></span>|<span data-ttu-id="17d0a-124">TTL</span><span class="sxs-lookup"><span data-stu-id="17d0a-124">TTL</span></span>|<span data-ttu-id="17d0a-125">Valor</span><span class="sxs-lookup"><span data-stu-id="17d0a-125">Value</span></span>|
    |---|---|---|---|
    |<span data-ttu-id="17d0a-126">SRV</span><span class="sxs-lookup"><span data-stu-id="17d0a-126">SRV</span></span>|<span data-ttu-id="17d0a-127">_sipfederationtls. _ TCP</span><span class="sxs-lookup"><span data-stu-id="17d0a-127">_sipfederationtls._tcp</span></span>|<span data-ttu-id="17d0a-128">3600</span><span class="sxs-lookup"><span data-stu-id="17d0a-128">3600</span></span>|<span data-ttu-id="17d0a-129">100 1 5061 sipfed. online. Lync. <span>com</span><span class="sxs-lookup"><span data-stu-id="17d0a-129">100 1 5061 sipfed.online.lync.<span>com</span></span>|
    |<span data-ttu-id="17d0a-130">SRV</span><span class="sxs-lookup"><span data-stu-id="17d0a-130">SRV</span></span>|<span data-ttu-id="17d0a-131">_ SIP. _ TLS</span><span class="sxs-lookup"><span data-stu-id="17d0a-131">_sip._tls</span></span>|<span data-ttu-id="17d0a-132">3600</span><span class="sxs-lookup"><span data-stu-id="17d0a-132">3600</span></span>|<span data-ttu-id="17d0a-133">100 1 443 sipdir. online. Lync. <span>com</span><span class="sxs-lookup"><span data-stu-id="17d0a-133">100 1 443 sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="17d0a-134">CNAME</span><span class="sxs-lookup"><span data-stu-id="17d0a-134">CNAME</span></span>| <span data-ttu-id="17d0a-135">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="17d0a-135">lyncdiscover</span></span>|   <span data-ttu-id="17d0a-136">3600</span><span class="sxs-lookup"><span data-stu-id="17d0a-136">3600</span></span>|   <span data-ttu-id="17d0a-137">webdir. online. Lync. <span>com</span><span class="sxs-lookup"><span data-stu-id="17d0a-137">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="17d0a-138">CNAME</span><span class="sxs-lookup"><span data-stu-id="17d0a-138">CNAME</span></span>| <span data-ttu-id="17d0a-139">sip</span><span class="sxs-lookup"><span data-stu-id="17d0a-139">sip</span></span>|    <span data-ttu-id="17d0a-140">3600</span><span class="sxs-lookup"><span data-stu-id="17d0a-140">3600</span></span>|   <span data-ttu-id="17d0a-141">sipdir. online. Lync. <span>com</span><span class="sxs-lookup"><span data-stu-id="17d0a-141">sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="17d0a-142">CNAME</span><span class="sxs-lookup"><span data-stu-id="17d0a-142">CNAME</span></span>| <span data-ttu-id="17d0a-143">cumplir</span><span class="sxs-lookup"><span data-stu-id="17d0a-143">meet</span></span>|   <span data-ttu-id="17d0a-144">3600</span><span class="sxs-lookup"><span data-stu-id="17d0a-144">3600</span></span>|   <span data-ttu-id="17d0a-145">webdir. online. Lync. <span>com</span><span class="sxs-lookup"><span data-stu-id="17d0a-145">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="17d0a-146">CNAME</span><span class="sxs-lookup"><span data-stu-id="17d0a-146">CNAME</span></span>| <span data-ttu-id="17d0a-147">Dialin</span><span class="sxs-lookup"><span data-stu-id="17d0a-147">dialin</span></span>  |<span data-ttu-id="17d0a-148">3600</span><span class="sxs-lookup"><span data-stu-id="17d0a-148">3600</span></span>|  <span data-ttu-id="17d0a-149">webdir. online. Lync. <span>com</span><span class="sxs-lookup"><span data-stu-id="17d0a-149">webdir.online.lync.<span>com</span></span>|

2.  <span data-ttu-id="17d0a-150">*Deshabilitar el espacio de direcciones SIP compartido en Office 365 tenant.*</span><span class="sxs-lookup"><span data-stu-id="17d0a-150">*Disable shared SIP address space in Office 365 tenant.*</span></span>
<span data-ttu-id="17d0a-151">El siguiente comando debe realizarse desde una ventana de PowerShell de Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="17d0a-151">The command below needs to be done from a Skype for Business Online PowerShell window.</span></span>

    `Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false`
 
3.  <span data-ttu-id="17d0a-152">*Deshabilite la capacidad local para comunicarse con Office 365.*</span><span class="sxs-lookup"><span data-stu-id="17d0a-152">*Disable ability in on-prem to communicate with Office 365.*</span></span>  
<span data-ttu-id="17d0a-153">El siguiente comando debe realizarse desde una ventana de PowerShell local.</span><span class="sxs-lookup"><span data-stu-id="17d0a-153">The command below needs to be done from an on-premises PowerShell window.</span></span>  <span data-ttu-id="17d0a-154">Si ya ha importado una sesión de Skype empresarial online, inicie una nueva sesión de PowerShell de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="17d0a-154">If you have previously imported a Skype for Business Online session, start a new Skype for Business PowerShell session.</span></span>

    `Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false`

## <a name="see-also"></a><span data-ttu-id="17d0a-155">Vea también</span><span class="sxs-lookup"><span data-stu-id="17d0a-155">See also</span></span>

[<span data-ttu-id="17d0a-156">Consolidación en la nube para Teams y Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="17d0a-156">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)