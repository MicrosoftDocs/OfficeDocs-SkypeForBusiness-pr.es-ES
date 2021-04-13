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
description: Mover usuarios antes de retirar un entorno local de Skype Empresarial.
ms.openlocfilehash: f04ebeec51b739faa89f907de6c363f0ef70a78e
ms.sourcegitcommit: 71d90f0a0056f7604109f64e9722c80cf0eda47d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2021
ms.locfileid: "51656676"
---
# <a name="move-required-users-before-decommissioning-your-on-premises-environment"></a><span data-ttu-id="56153-103">Mover usuarios necesarios antes de retirar el entorno local</span><span class="sxs-lookup"><span data-stu-id="56153-103">Move required users before decommissioning your on-premises environment</span></span>

<span data-ttu-id="56153-104">En este artículo se describe cómo mover los usuarios necesarios a la nube de Microsoft antes de retirar el entorno local de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="56153-104">This article describes how to move required users to the Microsoft cloud before decommissioning your on-premises Skype for Business environment.</span></span> <span data-ttu-id="56153-105">Este es el paso 1 de los siguientes pasos para retirar el entorno local:</span><span class="sxs-lookup"><span data-stu-id="56153-105">This is step 1 of the following steps to decommission your on-premises environment:</span></span>

- <span data-ttu-id="56153-106">**Paso 1. Mueva todos los usuarios necesarios de local a online.**</span><span class="sxs-lookup"><span data-stu-id="56153-106">**Step 1. Move all required users from on-premises to online.**</span></span> <span data-ttu-id="56153-107">(Este artículo)</span><span class="sxs-lookup"><span data-stu-id="56153-107">(This article)</span></span>

