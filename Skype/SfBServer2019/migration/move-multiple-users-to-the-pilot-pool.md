---
title: Mover varios usuarios al grupo piloto
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Puede mover varios usuarios del grupo heredado al grupo piloto de Skype Empresarial Server 2019 mediante el Panel de control de Skype Empresarial Server 2019 o el Shell de administración de Skype Empresarial Server 2019.
ms.openlocfilehash: d1b003c5630a0917fbecbd9b04196675657fef83
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753432"
---
# <a name="move-multiple-users-to-the-pilot-pool"></a><span data-ttu-id="0b72e-103">Mover varios usuarios al grupo piloto</span><span class="sxs-lookup"><span data-stu-id="0b72e-103">Move multiple users to the pilot pool</span></span>

<span data-ttu-id="0b72e-104">Puede mover varios usuarios del grupo heredado al grupo piloto de Skype Empresarial Server 2019 mediante el Panel de control de Skype Empresarial Server 2019 o el Shell de administración de Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="0b72e-104">You can move multiple users from your legacy pool to your Skype for Business Server 2019 pilot pool using Skype for Business Server 2019 Control Panel or Skype for Business Server 2019 Management Shell.</span></span>

 <span data-ttu-id="0b72e-105">**En este artículo**</span><span class="sxs-lookup"><span data-stu-id="0b72e-105">**In this article**</span></span>
  
