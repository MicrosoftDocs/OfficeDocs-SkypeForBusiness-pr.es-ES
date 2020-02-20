---
title: Mover un solo usuario al grupo piloto
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Move a single user to the pilot pool
ms:assetid: 80d5b365-f153-4c61-a148-f9e18ce6e027
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688109(v=OCS.15)
ms:contentKeyID: 49733708
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7320f55b88786ccf4e1a1a26c28483f3ccbd7d77
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148679"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-a-single-user-to-the-pilot-pool"></a><span data-ttu-id="1cfbe-102">Mover un solo usuario al grupo piloto</span><span class="sxs-lookup"><span data-stu-id="1cfbe-102">Move a single user to the pilot pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1cfbe-103">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="1cfbe-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="1cfbe-104">Puede mover un usuario del grupo de servidores de Office Communications Server 2007 R2 a su grupo piloto de Lync Server 2013 mediante el panel de control de Lync Server 2013 o el shell de administración de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1cfbe-104">You can move a user from your Office Communications Server 2007 R2 pool to your Lync Server 2013 pilot pool using Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="1cfbe-105">En el ejemplo siguiente, en la columna de grupo de registrador, \*\* \<Office Communications Server\> \*\* es el grupo de Office Communications Server 2007 R2 y los seis usuarios están conectados a este grupo.</span><span class="sxs-lookup"><span data-stu-id="1cfbe-105">In the example below, in the Registrar pool column, **\<Office Communications Server\>** is the Office Communications Server 2007 R2 pool, and all six of these users are connected to this pool.</span></span> <span data-ttu-id="1cfbe-106">Use los siguientes procedimientos para mover un usuario al grupo de servidores de Lync Server 2013 mediante el panel de control de Lync Server 2013 y el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1cfbe-106">Use the following procedures to move a user to your Lync Server 2013 pool using Lync Server 2013 Control Panel and Lync Server Management Shell.</span></span>

<span data-ttu-id="1cfbe-107">![Buscar usuarios de OCS en el panel de control de Lync Server](images/JJ688109.d2008fd6-868b-4f26-84cf-57bb69e073d3(OCS.15).jpg "Buscar usuarios de OCS en el panel de control de Lync Server")</span><span class="sxs-lookup"><span data-stu-id="1cfbe-107">![Search for OCS users in Lync Server Control Panel](images/JJ688109.d2008fd6-868b-4f26-84cf-57bb69e073d3(OCS.15).jpg "Search for OCS users in Lync Server Control Panel")</span></span>

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-control-panel"></a><span data-ttu-id="1cfbe-108">Para mover un usuario mediante el panel de control de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1cfbe-108">To move a user by using the Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="1cfbe-109">Inicie sesión en el servidor front-end con una cuenta que sea miembro del grupo RTCUniversalServerAdmins, o del rol administrativo CsAdministrator o CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="1cfbe-109">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>

2.  <span data-ttu-id="1cfbe-110">Abrir Panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1cfbe-110">Open Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="1cfbe-111">Haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="1cfbe-111">Click **Users**.</span></span>

4.  <span data-ttu-id="1cfbe-112">Desde la pestaña **Búsqueda de usuarios** haga clic en el botón **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="1cfbe-112">From the **User Search** tab, click the **Search** button.</span></span>

5.  <span data-ttu-id="1cfbe-113">A continuación, haga clic en **Agregar filtro**.</span><span class="sxs-lookup"><span data-stu-id="1cfbe-113">Next, click **Add Filter**.</span></span>

6.  <span data-ttu-id="1cfbe-114">Cree un filtro donde el **usuario de servidor Office Communications Server** es igual a **Verdadero**.</span><span class="sxs-lookup"><span data-stu-id="1cfbe-114">Create a filter where **Office Communications Server user** is equal to **True**.</span></span>

7.  <span data-ttu-id="1cfbe-115">Haga clic en **Buscar** para buscar usuarios heredados de Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="1cfbe-115">Click **Find** to search for legacy Office Communications Server 2007 R2 users.</span></span>
    
    <span data-ttu-id="1cfbe-116">![Buscar usuarios de OCS en el panel de control de Lync Server](images/JJ688109.09528349-7915-41e1-91b4-6ab5c12b1b38(OCS.15).jpg "Buscar usuarios de OCS en el panel de control de Lync Server")</span><span class="sxs-lookup"><span data-stu-id="1cfbe-116">![Search for OCS users in Lync Server Control Panel](images/JJ688109.09528349-7915-41e1-91b4-6ab5c12b1b38(OCS.15).jpg "Search for OCS users in Lync Server Control Panel")</span></span>  

