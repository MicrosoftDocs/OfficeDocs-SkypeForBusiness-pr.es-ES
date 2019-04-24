---
title: Habilitar la recogida de llamadas de grupo para los usuarios y asignar a un número de grupo en Skype para la empresa
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
description: Permitir a los usuarios para su grupo de llamada recogida en Skype para Business Server Enterprise Voice y asignar a un número de grupo.
ms.openlocfilehash: f2d02aa4993e103b786894f642dd88ca93dcf354
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212498"
---
# <a name="enable-group-call-pickup-for-users-and-assign-a-group-number-in-skype-for-business"></a><span data-ttu-id="b5ec1-103">Habilitar la recogida de llamadas de grupo para los usuarios y asignar a un número de grupo en Skype para la empresa</span><span class="sxs-lookup"><span data-stu-id="b5ec1-103">Enable Group Call Pickup for users and assign a group number in Skype for Business</span></span>

<span data-ttu-id="b5ec1-104">Permitir a los usuarios para su grupo de llamada recogida en Skype para Business Server Enterprise Voice y asignar a un número de grupo.</span><span class="sxs-lookup"><span data-stu-id="b5ec1-104">Enable users for Group Call Pickup in Skype for Business Server Enterprise Voice, and assign a group number.</span></span>

<span data-ttu-id="b5ec1-105">Después de agregar números de llamada pickup grupo a la tabla de órbitas de estacionamiento de llamada, use la herramienta SEFAUtil para asignar a los números de grupo a los usuarios y habilitar recogida de llamadas de grupo para ellos.</span><span class="sxs-lookup"><span data-stu-id="b5ec1-105">After you add call pickup group numbers to the call park orbit table, you use the SEFAUtil tool to assign the group numbers to users and enable Group Call Pickup for them.</span></span>

> [!NOTE]
> <span data-ttu-id="b5ec1-106">En una implementación híbrida, no asigne a un grupo de recogida de llamadas de grupo a los usuarios que están hospedados en línea.</span><span class="sxs-lookup"><span data-stu-id="b5ec1-106">In a hybrid deployment, do not assign a Group Call Pickup group to users who are homed online.</span></span> <span data-ttu-id="b5ec1-107">Los usuarios que están hospedados en línea no pueden participar en recogida de llamadas de grupo.</span><span class="sxs-lookup"><span data-stu-id="b5ec1-107">Users who are homed online cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="b5ec1-108">Es decir, sus llamadas no pueden ser atendidas por otros usuarios y no pueden atender las llamadas a otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="b5ec1-108">That is, their calls cannot be answered by other users, and they cannot answer calls to other users.</span></span>

### <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a><span data-ttu-id="b5ec1-109">Para asignar a un número de grupo y habilitar recogida de llamadas de grupo para un usuario</span><span class="sxs-lookup"><span data-stu-id="b5ec1-109">To assign a group number and enable Group Call Pickup for a user</span></span>

1. <span data-ttu-id="b5ec1-110">Inicie sesión como administrador en el equipo en el que haya instalado la herramienta SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="b5ec1-110">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2. <span data-ttu-id="b5ec1-111">En la línea de comandos, ejecute:</span><span class="sxs-lookup"><span data-stu-id="b5ec1-111">At the command line, run:</span></span>

   ```
   SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
   ```

    <span data-ttu-id="b5ec1-112">Por ejemplo, para asignar el número de grupo 199 a un usuario:</span><span class="sxs-lookup"><span data-stu-id="b5ec1-112">For example, to assign group number 199 to a user:</span></span>

   ```
   SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199
   ```

## <a name="see-also"></a><span data-ttu-id="b5ec1-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="b5ec1-113">See also</span></span>

[<span data-ttu-id="b5ec1-114">Disable Group Pickup for Users</span><span class="sxs-lookup"><span data-stu-id="b5ec1-114">Disable Group Pickup for Users</span></span>](https://technet.microsoft.com/library/91b06f9e-2840-45a2-bbb3-6a29179b9a9f.aspx)

