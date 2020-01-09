---
title: Asignar una directiva de PIN por usuario en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d8211c64-0b63-4193-a074-673da7d14287
description: 'Resumen: haga una copia de los certificados de AV y OAuth para Skype empresarial Server.'
ms.openlocfilehash: 7591464d55970a9aee4fb1f7ddbb28c2efbac601
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992727"
---
# <a name="assign-a-per-user-pin-policy-in-skype-for-business-server"></a><span data-ttu-id="5c3bf-103">Asignar una directiva de PIN por usuario en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="5c3bf-103">Assign a per-user PIN policy in Skype for Business Server</span></span>

<span data-ttu-id="5c3bf-104">**Resumen:** Ensayar los certificados de AV y OAuth para Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="5c3bf-104">**Summary:** Stage AV and OAuth certificates for Skype for Business Server.</span></span>
  
<span data-ttu-id="5c3bf-105">La Directiva número de identificación personal (PIN) de la Conferencia de acceso telefónico local es una de las opciones de configuración individuales de una cuenta de usuario que se puede configurar en el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="5c3bf-105">The dial-in conferencing personal identification number (PIN) policy is one of the individual settings of a user account that can be configured in the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="5c3bf-p101">La implementación de una o más directivas de PIN por usuario es opcional. Asimismo, puede implementar solamente una directiva de PIN a nivel global o a nivel de sitio. Si implementa directivas por usuario, es preciso que las asigne explícitamente a un objeto de usuario, grupo o contacto. Los derechos y permisos de usuario para el uso de PIN de conferencia de acceso telefónico local pasan a ser, de forma predeterminada, los definidos en la directiva de PIN de nivel global cuando no se haya asignado una directiva específica de nivel de sitio o por usuario.</span><span class="sxs-lookup"><span data-stu-id="5c3bf-p101">Deploying one or more per-user PIN policies is optional. You can also deploy only a global-level PIN policy or site-level PIN policy. If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact object. User rights and permissions regarding the use of PINs for dial-in conferencing automatically default to those defined in the global-level PIN policy when no specific site-level or per-user policy is assigned.</span></span>
  
<span data-ttu-id="5c3bf-110">Tras crear al menos una directiva de PIN por usuario, emplee los procedimientos de este tema para asignar la directiva que especifique las restricciones que desee que imponga el servidor en los PIN que haya creado y usado un usuario en particular.</span><span class="sxs-lookup"><span data-stu-id="5c3bf-110">After creating at least one per-user PIN policy, use the procedures in this topic to assign the policy that specifies the constraints you want the server to impose on the PINs created by and used by a particular user.</span></span>
  
### <a name="to-assign-a-per-user-pin-policy"></a><span data-ttu-id="5c3bf-111">Para asignar una directiva de PIN por usuario</span><span class="sxs-lookup"><span data-stu-id="5c3bf-111">To assign a per-user PIN policy</span></span>

