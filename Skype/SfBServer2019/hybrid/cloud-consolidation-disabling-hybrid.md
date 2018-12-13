---
title: Deshabilitar híbrido para completar la migración a la nube
ms.author: crowe
author: crowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.service:
- skype-for-business-online
- msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: Este apéndice incluye los pasos detallados para deshabilitar híbrida como parte de la consolidación en la nube para equipos y Skype para la empresa.
ms.openlocfilehash: 03c38a4482d9a0bd6e728138b3d856b552e4754a
ms.sourcegitcommit: 4dac1994b829d7a7aefc3c003eec998e011c1bd3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/13/2018
ms.locfileid: "27247734"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud"></a><span data-ttu-id="e43e6-103">Deshabilitar híbrido para completar la migración a la nube</span><span class="sxs-lookup"><span data-stu-id="e43e6-103">Disable hybrid to complete migration to the cloud</span></span>

<span data-ttu-id="e43e6-104">Después de mover todos los usuarios de local a la nube, puede retirar el Skype local para la implementación de la empresa.</span><span class="sxs-lookup"><span data-stu-id="e43e6-104">After you have moved all users from on-premises to the cloud, you can decommission the on-premises Skype for Business deployment.</span></span> <span data-ttu-id="e43e6-105">Aparte de eliminar cualquier hardware, un paso crítico es separar de forma lógica que la implementación local de Office 365 deshabilitando híbrida.</span><span class="sxs-lookup"><span data-stu-id="e43e6-105">Aside from removing any hardware, a critical step is to logically separate that on-premises deployment from Office 365 by disabling hybrid.</span></span> <span data-ttu-id="e43e6-106">Deshabilitar híbrida consta de 3 pasos:</span><span class="sxs-lookup"><span data-stu-id="e43e6-106">Disabling hybrid consists of 3 steps:</span></span>

1. <span data-ttu-id="e43e6-107">Actualizar registros DNS que apunten a Office 365.</span><span class="sxs-lookup"><span data-stu-id="e43e6-107">Update DNS records to point to Office 365.</span></span>
2. <span data-ttu-id="e43e6-108">Deshabilitar dominio dividido en el inquilino de Office 365.</span><span class="sxs-lookup"><span data-stu-id="e43e6-108">Disable split domain in the Office 365 tenant.</span></span>
3. <span data-ttu-id="e43e6-109">Deshabilitar la capacidad de comunicarse con Office 365 en prem.</span><span class="sxs-lookup"><span data-stu-id="e43e6-109">Disable ability in on-prem to communicate with Office 365.</span></span>


<span data-ttu-id="e43e6-110">Estos pasos deben realizarse conjuntamente como una unidad.</span><span class="sxs-lookup"><span data-stu-id="e43e6-110">These steps should be done together as a unit.</span></span> <span data-ttu-id="e43e6-111">A continuación se proporcionan los detalles.</span><span class="sxs-lookup"><span data-stu-id="e43e6-111">Details are provided below.</span></span>

