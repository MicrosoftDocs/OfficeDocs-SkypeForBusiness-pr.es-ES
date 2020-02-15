---
title: 'Lync Server 2013: asignar una directiva de PIN por usuario'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user PIN policy
ms:assetid: d8211c64-0b63-4193-a074-673da7d14287
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182594(v=OCS.15)
ms:contentKeyID: 48185475
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9523794808ca3b689cf1f3213c1f4ad657c83c25
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030123"
---
# <a name="assign-a-per-user-pin-policy-in-lync-server-2013"></a><span data-ttu-id="f46e0-102">Asignar una directiva de PIN por usuario en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f46e0-102">Assign a per-user PIN policy in Lync Server 2013</span></span>

 


<span data-ttu-id="f46e0-103">La Directiva de número de identificación personal (PIN) de conferencia de acceso telefónico local es una de las configuraciones individuales de una cuenta de usuario que se puede configurar en el panel de control de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f46e0-103">The dial-in conferencing personal identification number (PIN) policy is one of the individual settings of a user account that can be configured in the Lync Server 2013 Control Panel.</span></span>

<span data-ttu-id="f46e0-p101">La implementación de una o más directivas de PIN por usuario es opcional. Asimismo, puede implementar solamente una directiva de PIN a nivel global o a nivel de sitio. Si implementa directivas por usuario, es preciso que las asigne explícitamente a un objeto de usuario, grupo o contacto. Los derechos y permisos de usuario para el uso de PIN de conferencia de acceso telefónico local pasan a ser, de forma predeterminada, los definidos en la directiva de PIN de nivel global cuando no se haya asignado una directiva específica de nivel de sitio o por usuario.</span><span class="sxs-lookup"><span data-stu-id="f46e0-p101">Deploying one or more per-user PIN policies is optional. You can also deploy only a global-level PIN policy or site-level PIN policy. If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact object. User rights and permissions regarding the use of PINs for dial-in conferencing automatically default to those defined in the global-level PIN policy when no specific site-level or per-user policy is assigned.</span></span>

<span data-ttu-id="f46e0-108">Tras crear al menos una directiva de PIN por usuario, emplee los procedimientos de este tema para asignar la directiva que especifique las restricciones que desee que imponga el servidor en los PIN que haya creado y usado un usuario en particular.</span><span class="sxs-lookup"><span data-stu-id="f46e0-108">After creating at least one per-user PIN policy, use the procedures in this topic to assign the policy that specifies the constraints you want the server to impose on the PINs created by and used by a particular user.</span></span>

<span data-ttu-id="f46e0-109">Para obtener información detallada sobre cómo crear directivas de PIN de conferencia de acceso telefónico local por usuario, vea [crear o modificar la configuración de PIN de conferencia de acceso telefónico local en Lync Server 2013 para un sitio o grupo de usuarios](lync-server-2013-create-or-modify-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md).</span><span class="sxs-lookup"><span data-stu-id="f46e0-109">For details about creating per-user dial-in conferencing PIN policies, see [Create or modify dial-in conferencing PIN settings in Lync Server 2013 for a site or group of users](lync-server-2013-create-or-modify-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md).</span></span>

## <a name="to-assign-a-per-user-pin-policy"></a><span data-ttu-id="f46e0-110">Para asignar una directiva de PIN por usuario</span><span class="sxs-lookup"><span data-stu-id="f46e0-110">To assign a per-user PIN policy</span></span>

