---
title: Mover varios usuarios al grupo piloto
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Move multiple users to the pilot pool
ms:assetid: 9492797f-2a26-4773-8ad2-97cb53fa68fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688143(v=OCS.15)
ms:contentKeyID: 49733745
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 41c663566605529b25d9890bb31cba462364c813
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756469"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-multiple-users-to-the-pilot-pool"></a><span data-ttu-id="83755-102">Mover varios usuarios al grupo piloto</span><span class="sxs-lookup"><span data-stu-id="83755-102">Move multiple users to the pilot pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="83755-103">_**Última modificación del tema:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="83755-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="83755-104">Puede mover varios usuarios desde el grupo de servidores de Office Communications Server 2007 R2 a su grupo piloto de Lync Server 2013 mediante el panel de control de Lync Server 2013 o el shell de administración de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="83755-104">You can move multiple users from your Office Communications Server 2007 R2 pool to your Lync Server 2013 pilot pool using Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-control-panel"></a><span data-ttu-id="83755-105">Para mover varios usuarios mediante el panel de control de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="83755-105">To move multiple users by using the Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="83755-106">Abra el **Panel de control de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="83755-106">Open **Lync Server Control Panel**.</span></span>

2.  <span data-ttu-id="83755-107">En la pestaña **Búsqueda de usuario**, haga clic en el botón **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="83755-107">From the **User Search** tab, click the **Search** button.</span></span>

3.  <span data-ttu-id="83755-108">A continuación, haga clic en **Agregar filtro**.</span><span class="sxs-lookup"><span data-stu-id="83755-108">Next, click **Add Filter**.</span></span>

4.  <span data-ttu-id="83755-109">Cree un filtro donde el **usuario de servidor Office Communications Server** es igual a **Verdadero**.</span><span class="sxs-lookup"><span data-stu-id="83755-109">Create a filter where **Office Communications Server user** is equal to **True**.</span></span>

5.  <span data-ttu-id="83755-110">Haga clic en **Buscar** para buscar usuarios heredados de Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="83755-110">Click **Find** to search for legacy Office Communications Server 2007 R2 users.</span></span>

6.  <span data-ttu-id="83755-111">Seleccione dos usuarios que desee mover al grupo de servidores de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="83755-111">Select two users that you want to move to the Lync Server 2013 pool.</span></span> <span data-ttu-id="83755-112">En este ejemplo, moveremos los usuarios Chen Yang y Claus Hansen.</span><span class="sxs-lookup"><span data-stu-id="83755-112">In this example, we will move users Chen Yang and Claus Hansen.</span></span>
    
    <span data-ttu-id="83755-113">![Lista de usuarios que se muestra al buscar usuarios de OCS](images/JJ688143.76beb4fa-72e0-41ef-b96e-3553e96645c0(OCS.15).jpg "Lista de usuarios que se muestra al buscar usuarios de OCS")</span><span class="sxs-lookup"><span data-stu-id="83755-113">![User list displayed from searching for OCS users](images/JJ688143.76beb4fa-72e0-41ef-b96e-3553e96645c0(OCS.15).jpg "User list displayed from searching for OCS users")</span></span>  

7.  <span data-ttu-id="83755-114">En el menú **Acción** seleccione **Mover usuarios seleccionados a grupo**.</span><span class="sxs-lookup"><span data-stu-id="83755-114">From the **Action** menu, select **Move selected users to pool**.</span></span>

8.  <span data-ttu-id="83755-115">En la lista desplegable, seleccione el grupo de servidores de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="83755-115">From the drop-down list, select the Lync Server 2013 pool.</span></span>

9.  <span data-ttu-id="83755-116">Haga clic en **Acción** y, a continuación, en **Mover usuarios seleccionados a grupo**.</span><span class="sxs-lookup"><span data-stu-id="83755-116">Click **Action** and then click **Move selected users to pool**.</span></span> <span data-ttu-id="83755-117">Haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="83755-117">Click OK.</span></span>
    
    <span data-ttu-id="83755-118">![Cuadro de diálogo mover usuarios, grupo de registradores de destino](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Cuadro de diálogo mover usuarios, grupo de registradores de destino")</span><span class="sxs-lookup"><span data-stu-id="83755-118">![Move Users, destination registrar pool dialog box](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Move Users, destination registrar pool dialog box")</span></span>  

10. <span data-ttu-id="83755-119">Compruebe que la columna **grupo de registradores** de los usuarios ahora contiene el grupo de servidores de Lync Server 2013, lo que indica que los usuarios se movieron correctamente.</span><span class="sxs-lookup"><span data-stu-id="83755-119">Verify that the **Registrar pool** column for the users now contains the Lync Server 2013 pool, which indicates that the users have been successfully moved.</span></span>

</div>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="83755-120">Para mover varios usuarios mediante el shell de administración de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="83755-120">To move multiple users by using the Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="83755-121">Abra el shell de administración de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="83755-121">Open the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="83755-122">En la línea de comandos, escriba lo siguiente y reemplace **user1** y **user2** por los nombres de usuario específicos que desea mover y reemplazar el \*\* \_ FQDN del grupo\*\* de servidores con el nombre del grupo de servidores de destino.</span><span class="sxs-lookup"><span data-stu-id="83755-122">At the command line, type the following and replace **User1** and **User2** with specific user names you want to move and replace **pool\_FQDN** with the name of the destination pool.</span></span> <span data-ttu-id="83755-123">En este ejemplo, moveremos los usuarios Hao Chen y Katie Jordan:</span><span class="sxs-lookup"><span data-stu-id="83755-123">In this example we will move users Hao Chen and Katie Jordan.</span></span>
    
        Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsLegacyUser -Target "pool_FQDN"
    
    <span data-ttu-id="83755-124">![Cmdlet de ejemplo para mover un usuario heredado](images/JJ688143.57cfc28e-3df5-459f-83ef-8b0edf182a25(OCS.15).jpg "Cmdlet de ejemplo para mover un usuario heredado")</span><span class="sxs-lookup"><span data-stu-id="83755-124">![Example cmdlet to move a legacy user](images/JJ688143.57cfc28e-3df5-459f-83ef-8b0edf182a25(OCS.15).jpg "Example cmdlet to move a legacy user")</span></span>  

