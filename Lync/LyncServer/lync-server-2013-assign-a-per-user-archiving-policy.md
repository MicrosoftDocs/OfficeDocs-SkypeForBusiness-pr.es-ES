---
title: 'Lync Server 2013: asignar una directiva de archivado por usuario'
description: 'Lync Server 2013: asignar una directiva de archivado por usuario.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user archiving policy
ms:assetid: a12ca483-b235-460f-b3fe-130fb3087264
ms:mtpsurl: https://technet.microsoft.com/library/Gg182560(v=OCS.15)
ms:contentKeyID: 48185014
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c81d7e426f16c298196aba733d720a92d0854bd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559996"
---
# <a name="assign-a-per-user-archiving-policy-in-lync-server-2013"></a><span data-ttu-id="0720b-103">Asignar una directiva de archivado por usuario en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0720b-103">Assign a per-user archiving policy in Lync Server 2013</span></span>

 


<span data-ttu-id="0720b-104">La Directiva de archivado es una de las configuraciones individuales de una cuenta de usuario que se puede configurar en el panel de control de 2013 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0720b-104">The archiving policy is one of the individual settings of a user account that you can configure in the Lync Server 2013 Control Panel.</span></span>

<span data-ttu-id="0720b-p101">La implementación de una o más directivas de archivado por usuario es opcional. Asimismo, puede implementar solamente una directiva de archivado a nivel global o a nivel de sitio. Si no implementa directivas por usuario, es preciso que las asigne explícitamente a un objeto de usuario, grupo o contacto. Los requisitos de archivado toman automáticamente los valores predeterminados de aquellos definidos en la directiva de conferencia cuando no se asigna una directiva a nivel de sitio o por usuario específica.</span><span class="sxs-lookup"><span data-stu-id="0720b-p101">Deploying one or more per-user archiving policies is optional. You can also deploy only a global-level archiving policy or site-level archiving policy. If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact object. Archiving requirements automatically default to those defined in the global-level conferencing policy when no specific site-level or per-user policy is assigned.</span></span>

<span data-ttu-id="0720b-109">Tras crear al menos una directiva de archivado por usuario, use los procedimientos en este tema para asignar la directiva que especifique adecuadamente si el servidor archivará las comunicaciones internas y externas de un usuario, o ambas.</span><span class="sxs-lookup"><span data-stu-id="0720b-109">After creating at least one per-user archiving policy, use the procedures in this topic to assign the policy that appropriately specifies whether a particular user’s internal communications, external communications, or both, will be archived by the server.</span></span>

<span data-ttu-id="0720b-110">Para obtener información detallada sobre cómo crear directivas de archivado por usuario, vea [crear una directiva de archivado en Lync Server 2013 para habilitar o deshabilitar el archivado de comunicaciones internas o externas para sitios o usuarios específicos](lync-server-2013-create-archiving-policy-sites-users.md).</span><span class="sxs-lookup"><span data-stu-id="0720b-110">For details about creating per-user archiving policies, see [Creating an Archiving policy in Lync Server 2013 to enable or disable Archiving of Internal or external communications for specific sites or users](lync-server-2013-create-archiving-policy-sites-users.md).</span></span>

## <a name="to-assign-a-per-user-archiving-policy"></a><span data-ttu-id="0720b-111">Para asignar una directiva de archivado por usuario</span><span class="sxs-lookup"><span data-stu-id="0720b-111">To assign a per-user archiving policy</span></span>

