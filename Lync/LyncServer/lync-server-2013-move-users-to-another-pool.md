---
title: 'Lync Server 2013: mover usuarios a otro grupo'
description: 'Lync Server 2013: mover usuarios a otro grupo.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move users to another pool
ms:assetid: e7b4968c-0e9d-4d56-b5f1-9edf0f7206f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182600(v=OCS.15)
ms:contentKeyID: 48185879
ms.date: 02/09/2018
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 21012e0df7567a79bca018d194878c85b8653ae4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566396"
---
# <a name="move-users-to-another-pool-in-lync-server-2013"></a><span data-ttu-id="0b1e1-103">Mover usuarios a otro grupo de servidores en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0b1e1-103">Move users to another pool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="0b1e1-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="0b1e1-104">

<span> </span></span></span>

<span data-ttu-id="0b1e1-105">_**Última modificación del tema:** 2018-02-09_</span><span class="sxs-lookup"><span data-stu-id="0b1e1-105">_**Topic Last Modified:** 2018-02-09_</span></span>

<span data-ttu-id="0b1e1-106">Puede usar el panel de control de Lync Server para asignar usuarios a un servidor o grupo de servidores específico.</span><span class="sxs-lookup"><span data-stu-id="0b1e1-106">You can use Lync Server Control Panel to assign users to a specific server or pool.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="0b1e1-107">Mover todos los usuarios existentes de un grupo de servidores de origen que ejecuta Lync Server 2010 o anterior a un grupo de servidores de destino de Lync Server 2013 en un entorno de Active Directory complejo puede dar como resultado una replicación más lenta de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0b1e1-107">Moving all existing users from a source pool that is running Lync Server 2010 or earlier to a Lync Server 2013 destination pool in a complex Active Directory environment might result in slower Active Directory replication.</span></span> <span data-ttu-id="0b1e1-108">Para evitar esto, puede usar filtros de búsqueda para mover usuarios de grupos que ejecutan Lync Server 2010 o una versión anterior por separado, o puede usar el shell de administración de Lync Server para mover usuarios con cmdlets.</span><span class="sxs-lookup"><span data-stu-id="0b1e1-108">To avoid this, you can use search filters to move users from pools that are running Lync Server 2010 or earlier separately, or you can use Lync Server Management Shell to move users with cmdlets.</span></span> <span data-ttu-id="0b1e1-109">Además, la funcionalidad de filtros funciona con los usuarios de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0b1e1-109">Also, the filter functionality works with Lync Server 2013 users.</span></span>



</div>

<div>

## <a name="to-move-selected-users-to-a-different-server-or-pool"></a><span data-ttu-id="0b1e1-110">Para mover determinados usuarios a otro servidor o grupo de servidores</span><span class="sxs-lookup"><span data-stu-id="0b1e1-110">To move selected users to a different server or pool</span></span>

1.  <span data-ttu-id="0b1e1-111">Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="0b1e1-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="0b1e1-112">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0b1e1-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="0b1e1-113">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="0b1e1-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="0b1e1-114">En la barra de navegación izquierda, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="0b1e1-114">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="0b1e1-115">En el cuadro **Buscar usuarios**, escriba la primera parte del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de la cuenta de usuario que desee y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="0b1e1-115">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span>

5.  <span data-ttu-id="0b1e1-116">En la tabla, seleccione uno o varios usuarios de la lista.</span><span class="sxs-lookup"><span data-stu-id="0b1e1-116">In the table, select a specific user or users in the list.</span></span>

6.  <span data-ttu-id="0b1e1-117">En el menú **Acción**, haga clic en **Mover usuarios seleccionados a un grupo de servidores**.</span><span class="sxs-lookup"><span data-stu-id="0b1e1-117">On the **Action** menu, click **Move selected users to pool**.</span></span>

7.  <span data-ttu-id="0b1e1-118">En **Mover usuarios**, seleccione el grupo de servidores al que desea trasladar los usuarios en **Grupo de registrador de destino**.</span><span class="sxs-lookup"><span data-stu-id="0b1e1-118">In **Move Users**, select the pool that you want to move the users to in **Destination registrar pool**.</span></span>

8.  <span data-ttu-id="0b1e1-119">(Opcional) Si el servidor o grupo de destino no está disponible, active la casilla **Imponer**.</span><span class="sxs-lookup"><span data-stu-id="0b1e1-119">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    <div>
    

    > [!Caution]  
    > <span data-ttu-id="0b1e1-120">Si selecciona <STRONG>forzar</STRONG>, la cuenta de usuario se mueve, pero los datos de usuario asociados, las conferencias y los contactos programados no se mueven.</span><span class="sxs-lookup"><span data-stu-id="0b1e1-120">If you select <STRONG>Force</STRONG>, the user account is moved, but associated user data such scheduled conferences and contacts is not moved.</span></span>

    
    </div>

