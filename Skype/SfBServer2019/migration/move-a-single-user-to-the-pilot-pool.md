---
title: Mover un usuario único para el grupo piloto
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Puede mover un usuario de su grupo heredado a su Skype para Business Server 2019 grupo piloto con Skype para el Panel de Control de Business Server 2019 o Skype para Shell de administración de Business Server 2019. En el ejemplo siguiente, en la columna grupo de registrador, pool01.contoso.net es el grupo heredado y todos los seis de estos usuarios están conectados a este grupo de servidores. Use los siguientes procedimientos para mover un usuario a su Skype para grupo de negocio Server 2019 mediante Skype para el Panel de Control de Business Server 2019 y Skype para Shell de administración de servidor empresarial.
ms.openlocfilehash: 94896ce2ea05a3102d5a7643e3f26430e74bfe19
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30880252"
---
# <a name="move-a-single-user-to-the-pilot-pool"></a><span data-ttu-id="cf000-105">Mover un usuario único para el grupo piloto</span><span class="sxs-lookup"><span data-stu-id="cf000-105">Move a single user to the pilot pool</span></span>

<span data-ttu-id="cf000-106">Puede mover un usuario de su grupo heredado a su Skype para Business Server 2019 grupo piloto con Skype para el Panel de Control de Business Server 2019 o Skype para Shell de administración de Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="cf000-106">You can move a user from your legacy pool to your Skype for Business Server 2019 pilot pool using Skype for Business Server 2019 Control Panel or Skype for Business Server 2019 Management Shell.</span></span> <span data-ttu-id="cf000-107">En el ejemplo siguiente, en la columna **grupo de registrador** , **pool01.contoso.net** es el grupo heredado y todos los seis de estos usuarios están conectados a este grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="cf000-107">In the example below, in the **Registrar pool** column, **pool01.contoso.net** is the legacy pool, and all six of these users are connected to this pool.</span></span> <span data-ttu-id="cf000-108">Use los siguientes procedimientos para mover un usuario a su Skype para grupo de negocio Server 2019 mediante Skype para el Panel de Control de Business Server 2019 y Skype para Shell de administración de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="cf000-108">Use the following procedures to move a user to your Skype for Business Server 2019 pool using Skype for Business Server 2019 Control Panel and Skype for Business Server Management Shell.</span></span> 
  
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-control-panel"></a><span data-ttu-id="cf000-109">Para mover un usuario mediante el Skype para el Panel de Control de Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="cf000-109">To move a user by using the Skype for Business Server 2019 Control Panel</span></span>
  
1. <span data-ttu-id="cf000-110">Inicie sesión en el servidor front-end con una cuenta que sea miembro del grupo RTCUniversalServerAdmins o miembro del rol administrativo CsAdministrator o CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="cf000-110">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>
    
2. <span data-ttu-id="cf000-111">Abra **Skype para el Panel de Control de servidor empresarial**.</span><span class="sxs-lookup"><span data-stu-id="cf000-111">Open **Skype for Business Server Control Panel**.</span></span>
    
3. <span data-ttu-id="cf000-112">Haga clic en **usuarios**, haga clic en **Buscar**y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="cf000-112">Click **Users**, click **Search**, and then click **Find**.</span></span>
    
4. <span data-ttu-id="cf000-113">Seleccione el usuario que desea mover a la Skype para el grupo de servidores de Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="cf000-113">Select a user that you want to move to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="cf000-114">En este ejemplo, moveremos a Sara Davis.</span><span class="sxs-lookup"><span data-stu-id="cf000-114">In this example, we will move user Sara Davis.</span></span>
    
5. <span data-ttu-id="cf000-115">En el menú **Acción**, seleccione **Mover usuarios seleccionados a grupo**.</span><span class="sxs-lookup"><span data-stu-id="cf000-115">On the **Action** menu, select **Move selected users to pool**.</span></span>
    
6. <span data-ttu-id="cf000-116">En la lista desplegable, seleccione el Skype para el grupo de servidores de Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="cf000-116">From the drop-down list, select the Skype for Business Server 2019 pool.</span></span>
    
7. <span data-ttu-id="cf000-117">Haga clic en **acción**y, a continuación, haga clic en **mover usuarios seleccionados al grupo de servidores**.</span><span class="sxs-lookup"><span data-stu-id="cf000-117">Click **Action**, and then click **Move selected users to pool**.</span></span> <span data-ttu-id="cf000-118">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="cf000-118">Click **OK**.</span></span>
  
8. <span data-ttu-id="cf000-119">Compruebe que la columna **grupo de registrador** para el usuario contiene ahora el Skype para el grupo de Business Server 2019, que indica que el usuario se ha movido correctamente.</span><span class="sxs-lookup"><span data-stu-id="cf000-119">Verify that the **Registrar pool** column for the user now contains the Skype for Business Server 2019 pool, which indicates that the user has been successfully moved.</span></span> 
    
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="cf000-120">Para mover un usuario mediante el Skype para Shell de administración de Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="cf000-120">To move a user by using the Skype for Business Server 2019 Management Shell</span></span>

1. <span data-ttu-id="cf000-121">Abra el Skype para Shell de administración de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="cf000-121">Open the Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="cf000-122">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="cf000-122">At the command line, type the following:</span></span> 
    
   ```
   Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"
   ```

3. <span data-ttu-id="cf000-123">A continuación, en la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="cf000-123">Next, at the command line, type the following:</span></span> 
    
   ```
   Get-CsUser -Identity "David Pelton"
   ```

4. <span data-ttu-id="cf000-124">La identidad de **RegistrarPool** ahora apunta a la Skype para el grupo de servidores de Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="cf000-124">The **RegistrarPool** identity now points to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="cf000-125">La presencia de esta identidad confirma que el usuario se ha movido correctamente.</span><span class="sxs-lookup"><span data-stu-id="cf000-125">The presence of this identity confirms that the user has been successfully moved.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="cf000-126">Para obtener información detallada acerca del cmdlet **Get-CsUser** , ejecute: **Get-Help Get-CsUser-detallada**</span><span class="sxs-lookup"><span data-stu-id="cf000-126">For details about the **Get-CsUser** cmdlet, run: **Get-Help Get-CsUser -Detailed**</span></span>
  

