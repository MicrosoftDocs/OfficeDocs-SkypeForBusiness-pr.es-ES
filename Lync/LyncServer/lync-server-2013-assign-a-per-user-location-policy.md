---
title: 'Lync Server 2013: asignar una directiva de ubicación por usuario'
description: 'Lync Server 2013: asignar una directiva de ubicación por usuario.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user location policy
ms:assetid: 343f2de3-a0ae-4403-8456-6e520b579d32
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520974(v=OCS.15)
ms:contentKeyID: 48183794
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 81631740e0a6c908c392ccacb6b37d7033d9224c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559886"
---
# <a name="assign-a-per-user-location-policy-in-lync-server-2013"></a><span data-ttu-id="1cfe3-103">Asignar una directiva de ubicación por usuario en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1cfe3-103">Assign a per-user location policy in Lync Server 2013</span></span>

 


<span data-ttu-id="1cfe3-104">La Directiva de ubicación es una de las configuraciones individuales de una cuenta de usuario que se puede configurar en el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1cfe3-104">The location policy is one of the individual settings of a user account that you can configure in the Lync Server Control Panel.</span></span>

<span data-ttu-id="1cfe3-p101">La implementación de una o varias directivas de ubicación por usuario es opcional. También puede implementar solamente una directiva de ubicación de nivel global o una directiva de ubicación de nivel de subred. Si no implementa directivas por usuario, es preciso que las asigne explícitamente a un objeto de usuario, grupo o contacto. La configuración de Enhanced 9-1-1 (E9-1-1) establece automáticamente como predeterminada la definida en la directiva de ubicación de nivel global, en el caso de que no se haya asignado una directiva específica a nivel de subred o por usuario.</span><span class="sxs-lookup"><span data-stu-id="1cfe3-p101">Deploying one or more per-user location policies is optional. You can also deploy only a global-level location policy or subnet-level location policy. If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact object. Enhanced 9-1-1 (E9-1-1) settings automatically default to those defined in the global-level location policy when no specific subnet-level or per-user policy is assigned.</span></span>

<span data-ttu-id="1cfe3-109">Tras crear al menos una directiva de ubicación por usuario, emplee los procedimientos de este tema para asignar a la directiva que especifique la configuración que desea que aplique el servidor para las llamadas de emergencia realizadas por parte de un usuario particular.</span><span class="sxs-lookup"><span data-stu-id="1cfe3-109">After creating at least one per-user location policy, use the procedures in this topic to assign to the policy that specifies the settings that you want the server to apply for emergency calls placed by a particular user.</span></span>

<span data-ttu-id="1cfe3-110">Para obtener una lista de todas las opciones de configuración de directivas de ubicación disponibles, consulte [Defining The location Policy for Lync Server 2013](lync-server-2013-defining-the-location-policy.md).</span><span class="sxs-lookup"><span data-stu-id="1cfe3-110">For a list of all available location policy settings, see [Defining the location policy for Lync Server 2013](lync-server-2013-defining-the-location-policy.md).</span></span>

<span data-ttu-id="1cfe3-111">Para obtener información detallada sobre cómo crear directivas de ubicación, consulte [Create Location policies in Lync Server 2013](lync-server-2013-create-location-policies.md).</span><span class="sxs-lookup"><span data-stu-id="1cfe3-111">For details about creating location policies, see [Create location policies in Lync Server 2013](lync-server-2013-create-location-policies.md).</span></span>

## <a name="to-assign-a-per-user-location-policy-with-the-lync-server-control-panel"></a><span data-ttu-id="1cfe3-112">Para asignar una directiva de ubicación por usuario con el panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="1cfe3-112">To assign a per-user location policy with the Lync Server Control Panel</span></span>

