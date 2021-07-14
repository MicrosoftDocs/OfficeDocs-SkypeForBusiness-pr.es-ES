---
title: Migrar puntos de conexión de aplicaciones híbridas a la nube
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Migre los puntos de conexión de la aplicación hirid antes de retirar Skype Empresarial entorno local.
ms.openlocfilehash: 7315ee807bb79b9186cd92ccc19074021b2fcfa1
ms.sourcegitcommit: f39484688800a3d22f361e660d0eeba974a44fb1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420805"
---
# <a name="migrate-hybrid-application-endpoints-before-decommissioning-your-on-premises-environment"></a><span data-ttu-id="ad7d2-103">Migrar puntos de conexión de aplicaciones híbridas antes de retirar el entorno local</span><span class="sxs-lookup"><span data-stu-id="ad7d2-103">Migrate hybrid application endpoints before decommissioning your on-premises environment</span></span>

<span data-ttu-id="ad7d2-104">En este artículo se describe cómo mover puntos de conexión de aplicación híbrida necesarios a la nube de Microsoft antes de retirar el entorno Skype Empresarial local.</span><span class="sxs-lookup"><span data-stu-id="ad7d2-104">This article describes how to move required hybrid application endpoints to the Microsoft cloud before decommissioning your on-premises Skype for Business environment.</span></span> <span data-ttu-id="ad7d2-105">Este es el paso 3 de los siguientes pasos para retirar el entorno local:</span><span class="sxs-lookup"><span data-stu-id="ad7d2-105">This is step 3 of the following steps to decommission your on-premises environment:</span></span>

- <span data-ttu-id="ad7d2-106">Paso 1.</span><span class="sxs-lookup"><span data-stu-id="ad7d2-106">Step 1.</span></span> [<span data-ttu-id="ad7d2-107">Mover todos los usuarios necesarios de local a online</span><span class="sxs-lookup"><span data-stu-id="ad7d2-107">Move all required users from on-premises to online</span></span>](decommission-move-on-prem-users.md)

