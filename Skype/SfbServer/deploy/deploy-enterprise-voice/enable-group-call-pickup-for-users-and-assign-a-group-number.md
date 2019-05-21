---
title: Habilitar la recogida de llamadas grupales para los usuarios y asignar un número de grupo en Skype empresarial
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
description: Habilite usuarios para la recogida de llamadas grupales en Skype empresarial Server Enterprise Voice y asigne un número de grupo.
ms.openlocfilehash: 14f17d3e217fa9ea44cc81db4d8fa6bf12644894
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34291584"
---
# <a name="enable-group-call-pickup-for-users-and-assign-a-group-number-in-skype-for-business"></a><span data-ttu-id="7a071-103">Habilitar la recogida de llamadas grupales para los usuarios y asignar un número de grupo en Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="7a071-103">Enable Group Call Pickup for users and assign a group number in Skype for Business</span></span>

<span data-ttu-id="7a071-104">Habilite usuarios para la recogida de llamadas grupales en Skype empresarial Server Enterprise Voice y asigne un número de grupo.</span><span class="sxs-lookup"><span data-stu-id="7a071-104">Enable users for Group Call Pickup in Skype for Business Server Enterprise Voice, and assign a group number.</span></span>

<span data-ttu-id="7a071-105">Después de agregar los números del grupo de recogida de llamadas a la tabla de llamadas en órbita, use la herramienta SEFAUtil para asignar los números de grupo a los usuarios y habilitar la recogida de llamadas grupales.</span><span class="sxs-lookup"><span data-stu-id="7a071-105">After you add call pickup group numbers to the call park orbit table, you use the SEFAUtil tool to assign the group numbers to users and enable Group Call Pickup for them.</span></span>

> [!NOTE]
> <span data-ttu-id="7a071-106">En una implementación híbrida, no asigne un grupo de recogida de llamadas grupal a los usuarios alojados en línea.</span><span class="sxs-lookup"><span data-stu-id="7a071-106">In a hybrid deployment, do not assign a Group Call Pickup group to users who are homed online.</span></span> <span data-ttu-id="7a071-107">Los usuarios alojados en Internet no pueden participar en la recogida de llamadas grupales.</span><span class="sxs-lookup"><span data-stu-id="7a071-107">Users who are homed online cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="7a071-108">Es decir, otros usuarios no pueden contestar las llamadas y no pueden responder llamadas a otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="7a071-108">That is, their calls cannot be answered by other users, and they cannot answer calls to other users.</span></span>

### <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a><span data-ttu-id="7a071-109">Para asignar un número de grupo y habilitar la recogida de llamadas grupales para un usuario</span><span class="sxs-lookup"><span data-stu-id="7a071-109">To assign a group number and enable Group Call Pickup for a user</span></span>

1. <span data-ttu-id="7a071-110">Inicie sesión como administrador en el equipo en el que haya instalado la herramienta SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="7a071-110">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2. <span data-ttu-id="7a071-111">En la línea de comandos, ejecute:</span><span class="sxs-lookup"><span data-stu-id="7a071-111">At the command line, run:</span></span>

   ```
   SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
   ```

    <span data-ttu-id="7a071-112">Por ejemplo, para asignar el número de grupo 199 a un usuario:</span><span class="sxs-lookup"><span data-stu-id="7a071-112">For example, to assign group number 199 to a user:</span></span>

   ```
   SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199
   ```

## <a name="see-also"></a><span data-ttu-id="7a071-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="7a071-113">See also</span></span>

[<span data-ttu-id="7a071-114">Disable Group Pickup for Users</span><span class="sxs-lookup"><span data-stu-id="7a071-114">Disable Group Pickup for Users</span></span>](https://technet.microsoft.com/library/91b06f9e-2840-45a2-bbb3-6a29179b9a9f.aspx)

