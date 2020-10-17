---
title: Mover varios usuarios al grupo piloto
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Move multiple users to the pilot pool
ms:assetid: 90d0590c-922c-4933-b778-9dd850b59310
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205096(v=OCS.15)
ms:contentKeyID: 48184838
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be7fd473b858c6a35b23f8aaa0c525875218d3f7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500237"
---
# <a name="move-multiple-users-to-the-pilot-pool"></a><span data-ttu-id="5941d-102">Mover varios usuarios al grupo piloto</span><span class="sxs-lookup"><span data-stu-id="5941d-102">Move multiple users to the pilot pool</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5941d-103">_**Última modificación del tema:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="5941d-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="5941d-104">Puede mover varios usuarios de su grupo de servidores de Lync Server 2010 a su grupo piloto de Lync Server 2013 mediante el panel de control de Lync Server 2013 o el shell de administración de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5941d-104">You can move multiple users from your Lync Server 2010 pool to your Lync Server 2013 pilot pool using Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-control-panel"></a><span data-ttu-id="5941d-105">Para mover varios usuarios mediante el panel de control de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5941d-105">To move multiple users by using the Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="5941d-106">Abra el **Panel de control de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="5941d-106">Open **Lync Server Control Panel**.</span></span>

2.  <span data-ttu-id="5941d-107">Haga clic en **Usuarios**, Buscar y **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="5941d-107">Click **Users**, click Search, and then click **Find**.</span></span>

3.  <span data-ttu-id="5941d-108">Seleccione dos usuarios que desee mover al grupo de servidores de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5941d-108">Select two users that you want to move to the Lync Server 2013 pool.</span></span> <span data-ttu-id="5941d-109">En este ejemplo, moveremos los usuarios Chen Yang y Claus Hansen.</span><span class="sxs-lookup"><span data-stu-id="5941d-109">In this example, we will move users Chen Yang and Claus Hansen.</span></span>
    
    <span data-ttu-id="5941d-110">![Mover usuarios a un grupo de registros específico](images/JJ205096.70d510e1-8e6b-40a5-a80b-27cbc63fc337(OCS.15).jpg "Mover usuarios a un grupo de registros específico")</span><span class="sxs-lookup"><span data-stu-id="5941d-110">![Move users to specific register pool](images/JJ205096.70d510e1-8e6b-40a5-a80b-27cbc63fc337(OCS.15).jpg "Move users to specific register pool")</span></span>  

4.  <span data-ttu-id="5941d-111">En el menú **Acción** seleccione **Mover usuarios seleccionados a grupo**.</span><span class="sxs-lookup"><span data-stu-id="5941d-111">From the **Action** menu, select **Move selected users to pool**.</span></span>

5.  <span data-ttu-id="5941d-112">En la lista desplegable, seleccione el grupo de servidores de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5941d-112">From the drop-down list, select the Lync Server 2013 pool.</span></span>

6.  <span data-ttu-id="5941d-113">Haga clic en **Acción** y, a continuación, en **Mover usuarios seleccionados a grupo**.</span><span class="sxs-lookup"><span data-stu-id="5941d-113">Click **Action** and then click **Move selected users to pool**.</span></span> <span data-ttu-id="5941d-114">Haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="5941d-114">Click OK.</span></span>
    
    <span data-ttu-id="5941d-115">![Cuadro de diálogo mover usuarios, grupo de registradores de destino](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Cuadro de diálogo mover usuarios, grupo de registradores de destino")</span><span class="sxs-lookup"><span data-stu-id="5941d-115">![Move Users, destination registrar pool dialog box](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Move Users, destination registrar pool dialog box")</span></span>  

7.  <span data-ttu-id="5941d-116">Compruebe que la columna **grupo de registradores** de los usuarios ahora contiene el grupo de servidores de Lync Server 2013, lo que indica que los usuarios se movieron correctamente.</span><span class="sxs-lookup"><span data-stu-id="5941d-116">Verify that the **Registrar pool** column for the users now contains the Lync Server 2013 pool, which indicates that the users have been successfully moved.</span></span>

</div>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="5941d-117">Para mover varios usuarios mediante el shell de administración de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5941d-117">To move multiple users by using the Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="5941d-118">Abra el shell de administración de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5941d-118">Open the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="5941d-119">En la línea de comandos, escriba lo siguiente y reemplace **user1** y **user2** por los nombres de usuario específicos que desea mover y reemplazar el \*\* \_ FQDN del grupo\*\* de servidores con el nombre del grupo de servidores de destino.</span><span class="sxs-lookup"><span data-stu-id="5941d-119">At the command line, type the following and replace **User1** and **User2** with specific user names you want to move and replace **pool\_FQDN** with the name of the destination pool.</span></span> <span data-ttu-id="5941d-120">En este ejemplo, moveremos los usuarios Hao Chen y Katie Jordan:</span><span class="sxs-lookup"><span data-stu-id="5941d-120">In this example we will move users Hao Chen and Katie Jordan.</span></span>
    
        Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
    
    <span data-ttu-id="5941d-121">![Ejemplo de cmdlet de Get-CsUser de PowerShell](images/JJ205096.767ff9fc-755d-4a80-a710-5b1367aecbe0(OCS.15).jpg "Ejemplo de cmdlet de Get-CsUser de PowerShell")</span><span class="sxs-lookup"><span data-stu-id="5941d-121">![Example of PowerShell Get-CsUser cmdlet](images/JJ205096.767ff9fc-755d-4a80-a710-5b1367aecbe0(OCS.15).jpg "Example of PowerShell Get-CsUser cmdlet")</span></span>  