8.  <span data-ttu-id="1cfbe-117">Seleccione un usuario que quiera mover al grupo de servidores de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1cfbe-117">Select a user that you want to move to the Lync Server 2013 pool.</span></span> <span data-ttu-id="1cfbe-118">En ste ejemplo, moveremos al usuario Sara Davis.</span><span class="sxs-lookup"><span data-stu-id="1cfbe-118">In this example, we will move user Sara Davis.</span></span>

9.  <span data-ttu-id="1cfbe-119">En el menú  \*\*Acción \*\*, haga clic en  \*\*Mover usuarios seleccionados a un grupo de servidores \*\*.</span><span class="sxs-lookup"><span data-stu-id="1cfbe-119">On the **Action** menu, select **Move selected users to pool**.</span></span>

10. <span data-ttu-id="1cfbe-120">En la lista desplegable, seleccione el grupo de servidores de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1cfbe-120">From the drop-down list, select the Lync Server 2013 pool.</span></span>

11. <span data-ttu-id="1cfbe-121">Haga clic en **Acción** y, a continuación, en **Mover usuarios seleccionados a grupo**.</span><span class="sxs-lookup"><span data-stu-id="1cfbe-121">Click **Action** and then click **Move selected users to pool**.</span></span> <span data-ttu-id="1cfbe-122">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1cfbe-122">Click **OK**.</span></span>
    
    <span data-ttu-id="1cfbe-123">![Configuración del grupo de servidores de destino en el cuadro de diálogo mover usuarios](images/JJ688109.d7dc0759-87c5-4c23-938f-361576621504(OCS.15).jpg "Configuración del grupo de servidores de destino en el cuadro de diálogo mover usuarios")</span><span class="sxs-lookup"><span data-stu-id="1cfbe-123">![Setting the Destination pool in Move Users dialog](images/JJ688109.d7dc0759-87c5-4c23-938f-361576621504(OCS.15).jpg "Setting the Destination pool in Move Users dialog")</span></span>  

12. <span data-ttu-id="1cfbe-124">Compruebe que la columna **grupo de registradores** para el usuario contiene ahora el grupo de servidores de Lync Server 2013, que indica que el usuario se movió correctamente</span><span class="sxs-lookup"><span data-stu-id="1cfbe-124">Verify that the **Registrar pool** column for the user now contains the Lync Server 2013 pool, which indicates that the user has been successfully moved</span></span>

</div>

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="1cfbe-125">Para mover un usuario mediante el shell de administración de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1cfbe-125">To move a user by using the Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="1cfbe-126">Abra el Shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1cfbe-126">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="1cfbe-127">En la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1cfbe-127">At the command line, type the following:</span></span>
    
        Move-CsLegacyUser -Identity "David Pelton" -Target "pool02.contoso.net"

3.  <span data-ttu-id="1cfbe-128">A continuación, en la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1cfbe-128">Next, at the command line, type the following:</span></span>
    
        Get-CsUser -Identity "David Pelton"

4.  <span data-ttu-id="1cfbe-129">La identidad **RegistrarPool** ahora apunta al grupo de servidores de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="1cfbe-129">The **RegistrarPool** identity now points to the Lync Server 2013 pool.</span></span> <span data-ttu-id="1cfbe-130">La presencia de esta identidad confirma que se movió al usuario correctamente.</span><span class="sxs-lookup"><span data-stu-id="1cfbe-130">The presence of this identity confirms that the user has been successfully moved.</span></span>
    
    <span data-ttu-id="1cfbe-131">![Resultado del cmdlet Get-CsUser con el filtro de identidad](images/JJ205401.bc5d4672-8068-4475-b882-dbd305c801a9(OCS.15).jpg "Resultado del cmdlet Get-CsUser con el filtro de identidad")</span><span class="sxs-lookup"><span data-stu-id="1cfbe-131">![Output from Get-CsUser cmdlet with Identity filter](images/JJ205401.bc5d4672-8068-4475-b882-dbd305c801a9(OCS.15).jpg "Output from Get-CsUser cmdlet with Identity filter")</span></span>  
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1cfbe-132">Para obtener detalles acerca del cmdlet <STRONG>Get-CsUser</STRONG>, ejecute: <STRONG>Get-Help Get-CsUser –Detailed</STRONG></span><span class="sxs-lookup"><span data-stu-id="1cfbe-132">For details about the <STRONG>Get-CsUser</STRONG> cmdlet, run: <STRONG>Get-Help Get-CsUser –Detailed</STRONG></span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

