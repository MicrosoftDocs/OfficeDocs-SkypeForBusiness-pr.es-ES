---
title: Mover varios usuarios a la agrupación piloto
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Puede mover varios usuarios de su grupo heredado a su grupo piloto de Skype empresarial Server 2019 con el panel de control de Skype empresarial Server 2019 o el shell de administración de Skype empresarial 2019.
ms.openlocfilehash: abaffea04ff190b2ae99639484f63b564fd7784a
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "40988955"
---
# <a name="move-multiple-users-to-the-pilot-pool"></a><span data-ttu-id="02bf0-103">Mover varios usuarios a la agrupación piloto</span><span class="sxs-lookup"><span data-stu-id="02bf0-103">Move multiple users to the pilot pool</span></span>

<span data-ttu-id="02bf0-104">Puede mover varios usuarios de su grupo heredado a su grupo piloto de Skype empresarial Server 2019 con el panel de control de Skype empresarial Server 2019 o el shell de administración de Skype empresarial 2019.</span><span class="sxs-lookup"><span data-stu-id="02bf0-104">You can move multiple users from your legacy pool to your Skype for Business Server 2019 pilot pool using Skype for Business Server 2019 Control Panel or Skype for Business Server 2019 Management Shell.</span></span>

 <span data-ttu-id="02bf0-105">**En este artículo**</span><span class="sxs-lookup"><span data-stu-id="02bf0-105">**In this article**</span></span>
  
