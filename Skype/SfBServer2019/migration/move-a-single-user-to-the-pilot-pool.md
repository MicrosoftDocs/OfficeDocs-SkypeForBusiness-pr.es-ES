---
title: Mover un solo usuario al grupo piloto
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
description: Puede mover un usuario de su grupo de servidores heredado al grupo piloto de Skype empresarial Server 2019 mediante el panel de control de Skype empresarial Server 2019 o el shell de administración de Skype empresarial Server 2019. En el ejemplo siguiente, en la columna registrador de grupo de servidores, pool01.contoso.net es el grupo heredado y los seis usuarios están conectados a este grupo. Use los siguientes procedimientos para mover un usuario al grupo de servidores de Skype empresarial Server 2019 mediante el panel de control de Skype empresarial Server 2019 y el shell de administración de Skype empresarial Server.
ms.openlocfilehash: 6be30f37987cc31835a12178d32a8337d9fc5cae
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752512"
---
# <a name="move-a-single-user-to-the-pilot-pool"></a><span data-ttu-id="f5565-105">Mover un solo usuario al grupo piloto</span><span class="sxs-lookup"><span data-stu-id="f5565-105">Move a single user to the pilot pool</span></span>

<span data-ttu-id="f5565-106">Puede mover un usuario de su grupo de servidores heredado al grupo piloto de Skype empresarial Server 2019 mediante el panel de control de Skype empresarial Server 2019 o el shell de administración de Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="f5565-106">You can move a user from your legacy pool to your Skype for Business Server 2019 pilot pool using Skype for Business Server 2019 Control Panel or Skype for Business Server 2019 Management Shell.</span></span> <span data-ttu-id="f5565-107">En el ejemplo siguiente, en la columna **registrador de grupo** de servidores, **pool01.contoso.net** es el grupo heredado y los seis usuarios están conectados a este grupo.</span><span class="sxs-lookup"><span data-stu-id="f5565-107">In the example below, in the **Registrar pool** column, **pool01.contoso.net** is the legacy pool, and all six of these users are connected to this pool.</span></span> <span data-ttu-id="f5565-108">Use los siguientes procedimientos para mover un usuario al grupo de servidores de Skype empresarial Server 2019 mediante el panel de control de Skype empresarial Server 2019 y el shell de administración de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="f5565-108">Use the following procedures to move a user to your Skype for Business Server 2019 pool using Skype for Business Server 2019 Control Panel and Skype for Business Server Management Shell.</span></span> 
  
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-control-panel"></a><span data-ttu-id="f5565-109">Para mover un usuario mediante el panel de control de Skype empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="f5565-109">To move a user by using the Skype for Business Server 2019 Control Panel</span></span>
  
1. <span data-ttu-id="f5565-110">Inicie sesión en el servidor front-end con una cuenta que sea miembro del grupo RTCUniversalServerAdmins, o del rol administrativo CsAdministrator o CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="f5565-110">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>
    
2. <span data-ttu-id="f5565-111">Abra el **Panel de control de Skype empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="f5565-111">Open **Skype for Business Server Control Panel**.</span></span>
    
3. <span data-ttu-id="f5565-112">Haga clic en **Usuarios**, **Buscar** y, a continuación, en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="f5565-112">Click **Users**, click **Search**, and then click **Find**.</span></span>
    
4. <span data-ttu-id="f5565-113">Seleccione un usuario que quiera mover al grupo de Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="f5565-113">Select a user that you want to move to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="f5565-114">En ste ejemplo, moveremos al usuario Sara Davis.</span><span class="sxs-lookup"><span data-stu-id="f5565-114">In this example, we will move user Sara Davis.</span></span>
    
5. <span data-ttu-id="f5565-115">En el menú  \*\*Acción \*\*, haga clic en  \*\*Mover usuarios seleccionados a un grupo de servidores \*\*.</span><span class="sxs-lookup"><span data-stu-id="f5565-115">On the **Action** menu, select **Move selected users to pool**.</span></span>
    
6. <span data-ttu-id="f5565-116">En la lista desplegable, seleccione el grupo de servidores de Skype empresarial 2019.</span><span class="sxs-lookup"><span data-stu-id="f5565-116">From the drop-down list, select the Skype for Business Server 2019 pool.</span></span>
    
7. <span data-ttu-id="f5565-117">Haga clic en **Acción** y, a continuación, en **Mover usuarios seleccionados a grupo**.</span><span class="sxs-lookup"><span data-stu-id="f5565-117">Click **Action**, and then click **Move selected users to pool**.</span></span> <span data-ttu-id="f5565-118">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f5565-118">Click **OK**.</span></span>
  
8. <span data-ttu-id="f5565-119">Compruebe que la columna **grupo de registradores** para el usuario contiene ahora el grupo de servidores de Skype empresarial Server 2019, que indica que el usuario se ha movido correctamente.</span><span class="sxs-lookup"><span data-stu-id="f5565-119">Verify that the **Registrar pool** column for the user now contains the Skype for Business Server 2019 pool, which indicates that the user has been successfully moved.</span></span> 
    
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="f5565-120">Para mover un usuario mediante el shell de administración de Skype empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="f5565-120">To move a user by using the Skype for Business Server 2019 Management Shell</span></span>

1. <span data-ttu-id="f5565-121">Abra el shell de administración de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="f5565-121">Open the Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="f5565-122">En la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f5565-122">At the command line, type the following:</span></span> 
    
   ```PowerShell
   Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"
   ```

3. <span data-ttu-id="f5565-123">A continuación, en la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f5565-123">Next, at the command line, type the following:</span></span> 
    
   ```PowerShell
   Get-CsUser -Identity "David Pelton"
   ```

4. <span data-ttu-id="f5565-124">La identidad **RegistrarPool** ahora apunta al grupo de servidores de Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="f5565-124">The **RegistrarPool** identity now points to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="f5565-125">La presencia de esta identidad confirma que se movió al usuario correctamente.</span><span class="sxs-lookup"><span data-stu-id="f5565-125">The presence of this identity confirms that the user has been successfully moved.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="f5565-126">Para obtener más información sobre el cmdlet **Get-CsUser** , ejecute: **Get-Help Get-CsUser-Detailed**</span><span class="sxs-lookup"><span data-stu-id="f5565-126">For details about the **Get-CsUser** cmdlet, run: **Get-Help Get-CsUser -Detailed**</span></span>
  

