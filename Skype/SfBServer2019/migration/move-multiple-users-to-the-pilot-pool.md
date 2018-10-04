---
title: Mover varios usuarios al grupo piloto
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Puede mover varios usuarios de su grupo heredado a su Skype para Business Server 2019 grupo piloto con Skype para el Panel de Control de Business Server 2019 o Skype para Shell de administración de Business Server 2019.
ms.openlocfilehash: 3b01613e16e41ed2ee7aac7bc6c443e19db933c2
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25372512"
---
# <a name="move-multiple-users-to-the-pilot-pool"></a><span data-ttu-id="b8845-103">Mover varios usuarios al grupo piloto</span><span class="sxs-lookup"><span data-stu-id="b8845-103">Move multiple users to the pilot pool</span></span>

<span data-ttu-id="b8845-104">Puede mover varios usuarios de su grupo heredado a su Skype para Business Server 2019 grupo piloto con Skype para el Panel de Control de Business Server 2019 o Skype para Shell de administración de Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="b8845-104">You can move multiple users from your legacy pool to your Skype for Business Server 2019 pilot pool using Skype for Business Server 2019 Control Panel or Skype for Business Server 2019 Management Shell.</span></span>

 <span data-ttu-id="b8845-105">**En este artículo**</span><span class="sxs-lookup"><span data-stu-id="b8845-105">**In this article**</span></span>
  