</div>

<div>

## <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a><span data-ttu-id="0b1e1-121">Para mover todos los usuarios de un servidor o grupo de servidores a otro servidor o grupo de servidores</span><span class="sxs-lookup"><span data-stu-id="0b1e1-121">To move all users from one server or pool to a different server or pool</span></span>

1.  <span data-ttu-id="0b1e1-122">Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="0b1e1-122">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="0b1e1-123">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0b1e1-123">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="0b1e1-124">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="0b1e1-124">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="0b1e1-125">En la barra de navegación izquierda, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="0b1e1-125">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="0b1e1-126">En el menú **Acción**, haga clic en **Mover todos los usuarios a un grupo de servidores**.</span><span class="sxs-lookup"><span data-stu-id="0b1e1-126">On the **Action** menu, click **Move all users to pool**.</span></span>

5.  <span data-ttu-id="0b1e1-127">En **Mover usuarios**, seleccione el grupo de servidores que contiene las cuentas de usuario que desea trasladar en **Grupo de registrador de origen**.</span><span class="sxs-lookup"><span data-stu-id="0b1e1-127">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>

6.  <span data-ttu-id="0b1e1-128">En **Grupo de registrador de destino**, seleccione el grupo de servidores al que desea trasladar los usuarios.</span><span class="sxs-lookup"><span data-stu-id="0b1e1-128">In **Destination registrar pool**, select the pool that you want to move the users to.</span></span>

7.  <span data-ttu-id="0b1e1-129">(Opcional) Si el servidor o grupo de destino no está disponible, active la casilla **Imponer**.</span><span class="sxs-lookup"><span data-stu-id="0b1e1-129">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    <div>
    

    > [!Caution]  
    > <span data-ttu-id="0b1e1-130">Si selecciona <STRONG>forzar</STRONG>, la cuenta de usuario se mueve, pero los datos de usuario asociados, las conferencias y los contactos programados no se mueven.</span><span class="sxs-lookup"><span data-stu-id="0b1e1-130">If you select <STRONG>Force</STRONG>, the user account is moved, but associated user data such scheduled conferences and contacts is not moved.</span></span>

    
    </div>

</div>

<div>

## <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a><span data-ttu-id="0b1e1-131">Para mover usuarios de un grupo a otro grupo diferente mediante un filtro</span><span class="sxs-lookup"><span data-stu-id="0b1e1-131">To move users from one pool to a different pool by using a filter</span></span>

1.  <span data-ttu-id="0b1e1-132">Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="0b1e1-132">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="0b1e1-133">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0b1e1-133">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="0b1e1-134">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="0b1e1-134">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="0b1e1-135">En la barra de navegación izquierda, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="0b1e1-135">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="0b1e1-136">En **búsqueda de usuarios**, haga clic en **Buscar**y, a continuación, en **Agregar filtro**.</span><span class="sxs-lookup"><span data-stu-id="0b1e1-136">In **User Search**, click **Search**, and then click **Add Filter**.</span></span>

5.  <span data-ttu-id="0b1e1-137">En los Criterios de búsqueda, seleccione **Grupo de registradores**, **Igual que**, **FQDN del grupo actual** y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="0b1e1-137">In the Search criteria, select **Registrar Pool**, select **Equal to**, select **Current Pool FQDN**, and then click **Find**.</span></span>

6.  <span data-ttu-id="0b1e1-138">En el menú **Acción**, haga clic en **Mover todos los usuarios al grupo**.</span><span class="sxs-lookup"><span data-stu-id="0b1e1-138">On the **Action** menu, click **Move all users to pool**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0b1e1-139">Cuando se aplica un filtro a un conjunto de usuarios existente, la opción <STRONG>mover todos los usuarios al grupo</STRONG> está en el contexto del subconjunto filtrado de usuarios, no de <STRONG><EM>todos</EM></STRONG> los usuarios posibles.</span><span class="sxs-lookup"><span data-stu-id="0b1e1-139">When a filter is applied to an existing set of users, the option <STRONG>Move all users to pool</STRONG> is in the context of the filtered subset of users, not <STRONG><EM>all</EM></STRONG> possible users.</span></span>

    
    </div>

