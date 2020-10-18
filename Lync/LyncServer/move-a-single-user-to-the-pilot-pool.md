---
title: Mover un solo usuario al grupo piloto
description: Mover un solo usuario al grupo piloto.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Move a single user to the pilot pool
ms:assetid: e9de81a8-40dd-4446-81e7-a2b810eaea50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205401(v=OCS.15)
ms:contentKeyID: 48185905
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f5f7396ed2d92c7015f01ff6cd6e90fd3998219d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574736"
---
# <a name="move-a-single-user-to-the-pilot-pool"></a><span data-ttu-id="0b4f4-103">Mover un solo usuario al grupo piloto</span><span class="sxs-lookup"><span data-stu-id="0b4f4-103">Move a single user to the pilot pool</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0b4f4-104">_**Última modificación del tema:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="0b4f4-104">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="0b4f4-105">Puede mover un usuario de su grupo de servidores de Lync Server 2010 al grupo piloto de Lync Server 2013 mediante el panel de control de Lync Server 2013 o el shell de administración de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0b4f4-105">You can move a user from your Lync Server 2010 pool to your Lync Server 2013 pilot pool using Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="0b4f4-106">En el ejemplo siguiente, en la columna de grupo de registrador, **pool01.contoso.net** es el grupo de servidores de Lync Server 2010 y los seis usuarios están conectados a este grupo.</span><span class="sxs-lookup"><span data-stu-id="0b4f4-106">In the example below, in the Registrar pool column, **pool01.contoso.net** is the Lync Server 2010 pool, and all six of these users are connected to this pool.</span></span> <span data-ttu-id="0b4f4-107">Use los siguientes procedimientos para mover un usuario al grupo de servidores de Lync Server 2013 mediante el panel de control de Lync Server 2013 y el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0b4f4-107">Use the following procedures to move a user to your Lync Server 2013 pool using Lync Server 2013 Control Panel and Lync Server Management Shell.</span></span>

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-control-panel"></a><span data-ttu-id="0b4f4-108">Para mover un usuario mediante el panel de control de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0b4f4-108">To move a user by using the Lync Server 2013 Control Panel</span></span>

<span data-ttu-id="0b4f4-109">**Lista de usuarios en el panel de control de Lync Server 2013**</span><span class="sxs-lookup"><span data-stu-id="0b4f4-109">**List of users in the Lync Server 2013 Control Panel**</span></span>

<span data-ttu-id="0b4f4-110">![Panel de control de Lync Server, cuadro de diálogo mover usuario](images/JJ721870.a2bce284-0392-4db3-9bb2-9f12699738e7(OCS.15).jpg "Panel de control de Lync Server, cuadro de diálogo mover usuario")</span><span class="sxs-lookup"><span data-stu-id="0b4f4-110">![Lync Server Control Panel, Move User dialog](images/JJ721870.a2bce284-0392-4db3-9bb2-9f12699738e7(OCS.15).jpg "Lync Server Control Panel, Move User dialog")</span></span>

1.  <span data-ttu-id="0b4f4-111">Inicie sesión en el servidor front-end con una cuenta que sea miembro del grupo RTCUniversalServerAdmins o miembro del rol administrativo CsAdministrator o CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="0b4f4-111">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>

2.  <span data-ttu-id="0b4f4-112">Abrir **Panel de control de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="0b4f4-112">Open **Lync Server Control Panel**.</span></span>

3.  <span data-ttu-id="0b4f4-113">Haga clic en **Usuarios**, Buscar y **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="0b4f4-113">Click **Users**, click Search, and then click **Find**.</span></span>

4.  <span data-ttu-id="0b4f4-114">Seleccione un usuario que quiera mover al grupo de servidores de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0b4f4-114">Select a user that you want to move to the Lync Server 2013 pool.</span></span> <span data-ttu-id="0b4f4-115">En ste ejemplo, moveremos al usuario Sara Davis.</span><span class="sxs-lookup"><span data-stu-id="0b4f4-115">In this example, we will move user Sara Davis.</span></span>

