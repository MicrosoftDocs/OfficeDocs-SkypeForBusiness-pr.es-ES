---
title: Mover usuarios y puntos de conexión a la nube
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
description: Mueva usuarios y puntos de conexión antes de retirar un entorno local de Skype Empresarial.
ms.openlocfilehash: 130f276d07dd33be33d3c038c2ead20c7a887e6b
ms.sourcegitcommit: f223b5f3735f165d46bb611a52fcdfb0f4b88f66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/06/2021
ms.locfileid: "51593913"
---
# <a name="move-required-users-and-endpoints-before-decommissioning-your-on-premises-environment"></a><span data-ttu-id="f2c02-103">Mover los usuarios y puntos de conexión necesarios antes de retirar el entorno local</span><span class="sxs-lookup"><span data-stu-id="f2c02-103">Move required users and endpoints before decommissioning your on-premises environment</span></span>

<span data-ttu-id="f2c02-104">En este artículo se describe cómo mover usuarios y puntos de conexión de aplicaciones necesarios a la nube de Microsoft antes de retirar el entorno local de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="f2c02-104">This article describes how to move required users and application endpoints to the Microsoft cloud before decommissioning your on-premises Skype for Business environment.</span></span> <span data-ttu-id="f2c02-105">Este es el paso 1 de los siguientes pasos para retirar el entorno local:</span><span class="sxs-lookup"><span data-stu-id="f2c02-105">This is step 1 of the following steps to decommission your on-premises environment:</span></span>

- <span data-ttu-id="f2c02-106">**Paso 1. Mueva todos los usuarios y extremos de aplicación necesarios de local a en línea.**</span><span class="sxs-lookup"><span data-stu-id="f2c02-106">**Step 1. Move all required users and application endpoints from on-premises to online.**</span></span> <span data-ttu-id="f2c02-107">(En este artículo).</span><span class="sxs-lookup"><span data-stu-id="f2c02-107">(This article.)</span></span>

