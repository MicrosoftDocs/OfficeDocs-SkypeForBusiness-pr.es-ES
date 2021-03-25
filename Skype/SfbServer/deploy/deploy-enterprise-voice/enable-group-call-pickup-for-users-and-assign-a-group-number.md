---
title: Habilitar la recogida de llamadas de grupo para los usuarios y asignar un número de grupo en Skype Empresarial
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
description: Habilite a los usuarios para la recogida de llamadas en grupo en Skype Empresarial Server Telefonía IP empresarial y asigne un número de grupo.
ms.openlocfilehash: 5469e9634e16b855993518092114184a2dca7359
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111836"
---
# <a name="enable-group-call-pickup-for-users-and-assign-a-group-number-in-skype-for-business"></a><span data-ttu-id="958af-103">Habilitar la recogida de llamadas de grupo para los usuarios y asignar un número de grupo en Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="958af-103">Enable Group Call Pickup for users and assign a group number in Skype for Business</span></span>

<span data-ttu-id="958af-104">Habilite a los usuarios para la recogida de llamadas en grupo en Skype Empresarial Server Telefonía IP empresarial y asigne un número de grupo.</span><span class="sxs-lookup"><span data-stu-id="958af-104">Enable users for Group Call Pickup in Skype for Business Server Enterprise Voice, and assign a group number.</span></span>

<span data-ttu-id="958af-105">Después de agregar números de grupo de recogida de llamadas a la tabla de órbitas de estacionamiento de llamadas, use la herramienta SEFAUtil para asignar los números de grupo a los usuarios y habilitar la recogida de llamadas de grupo para ellos.</span><span class="sxs-lookup"><span data-stu-id="958af-105">After you add call pickup group numbers to the call park orbit table, you use the SEFAUtil tool to assign the group numbers to users and enable Group Call Pickup for them.</span></span>

> [!NOTE]
> <span data-ttu-id="958af-106">En una implementación híbrida, no asigne un grupo de recogida de llamadas de grupo a los usuarios que estén en línea.</span><span class="sxs-lookup"><span data-stu-id="958af-106">In a hybrid deployment, do not assign a Group Call Pickup group to users who are homed online.</span></span> <span data-ttu-id="958af-107">Los usuarios que están en línea no pueden participar en la recogida de llamadas en grupo.</span><span class="sxs-lookup"><span data-stu-id="958af-107">Users who are homed online cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="958af-108">Es decir, otros usuarios no pueden responder sus llamadas y no pueden responder llamadas a otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="958af-108">That is, their calls cannot be answered by other users, and they cannot answer calls to other users.</span></span>

### <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a><span data-ttu-id="958af-109">Para asignar un número de grupo y habilitar la recogida de llamadas de grupo para un usuario</span><span class="sxs-lookup"><span data-stu-id="958af-109">To assign a group number and enable Group Call Pickup for a user</span></span>

1. <span data-ttu-id="958af-110">Inicie sesión en el equipo donde instaló la herramienta SEFAUtil con derechos de administrador.</span><span class="sxs-lookup"><span data-stu-id="958af-110">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2. <span data-ttu-id="958af-111">En la línea de comandos, ejecute:</span><span class="sxs-lookup"><span data-stu-id="958af-111">At the command line, run:</span></span>

   ```console
   SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
   ```

    <span data-ttu-id="958af-112">Por ejemplo, para asignar el número de grupo 199 a un usuario:</span><span class="sxs-lookup"><span data-stu-id="958af-112">For example, to assign group number 199 to a user:</span></span>

   ```console
   SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199
   ```

## <a name="see-also"></a><span data-ttu-id="958af-113">Ver también</span><span class="sxs-lookup"><span data-stu-id="958af-113">See also</span></span>

[<span data-ttu-id="958af-114">Deshabilitar la recogida de grupos para usuarios</span><span class="sxs-lookup"><span data-stu-id="958af-114">Disable Group Pickup for Users</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-disable-group-call-pickup-for-users)