1.  <span data-ttu-id="f46e0-111">Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="f46e0-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f46e0-112">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f46e0-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f46e0-113">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f46e0-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f46e0-114">En la barra de navegación izquierda, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="f46e0-114">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="f46e0-115">Utilice uno de los métodos siguientes para encontrar a un usuario:</span><span class="sxs-lookup"><span data-stu-id="f46e0-115">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="f46e0-116">En el cuadro **Buscar usuarios**, escriba la primera porción del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de la cuenta de usuario y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="f46e0-116">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="f46e0-117">Si ha guardado una consulta, haga clic en el icono **Abrir consulta**, utilice el cuadro de diálogo **Abrir** para recuperar la consulta (un archivo .usf) y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="f46e0-117">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="f46e0-118">(Opcional) Especificar criterios de búsqueda adicionales para restringir los resultados:</span><span class="sxs-lookup"><span data-stu-id="f46e0-118">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="f46e0-119">Haga clic en **Agregar filtro**.</span><span class="sxs-lookup"><span data-stu-id="f46e0-119">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="f46e0-120">Especifique la propiedad de usuario; para ello, escríbala o haga clic en la flecha de la lista desplegable para seleccionar la propiedad.</span><span class="sxs-lookup"><span data-stu-id="f46e0-120">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="f46e0-121">En la lista desplegable **Igual a**, haga clic en el operador (por ejemplo, **Igual a** o **No igual a**).</span><span class="sxs-lookup"><span data-stu-id="f46e0-121">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="f46e0-122">En función de la propiedad de usuario que haya seleccionado, especifique los criterios que desee utilizar para filtrar los resultados de búsqueda escribiendo o haciendo clic en la flecha de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="f46e0-122">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="f46e0-123">Para agregar cláusulas de búsqueda adicionales a la consulta, haga clic en <STRONG>Agregar filtro</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="f46e0-123">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="f46e0-124">Haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="f46e0-124">Click **Find**.</span></span>

6.  <span data-ttu-id="f46e0-125">Haga clic en un usuario en los resultados de búsqueda, haga clic en **Acción** y, a continuación, en **Asignar directivas**.</span><span class="sxs-lookup"><span data-stu-id="f46e0-125">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="f46e0-126">Si desea aplicar la misma directiva de PIN por usuario a varios usuarios, seleccione los distintos usuarios en los resultados de la búsqueda, haga clic en <STRONG>Acciones</STRONG> y después en <STRONG>Asignar directivas</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="f46e0-126">If you want the same per-user PIN policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="f46e0-127">En **Asignar directivas**, en **Directiva de PIN**, realice uno de los procedimientos siguientes:</span><span class="sxs-lookup"><span data-stu-id="f46e0-127">In **Assign Policies**, under **PIN policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="f46e0-128">Debido a que hay varias directivas que puede configurar mediante el cuadro de diálogo <STRONG>asignar directivas</STRONG> , <STRONG> &lt;se selecciona la&gt; opción mantener como está</STRONG> seleccionada de forma predeterminada para cada Directiva del cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="f46e0-128">Because there are multiple policies that you can configure by using the <STRONG>Assign Policies</STRONG> dialog box, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="f46e0-129">Para seguir utilizando la directiva asignada anteriormente al usuario, no efectúe cambios en esta configuración.</span><span class="sxs-lookup"><span data-stu-id="f46e0-129">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="f46e0-130">Permita que Lync Server 2013 elija automáticamente la Directiva de nivel global o, si está definida, la Directiva de nivel de sitio.</span><span class="sxs-lookup"><span data-stu-id="f46e0-130">Allow Lync Server 2013 to automatically choose either the global-level policy or, if defined, the site-level policy.</span></span>
    
      - <span data-ttu-id="f46e0-131">Haga clic en el nombre de una directiva de PIN por usuario que haya definido anteriormente en la página **Directiva de PIN**.</span><span class="sxs-lookup"><span data-stu-id="f46e0-131">Click the name of a per-user PIN policy you previously defined on the **PIN Policy** page.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="f46e0-132">Para que le sea más fácil decidir la directiva que desea asignar, tras hacer clic en el nombre de una directiva, haga clic en <STRONG>Ver</STRONG> para ver los derechos y permisos de usuario definidos en la directiva.</span><span class="sxs-lookup"><span data-stu-id="f46e0-132">To help you decide the policy you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="f46e0-133">Cuando haya terminado, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f46e0-133">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-pin-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="f46e0-134">Asignar una directiva de PIN por usuario mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f46e0-134">Assigning a Per-User PIN Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="f46e0-135">Puede asignar directivas de PIN por usuario con Windows PowerShell y el cmdlet **Grant-CsPinPolicy** .</span><span class="sxs-lookup"><span data-stu-id="f46e0-135">You can assign per-user PIN policies by using Windows PowerShell and the **Grant-CsPinPolicy** cmdlet.</span></span> <span data-ttu-id="f46e0-136">Puede ejecutar este cmdlet desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f46e0-136">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="f46e0-137">Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.</span><span class="sxs-lookup"><span data-stu-id="f46e0-137">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-pin-policy-to-a-single-user"></a><span data-ttu-id="f46e0-138">Asignar una directiva de PIN por usuario a un único usuario</span><span class="sxs-lookup"><span data-stu-id="f46e0-138">To assign a per-user PIN policy to a single user</span></span>

  - <span data-ttu-id="f46e0-139">El comando siguiente asigna la directiva de PIN por usuario RedmondPinPolicy al usuario Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="f46e0-139">The following command assigns the per-user PIN policy RedmondPinPolicy to the user Ken Myer.</span></span>
    
        Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName "RedmondPinPolicy"