1.  <span data-ttu-id="0720b-112">Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="0720b-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="0720b-113">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0720b-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="0720b-114">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="0720b-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="0720b-115">En la barra de navegación izquierda, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="0720b-115">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="0720b-116">Utilice uno de los métodos siguientes para encontrar a un usuario:</span><span class="sxs-lookup"><span data-stu-id="0720b-116">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="0720b-117">En el cuadro **Buscar usuarios**, escriba la primera porción del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de la cuenta de usuario y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="0720b-117">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="0720b-118">Si ha guardado una consulta, haga clic en el icono **Abrir consulta**, utilice el cuadro de diálogo **Abrir** para recuperar la consulta (un archivo .usf) y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="0720b-118">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="0720b-119">(Opcional) Especificar criterios de búsqueda adicionales para restringir los resultados:</span><span class="sxs-lookup"><span data-stu-id="0720b-119">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="0720b-120">Haga clic en **Agregar filtro**.</span><span class="sxs-lookup"><span data-stu-id="0720b-120">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="0720b-121">Especifique la propiedad de usuario; para ello, escríbala o haga clic en la flecha de la lista desplegable para seleccionar la propiedad.</span><span class="sxs-lookup"><span data-stu-id="0720b-121">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="0720b-122">En la lista desplegable **Igual a**, haga clic en el operador (por ejemplo, **Igual a** o **No igual a**).</span><span class="sxs-lookup"><span data-stu-id="0720b-122">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="0720b-123">En función de la propiedad de usuario que haya seleccionado, especifique los criterios que desee utilizar para filtrar los resultados de búsqueda escribiendo o haciendo clic en la flecha de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="0720b-123">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="0720b-124">Para agregar cláusulas de búsqueda adicionales a la consulta, haga clic en <STRONG>Agregar filtro</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="0720b-124">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="0720b-125">Haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="0720b-125">Click **Find**.</span></span>