5.  <span data-ttu-id="0b4f4-116">En el menú  \*\*Acción \*\*, haga clic en  \*\*Mover usuarios seleccionados a un grupo de servidores \*\*.</span><span class="sxs-lookup"><span data-stu-id="0b4f4-116">On the **Action** menu, select **Move selected users to pool**.</span></span>

6.  <span data-ttu-id="0b4f4-117">En la lista desplegable, seleccione el grupo de servidores de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0b4f4-117">From the drop-down list, select the Lync Server 2013 pool.</span></span>

7.  <span data-ttu-id="0b4f4-118">Haga clic en **Acción** y, a continuación, en **Mover usuarios seleccionados a grupo**.</span><span class="sxs-lookup"><span data-stu-id="0b4f4-118">Click **Action** and then click **Move selected users to pool**.</span></span> <span data-ttu-id="0b4f4-119">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0b4f4-119">Click **OK**.</span></span>
    
    <span data-ttu-id="0b4f4-120">![Cuadro de diálogo mover usuarios, grupo de registradores de destino](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Cuadro de diálogo mover usuarios, grupo de registradores de destino")</span><span class="sxs-lookup"><span data-stu-id="0b4f4-120">![Move Users, destination registrar pool dialog box](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Move Users, destination registrar pool dialog box")</span></span>  

8.  <span data-ttu-id="0b4f4-121">Compruebe que la columna **grupo de registradores** del usuario contiene ahora el grupo de servidores de Lync Server 2013, lo que indica que el usuario se movió correctamente.</span><span class="sxs-lookup"><span data-stu-id="0b4f4-121">Verify that the **Registrar pool** column for the user now contains the Lync Server 2013 pool, which indicates that the user has been successfully moved.</span></span>

</div>

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="0b4f4-122">Para mover un usuario mediante el shell de administración de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0b4f4-122">To move a user by using the Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="0b4f4-123">Abra el Shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0b4f4-123">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="0b4f4-124">En la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0b4f4-124">At the command line, type the following:</span></span>
    
        Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"

3.  <span data-ttu-id="0b4f4-125">A continuación, en la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0b4f4-125">Next, at the command line, type the following:</span></span>
    
        Get-CsUser -Identity "David Pelton"

4.  <span data-ttu-id="0b4f4-126">La identidad **RegistrarPool** ahora apunta al grupo de servidores de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="0b4f4-126">The **RegistrarPool** identity now points to the Lync Server 2013 pool.</span></span> <span data-ttu-id="0b4f4-127">La presencia de esta identidad confirma que se movió al usuario correctamente.</span><span class="sxs-lookup"><span data-stu-id="0b4f4-127">The presence of this identity confirms that the user has been successfully moved.</span></span>
    
    <span data-ttu-id="0b4f4-128">![Resultado de Get-CsUser cmdlet con el filtro de identidad](images/JJ205401.bc5d4672-8068-4475-b882-dbd305c801a9(OCS.15).jpg "Resultado de Get-CsUser cmdlet con el filtro de identidad")</span><span class="sxs-lookup"><span data-stu-id="0b4f4-128">![Output from Get-CsUser cmdlet with Identity filter](images/JJ205401.bc5d4672-8068-4475-b882-dbd305c801a9(OCS.15).jpg "Output from Get-CsUser cmdlet with Identity filter")</span></span>  
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0b4f4-129">Para obtener detalles acerca del cmdlet <STRONG>Get-CsUser</STRONG>, ejecute: <STRONG>Get-Help Get-CsUser –Detailed</STRONG></span><span class="sxs-lookup"><span data-stu-id="0b4f4-129">For details about the <STRONG>Get-CsUser</STRONG> cmdlet, run: <STRONG>Get-Help Get-CsUser –Detailed</STRONG></span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