1.  <span data-ttu-id="1cfe3-113">Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="1cfe3-113">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1cfe3-114">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1cfe3-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1cfe3-115">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="1cfe3-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1cfe3-116">En la barra de navegación izquierda, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="1cfe3-116">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="1cfe3-117">Utilice uno de los métodos siguientes para encontrar a un usuario:</span><span class="sxs-lookup"><span data-stu-id="1cfe3-117">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="1cfe3-118">En el cuadro **Buscar usuarios**, escriba la primera porción del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de la cuenta de usuario y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="1cfe3-118">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="1cfe3-119">Si ha guardado una consulta, haga clic en el icono **Abrir consulta**, utilice el cuadro de diálogo **Abrir** para recuperar la consulta (un archivo .usf) y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="1cfe3-119">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="1cfe3-120">(Opcional) Especificar criterios de búsqueda adicionales para restringir los resultados:</span><span class="sxs-lookup"><span data-stu-id="1cfe3-120">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="1cfe3-121">Haga clic en **Agregar filtro**.</span><span class="sxs-lookup"><span data-stu-id="1cfe3-121">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="1cfe3-122">Especifique la propiedad de usuario; para ello, escríbala o haga clic en la flecha de la lista desplegable para seleccionar la propiedad.</span><span class="sxs-lookup"><span data-stu-id="1cfe3-122">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="1cfe3-123">En la lista desplegable **Igual a**, haga clic en el operador (por ejemplo, **Igual a** o **No igual a**).</span><span class="sxs-lookup"><span data-stu-id="1cfe3-123">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="1cfe3-124">En función de la propiedad de usuario que haya seleccionado, especifique los criterios que desee utilizar para filtrar los resultados de búsqueda escribiendo o haciendo clic en la flecha de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="1cfe3-124">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="1cfe3-125">Para agregar cláusulas de búsqueda adicionales a la consulta, haga clic en <STRONG>Agregar filtro</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="1cfe3-125">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="1cfe3-126">Haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="1cfe3-126">Click **Find**.</span></span>

6.  <span data-ttu-id="1cfe3-127">Haga clic en un usuario en los resultados de búsqueda, haga clic en **Acción** y, a continuación, en **Asignar directivas**.</span><span class="sxs-lookup"><span data-stu-id="1cfe3-127">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="1cfe3-128">Si desea aplicar la misma directiva de ubicación por usuario a varios usuarios, seleccione los distintos usuarios en los resultados de la búsqueda, haga clic en <STRONG>Acciones</STRONG> y, a continuación, en <STRONG>Asignar directivas</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="1cfe3-128">If you want the same per-user location policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="1cfe3-129">En **Asignar directivas**, en **Directiva de ubicación**, lleve a cabo uno de los procedimientos siguientes:</span><span class="sxs-lookup"><span data-stu-id="1cfe3-129">In **Assign Policies**, under **Location policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="1cfe3-130">Debido a que hay varias directivas que puede configurar mediante el cuadro de diálogo <STRONG>asignar directivas</STRONG> , se selecciona la opción <STRONG> &lt; mantener como está &gt; </STRONG> seleccionada de forma predeterminada para cada Directiva del cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="1cfe3-130">Because there are multiple policies that you can configure by using the <STRONG>Assign Policies</STRONG> dialog box, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="1cfe3-131">Para seguir utilizando la directiva asignada anteriormente al usuario, no efectúe cambios en esta configuración.</span><span class="sxs-lookup"><span data-stu-id="1cfe3-131">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="1cfe3-132">Permita que Lync Server 2013 elija automáticamente la Directiva de nivel global o, si está definida, la Directiva de nivel de subred.</span><span class="sxs-lookup"><span data-stu-id="1cfe3-132">Allow Lync Server 2013 to automatically choose either the global-level policy or, if defined, the subnet-level policy.</span></span>
    
      - <span data-ttu-id="1cfe3-133">Haga clic en el nombre de una directiva de ubicación por usuario que haya definido anteriormente con el cmdlet **New-CsLocationPolicy**.</span><span class="sxs-lookup"><span data-stu-id="1cfe3-133">Click the name of a per-user location policy you previously defined by running the **New-CsLocationPolicy** cmdlet.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="1cfe3-134">Para ayudarle a decidir la directiva que desea asignar, tras hacer clic en el nombre de una directiva, haga clic en <STRONG>Ver</STRONG> para ver los derechos y permisos de usuarios definidos en la directiva.</span><span class="sxs-lookup"><span data-stu-id="1cfe3-134">To help you decide the policy that you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="1cfe3-135">Cuando haya terminado, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1cfe3-135">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-location-policy-by-using-lync-server-management-shell-cmdlets"></a><span data-ttu-id="1cfe3-136">Asignación de una directiva de ubicación de Per-User mediante el uso de cmdlets del shell de administración de Lync Server</span><span class="sxs-lookup"><span data-stu-id="1cfe3-136">Assigning a Per-User Location Policy by Using Lync Server Management Shell Cmdlets</span></span>

