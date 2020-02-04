---
title: 'Lync Server 2013: asignar una directiva de versión de cliente por usuario'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user client version policy
ms:assetid: f7e8ba2f-62dc-4e7d-8b63-682986f10240
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182607(v=OCS.15)
ms:contentKeyID: 48185868
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e509427b6d2651f84b96a96c87fbe7cfd6177a7d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738380"
---
# <a name="assign-a-per-user-client-version-policy-in-lync-server-2013"></a><span data-ttu-id="75eda-102">Asignar una directiva de versión de cliente por usuario en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75eda-102">Assign a per-user client version policy in Lync Server 2013</span></span>

 


<span data-ttu-id="75eda-103">La Directiva de versión de cliente es una de las opciones de configuración individuales de una cuenta de usuario que puede configurar en el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="75eda-103">The client version policy is one of the individual settings of a user account that you can configure in the Lync Server Control Panel.</span></span>

<span data-ttu-id="75eda-104">Implementar una o más directivas de versión de cliente por usuario es opcional.</span><span class="sxs-lookup"><span data-stu-id="75eda-104">Deploying one or more per-user client version policies is optional.</span></span> <span data-ttu-id="75eda-105">También puede implementar solo una directiva de versión de cliente global o directivas de versión de cliente de nivel de grupo o de sitio.</span><span class="sxs-lookup"><span data-stu-id="75eda-105">You can also deploy only a global-level client version policy, or site-level or pool-level client version policies.</span></span> <span data-ttu-id="75eda-106">Si implementa directivas por usuario, es preciso que las asigne explícitamente a un objeto de usuario, grupo o contacto.</span><span class="sxs-lookup"><span data-stu-id="75eda-106">If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact object.</span></span> <span data-ttu-id="75eda-107">Cuando no se asigna ninguna directiva específica de nivel de sitio, nivel de grupo o por usuario, los clientes predeterminados que tienen permitido registrarse con Lync Server 2013 son aquellos definidos en la Directiva de versión de cliente global.</span><span class="sxs-lookup"><span data-stu-id="75eda-107">When no specific site-level, pool-level, or per-user policy is assigned, the default clients that are allowed to register with Lync Server 2013 are those defined in the global-level client version policy.</span></span>

<span data-ttu-id="75eda-108">Después de crear al menos una directiva de versión de cliente por usuario, use los procedimientos de este tema para asignar la Directiva que especifica las versiones de cliente que desea permitir para registrarse en Lync Server.</span><span class="sxs-lookup"><span data-stu-id="75eda-108">After creating at least one per-user client version policy, use the procedures in this topic to assign the policy that specifies the client versions that you want to allow to register with Lync Server.</span></span>