## <a name="to-assign-a-per-user-pin-policy-to-multiple-users"></a><span data-ttu-id="f46e0-140">Asignar una directiva de PIN por usuario a varios usuarios</span><span class="sxs-lookup"><span data-stu-id="f46e0-140">To assign a per-user PIN policy to multiple users</span></span>

  - <span data-ttu-id="f46e0-141">El comando siguiente asigna la directiva de PIN por usuario RedmondUsersPinPolicy a todos los usuarios que trabajan en la ciudad de Redmond.</span><span class="sxs-lookup"><span data-stu-id="f46e0-141">The following command assigns the per-user PIN policy RedmondUsersPinPolicy to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="f46e0-142">Para obtener más información sobre el parámetro LdapFilter usado en este comando, consulte [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="f46e0-142">For details about the LdapFilter parameter used in this command, see [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)).</span></span>
    
        Get-CsUser -LdapFilter "l=Redmond" | Grant-CsPinPolicy -PolicyName "RedmondUsersPinPolicy"

## <a name="to-unassign-a-per-user-pin-policy"></a><span data-ttu-id="f46e0-143">Quitar la asignación de una directiva de PIN por usuario</span><span class="sxs-lookup"><span data-stu-id="f46e0-143">To unassign a per-user PIN policy</span></span>

  - <span data-ttu-id="f46e0-p106">El comando siguiente quita la asignación de las directivas de PIN por usuario asignadas previamente a Ken Myer. Después de quitar la asignación de la directiva por usuario, se usará automáticamente la directiva global o la directiva del sitio local, si existe, para administrar a Ken Myer. La directiva de sitio tiene prioridad sobre la directiva global.</span><span class="sxs-lookup"><span data-stu-id="f46e0-p106">The following command unassigns any per-user PIN policy previously assigned to Ken Myer. After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy. A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="f46e0-147">Para obtener más información, consulte [Grant-CsPinPolicy](https://technet.microsoft.com/library/gg398871\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="f46e0-147">For details, see [Grant-CsPinPolicy](https://technet.microsoft.com/library/gg398871\(v=ocs.15\)).</span></span>

## <a name="see-also"></a><span data-ttu-id="f46e0-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="f46e0-148">See Also</span></span>


[<span data-ttu-id="f46e0-149">Crear una directiva de PIN nueva en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f46e0-149">Create a new PIN policy in Lync Server 2013</span></span>](lync-server-2013-create-a-new-pin-policy.md)  


[<span data-ttu-id="f46e0-150">Asignación de directivas por usuario en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f46e0-150">Assigning per-user policies in Lync Server 2013</span></span>](lync-server-2013-assigning-per-user-policies.md)

