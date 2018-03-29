---
title: Bloquear o desbloquear el PIN de un usuario en Skype Empresarial Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 3d293a8a-e182-4547-8b06-2603c3c77329
description: 'Resumen: Bloquear o desbloquear la conferencia acceso telefónico del usuario PIN de Skype Business Server 2015.'
ms.openlocfilehash: 5bd4a334f9c0b543d9b4cade8631f992a920dfb1
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="lock-or-unlock-a-user-pin-in-skype-for-business-server-2015"></a><span data-ttu-id="32b28-103">Bloquear o desbloquear el PIN de un usuario en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="32b28-103">Lock or unlock a user PIN in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="32b28-104">**Resumen:** Bloquear o desbloquear la conferencia acceso telefónico del usuario PIN de Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="32b28-104">**Summary:** Lock or unlock a user's dial-in conferencing PIN for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="32b28-105">Puede bloquear o desbloquear el NIP de un usuario desde la sección de **usuarios** de Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="32b28-105">You can lock or unlock a user's PIN from the **Users** section of Skype for Business Server Control Panel.</span></span>
  
### <a name="to-lock-a-users-pin-in-skype-for-business-server-control-panel"></a><span data-ttu-id="32b28-106">Bloquear el NIP de un usuario en Skype para Panel de Control de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="32b28-106">To lock a user's PIN in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="32b28-107">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="32b28-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="32b28-108">Abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin para abrir el Skype para Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="32b28-108">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="32b28-109">En la barra de navegación izquierda, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="32b28-109">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="32b28-110">Utilice uno de los métodos siguientes para encontrar a un usuario:</span><span class="sxs-lookup"><span data-stu-id="32b28-110">Use one of the following methods to locate a user:</span></span>
    
    - <span data-ttu-id="32b28-111">En el cuadro **Buscar usuarios**, escriba la primera porción del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de la cuenta de usuario y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="32b28-111">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
    - <span data-ttu-id="32b28-112">Si ha guardado una consulta, haga clic en el icono **Abrir consulta**, utilice el cuadro de diálogo **Abrir** para recuperar la consulta (un archivo .usf) y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="32b28-112">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="32b28-113">(Opcional) Especificar criterios de búsqueda adicionales para restringir los resultados:</span><span class="sxs-lookup"><span data-stu-id="32b28-113">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="32b28-114">a.</span><span class="sxs-lookup"><span data-stu-id="32b28-114">a.</span></span> <span data-ttu-id="32b28-115">Haga clic en **Agregar filtro**.</span><span class="sxs-lookup"><span data-stu-id="32b28-115">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="32b28-116">b.</span><span class="sxs-lookup"><span data-stu-id="32b28-116">b.</span></span> <span data-ttu-id="32b28-117">Especifique la propiedad de usuario. Para ello, escríbala o haga clic en la flecha de la lista desplegable para seleccionar la propiedad.</span><span class="sxs-lookup"><span data-stu-id="32b28-117">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="32b28-118">c.</span><span class="sxs-lookup"><span data-stu-id="32b28-118">c.</span></span> <span data-ttu-id="32b28-119">En la lista desplegable **Igual a**, haga clic en el operador (por ejemplo, **Igual a** o **No igual a**).</span><span class="sxs-lookup"><span data-stu-id="32b28-119">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="32b28-120">d.</span><span class="sxs-lookup"><span data-stu-id="32b28-120">d.</span></span> <span data-ttu-id="32b28-121">En función de la propiedad de usuario que haya seleccionado, especifique los criterios que desee usar para filtrar los resultados de búsqueda escribiendo o haciendo clic en la flecha de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="32b28-121">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="32b28-122">Para agregar cláusulas de búsqueda adicionales a la consulta, haga clic en **Agregar filtro**.</span><span class="sxs-lookup"><span data-stu-id="32b28-122">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="32b28-123">e.</span><span class="sxs-lookup"><span data-stu-id="32b28-123">e.</span></span> <span data-ttu-id="32b28-124">Haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="32b28-124">Click **Find**.</span></span>
    
   <span data-ttu-id="32b28-125">f.</span><span class="sxs-lookup"><span data-stu-id="32b28-125">f.</span></span> <span data-ttu-id="32b28-126">Haga clic en el usuario, en **Acción** y, a continuación, haga clic en **Bloquear PIN**.</span><span class="sxs-lookup"><span data-stu-id="32b28-126">Click the user, click **Action**, and then click **Lock PIN**.</span></span>
    
