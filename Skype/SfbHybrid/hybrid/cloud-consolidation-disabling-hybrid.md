---
title: Deshabilitar la implementación híbrida para completar la migración a la nube
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
f1.keywords:
- NOCSH
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: Este apéndice incluye pasos detallados para deshabilitar la implementación híbrida como parte de la consolidación en la nube para Teams y Skype empresarial.
ms.openlocfilehash: 053d632b5a07b7ce7cca8ef7a1ddf45a673bcf59
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780149"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud"></a><span data-ttu-id="ac0f7-103">Deshabilitar la implementación híbrida para completar la migración a la nube</span><span class="sxs-lookup"><span data-stu-id="ac0f7-103">Disable hybrid to complete migration to the cloud</span></span>

<span data-ttu-id="ac0f7-104">Después de mover todos los usuarios del entorno local a la nube, puede desactivar la implementación local de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="ac0f7-104">After you have moved all users from on-premises to the cloud, you can decommission the on-premises Skype for Business deployment.</span></span> <span data-ttu-id="ac0f7-105">Aparte de quitar el hardware, un paso crítico es separar lógicamente la implementación local de Office 365 deshabilitando la implementación híbrida.</span><span class="sxs-lookup"><span data-stu-id="ac0f7-105">Aside from removing any hardware, a critical step is to logically separate that on-premises deployment from Office 365 by disabling hybrid.</span></span> <span data-ttu-id="ac0f7-106">La deshabilitación de un híbrido consta de tres pasos:</span><span class="sxs-lookup"><span data-stu-id="ac0f7-106">Disabling hybrid consists of 3 steps:</span></span>

1. <span data-ttu-id="ac0f7-107">Actualizar los registros DNS para que apunten a Office 365.</span><span class="sxs-lookup"><span data-stu-id="ac0f7-107">Update DNS records to point to Office 365.</span></span>

2. <span data-ttu-id="ac0f7-108">Deshabilite el dominio dividido en la organización de Office 365.</span><span class="sxs-lookup"><span data-stu-id="ac0f7-108">Disable split domain in the Office 365 organization.</span></span>

3. <span data-ttu-id="ac0f7-109">Deshabilite la capacidad local para comunicarse con Office 365.</span><span class="sxs-lookup"><span data-stu-id="ac0f7-109">Disable the ability in on-premises to communicate with Office 365.</span></span>

<span data-ttu-id="ac0f7-110">Estos pasos deben realizarse juntos como una unidad.</span><span class="sxs-lookup"><span data-stu-id="ac0f7-110">These steps should be done together as a unit.</span></span> <span data-ttu-id="ac0f7-111">A continuación se proporcionan detalles.</span><span class="sxs-lookup"><span data-stu-id="ac0f7-111">Details are provided below.</span></span> <span data-ttu-id="ac0f7-112">Además, se proporcionan instrucciones para administrar los números de teléfono de los usuarios migrados una vez que la implementación local está desconectada.</span><span class="sxs-lookup"><span data-stu-id="ac0f7-112">In addition, guidelines are provided for managing phone numbers for migrated users once the on-premises deployment is disconnected.</span></span>

