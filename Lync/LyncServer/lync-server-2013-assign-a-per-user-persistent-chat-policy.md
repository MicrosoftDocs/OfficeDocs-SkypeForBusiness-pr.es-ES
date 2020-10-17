---
title: 'Lync Server 2013: asignar una directiva de chat persistente por usuario'
description: 'Lync Server 2013: asignar una directiva de chat persistente por usuario.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user Persistent Chat policy
ms:assetid: e22168f2-fde1-4f0a-b194-1fc881436822
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721908(v=OCS.15)
ms:contentKeyID: 49733842
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 637f1947fff7f4e919e5f9c252c047b2d0e60392
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563606"
---
# <a name="assign-a-per-user-persistent-chat-policy-in-lync-server-2013"></a><span data-ttu-id="470bb-103">Asignar una directiva de chat persistente por usuario en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="470bb-103">Assign a per-user Persistent Chat policy in Lync Server 2013</span></span>

 


<span data-ttu-id="470bb-104">Puede asignar una directiva de chat persistente por usuario a través del panel de control de Lync Server 2013 o el shell de administración de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="470bb-104">You can assign a per-user persistent chat policy with either Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="470bb-105">Para obtener información sobre cómo crear directivas de usuario para el servidor de chat persistente, consulte [crear una directiva de usuario para chat persistente en Lync Server 2013](lync-server-2013-create-a-user-policy-for-persistent-chat.md).</span><span class="sxs-lookup"><span data-stu-id="470bb-105">For details on creating user policies for Persistent Chat Server, see [Create a user policy for Persistent Chat in Lync Server 2013](lync-server-2013-create-a-user-policy-for-persistent-chat.md).</span></span>

## <a name="to-assign-a-per-user-persistent-chat-policy-with-lync-server-control-panel"></a><span data-ttu-id="470bb-106">Para asignar una directiva de chat persistente por usuario con el panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="470bb-106">To assign a per-user persistent chat policy with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="470bb-107">Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="470bb-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="470bb-108">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="470bb-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="470bb-109">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="470bb-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="470bb-110">En la barra de navegación izquierda, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="470bb-110">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="470bb-111">Utilice uno de los métodos siguientes para encontrar a un usuario:</span><span class="sxs-lookup"><span data-stu-id="470bb-111">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="470bb-112">En el cuadro **Buscar usuarios**, escriba la primera porción del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de la cuenta de usuario y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="470bb-112">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="470bb-113">Si ha guardado una consulta, haga clic en el icono **Abrir consulta**, utilice el cuadro de diálogo **Abrir** para recuperar la consulta (un archivo .usf) y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="470bb-113">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="470bb-114">(Opcional) Especificar criterios de búsqueda adicionales para restringir los resultados:</span><span class="sxs-lookup"><span data-stu-id="470bb-114">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="470bb-115">Haga clic en **Agregar filtro**.</span><span class="sxs-lookup"><span data-stu-id="470bb-115">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="470bb-116">Especifique la propiedad de usuario; para ello, escríbala o haga clic en la flecha de la lista desplegable para seleccionar la propiedad.</span><span class="sxs-lookup"><span data-stu-id="470bb-116">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="470bb-117">En la lista desplegable **Igual a**, haga clic en el operador (por ejemplo, **Igual a** o **No igual a**).</span><span class="sxs-lookup"><span data-stu-id="470bb-117">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="470bb-118">En función de la propiedad de usuario que haya seleccionado, especifique los criterios que desee utilizar para filtrar los resultados de búsqueda escribiendo o haciendo clic en la flecha de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="470bb-118">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="470bb-119">Para agregar cláusulas de búsqueda adicionales a la consulta, haga clic en <STRONG>Agregar filtro</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="470bb-119">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="470bb-120">Haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="470bb-120">Click **Find**.</span></span>