7.  <span data-ttu-id="0b1e1-140">En **Mover usuarios**, seleccione el grupo de servidores que contiene las cuentas de usuario que desea trasladar en **Grupo de registradores de origen**.</span><span class="sxs-lookup"><span data-stu-id="0b1e1-140">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>

8.  <span data-ttu-id="0b1e1-141">En **Grupo de registradores de destino**, seleccione el grupo de servidores al que desea trasladar los usuarios.</span><span class="sxs-lookup"><span data-stu-id="0b1e1-141">In **Destination registrar pool**, select the pool where you want to move the users.</span></span>

9.  <span data-ttu-id="0b1e1-142">(Opcional) Si el servidor o grupo de destino no está disponible, active la casilla **Forzar**.</span><span class="sxs-lookup"><span data-stu-id="0b1e1-142">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    <div>
    

    > [!Caution]  
    > <span data-ttu-id="0b1e1-143">Si selecciona <STRONG>forzar</STRONG>, la cuenta de usuario se mueve, pero los datos de usuario asociados, las conferencias y los contactos programados no se mueven.</span><span class="sxs-lookup"><span data-stu-id="0b1e1-143">If you select <STRONG>Force</STRONG>, the user account is moved, but associated user data such scheduled conferences and contacts is not moved.</span></span>

    
    </div>

</div>

<div>

## <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a><span data-ttu-id="0b1e1-144">Para mover usuarios de un grupo de servidores a otro mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0b1e1-144">To move users from one pool to another using Windows PowerShell cmdlets</span></span>

1.  <span data-ttu-id="0b1e1-145">En función de cómo ejecute los comandos de Windows PowerShell (es decir, local o remotamente), debe iniciar sesión como miembro de los roles administrativos correctos de Lync Server 2013 de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="0b1e1-145">Depending on how you run Windows PowerShell commands (that is, locally or remotely), you need to log on as a member of the correct Lync Server 2013 administrative roles as follows:</span></span>
    
    1.  <span data-ttu-id="0b1e1-146">Si está ejecutando los comandos en el equipo local (por ejemplo, inicia sesión directamente en un servidor front-end): inicie sesión en el equipo en el que está instalado el shell de administración de Lync Server como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios, tal y como se describe en [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="0b1e1-146">If you are running the commands on the local machine (for example, you log on directly to a Front End Server): Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>
    
    2.  <span data-ttu-id="0b1e1-147">Si ejecuta los comandos de forma remota en otro equipo (por ejemplo, inicia sesión en el equipo y ejecuta los comandos de forma remota en un servidor front-end Standard Edition): desde una cuenta de usuario asignada al rol CsUserAdministrator o al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="0b1e1-147">If you are running the commands remotely on another computer (for example, you log on to your computer and run the commands remotely on a Standard Edition Front End Server): From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="0b1e1-148">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="0b1e1-148">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="0b1e1-149">Para mover usuarios únicos, use el cmdlet Move-CsUser de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="0b1e1-149">To move single users, use the Move-CsUser cmdlet as follows:</span></span>
    
        Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    
    <span data-ttu-id="0b1e1-150">Donde el usuario que se moverá es Pilar Ackerman, y el usuario se moverá de su grupo de servidores principales actualmente asignado al grupo pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="0b1e1-150">Where the user to move is the user Pilar Ackerman, and the user will be moved from their currently assigned home pool to the pool pool01.contoso.net</span></span>

4.  <span data-ttu-id="0b1e1-151">Para mover una cantidad grande de usuarios, use filtros con el cmdlet **Get-CsUser** y pase el conjunto resultante de usuarios a **Move-CsUser**:</span><span class="sxs-lookup"><span data-stu-id="0b1e1-151">To move a large number of users, use filters with the **Get-CsUser** cmdlet and pass the resulting set of users to **Move-CsUser**:</span></span>
    
        Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    
    <span data-ttu-id="0b1e1-152">Los comandos combinados de los cmdlets **Get-CsUser** y **Move-CsUser** podrían dar el resultado siguiente:</span><span class="sxs-lookup"><span data-stu-id="0b1e1-152">The combined commands of the **Get-CsUser** and **Move-CsUser** might result in this:</span></span>
    
        Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0b1e1-153">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0b1e1-153">See Also</span></span>


[<span data-ttu-id="0b1e1-154">Modificación de las propiedades de la cuenta de usuario en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0b1e1-154">Modifying user account properties in Lync Server 2013</span></span>](lync-server-2013-modifying-user-account-properties.md)  
  

<span data-ttu-id="0b1e1-155"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="0b1e1-155"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

