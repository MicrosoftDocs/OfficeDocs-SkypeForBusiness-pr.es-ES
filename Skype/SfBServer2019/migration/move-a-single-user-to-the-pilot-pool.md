---
title: Mover un solo usuario a la agrupación piloto
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Puede mover un usuario de su grupo heredado a su grupo piloto de Skype empresarial Server 2019 con el panel de control de Skype empresarial Server 2019 o el shell de administración de Skype empresarial 2019. En el ejemplo siguiente, en la columna registrar grupo, pool01.contoso.net es el grupo heredado y los seis de estos usuarios están conectados a este grupo. Use los procedimientos siguientes para mover un usuario a su grupo de servidores de Skype empresarial 2019 con el panel de control de Skype empresarial Server 2019 y el shell de administración de Skype empresarial Server.
ms.openlocfilehash: 8964dd3dc868c22cd14389ba70b88d32b6bd145a
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "40988965"
---
# <a name="move-a-single-user-to-the-pilot-pool"></a><span data-ttu-id="6a9aa-105">Mover un solo usuario a la agrupación piloto</span><span class="sxs-lookup"><span data-stu-id="6a9aa-105">Move a single user to the pilot pool</span></span>

<span data-ttu-id="6a9aa-106">Puede mover un usuario de su grupo heredado a su grupo piloto de Skype empresarial Server 2019 con el panel de control de Skype empresarial Server 2019 o el shell de administración de Skype empresarial 2019.</span><span class="sxs-lookup"><span data-stu-id="6a9aa-106">You can move a user from your legacy pool to your Skype for Business Server 2019 pilot pool using Skype for Business Server 2019 Control Panel or Skype for Business Server 2019 Management Shell.</span></span> <span data-ttu-id="6a9aa-107">En el ejemplo siguiente, en la columna **registrar grupo** , **pool01.contoso.net** es el grupo heredado y los seis de estos usuarios están conectados a este grupo.</span><span class="sxs-lookup"><span data-stu-id="6a9aa-107">In the example below, in the **Registrar pool** column, **pool01.contoso.net** is the legacy pool, and all six of these users are connected to this pool.</span></span> <span data-ttu-id="6a9aa-108">Use los procedimientos siguientes para mover un usuario a su grupo de servidores de Skype empresarial 2019 con el panel de control de Skype empresarial Server 2019 y el shell de administración de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="6a9aa-108">Use the following procedures to move a user to your Skype for Business Server 2019 pool using Skype for Business Server 2019 Control Panel and Skype for Business Server Management Shell.</span></span> 
  
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-control-panel"></a><span data-ttu-id="6a9aa-109">Para mover un usuario mediante el panel de control de Skype empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="6a9aa-109">To move a user by using the Skype for Business Server 2019 Control Panel</span></span>
  
1. <span data-ttu-id="6a9aa-110">Inicie sesión en el servidor front-end con una cuenta que sea miembro del grupo RTCUniversalServerAdmins o miembro del rol administrativo CsAdministrator o CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="6a9aa-110">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>
    
2. <span data-ttu-id="6a9aa-111">Abra el **Panel de control de Skype empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="6a9aa-111">Open **Skype for Business Server Control Panel**.</span></span>
    
3. <span data-ttu-id="6a9aa-112">Haga clic en **usuarios**, en **Buscar**y, a continuación, en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="6a9aa-112">Click **Users**, click **Search**, and then click **Find**.</span></span>
    
4. <span data-ttu-id="6a9aa-113">Seleccione el usuario que desea mover al grupo de servidores de Skype empresarial 2019.</span><span class="sxs-lookup"><span data-stu-id="6a9aa-113">Select a user that you want to move to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="6a9aa-114">En este ejemplo, moveremos a Sara Davis.</span><span class="sxs-lookup"><span data-stu-id="6a9aa-114">In this example, we will move user Sara Davis.</span></span>
    
5. <span data-ttu-id="6a9aa-115">En el menú **Acción**, seleccione **Mover usuarios seleccionados a grupo**.</span><span class="sxs-lookup"><span data-stu-id="6a9aa-115">On the **Action** menu, select **Move selected users to pool**.</span></span>
    
6. <span data-ttu-id="6a9aa-116">En la lista desplegable, seleccione el grupo de servidores de Skype empresarial 2019.</span><span class="sxs-lookup"><span data-stu-id="6a9aa-116">From the drop-down list, select the Skype for Business Server 2019 pool.</span></span>
    
7. <span data-ttu-id="6a9aa-117">Haga clic en **acción**y, a continuación, haga clic en **mover los usuarios seleccionados al grupo**.</span><span class="sxs-lookup"><span data-stu-id="6a9aa-117">Click **Action**, and then click **Move selected users to pool**.</span></span> <span data-ttu-id="6a9aa-118">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6a9aa-118">Click **OK**.</span></span>
  
8. <span data-ttu-id="6a9aa-119">Compruebe que la columna del **Grupo registrador** del usuario contiene ahora el grupo de servidores de Skype empresarial 2019, lo que indica que el usuario se ha movido correctamente.</span><span class="sxs-lookup"><span data-stu-id="6a9aa-119">Verify that the **Registrar pool** column for the user now contains the Skype for Business Server 2019 pool, which indicates that the user has been successfully moved.</span></span> 
    
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="6a9aa-120">Para mover un usuario mediante el shell de administración de Skype empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="6a9aa-120">To move a user by using the Skype for Business Server 2019 Management Shell</span></span>

1. <span data-ttu-id="6a9aa-121">Abra el shell de administración de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="6a9aa-121">Open the Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="6a9aa-122">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="6a9aa-122">At the command line, type the following:</span></span> 
    
   ```PowerShell
   Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"
   ```

3. <span data-ttu-id="6a9aa-123">A continuación, en la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6a9aa-123">Next, at the command line, type the following:</span></span> 
    
   ```PowerShell
   Get-CsUser -Identity "David Pelton"
   ```

4. <span data-ttu-id="6a9aa-124">La identidad de **RegistrarPool** apunta ahora al grupo de servidores de Skype empresarial 2019.</span><span class="sxs-lookup"><span data-stu-id="6a9aa-124">The **RegistrarPool** identity now points to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="6a9aa-125">La presencia de esta identidad confirma que el usuario se movió correctamente.</span><span class="sxs-lookup"><span data-stu-id="6a9aa-125">The presence of this identity confirms that the user has been successfully moved.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="6a9aa-126">Para obtener detalles sobre el cmdlet **Get-CsUser** , ejecute: **Get-Help Get-CsUser-Detailed**</span><span class="sxs-lookup"><span data-stu-id="6a9aa-126">For details about the **Get-CsUser** cmdlet, run: **Get-Help Get-CsUser -Detailed**</span></span>
  