1. <span data-ttu-id="5c3bf-112">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="5c3bf-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="5c3bf-113">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="5c3bf-113">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="5c3bf-114">En la barra de navegación izquierda, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="5c3bf-114">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="5c3bf-115">Use uno de los métodos siguientes para encontrar a un usuario:</span><span class="sxs-lookup"><span data-stu-id="5c3bf-115">Use one of the following methods to locate a user:</span></span>
    
   - <span data-ttu-id="5c3bf-116">En el cuadro **Buscar usuarios**, escriba la primera porción del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de la cuenta de usuario y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="5c3bf-116">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
   - <span data-ttu-id="5c3bf-117">Si ha guardado una consulta, haga clic en el icono **Abrir consulta**, use el cuadro de diálogo **Abrir** para recuperar la consulta (un archivo .usf) y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="5c3bf-117">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="5c3bf-118">(Opcional) Especificar criterios de búsqueda adicionales para restringir los resultados:</span><span class="sxs-lookup"><span data-stu-id="5c3bf-118">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="5c3bf-119">a.</span><span class="sxs-lookup"><span data-stu-id="5c3bf-119">a.</span></span> <span data-ttu-id="5c3bf-120">Haga clic en **Agregar filtro**.</span><span class="sxs-lookup"><span data-stu-id="5c3bf-120">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="5c3bf-121">b.</span><span class="sxs-lookup"><span data-stu-id="5c3bf-121">b.</span></span> <span data-ttu-id="5c3bf-122">Especifique la propiedad de usuario. Para ello, escríbala o haga clic en la flecha de la lista desplegable para seleccionar la propiedad.</span><span class="sxs-lookup"><span data-stu-id="5c3bf-122">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="5c3bf-123">c.</span><span class="sxs-lookup"><span data-stu-id="5c3bf-123">c.</span></span> <span data-ttu-id="5c3bf-124">En la lista desplegable **Igual a**, haga clic en el operador (por ejemplo, **Igual a** o **No igual a**).</span><span class="sxs-lookup"><span data-stu-id="5c3bf-124">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="5c3bf-125">d.</span><span class="sxs-lookup"><span data-stu-id="5c3bf-125">d.</span></span> <span data-ttu-id="5c3bf-126">En función de la propiedad de usuario que haya seleccionado, especifique los criterios que desee utilizar para filtrar los resultados de búsqueda escribiendo o haciendo clic en la flecha de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="5c3bf-126">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="5c3bf-127">Para agregar cláusulas de búsqueda adicionales a la consulta, haga clic en **Agregar filtro**.</span><span class="sxs-lookup"><span data-stu-id="5c3bf-127">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="5c3bf-128">&.</span><span class="sxs-lookup"><span data-stu-id="5c3bf-128">e.</span></span> <span data-ttu-id="5c3bf-129">Haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="5c3bf-129">Click **Find**.</span></span>
    
6. <span data-ttu-id="5c3bf-130">Haga clic en un usuario en los resultados de búsqueda, haga clic en **Acción** y, a continuación, en **Asignar directivas**.</span><span class="sxs-lookup"><span data-stu-id="5c3bf-130">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="5c3bf-131">Si desea aplicar la misma directiva de PIN por usuario a varios usuarios, seleccione los distintos usuarios en los resultados de la búsqueda, haga clic en **Acciones** y, después, en **Asignar directivas**.</span><span class="sxs-lookup"><span data-stu-id="5c3bf-131">If you want the same per-user PIN policy to apply to multiple users, select multiple users in the search results, then click **Actions**, and then click **Assign policies**.</span></span> 
  
7. <span data-ttu-id="5c3bf-132">En **Asignar directivas**, en **Directiva de PIN**, realice uno de los procedimientos siguientes:</span><span class="sxs-lookup"><span data-stu-id="5c3bf-132">In **Assign Policies**, under **PIN policy**, do one of the following:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5c3bf-133">Puesto que existen varias directivas que puede configurar mediante el cuadro de diálogo **asignar directivas** , \*\* \<\> \*\* la opción mantener está seleccionada de forma predeterminada para todas las directivas del cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="5c3bf-133">Because there are multiple policies that you can configure by using the **Assign Policies** dialog box, **\<Keep as is\>** is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="5c3bf-134">Para seguir usando la directiva asignada anteriormente al usuario, no efectúe cambios en esta configuración.</span><span class="sxs-lookup"><span data-stu-id="5c3bf-134">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>
  
   - <span data-ttu-id="5c3bf-135">Permitir que Skype empresarial Server elija automáticamente la Directiva de nivel global o, si está definida, la Directiva de nivel de sitio.</span><span class="sxs-lookup"><span data-stu-id="5c3bf-135">Allow Skype for Business Server to automatically choose either the global-level policy or, if defined, the site-level policy.</span></span>
    
   - <span data-ttu-id="5c3bf-136">Haga clic en el nombre de una directiva de PIN por usuario que haya definido anteriormente en la página **Directiva de PIN**.</span><span class="sxs-lookup"><span data-stu-id="5c3bf-136">Click the name of a per-user PIN policy you previously defined on the **PIN Policy** page.</span></span>
    
     > [!TIP]
     > <span data-ttu-id="5c3bf-137">Para ayudarle a decidir la directiva que desea asignar, tras hacer clic en el nombre de una directiva, haga clic en **Ver** para ver los derechos y permisos de usuario definidos en la directiva.</span><span class="sxs-lookup"><span data-stu-id="5c3bf-137">To help you decide the policy you want to assign, after you click a policy name, click **View** to view the user rights and permissions defined in the policy.</span></span>
  
