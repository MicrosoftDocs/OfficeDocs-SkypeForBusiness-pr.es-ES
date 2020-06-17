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
description: Puede mover varios usuarios de su grupo heredado al grupo piloto de Skype empresarial Server 2019 mediante el panel de control de Skype empresarial Server 2019 o el shell de administración de Skype empresarial Server 2019.
ms.openlocfilehash: d1b003c5630a0917fbecbd9b04196675657fef83
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753432"
---
# <a name="move-multiple-users-to-the-pilot-pool"></a><span data-ttu-id="b08fb-103">Mover varios usuarios al grupo piloto</span><span class="sxs-lookup"><span data-stu-id="b08fb-103">Move multiple users to the pilot pool</span></span>

<span data-ttu-id="b08fb-104">Puede mover varios usuarios de su grupo heredado al grupo piloto de Skype empresarial Server 2019 mediante el panel de control de Skype empresarial Server 2019 o el shell de administración de Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="b08fb-104">You can move multiple users from your legacy pool to your Skype for Business Server 2019 pilot pool using Skype for Business Server 2019 Control Panel or Skype for Business Server 2019 Management Shell.</span></span>

 <span data-ttu-id="b08fb-105">**En este artículo**</span><span class="sxs-lookup"><span data-stu-id="b08fb-105">**In this article**</span></span>
  
