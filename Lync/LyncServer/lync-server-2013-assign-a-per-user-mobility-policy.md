---
title: 'Lync Server 2013: asignar una directiva de movilidad por usuario'
description: 'Lync Server 2013: asignar una directiva de movilidad por usuario.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user mobility policy
ms:assetid: d8bf997f-4bc7-48d3-973b-323505f55e9d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721902(v=OCS.15)
ms:contentKeyID: 49733836
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9b17c58cf3477002a7fa43035b72c77963663316
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559836"
---
# <a name="assign-a-per-user-mobility-policy-in-lync-server-2013"></a><span data-ttu-id="988d7-103">Asignar una directiva de movilidad por usuario en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="988d7-103">Assign a per-user mobility policy in Lync Server 2013</span></span>

 


<span data-ttu-id="988d7-104">La Directiva de movilidad es una de las configuraciones individuales de una cuenta de usuario que puede configurar en el panel de control de Lync Server o en el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="988d7-104">The mobility policy is one of the individual settings of a user account that you can configure in Lync Server Control Panel or Lync Server Management Shell.</span></span>

## <a name="to-assign-a-per-user-mobility-policy-with-lync-server-control-panel"></a><span data-ttu-id="988d7-105">Para asignar una directiva de movilidad por usuario con el panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="988d7-105">To assign a per-user mobility policy with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="988d7-106">Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="988d7-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="988d7-107">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="988d7-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="988d7-108">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="988d7-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="988d7-109">En la barra de navegación izquierda, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="988d7-109">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="988d7-110">Utilice uno de los métodos siguientes para encontrar a un usuario:</span><span class="sxs-lookup"><span data-stu-id="988d7-110">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="988d7-111">En el cuadro **Buscar usuarios**, escriba la primera porción del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de la cuenta de usuario y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="988d7-111">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="988d7-112">Si ha guardado una consulta, haga clic en el icono **Abrir consulta**, utilice el cuadro de diálogo **Abrir** para recuperar la consulta (un archivo .usf) y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="988d7-112">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="988d7-113">(Opcional) Especificar criterios de búsqueda adicionales para restringir los resultados:</span><span class="sxs-lookup"><span data-stu-id="988d7-113">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="988d7-114">Haga clic en **Agregar filtro**.</span><span class="sxs-lookup"><span data-stu-id="988d7-114">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="988d7-115">Especifique la propiedad de usuario; para ello, escríbala o haga clic en la flecha de la lista desplegable para seleccionar la propiedad.</span><span class="sxs-lookup"><span data-stu-id="988d7-115">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="988d7-116">En la lista desplegable **Igual a**, haga clic en el operador (por ejemplo, **Igual a** o **No igual a**).</span><span class="sxs-lookup"><span data-stu-id="988d7-116">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="988d7-117">En función de la propiedad de usuario que haya seleccionado, especifique los criterios que desee utilizar para filtrar los resultados de búsqueda escribiendo o haciendo clic en la flecha de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="988d7-117">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="988d7-118">Para agregar cláusulas de búsqueda adicionales a la consulta, haga clic en <STRONG>Agregar filtro</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="988d7-118">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="988d7-119">Haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="988d7-119">Click **Find**.</span></span>

