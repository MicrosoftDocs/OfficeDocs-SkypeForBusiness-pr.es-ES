---
title: Deshabilitar híbrido para completar la migración a Teams solo
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
description: En este artículo se incluyen pasos detallados para deshabilitar la implementación híbrida como parte de la consolidación de la nube Teams y Skype Empresarial.
ms.openlocfilehash: 87bd1f6e0dcabed067174972dd0f0fc51149beb0
ms.sourcegitcommit: 405b22cfd94e50d651f4c3f73fb46780cd8a6d06
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/15/2021
ms.locfileid: "53453649"
---
# <a name="disable-your-hybrid-configuration-to-complete-migration-to-teams-only"></a><span data-ttu-id="3101b-103">Deshabilitar la configuración híbrida para completar la migración a Teams solo</span><span class="sxs-lookup"><span data-stu-id="3101b-103">Disable your hybrid configuration to complete migration to Teams Only</span></span> 

<span data-ttu-id="3101b-104">En este artículo se describe cómo deshabilitar la configuración híbrida antes de retirar el entorno Skype Empresarial local.</span><span class="sxs-lookup"><span data-stu-id="3101b-104">This article describes how to disable your hybrid configuration before decommissioning your on-premises Skype for Business environment.</span></span> <span data-ttu-id="3101b-105">Este es el paso 2 de los siguientes pasos para retirar el entorno local:</span><span class="sxs-lookup"><span data-stu-id="3101b-105">This is step 2 of the following steps to decommission your on-premises environment:</span></span>

- <span data-ttu-id="3101b-106">Paso 1.</span><span class="sxs-lookup"><span data-stu-id="3101b-106">Step 1.</span></span> <span data-ttu-id="3101b-107">[Mueva todos los usuarios necesarios de local a en línea.](decommission-move-on-prem-users.md)</span><span class="sxs-lookup"><span data-stu-id="3101b-107">[Move all required users from on-premises to online](decommission-move-on-prem-users.md).</span></span>

- <span data-ttu-id="3101b-108">**Paso 2. Deshabilite la configuración híbrida.**</span><span class="sxs-lookup"><span data-stu-id="3101b-108">**Step 2. Disable your hybrid configuration.**</span></span> <span data-ttu-id="3101b-109">(Este artículo)</span><span class="sxs-lookup"><span data-stu-id="3101b-109">(This article)</span></span>

- <span data-ttu-id="3101b-110">Paso 3.</span><span class="sxs-lookup"><span data-stu-id="3101b-110">Step 3.</span></span> <span data-ttu-id="3101b-111">[Migre los puntos de conexión de aplicaciones híbridas de local a en línea.](decommission-move-on-prem-endpoints.md)</span><span class="sxs-lookup"><span data-stu-id="3101b-111">[Migrate hybrid application endpoints from on-premises to online](decommission-move-on-prem-endpoints.md).</span></span>