<span data-ttu-id="75eda-109">Para obtener información detallada sobre la creación de directivas de versión de cliente por usuario, vea [especificar las aplicaciones cliente que se pueden usar para iniciar sesión en Lync Server 2013](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="75eda-109">For details about creating per-user client version policies, see [Specifying the client applications that can be used to log on to Lync Server 2013](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md).</span></span>

## <a name="to-assign-a-per-user-client-version-policy"></a><span data-ttu-id="75eda-110">Para asignar una directiva de versión de cliente por usuario</span><span class="sxs-lookup"><span data-stu-id="75eda-110">To assign a per-user client version policy</span></span>

1.  <span data-ttu-id="75eda-111">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="75eda-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="75eda-112">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="75eda-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="75eda-113">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="75eda-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="75eda-114">En la barra de navegación izquierda, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="75eda-114">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="75eda-115">Use uno de los métodos siguientes para encontrar a un usuario:</span><span class="sxs-lookup"><span data-stu-id="75eda-115">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="75eda-116">En el cuadro **Buscar usuarios**, escriba la primera porción del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de la cuenta de usuario y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="75eda-116">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="75eda-117">Si ha guardado una consulta, haga clic en el icono **Abrir consulta**, use el cuadro de diálogo **Abrir** para recuperar la consulta (un archivo .usf) y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="75eda-117">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="75eda-118">(Opcional) Especificar criterios de búsqueda adicionales para restringir los resultados:</span><span class="sxs-lookup"><span data-stu-id="75eda-118">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="75eda-119">Haga clic en **Agregar filtro**.</span><span class="sxs-lookup"><span data-stu-id="75eda-119">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="75eda-120">Especifique la propiedad de usuario. Para ello, escríbala o haga clic en la flecha de la lista desplegable para seleccionar la propiedad.</span><span class="sxs-lookup"><span data-stu-id="75eda-120">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="75eda-121">En la lista desplegable **Igual a**, haga clic en el operador (por ejemplo, **Igual a** o **No igual a**).</span><span class="sxs-lookup"><span data-stu-id="75eda-121">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="75eda-122">En función de la propiedad de usuario que haya seleccionado, especifique los criterios que desee utilizar para filtrar los resultados de búsqueda escribiendo o haciendo clic en la flecha de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="75eda-122">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="75eda-123">Para agregar cláusulas de búsqueda adicionales a la consulta, haga clic en <STRONG>Agregar filtro</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="75eda-123">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="75eda-124">Haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="75eda-124">Click **Find**.</span></span>

6.  <span data-ttu-id="75eda-125">Haga clic en un usuario en los resultados de búsqueda, haga clic en **Acción** y, a continuación, en **Asignar directivas**.</span><span class="sxs-lookup"><span data-stu-id="75eda-125">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="75eda-126">Si desea aplicar la misma directiva de versión de cliente por usuario a varios usuarios, seleccione varios usuarios en los resultados de búsqueda, haga clic en <STRONG>acciones</STRONG>y, a continuación, haga clic en <STRONG>asignar directivas</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="75eda-126">If you want the same per-user client version policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="75eda-127">En **asignar directivas**, en **Directiva de versión de cliente**, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="75eda-127">In **Assign Policies**, under **Client version policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="75eda-128">Puesto que existen varias directivas que puede configurar mediante el cuadro de diálogo <STRONG>asignar directivas</STRONG> , <STRONG> &lt;&gt; </STRONG> la opción mantener está seleccionada de forma predeterminada para todas las directivas del cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="75eda-128">Because there are multiple policies that you can configure by using the <STRONG>Assign Policies</STRONG> dialog box, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="75eda-129">Para seguir usando la directiva asignada anteriormente al usuario, no efectúe cambios en esta configuración.</span><span class="sxs-lookup"><span data-stu-id="75eda-129">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="75eda-130">Permita que Lync Server elija de forma automática la Directiva de nivel global o, si está definida, la Directiva de nivel de sitio o la Directiva de nivel de grupo.</span><span class="sxs-lookup"><span data-stu-id="75eda-130">Allow Lync Server to automatically choose either the global-level policy or, if defined, the site-level policy or pool-level policy.</span></span>
    
      - <span data-ttu-id="75eda-131">Haga clic en el nombre de una directiva de versión de cliente por usuario que haya definido previamente en la página de **Directiva de versión de cliente** .</span><span class="sxs-lookup"><span data-stu-id="75eda-131">Click the name of a per-user client version policy you previously defined on the **Client Version Policy** page.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="75eda-132">Para ayudarle a decidir la directiva que desea asignar, tras hacer clic en el nombre de una directiva, haga clic en <STRONG>Ver</STRONG> para ver los derechos y permisos de usuario definidos en la directiva.</span><span class="sxs-lookup"><span data-stu-id="75eda-132">To help you decide the policy you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="75eda-133">Cuando haya terminado, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="75eda-133">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-client-version-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="75eda-134">Asignar una directiva de versión de cliente por usuario mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="75eda-134">Assigning a Per-User Client Version Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="75eda-135">Puede asignar directivas de versión de cliente por usuario mediante el cmdlet Grant-CsClientVersionPolicy.</span><span class="sxs-lookup"><span data-stu-id="75eda-135">You can assign per-user client version policies by using the Grant-CsClientVersionPolicy cmdlet.</span></span> <span data-ttu-id="75eda-136">Puede ejecutar este cmdlet desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="75eda-136">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="75eda-137">Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.</span><span class="sxs-lookup"><span data-stu-id="75eda-137">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-client-version-policy-to-a-single-user"></a><span data-ttu-id="75eda-138">Para asignar una directiva de versión de cliente por usuario a un solo usuario</span><span class="sxs-lookup"><span data-stu-id="75eda-138">To assign a per-user client version policy to a single user</span></span>

  - <span data-ttu-id="75eda-139">El comando siguiente asigna la Directiva de versión del cliente por usuario RedmondClientVersionPolicy al usuario Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="75eda-139">The following command assigns the per-user client version policy RedmondClientVersionPolicy to the user Ken Myer.</span></span>
    
        Grant-CsClientVersionPolicy -Identity "Ken Myer" -PolicyName "RedmondClientVersionPolicy"

## <a name="to-assign-a-per-user-client-version-policy-to-multiple-users"></a><span data-ttu-id="75eda-140">Para asignar una directiva de versión de cliente por usuario a varios usuarios</span><span class="sxs-lookup"><span data-stu-id="75eda-140">To assign a per-user client version policy to multiple users</span></span>

  - <span data-ttu-id="75eda-141">Este comando asigna la Directiva de versión del cliente por usuario RedmondClientVersionPolicy a todos los usuarios que actualmente tienen asignada la Directiva de voz RedmondVoicePolicy.</span><span class="sxs-lookup"><span data-stu-id="75eda-141">This command assigns the per-user client version policy RedmondClientVersionPolicy to all the users who are currently assigned the voice policy RedmondVoicePolicy.</span></span> <span data-ttu-id="75eda-142">Para obtener más información sobre el parámetro de filtro usado en este comando, consulte la documentación del cmdlet [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="75eda-142">For more information on the Filter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -Filter {VoicePolicy -eq "RedmondVoicePolicy"} | Grant-CsClientVersionPolicy -PolicyName "RedmondClientVersionPolicy"

## <a name="to-unassign-a-per-user-client-version-policy"></a><span data-ttu-id="75eda-143">Para cancelar la asignación de una directiva de versión de cliente por usuario</span><span class="sxs-lookup"><span data-stu-id="75eda-143">To unassign a per-user client version policy</span></span>

  - <span data-ttu-id="75eda-144">El comando siguiente elimina la asignación de la Directiva de versión de cliente por usuario asignada previamente a Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="75eda-144">The following command unassigns any per-user client version policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="75eda-145">Después de que la Directiva por usuario no esté asignada, Ken Myer se administrará automáticamente mediante la directiva global, su Directiva de sitio local (si existe alguna) o la Directiva de ámbito de servicio asignada a su registrador.</span><span class="sxs-lookup"><span data-stu-id="75eda-145">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy, his local site policy (if one exists), or the service-scope policy assigned to his Registrar.</span></span> <span data-ttu-id="75eda-146">Una directiva de ámbito de servicio tiene prioridad sobre cualquier directiva del sitio y la Directiva de sitio tiene prioridad sobre la directiva global.</span><span class="sxs-lookup"><span data-stu-id="75eda-146">A service scope policy takes precedence over any site policy, and a site policy takes precedence over the global policy.</span></span>
    
        Grant-CsClientVersionPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="75eda-147">Para obtener más información, consulte el tema de ayuda para el cmdlet [Grant-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/gg412903\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="75eda-147">For more information, see the help topic for the [Grant-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/gg412903\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="75eda-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="75eda-148">See Also</span></span>


[<span data-ttu-id="75eda-149">Asignación de directivas por usuario en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75eda-149">Assigning per-user policies in Lync Server 2013</span></span>](lync-server-2013-assigning-per-user-policies.md)  
[<span data-ttu-id="75eda-150">Administrar dispositivos, teléfonos y aplicaciones cliente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75eda-150">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)

