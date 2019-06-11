---
title: Mover un solo usuario a la agrupación piloto
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Move a single user to the pilot pool
ms:assetid: 80d5b365-f153-4c61-a148-f9e18ce6e027
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688109(v=OCS.15)
ms:contentKeyID: 49733708
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 086af622644f8d8285ef5f7be8e17f75ff436000
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849946"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-a-single-user-to-the-pilot-pool"></a><span data-ttu-id="18f5a-102">Mover un solo usuario a la agrupación piloto</span><span class="sxs-lookup"><span data-stu-id="18f5a-102">Move a single user to the pilot pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="18f5a-103">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="18f5a-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="18f5a-104">Puede mover un usuario del grupo de Office Communications Server 2007 R2 a su grupo de pruebas piloto de Lync Server 2013 mediante el panel de control de Lync Server 2013 o el shell de administración de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="18f5a-104">You can move a user from your Office Communications Server 2007 R2 pool to your Lync Server 2013 pilot pool using Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="18f5a-105">En el ejemplo siguiente, en la columna registrar grupo, \*\* \<Office Communications Server\> \*\* es el grupo de Office Communications Server 2007 R2 y todos los seis de estos usuarios están conectados a este grupo.</span><span class="sxs-lookup"><span data-stu-id="18f5a-105">In the example below, in the Registrar pool column, **\<Office Communications Server\>** is the Office Communications Server 2007 R2 pool, and all six of these users are connected to this pool.</span></span> <span data-ttu-id="18f5a-106">Use los procedimientos siguientes para mover un usuario a su grupo de servidores de Lync Server 2013 con el panel de control de Lync Server 2013 y el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="18f5a-106">Use the following procedures to move a user to your Lync Server 2013 pool using Lync Server 2013 Control Panel and Lync Server Management Shell.</span></span>

<span data-ttu-id="18f5a-107">![Buscar usuarios de OCS en el panel de control de Lync Server] (images/JJ688109.d2008fd6-868b-4f26-84cf-57bb69e073d3(OCS.15).jpg "Buscar usuarios de OCS en el panel de control de Lync Server")</span><span class="sxs-lookup"><span data-stu-id="18f5a-107">![Search for OCS users in Lync Server Control Panel](images/JJ688109.d2008fd6-868b-4f26-84cf-57bb69e073d3(OCS.15).jpg "Search for OCS users in Lync Server Control Panel")</span></span>

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-control-panel"></a><span data-ttu-id="18f5a-108">Para mover un usuario mediante el panel de control de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="18f5a-108">To move a user by using the Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="18f5a-109">Inicie sesión en el servidor front-end con una cuenta que sea miembro del grupo RTCUniversalServerAdmins o miembro del rol administrativo CsAdministrator o CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="18f5a-109">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>

2.  <span data-ttu-id="18f5a-110">Abra el Panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="18f5a-110">Open Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="18f5a-111">Haga clic en **usuarios**.</span><span class="sxs-lookup"><span data-stu-id="18f5a-111">Click **Users**.</span></span>

4.  <span data-ttu-id="18f5a-112">En la pestaña **búsqueda de usuarios** , haga clic en el botón **Buscar** .</span><span class="sxs-lookup"><span data-stu-id="18f5a-112">From the **User Search** tab, click the **Search** button.</span></span>

5.  <span data-ttu-id="18f5a-113">A continuación, haga clic en **Agregar filtro**.</span><span class="sxs-lookup"><span data-stu-id="18f5a-113">Next, click **Add Filter**.</span></span>

6.  <span data-ttu-id="18f5a-114">Crear un filtro en el que el **usuario de Office Communications Server** sea igual a **true**.</span><span class="sxs-lookup"><span data-stu-id="18f5a-114">Create a filter where **Office Communications Server user** is equal to **True**.</span></span>

7.  <span data-ttu-id="18f5a-115">Haga clic en **Buscar** para buscar usuarios heredados de Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="18f5a-115">Click **Find** to search for legacy Office Communications Server 2007 R2 users.</span></span>
    
    <span data-ttu-id="18f5a-116">![Buscar usuarios de OCS en el panel de control de Lync Server] (images/JJ688109.09528349-7915-41e1-91b4-6ab5c12b1b38(OCS.15).jpg "Buscar usuarios de OCS en el panel de control de Lync Server")</span><span class="sxs-lookup"><span data-stu-id="18f5a-116">![Search for OCS users in Lync Server Control Panel](images/JJ688109.09528349-7915-41e1-91b4-6ab5c12b1b38(OCS.15).jpg "Search for OCS users in Lync Server Control Panel")</span></span>  