6.  <span data-ttu-id="0720b-126">Haga clic en un usuario en los resultados de búsqueda, haga clic en **Acción** y, a continuación, en **Asignar directivas**.</span><span class="sxs-lookup"><span data-stu-id="0720b-126">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="0720b-127">Si desea que se aplique la misma directiva de archivado por usuario a múltiples usuarios, seleccione varios usuarios en los resultados de la búsqueda, a continuación, haga clic en <STRONG>Acciones</STRONG> y en <STRONG>Asignar directivas</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="0720b-127">If you want the same per-user archiving policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="0720b-128">En **Asignar directivas**, en **Directiva de archivado**, realice uno de los procedimientos siguientes:</span><span class="sxs-lookup"><span data-stu-id="0720b-128">In **Assign Policies**, under **Archiving policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="0720b-129">Debido a que hay varias directivas que puede configurar mediante el cuadro de diálogo <STRONG>asignar directivas</STRONG> , se selecciona la opción <STRONG> &lt; mantener como está &gt; </STRONG> seleccionada de forma predeterminada para cada Directiva del cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="0720b-129">Because there are multiple policies that you can configure by using the <STRONG>Assign Policies</STRONG> dialog box, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="0720b-130">Para seguir utilizando la directiva asignada anteriormente al usuario, no efectúe cambios en esta configuración.</span><span class="sxs-lookup"><span data-stu-id="0720b-130">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="0720b-131">Permita que Lync Server 2013 elija automáticamente la Directiva de nivel global o, si está definida, la Directiva de nivel de sitio.</span><span class="sxs-lookup"><span data-stu-id="0720b-131">Allow Lync Server 2013 to automatically choose either the global-level policy or, if defined, the site-level policy.</span></span>
    
      - <span data-ttu-id="0720b-132">Haga clic en el nombre de una directiva de archivado por usuario que haya definido anteriormente en la página **Directiva de archivado**.</span><span class="sxs-lookup"><span data-stu-id="0720b-132">Click the name of a per-user archiving policy you previously defined on the **Archiving Policy** page.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="0720b-133">Para ayudarle a decidir la directiva que desea asignar, tras hacer clic en el nombre de una directiva, haga clic en <STRONG>Ver</STRONG> para ver los derechos y permisos de usuarios definidos en la directiva.</span><span class="sxs-lookup"><span data-stu-id="0720b-133">To help you decide the policy that you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="0720b-134">Cuando haya terminado, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0720b-134">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-archiving-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="0720b-135">Asignación de una directiva de archivado de Per-User mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0720b-135">Assigning a Per-User Archiving Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="0720b-136">Puede asignar directivas de archivado por usuario con Windows PowerShell y el cmdlet **Grant-CsArchivingPolicy** .</span><span class="sxs-lookup"><span data-stu-id="0720b-136">You can assign per-user archiving policies by using Windows PowerShell and the **Grant-CsArchivingPolicy** cmdlet.</span></span> <span data-ttu-id="0720b-137">Puede ejecutar este cmdlet desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0720b-137">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="0720b-138">Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server 2010 mediante PowerShell remoto" en [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="0720b-138">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-archiving-policy-to-a-single-user"></a><span data-ttu-id="0720b-139">Para asignar una directiva de archivado por usuario a un solo usuario</span><span class="sxs-lookup"><span data-stu-id="0720b-139">To assign a per-user archiving policy to a single user</span></span>

  - <span data-ttu-id="0720b-140">El siguiente comando permite asignar la directiva de archivado por usuario RedmondArchivingPolicy al usuario Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="0720b-140">The following command assigns the per-user archiving policy RedmondArchivingPolicy to the user Ken Myer.</span></span>
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"

## <a name="to-assign-a-per-user-archiving-policy-to-multiple-users"></a><span data-ttu-id="0720b-141">Para asignar una directiva de archivado por usuario a varios usuarios</span><span class="sxs-lookup"><span data-stu-id="0720b-141">To assign a per-user archiving policy to multiple users</span></span>

  - <span data-ttu-id="0720b-142">Este comando asigna la directiva de archivado por usuario RedmondArchivingPolicy a todos los usuarios que tengan cuentas alojadas en el grupo de registradores en atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="0720b-142">This command assigns the per-user archiving policy RedmondArchivingPolicy to all the users who have accounts homed on the Registrar pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="0720b-143">Para obtener más información sobre el parámetro filter usado en este comando, consulte la documentación del cmdlet [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="0720b-143">For more information on the Filter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"

## <a name="to-unassign-a-per-user-archiving-policy"></a><span data-ttu-id="0720b-144">Para cancelar la asignación de una directiva de archivado por usuario</span><span class="sxs-lookup"><span data-stu-id="0720b-144">To unassign a per-user archiving policy</span></span>

  - <span data-ttu-id="0720b-p106">Este comando desasigna cualquier directiva de archivado por usuario previamente asignada a Ken Myer. Una vez desasignada la directiva por usuario, Ken Myer pasará automáticamente a ser administrado mediante la directiva global (o, de existir, por la directiva de su sitio local). Las directivas de sitio tienen prioridad sobre la directiva global.</span><span class="sxs-lookup"><span data-stu-id="0720b-p106">The following command unassigns any per-user archiving policy previously assigned to Ken Myer. After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy. A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="0720b-148">Para obtener más información, consulte el tema de ayuda para el cmdlet [Grant-CsArchivingPolicy](https://technet.microsoft.com/library/gg398475\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="0720b-148">For more information, see the help topic for the [Grant-CsArchivingPolicy](https://technet.microsoft.com/library/gg398475\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="0720b-149">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0720b-149">See Also</span></span>


[<span data-ttu-id="0720b-150">Crear una directiva de archivado en Lync Server 2013 para habilitar o deshabilitar el archivado de comunicaciones internas o externas para sitios o usuarios específicos</span><span class="sxs-lookup"><span data-stu-id="0720b-150">Creating an Archiving policy in Lync Server 2013 to enable or disable Archiving of internal or external communications for specific sites or users</span></span>](lync-server-2013-create-archiving-policy-sites-users.md)  


[<span data-ttu-id="0720b-151">Asignación de directivas por usuario en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0720b-151">Assigning per-user policies in Lync Server 2013</span></span>](lync-server-2013-assigning-per-user-policies.md)