8. <span data-ttu-id="5c3bf-138">Cuando haya terminado, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5c3bf-138">When you are finished, click **OK**.</span></span>
    
## <a name="assigning-a-per-user-pin-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="5c3bf-139">Asignar una directiva de PIN por usuario mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5c3bf-139">Assigning a Per-User PIN Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="5c3bf-140">Puede asignar directivas de PIN por usuario mediante Windows PowerShell y el cmdlet **Grant-CsPinPolicy** .</span><span class="sxs-lookup"><span data-stu-id="5c3bf-140">You can assign per-user PIN policies by using Windows PowerShell and the **Grant-CsPinPolicy** cmdlet.</span></span> <span data-ttu-id="5c3bf-141">Puede ejecutar este cmdlet desde el shell de administración de Skype empresarial Server o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5c3bf-141">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="5c3bf-142">Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Skype empresarial Server, consulte el artículo del blog ["Inicio rápido: administración de Microsoft Lync Server 2010 mediante PowerShell remoto"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="5c3bf-142">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="5c3bf-143">El proceso es el mismo en Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="5c3bf-143">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-assign-a-per-user-pin-policy-to-a-single-user"></a><span data-ttu-id="5c3bf-144">Asignar una directiva de PIN por usuario a un único usuario</span><span class="sxs-lookup"><span data-stu-id="5c3bf-144">To assign a per-user PIN policy to a single user</span></span>

- <span data-ttu-id="5c3bf-145">El comando siguiente asigna la directiva de PIN por usuario RedmondPinPolicy al usuario Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="5c3bf-145">The following command assigns the per-user PIN policy RedmondPinPolicy to the user Ken Myer.</span></span>
    
  ```PowerShell
  Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName "RedmondPinPolicy"
  ```

### <a name="to-assign-a-per-user-pin-policy-to-multiple-users"></a><span data-ttu-id="5c3bf-146">Asignar una directiva de PIN por usuario a varios usuarios</span><span class="sxs-lookup"><span data-stu-id="5c3bf-146">To assign a per-user PIN policy to multiple users</span></span>

- <span data-ttu-id="5c3bf-147">El comando siguiente asigna la directiva de PIN por usuario RedmondUsersPinPolicy a todos los usuarios que trabajan en la ciudad de Redmond.</span><span class="sxs-lookup"><span data-stu-id="5c3bf-147">The following command assigns the per-user PIN policy RedmondUsersPinPolicy to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="5c3bf-148">Para obtener más información sobre el parámetro LdapFilter que se usa en este comando, vea [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="5c3bf-148">For details about the LdapFilter parameter used in this command, see [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps).</span></span>
    
  ```PowerShell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsPinPolicy -PolicyName "RedmondUsersPinPolicy"
  ```

### <a name="to-unassign-a-per-user-pin-policy"></a><span data-ttu-id="5c3bf-149">Quitar la asignación de una directiva de PIN por usuario</span><span class="sxs-lookup"><span data-stu-id="5c3bf-149">To unassign a per-user PIN policy</span></span>

- <span data-ttu-id="5c3bf-p110">El comando siguiente quita la asignación de las directivas de PIN por usuario asignadas previamente a Ken Myer. Después de quitar la asignación de la directiva por usuario, se usará automáticamente la directiva global o la directiva del sitio local, si existe, para administrar a Ken Myer. La directiva de sitio tiene prioridad sobre la directiva global.</span><span class="sxs-lookup"><span data-stu-id="5c3bf-p110">The following command unassigns any per-user PIN policy previously assigned to Ken Myer. After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy. A site policy takes precedence over the global policy.</span></span>
    
  ```PowerShell
  Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

<span data-ttu-id="5c3bf-153">Para obtener más información, consulte [Grant-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cspinpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="5c3bf-153">For details, see [Grant-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cspinpolicy?view=skype-ps).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5c3bf-154">Vea también</span><span class="sxs-lookup"><span data-stu-id="5c3bf-154">See also</span></span>

[<span data-ttu-id="5c3bf-155">Crear una nueva Directiva de PIN en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="5c3bf-155">Create a new PIN policy in Skype for Business Server</span></span>](create-a-new-pin-policy.md)
