---
title: Mover usuarios a la nube
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
description: Mueva usuarios antes de retirar un Skype Empresarial entorno local.
ms.openlocfilehash: 992f2dd479e0b8ca8a3f11f069e8ef049259ad9c
ms.sourcegitcommit: f39484688800a3d22f361e660d0eeba974a44fb1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420815"
---
# <a name="move-required-users-before-decommissioning-your-on-premises-environment"></a><span data-ttu-id="e266f-103">Mover usuarios necesarios antes de retirar el entorno local</span><span class="sxs-lookup"><span data-stu-id="e266f-103">Move required users before decommissioning your on-premises environment</span></span>

<span data-ttu-id="e266f-104">En este artículo se describe cómo mover los usuarios necesarios a la nube de Microsoft antes de retirar el entorno Skype Empresarial local.</span><span class="sxs-lookup"><span data-stu-id="e266f-104">This article describes how to move required users to the Microsoft cloud before decommissioning your on-premises Skype for Business environment.</span></span> <span data-ttu-id="e266f-105">Este es el paso 1 de los siguientes pasos para retirar el entorno local:</span><span class="sxs-lookup"><span data-stu-id="e266f-105">This is step 1 of the following steps to decommission your on-premises environment:</span></span>

- <span data-ttu-id="e266f-106">**Paso 1. Mueva todos los usuarios necesarios de local a online.**</span><span class="sxs-lookup"><span data-stu-id="e266f-106">**Step 1. Move all required users from on-premises to online.**</span></span> <span data-ttu-id="e266f-107">(Este artículo)</span><span class="sxs-lookup"><span data-stu-id="e266f-107">(This article)</span></span>

