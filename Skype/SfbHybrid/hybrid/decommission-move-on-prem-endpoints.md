---
title: Mover puntos de conexión de aplicaciones híbridas a la nube
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
description: Mueva los puntos de conexión de la aplicación hirid antes de retirar Skype Empresarial entorno local.
ms.openlocfilehash: 562da9e8e83684ab3ff532be68190161ffc412b5
ms.sourcegitcommit: 02703e8f9a512848e158a3a4f38d84501ad5f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52526723"
---
# <a name="move-hybrid-application-endpoints-before-decommissioning-your-on-premises-environment"></a><span data-ttu-id="f9c83-103">Mover puntos de conexión de aplicaciones híbridas antes de retirar el entorno local</span><span class="sxs-lookup"><span data-stu-id="f9c83-103">Move hybrid application endpoints before decommissioning your on-premises environment</span></span>

<span data-ttu-id="f9c83-104">En este artículo se describe cómo mover puntos de conexión de aplicación híbrida necesarios a la nube de Microsoft antes de retirar el entorno Skype Empresarial local.</span><span class="sxs-lookup"><span data-stu-id="f9c83-104">This article describes how to move required hybrid application endpoints to the Microsoft cloud before decommissioning your on-premises Skype for Business environment.</span></span> <span data-ttu-id="f9c83-105">Este es el paso 3 de los siguientes pasos para retirar el entorno local:</span><span class="sxs-lookup"><span data-stu-id="f9c83-105">This is step 3 of the following steps to decommission your on-premises environment:</span></span>

- <span data-ttu-id="f9c83-106">Paso 1.</span><span class="sxs-lookup"><span data-stu-id="f9c83-106">Step 1.</span></span> [<span data-ttu-id="f9c83-107">Mover todos los usuarios necesarios de local a online</span><span class="sxs-lookup"><span data-stu-id="f9c83-107">Move all required users from on-premises to online</span></span>](decommission-move-on-prem-users.md)

