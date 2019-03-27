---
title: Bloquear o desbloquear un usuario PIN en Skype para Business Server
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 3d293a8a-e182-4547-8b06-2603c3c77329
description: 'Resumen: Bloquear o desbloquear telefónico PIN de la conferencia un usuario de Skype para Business Server.'
ms.openlocfilehash: fb90cd54ac5f339050adc51378e42d2542e489fa
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30895394"
---
# <a name="lock-or-unlock-a-user-pin-in-skype-for-business-server"></a><span data-ttu-id="3be0b-103">Bloquear o desbloquear un usuario PIN en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="3be0b-103">Lock or unlock a user PIN in Skype for Business Server</span></span>
 
<span data-ttu-id="3be0b-104">**Resumen:** Bloquear o desbloquear telefónico un usuario PIN para Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="3be0b-104">**Summary:** Lock or unlock a user's dial-in conferencing PIN for Skype for Business Server.</span></span>
  
<span data-ttu-id="3be0b-105">Puede bloquear o desbloquear un PIN de usuario de la sección **usuarios** de Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="3be0b-105">You can lock or unlock a user's PIN from the **Users** section of Skype for Business Server Control Panel.</span></span>
  
### <a name="to-lock-a-users-pin-in-skype-for-business-server-control-panel"></a><span data-ttu-id="3be0b-106">Para bloquear el PIN de un usuario en Skype para el Panel de Control de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="3be0b-106">To lock a user's PIN in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="3be0b-107">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="3be0b-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="3be0b-108">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="3be0b-108">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="3be0b-109">En la barra de navegación izquierda, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="3be0b-109">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="3be0b-110">Use uno de los métodos siguientes para encontrar a un usuario:</span><span class="sxs-lookup"><span data-stu-id="3be0b-110">Use one of the following methods to locate a user:</span></span>
    
    - <span data-ttu-id="3be0b-111">En el cuadro **Buscar usuarios**, escriba la primera porción del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de la cuenta de usuario y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="3be0b-111">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
    - <span data-ttu-id="3be0b-112">Si ha guardado una consulta, haga clic en el icono **Abrir consulta**, use el cuadro de diálogo **Abrir** para recuperar la consulta (un archivo .usf) y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="3be0b-112">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="3be0b-113">(Opcional) Especificar criterios de búsqueda adicionales para restringir los resultados:</span><span class="sxs-lookup"><span data-stu-id="3be0b-113">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="3be0b-114">a.</span><span class="sxs-lookup"><span data-stu-id="3be0b-114">a.</span></span> <span data-ttu-id="3be0b-115">Haga clic en **Agregar filtro**.</span><span class="sxs-lookup"><span data-stu-id="3be0b-115">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="3be0b-116">b.</span><span class="sxs-lookup"><span data-stu-id="3be0b-116">b.</span></span> <span data-ttu-id="3be0b-117">Especifique la propiedad de usuario. Para ello, escríbala o haga clic en la flecha de la lista desplegable para seleccionar la propiedad.</span><span class="sxs-lookup"><span data-stu-id="3be0b-117">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="3be0b-118">c.</span><span class="sxs-lookup"><span data-stu-id="3be0b-118">c.</span></span> <span data-ttu-id="3be0b-119">En la lista desplegable **Igual a**, haga clic en el operador (por ejemplo, **Igual a** o **No igual a**).</span><span class="sxs-lookup"><span data-stu-id="3be0b-119">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="3be0b-120">d.</span><span class="sxs-lookup"><span data-stu-id="3be0b-120">d.</span></span> <span data-ttu-id="3be0b-121">En función de la propiedad de usuario que haya seleccionado, especifique los criterios que desee usar para filtrar los resultados de búsqueda escribiendo o haciendo clic en la flecha de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="3be0b-121">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="3be0b-122">Para agregar cláusulas de búsqueda adicionales a la consulta, haga clic en **Agregar filtro**.</span><span class="sxs-lookup"><span data-stu-id="3be0b-122">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="3be0b-123">e.</span><span class="sxs-lookup"><span data-stu-id="3be0b-123">e.</span></span> <span data-ttu-id="3be0b-124">Haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="3be0b-124">Click **Find**.</span></span>
    
   <span data-ttu-id="3be0b-125">f.</span><span class="sxs-lookup"><span data-stu-id="3be0b-125">f.</span></span> <span data-ttu-id="3be0b-126">Haga clic en el usuario, en **Acción** y, a continuación, haga clic en **Bloquear PIN**.</span><span class="sxs-lookup"><span data-stu-id="3be0b-126">Click the user, click **Action**, and then click **Lock PIN**.</span></span>
    