[<span data-ttu-id="02bf0-106">Para mover varios usuarios con el panel de control de Skype empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="02bf0-106">To move multiple users by using the Skype for Business Server 2019 Control Panel</span></span>](#sectionSection0)
  
[<span data-ttu-id="02bf0-107">Para mover varios usuarios con el shell de administración de Skype empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="02bf0-107">To move multiple users by using the Skype for Business Server 2019 Management Shell</span></span>](#sectionSection1)
  
[<span data-ttu-id="02bf0-108">Para mover todos los usuarios al mismo tiempo con el shell de administración de Skype empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="02bf0-108">To move all users at the same time by using the Skype for Business Server 2019 Management Shell</span></span>](#sectionSection2)
  
  
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-control-panel"></a><span data-ttu-id="02bf0-109">Para mover varios usuarios con el panel de control de Skype empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="02bf0-109">To move multiple users by using the Skype for Business Server 2019 Control Panel</span></span>
<span data-ttu-id="02bf0-110"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="02bf0-110"></span></span>

1. <span data-ttu-id="02bf0-111">Abra el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="02bf0-111">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="02bf0-112">Haga clic en **usuarios**, en **Buscar**y, a continuación, en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="02bf0-112">Click **Users**, click **Search**, and then click **Find**.</span></span>
    
3. <span data-ttu-id="02bf0-113">Seleccione dos usuarios que quiera mover al grupo de servidores de Skype empresarial 2019.</span><span class="sxs-lookup"><span data-stu-id="02bf0-113">Select two users that you want to move to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="02bf0-114">En este ejemplo, se moverán los usuarios Chen Yang y Claus Hansen.</span><span class="sxs-lookup"><span data-stu-id="02bf0-114">In this example, we will move users Chen Yang and Claus Hansen.</span></span>
    
     ![Mover usuarios a un grupo de registros específico](../media/Migration_LyncServer_CPanel_fromLyncServer2010_MoveMultipleUsersList.JPG)
  
4. <span data-ttu-id="02bf0-116">En el menú **acción** , seleccione **mover usuarios seleccionados al grupo**.</span><span class="sxs-lookup"><span data-stu-id="02bf0-116">From the **Action** menu, select **Move selected users to pool**.</span></span>
    
5. <span data-ttu-id="02bf0-117">En la lista desplegable, seleccione el grupo de servidores de Skype empresarial 2019.</span><span class="sxs-lookup"><span data-stu-id="02bf0-117">From the drop-down list, select the Skype for Business Server 2019 pool.</span></span>
    
6. <span data-ttu-id="02bf0-118">Haga clic en **acción**y, a continuación, haga clic en **mover los usuarios seleccionados al grupo**.</span><span class="sxs-lookup"><span data-stu-id="02bf0-118">Click **Action**, and then click **Move selected users to pool**.</span></span> <span data-ttu-id="02bf0-119">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="02bf0-119">Click **OK**.</span></span>
    
     ![Cuadro de diálogo mover usuarios, conjunto de registradores de destino](../media/Migration_LyncServer_from_LyncServer2010_CPanelMoveUserSelectPoolDialog.png)
  
7. <span data-ttu-id="02bf0-121">Compruebe que la columna del **Grupo registrador** de los usuarios contiene ahora el grupo de servidores de Skype empresarial 2019, lo que indica que los usuarios se movieron correctamente.</span><span class="sxs-lookup"><span data-stu-id="02bf0-121">Verify that the **Registrar pool** column for the users now contains the Skype for Business Server 2019 pool, which indicates that the users have been successfully moved.</span></span> 
    
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="02bf0-122">Para mover varios usuarios con el shell de administración de Skype empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="02bf0-122">To move multiple users by using the Skype for Business Server 2019 Management Shell</span></span>
<span data-ttu-id="02bf0-123"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="02bf0-123"></span></span>

1. <span data-ttu-id="02bf0-124">Abra el shell de administración de Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="02bf0-124">Open the Skype for Business Server 2019 Management Shell.</span></span> 
    
2. <span data-ttu-id="02bf0-125">En la línea de comandos, escriba lo siguiente y reemplace **user1** y **usuario2** por los nombres de usuario específicos que desea mover, y reemplace **pool_FQDN** por el nombre del grupo de destino.</span><span class="sxs-lookup"><span data-stu-id="02bf0-125">At the command line, type the following and replace **User1** and **User2** with specific user names you want to move, and replace **pool_FQDN** with the name of the destination pool.</span></span> <span data-ttu-id="02bf0-126">En este ejemplo, moveremos a los usuarios Hao Chen y Katie Katie.</span><span class="sxs-lookup"><span data-stu-id="02bf0-126">In this example we will move users Hao Chen and Katie Jordan.</span></span> 
    
   ```PowerShell
   Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
   ```

    ![Ejemplo de cmdlet Get-CsUser de PowerShell](../media/Migration_LyncServer_from_LyncServer2010_move2users.jpg)
  
3. <span data-ttu-id="02bf0-128">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="02bf0-128">At the command line, type the following:</span></span> 
    
   ```PowerShell
   Get-CsUser -Identity "User1"
   ```

4. <span data-ttu-id="02bf0-129">La identidad del **grupo de registradores** debe apuntar ahora al grupo que especificó como **pool_FQDN** en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="02bf0-129">The **Registrar Pool** identity should now point to the pool you specified as **pool_FQDN** in the previous step.</span></span> <span data-ttu-id="02bf0-130">La presencia de esta identidad confirma que el usuario se movió correctamente.</span><span class="sxs-lookup"><span data-stu-id="02bf0-130">The presence of this identity confirms that the user has been successfully moved.</span></span> <span data-ttu-id="02bf0-131">Repita el paso para comprobar que **usuario2** se ha movido.</span><span class="sxs-lookup"><span data-stu-id="02bf0-131">Repeat step to verify that **User2** has been moved.</span></span> 
    
     ![Resultado del cmdlet Get-UsUser-Identity de PowerShell](../media/Migration_LyncServer_from_LyncServer2010_showuser.jpg)
  
## <a name="to-move-all-users-at-the-same-time-by-using-the-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="02bf0-133">Para mover todos los usuarios al mismo tiempo con el shell de administración de Skype empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="02bf0-133">To move all users at the same time by using the Skype for Business Server 2019 Management Shell</span></span>
<span data-ttu-id="02bf0-134"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="02bf0-134"></span></span>

<span data-ttu-id="02bf0-135">En este ejemplo, todos los usuarios han sido devueltos al grupo heredado (pool01.contoso.net).</span><span class="sxs-lookup"><span data-stu-id="02bf0-135">In this example, all users have been returned to the legacy pool (pool01.contoso.net).</span></span> <span data-ttu-id="02bf0-136">Con el shell de administración de Skype empresarial Server 2019, moveremos todos los usuarios al mismo tiempo al grupo de servidores de Skype empresarial 2019 (pool02.contoso.net).</span><span class="sxs-lookup"><span data-stu-id="02bf0-136">Using the Skype for Business Server 2019 Management Shell, we will move all users at the same time to the Skype for Business Server 2019 pool (pool02.contoso.net).</span></span>
  
1. <span data-ttu-id="02bf0-137">Abra el shell de administración de Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="02bf0-137">Open the Skype for Business Server 2019 Management Shell.</span></span>
    
2. <span data-ttu-id="02bf0-138">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="02bf0-138">At the command line, type the following:</span></span> 
    
   ```PowerShell
   Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
   ```

     ![Cmdlet de PowerShell y resultados en el shell de administración](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserMultipleAll.png)
  
3. <span data-ttu-id="02bf0-140">Ejecute **Get-CsUser** para uno de los usuarios de la prueba piloto.</span><span class="sxs-lookup"><span data-stu-id="02bf0-140">Run **Get-CsUser** for one of the pilot users.</span></span> 
    
   ```PowerShell
   Get-CsUser -Identity "Hao Chen"
   ```

4. <span data-ttu-id="02bf0-141">La identidad del **grupo de registradores** de cada usuario apunta ahora al grupo que especificó como **pool_FQDN** en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="02bf0-141">The **Registrar Pool** identity for each user now points to the pool you specified as **pool_FQDN** in the previous step.</span></span> <span data-ttu-id="02bf0-142">La presencia de esta identidad confirma que el usuario se movió correctamente.</span><span class="sxs-lookup"><span data-stu-id="02bf0-142">The presence of this identity confirms that the user has been successfully moved.</span></span> 
    
5. <span data-ttu-id="02bf0-143">Además, podemos ver la lista de usuarios en el panel de control de Skype empresarial Server 2019 y verificar que el valor del grupo de registrador ahora apunta al grupo de Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="02bf0-143">Additionally, we can view the list of users in the Skype for Business Server 2019 Control Panel and verify that the Registrar Pool value now points to the Skype for Business Server 2019 pool.</span></span>
    
     ![Lista de usuarios del panel de control de Skype empresarial Server 2019](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserVerifyHao.JPG)
  