> [!Note] 
> <span data-ttu-id="ac0f7-113">En raras ocasiones, al cambiar el DNS de los locales a Office 365 para su organización, la Federación con otras organizaciones puede dejar de funcionar hasta que la otra organización actualice la configuración de la Federación:</span><span class="sxs-lookup"><span data-stu-id="ac0f7-113">In rare cases, changing DNS from pointing on premises to Office 365 for your organization may cause federation with some other organizations to stop working until that other organization updates their federation configuration:</span></span><ul><li>
<span data-ttu-id="ac0f7-114">Todas las organizaciones federadas que usen el modelo de Federación directa anterior (también conocido como servidor asociado permitido) tendrán que actualizar las entradas de dominio permitidas en su organización para quitar el FQDN del proxy.</span><span class="sxs-lookup"><span data-stu-id="ac0f7-114">Any federated organizations that are using the older Direct Federation model (also known as Allowed Partner Server) will need to update their allowed domain entries for their organization to remove the proxy FQDN.</span></span> <span data-ttu-id="ac0f7-115">Este modelo de Federación heredada no se basa en los registros SRV de DNS, por lo que dicha configuración quedará obsoleta una vez que la organización se traslade a la nube.</span><span class="sxs-lookup"><span data-stu-id="ac0f7-115">This legacy federation model is not based on DNS SRV records, so such a configuration will become out of date once your organization moves to the cloud.</span></span> </li><li><span data-ttu-id="ac0f7-116">Cualquier organización federada que no tenga un proveedor de hospedaje habilitado para sipfed. online. Lync. <span>com tendrá que actualizar su configuración para habilitarlo.</span><span class="sxs-lookup"><span data-stu-id="ac0f7-116">Any federated organization that does not have an enabled hosting provider for sipfed.online.lync.<span>com will need to update their configuration to enable that.</span></span> <span data-ttu-id="ac0f7-117">Esta situación solo es posible si la organización federada se encuentra exclusivamente local y nunca se ha federado con ningún inquilino híbrido o en línea.</span><span class="sxs-lookup"><span data-stu-id="ac0f7-117">This situation is only possible if the federated organization is purely on premises and has never federated with any hybrid or online tenant.</span></span> <span data-ttu-id="ac0f7-118">En tal caso, la Federación con estas organizaciones no funcionará hasta que habilite su proveedor de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="ac0f7-118">In such a case, federation with these organizations will not work until they enable their hosting provider.</span></span></li></ul><span data-ttu-id="ac0f7-119">Si sospecha que cualquiera de sus socios federados puede usar Federación directa o que se ha federado con una organización en línea o híbrida, le sugerimos que les envíe una comunicación sobre esto cuando se prepare para completar la migración a la nube.</span><span class="sxs-lookup"><span data-stu-id="ac0f7-119">If you suspect that any of your federated partners may be using Direct Federation or have federated with any online or hybrid organization, we suggest you send them a communication about this as you prepare to complete your migration to the cloud.</span></span>

