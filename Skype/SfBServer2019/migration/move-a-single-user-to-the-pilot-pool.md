---
title: Mover un solo usuario a la agrupación piloto
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Puede mover un usuario de su grupo heredado a su grupo piloto de Skype empresarial Server 2019 con el panel de control de Skype empresarial Server 2019 o el shell de administración de Skype empresarial 2019. En el ejemplo siguiente, en la columna registrar grupo, pool01.contoso.net es el grupo heredado y los seis de estos usuarios están conectados a este grupo. Use los procedimientos siguientes para mover un usuario a su grupo de servidores de Skype empresarial 2019 con el panel de control de Skype empresarial Server 2019 y el shell de administración de Skype empresarial Server.
ms.openlocfilehash: 23ce56f8bcf759aeeaa9e9a9b64820958c656c6a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34298137"
---
# <a name="move-a-single-user-to-the-pilot-pool"></a><span data-ttu-id="76b36-105">Mover un solo usuario a la agrupación piloto</span><span class="sxs-lookup"><span data-stu-id="76b36-105">Move a single user to the pilot pool</span></span>

<span data-ttu-id="76b36-106">Puede mover un usuario de su grupo heredado a su grupo piloto de Skype empresarial Server 2019 con el panel de control de Skype empresarial Server 2019 o el shell de administración de Skype empresarial 2019.</span><span class="sxs-lookup"><span data-stu-id="76b36-106">You can move a user from your legacy pool to your Skype for Business Server 2019 pilot pool using Skype for Business Server 2019 Control Panel or Skype for Business Server 2019 Management Shell.</span></span> <span data-ttu-id="76b36-107">En el ejemplo siguiente, en la columna **registrar grupo** , **pool01.contoso.net** es el grupo heredado y los seis de estos usuarios están conectados a este grupo.</span><span class="sxs-lookup"><span data-stu-id="76b36-107">In the example below, in the **Registrar pool** column, **pool01.contoso.net** is the legacy pool, and all six of these users are connected to this pool.</span></span> <span data-ttu-id="76b36-108">Use los procedimientos siguientes para mover un usuario a su grupo de servidores de Skype empresarial 2019 con el panel de control de Skype empresarial Server 2019 y el shell de administración de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="76b36-108">Use the following procedures to move a user to your Skype for Business Server 2019 pool using Skype for Business Server 2019 Control Panel and Skype for Business Server Management Shell.</span></span> 
  
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-control-panel"></a><span data-ttu-id="76b36-109">Para mover un usuario mediante el panel de control de Skype empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="76b36-109">To move a user by using the Skype for Business Server 2019 Control Panel</span></span>
  
1. <span data-ttu-id="76b36-110">Inicie sesión en el servidor front-end con una cuenta que sea miembro del grupo RTCUniversalServerAdmins o miembro del rol administrativo CsAdministrator o CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="76b36-110">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>
    
2. <span data-ttu-id="76b36-111">Abra el **Panel de control de Skype empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="76b36-111">Open **Skype for Business Server Control Panel**.</span></span>
    
3. <span data-ttu-id="76b36-112">Haga clic en **usuarios**, en **Buscar**y, a continuación, en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="76b36-112">Click **Users**, click **Search**, and then click **Find**.</span></span>
    
4. <span data-ttu-id="76b36-113">Seleccione el usuario que desea mover al grupo de servidores de Skype empresarial 2019.</span><span class="sxs-lookup"><span data-stu-id="76b36-113">Select a user that you want to move to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="76b36-114">En este ejemplo, moveremos a Sara Davis.</span><span class="sxs-lookup"><span data-stu-id="76b36-114">In this example, we will move user Sara Davis.</span></span>
    
5. <span data-ttu-id="76b36-115">En el menú **Acción**, seleccione **Mover usuarios seleccionados a grupo**.</span><span class="sxs-lookup"><span data-stu-id="76b36-115">On the **Action** menu, select **Move selected users to pool**.</span></span>
    
6. <span data-ttu-id="76b36-116">En la lista desplegable, seleccione el grupo de servidores de Skype empresarial 2019.</span><span class="sxs-lookup"><span data-stu-id="76b36-116">From the drop-down list, select the Skype for Business Server 2019 pool.</span></span>
    
7. <span data-ttu-id="76b36-117">Haga clic en **acción**y, a continuación, haga clic en **mover los usuarios seleccionados al grupo**.</span><span class="sxs-lookup"><span data-stu-id="76b36-117">Click **Action**, and then click **Move selected users to pool**.</span></span> <span data-ttu-id="76b36-118">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="76b36-118">Click **OK**.</span></span>
  
8. <span data-ttu-id="76b36-119">Compruebe que la columna del **Grupo registrador** del usuario contiene ahora el grupo de servidores de Skype empresarial 2019, lo que indica que el usuario se ha movido correctamente.</span><span class="sxs-lookup"><span data-stu-id="76b36-119">Verify that the **Registrar pool** column for the user now contains the Skype for Business Server 2019 pool, which indicates that the user has been successfully moved.</span></span> 
    
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="76b36-120">Para mover un usuario mediante el shell de administración de Skype empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="76b36-120">To move a user by using the Skype for Business Server 2019 Management Shell</span></span>

1. <span data-ttu-id="76b36-121">Abra el shell de administración de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="76b36-121">Open the Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="76b36-122">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="76b36-122">At the command line, type the following:</span></span> 
    
   ```
   Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"
   ```

3. <span data-ttu-id="76b36-123">A continuación, en la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="76b36-123">Next, at the command line, type the following:</span></span> 
    
   ```
   Get-CsUser -Identity "David Pelton"
   ```

4. <span data-ttu-id="76b36-124">La identidad de **RegistrarPool** apunta ahora al grupo de servidores de Skype empresarial 2019.</span><span class="sxs-lookup"><span data-stu-id="76b36-124">The **RegistrarPool** identity now points to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="76b36-125">La presencia de esta identidad confirma que el usuario se movió correctamente.</span><span class="sxs-lookup"><span data-stu-id="76b36-125">The presence of this identity confirms that the user has been successfully moved.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="76b36-126">Para obtener detalles sobre el cmdlet **Get-CsUser** , ejecute: **Get-Help Get-CsUser-** Detailed</span><span class="sxs-lookup"><span data-stu-id="76b36-126">For details about the **Get-CsUser** cmdlet, run: **Get-Help Get-CsUser -Detailed**</span></span>
  