### <a name="to-unlock-a-users-pin-in-skype-for-business-server-control-panel"></a><span data-ttu-id="3be0b-127">Para desbloquear un PIN de usuario en Skype para el Panel de Control de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="3be0b-127">To unlock a user's PIN in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="3be0b-128">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="3be0b-128">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="3be0b-129">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="3be0b-129">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="3be0b-130">En la barra de navegación izquierda, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="3be0b-130">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="3be0b-131">Use uno de los métodos siguientes para encontrar a un usuario:</span><span class="sxs-lookup"><span data-stu-id="3be0b-131">Use one of the following methods to locate a user:</span></span>
    
   - <span data-ttu-id="3be0b-132">En el cuadro **Buscar usuarios**, escriba la primera porción del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de la cuenta de usuario y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="3be0b-132">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
   - <span data-ttu-id="3be0b-133">Si ha guardado una consulta, haga clic en el icono **Abrir consulta**, use el cuadro de diálogo **Abrir** para recuperar la consulta (un archivo .usf) y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="3be0b-133">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="3be0b-134">(Opcional) Especificar criterios de búsqueda adicionales para restringir los resultados:</span><span class="sxs-lookup"><span data-stu-id="3be0b-134">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="3be0b-135">a.</span><span class="sxs-lookup"><span data-stu-id="3be0b-135">a.</span></span> <span data-ttu-id="3be0b-136">Haga clic en **Agregar filtro**.</span><span class="sxs-lookup"><span data-stu-id="3be0b-136">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="3be0b-137">b.</span><span class="sxs-lookup"><span data-stu-id="3be0b-137">b.</span></span> <span data-ttu-id="3be0b-138">Especifique la propiedad de usuario. Para ello, escríbala o haga clic en la flecha de la lista desplegable para seleccionar la propiedad.</span><span class="sxs-lookup"><span data-stu-id="3be0b-138">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="3be0b-139">c.</span><span class="sxs-lookup"><span data-stu-id="3be0b-139">c.</span></span> <span data-ttu-id="3be0b-140">En la lista desplegable **Igual a**, haga clic en el operador (por ejemplo, **Igual a** o **No igual a**).</span><span class="sxs-lookup"><span data-stu-id="3be0b-140">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="3be0b-141">d.</span><span class="sxs-lookup"><span data-stu-id="3be0b-141">d.</span></span> <span data-ttu-id="3be0b-142">En función de la propiedad de usuario que haya seleccionado, especifique los criterios que desee usar para filtrar los resultados de búsqueda escribiendo o haciendo clic en la flecha de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="3be0b-142">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="3be0b-143">Para agregar cláusulas de búsqueda adicionales a la consulta, haga clic en **Agregar filtro**.</span><span class="sxs-lookup"><span data-stu-id="3be0b-143">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="3be0b-144">e.</span><span class="sxs-lookup"><span data-stu-id="3be0b-144">e.</span></span> <span data-ttu-id="3be0b-145">Haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="3be0b-145">Click **Find**.</span></span>
    
   <span data-ttu-id="3be0b-146">f.</span><span class="sxs-lookup"><span data-stu-id="3be0b-146">f.</span></span> <span data-ttu-id="3be0b-147">Haga clic en el usuario, en **Acción** y, a continuación, haga clic en **Desbloquear PIN**.</span><span class="sxs-lookup"><span data-stu-id="3be0b-147">Click the user, click **Action**, and then click **Unlock PIN**.</span></span>
    
## <a name="locking-and-unlocking-user-pins-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="3be0b-148">Bloquear y Desbloquear PIN de usuario mediante el uso de Cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3be0b-148">Locking and Unlocking User PINs by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="3be0b-149">Puede bloquear y Desbloquear PIN de usuario mediante el uso de Windows PowerShell y los cmdlets Lock-CsClientPin y Unlock-CsClientPin.</span><span class="sxs-lookup"><span data-stu-id="3be0b-149">You can lock and unlock user PINs by using Windows PowerShell and the Lock-CsClientPin and Unlock-CsClientPin cmdlets.</span></span> <span data-ttu-id="3be0b-150">Se puede ejecutar estos cmdlets, ya sea desde el Skype para Shell de administración de servidor empresarial o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3be0b-150">You can run these cmdlets either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="3be0b-151">Para obtener información detallada acerca del uso de Windows PowerShell remoto para conectarse a Skype para Business Server, vea el artículo del blog ["rápido iniciar: administración de Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="3be0b-151">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="3be0b-152">El proceso es el mismo en Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="3be0b-152">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-lock-a-user-pin"></a><span data-ttu-id="3be0b-153">Para bloquear el PIN de un usuario</span><span class="sxs-lookup"><span data-stu-id="3be0b-153">To lock a user PIN</span></span>

- <span data-ttu-id="3be0b-154">Para bloquear un PIN de usuario, use el cmdlet Lock-CsClientPin.</span><span class="sxs-lookup"><span data-stu-id="3be0b-154">To lock a user's PIN, use the Lock-CsClientPin cmdlet.</span></span> <span data-ttu-id="3be0b-155">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="3be0b-155">For example:</span></span>
    
  ```
  Lock-CsClientPin -Identity "Ken Myer"
  ```

### <a name="to-unlock-a-user-pin"></a><span data-ttu-id="3be0b-156">Para desbloquear el PIN de un usuario</span><span class="sxs-lookup"><span data-stu-id="3be0b-156">To unlock a user PIN</span></span>

- <span data-ttu-id="3be0b-157">Para desbloquear un PIN de usuario, use el cmdlet Unlock-CsClientPin.</span><span class="sxs-lookup"><span data-stu-id="3be0b-157">To unlock a user's PIN, use the Unlock-CsClientPin cmdlet.</span></span> <span data-ttu-id="3be0b-158">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="3be0b-158">For example:</span></span>
    
  ```
  Unlock-CsClientPin -Identity "Ken Myer"
  ```

<span data-ttu-id="3be0b-159">Para obtener más información, vea el tema de Ayuda de los cmdlets [Lock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/lock-csclientpin?view=skype-ps) y [Unlock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/unlock-csclientpin?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="3be0b-159">For more information, see the help topic for the [Lock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/lock-csclientpin?view=skype-ps) and [Unlock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/unlock-csclientpin?view=skype-ps) cmdlets.</span></span>
