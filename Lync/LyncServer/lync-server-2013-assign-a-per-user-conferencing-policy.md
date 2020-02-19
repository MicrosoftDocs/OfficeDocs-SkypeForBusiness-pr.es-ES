---
title: 'Lync Server 2013: asignar una directiva de conferencia por usuario'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user conferencing policy
ms:assetid: 72f12c72-65f7-44fe-ab81-0f57cb2f87d1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521015(v=OCS.15)
ms:contentKeyID: 48184475
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47419dfde4bf41b0edfccb2bce23393f04c49a3d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134456"
---
# <a name="assign-a-per-user-conferencing-policy-in-lync-server-2013"></a><span data-ttu-id="4a181-102">Asignar una directiva de conferencia por usuario en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4a181-102">Assign a per-user conferencing policy in Lync Server 2013</span></span>

 


<span data-ttu-id="4a181-103">La Directiva de conferencia es una de las configuraciones individuales de una cuenta de usuario que se puede configurar en el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4a181-103">The conferencing policy is one of the individual settings of a user account that you can configure in Lync Server Control Panel.</span></span>

<span data-ttu-id="4a181-p101">La implementación de una o varias directivas de conferencia por usuario es opcional. También puede implementar solamente una directiva de conferencia de nivel global o una directiva de conferencia de nivel de sitio. Si no implementa directivas por usuario, es preciso que las asigne explícitamente a objetos de usuario, grupo o contacto. En el caso de que no se haya asignado una directiva específica de nivel de sitio o por usuario, los derechos y permisos de conferencia se predeterminan automáticamente de acuerdo con los definidos en la directiva de conferencia de nivel global.</span><span class="sxs-lookup"><span data-stu-id="4a181-p101">Deploying one or more per-user conferencing policies is optional. You can also deploy only a global-level conferencing policy or site-level conferencing policy. If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact objects. Conferencing user rights and permissions automatically default to those defined in the global-level conferencing policy when no specific site-level or per-user policy is assigned.</span></span>

<span data-ttu-id="4a181-108">Después de crear al menos una directiva de conferencia por usuario, use los procedimientos de este tema para asignar la directiva que especifica los permisos y derechos de usuario que desea que aplique el servidor a las reuniones organizadas por un usuario determinado.</span><span class="sxs-lookup"><span data-stu-id="4a181-108">After creating at least one per-user conferencing policy, use the procedures in this topic to assign the policy that specifies the user rights and permissions that you want the server to grant to the meetings organized by a particular user.</span></span>