- <span data-ttu-id="56153-108">Paso 2.</span><span class="sxs-lookup"><span data-stu-id="56153-108">Step 2.</span></span> <span data-ttu-id="56153-109">[Deshabilite la configuración híbrida](cloud-consolidation-disabling-hybrid.md).</span><span class="sxs-lookup"><span data-stu-id="56153-109">[Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

- <span data-ttu-id="56153-110">Paso 3.</span><span class="sxs-lookup"><span data-stu-id="56153-110">Step 3.</span></span> <span data-ttu-id="56153-111">[Mover extremos de aplicación híbrida de local a en línea.](decommission-move-on-prem-endpoints.md)</span><span class="sxs-lookup"><span data-stu-id="56153-111">[Move hybrid application endpoints from on-premises to online](decommission-move-on-prem-endpoints.md).</span></span>

- <span data-ttu-id="56153-112">Paso 4.</span><span class="sxs-lookup"><span data-stu-id="56153-112">Step 4.</span></span> <span data-ttu-id="56153-113">[Quite la implementación local de Skype Empresarial](decommission-remove-on-prem.md).</span><span class="sxs-lookup"><span data-stu-id="56153-113">[Remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>


## <a name="move-all-required-users-from-on-premises-to-the-cloud"></a><span data-ttu-id="56153-114">Mover todos los usuarios necesarios de local a la nube</span><span class="sxs-lookup"><span data-stu-id="56153-114">Move all required users from on-premises to the cloud</span></span>

<span data-ttu-id="56153-115">Los usuarios que seguirá usando después de completar la migración deben moverse primero de local a la nube.</span><span class="sxs-lookup"><span data-stu-id="56153-115">Any users that you will continue to use after completing the migration must first be moved from on-premises to the cloud.</span></span> <span data-ttu-id="56153-116">Los usuarios se mueven mediante las herramientas de administración locales.</span><span class="sxs-lookup"><span data-stu-id="56153-116">You move users by using the on-premises administration tools.</span></span> <span data-ttu-id="56153-117">Para obtener más información, consulte [Move users between on-premises and cloud](move-users-between-on-premises-and-cloud.md).</span><span class="sxs-lookup"><span data-stu-id="56153-117">For details, see [Move users between on-premises and cloud](move-users-between-on-premises-and-cloud.md).</span></span>

<span data-ttu-id="56153-118">Aunque es posible que los usuarios con cuentas locales de Skype Empresarial Server usen Teams, estos usuarios no tienen la funcionalidad completa de Teams.</span><span class="sxs-lookup"><span data-stu-id="56153-118">Although it is possible for users with on-premises Skype for Business Server accounts to use Teams, these users do not have the full functionality of Teams.</span></span> <span data-ttu-id="56153-119">Estos usuarios no pueden interoperar ni federar con ningún otro usuario que aún use Skype Empresarial (ya sea en línea o local).</span><span class="sxs-lookup"><span data-stu-id="56153-119">These users cannot interoperate or federate with any other user still using Skype for Business (whether online or on-premises).</span></span> <span data-ttu-id="56153-120">Estos usuarios tampoco pueden recibir llamadas RTC en su cliente de Teams.</span><span class="sxs-lookup"><span data-stu-id="56153-120">Nor can these users receive PSTN calls in their Teams client.</span></span> <span data-ttu-id="56153-121">Por lo tanto, debe mover estos usuarios a línea.</span><span class="sxs-lookup"><span data-stu-id="56153-121">Therefore, you must move these users to online.</span></span> <span data-ttu-id="56153-122">Este paso también garantiza que los contactos o reuniones creados en Skype Empresarial Server se migren a Teams.</span><span class="sxs-lookup"><span data-stu-id="56153-122">This step also ensures any contacts or meetings created in Skype for Business Server are migrated to Teams.</span></span>

<span data-ttu-id="56153-123">Para comprobar si hay algún usuario restante en la implementación local, ejecute el siguiente cmdlet en una ventana de PowerShell de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="56153-123">To check if there are any remaining users in your on-premises deployment, run the following cmdlet in a Skype for Business Server PowerShell window.</span></span>

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"}
```

<span data-ttu-id="56153-124">Si se devuelve algún usuario, revise el resultado para determinar si se debe mover alguna cuenta a la nube y, para cualquiera de estos usuarios, siga los pasos [aquí](move-users-between-on-premises-and-cloud.md).</span><span class="sxs-lookup"><span data-stu-id="56153-124">If any users are returned, review the output to determine if any accounts must be moved to the cloud, and, for any such users, follow the steps [here](move-users-between-on-premises-and-cloud.md).</span></span> <span data-ttu-id="56153-125">Para las cuentas de usuario que ya no son necesarias, ejecute el siguiente cmdlet de PowerShell de Skype Empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="56153-125">For user accounts that are no longer needed, run the following Skype for Business Server PowerShell cmdlet:</span></span>

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Disable-CsUser
```

> [!NOTE]
> <span data-ttu-id="56153-126">Al Disable-CsUser se quitarán todos los atributos de Skype Empresarial para todos los usuarios que cumplan los criterios de filtro.</span><span class="sxs-lookup"><span data-stu-id="56153-126">Running Disable-CsUser will remove all Skype for Business attributes for all users meeting the filter criteria.</span></span> <span data-ttu-id="56153-127">Antes de continuar, confirme que estas cuentas ya no son necesarias en el futuro.</span><span class="sxs-lookup"><span data-stu-id="56153-127">Before proceeding, confirm that these accounts are no longer needed going forward.</span></span>


<span data-ttu-id="56153-128">Ya está listo para deshabilitar [la configuración híbrida](cloud-consolidation-disabling-hybrid.md).</span><span class="sxs-lookup"><span data-stu-id="56153-128">You are now ready to [disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="56153-129">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="56153-129">See also</span></span>

- [<span data-ttu-id="56153-130">Retirar el entorno local de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="56153-130">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

- [<span data-ttu-id="56153-131">Deshabilitar la configuración híbrida</span><span class="sxs-lookup"><span data-stu-id="56153-131">Disable your hybrid configuration</span></span>](cloud-consolidation-disabling-hybrid.md)

- [<span data-ttu-id="56153-132">Mover puntos de conexión de aplicaciones híbridas de local a online</span><span class="sxs-lookup"><span data-stu-id="56153-132">Move hybrid application endpoints from on-premises to online</span></span>](decommission-move-on-prem-endpoints.md)

- [<span data-ttu-id="56153-133">Eliminar la implementación local de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="56153-133">Remove your on-premises Skype for Business deployment</span></span>](decommission-remove-on-prem.md)




