---
title: 'Lync Server 2013: asignar una directiva de archivado por usuario'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign a per-user archiving policy
ms:assetid: a12ca483-b235-460f-b3fe-130fb3087264
ms:mtpsurl: https://technet.microsoft.com/library/Gg182560(v=OCS.15)
ms:contentKeyID: 48185014
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 36d23e44e397a77f0d490d8fda27ee711d1c61c5
ms.sourcegitcommit: 0119af282f53f49c4ab6e01c3319d01bc6fdad2c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2020
ms.locfileid: "41111584"
---
# <a name="assign-a-per-user-archiving-policy-in-lync-server-2013"></a><span data-ttu-id="459af-102">Asignar una directiva de archivado por usuario en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="459af-102">Assign a per-user archiving policy in Lync Server 2013</span></span>

 


<span data-ttu-id="459af-103">La Directiva de archivado es una de las configuraciones individuales de una cuenta de usuario que puede configurar en el panel de control de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="459af-103">The archiving policy is one of the individual settings of a user account that you can configure in the Lync Server 2013 Control Panel.</span></span>

<span data-ttu-id="459af-104">La implementación de una o más directivas de archivado por usuario es opcional.</span><span class="sxs-lookup"><span data-stu-id="459af-104">Deploying one or more per-user archiving policies is optional.</span></span> <span data-ttu-id="459af-105">También puede implementar una directiva de archivado de nivel global o una directiva de archivado de nivel de sitio.</span><span class="sxs-lookup"><span data-stu-id="459af-105">You can also deploy only a global-level archiving policy or site-level archiving policy.</span></span> <span data-ttu-id="459af-106">Si implementa directivas por usuario, es preciso que las asigne explícitamente a un objeto de usuario, grupo o contacto.</span><span class="sxs-lookup"><span data-stu-id="459af-106">If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact object.</span></span> <span data-ttu-id="459af-107">Los requisitos de archivado se especifican de forma automática predeterminada para los definidos en la Directiva de conferencia global cuando no se ha asignado ninguna directiva específica de nivel de sitio o de usuario.</span><span class="sxs-lookup"><span data-stu-id="459af-107">Archiving requirements automatically default to those defined in the global-level conferencing policy when no specific site-level or per-user policy is assigned.</span></span>

<span data-ttu-id="459af-108">Después de crear al menos una directiva de archivado por usuario, use los procedimientos de este tema para asignar la Directiva que especifica correctamente si el servidor archivará las comunicaciones internas, las comunicaciones externas o ambas de un usuario en particular.</span><span class="sxs-lookup"><span data-stu-id="459af-108">After creating at least one per-user archiving policy, use the procedures in this topic to assign the policy that appropriately specifies whether a particular user’s internal communications, external communications, or both, will be archived by the server.</span></span>

<span data-ttu-id="459af-109">Para obtener más información sobre la creación de directivas de archivado por usuario, consulte [crear una directiva de archivado en Lync Server 2013 para habilitar o deshabilitar el archivado de las comunicaciones internas o externas para determinados sitios o usuarios](lync-server-2013-create-archiving-policy-sites-users.md).</span><span class="sxs-lookup"><span data-stu-id="459af-109">For details about creating per-user archiving policies, see [Creating an Archiving policy in Lync Server 2013 to enable or disable Archiving of Internal or external communications for specific sites or users](lync-server-2013-create-archiving-policy-sites-users.md).</span></span>

## <a name="to-assign-a-per-user-archiving-policy"></a><span data-ttu-id="459af-110">Para asignar una directiva de archivado por usuario</span><span class="sxs-lookup"><span data-stu-id="459af-110">To assign a per-user archiving policy</span></span>