<span data-ttu-id="4a181-109">Para obtener una lista de todas las opciones de configuración de directivas de conferencia disponibles, consulte [referencia de configuración de directivas de conferencia para Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span><span class="sxs-lookup"><span data-stu-id="4a181-109">For a list of all available conferencing policy settings, see [Conferencing policy settings reference for Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span></span>

<span data-ttu-id="4a181-110">Para obtener más información sobre cómo crear directivas de conferencia, consulte [Create or Modify a Conferencing Policy in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).</span><span class="sxs-lookup"><span data-stu-id="4a181-110">For details about creating conferencing policies, see [Create or modify a conferencing policy in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).</span></span>

## <a name="to-assign-a-per-user-conferencing-policy"></a><span data-ttu-id="4a181-111">Asignación de una directiva de conferencia por usuario</span><span class="sxs-lookup"><span data-stu-id="4a181-111">To assign a per-user conferencing policy</span></span>

1.  <span data-ttu-id="4a181-112">Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="4a181-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4a181-113">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4a181-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4a181-114">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="4a181-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4a181-115">En la barra de navegación izquierda, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="4a181-115">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="4a181-116">Utilice uno de los métodos siguientes para encontrar a un usuario:</span><span class="sxs-lookup"><span data-stu-id="4a181-116">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="4a181-117">En el cuadro **Buscar usuarios**, escriba la primera porción del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de la cuenta de usuario y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="4a181-117">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="4a181-118">Si ha guardado una consulta, haga clic en el icono **Abrir consulta**, utilice el cuadro de diálogo **Abrir** para recuperar la consulta (un archivo .usf) y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="4a181-118">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="4a181-119">(Opcional) Especificar criterios de búsqueda adicionales para restringir los resultados:</span><span class="sxs-lookup"><span data-stu-id="4a181-119">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="4a181-120">Haga clic en **Agregar filtro**.</span><span class="sxs-lookup"><span data-stu-id="4a181-120">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="4a181-121">Especifique la propiedad de usuario; para ello, escríbala o haga clic en la flecha de la lista desplegable para seleccionar la propiedad.</span><span class="sxs-lookup"><span data-stu-id="4a181-121">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="4a181-122">En la lista desplegable **Igual a**, haga clic en el operador (por ejemplo, **Igual a** o **No igual a**).</span><span class="sxs-lookup"><span data-stu-id="4a181-122">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="4a181-123">En función de la propiedad de usuario que haya seleccionado, especifique los criterios que desee utilizar para filtrar los resultados de búsqueda escribiendo o haciendo clic en la flecha de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="4a181-123">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="4a181-124">Para agregar cláusulas de búsqueda adicionales a la consulta, haga clic en <STRONG>Agregar filtro</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="4a181-124">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="4a181-125">Haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="4a181-125">Click **Find**.</span></span>

6.  <span data-ttu-id="4a181-126">Haga clic en un usuario en los resultados de búsqueda, haga clic en **Acción** y, a continuación, en **Asignar directivas**.</span><span class="sxs-lookup"><span data-stu-id="4a181-126">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="4a181-127">Si desea aplicar la misma directiva de conferencia por usuario a varios usuarios, seleccione los distintos usuarios en los resultados de la búsqueda, haga clic en <STRONG>Acciones</STRONG> y, a continuación, en <STRONG>Asignar directivas</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="4a181-127">If you want the same per-user conferencing policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="4a181-128">En **Asignar directivas**, en **Directiva de conferencia**, lleve a cabo uno de los siguientes procedimientos:</span><span class="sxs-lookup"><span data-stu-id="4a181-128">In **Assign Policies**, under **Conferencing policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="4a181-129">Debido a que hay varias directivas que puede configurar en <STRONG>asignar directivas</STRONG>, <STRONG> &lt;mantener como está&gt; </STRONG> seleccionada de forma predeterminada para cada directiva en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="4a181-129">Because there are multiple policies that you can configure in <STRONG>Assign Policies</STRONG>, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="4a181-130">Para seguir utilizando la directiva asignada anteriormente al usuario, no efectúe cambios en esta configuración.</span><span class="sxs-lookup"><span data-stu-id="4a181-130">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="4a181-131">Seleccione \*\* \<automático\> \*\* para permitir que Lync Server 2013 elija automáticamente la Directiva de nivel global o, si está definida, la Directiva de nivel de sitio.</span><span class="sxs-lookup"><span data-stu-id="4a181-131">Select **\<Automatic\>** to allow Lync Server 2013 to automatically choose either the global-level policy or, if defined, the site-level policy.</span></span>
    
      - <span data-ttu-id="4a181-132">Haga clic en el nombre de una directiva de conferencia por usuario que haya definido anteriormente en la página **Directiva de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="4a181-132">Click the name of a per-user conferencing policy you previously defined on the **Conferencing Policy** page.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="4a181-133">Para ayudarle a decidir la directiva que desea asignar, tras hacer clic en el nombre de una directiva, haga clic en <STRONG>Ver</STRONG> para ver los derechos y permisos de usuario definidos en la directiva.</span><span class="sxs-lookup"><span data-stu-id="4a181-133">To help you decide the policy you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="4a181-134">Cuando haya terminado, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4a181-134">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-conferencing-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="4a181-135">Asignar una directiva de conferencia por usuario mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4a181-135">Assigning a Per-User Conferencing Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="4a181-136">Las directivas de conferencia por usuario se pueden asignar mediante Windows PowerShell y el cmdlet Grant-CsConferencingPolicy.</span><span class="sxs-lookup"><span data-stu-id="4a181-136">Per-user conferencing policies can be assigned by using Windows PowerShell and the Grant-CsConferencingPolicy cmdlet.</span></span> <span data-ttu-id="4a181-137">Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4a181-137">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="4a181-138">Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.</span><span class="sxs-lookup"><span data-stu-id="4a181-138">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-conferencing-policy-to-a-single-user"></a><span data-ttu-id="4a181-139">Para asignar una directiva de conferencia por usuario a un solo usuario</span><span class="sxs-lookup"><span data-stu-id="4a181-139">To assign a per-user conferencing policy to a single user</span></span>

  - <span data-ttu-id="4a181-140">El comando siguiente asigna la directiva de conferencia por usuario RedmondConferencingPolicy al usuario Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="4a181-140">The following command assigns the per-user conferencing policy RedmondConferencingPolicy to the user Ken Myer.</span></span>
    
        Grant-CsConferencingPolicy -Identity "Ken Myer" -PolicyName "RedmondConferencingPolicy"

## <a name="to-assign-a-per-user-conferencing-policy-to-multiple-users"></a><span data-ttu-id="4a181-141">Para asignar una directiva de conferencia por usuario a varios usuarios</span><span class="sxs-lookup"><span data-stu-id="4a181-141">To assign a per-user conferencing policy to multiple users</span></span>

  - <span data-ttu-id="4a181-142">Este comando asigna la directiva de conferencia por usuario HRConferencingPolicy a todos los usuarios que trabajan en el departamento de recursos humanos.</span><span class="sxs-lookup"><span data-stu-id="4a181-142">This command assigns the per-user conferencing policy HRConferencingPolicy to all the users who work for the Human Resources department.</span></span> <span data-ttu-id="4a181-143">Para obtener más información sobre el parámetro LdapFilter usado en este comando, consulte la documentación del cmdlet [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="4a181-143">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -LdapFilter "Department=Human Resources" | Grant-CsConferencingPolicy -PolicyName "HRConferencingPolicy"

## <a name="to-unassign-a-per-user-conferencing-policy"></a><span data-ttu-id="4a181-144">Para cancelar la asignación de una directiva de conferencia por usuario</span><span class="sxs-lookup"><span data-stu-id="4a181-144">To unassign a per-user conferencing policy</span></span>

  - <span data-ttu-id="4a181-p106">El comando siguiente anula la asignación de una directiva de conferencia por usuario que se había asignado a Ken Myer. Una vez anulada la asignación, el usuario Ken Myer será administrado por la directiva global o, si la hay, por su directiva de sitio local. Las directivas de sitio tienen preferencia sobre la directiva global.</span><span class="sxs-lookup"><span data-stu-id="4a181-p106">The following command unassigns any per-user conferencing policy previously assigned to Ken Myer. After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy. A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsConferencingPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="4a181-148">Para obtener más información, consulte el tema de ayuda para el cmdlet [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/gg425937\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="4a181-148">For more information, see the help topic for the [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/gg425937\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="4a181-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="4a181-149">See Also</span></span>


[<span data-ttu-id="4a181-150">Crear o modificar una directiva de conferencia en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4a181-150">Create or modify a conferencing policy in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-conferencing-policy.md)  


[<span data-ttu-id="4a181-151">Asignación de directivas por usuario en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4a181-151">Assigning per-user policies in Lync Server 2013</span></span>](lync-server-2013-assigning-per-user-policies.md)