> [!Note] 
> <span data-ttu-id="e43e6-112">En algunos casos poco frecuentes, cambiar DNS de apuntar en local a Office 365 para su organización puede causar federación con otras organizaciones dejen de funcionar hasta que otra organización actualiza su configuración de federación:</span><span class="sxs-lookup"><span data-stu-id="e43e6-112">In rare cases, changing DNS from pointing on premises to Office 365 for your organization may cause federation with some other organizations to stop working until that other organization updates their federation configuration:</span></span><ul><li>
<span data-ttu-id="e43e6-113">Las organizaciones federadas que usan el modelo de federación directa antiguo (también conocido como servidor de socio permitido) tendrá que actualizar sus entradas de dominios permitidos para su organización quitar el FQDN del proxy.</span><span class="sxs-lookup"><span data-stu-id="e43e6-113">Any federated organizations that are using the older Direct Federation model (also known as Allowed Partner Server) will need to update their allowed domain entries for their organization to remove the proxy FQDN.</span></span> <span data-ttu-id="e43e6-114">Este modelo de federación heredada no se basa en los registros DNS SRV, por lo que dicha configuración se convertirán en caducada una vez que la organización se mueve a la nube.</span><span class="sxs-lookup"><span data-stu-id="e43e6-114">This legacy federation model is not based on DNS SRV records, so such a configuration will become out of date once your organization moves to the cloud.</span></span> </li><li><span data-ttu-id="e43e6-115">Cualquier organización federada que no tiene un proveedor de hospedaje habilitado para sipfed.online.lync. <span>com tendrá que actualizar su configuración para permitir que.</span><span class="sxs-lookup"><span data-stu-id="e43e6-115">Any federated organization that does not have an enabled hosting provider for sipfed.online.lync.<span>com will need to update their configuration to enable that.</span></span> <span data-ttu-id="e43e6-116">Esta situación sólo es posible si la organización federada es puramente local y nunca ha federados con cualquier híbrido o inquilino en línea.</span><span class="sxs-lookup"><span data-stu-id="e43e6-116">This situation is only possible if the federated organization is purely on premises and has never federated with any hybrid or online tenant.</span></span> <span data-ttu-id="e43e6-117">En tal caso, la federación con estas organizaciones no funcionará hasta que permiten que su proveedor de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="e43e6-117">In such a case, federation with these organizations will not work until they enable their hosting provider.</span></span></li></ul><span data-ttu-id="e43e6-118">Si sospecha que alguno de los socios federados que esté utilizando la federación directa o tengan federado en línea con cualquiera u organización híbrida, es recomendable que les envíe una comunicación sobre esto mientras se prepara para llevar a cabo la migración a la nube.</span><span class="sxs-lookup"><span data-stu-id="e43e6-118">If you suspect that any of your federated partners may be using Direct Federation or have federated with any online or hybrid organization, we suggest you send them a communication about this as you prepare to complete your migration to the cloud.</span></span>

1.  <span data-ttu-id="e43e6-119">*Actualización de DNS para que apunten a Office 365.*</span><span class="sxs-lookup"><span data-stu-id="e43e6-119">*Update DNS to point to Office 365.*</span></span>
<span data-ttu-id="e43e6-120">DNS externo de la organización para la organización local debe actualizarse para que apunten Skype para los registros de negocios a Office 365 en lugar de la implementación local.</span><span class="sxs-lookup"><span data-stu-id="e43e6-120">The organization’s external DNS for the on-premises organization needs to be updated so that Skype for Business records point to Office 365 instead of the on-premises deployment.</span></span> <span data-ttu-id="e43e6-121">En concreto:</span><span class="sxs-lookup"><span data-stu-id="e43e6-121">Specifically:</span></span>

    |<span data-ttu-id="e43e6-122">Tipo de registro</span><span class="sxs-lookup"><span data-stu-id="e43e6-122">Record type</span></span>|<span data-ttu-id="e43e6-123">Nombre</span><span class="sxs-lookup"><span data-stu-id="e43e6-123">Name</span></span>|<span data-ttu-id="e43e6-124">TTL</span><span class="sxs-lookup"><span data-stu-id="e43e6-124">TTL</span></span>|<span data-ttu-id="e43e6-125">Valor</span><span class="sxs-lookup"><span data-stu-id="e43e6-125">Value</span></span>|
    |---|---|---|---|
    |<span data-ttu-id="e43e6-126">SRV</span><span class="sxs-lookup"><span data-stu-id="e43e6-126">SRV</span></span>|<span data-ttu-id="e43e6-127">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="e43e6-127">_sipfederationtls._tcp</span></span>|<span data-ttu-id="e43e6-128">3600</span><span class="sxs-lookup"><span data-stu-id="e43e6-128">3600</span></span>|<span data-ttu-id="e43e6-129">100 1 5061 sipfed.online.lync. <span>com</span><span class="sxs-lookup"><span data-stu-id="e43e6-129">100 1 5061 sipfed.online.lync.<span>com</span></span>|
    |<span data-ttu-id="e43e6-130">SRV</span><span class="sxs-lookup"><span data-stu-id="e43e6-130">SRV</span></span>|<span data-ttu-id="e43e6-131">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="e43e6-131">_sip._tls</span></span>|<span data-ttu-id="e43e6-132">3600</span><span class="sxs-lookup"><span data-stu-id="e43e6-132">3600</span></span>|<span data-ttu-id="e43e6-133">100 1 443 sipdir.online.lync. <span>com</span><span class="sxs-lookup"><span data-stu-id="e43e6-133">100 1 443 sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="e43e6-134">CNAME</span><span class="sxs-lookup"><span data-stu-id="e43e6-134">CNAME</span></span>| <span data-ttu-id="e43e6-135">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="e43e6-135">lyncdiscover</span></span>|   <span data-ttu-id="e43e6-136">3600</span><span class="sxs-lookup"><span data-stu-id="e43e6-136">3600</span></span>|   <span data-ttu-id="e43e6-137">WebDir.Online.Lync. <span>com</span><span class="sxs-lookup"><span data-stu-id="e43e6-137">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="e43e6-138">CNAME</span><span class="sxs-lookup"><span data-stu-id="e43e6-138">CNAME</span></span>| <span data-ttu-id="e43e6-139">SIP</span><span class="sxs-lookup"><span data-stu-id="e43e6-139">sip</span></span>|    <span data-ttu-id="e43e6-140">3600</span><span class="sxs-lookup"><span data-stu-id="e43e6-140">3600</span></span>|   <span data-ttu-id="e43e6-141">sipdir.Online.Lync. <span>com</span><span class="sxs-lookup"><span data-stu-id="e43e6-141">sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="e43e6-142">CNAME</span><span class="sxs-lookup"><span data-stu-id="e43e6-142">CNAME</span></span>| <span data-ttu-id="e43e6-143">cumplir</span><span class="sxs-lookup"><span data-stu-id="e43e6-143">meet</span></span>|   <span data-ttu-id="e43e6-144">3600</span><span class="sxs-lookup"><span data-stu-id="e43e6-144">3600</span></span>|   <span data-ttu-id="e43e6-145">WebDir.Online.Lync. <span>com</span><span class="sxs-lookup"><span data-stu-id="e43e6-145">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="e43e6-146">CNAME</span><span class="sxs-lookup"><span data-stu-id="e43e6-146">CNAME</span></span>| <span data-ttu-id="e43e6-147">acceso telefónico</span><span class="sxs-lookup"><span data-stu-id="e43e6-147">dialin</span></span>  |<span data-ttu-id="e43e6-148">3600</span><span class="sxs-lookup"><span data-stu-id="e43e6-148">3600</span></span>|  <span data-ttu-id="e43e6-149">WebDir.Online.Lync. <span>com</span><span class="sxs-lookup"><span data-stu-id="e43e6-149">webdir.online.lync.<span>com</span></span>|