[<span data-ttu-id="b8845-106">Para mover varios usuarios mediante el Skype para el Panel de Control de Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="b8845-106">To move multiple users by using the Skype for Business Server 2019 Control Panel</span></span>](#sectionSection0)
  
[<span data-ttu-id="b8845-107">Para mover varios usuarios mediante el Skype para Shell de administración de Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="b8845-107">To move multiple users by using the Skype for Business Server 2019 Management Shell</span></span>](#sectionSection1)
  
[<span data-ttu-id="b8845-108">Para mover todos los usuarios al mismo tiempo mediante el Skype para Shell de administración de Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="b8845-108">To move all users at the same time by using the Skype for Business Server 2019 Management Shell</span></span>](#sectionSection2)
  
  
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-control-panel"></a><span data-ttu-id="b8845-109">Para mover varios usuarios mediante el Skype para el Panel de Control de Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="b8845-109">To move multiple users by using the Skype for Business Server 2019 Control Panel</span></span>
<span data-ttu-id="b8845-110"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="b8845-110"></span></span>

1. <span data-ttu-id="b8845-111">Abra Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="b8845-111">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="b8845-112">Haga clic en **usuarios**, haga clic en **Buscar**y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="b8845-112">Click **Users**, click **Search**, and then click **Find**.</span></span>
    
3. <span data-ttu-id="b8845-113">Seleccione dos usuarios que se desean mover a la Skype para el grupo de servidores de Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="b8845-113">Select two users that you want to move to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="b8845-114">En este ejemplo, se va a mover los usuarios Chen Bermejo y Claus Hansen.</span><span class="sxs-lookup"><span data-stu-id="b8845-114">In this example, we will move users Chen Yang and Claus Hansen.</span></span>
    
     ![Mover usuarios al grupo de registro específico](../media/Migration_LyncServer_CPanel_fromLyncServer2010_MoveMultipleUsersList.JPG)
  
4. <span data-ttu-id="b8845-116">En el menú **acción** , seleccione **mover usuarios seleccionados al grupo de servidores**.</span><span class="sxs-lookup"><span data-stu-id="b8845-116">From the **Action** menu, select **Move selected users to pool**.</span></span>
    
5. <span data-ttu-id="b8845-117">En la lista desplegable, seleccione el Skype para el grupo de servidores de Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="b8845-117">From the drop-down list, select the Skype for Business Server 2019 pool.</span></span>
    
6. <span data-ttu-id="b8845-118">Haga clic en **acción**y, a continuación, haga clic en **mover usuarios seleccionados al grupo de servidores**.</span><span class="sxs-lookup"><span data-stu-id="b8845-118">Click **Action**, and then click **Move selected users to pool**.</span></span> <span data-ttu-id="b8845-119">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b8845-119">Click **OK**.</span></span>
    
     ![Mover usuarios, cuadro de diálogo de grupo de servidores de registrador de destino](../media/Migration_LyncServer_from_LyncServer2010_CPanelMoveUserSelectPoolDialog.png)
  
7. <span data-ttu-id="b8845-121">Compruebe que la columna **grupo de registrador** para los usuarios ahora contiene el Skype para el grupo de Business Server 2019, que indica que los usuarios se han movido correctamente.</span><span class="sxs-lookup"><span data-stu-id="b8845-121">Verify that the **Registrar pool** column for the users now contains the Skype for Business Server 2019 pool, which indicates that the users have been successfully moved.</span></span> 
    
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="b8845-122">Para mover varios usuarios mediante el Skype para Shell de administración de Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="b8845-122">To move multiple users by using the Skype for Business Server 2019 Management Shell</span></span>
<span data-ttu-id="b8845-123"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="b8845-123"></span></span>

1. <span data-ttu-id="b8845-124">Abra el Skype para Shell de administración de Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="b8845-124">Open the Skype for Business Server 2019 Management Shell.</span></span> 
    
2. <span data-ttu-id="b8845-125">En la línea de comandos, escriba lo siguiente y reemplace **User1** y **User2** por nombres de usuario específicos que desea mover y sustituya **pool_FQDN** por el nombre del grupo de servidores de destino.</span><span class="sxs-lookup"><span data-stu-id="b8845-125">At the command line, type the following and replace **User1** and **User2** with specific user names you want to move, and replace **pool_FQDN** with the name of the destination pool.</span></span> <span data-ttu-id="b8845-126">En este ejemplo se va a mover los usuarios Hao Chen y Katie Jordan.</span><span class="sxs-lookup"><span data-stu-id="b8845-126">In this example we will move users Hao Chen and Katie Jordan.</span></span> 
    
   ```
   Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
   ```

    ![Ejemplo de cmdlet de PowerShell Get-CsUser](../media/Migration_LyncServer_from_LyncServer2010_move2users.jpg)
  
3. <span data-ttu-id="b8845-128">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="b8845-128">At the command line, type the following:</span></span> 
    
   ```
   Get-CsUser -Identity "User1"
   ```

4. <span data-ttu-id="b8845-129">La identidad **Del grupo de registrador** ahora debe apuntar al grupo de servidores especificado como **pool_FQDN** en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="b8845-129">The **Registrar Pool** identity should now point to the pool you specified as **pool_FQDN** in the previous step.</span></span> <span data-ttu-id="b8845-130">La presencia de esta identidad confirma que el usuario se ha movido correctamente.</span><span class="sxs-lookup"><span data-stu-id="b8845-130">The presence of this identity confirms that the user has been successfully moved.</span></span> <span data-ttu-id="b8845-131">Repita el paso para comprobar que se ha movido **el usuario 2** .</span><span class="sxs-lookup"><span data-stu-id="b8845-131">Repeat step to verify that **User2** has been moved.</span></span> 
    
     ![Salida de PowerShell Get-UsUser-cmdlet de identidad](../media/Migration_LyncServer_from_LyncServer2010_showuser.jpg)
  
## <a name="to-move-all-users-at-the-same-time-by-using-the-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="b8845-133">Para mover todos los usuarios al mismo tiempo mediante el Skype para Shell de administración de Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="b8845-133">To move all users at the same time by using the Skype for Business Server 2019 Management Shell</span></span>
<span data-ttu-id="b8845-134"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="b8845-134"></span></span>

<span data-ttu-id="b8845-135">En este ejemplo, se han devuelto todos los usuarios al grupo de servidores heredado (pool01.contoso.net).</span><span class="sxs-lookup"><span data-stu-id="b8845-135">In this example, all users have been returned to the legacy pool (pool01.contoso.net).</span></span> <span data-ttu-id="b8845-136">Usa el Skype para Shell de administración de Business Server 2019, se va a mover todos los usuarios al mismo tiempo a la Skype para el grupo de servidores de Business Server 2019 (pool02.contoso.net).</span><span class="sxs-lookup"><span data-stu-id="b8845-136">Using the Skype for Business Server 2019 Management Shell, we will move all users at the same time to the Skype for Business Server 2019 pool (pool02.contoso.net).</span></span>
  
1. <span data-ttu-id="b8845-137">Abra el Skype para Shell de administración de Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="b8845-137">Open the Skype for Business Server 2019 Management Shell.</span></span>
    
2. <span data-ttu-id="b8845-138">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="b8845-138">At the command line, type the following:</span></span> 
    
   ```
   Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
   ```

     ![Cmdlet de PowerShell y los resultados en el Shell de administración](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserMultipleAll.png)
  
3. <span data-ttu-id="b8845-140">Ejecute **Get-CsUser** para uno de los usuarios pilotos.</span><span class="sxs-lookup"><span data-stu-id="b8845-140">Run **Get-CsUser** for one of the pilot users.</span></span> 
    
   ```
   Get-CsUser -Identity "Hao Chen"
   ```

4. <span data-ttu-id="b8845-141">La identidad del **Grupo de registrador** para cada usuario ahora apunta al grupo de servidores especificado como **pool_FQDN** en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="b8845-141">The **Registrar Pool** identity for each user now points to the pool you specified as **pool_FQDN** in the previous step.</span></span> <span data-ttu-id="b8845-142">La presencia de esta identidad confirma que el usuario se ha movido correctamente.</span><span class="sxs-lookup"><span data-stu-id="b8845-142">The presence of this identity confirms that the user has been successfully moved.</span></span> 
    
5. <span data-ttu-id="b8845-143">Además, podemos ver la lista de usuarios en el Skype para el Panel de Control de Business Server 2019 y compruebe que el valor de grupo de registradores ahora apunta a la Skype para el grupo de servidores de Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="b8845-143">Additionally, we can view the list of users in the Skype for Business Server 2019 Control Panel and verify that the Registrar Pool value now points to the Skype for Business Server 2019 pool.</span></span>
    
     ![Skype para la lista de usuario del Panel de Control de Business Server 2019](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserVerifyHao.JPG)
  