- <span data-ttu-id="e266f-108">Paso 2.</span><span class="sxs-lookup"><span data-stu-id="e266f-108">Step 2.</span></span> <span data-ttu-id="e266f-109">[Deshabilite la configuración híbrida](cloud-consolidation-disabling-hybrid.md).</span><span class="sxs-lookup"><span data-stu-id="e266f-109">[Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

- <span data-ttu-id="e266f-110">Paso 3.</span><span class="sxs-lookup"><span data-stu-id="e266f-110">Step 3.</span></span> <span data-ttu-id="e266f-111">[Migre los puntos de conexión de aplicaciones híbridas de local a en línea.](decommission-move-on-prem-endpoints.md)</span><span class="sxs-lookup"><span data-stu-id="e266f-111">[Migrate hybrid application endpoints from on-premises to online](decommission-move-on-prem-endpoints.md).</span></span> <span data-ttu-id="e266f-112">Tenga en cuenta que los puntos de conexión de aplicaciones híbridas existentes no se podrán detectar entre el momento en que realice el paso 2 anterior hasta que complete este paso.</span><span class="sxs-lookup"><span data-stu-id="e266f-112">Be aware that any existing hybrid application endpoints will not be discoverable between the time you perform Step 2 above until you complete this step.</span></span> <span data-ttu-id="e266f-113">Debe planear realizar los pasos 2 y 3 en la misma ventana de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="e266f-113">You should plan to do both steps 2 and 3 in the same maintenance window.</span></span>

- <span data-ttu-id="e266f-114">Paso 4.</span><span class="sxs-lookup"><span data-stu-id="e266f-114">Step 4.</span></span> <span data-ttu-id="e266f-115">[Quite la implementación Skype Empresarial local.](decommission-remove-on-prem.md)</span><span class="sxs-lookup"><span data-stu-id="e266f-115">[Remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>


## <a name="move-all-required-users-from-on-premises-to-the-cloud"></a><span data-ttu-id="e266f-116">Mover todos los usuarios necesarios de local a la nube</span><span class="sxs-lookup"><span data-stu-id="e266f-116">Move all required users from on-premises to the cloud</span></span>

<span data-ttu-id="e266f-117">Los usuarios que seguirá usando después de completar la migración deben moverse primero de local a la nube.</span><span class="sxs-lookup"><span data-stu-id="e266f-117">Any users that you will continue to use after completing the migration must first be moved from on-premises to the cloud.</span></span> <span data-ttu-id="e266f-118">Los usuarios se mueven mediante las herramientas de administración locales.</span><span class="sxs-lookup"><span data-stu-id="e266f-118">You move users by using the on-premises administration tools.</span></span> <span data-ttu-id="e266f-119">Para obtener más información, consulte [Move users between on-premises and cloud](move-users-between-on-premises-and-cloud.md).</span><span class="sxs-lookup"><span data-stu-id="e266f-119">For details, see [Move users between on-premises and cloud](move-users-between-on-premises-and-cloud.md).</span></span>

<span data-ttu-id="e266f-120">Aunque es posible que los usuarios con cuentas Skype Empresarial Server locales usen Teams, estos usuarios no tienen la funcionalidad completa de Teams.</span><span class="sxs-lookup"><span data-stu-id="e266f-120">Although it is possible for users with on-premises Skype for Business Server accounts to use Teams, these users do not have the full functionality of Teams.</span></span> <span data-ttu-id="e266f-121">Estos usuarios no pueden interoperar ni federar con ningún otro usuario que aún use Skype Empresarial (ya sea en línea o local).</span><span class="sxs-lookup"><span data-stu-id="e266f-121">These users cannot interoperate or federate with any other user still using Skype for Business (whether online or on-premises).</span></span> <span data-ttu-id="e266f-122">Estos usuarios tampoco pueden recibir llamadas RTC en su Teams cliente.</span><span class="sxs-lookup"><span data-stu-id="e266f-122">Nor can these users receive PSTN calls in their Teams client.</span></span> <span data-ttu-id="e266f-123">Por lo tanto, debe mover estos usuarios a línea.</span><span class="sxs-lookup"><span data-stu-id="e266f-123">Therefore, you must move these users to online.</span></span> <span data-ttu-id="e266f-124">Este paso también garantiza que los contactos o reuniones creados en Skype Empresarial Server se migren a Teams.</span><span class="sxs-lookup"><span data-stu-id="e266f-124">This step also ensures any contacts or meetings created in Skype for Business Server are migrated to Teams.</span></span>

<span data-ttu-id="e266f-125">Para comprobar si hay algún usuario restante en la implementación local, ejecute el siguiente cmdlet en una ventana Skype Empresarial Server PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e266f-125">To check if there are any remaining users in your on-premises deployment, run the following cmdlet in a Skype for Business Server PowerShell window.</span></span>

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"}
```

<span data-ttu-id="e266f-126">Si se devuelve algún usuario, revise el resultado para determinar si se debe mover alguna cuenta a la nube y, para cualquiera de estos usuarios, siga los pasos [aquí](move-users-between-on-premises-and-cloud.md).</span><span class="sxs-lookup"><span data-stu-id="e266f-126">If any users are returned, review the output to determine if any accounts must be moved to the cloud, and, for any such users, follow the steps [here](move-users-between-on-premises-and-cloud.md).</span></span> <span data-ttu-id="e266f-127">Para las cuentas de usuario que ya no son necesarias, ejecute el siguiente cmdlet Skype Empresarial Server PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e266f-127">For user accounts that are no longer needed, run the following Skype for Business Server PowerShell cmdlet:</span></span>

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Disable-CsUser
```

> [!NOTE]
> <span data-ttu-id="e266f-128">Al Disable-CsUser se quitarán todos los Skype Empresarial para todos los usuarios que cumplan los criterios de filtro.</span><span class="sxs-lookup"><span data-stu-id="e266f-128">Running Disable-CsUser will remove all Skype for Business attributes for all users meeting the filter criteria.</span></span> <span data-ttu-id="e266f-129">Antes de continuar, confirme que estas cuentas ya no son necesarias en el futuro.</span><span class="sxs-lookup"><span data-stu-id="e266f-129">Before proceeding, confirm that these accounts are no longer needed going forward.</span></span>


<span data-ttu-id="e266f-130">Ya está listo para deshabilitar [la configuración híbrida](cloud-consolidation-disabling-hybrid.md).</span><span class="sxs-lookup"><span data-stu-id="e266f-130">You are now ready to [disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e266f-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e266f-131">See also</span></span>

- [<span data-ttu-id="e266f-132">Retirar el entorno local de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="e266f-132">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

- [<span data-ttu-id="e266f-133">Deshabilitar la configuración híbrida</span><span class="sxs-lookup"><span data-stu-id="e266f-133">Disable your hybrid configuration</span></span>](cloud-consolidation-disabling-hybrid.md)

- [<span data-ttu-id="e266f-134">Mover puntos de conexión de aplicaciones híbridas de local a online</span><span class="sxs-lookup"><span data-stu-id="e266f-134">Move hybrid application endpoints from on-premises to online</span></span>](decommission-move-on-prem-endpoints.md)

- [<span data-ttu-id="e266f-135">Eliminar la implementación local de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="e266f-135">Remove your on-premises Skype for Business deployment</span></span>](decommission-remove-on-prem.md)