[<span data-ttu-id="b08fb-106">Para mover varios usuarios mediante el panel de control de Skype empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="b08fb-106">To move multiple users by using the Skype for Business Server 2019 Control Panel</span></span>](#sectionSection0)
  
[<span data-ttu-id="b08fb-107">Para mover varios usuarios mediante el shell de administración de Skype empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="b08fb-107">To move multiple users by using the Skype for Business Server 2019 Management Shell</span></span>](#sectionSection1)
  
[<span data-ttu-id="b08fb-108">Para mover todos los usuarios al mismo tiempo mediante el shell de administración de Skype empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="b08fb-108">To move all users at the same time by using the Skype for Business Server 2019 Management Shell</span></span>](#sectionSection2)
  
  
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-control-panel"></a><span data-ttu-id="b08fb-109">Para mover varios usuarios mediante el panel de control de Skype empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="b08fb-109">To move multiple users by using the Skype for Business Server 2019 Control Panel</span></span>
<span data-ttu-id="b08fb-110"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="b08fb-110"><a name="sectionSection0"> </a></span></span>

1. <span data-ttu-id="b08fb-111">Abra el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="b08fb-111">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="b08fb-112">Haga clic en **Usuarios**, **Buscar** y, a continuación, en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="b08fb-112">Click **Users**, click **Search**, and then click **Find**.</span></span>
    
3. <span data-ttu-id="b08fb-113">Seleccione dos usuarios que quiera mover al grupo de Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="b08fb-113">Select two users that you want to move to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="b08fb-114">En este ejemplo, moveremos los usuarios Chen Yang y Claus Hansen.</span><span class="sxs-lookup"><span data-stu-id="b08fb-114">In this example, we will move users Chen Yang and Claus Hansen.</span></span>
    
     ![Mover usuarios a un grupo de registros específico](../media/Migration_LyncServer_CPanel_fromLyncServer2010_MoveMultipleUsersList.JPG)
  
4. <span data-ttu-id="b08fb-116">En el menú **Acción** seleccione **Mover usuarios seleccionados a grupo**.</span><span class="sxs-lookup"><span data-stu-id="b08fb-116">From the **Action** menu, select **Move selected users to pool**.</span></span>
    
5. <span data-ttu-id="b08fb-117">En la lista desplegable, seleccione el grupo de servidores de Skype empresarial 2019.</span><span class="sxs-lookup"><span data-stu-id="b08fb-117">From the drop-down list, select the Skype for Business Server 2019 pool.</span></span>
    
6. <span data-ttu-id="b08fb-118">Haga clic en **Acción** y, a continuación, en **Mover usuarios seleccionados a grupo**.</span><span class="sxs-lookup"><span data-stu-id="b08fb-118">Click **Action**, and then click **Move selected users to pool**.</span></span> <span data-ttu-id="b08fb-119">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b08fb-119">Click **OK**.</span></span>
    
     ![Cuadro de diálogo mover usuarios, grupo de registradores de destino](../media/Migration_LyncServer_from_LyncServer2010_CPanelMoveUserSelectPoolDialog.png)
  
7. <span data-ttu-id="b08fb-121">Compruebe que la columna **grupo de registradores** para los usuarios contiene ahora el grupo de servidores de Skype empresarial Server 2019, que indica que los usuarios se han movido correctamente.</span><span class="sxs-lookup"><span data-stu-id="b08fb-121">Verify that the **Registrar pool** column for the users now contains the Skype for Business Server 2019 pool, which indicates that the users have been successfully moved.</span></span> 
    
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="b08fb-122">Para mover varios usuarios mediante el shell de administración de Skype empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="b08fb-122">To move multiple users by using the Skype for Business Server 2019 Management Shell</span></span>
<span data-ttu-id="b08fb-123"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="b08fb-123"><a name="sectionSection1"> </a></span></span>

1. <span data-ttu-id="b08fb-124">Abra el shell de administración de Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="b08fb-124">Open the Skype for Business Server 2019 Management Shell.</span></span> 
    
2. <span data-ttu-id="b08fb-125">En la línea de comandos, escriba lo siguiente y reemplace **user1** y **user2** por los nombres de usuario específicos que desea mover, y reemplace **pool_FQDN** por el nombre del grupo de servidores de destino.</span><span class="sxs-lookup"><span data-stu-id="b08fb-125">At the command line, type the following and replace **User1** and **User2** with specific user names you want to move, and replace **pool_FQDN** with the name of the destination pool.</span></span> <span data-ttu-id="b08fb-126">En este ejemplo, moveremos los usuarios Hao Chen y Katie Jordan:</span><span class="sxs-lookup"><span data-stu-id="b08fb-126">In this example we will move users Hao Chen and Katie Jordan.</span></span> 
    
   ```PowerShell
   Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
   ```

    ![Ejemplo de cmdlet Get-CsUser de PowerShell](../media/Migration_LyncServer_from_LyncServer2010_move2users.jpg)
  
3. <span data-ttu-id="b08fb-128">Escriba lo siguiente en la línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="b08fb-128">At the command line, type the following:</span></span> 
    
   ```PowerShell
   Get-CsUser -Identity "User1"
   ```

4. <span data-ttu-id="b08fb-129">Ahora, la identidad **Grupo de registradores** debería apuntar al grupo que especificó como **pool_FQDN** en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="b08fb-129">The **Registrar Pool** identity should now point to the pool you specified as **pool_FQDN** in the previous step.</span></span> <span data-ttu-id="b08fb-130">La presencia de esta identidad confirma que se ha movido correctamente al usuario.</span><span class="sxs-lookup"><span data-stu-id="b08fb-130">The presence of this identity confirms that the user has been successfully moved.</span></span> <span data-ttu-id="b08fb-131">Repita el paso para comprobar que se ha movido a **usuario2** .</span><span class="sxs-lookup"><span data-stu-id="b08fb-131">Repeat step to verify that **User2** has been moved.</span></span> 
    
     ![Resultado del cmdlet PowerShell Get-UsUser-Identity](../media/Migration_LyncServer_from_LyncServer2010_showuser.jpg)
  
## <a name="to-move-all-users-at-the-same-time-by-using-the-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="b08fb-133">Para mover todos los usuarios al mismo tiempo mediante el shell de administración de Skype empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="b08fb-133">To move all users at the same time by using the Skype for Business Server 2019 Management Shell</span></span>
<span data-ttu-id="b08fb-134"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="b08fb-134"><a name="sectionSection2"> </a></span></span>

<span data-ttu-id="b08fb-135">En este ejemplo, todos los usuarios se han devuelto al grupo heredado (pool01.contoso.net).</span><span class="sxs-lookup"><span data-stu-id="b08fb-135">In this example, all users have been returned to the legacy pool (pool01.contoso.net).</span></span> <span data-ttu-id="b08fb-136">Con el shell de administración de Skype empresarial Server 2019, todos los usuarios se moverán al mismo tiempo al grupo de servidores de Skype empresarial 2019 (pool02.contoso.net).</span><span class="sxs-lookup"><span data-stu-id="b08fb-136">Using the Skype for Business Server 2019 Management Shell, we will move all users at the same time to the Skype for Business Server 2019 pool (pool02.contoso.net).</span></span>
  
1. <span data-ttu-id="b08fb-137">Abra el shell de administración de Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="b08fb-137">Open the Skype for Business Server 2019 Management Shell.</span></span>
    
2. <span data-ttu-id="b08fb-138">Escriba lo siguiente en la línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="b08fb-138">At the command line, type the following:</span></span> 
    
   ```PowerShell
   Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
   ```

     ![Cmdlet de PowerShell y resultados en Shell de administración](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserMultipleAll.png)
  
3. <span data-ttu-id="b08fb-140">Ejecute **Get-CsUser** para uno de los usuarios piloto.</span><span class="sxs-lookup"><span data-stu-id="b08fb-140">Run **Get-CsUser** for one of the pilot users.</span></span> 
    
   ```PowerShell
   Get-CsUser -Identity "Hao Chen"
   ```

4. <span data-ttu-id="b08fb-141">La identidad del **grupo de registradores** para cada usuario apunta ahora al grupo especificado como **pool_FQDN** en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="b08fb-141">The **Registrar Pool** identity for each user now points to the pool you specified as **pool_FQDN** in the previous step.</span></span> <span data-ttu-id="b08fb-142">La presencia de esta identidad confirma que se movió al usuario correctamente.</span><span class="sxs-lookup"><span data-stu-id="b08fb-142">The presence of this identity confirms that the user has been successfully moved.</span></span> 
    
5. <span data-ttu-id="b08fb-143">Además, podemos ver la lista de usuarios en el panel de control de Skype empresarial Server 2019 y comprobar que el valor del grupo de registradores ahora apunta al grupo de Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="b08fb-143">Additionally, we can view the list of users in the Skype for Business Server 2019 Control Panel and verify that the Registrar Pool value now points to the Skype for Business Server 2019 pool.</span></span>
    
     ![Lista de usuarios del panel de control de Skype empresarial Server 2019](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserVerifyHao.JPG)
  