1.  <span data-ttu-id="459af-111">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="459af-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="459af-112">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="459af-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="459af-113">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="459af-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="459af-114">En la barra de navegación izquierda, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="459af-114">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="459af-115">Use uno de los métodos siguientes para encontrar a un usuario:</span><span class="sxs-lookup"><span data-stu-id="459af-115">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="459af-116">En el cuadro **Buscar usuarios**, escriba la primera porción del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de la cuenta de usuario y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="459af-116">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="459af-117">Si ha guardado una consulta, haga clic en el icono **Abrir consulta**, use el cuadro de diálogo **Abrir** para recuperar la consulta (un archivo .usf) y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="459af-117">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="459af-118">(Opcional) Especificar criterios de búsqueda adicionales para restringir los resultados:</span><span class="sxs-lookup"><span data-stu-id="459af-118">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="459af-119">Haga clic en **Agregar filtro**.</span><span class="sxs-lookup"><span data-stu-id="459af-119">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="459af-120">Especifique la propiedad de usuario. Para ello, escríbala o haga clic en la flecha de la lista desplegable para seleccionar la propiedad.</span><span class="sxs-lookup"><span data-stu-id="459af-120">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="459af-121">En la lista desplegable **Igual a**, haga clic en el operador (por ejemplo, **Igual a** o **No igual a**).</span><span class="sxs-lookup"><span data-stu-id="459af-121">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="459af-122">En función de la propiedad de usuario que haya seleccionado, especifique los criterios que desee utilizar para filtrar los resultados de búsqueda escribiendo o haciendo clic en la flecha de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="459af-122">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="459af-123">Para agregar cláusulas de búsqueda adicionales a la consulta, haga clic en <STRONG>Agregar filtro</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="459af-123">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="459af-124">Haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="459af-124">Click **Find**.</span></span>

6.  <span data-ttu-id="459af-125">Haga clic en un usuario en los resultados de búsqueda, haga clic en **Acción** y, a continuación, en **Asignar directivas**.</span><span class="sxs-lookup"><span data-stu-id="459af-125">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="459af-126">Si desea aplicar la misma directiva de archivado por usuario a varios usuarios, seleccione varios usuarios en los resultados de búsqueda, haga clic en <STRONG>acciones</STRONG>y, a continuación, haga clic en <STRONG>asignar directivas</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="459af-126">If you want the same per-user archiving policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="459af-127">En **asignar directivas**, en **Directiva de archivado**, siga uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="459af-127">In **Assign Policies**, under **Archiving policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="459af-128">Puesto que existen varias directivas que puede configurar mediante el cuadro de diálogo <STRONG>asignar directivas</STRONG> , <STRONG> &lt;&gt; </STRONG> la opción mantener está seleccionada de forma predeterminada para todas las directivas del cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="459af-128">Because there are multiple policies that you can configure by using the <STRONG>Assign Policies</STRONG> dialog box, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="459af-129">Para seguir usando la directiva asignada anteriormente al usuario, no efectúe cambios en esta configuración.</span><span class="sxs-lookup"><span data-stu-id="459af-129">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="459af-130">Permita Lync Server 2013 para elegir automáticamente la Directiva de nivel global o, si se ha definido, la Directiva de nivel de sitio.</span><span class="sxs-lookup"><span data-stu-id="459af-130">Allow Lync Server 2013 to automatically choose either the global-level policy or, if defined, the site-level policy.</span></span>
    
      - <span data-ttu-id="459af-131">Haga clic en el nombre de una directiva de archivado por usuario que haya definido previamente en la página **Directiva de archivado** .</span><span class="sxs-lookup"><span data-stu-id="459af-131">Click the name of a per-user archiving policy you previously defined on the **Archiving Policy** page.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="459af-132">Para ayudarle a decidir la Directiva que desea asignar, después de hacer clic en un nombre de Directiva, haga clic en <STRONG>Ver</STRONG> para ver los derechos de usuario y permisos definidos en la Directiva.</span><span class="sxs-lookup"><span data-stu-id="459af-132">To help you decide the policy that you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="459af-133">Cuando haya terminado, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="459af-133">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-archiving-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="459af-134">Asignar una directiva de archivado por usuario mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="459af-134">Assigning a Per-User Archiving Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="459af-135">Puede asignar directivas de archivado por usuario mediante Windows PowerShell y el cmdlet **Grant-CsArchivingPolicy** .</span><span class="sxs-lookup"><span data-stu-id="459af-135">You can assign per-user archiving policies by using Windows PowerShell and the **Grant-CsArchivingPolicy** cmdlet.</span></span> <span data-ttu-id="459af-136">Puede ejecutar este cmdlet desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="459af-136">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="459af-137">Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.</span><span class="sxs-lookup"><span data-stu-id="459af-137">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-archiving-policy-to-a-single-user"></a><span data-ttu-id="459af-138">Para asignar una directiva de archivado por usuario a un solo usuario</span><span class="sxs-lookup"><span data-stu-id="459af-138">To assign a per-user archiving policy to a single user</span></span>

  - <span data-ttu-id="459af-139">El siguiente comando permite asignar la directiva de archivado por usuario RedmondArchivingPolicy al usuario Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="459af-139">The following command assigns the per-user archiving policy RedmondArchivingPolicy to the user Ken Myer.</span></span>
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"