1.  <span data-ttu-id="ac0f7-120">*Actualice DNS para que apunte a Office 365.*</span><span class="sxs-lookup"><span data-stu-id="ac0f7-120">*Update DNS to point to Office 365.*</span></span>
<span data-ttu-id="ac0f7-121">El DNS externo de la organización para la organización local debe actualizarse para que los registros de Skype empresarial apunten a Office 365 en lugar de a la implementación local.</span><span class="sxs-lookup"><span data-stu-id="ac0f7-121">The organization’s external DNS for the on-premises organization needs to be updated so that Skype for Business records point to Office 365 instead of the on-premises deployment.</span></span> <span data-ttu-id="ac0f7-122">En particular:</span><span class="sxs-lookup"><span data-stu-id="ac0f7-122">Specifically:</span></span>

    |<span data-ttu-id="ac0f7-123">Tipo de registro</span><span class="sxs-lookup"><span data-stu-id="ac0f7-123">Record type</span></span>|<span data-ttu-id="ac0f7-124">Nombre</span><span class="sxs-lookup"><span data-stu-id="ac0f7-124">Name</span></span>|<span data-ttu-id="ac0f7-125">TTL</span><span class="sxs-lookup"><span data-stu-id="ac0f7-125">TTL</span></span>|<span data-ttu-id="ac0f7-126">Valor</span><span class="sxs-lookup"><span data-stu-id="ac0f7-126">Value</span></span>|
    |---|---|---|---|
    |<span data-ttu-id="ac0f7-127">SRV</span><span class="sxs-lookup"><span data-stu-id="ac0f7-127">SRV</span></span>|<span data-ttu-id="ac0f7-128">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="ac0f7-128">_sipfederationtls._tcp</span></span>|<span data-ttu-id="ac0f7-129">3600</span><span class="sxs-lookup"><span data-stu-id="ac0f7-129">3600</span></span>|<span data-ttu-id="ac0f7-130">100 1 5061 sipfed. online. Lync. <span>com</span><span class="sxs-lookup"><span data-stu-id="ac0f7-130">100 1 5061 sipfed.online.lync.<span>com</span></span>|
    |<span data-ttu-id="ac0f7-131">SRV</span><span class="sxs-lookup"><span data-stu-id="ac0f7-131">SRV</span></span>|<span data-ttu-id="ac0f7-132">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="ac0f7-132">_sip._tls</span></span>|<span data-ttu-id="ac0f7-133">3600</span><span class="sxs-lookup"><span data-stu-id="ac0f7-133">3600</span></span>|<span data-ttu-id="ac0f7-134">100 1 443 sipdir. online. Lync. <span>com</span><span class="sxs-lookup"><span data-stu-id="ac0f7-134">100 1 443 sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="ac0f7-135">CNAME</span><span class="sxs-lookup"><span data-stu-id="ac0f7-135">CNAME</span></span>| <span data-ttu-id="ac0f7-136">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="ac0f7-136">lyncdiscover</span></span>|   <span data-ttu-id="ac0f7-137">3600</span><span class="sxs-lookup"><span data-stu-id="ac0f7-137">3600</span></span>|   <span data-ttu-id="ac0f7-138">webdir. online. Lync. <span>com</span><span class="sxs-lookup"><span data-stu-id="ac0f7-138">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="ac0f7-139">CNAME</span><span class="sxs-lookup"><span data-stu-id="ac0f7-139">CNAME</span></span>| <span data-ttu-id="ac0f7-140">sip</span><span class="sxs-lookup"><span data-stu-id="ac0f7-140">sip</span></span>|    <span data-ttu-id="ac0f7-141">3600</span><span class="sxs-lookup"><span data-stu-id="ac0f7-141">3600</span></span>|   <span data-ttu-id="ac0f7-142">sipdir. online. Lync. <span>com</span><span class="sxs-lookup"><span data-stu-id="ac0f7-142">sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="ac0f7-143">CNAME</span><span class="sxs-lookup"><span data-stu-id="ac0f7-143">CNAME</span></span>| <span data-ttu-id="ac0f7-144">cumplir</span><span class="sxs-lookup"><span data-stu-id="ac0f7-144">meet</span></span>|   <span data-ttu-id="ac0f7-145">3600</span><span class="sxs-lookup"><span data-stu-id="ac0f7-145">3600</span></span>|   <span data-ttu-id="ac0f7-146">webdir. online. Lync. <span>com</span><span class="sxs-lookup"><span data-stu-id="ac0f7-146">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="ac0f7-147">CNAME</span><span class="sxs-lookup"><span data-stu-id="ac0f7-147">CNAME</span></span>| <span data-ttu-id="ac0f7-148">Dialin</span><span class="sxs-lookup"><span data-stu-id="ac0f7-148">dialin</span></span>  |<span data-ttu-id="ac0f7-149">3600</span><span class="sxs-lookup"><span data-stu-id="ac0f7-149">3600</span></span>|  <span data-ttu-id="ac0f7-150">webdir. online. Lync. <span>com</span><span class="sxs-lookup"><span data-stu-id="ac0f7-150">webdir.online.lync.<span>com</span></span>|

2.  <span data-ttu-id="ac0f7-151">*Deshabilite el espacio de direcciones SIP compartido en la organización de Office 365.*</span><span class="sxs-lookup"><span data-stu-id="ac0f7-151">*Disable shared SIP address space in Office 365 organization.*</span></span>
<span data-ttu-id="ac0f7-152">El siguiente comando debe realizarse desde una ventana de PowerShell de Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="ac0f7-152">The command below needs to be done from a Skype for Business Online PowerShell window.</span></span>

    ```PowerShell
    Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
    ```
 
3.  <span data-ttu-id="ac0f7-153">*Deshabilite la capacidad local para comunicarse con Office 365.*</span><span class="sxs-lookup"><span data-stu-id="ac0f7-153">*Disable ability in on-premises to communicate with Office 365.*</span></span>  
<span data-ttu-id="ac0f7-154">El siguiente comando debe realizarse desde una ventana de PowerShell local:</span><span class="sxs-lookup"><span data-stu-id="ac0f7-154">The command below needs to be done from an on-premises PowerShell window:</span></span>
```PowerShell
    Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
```