- <span data-ttu-id="f2c02-108">Paso 2.</span><span class="sxs-lookup"><span data-stu-id="f2c02-108">Step 2.</span></span> <span data-ttu-id="f2c02-109">[Deshabilite la configuración híbrida](cloud-consolidation-disabling-hybrid.md).</span><span class="sxs-lookup"><span data-stu-id="f2c02-109">[Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

- <span data-ttu-id="f2c02-110">Paso 3.</span><span class="sxs-lookup"><span data-stu-id="f2c02-110">Step 3.</span></span> <span data-ttu-id="f2c02-111">[Quite la implementación local de Skype Empresarial](decommission-remove-on-prem.md).</span><span class="sxs-lookup"><span data-stu-id="f2c02-111">[Remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>


## <a name="move-all-required-users-from-on-premises-to-the-cloud"></a><span data-ttu-id="f2c02-112">Mover todos los usuarios necesarios de local a la nube</span><span class="sxs-lookup"><span data-stu-id="f2c02-112">Move all required users from on-premises to the cloud</span></span>

<span data-ttu-id="f2c02-113">Los usuarios que seguirá usando después de completar la migración deben moverse primero de local a la nube.</span><span class="sxs-lookup"><span data-stu-id="f2c02-113">Any users that you will continue to use after completing the migration must first be moved from on-premises to the cloud.</span></span> <span data-ttu-id="f2c02-114">Los usuarios se mueven mediante las herramientas de administración locales.</span><span class="sxs-lookup"><span data-stu-id="f2c02-114">You move users by using the on-premises administration tools.</span></span> <span data-ttu-id="f2c02-115">Para obtener más información, consulte [Move users between on-premises and cloud](move-users-between-on-premises-and-cloud.md).</span><span class="sxs-lookup"><span data-stu-id="f2c02-115">For details, see [Move users between on-premises and cloud](move-users-between-on-premises-and-cloud.md).</span></span>

<span data-ttu-id="f2c02-116">Aunque es posible que los usuarios con cuentas locales de Skype Empresarial Server usen Teams, estos usuarios no tienen la funcionalidad completa de Teams.</span><span class="sxs-lookup"><span data-stu-id="f2c02-116">Although it is possible for users with on-premises Skype for Business Server accounts to use Teams, these users do not have the full functionality of Teams.</span></span> <span data-ttu-id="f2c02-117">Estos usuarios no pueden interoperar ni federar con ningún otro usuario que aún use Skype Empresarial (ya sea en línea o local).</span><span class="sxs-lookup"><span data-stu-id="f2c02-117">These users cannot interoperate or federate with any other user still using Skype for Business (whether online or on-premises).</span></span> <span data-ttu-id="f2c02-118">Estos usuarios tampoco pueden recibir llamadas RTC en su cliente de Teams.</span><span class="sxs-lookup"><span data-stu-id="f2c02-118">Nor can these users receive PSTN calls in their Teams client.</span></span> <span data-ttu-id="f2c02-119">Por lo tanto, debe mover estos usuarios a línea.</span><span class="sxs-lookup"><span data-stu-id="f2c02-119">Therefore, you must move these users to online.</span></span> <span data-ttu-id="f2c02-120">Este paso también garantiza que los contactos o reuniones creados en Skype Empresarial Server se migren a Teams.</span><span class="sxs-lookup"><span data-stu-id="f2c02-120">This step also ensures any contacts or meetings created in Skype for Business Server are migrated to Teams.</span></span>

<span data-ttu-id="f2c02-121">Para comprobar si hay algún usuario restante en la implementación local, ejecute el siguiente cmdlet en una ventana de PowerShell de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="f2c02-121">To check if there are any remaining users in your on-premises deployment, run the following cmdlet in a Skype for Business Server PowerShell window.</span></span>

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"}
```

<span data-ttu-id="f2c02-122">Si se devuelve algún usuario, revise el resultado para determinar si se debe mover alguna cuenta a la nube y, para cualquiera de estos usuarios, siga los pasos [aquí](move-users-between-on-premises-and-cloud.md).</span><span class="sxs-lookup"><span data-stu-id="f2c02-122">If any users are returned, review the output to determine if any accounts must be moved to the cloud, and, for any such users, follow the steps [here](move-users-between-on-premises-and-cloud.md).</span></span> <span data-ttu-id="f2c02-123">Para las cuentas de usuario que ya no son necesarias, ejecute el siguiente cmdlet de PowerShell de Skype Empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="f2c02-123">For user accounts that are no longer needed, run the following Skype for Business Server PowerShell cmdlet:</span></span>

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Disable-CsUser
```

> [!NOTE]
> <span data-ttu-id="f2c02-124">Al Disable-CsUser se quitarán todos los atributos de Skype Empresarial para todos los usuarios que cumplan los criterios de filtro.</span><span class="sxs-lookup"><span data-stu-id="f2c02-124">Running Disable-CsUser will remove all Skype for Business attributes for all users meeting the filter criteria.</span></span> <span data-ttu-id="f2c02-125">Antes de continuar, confirme que estas cuentas ya no son necesarias en el futuro.</span><span class="sxs-lookup"><span data-stu-id="f2c02-125">Before proceeding, confirm that these accounts are no longer needed going forward.</span></span>

## <a name="move-on-premises-hybrid-application-endpoints-to-microsoft-365"></a><span data-ttu-id="f2c02-126">Mover puntos de conexión de aplicaciones híbridas locales a Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f2c02-126">Move on-premises hybrid application endpoints to Microsoft 365</span></span>

1. <span data-ttu-id="f2c02-127">Recupere y exporte la configuración de extremo de aplicación híbrida local ejecutando el siguiente comando local de PowerShell de Skype Empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="f2c02-127">Retrieve and export on-premises hybrid application endpoint settings by executing the following on-premises Skype for Business Server PowerShell command:</span></span>

   ```PowerShell
   Get-CsHybridApplicationEndpoint|select Sipaddress, DisplayName, ApplicationID, LineUri |Export-Csv -Path "c:\backup\HybridEndpoints.csv"
   ```
2. <span data-ttu-id="f2c02-128">Crear y licenciar [nuevas cuentas de](https://docs.microsoft.com/microsoftteams/manage-resource-accounts) recursos en Microsoft 365 para reemplazar los puntos de conexión de aplicaciones híbridas locales existentes.</span><span class="sxs-lookup"><span data-stu-id="f2c02-128">Create and license new [Resource Accounts](https://docs.microsoft.com/microsoftteams/manage-resource-accounts) in Microsoft 365 to replace the existing on-premises hybrid application endpoints.</span></span>

3. <span data-ttu-id="f2c02-129">Asocie las nuevas cuentas de recursos con los extremos de aplicación híbrida existentes.</span><span class="sxs-lookup"><span data-stu-id="f2c02-129">Associate the new Resource Accounts with the existing hybrid application endpoints.</span></span>

4. <span data-ttu-id="f2c02-130">Quite los números de teléfono definidos en los extremos de la aplicación híbrida local ejecutando el siguiente comando local de PowerShell de Skype Empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="f2c02-130">Remove phone numbers defined in the on-premises hybrid application endpoints by executing the following on-premises Skype for Business Server PowerShell command:</span></span>

   ```PowerShell
   Get-CsHybridApplicationEndpoint -Filter {LineURI -ne $null} | Set-CsHybridApplicationEndpoint -LineURI ""
   ```
5. <span data-ttu-id="f2c02-131">Dado que es posible que los números de teléfono de estas cuentas se administraron en Microsoft 365 en lugar de local, ejecute el siguiente comando en PowerShell de Skype Empresarial Online:</span><span class="sxs-lookup"><span data-stu-id="f2c02-131">Because it's possible that phone numbers for these accounts were managed in Microsoft 365 instead of on-premises, run the following command in Skype for Business Online PowerShell:</span></span>

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

6. <span data-ttu-id="f2c02-132">Asigne números de teléfono a las nuevas cuentas de recursos creadas en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="f2c02-132">Assign phone numbers to the new Resource Accounts created in Step 2.</span></span> <span data-ttu-id="f2c02-133">Para obtener más información acerca de cómo asignar un número de teléfono a una cuenta de recurso, vea el siguiente artículo: [Asignar un número de servicio](https://docs.microsoft.com/microsoftteams/manage-resource-accounts#assign-a-service-number).</span><span class="sxs-lookup"><span data-stu-id="f2c02-133">For more information about how to assign a phone number to a resource account, see the following article: [Assign a service number](https://docs.microsoft.com/microsoftteams/manage-resource-accounts#assign-a-service-number).</span></span>

7. <span data-ttu-id="f2c02-134">Elimine los extremos locales ejecutando el siguiente comando local de PowerShell de Skype Empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="f2c02-134">Delete the on-premises endpoints by executing the following on-premises Skype for Business Server PowerShell command:</span></span>

   ```PowerShell
   Get-CsHybridApplicationEndpoint | Remove-CsHybridApplicationEndpoint
   ```
<span data-ttu-id="f2c02-135">Ya está listo para deshabilitar [la configuración híbrida](cloud-consolidation-disabling-hybrid.md).</span><span class="sxs-lookup"><span data-stu-id="f2c02-135">You are now ready to [disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f2c02-136">Ver también</span><span class="sxs-lookup"><span data-stu-id="f2c02-136">See also</span></span>

- [<span data-ttu-id="f2c02-137">Retirar el entorno local de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="f2c02-137">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

- [<span data-ttu-id="f2c02-138">Deshabilitar la configuración híbrida</span><span class="sxs-lookup"><span data-stu-id="f2c02-138">Disable your hybrid configuration</span></span>](cloud-consolidation-disabling-hybrid.md)

- [<span data-ttu-id="f2c02-139">Quitar la implementación local de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="f2c02-139">Remove your on-premises Skype for Business deployment</span></span>](decommission-remove-on-prem.md)