- <span data-ttu-id="ad7d2-108">Paso 2.</span><span class="sxs-lookup"><span data-stu-id="ad7d2-108">Step 2.</span></span> <span data-ttu-id="ad7d2-109">[Deshabilite la configuración híbrida](cloud-consolidation-disabling-hybrid.md).</span><span class="sxs-lookup"><span data-stu-id="ad7d2-109">[Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

- <span data-ttu-id="ad7d2-110">**Paso 3. Migre los puntos de conexión de aplicaciones híbridas de local a online.**</span><span class="sxs-lookup"><span data-stu-id="ad7d2-110">**Step 3. Migrate hybrid application endpoints from on-premises to online.**</span></span> <span data-ttu-id="ad7d2-111">(Este artículo)</span><span class="sxs-lookup"><span data-stu-id="ad7d2-111">(This article)</span></span>

- <span data-ttu-id="ad7d2-112">Paso 4.</span><span class="sxs-lookup"><span data-stu-id="ad7d2-112">Step 4.</span></span> <span data-ttu-id="ad7d2-113">[Quite la implementación Skype Empresarial local.](decommission-remove-on-prem.md)</span><span class="sxs-lookup"><span data-stu-id="ad7d2-113">[Remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>


## <a name="migrate-all-required-hybrid-application-endpoints-from-on-premises-to-online"></a><span data-ttu-id="ad7d2-114">Migrar todos los extremos de aplicación híbrida necesarios de local a online</span><span class="sxs-lookup"><span data-stu-id="ad7d2-114">Migrate all required hybrid application endpoints from on-premises to online</span></span>

<span data-ttu-id="ad7d2-115">Para poder mover estos puntos de conexión a línea, debe asegurarse de que ha actualizado los registros DNS para que apunten a Microsoft 365 para todos los dominios sip usados por los puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="ad7d2-115">Before you can move these endpoints to online, you must ensure you have updated DNS records to point to Microsoft 365 for all sip domains used by the endpoints.</span></span> <span data-ttu-id="ad7d2-116">Tenga en cuenta que una vez que actualice DNS para que apunte a Microsoft 365, los puntos de conexión de aplicaciones híbridas existentes ya no se podrán detectar hasta que complete este paso.</span><span class="sxs-lookup"><span data-stu-id="ad7d2-116">Be aware that once you update DNS to point to Microsoft 365, any existing hybrid application endpoints will no longer be discoverable until you complete this step.</span></span> <span data-ttu-id="ad7d2-117">Dado que este paso (crear cuentas de recursos en línea) no es posible si los registros DNS apuntan a local, debe planear realizar los pasos 2 y 3 en la misma ventana de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="ad7d2-117">Since this step (creating online Resource Accounts) is not possible if DNS records point to on-premises you should plan to do both steps 2 and 3 in the same maintenance window.</span></span> <span data-ttu-id="ad7d2-118">Para obtener más información, vea [Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span><span class="sxs-lookup"><span data-stu-id="ad7d2-118">For more information, see [Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

1. <span data-ttu-id="ad7d2-119">Recupere y exporte la configuración de extremo de aplicación híbrida local ejecutando el siguiente comando de PowerShell Skype Empresarial Server local:</span><span class="sxs-lookup"><span data-stu-id="ad7d2-119">Retrieve and export on-premises hybrid application endpoint settings by executing the following on-premises Skype for Business Server PowerShell command:</span></span>

   ```PowerShell
   Get-CsHybridApplicationEndpoint|select Sipaddress, DisplayName, ApplicationID, LineUri |Export-Csv -Path "c:\backup\HybridEndpoints.csv"
   ```
2. <span data-ttu-id="ad7d2-120">Cree y licencia nuevas [cuentas de](/microsoftteams/manage-resource-accounts) recursos en Microsoft 365 reemplazar los puntos de conexión de aplicación híbrida locales existentes.</span><span class="sxs-lookup"><span data-stu-id="ad7d2-120">Create and license new [Resource Accounts](/microsoftteams/manage-resource-accounts) in Microsoft 365 to replace the existing on-premises hybrid application endpoints.</span></span>

3. <span data-ttu-id="ad7d2-121">Asocie las nuevas cuentas de recursos con los extremos de aplicación híbrida existentes.</span><span class="sxs-lookup"><span data-stu-id="ad7d2-121">Associate the new Resource Accounts with the existing hybrid application endpoints.</span></span>

4. <span data-ttu-id="ad7d2-122">Quite los números de teléfono definidos en los extremos de la aplicación híbrida local ejecutando el siguiente comando de PowerShell Skype Empresarial Server local:</span><span class="sxs-lookup"><span data-stu-id="ad7d2-122">Remove phone numbers defined in the on-premises hybrid application endpoints by executing the following on-premises Skype for Business Server PowerShell command:</span></span>

   ```PowerShell
   Get-CsHybridApplicationEndpoint -Filter {LineURI -ne $null} | Set-CsHybridApplicationEndpoint -LineURI ""
   ```
5. <span data-ttu-id="ad7d2-123">Dado que es posible que los números de teléfono de estas cuentas se administraron en Microsoft 365 en lugar de local, ejecute el siguiente comando en Skype Empresarial PowerShell en línea:</span><span class="sxs-lookup"><span data-stu-id="ad7d2-123">Because it's possible that phone numbers for these accounts were managed in Microsoft 365 instead of on-premises, run the following command in Skype for Business Online PowerShell:</span></span>

   ```PowerShell
   $endpoints = import-csv "c:\backup\HybridEndpoints.csv"
   foreach ($endpoint in $endpoints)
   {
   if($endpoint.LineUri)
       {
           $upn = $endpoint.SipAddress.Replace("sip:","")
           $ra=Get-CsOnlineApplicationInstance | where UserPrincipalName -eq $upn 
           Set-CsOnlineApplicationInstance -Identity $ra.Objectid -OnpremPhoneNumber ""
       }
   }
   ```

6. <span data-ttu-id="ad7d2-124">Asigne números de teléfono a las nuevas cuentas de recursos creadas en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="ad7d2-124">Assign phone numbers to the new Resource Accounts created in Step 2.</span></span> <span data-ttu-id="ad7d2-125">Para obtener más información acerca de cómo asignar un número de teléfono a una cuenta de recurso, vea el siguiente artículo: [Asignar un número de servicio](/microsoftteams/manage-resource-accounts#assign-a-service-number).</span><span class="sxs-lookup"><span data-stu-id="ad7d2-125">For more information about how to assign a phone number to a resource account, see the following article: [Assign a service number](/microsoftteams/manage-resource-accounts#assign-a-service-number).</span></span>

7. <span data-ttu-id="ad7d2-126">Elimine los extremos locales ejecutando el siguiente comando local Skype Empresarial Server PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ad7d2-126">Delete the on-premises endpoints by executing the following on-premises Skype for Business Server PowerShell command:</span></span>

   ```PowerShell
   Get-CsHybridApplicationEndpoint | Remove-CsHybridApplicationEndpoint
   ```
<span data-ttu-id="ad7d2-127">Ya está listo para [quitar la implementación Skype Empresarial local.](decommission-remove-on-prem.md)</span><span class="sxs-lookup"><span data-stu-id="ad7d2-127">You are now ready to [remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ad7d2-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ad7d2-128">See also</span></span>

- [<span data-ttu-id="ad7d2-129">Retirar el entorno local de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="ad7d2-129">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

- [<span data-ttu-id="ad7d2-130">Mover todos los usuarios necesarios de local a online</span><span class="sxs-lookup"><span data-stu-id="ad7d2-130">Move all required users from on-premises to online</span></span>](decommission-move-on-prem-users.md)

- [<span data-ttu-id="ad7d2-131">Deshabilitar la configuración híbrida</span><span class="sxs-lookup"><span data-stu-id="ad7d2-131">Disable your hybrid configuration</span></span>](cloud-consolidation-disabling-hybrid.md)

- [<span data-ttu-id="ad7d2-132">Eliminar la implementación local de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="ad7d2-132">Remove your on-premises Skype for Business deployment</span></span>](decommission-remove-on-prem.md)