### <a name="manage-phone-numbers-for-users-who-were-migrated-from-on-premises"></a><span data-ttu-id="ac0f7-155">Administrar los números de teléfono para los usuarios que se han migrado de local</span><span class="sxs-lookup"><span data-stu-id="ac0f7-155">Manage phone numbers for users who were migrated from on-premises</span></span>

<span data-ttu-id="ac0f7-156">Los administradores pueden administrar los usuarios que se movieron anteriormente desde un servidor local de Skype empresarial Server a la nube, incluso después de que se haya retirado la implementación local.</span><span class="sxs-lookup"><span data-stu-id="ac0f7-156">Administrators can manage users who were previously moved from an on-premises Skype for Business Server to the cloud, even after the on-premises deployment is decommissioned.</span></span> <span data-ttu-id="ac0f7-157">Hay dos posibilidades diferentes:</span><span class="sxs-lookup"><span data-stu-id="ac0f7-157">There are two different possibilities:</span></span>

- <span data-ttu-id="ac0f7-158">El usuario no tenía un valor para LineURI local antes del movimiento.</span><span class="sxs-lookup"><span data-stu-id="ac0f7-158">The user did not have a value for LineURI on-premises before the move.</span></span> 

  <span data-ttu-id="ac0f7-159">En este caso, puede modificar la LineURI con los parámetros-onpremLineUri del [cmdlet Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) en el módulo de PowerShell de Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="ac0f7-159">In this case, you can modify the LineURI using the -onpremLineUri parameters in the [Set-CsUser cmdlet](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) in the Skype for Business Online PowerShell module.</span></span>

- <span data-ttu-id="ac0f7-160">El usuario tenía un LineURI local antes del movimiento (presumiblemente porque el usuario estaba habilitado para telefonía IP empresarial).</span><span class="sxs-lookup"><span data-stu-id="ac0f7-160">The user had a LineURI on-premises before the move (presumably because the user was enabled for Enterprise Voice).</span></span> 

  <span data-ttu-id="ac0f7-161">Si desea cambiar la LineURI, debe hacerlo en Active Directory local y dejar que el valor pase a Azure AD...</span><span class="sxs-lookup"><span data-stu-id="ac0f7-161">If you want to change the LineURI, you must do this in the on-premises Active Directory and let the value flow up to Azure AD.</span></span> <span data-ttu-id="ac0f7-162">Esto no requiere Skype empresarial Server local.</span><span class="sxs-lookup"><span data-stu-id="ac0f7-162">This does NOT require on-premises Skype for Business Server.</span></span> <span data-ttu-id="ac0f7-163">En su lugar, este atributo, msRTCSIP-line, se puede editar directamente en Active Directory local, mediante el complemento usuarios y equipos de Active Directory de MMC, o bien mediante PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ac0f7-163">Rather, this attribute, msRTCSIP-Line, can be edited directly in the on-premises Active Directory, using either the Active Directory Users and Computers MMC snap-in, or by using PowerShell.</span></span> <span data-ttu-id="ac0f7-164">Si está usando el complemento de MMC, abra la página de propiedades del usuario, haga clic en la pestaña Editor de atributos y busque msRTCSIP-line.</span><span class="sxs-lookup"><span data-stu-id="ac0f7-164">If you are using the MMC snap-in, open to the properties page of the user, click Attribute Editor tab, and find msRTCSIP-Line.</span></span>

  ![Herramienta usuarios y equipos de Active Directory](../media/disable-hybrid-1.png)

## <a name="see-also"></a><span data-ttu-id="ac0f7-166">Ver también</span><span class="sxs-lookup"><span data-stu-id="ac0f7-166">See also</span></span>

[<span data-ttu-id="ac0f7-167">Consolidación en la nube para Teams y Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="ac0f7-167">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)