6.  <span data-ttu-id="988d7-120">Haga clic en un usuario en los resultados de búsqueda, haga clic en **Acción** y, a continuación, en **Asignar directivas**.</span><span class="sxs-lookup"><span data-stu-id="988d7-120">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="988d7-121">Si desea que se aplique la misma directiva de movilidad por usuario a varios usuarios, seleccione varios usuarios en los resultados de la búsqueda, haga clic en <STRONG>acciones</STRONG>y, a continuación, haga clic en <STRONG>asignar directivas</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="988d7-121">If you want the same per-user mobility policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="988d7-122">En **asignar directivas**, en **Directiva de movilidad**, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="988d7-122">In **Assign Policies**, under **Mobility policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="988d7-123">Debido a que hay varias directivas que puede configurar en <STRONG>asignar directivas</STRONG>, <STRONG> &lt; mantener como está &gt; </STRONG> seleccionada de forma predeterminada para cada directiva en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="988d7-123">Because there are multiple policies that you can configure in <STRONG>Assign Policies</STRONG>, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="988d7-124">Para seguir utilizando la directiva asignada anteriormente al usuario, no efectúe cambios en esta configuración.</span><span class="sxs-lookup"><span data-stu-id="988d7-124">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="988d7-125">Seleccione esta opción **\<Automatic\>** para permitir que Lync Server 2013 elija automáticamente la Directiva de nivel global o, si está definida, la Directiva de nivel de sitio.</span><span class="sxs-lookup"><span data-stu-id="988d7-125">Select **\<Automatic\>** to allow Lync Server 2013 to automatically choose either the global-level policy or, if defined, the site-level policy.</span></span>
    
      - <span data-ttu-id="988d7-126">Haga clic en el nombre de una directiva de movilidad por usuario que haya definido anteriormente en la página **Directiva de movilidad** .</span><span class="sxs-lookup"><span data-stu-id="988d7-126">Click the name of a per-user mobility policy you previously defined on the **Mobility Policy** page.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="988d7-127">Para ayudarle a decidir la directiva que desea asignar, tras hacer clic en el nombre de una directiva, haga clic en <STRONG>Ver</STRONG> para ver los derechos y permisos de usuario definidos en la directiva.</span><span class="sxs-lookup"><span data-stu-id="988d7-127">To help you decide the policy you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="988d7-128">Cuando haya terminado, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="988d7-128">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-mobility-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="988d7-129">Asignación de una directiva de movilidad de Per-User mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="988d7-129">Assigning a Per-User Mobility Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="988d7-130">Puede asignar directivas de movilidad por usuario con Windows PowerShell y el cmdlet **Grant-CsMobilityPolicy** .</span><span class="sxs-lookup"><span data-stu-id="988d7-130">You can assign per-user mobility policies by using Windows PowerShell and the **Grant-CsMobilityPolicy** cmdlet.</span></span> <span data-ttu-id="988d7-131">Puede ejecutar este cmdlet desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="988d7-131">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="988d7-132">Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server 2010 mediante PowerShell remoto" en [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="988d7-132">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-mobility-policy-to-a-single-user"></a><span data-ttu-id="988d7-133">Para asignar una directiva de movilidad por usuario a un solo usuario</span><span class="sxs-lookup"><span data-stu-id="988d7-133">To assign a per-user mobility policy to a single user</span></span>

  - <span data-ttu-id="988d7-134">El comando siguiente asigna la Directiva de movilidad por usuario RedmondMobilityPolicy al usuario Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="988d7-134">The following command assigns the per-user mobility policy RedmondMobilityPolicy to the user Ken Myer.</span></span>
    
        Grant-CsMobilityPolicy -Identity "Ken Myer" -PolicyName "RedmondMobilityPolicy"

## <a name="to-assign-a-per-user-mobility-policy-to-multiple-users"></a><span data-ttu-id="988d7-135">Para asignar una directiva de movilidad por usuario a varios usuarios</span><span class="sxs-lookup"><span data-stu-id="988d7-135">To assign a per-user mobility policy to multiple users</span></span>

  - <span data-ttu-id="988d7-136">El comando siguiente asigna la Directiva de movilidad por usuario RedmondMobilityPolicy a todos los usuarios que están actualmente asignados a la Directiva NorthAmericaMobilityPolicy.</span><span class="sxs-lookup"><span data-stu-id="988d7-136">The following command assigns the per-user mobility policy RedmondMobilityPolicy to all the users who are currently assigned the policy NorthAmericaMobilityPolicy.</span></span> <span data-ttu-id="988d7-137">Para obtener más información sobre el parámetro filter que se usa en este comando, consulte [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="988d7-137">For details about the Filter parameter used in this command, see [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)).</span></span>
    
        Get-CsUser -Filter {MobilityPolicy -eq "NorthAmericaMobilityPolicy"} | Grant-CsMobilityPolicy -PolicyName "RedmondMobilityPolicy"

## <a name="to-unassign-a-per-user-mobility-policy"></a><span data-ttu-id="988d7-138">Para cancelar la asignación de una directiva de movilidad por usuario</span><span class="sxs-lookup"><span data-stu-id="988d7-138">To unassign a per-user mobility policy</span></span>

  - <span data-ttu-id="988d7-139">El comando siguiente desasigna cualquier directiva de movilidad por usuario asignada previamente a Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="988d7-139">The following command unassigns any per-user mobility policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="988d7-140">Una vez desasignada la directiva por usuario, Ken Myer pasará automáticamente a ser administrado mediante la directiva global (o, de existir, por la directiva de su sitio local).</span><span class="sxs-lookup"><span data-stu-id="988d7-140">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="988d7-141">Las directivas de sitio tienen prioridad sobre la directiva global.</span><span class="sxs-lookup"><span data-stu-id="988d7-141">A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsMobilityPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="988d7-142">Para obtener más información, consulte [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/hh690038\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="988d7-142">For details, see [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/hh690038\(v=ocs.15\)).</span></span>

## <a name="see-also"></a><span data-ttu-id="988d7-143">Consulte también</span><span class="sxs-lookup"><span data-stu-id="988d7-143">See Also</span></span>


[<span data-ttu-id="988d7-144">Configuración de la Directiva de movilidad en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="988d7-144">Configuring mobility policy in Lync Server 2013</span></span>](lync-server-2013-configuring-mobility-policy.md)

