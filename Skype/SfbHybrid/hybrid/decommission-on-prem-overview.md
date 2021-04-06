---
title: Retirar el entorno local de Skype Empresarial
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
description: Instrucciones sobre cómo retirar el entorno local de Skype Empresarial.
ms.openlocfilehash: 7f5109661fc7d29d83172489dd987b96cb7e87fd
ms.sourcegitcommit: f223b5f3735f165d46bb611a52fcdfb0f4b88f66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/06/2021
ms.locfileid: "51593903"
---
# <a name="decommission-your-on-premises-skype-for-business-environment"></a><span data-ttu-id="f21d7-103">Retirar el entorno local de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="f21d7-103">Decommission your on-premises Skype for Business environment</span></span>

<span data-ttu-id="f21d7-104">Si su organización usa Teams o Skype Empresarial Online con una implementación local de Skype Empresarial Server, puede migrar estos entornos completamente a la nube y, a continuación, retirar la implementación local de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="f21d7-104">If your organization uses Teams or Skype for Business Online with an on-premises deployment of Skype for Business Server, you can migrate these environments fully to the cloud, and then retire your on-premises deployment of Skype for Business Server.</span></span> 

> [!NOTE]
> <span data-ttu-id="f21d7-105">Antes de retirar el entorno local, debe configurar la conectividad híbrida [entre](configure-hybrid-connectivity.md) la implementación local y Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f21d7-105">Before decommissioning your on-premises environment, you must [configure hybrid connectivity](configure-hybrid-connectivity.md) between your on-premises deployment and Microsoft 365.</span></span> <span data-ttu-id="f21d7-106">Después de configurar la conectividad híbrida, puede migrar usuarios a la nube, mientras migra sus reuniones desde locales y migra cualquier contacto de Skype Empresarial Server a Teams.</span><span class="sxs-lookup"><span data-stu-id="f21d7-106">After configuring hybrid connectivity, you can migrate users to the cloud, while migrating their meetings from on-premises, and migrating any contacts from Skype for Business Server to Teams.</span></span> <span data-ttu-id="f21d7-107">Configurar la conectividad híbrida es un paso necesario para migrar usuarios de local a la nube y para garantizar la funcionalidad completa de Teams.</span><span class="sxs-lookup"><span data-stu-id="f21d7-107">Configuring hybrid connectivity is a required step to migrate users from on-premises to the cloud and to ensure full Teams functionality.</span></span>

<span data-ttu-id="f21d7-108">Para completar el traslado de local a la nube y retirar el entorno local de Skype Empresarial Server, debe completar los siguientes pasos en el siguiente orden:</span><span class="sxs-lookup"><span data-stu-id="f21d7-108">To complete your move from on-premises to the cloud and decommission your on-premises Skype for Business Server environment, you must complete the following steps in the following order:</span></span>

- <span data-ttu-id="f21d7-109">**Paso 1.**</span><span class="sxs-lookup"><span data-stu-id="f21d7-109">**Step 1.**</span></span> <span data-ttu-id="f21d7-110">[Mueva todos los usuarios y extremos de aplicación necesarios de local a en línea.](decommission-move-on-prem-users.md)</span><span class="sxs-lookup"><span data-stu-id="f21d7-110">[Move all required users and application endpoints from on-premises to online](decommission-move-on-prem-users.md).</span></span>

- <span data-ttu-id="f21d7-111">**Paso 2.**</span><span class="sxs-lookup"><span data-stu-id="f21d7-111">**Step 2.**</span></span> <span data-ttu-id="f21d7-112">[Deshabilite la configuración híbrida](cloud-consolidation-disabling-hybrid.md).</span><span class="sxs-lookup"><span data-stu-id="f21d7-112">[Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

- <span data-ttu-id="f21d7-113">**Paso 3.**</span><span class="sxs-lookup"><span data-stu-id="f21d7-113">**Step 3.**</span></span> <span data-ttu-id="f21d7-114">[Quite la implementación local de Skype Empresarial](decommission-remove-on-prem.md).</span><span class="sxs-lookup"><span data-stu-id="f21d7-114">[Remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>

