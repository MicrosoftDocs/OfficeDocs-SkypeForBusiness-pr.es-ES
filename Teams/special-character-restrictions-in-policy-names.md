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
ms.openlocfilehash: 7d835669f0acc7cd2a2e42acb1aa9fa9d2fdf765
ms.sourcegitcommit: 26d93a15c9d4704c08f3fabc5635839ce2456b2d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2018
ms.locfileid: "20205081"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a><span data-ttu-id="41d19-103">¿Cuáles son las restricciones de caracteres especiales en las directivas de los equipos?</span><span class="sxs-lookup"><span data-stu-id="41d19-103">What are the special character restrictions in Teams policies?</span></span>

<span data-ttu-id="41d19-104">**Aunque pueden usar caracteres especiales para la creación de directivas de los equipos con PowerShell, limitará en la administración de estas directivas.  Por lo tanto, se recomienda encarecidamente nombres de directiva no incluir caracteres especiales.**</span><span class="sxs-lookup"><span data-stu-id="41d19-104">**Although special characters can be used for creating Teams policies with PowerShell, you will be limited in managing these policies .  As such, we strongly recommend policy names do not include special characters.**</span></span>

<span data-ttu-id="41d19-105">Nombres de directiva que se crean con PowerShell para las reuniones y conversaciones en los equipos pueden tener caracteres especiales, como @, #, $.</span><span class="sxs-lookup"><span data-stu-id="41d19-105">Policy names that you create using PowerShell for meetings and chat in Teams can have special characters such as @,#,$.</span></span> <span data-ttu-id="41d19-106">Sin embargo, si desea editar la directiva en el Microsoft Teams y Skype para el centro de administración de negocio, no podrá a.</span><span class="sxs-lookup"><span data-stu-id="41d19-106">However, if you are wanting to edit the policy in the Microsoft Teams and Skype for Business admin center, you won't be able to.</span></span> <span data-ttu-id="41d19-107">Debe usar Windows PowerShell y el cmdlet de directiva correcta para realizar cambios.</span><span class="sxs-lookup"><span data-stu-id="41d19-107">You must use Windows PowerShell and the correct policy cmdlet to make changes.</span></span>

<span data-ttu-id="41d19-108">Si tiene un objeto de directiva con caracteres especiales y que desea quitar los caracteres especiales con el fin de administrar mejor la directiva en el Microsoft Teams y Skype para el centro de administración de negocio, debe usar el siguiente procedimiento.</span><span class="sxs-lookup"><span data-stu-id="41d19-108">If you have a policy object with special characters and you want to remove the special characters in order to better manage the policy in the Microsoft Teams and Skype for Business admin center, you will need to use the below procedure.</span></span> 

<span data-ttu-id="41d19-109">Nota: En el procedimiento articulado aquí se usa en el ejemplo de una directiva de mensajería.</span><span class="sxs-lookup"><span data-stu-id="41d19-109">Note: The procedure articulated here uses the example of a Messaging policy.</span></span>  <span data-ttu-id="41d19-110">Por subsituting los cmdlets relevantes, se usaría el mismo proceso para cualquier otro tipo de directiva (por ejemplo, las de reuniones).</span><span class="sxs-lookup"><span data-stu-id="41d19-110">The same process would be used for another policy type (Meetings for example) by subsituting the relevant cmdlets.</span></span> 

<span data-ttu-id="41d19-111">1.) llamar a Get-CSMessagingPolicy-identidad < antiguoNombreDeDirectiva > y captura el resultado de la directiva.</span><span class="sxs-lookup"><span data-stu-id="41d19-111">1.) Call Get-CSMessagingPolicy -identity <old_policy_name> and capture the output of the policy.</span></span>
<span data-ttu-id="41d19-112">2.) llame a Set-CSMessagingPolicy-identidad < nuevoNombreDeDirectiva > para crear una nueva directiva con la misma configuración que la directiva original pero sin caracteres especiales en el nombre.</span><span class="sxs-lookup"><span data-stu-id="41d19-112">2.) Call Set-CSMessagingPolicy -identity <new_policy_name> to create a new policy with the same configuration as the original policy but without any special characters in the name.</span></span>
<span data-ttu-id="41d19-113">3.) llamar a Delete-CSMessagingPolicy-identidad < antiguoNombreDeDirectiva > para eliminar la directiva.</span><span class="sxs-lookup"><span data-stu-id="41d19-113">3.) Call Delete-CSMessagingPolicy -identity <old_policy_name> to delete the policy.</span></span>  <span data-ttu-id="41d19-114">Si este comando se ejecuta correctamente, se hayan acabado y puede empezar a asignar a los usuarios a la nueva directiva de uso de PowerShell o el Microsoft Teams y Skype para el centro de administración de negocio.</span><span class="sxs-lookup"><span data-stu-id="41d19-114">If this command succeeds, you're done and can begin to assign users to the new policy using either PowerShell or the Microsoft Teams and Skype for Business admin center.</span></span>
<span data-ttu-id="41d19-115">4.) si el comando anterior no se realiza correctamente, es debido a que se ha asignado la directiva anterior a un usuario.</span><span class="sxs-lookup"><span data-stu-id="41d19-115">4.) If the above command does not succeed, it is because the old policy has been assigned to a user.</span></span>  <span data-ttu-id="41d19-116">Ejecutar cancelar la asignación de cmdlet para quitar la asignación de la directiva de usuario, asignar la nueva directiva y, a continuación, vuelva a ejecutar dwlete.</span><span class="sxs-lookup"><span data-stu-id="41d19-116">Run unassign cmdlet to unassign the policy from user, assign new policy, then run dwlete again.</span></span>