2.  <span data-ttu-id="e43e6-150">*Deshabilitar el espacio de direcciones SIP compartido en Office 365 inquilino.*</span><span class="sxs-lookup"><span data-stu-id="e43e6-150">*Disable shared SIP address space in Office 365 tenant.*</span></span>
<span data-ttu-id="e43e6-151">El comando siguiente debe realizarse desde un Skype para la ventana de PowerShell en línea de negocio.</span><span class="sxs-lookup"><span data-stu-id="e43e6-151">The command below needs to be done from a Skype for Business Online PowerShell window.</span></span>

    `Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false`
 
3.  <span data-ttu-id="e43e6-152">*Deshabilitar la capacidad de comunicarse con Office 365 en prem.*</span><span class="sxs-lookup"><span data-stu-id="e43e6-152">*Disable ability in on-prem to communicate with Office 365.*</span></span>  
<span data-ttu-id="e43e6-153">El comando siguiente debe realizarse desde una ventana de PowerShell local.</span><span class="sxs-lookup"><span data-stu-id="e43e6-153">The command below needs to be done from an on-premises PowerShell window.</span></span>  <span data-ttu-id="e43e6-154">Si ha importado previamente un Skype para sesión empresarial en línea, inicie un nuevo Skype para la sesión de PowerShell de negocio.</span><span class="sxs-lookup"><span data-stu-id="e43e6-154">If you have previously imported a Skype for Business Online session, start a new Skype for Business PowerShell session.</span></span>

    `Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false`

## <a name="see-also"></a><span data-ttu-id="e43e6-155">Vea también</span><span class="sxs-lookup"><span data-stu-id="e43e6-155">See also</span></span>

[<span data-ttu-id="e43e6-156">Consolidación de la nube para equipos y Skype para la empresa</span><span class="sxs-lookup"><span data-stu-id="e43e6-156">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)