8.  <span data-ttu-id="18f5a-117">Seleccione el usuario que desea mover al grupo de servidores de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="18f5a-117">Select a user that you want to move to the Lync Server 2013 pool.</span></span> <span data-ttu-id="18f5a-118">En este ejemplo, moveremos a Sara Davis.</span><span class="sxs-lookup"><span data-stu-id="18f5a-118">In this example, we will move user Sara Davis.</span></span>

9.  <span data-ttu-id="18f5a-119">En el menú **Acción**, seleccione **Mover usuarios seleccionados a grupo**.</span><span class="sxs-lookup"><span data-stu-id="18f5a-119">On the **Action** menu, select **Move selected users to pool**.</span></span>

10. <span data-ttu-id="18f5a-120">En la lista desplegable, seleccione el grupo de 2013 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="18f5a-120">From the drop-down list, select the Lync Server 2013 pool.</span></span>

11. <span data-ttu-id="18f5a-121">Haga clic en **Acción** y, posteriormente, haga clic en **Mover usuarios seleccionados a grupo**.</span><span class="sxs-lookup"><span data-stu-id="18f5a-121">Click **Action** and then click **Move selected users to pool**.</span></span> <span data-ttu-id="18f5a-122">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="18f5a-122">Click **OK**.</span></span>
    
    <span data-ttu-id="18f5a-123">![Establecer el grupo de destino en el cuadro de diálogo mover usuarios] (images/JJ688109.d7dc0759-87c5-4c23-938f-361576621504(OCS.15).jpg "Establecer el grupo de destino en el cuadro de diálogo mover usuarios")</span><span class="sxs-lookup"><span data-stu-id="18f5a-123">![Setting the Destination pool in Move Users dialog](images/JJ688109.d7dc0759-87c5-4c23-938f-361576621504(OCS.15).jpg "Setting the Destination pool in Move Users dialog")</span></span>  

12. <span data-ttu-id="18f5a-124">Compruebe que la columna del **Grupo registrador** del usuario contiene ahora el grupo de servidores de Lync Server 2013, lo que indica que se movió correctamente el usuario</span><span class="sxs-lookup"><span data-stu-id="18f5a-124">Verify that the **Registrar pool** column for the user now contains the Lync Server 2013 pool, which indicates that the user has been successfully moved</span></span>

</div>

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="18f5a-125">Para mover un usuario mediante el shell de administración de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="18f5a-125">To move a user by using the Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="18f5a-126">Abra el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="18f5a-126">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="18f5a-127">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="18f5a-127">At the command line, type the following:</span></span>
    
        Move-CsLegacyUser -Identity "David Pelton" -Target "pool02.contoso.net"

3.  <span data-ttu-id="18f5a-128">A continuación, en la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="18f5a-128">Next, at the command line, type the following:</span></span>
    
        Get-CsUser -Identity "David Pelton"

4.  <span data-ttu-id="18f5a-129">La identidad de **RegistrarPool** apunta ahora al grupo de servidores de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="18f5a-129">The **RegistrarPool** identity now points to the Lync Server 2013 pool.</span></span> <span data-ttu-id="18f5a-130">La presencia de esta identidad confirma que el usuario se movió correctamente.</span><span class="sxs-lookup"><span data-stu-id="18f5a-130">The presence of this identity confirms that the user has been successfully moved.</span></span>
    
    <span data-ttu-id="18f5a-131">![Resultado del cmdlet Get-CsUser con el filtro de identidad] (images/JJ205401.bc5d4672-8068-4475-b882-dbd305c801a9(OCS.15).jpg "Resultado del cmdlet Get-CsUser con el filtro de identidad")</span><span class="sxs-lookup"><span data-stu-id="18f5a-131">![Output from Get-CsUser cmdlet with Identity filter](images/JJ205401.bc5d4672-8068-4475-b882-dbd305c801a9(OCS.15).jpg "Output from Get-CsUser cmdlet with Identity filter")</span></span>  
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="18f5a-132">Para obtener detalles sobre el cmdlet <STRONG>Get-CsUser</STRONG> , ejecute: <STRONG>Get-Help Get-CsUser-</STRONG> Detailed</span><span class="sxs-lookup"><span data-stu-id="18f5a-132">For details about the <STRONG>Get-CsUser</STRONG> cmdlet, run: <STRONG>Get-Help Get-CsUser –Detailed</STRONG></span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