- <span data-ttu-id="3101b-112">Paso 4.</span><span class="sxs-lookup"><span data-stu-id="3101b-112">Step 4.</span></span> <span data-ttu-id="3101b-113">[Quite la implementación Skype Empresarial local.](decommission-remove-on-prem.md)</span><span class="sxs-lookup"><span data-stu-id="3101b-113">[Remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>

> [!NOTE]
> <span data-ttu-id="3101b-114">Los pasos 2 y 3 deben realizarse en la misma ventana de mantenimiento porque los extremos de aplicación híbrida existentes no se podrán detectar entre los pasos 2 y la finalización del paso 3.</span><span class="sxs-lookup"><span data-stu-id="3101b-114">Steps 2 and 3 should be done in the same maintenance window because any existing hybrid application endpoints will not be discoverable between steps 2 and completion of step 3.</span></span>


## <a name="summary"></a><span data-ttu-id="3101b-115">Resumen</span><span class="sxs-lookup"><span data-stu-id="3101b-115">Summary</span></span>

<span data-ttu-id="3101b-116">Después de actualizar todos los usuarios de Skype Empresarial local a Teams Solo en Microsoft 365, puede retirar la implementación Skype Empresarial local.</span><span class="sxs-lookup"><span data-stu-id="3101b-116">After you have upgraded all users from Skype for Business on-premises to Teams Only in Microsoft 365, you can decommission the on-premises Skype for Business deployment.</span></span>

<span data-ttu-id="3101b-117">Antes de retirar la implementación Skype Empresarial local y quitar cualquier hardware, debe separar lógicamente la implementación local de Microsoft 365 deshabilitando la implementación híbrida.</span><span class="sxs-lookup"><span data-stu-id="3101b-117">Before you decommission the on-premises Skype for Business deployment and remove any hardware, you must logically separate the on-premises deployment from Microsoft 365 by disabling hybrid.</span></span> <span data-ttu-id="3101b-118">La deshabilitación híbrida consta de los cuatro pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="3101b-118">Disabling hybrid consists of the following four steps:</span></span>

1. <span data-ttu-id="3101b-119">[Actualice los registros DNS para que apunten a Microsoft 365](#update-dns-to-point-to-microsoft-365).</span><span class="sxs-lookup"><span data-stu-id="3101b-119">[Update DNS records to point to Microsoft 365](#update-dns-to-point-to-microsoft-365).</span></span>

2. <span data-ttu-id="3101b-120">[Cambie el modo de coexistencia de la organización a Teams Solo](#change-the-coexistence-mode-for-your-organization-to-teams-only).</span><span class="sxs-lookup"><span data-stu-id="3101b-120">[Change the coexistence mode for your organization to Teams Only](#change-the-coexistence-mode-for-your-organization-to-teams-only).</span></span>

3. <span data-ttu-id="3101b-121">[Deshabilitar el espacio de direcciones sip compartido (también conocido como "dominio dividido")](#disable-shared-sip-address-space-in-microsoft-365-organization)en la Microsoft 365 organización .</span><span class="sxs-lookup"><span data-stu-id="3101b-121">[Disable shared sip address space (also known as "split domain") in the Microsoft 365 organization](#disable-shared-sip-address-space-in-microsoft-365-organization).</span></span>

4. [<span data-ttu-id="3101b-122">Deshabilitar la comunicación entre locales y Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3101b-122">Disable communication between on-premises and Microsoft 365</span></span>](#disable-communication-between-on-premises-and-microsoft-365)

<span data-ttu-id="3101b-123">Estos pasos separan lógicamente la implementación local de Skype Empresarial Server de Microsoft 365 y garantizan que la organización Teams solo.</span><span class="sxs-lookup"><span data-stu-id="3101b-123">These steps logically separate your on-premises deployment of Skype for Business Server from Microsoft 365 and ensure your organization is fully Teams Only.</span></span> <span data-ttu-id="3101b-124">Después de completar estos pasos, puede retirar la implementación de Skype Empresarial local mediante uno de los dos métodos a los que se hace referencia en [Decide how to manage attributes after decommissioning](cloud-consolidation-managing-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="3101b-124">After you've completed these steps, you can decommission your on-premises Skype for Business deployment by using one of two methods referenced in [Decide how to manage attributes after decommissioning](cloud-consolidation-managing-attributes.md).</span></span>

> [!Important] 
> <span data-ttu-id="3101b-125">Una vez completada esta separación lógica, los atributos msRTCSIP de su Active Directory local siguen teniendo valores y seguirán sincroniendo a través de Azure AD Conectar en Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3101b-125">Once this logical separation is complete, msRTCSIP attributes from your on-premises Active Directory still have values and will continue to sync via Azure AD Connect into Azure AD.</span></span> <span data-ttu-id="3101b-126">La forma de retirar el entorno local depende de si desea dejar estos atributos en su lugar o, en primer lugar, borrarlos de su Active Directory local.</span><span class="sxs-lookup"><span data-stu-id="3101b-126">How you decommission the on-premises environment depends on whether you intend to leave these attributes in place, or first clear them from your on-premises Active Directory.</span></span> <span data-ttu-id="3101b-127">Tenga en cuenta que borrar los atributos msRTCSIP locales después de migrar desde local podría provocar la pérdida de servicio para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="3101b-127">Be aware that clearing the on-premises msRTCSIP attributes after you have migrated from on-premises could result in loss of service for users!</span></span> <span data-ttu-id="3101b-128">Los detalles y las transacciones de los dos enfoques de retirada se describen en [Decide how to manage attributes after decommissioning](cloud-consolidation-managing-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="3101b-128">Details and tradeoffs of the two decommissioning approaches are described in [Decide how to manage attributes after decommissioning](cloud-consolidation-managing-attributes.md).</span></span>

## <a name="update-dns-to-point-to-microsoft-365"></a><span data-ttu-id="3101b-129">Actualizar DNS para que apunte a Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3101b-129">Update DNS to point to Microsoft 365</span></span>

<span data-ttu-id="3101b-130">El DNS externo de la organización para la organización local debe actualizarse para que los registros Skype Empresarial apunten a Microsoft 365 en lugar de a la implementación local.</span><span class="sxs-lookup"><span data-stu-id="3101b-130">The organization’s external DNS for the on-premises organization needs to be updated so that Skype for Business records point to Microsoft 365 instead of the on-premises deployment.</span></span> 

<span data-ttu-id="3101b-131">Además, se pueden eliminar los registros CNAME para meet o dialin (si están presentes).</span><span class="sxs-lookup"><span data-stu-id="3101b-131">In addition, CNAME records for meet or dialin (if present) can be deleted.</span></span> <span data-ttu-id="3101b-132">Por último, se deben quitar los registros DNS Skype Empresarial de la red interna.</span><span class="sxs-lookup"><span data-stu-id="3101b-132">Finally, any DNS records for Skype for Business in your internal network should be removed.</span></span>

<span data-ttu-id="3101b-133">Para obtener información detallada acerca de la actualización de registros [DNS,](decommission-manage-dns-entries.md)vea Actualizar entradas DNS para permitir que la organización sea Teams solo .</span><span class="sxs-lookup"><span data-stu-id="3101b-133">For details about updating DNS records, see [Update DNS entries to enable your organization to be all Teams Only](decommission-manage-dns-entries.md).</span></span>

## <a name="change-the-coexistence-mode-for-your-organization-to-teams-only"></a><span data-ttu-id="3101b-134">Cambiar el modo de coexistencia de la organización a Teams solo</span><span class="sxs-lookup"><span data-stu-id="3101b-134">Change the coexistence mode for your organization to Teams Only</span></span>

<span data-ttu-id="3101b-135">Este paso garantiza que cualquier nuevo usuario de la organización siempre se cree como un Teams solo usuario.</span><span class="sxs-lookup"><span data-stu-id="3101b-135">This step ensures that any new user in your organization is always created as a Teams Only user.</span></span> 

<span data-ttu-id="3101b-136">Al intentar cambiar el modo de inquilino a Teams Only comprobará automáticamente la existencia de los registros DNS locales que se hayan perdido en el paso 1 e identificará estos registros en el resultado.</span><span class="sxs-lookup"><span data-stu-id="3101b-136">Attempting to change the tenant mode to Teams Only will automatically check for existence of any on-premises DNS records that may have been missed in step 1 and identify these records in the output.</span></span> <span data-ttu-id="3101b-137">Cambiar el modo de inquilino a Teams Solo no se realizará correctamente hasta que se actualicen todos los registros DNS de la organización.</span><span class="sxs-lookup"><span data-stu-id="3101b-137">Changing the tenant mode to Teams Only will not succeed until all DNS records for your organization are updated.</span></span> 

<span data-ttu-id="3101b-138">Para cambiar el modo de inquilino a Teams ejecute el siguiente comando desde una ventana Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3101b-138">To change the tenant mode to Teams Only run the following command from a Teams PowerShell window.</span></span>

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Global
```

<span data-ttu-id="3101b-139">Como alternativa, puede usar el Centro de administración de Teams para cambiar el modo de coexistencia de inquilinos a TeamsOnly, en "Configuración de toda la organización" -> "Teams upgrade".</span><span class="sxs-lookup"><span data-stu-id="3101b-139">Alternatively, you can use the Teams Admin Center to change the tenant coexistence mode to TeamsOnly, under "Org-wide settings" -> "Teams Upgrade."</span></span>    

## <a name="disable-shared-sip-address-space-in-microsoft-365-organization"></a><span data-ttu-id="3101b-140">Deshabilitar el espacio de direcciones sip compartido en Microsoft 365 organización</span><span class="sxs-lookup"><span data-stu-id="3101b-140">Disable shared sip address space in Microsoft 365 organization</span></span>
    
<span data-ttu-id="3101b-141">Para deshabilitar el espacio de direcciones sip compartido, ejecute el siguiente comando desde una ventana Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3101b-141">To disable shared sip address space, run the following command from a Teams PowerShell window.</span></span>

```PowerShell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
```
 
## <a name="disable-communication-between-on-premises-and-microsoft-365"></a><span data-ttu-id="3101b-142">Deshabilitar la comunicación entre locales y Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3101b-142">Disable communication between on-premises and Microsoft 365</span></span>

<span data-ttu-id="3101b-143">Para deshabilitar la comunicación entre el entorno local y Microsoft 365, ejecute el siguiente comando desde una ventana de PowerShell local:</span><span class="sxs-lookup"><span data-stu-id="3101b-143">To disable communication between the on-premises environment and Microsoft 365, run the following command from an on-premises PowerShell window:</span></span>

```PowerShell
Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
```


## <a name="see-also"></a><span data-ttu-id="3101b-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="3101b-144">See also</span></span>

- [<span data-ttu-id="3101b-145">Consolidación de nube para Teams y Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="3101b-145">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)

- [<span data-ttu-id="3101b-146">Retirar el entorno local de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="3101b-146">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