<span data-ttu-id="1cfe3-137">Puede asignar directivas de ubicación por usuario con el cmdlet Grant-CsLocationPolicy.</span><span class="sxs-lookup"><span data-stu-id="1cfe3-137">You can assign per-user location policies by using the Grant-CsLocationPolicy cmdlet.</span></span> <span data-ttu-id="1cfe3-138">Puede ejecutar este cmdlet desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1cfe3-138">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="1cfe3-139">Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server 2010 mediante PowerShell remoto" en [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="1cfe3-139">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-location-policy-to-a-single-user"></a><span data-ttu-id="1cfe3-140">Para asignar una directiva de ubicación por usuario a un único usuario</span><span class="sxs-lookup"><span data-stu-id="1cfe3-140">To assign a per-user location policy to a single user</span></span>

  - <span data-ttu-id="1cfe3-141">El comando siguiente permite asignar la directiva de ubicación por usuario RedmondLocationPolicy al usuario Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="1cfe3-141">The following command assigns the per-user location policy RedmondLocationPolicy to the user Ken Myer.</span></span>
    
        Grant-CsLocationPolicy -Identity "Ken Myer" -PolicyName "RedmondLocationPolicy"

## <a name="to-assign-a-per-user-location-policy-to-multiple-users"></a><span data-ttu-id="1cfe3-142">Para asignar una directiva de ubicación por usuario a varios usuarios</span><span class="sxs-lookup"><span data-stu-id="1cfe3-142">To assign a per-user location policy to multiple users</span></span>

  - <span data-ttu-id="1cfe3-143">Este comando permite asignar la directiva de ubicación por usuario AccountingDepartmentLocationPolicy a todos los usuarios que trabajen en el departamento de Contabilidad.</span><span class="sxs-lookup"><span data-stu-id="1cfe3-143">This command assigns the per-user location policy AccountingDepartmentLocationPolicy to all the users who work for the Accounting department.</span></span> <span data-ttu-id="1cfe3-144">Para obtener más información sobre el parámetro LdapFilter usado en este comando, consulte la documentación del cmdlet [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="1cfe3-144">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -LdapFilter "Department=Accounting" | Grant-CsLocationPolicy -PolicyName "AccountingDepartmentLocationPolicy"

## <a name="to-unassign-a-per-user-location-policy"></a><span data-ttu-id="1cfe3-145">Para cancelar la asignación de una directiva de ubicación por usuario</span><span class="sxs-lookup"><span data-stu-id="1cfe3-145">To unassign a per-user location policy</span></span>

  - <span data-ttu-id="1cfe3-p106">El comando que se describe a continuación permite cancelar la asignación de directiva de ubicación por usuario previamente asignada a Ken Myer. Una vez cancelada la asignación de la directiva por usuario, la administración del usuario Ken Myer se realizará de forma automática mediante la directiva global o, en caso de que exista, mediante la directiva de sitio local. Las directivas de sitios prevalecen sobre las directivas globales.</span><span class="sxs-lookup"><span data-stu-id="1cfe3-p106">The following command unassigns any per-user location policy previously assigned to Ken Myer. After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy. A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsLocationPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="1cfe3-149">Para obtener más información, consulte el tema de ayuda para el cmdlet [Grant-CsLocationPolicy](https://technet.microsoft.com/library/gg413049\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="1cfe3-149">For more information, see the help topic for the [Grant-CsLocationPolicy](https://technet.microsoft.com/library/gg413049\(v=ocs.15\)) cmdlet.</span></span>