3.  <span data-ttu-id="5941d-122">En la línea de comandos, escriba lo siguiente</span><span class="sxs-lookup"><span data-stu-id="5941d-122">At the command line, type the following</span></span>
    
        Get-CsUser -Identity "User1"

4.  <span data-ttu-id="5941d-123">La identidad del **grupo de registrador** ahora debe apuntar al grupo especificado como \*\* \_ FQDN del grupo\*\* de servidores en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="5941d-123">The **Registrar Pool** identity should now point to the pool you specified as **pool\_FQDN** in the previous step.</span></span> <span data-ttu-id="5941d-124">La presencia de esta identidad confirma que se ha movido correctamente al usuario.</span><span class="sxs-lookup"><span data-stu-id="5941d-124">The presence of this identity confirms that the user has been successfully moved.</span></span> <span data-ttu-id="5941d-125">Repita el paso para comprobar que se ha movido a **User2**.</span><span class="sxs-lookup"><span data-stu-id="5941d-125">Repeat step to verify **User2** has been moved.</span></span>
    
    <span data-ttu-id="5941d-126">![Resultado del cmdlet Get-UsUser de identidad de PowerShell](images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "Resultado del cmdlet Get-UsUser de identidad de PowerShell")</span><span class="sxs-lookup"><span data-stu-id="5941d-126">![Output of PowerShell Get-UsUser -Identity cmdlet](images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "Output of PowerShell Get-UsUser -Identity  cmdlet")</span></span>  

</div>

<div>

## <a name="to-move-all-users-at-the-same-time-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="5941d-127">Para mover todos los usuarios al mismo tiempo mediante el shell de administración de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5941d-127">To move all users at the same time by using the Lync Server 2013 Management Shell</span></span>

<span data-ttu-id="5941d-128">En este ejemplo, todos los usuarios se han devuelto al grupo de servidores de Lync Server 2010 (pool01.contoso.net).</span><span class="sxs-lookup"><span data-stu-id="5941d-128">In this example, all users have been returned to the Lync Server 2010 pool (pool01.contoso.net).</span></span> <span data-ttu-id="5941d-129">Mediante el shell de administración de Lync Server 2013, todos los usuarios se moverán al mismo tiempo al grupo de servidores de Lync Server 2013 (pool02.contoso.net).</span><span class="sxs-lookup"><span data-stu-id="5941d-129">Using the Lync Server 2013 Management Shell, we will move all users at the same time to the Lync Server 2013 pool (pool02.contoso.net).</span></span>

1.  <span data-ttu-id="5941d-130">Abra el **Shell de administración de Lync Server 2013**.</span><span class="sxs-lookup"><span data-stu-id="5941d-130">Open the **Lync Server 2013 Management Shell**.</span></span>

2.  <span data-ttu-id="5941d-131">Escriba lo siguiente en la línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="5941d-131">At the command line, type the following:</span></span>
    
        Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
    
    <span data-ttu-id="5941d-132">![Cmdlet de PowerShell y resultados en Shell de administración](images/JJ205096.1e57ccb1-9378-4dc7-82b7-dcaa63a285c6(OCS.15).png "Cmdlet de PowerShell y resultados en Shell de administración")</span><span class="sxs-lookup"><span data-stu-id="5941d-132">![PowerShell cmdlet and results in Management Shell](images/JJ205096.1e57ccb1-9378-4dc7-82b7-dcaa63a285c6(OCS.15).png "PowerShell cmdlet and results in Management Shell")</span></span>  

3.  <span data-ttu-id="5941d-133">A continuación, ejecute **Get-CsUser** para uno de los usuarios piloto.</span><span class="sxs-lookup"><span data-stu-id="5941d-133">Next, run **Get-CsUser** for one of the pilot users.</span></span>
    
        Get-CsUser -Identity "Hao Chen"

4.  <span data-ttu-id="5941d-134">La identidad del **grupo de registradores** para cada usuario apunta ahora al grupo especificado como " \_ FQDN del grupo de servidores" en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="5941d-134">The **Registrar Pool** identity for each user now points to the pool you specified as “pool\_FQDN” in the previous step.</span></span> <span data-ttu-id="5941d-135">La presencia de esta identidad confirma que se movió al usuario correctamente.</span><span class="sxs-lookup"><span data-stu-id="5941d-135">The presence of this identity confirms that the user has been successfully moved.</span></span>

5.  <span data-ttu-id="5941d-136">Además, podemos ver la lista de usuarios en el panel de control de Lync Server 2013 y comprobar que el valor del grupo de registradores ahora apunta al grupo de servidores de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5941d-136">Additionally, we can view the list of users in the Lync Server 2013 Control Panel and verify that the Registrar Pool value now points to the Lync Server 2013 pool.</span></span>
    
    <span data-ttu-id="5941d-137">![Lista de usuarios del panel de control 2013 de Lync Server](images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Lista de usuarios del panel de control 2013 de Lync Server")</span><span class="sxs-lookup"><span data-stu-id="5941d-137">![Lync Server 2013 Control Panel user list](images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Lync Server 2013 Control Panel user list")</span></span>  

</div>

</div>

<span> </span>

</div>

</div>

</div>