### <a name="to-unlock-a-users-pin-in-skype-for-business-server-control-panel"></a><span data-ttu-id="32b28-127">Para desbloquear el NIP de un usuario en Skype de Panel de Control de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="32b28-127">To unlock a user's PIN in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="32b28-128">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="32b28-128">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="32b28-129">Abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin para abrir el Skype para Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="32b28-129">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="32b28-130">En la barra de navegación izquierda, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="32b28-130">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="32b28-131">Utilice uno de los métodos siguientes para encontrar a un usuario:</span><span class="sxs-lookup"><span data-stu-id="32b28-131">Use one of the following methods to locate a user:</span></span>
    
   - <span data-ttu-id="32b28-132">En el cuadro **Buscar usuarios**, escriba la primera porción del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de la cuenta de usuario y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="32b28-132">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
   - <span data-ttu-id="32b28-133">Si ha guardado una consulta, haga clic en el icono **Abrir consulta**, utilice el cuadro de diálogo **Abrir** para recuperar la consulta (un archivo .usf) y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="32b28-133">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="32b28-134">(Opcional) Especificar criterios de búsqueda adicionales para restringir los resultados:</span><span class="sxs-lookup"><span data-stu-id="32b28-134">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="32b28-135">a.</span><span class="sxs-lookup"><span data-stu-id="32b28-135">a.</span></span> <span data-ttu-id="32b28-136">Haga clic en **Agregar filtro**.</span><span class="sxs-lookup"><span data-stu-id="32b28-136">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="32b28-137">b.</span><span class="sxs-lookup"><span data-stu-id="32b28-137">b.</span></span> <span data-ttu-id="32b28-138">Especifique la propiedad de usuario. Para ello, escríbala o haga clic en la flecha de la lista desplegable para seleccionar la propiedad.</span><span class="sxs-lookup"><span data-stu-id="32b28-138">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="32b28-139">c.</span><span class="sxs-lookup"><span data-stu-id="32b28-139">c.</span></span> <span data-ttu-id="32b28-140">En la lista desplegable **Igual a**, haga clic en el operador (por ejemplo, **Igual a** o **No igual a**).</span><span class="sxs-lookup"><span data-stu-id="32b28-140">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="32b28-141">d.</span><span class="sxs-lookup"><span data-stu-id="32b28-141">d.</span></span> <span data-ttu-id="32b28-142">En función de la propiedad de usuario que haya seleccionado, especifique los criterios que desee usar para filtrar los resultados de búsqueda escribiendo o haciendo clic en la flecha de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="32b28-142">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="32b28-143">Para agregar cláusulas de búsqueda adicionales a la consulta, haga clic en **Agregar filtro**.</span><span class="sxs-lookup"><span data-stu-id="32b28-143">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="32b28-144">e.</span><span class="sxs-lookup"><span data-stu-id="32b28-144">e.</span></span> <span data-ttu-id="32b28-145">Haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="32b28-145">Click **Find**.</span></span>
    
   <span data-ttu-id="32b28-146">f.</span><span class="sxs-lookup"><span data-stu-id="32b28-146">f.</span></span> <span data-ttu-id="32b28-147">Haga clic en el usuario, en **Acción** y, a continuación, haga clic en **Desbloquear PIN**.</span><span class="sxs-lookup"><span data-stu-id="32b28-147">Click the user, click **Action**, and then click **Unlock PIN**.</span></span>
    
## <a name="locking-and-unlocking-user-pins-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="32b28-148">Bloqueo y desbloqueo NIP de los usuarios mediante Cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="32b28-148">Locking and Unlocking User PINs by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="32b28-149">Puede bloquear y desbloquear el PIN de usuario mediante Windows PowerShell y los cmdlets CsClientPin-Lock y Unlock CsClientPin.</span><span class="sxs-lookup"><span data-stu-id="32b28-149">You can lock and unlock user PINs by using Windows PowerShell and the Lock-CsClientPin and Unlock-CsClientPin cmdlets.</span></span> <span data-ttu-id="32b28-150">Estos cmdlets se puede ejecutar desde el Skype para el Shell de administración de servidor empresarial o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="32b28-150">You can run these cmdlets either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="32b28-151">Para obtener más información acerca del uso de Windows PowerShell remoto para conectar con Skype para Business Server, consulte el artículo de blog ["rápido inicio: administración de Microsoft Lync Server 2010 utilizando remoto PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="32b28-151">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="32b28-152">El proceso es el mismo en Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="32b28-152">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-lock-a-user-pin"></a><span data-ttu-id="32b28-153">Para bloquear el PIN de un usuario</span><span class="sxs-lookup"><span data-stu-id="32b28-153">To lock a user PIN</span></span>

- <span data-ttu-id="32b28-154">Para bloquear el NIP de un usuario, utilice el cmdlet Lock-CsClientPin.</span><span class="sxs-lookup"><span data-stu-id="32b28-154">To lock a user's PIN, use the Lock-CsClientPin cmdlet.</span></span> <span data-ttu-id="32b28-155">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="32b28-155">For example:</span></span>
    
  ```
  Lock-CsClientPin -Identity "Ken Myer"
  ```

### <a name="to-unlock-a-user-pin"></a><span data-ttu-id="32b28-156">Para desbloquear el PIN de un usuario</span><span class="sxs-lookup"><span data-stu-id="32b28-156">To unlock a user PIN</span></span>

- <span data-ttu-id="32b28-157">Para desbloquear el NIP de un usuario, utilice el cmdlet Unlock-CsClientPin.</span><span class="sxs-lookup"><span data-stu-id="32b28-157">To unlock a user's PIN, use the Unlock-CsClientPin cmdlet.</span></span> <span data-ttu-id="32b28-158">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="32b28-158">For example:</span></span>
    
  ```
  Unlock-CsClientPin -Identity "Ken Myer"
  ```

<span data-ttu-id="32b28-159">Para obtener más información, vea el tema de Ayuda de los cmdlets [CsClientPin-Lock](https://docs.microsoft.com/powershell/module/skype/lock-csclientpin?view=skype-ps) y [Unlock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/unlock-csclientpin?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="32b28-159">For more information, see the help topic for the [Lock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/lock-csclientpin?view=skype-ps) and [Unlock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/unlock-csclientpin?view=skype-ps) cmdlets.</span></span>