3.  <span data-ttu-id="83755-125">En la línea de comandos, escriba lo siguiente</span><span class="sxs-lookup"><span data-stu-id="83755-125">At the command line, type the following</span></span>
    
        Get-CsUser -Identity "User1"

4.  <span data-ttu-id="83755-126">La identidad del **grupo de registrador** ahora debe apuntar al grupo especificado como \*\* \_ FQDN del grupo\*\* de servidores en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="83755-126">The **Registrar Pool** identity should now point to the pool you specified as **pool\_FQDN** in the previous step.</span></span> <span data-ttu-id="83755-127">La presencia de esta identidad confirma que se ha movido correctamente al usuario.</span><span class="sxs-lookup"><span data-stu-id="83755-127">The presence of this identity confirms that the user has been successfully moved.</span></span> <span data-ttu-id="83755-128">Repita el paso para comprobar que se ha movido a **User2**.</span><span class="sxs-lookup"><span data-stu-id="83755-128">Repeat step to verify **User2** has been moved.</span></span>
    
    <span data-ttu-id="83755-129">![Resultado del cmdlet PowerShell Get-UsUser-Identity](images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "Resultado del cmdlet PowerShell Get-UsUser-Identity")</span><span class="sxs-lookup"><span data-stu-id="83755-129">![Output of PowerShell Get-UsUser -Identity cmdlet](images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "Output of PowerShell Get-UsUser -Identity  cmdlet")</span></span>  

</div>

<div>

## <a name="to-move-all-users-at-the-same-time-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="83755-130">Para mover todos los usuarios al mismo tiempo mediante el shell de administración de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="83755-130">To move all users at the same time by using the Lync Server 2013 Management Shell</span></span>

<span data-ttu-id="83755-131">En este ejemplo, todos los usuarios se han devuelto al grupo de Office Communications Server 2007 R2 (pool01.contoso.net).</span><span class="sxs-lookup"><span data-stu-id="83755-131">In this example, all users have been returned to the Office Communications Server 2007 R2 pool (pool01.contoso.net).</span></span> <span data-ttu-id="83755-132">Mediante el shell de administración de Lync Server 2013, todos los usuarios se moverán al mismo tiempo al grupo de servidores de Lync Server 2013 (pool02.contoso.net).</span><span class="sxs-lookup"><span data-stu-id="83755-132">Using the Lync Server 2013 Management Shell, we will move all users at the same time to the Lync Server 2013 pool (pool02.contoso.net).</span></span>

1.  <span data-ttu-id="83755-133">Abra el **Shell de administración de Lync Server 2013**.</span><span class="sxs-lookup"><span data-stu-id="83755-133">Open the **Lync Server 2013 Management Shell**.</span></span>

2.  <span data-ttu-id="83755-134">Escriba lo siguiente en la línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="83755-134">At the command line, type the following:</span></span>
    
        Get-CsUser -OnOfficeCommunicationServer | Move-CsLegacyUser -Target "pool_FQDN"
    
    <span data-ttu-id="83755-135">![Cmdlet de ejemplo para mover todos los usuarios heredados de un grupo de servidores](images/JJ688143.e6a2d578-296e-476c-bd45-d757917ea853(OCS.15).jpg "Cmdlet de ejemplo para mover todos los usuarios heredados de un grupo de servidores")</span><span class="sxs-lookup"><span data-stu-id="83755-135">![Example cmdlet to move all legacy users in a pool](images/JJ688143.e6a2d578-296e-476c-bd45-d757917ea853(OCS.15).jpg "Example cmdlet to move all legacy users in a pool")</span></span>  

3.  <span data-ttu-id="83755-136">A continuación, ejecute **Get-CsUser** para uno de los usuarios piloto.</span><span class="sxs-lookup"><span data-stu-id="83755-136">Next, run **Get-CsUser** for one of the pilot users.</span></span>
    
        Get-CsUser -Identity "Hao Chen"

4.  <span data-ttu-id="83755-137">La identidad del **grupo de registradores** para cada usuario apunta ahora al grupo especificado como " \_ FQDN del grupo de servidores" en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="83755-137">The **Registrar Pool** identity for each user now points to the pool you specified as “pool\_FQDN” in the previous step.</span></span> <span data-ttu-id="83755-138">La presencia de esta identidad confirma que se movió al usuario correctamente.</span><span class="sxs-lookup"><span data-stu-id="83755-138">The presence of this identity confirms that the user has been successfully moved.</span></span>

5.  <span data-ttu-id="83755-139">Además, podemos ver la lista de usuarios en el panel de control de Lync Server 2013 y comprobar que el valor del grupo de registradores ahora apunta al grupo de servidores de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="83755-139">Additionally, we can view the list of users in the Lync Server 2013 Control Panel and verify that the Registrar Pool value now points to the Lync Server 2013 pool.</span></span>
    
    <span data-ttu-id="83755-140">![Lista de usuarios del panel de control 2013 de Lync Server](images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Lista de usuarios del panel de control 2013 de Lync Server")</span><span class="sxs-lookup"><span data-stu-id="83755-140">![Lync Server 2013 Control Panel user list](images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Lync Server 2013 Control Panel user list")</span></span>  

</div>

</div>

<span> </span>

</div>

</div>

</div>