[<span data-ttu-id="0b72e-106">Para mover varios usuarios mediante el Panel de control de Skype Empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="0b72e-106">To move multiple users by using the Skype for Business Server 2019 Control Panel</span></span>](#sectionSection0)
  
[<span data-ttu-id="0b72e-107">Para mover varios usuarios mediante el Shell de administración de Skype Empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="0b72e-107">To move multiple users by using the Skype for Business Server 2019 Management Shell</span></span>](#sectionSection1)
  
[<span data-ttu-id="0b72e-108">Para mover todos los usuarios al mismo tiempo mediante el Shell de administración de Skype Empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="0b72e-108">To move all users at the same time by using the Skype for Business Server 2019 Management Shell</span></span>](#sectionSection2)
  
  
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-control-panel"></a><span data-ttu-id="0b72e-109">Para mover varios usuarios mediante el Panel de control de Skype Empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="0b72e-109">To move multiple users by using the Skype for Business Server 2019 Control Panel</span></span>
<span data-ttu-id="0b72e-110"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="0b72e-110"><a name="sectionSection0"> </a></span></span>

1. <span data-ttu-id="0b72e-111">Abra el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="0b72e-111">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="0b72e-112">Haga clic en **Usuarios**, **Buscar** y, a continuación, en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="0b72e-112">Click **Users**, click **Search**, and then click **Find**.</span></span>
    
3. <span data-ttu-id="0b72e-113">Seleccione dos usuarios que desee mover al grupo de Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="0b72e-113">Select two users that you want to move to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="0b72e-114">En este ejemplo, moveremos los usuarios Chen Yang y Claus Hansen.</span><span class="sxs-lookup"><span data-stu-id="0b72e-114">In this example, we will move users Chen Yang and Claus Hansen.</span></span>
    
     ![Mover usuarios a un grupo de registros específico](../media/Migration_LyncServer_CPanel_fromLyncServer2010_MoveMultipleUsersList.JPG)
  
4. <span data-ttu-id="0b72e-116">En el menú **Acción** seleccione **Mover usuarios seleccionados a grupo**.</span><span class="sxs-lookup"><span data-stu-id="0b72e-116">From the **Action** menu, select **Move selected users to pool**.</span></span>
    
5. <span data-ttu-id="0b72e-117">En la lista desplegable, seleccione el grupo de Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="0b72e-117">From the drop-down list, select the Skype for Business Server 2019 pool.</span></span>
    
6. <span data-ttu-id="0b72e-118">Haga clic en **Acción** y, a continuación, en **Mover usuarios seleccionados a grupo**.</span><span class="sxs-lookup"><span data-stu-id="0b72e-118">Click **Action**, and then click **Move selected users to pool**.</span></span> <span data-ttu-id="0b72e-119">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0b72e-119">Click **OK**.</span></span>
    
     ![Cuadro de diálogo Mover usuarios, grupo de registradores de destino](../media/Migration_LyncServer_from_LyncServer2010_CPanelMoveUserSelectPoolDialog.png)
  
7. <span data-ttu-id="0b72e-121">Compruebe que la **columna del grupo** de registradores para los usuarios ahora contiene el grupo de Skype Empresarial Server 2019, que indica que los usuarios se han movido correctamente.</span><span class="sxs-lookup"><span data-stu-id="0b72e-121">Verify that the **Registrar pool** column for the users now contains the Skype for Business Server 2019 pool, which indicates that the users have been successfully moved.</span></span> 
    
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="0b72e-122">Para mover varios usuarios mediante el Shell de administración de Skype Empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="0b72e-122">To move multiple users by using the Skype for Business Server 2019 Management Shell</span></span>
<span data-ttu-id="0b72e-123"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="0b72e-123"><a name="sectionSection1"> </a></span></span>

1. <span data-ttu-id="0b72e-124">Abra el Shell de administración de Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="0b72e-124">Open the Skype for Business Server 2019 Management Shell.</span></span> 
    
2. <span data-ttu-id="0b72e-125">En la línea de comandos, escriba lo siguiente y reemplace **User1** y **User2** por nombres de usuario específicos que desee mover y reemplace **pool_FQDN** por el nombre del grupo de servidores de destino.</span><span class="sxs-lookup"><span data-stu-id="0b72e-125">At the command line, type the following and replace **User1** and **User2** with specific user names you want to move, and replace **pool_FQDN** with the name of the destination pool.</span></span> <span data-ttu-id="0b72e-126">En este ejemplo, moveremos los usuarios Hao Chen y Katie Jordan:</span><span class="sxs-lookup"><span data-stu-id="0b72e-126">In this example we will move users Hao Chen and Katie Jordan.</span></span> 
    
   ```PowerShell
   Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
   ```

    ![Ejemplo de cmdlet de Get-CsUser PowerShell](../media/Migration_LyncServer_from_LyncServer2010_move2users.jpg)
  
3. <span data-ttu-id="0b72e-128">Escriba lo siguiente en la línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="0b72e-128">At the command line, type the following:</span></span> 
    
   ```PowerShell
   Get-CsUser -Identity "User1"
   ```

4. <span data-ttu-id="0b72e-129">Ahora, la identidad **Grupo de registradores** debería apuntar al grupo que especificó como **pool_FQDN** en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="0b72e-129">The **Registrar Pool** identity should now point to the pool you specified as **pool_FQDN** in the previous step.</span></span> <span data-ttu-id="0b72e-130">La presencia de esta identidad confirma que se ha movido correctamente al usuario.</span><span class="sxs-lookup"><span data-stu-id="0b72e-130">The presence of this identity confirms that the user has been successfully moved.</span></span> <span data-ttu-id="0b72e-131">Repita el paso para comprobar que **se ha movido user2.**</span><span class="sxs-lookup"><span data-stu-id="0b72e-131">Repeat step to verify that **User2** has been moved.</span></span> 
    
     ![Salida del cmdlet Get-UsUser -Identity de PowerShell](../media/Migration_LyncServer_from_LyncServer2010_showuser.jpg)
  
## <a name="to-move-all-users-at-the-same-time-by-using-the-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="0b72e-133">Para mover todos los usuarios al mismo tiempo mediante el Shell de administración de Skype Empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="0b72e-133">To move all users at the same time by using the Skype for Business Server 2019 Management Shell</span></span>
<span data-ttu-id="0b72e-134"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="0b72e-134"><a name="sectionSection2"> </a></span></span>

<span data-ttu-id="0b72e-135">En este ejemplo, se han devuelto todos los usuarios al grupo heredado (pool01.contoso.net).</span><span class="sxs-lookup"><span data-stu-id="0b72e-135">In this example, all users have been returned to the legacy pool (pool01.contoso.net).</span></span> <span data-ttu-id="0b72e-136">Con el Shell de administración de Skype Empresarial Server 2019, moveremos todos los usuarios al mismo tiempo al grupo de Skype Empresarial Server 2019 (pool02.contoso.net).</span><span class="sxs-lookup"><span data-stu-id="0b72e-136">Using the Skype for Business Server 2019 Management Shell, we will move all users at the same time to the Skype for Business Server 2019 pool (pool02.contoso.net).</span></span>
  
1. <span data-ttu-id="0b72e-137">Abra el Shell de administración de Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="0b72e-137">Open the Skype for Business Server 2019 Management Shell.</span></span>
    
2. <span data-ttu-id="0b72e-138">Escriba lo siguiente en la línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="0b72e-138">At the command line, type the following:</span></span> 
    
   ```PowerShell
   Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
   ```

     ![Cmdlet de PowerShell y resultados en shell de administración](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserMultipleAll.png)
  
3. <span data-ttu-id="0b72e-140">Ejecute **Get-CsUser para** uno de los usuarios piloto.</span><span class="sxs-lookup"><span data-stu-id="0b72e-140">Run **Get-CsUser** for one of the pilot users.</span></span> 
    
   ```PowerShell
   Get-CsUser -Identity "Hao Chen"
   ```

4. <span data-ttu-id="0b72e-141">La **identidad del grupo** de registradores para cada usuario apunta ahora al grupo de servidores que **especificó como pool_FQDN** en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="0b72e-141">The **Registrar Pool** identity for each user now points to the pool you specified as **pool_FQDN** in the previous step.</span></span> <span data-ttu-id="0b72e-142">La presencia de esta identidad confirma que se movió al usuario correctamente.</span><span class="sxs-lookup"><span data-stu-id="0b72e-142">The presence of this identity confirms that the user has been successfully moved.</span></span> 
    
5. <span data-ttu-id="0b72e-143">Además, podemos ver la lista de usuarios en el Panel de control de Skype Empresarial Server 2019 y comprobar que el valor del grupo de registradores apunta ahora al grupo de Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="0b72e-143">Additionally, we can view the list of users in the Skype for Business Server 2019 Control Panel and verify that the Registrar Pool value now points to the Skype for Business Server 2019 pool.</span></span>
    
     ![Lista de usuarios del Panel de control de Skype Empresarial Server 2019](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserVerifyHao.JPG)
  

