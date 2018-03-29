---
title: Habilitar la respuesta de llamadas grupales para los usuarios y asignar un número de grupo en Skype Empresarial 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
description: Habilitar a usuarios de grupo llamar recogida en Skype para Telefonía IP empresarial de Business Server y asignar a un número de grupo.
ms.openlocfilehash: aaacf080f9e7f7ae7f9bad3f8b13201972d7a72f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="enable-group-call-pickup-for-users-and-assign-a-group-number-in-skype-for-business-2015"></a><span data-ttu-id="67d12-103">Habilitar la respuesta de llamadas grupales para los usuarios y asignar un número de grupo en Skype Empresarial 2015</span><span class="sxs-lookup"><span data-stu-id="67d12-103">Enable Group Call Pickup for users and assign a group number in Skype for Business 2015</span></span>
 
<span data-ttu-id="67d12-104">Habilitar a usuarios de grupo llamar recogida en Skype para Telefonía IP empresarial de Business Server y asignar a un número de grupo.</span><span class="sxs-lookup"><span data-stu-id="67d12-104">Enable users for Group Call Pickup in Skype for Business Server Enterprise Voice, and assign a group number.</span></span>
  
<span data-ttu-id="67d12-105">Después de agregar números de grupo recogida de llamada a la tabla de llamada park órbita, utilice la herramienta SEFAUtil para asignar a los números de grupo a los usuarios y habilitar recogida de grupo llame para ellos.</span><span class="sxs-lookup"><span data-stu-id="67d12-105">After you add call pickup group numbers to the call park orbit table, you use the SEFAUtil tool to assign the group numbers to users and enable Group Call Pickup for them.</span></span>
  
> [!NOTE]
> <span data-ttu-id="67d12-106">En una implementación híbrida, no asigne a un grupo de recogida de llamar al grupo a los usuarios que están alojados en línea.</span><span class="sxs-lookup"><span data-stu-id="67d12-106">In a hybrid deployment, do not assign a Group Call Pickup group to users who are homed online.</span></span> <span data-ttu-id="67d12-107">Los usuarios que están alojados en línea no pueden participar en la recogida de llamar al grupo.</span><span class="sxs-lookup"><span data-stu-id="67d12-107">Users who are homed online cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="67d12-108">Es decir, no se puede contestar a sus llamadas por otros usuarios y no puede responder a las llamadas a otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="67d12-108">That is, their calls cannot be answered by other users, and they cannot answer calls to other users.</span></span> 
  
### <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a><span data-ttu-id="67d12-109">Para asignar a un número de grupo y habilitar recogida de grupo llame para un usuario</span><span class="sxs-lookup"><span data-stu-id="67d12-109">To assign a group number and enable Group Call Pickup for a user</span></span>

1. <span data-ttu-id="67d12-110">Inicie sesión como administrador en el equipo en el que haya instalado la herramienta SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="67d12-110">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>
    
2. <span data-ttu-id="67d12-111">En la línea de comandos, ejecute:</span><span class="sxs-lookup"><span data-stu-id="67d12-111">At the command line, run:</span></span>
    
   ```
   SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
   ```

    <span data-ttu-id="67d12-112">Por ejemplo, para asignar el número de grupo 199 a un usuario:</span><span class="sxs-lookup"><span data-stu-id="67d12-112">For example, to assign group number 199 to a user:</span></span>
    
   ```
   SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199 
   ```

## <a name="see-also"></a><span data-ttu-id="67d12-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="67d12-113">See also</span></span>

#### 

[<span data-ttu-id="67d12-114">Recogida de grupo deshabilitar para usuarios</span><span class="sxs-lookup"><span data-stu-id="67d12-114">Disable Group Pickup for Users</span></span>](http://technet.microsoft.com/library/91b06f9e-2840-45a2-bbb3-6a29179b9a9f.aspx)