6.  <span data-ttu-id="470bb-121">Haga clic en un usuario en los resultados de búsqueda, haga clic en **Acción** y después en **Asignar directivas**.</span><span class="sxs-lookup"><span data-stu-id="470bb-121">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="470bb-122">Si desea aplicar la misma directiva persistente por usuario a varios usuarios, seleccione los distintos usuarios en los resultados de la búsqueda, haga clic en <STRONG>Acciones</STRONG> y después en <STRONG>Asignar directivas</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="470bb-122">If you want the same per-user persistent Chat policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="470bb-123">En **Asignar directivas**, en **Directiva de chat persistente**, lleve a cabo uno de los procedimientos siguientes:</span><span class="sxs-lookup"><span data-stu-id="470bb-123">In **Assign Policies**, under **Persistent Chat policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="470bb-124">Debido a que hay varias directivas que puede configurar mediante el cuadro de diálogo <STRONG>asignar directivas</STRONG> , se selecciona la opción <STRONG> &lt; mantener como está &gt; </STRONG> seleccionada de forma predeterminada para cada Directiva del cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="470bb-124">Because there are multiple policies that you can configure by using the <STRONG>Assign Policies</STRONG> dialog box, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="470bb-125">Para seguir utilizando la directiva asignada anteriormente al usuario, no efectúe cambios en esta configuración.</span><span class="sxs-lookup"><span data-stu-id="470bb-125">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="470bb-126">Seleccione esta opción **\<Automatic\>** para permitir que Lync Server 2013 elija automáticamente la Directiva de nivel global o, si está definida, la Directiva de nivel de sitio.</span><span class="sxs-lookup"><span data-stu-id="470bb-126">Select **\<Automatic\>** to allow Lync Server 2013 to automatically choose either the global-level policy or, if defined, the site-level policy.</span></span>
    
      - <span data-ttu-id="470bb-127">Haga clic en el nombre de una directiva de chat persistente por usuario que haya definido anteriormente en la página **Directiva de chat persistente**.</span><span class="sxs-lookup"><span data-stu-id="470bb-127">Click the name of a per-user Persistent Chat policy you previously defined on the **Persistent Chat Policy** page.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="470bb-128">Para que le sea más fácil decidir la directiva que desea asignar, tras hacer clic en el nombre de una directiva, haga clic en <STRONG>Ver</STRONG> para ver los derechos y permisos de usuario definidos en la directiva.</span><span class="sxs-lookup"><span data-stu-id="470bb-128">To help you decide the policy you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="470bb-129">Cuando haya terminado, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="470bb-129">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-persistent-chat-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="470bb-130">Asignación de una Per-User una directiva de chat persistente mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="470bb-130">Assigning a Per-User Persistent Chat Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="470bb-131">También puede asignar directivas de chat persistente por usuario mediante el cmdlet **Grant-CsPersistentChatPolicy** .</span><span class="sxs-lookup"><span data-stu-id="470bb-131">You can also assign per-user persistent chat policies by using the **Grant-CsPersistentChatPolicy** cmdlet.</span></span> <span data-ttu-id="470bb-132">Puede ejecutar este cmdlet desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="470bb-132">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="470bb-133">Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server 2010 mediante PowerShell remoto" en [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="470bb-133">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-persistent-chat-policy-to-a-single-user"></a><span data-ttu-id="470bb-134">Para asignar una directiva de chat persistente por usuario a un solo usuario</span><span class="sxs-lookup"><span data-stu-id="470bb-134">To assign a per-user persistent chat policy to a single user</span></span>

  - <span data-ttu-id="470bb-135">El comando siguiente asigna la directiva de chat persistente por usuario RedmondPersistentChatPolicy al usuario Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="470bb-135">The following command assigns the per-user Persistent Chat policy RedmondPersistentChatPolicy to the user Ken Myer.</span></span>
    
        Grant-CsPersistentChatPolicy -Identity "Ken Myer" -PolicyName "RedmondPersistentChatPolicy"

## <a name="to-assign-a-per-user-persistent-chat-policy-to-multiple-users"></a><span data-ttu-id="470bb-136">Para asignar una directiva de chat persistente por usuario a varios usuarios</span><span class="sxs-lookup"><span data-stu-id="470bb-136">To assign a per-user persistent chat policy to multiple users</span></span>

  - <span data-ttu-id="470bb-137">Este comando asigna la directiva de chat persistente por usuario RedmondUsersPersistentChatPolicy a todos los usuarios que trabajan para el departamento de TI.</span><span class="sxs-lookup"><span data-stu-id="470bb-137">This command assigns the per-user Persistent Chat policy RedmondUsersPersistentChatPolicy to all the users who work for the IT department.</span></span> <span data-ttu-id="470bb-138">Para obtener más información sobre el parámetro LdapFilter usado en este comando, consulte la documentación del cmdlet [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="470bb-138">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -LdapFilter "Department=IT" | Grant-CsPersistentChatPolicy -PolicyName "RedmondUsersPersistentChatPolicy"

## <a name="to-unassign-a-per-user-persistent-chat-policy"></a><span data-ttu-id="470bb-139">Para cancelar la asignación de una directiva de chat persistente por usuario</span><span class="sxs-lookup"><span data-stu-id="470bb-139">To unassign a per-user persistent chat policy</span></span>

  - <span data-ttu-id="470bb-p106">El comando siguiente quita la asignación de las directivas de chat persistente por usuario asignadas previamente a Ken Myer. Después de quitar la asignación de la directiva por usuario, se usará automáticamente la directiva global o la directiva del sitio local, si existe, para administrar a Ken Myer. La directiva de sitio tiene prioridad sobre la directiva global.</span><span class="sxs-lookup"><span data-stu-id="470bb-p106">The following command unassigns any per-user Persistent Chat policy previously assigned to Ken Myer. After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy. A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsPersistentChatPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="470bb-143">Para obtener más información, consulte el tema de ayuda para el cmdlet [Grant-CsPersistentChatPolicy](https://technet.microsoft.com/library/jj204907\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="470bb-143">For more information, see the help topic for the [Grant-CsPersistentChatPolicy](https://technet.microsoft.com/library/jj204907\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="470bb-144">Consulte también</span><span class="sxs-lookup"><span data-stu-id="470bb-144">See Also</span></span>


[<span data-ttu-id="470bb-145">Crear una directiva de usuario para chat persistente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="470bb-145">Create a user policy for Persistent Chat in Lync Server 2013</span></span>](lync-server-2013-create-a-user-policy-for-persistent-chat.md)

