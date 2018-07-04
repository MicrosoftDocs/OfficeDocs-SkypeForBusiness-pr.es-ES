---
title: ¿Cuáles son las restricciones de caracteres especiales en las directivas de los equipos?
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords:
- me.teamsadmincenter.policies.naming.error
description: Vea ¿qué problemas hay con caracteres especiales en los nombres de las directivas y qué puede hacer para solucionarlo.
ms.openlocfilehash: 43e2daba187bb3a381fe617e088518129d918d09
ms.sourcegitcommit: 2b15226723c299fe94f1a012aa21222173fe3af8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/03/2018
ms.locfileid: "20192167"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a><span data-ttu-id="6557a-103">¿Cuáles son las restricciones de caracteres especiales en las directivas de los equipos?</span><span class="sxs-lookup"><span data-stu-id="6557a-103">What are the special character restrictions in Teams policies?</span></span>

<span data-ttu-id="6557a-104">**Aunque se pueden usar caracteres especiales en los nombres de las directivas que creó en los equipos, se recomienda encarecidamente que no lo hace.**</span><span class="sxs-lookup"><span data-stu-id="6557a-104">**Although you can use special characters in the names of policies you created in Teams, we strongly recommend that you don't.**</span></span>

<span data-ttu-id="6557a-105">Nombres de directiva que se crean para las reuniones, chat y prescense y otras cosas en los equipos pueden tener caracteres especiales, como @, #, $.</span><span class="sxs-lookup"><span data-stu-id="6557a-105">Policy names that you create for meetings, chat and prescense, and other things in Teams can have special characters such as @,#,$.</span></span> <span data-ttu-id="6557a-106">Sin embargo, si desea realizar cambios en el nombre en el Microsoft Teams y Skype para el centro de administración de negocio, no podrá a.</span><span class="sxs-lookup"><span data-stu-id="6557a-106">However, if you are wanting to make changes to the name in the Microsoft Teams and Skype for Business admin center, you won't be able to.</span></span> <span data-ttu-id="6557a-107">Debe usar Windows PowerShell y el cmdlet de directiva correcta para realizar cambios.</span><span class="sxs-lookup"><span data-stu-id="6557a-107">You must use Windows PowerShell and the correct policy cmdlet to make changes.</span></span>

<span data-ttu-id="6557a-108">Por ejemplo, si tiene una directiva de reunión con caracteres especiales y desea cambiar el nombre o quite los caracteres especiales del nombre, necesitará usar el cmdlet Set-CsMeetingPolicy.</span><span class="sxs-lookup"><span data-stu-id="6557a-108">For example, if you have a meeting policy with special characters and you want to change the name or remove the special characters from the name, you will need to use the Set-CsMeetingPolicy cmdlet.</span></span> 

<span data-ttu-id="6557a-109">Aquí tiene una lista de los cmdlets de directiva que necesita hacer esto:</span><span class="sxs-lookup"><span data-stu-id="6557a-109">Here is a list of the policy cmdlets that you may need to do this:</span></span>
1. <span data-ttu-id="6557a-110">Set-CsMeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="6557a-110">Set-CsMeetingPolicy</span></span>
2. <span data-ttu-id="6557a-111">Set-CsAppPolicy</span><span class="sxs-lookup"><span data-stu-id="6557a-111">Set-CsAppPolicy</span></span>
3. <span data-ttu-id="6557a-112">Set-\*</span><span class="sxs-lookup"><span data-stu-id="6557a-112">Set-\*</span></span>