## <a name="to-assign-a-per-user-archiving-policy-to-multiple-users"></a><span data-ttu-id="459af-140">Para asignar una directiva de archivado por usuario a varios usuarios</span><span class="sxs-lookup"><span data-stu-id="459af-140">To assign a per-user archiving policy to multiple users</span></span>

  - <span data-ttu-id="459af-141">Este comando asigna el RedmondArchivingPolicy de directiva de archivado por usuario a todos los usuarios que tienen cuentas alojadas en el registro de la agrupación de atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="459af-141">This command assigns the per-user archiving policy RedmondArchivingPolicy to all the users who have accounts homed on the Registrar pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="459af-142">Para obtener más información sobre el parámetro de filtro usado en este comando, consulte la documentación del cmdlet [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="459af-142">For more information on the Filter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"

## <a name="to-unassign-a-per-user-archiving-policy"></a><span data-ttu-id="459af-143">Para cancelar la asignación de una directiva de archivado por usuario</span><span class="sxs-lookup"><span data-stu-id="459af-143">To unassign a per-user archiving policy</span></span>

  - <span data-ttu-id="459af-144">El comando siguiente elimina la asignación de cualquier directiva de archivado por usuario previamente asignada a Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="459af-144">The following command unassigns any per-user archiving policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="459af-145">Después de quitar la asignación de la directiva por usuario, se usará automáticamente la directiva global o la directiva del sitio local, si existe, para administrar a Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="459af-145">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="459af-146">La directiva de sitio tiene prioridad sobre la directiva global.</span><span class="sxs-lookup"><span data-stu-id="459af-146">A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="459af-147">Para obtener más información, consulte el tema de ayuda para el cmdlet [Grant-CsArchivingPolicy](https://technet.microsoft.com/library/gg398475\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="459af-147">For more information, see the help topic for the [Grant-CsArchivingPolicy](https://technet.microsoft.com/library/gg398475\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="459af-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="459af-148">See Also</span></span>


[<span data-ttu-id="459af-149">Crear una directiva de archivado en Lync Server 2013 para habilitar o deshabilitar el archivado de las comunicaciones internas o externas para usuarios o sitios específicos</span><span class="sxs-lookup"><span data-stu-id="459af-149">Creating an Archiving policy in Lync Server 2013 to enable or disable Archiving of internal or external communications for specific sites or users</span></span>](lync-server-2013-create-archiving-policy-sites-users.md)  


[<span data-ttu-id="459af-150">Asignación de directivas por usuario en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="459af-150">Assigning per-user policies in Lync Server 2013</span></span>](lync-server-2013-assigning-per-user-policies.md)