- <span data-ttu-id="f9c83-108">Paso 2.</span><span class="sxs-lookup"><span data-stu-id="f9c83-108">Step 2.</span></span> <span data-ttu-id="f9c83-109">[Deshabilite la configuración híbrida](cloud-consolidation-disabling-hybrid.md).</span><span class="sxs-lookup"><span data-stu-id="f9c83-109">[Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

- <span data-ttu-id="f9c83-110">**Paso 3. Mueva los puntos de conexión de aplicaciones híbridas de local a online.**</span><span class="sxs-lookup"><span data-stu-id="f9c83-110">**Step 3. Move hybrid application endpoints from on-premises to online.**</span></span> <span data-ttu-id="f9c83-111">(Este artículo)</span><span class="sxs-lookup"><span data-stu-id="f9c83-111">(This article)</span></span>

- <span data-ttu-id="f9c83-112">Paso 4.</span><span class="sxs-lookup"><span data-stu-id="f9c83-112">Step 4.</span></span> <span data-ttu-id="f9c83-113">[Quite la implementación Skype Empresarial local.](decommission-remove-on-prem.md)</span><span class="sxs-lookup"><span data-stu-id="f9c83-113">[Remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>


## <a name="move-all-required-hybrid-application-endpoints-from-on-premises-to-online"></a><span data-ttu-id="f9c83-114">Mover todos los extremos de aplicación híbrida necesarios de local a online</span><span class="sxs-lookup"><span data-stu-id="f9c83-114">Move all required hybrid application endpoints from on-premises to online</span></span>

<span data-ttu-id="f9c83-115">Para poder mover estos puntos de conexión a línea, debe asegurarse de que ha actualizado los registros DNS para que apunten a Microsoft 365 para todos los dominios sip usados por los puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="f9c83-115">Before you can move these endpoints to online, you must ensure you have updated DNS records to point to Microsoft 365 for all sip domains used by the endpoints.</span></span> <span data-ttu-id="f9c83-116">No es posible crear cuentas de recursos en línea si los registros DNS apuntan a local.</span><span class="sxs-lookup"><span data-stu-id="f9c83-116">It is not possible to create online Resource Accounts if DNS records point to on-premises.</span></span> <span data-ttu-id="f9c83-117">Para obtener más información, vea [Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span><span class="sxs-lookup"><span data-stu-id="f9c83-117">For more information, see [Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

1. <span data-ttu-id="f9c83-118">Recupere y exporte la configuración de extremo de aplicación híbrida local ejecutando el siguiente comando de PowerShell Skype Empresarial Server local:</span><span class="sxs-lookup"><span data-stu-id="f9c83-118">Retrieve and export on-premises hybrid application endpoint settings by executing the following on-premises Skype for Business Server PowerShell command:</span></span>

   ```PowerShell
   Get-CsHybridApplicationEndpoint|select Sipaddress, DisplayName, ApplicationID, LineUri |Export-Csv -Path "c:\backup\HybridEndpoints.csv"
   ```
2. <span data-ttu-id="f9c83-119">Cree y licencia nuevas [cuentas de](https://docs.microsoft.com/microsoftteams/manage-resource-accounts) recursos en Microsoft 365 reemplazar los puntos de conexión de aplicación híbrida locales existentes.</span><span class="sxs-lookup"><span data-stu-id="f9c83-119">Create and license new [Resource Accounts](https://docs.microsoft.com/microsoftteams/manage-resource-accounts) in Microsoft 365 to replace the existing on-premises hybrid application endpoints.</span></span>

3. <span data-ttu-id="f9c83-120">Asocie las nuevas cuentas de recursos con los extremos de aplicación híbrida existentes.</span><span class="sxs-lookup"><span data-stu-id="f9c83-120">Associate the new Resource Accounts with the existing hybrid application endpoints.</span></span>

4. <span data-ttu-id="f9c83-121">Quite los números de teléfono definidos en los extremos de la aplicación híbrida local ejecutando el siguiente comando de PowerShell Skype Empresarial Server local:</span><span class="sxs-lookup"><span data-stu-id="f9c83-121">Remove phone numbers defined in the on-premises hybrid application endpoints by executing the following on-premises Skype for Business Server PowerShell command:</span></span>

   ```PowerShell
   Get-CsHybridApplicationEndpoint -Filter {LineURI -ne $null} | Set-CsHybridApplicationEndpoint -LineURI ""
   ```
5. <span data-ttu-id="f9c83-122">Dado que es posible que los números de teléfono de estas cuentas se administraron en Microsoft 365 en lugar de local, ejecute el siguiente comando en Skype Empresarial PowerShell en línea:</span><span class="sxs-lookup"><span data-stu-id="f9c83-122">Because it's possible that phone numbers for these accounts were managed in Microsoft 365 instead of on-premises, run the following command in Skype for Business Online PowerShell:</span></span>

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

6. <span data-ttu-id="f9c83-123">Asigne números de teléfono a las nuevas cuentas de recursos creadas en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="f9c83-123">Assign phone numbers to the new Resource Accounts created in Step 2.</span></span> <span data-ttu-id="f9c83-124">Para obtener más información acerca de cómo asignar un número de teléfono a una cuenta de recurso, vea el siguiente artículo: [Asignar un número de servicio](https://docs.microsoft.com/microsoftteams/manage-resource-accounts#assign-a-service-number).</span><span class="sxs-lookup"><span data-stu-id="f9c83-124">For more information about how to assign a phone number to a resource account, see the following article: [Assign a service number](https://docs.microsoft.com/microsoftteams/manage-resource-accounts#assign-a-service-number).</span></span>

7. <span data-ttu-id="f9c83-125">Elimine los extremos locales ejecutando el siguiente comando local Skype Empresarial Server PowerShell:</span><span class="sxs-lookup"><span data-stu-id="f9c83-125">Delete the on-premises endpoints by executing the following on-premises Skype for Business Server PowerShell command:</span></span>

   ```PowerShell
   Get-CsHybridApplicationEndpoint | Remove-CsHybridApplicationEndpoint
   ```
<span data-ttu-id="f9c83-126">Ya está listo para [quitar la implementación Skype Empresarial local.](decommission-remove-on-prem.md)</span><span class="sxs-lookup"><span data-stu-id="f9c83-126">You are now ready to [remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f9c83-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f9c83-127">See also</span></span>

- [<span data-ttu-id="f9c83-128">Retirar el entorno local de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="f9c83-128">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

- [<span data-ttu-id="f9c83-129">Mover todos los usuarios necesarios de local a online</span><span class="sxs-lookup"><span data-stu-id="f9c83-129">Move all required users from on-premises to online</span></span>](decommission-move-on-prem-users.md)

- [<span data-ttu-id="f9c83-130">Deshabilitar la configuración híbrida</span><span class="sxs-lookup"><span data-stu-id="f9c83-130">Disable your hybrid configuration</span></span>](cloud-consolidation-disabling-hybrid.md)

- [<span data-ttu-id="f9c83-131">Eliminar la implementación local de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="f9c83-131">Remove your on-premises Skype for Business deployment</span></span>](decommission-remove-on-prem.md)




