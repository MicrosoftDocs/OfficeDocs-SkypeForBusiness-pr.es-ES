---
title: Bloquear o desbloquear un PIN de usuario en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 3d293a8a-e182-4547-8b06-2603c3c77329
description: 'Resumen: bloquear o desbloquear el PIN de conferencias de acceso telefónico local de un usuario para Skype empresarial Server.'
ms.openlocfilehash: 600ddcb507c7cb0074a651580c684590fa283602
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294285"
---
# <a name="lock-or-unlock-a-user-pin-in-skype-for-business-server"></a><span data-ttu-id="8b8c9-103">Bloquear o desbloquear un PIN de usuario en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="8b8c9-103">Lock or unlock a user PIN in Skype for Business Server</span></span>
 
<span data-ttu-id="8b8c9-104">**Resumen:** Bloquear o desbloquear el PIN de conferencias de acceso telefónico local de un usuario para Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="8b8c9-104">**Summary:** Lock or unlock a user's dial-in conferencing PIN for Skype for Business Server.</span></span>
  
<span data-ttu-id="8b8c9-105">Puede bloquear o desbloquear el PIN de un usuario desde la sección **usuarios** del panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="8b8c9-105">You can lock or unlock a user's PIN from the **Users** section of Skype for Business Server Control Panel.</span></span>
  
### <a name="to-lock-a-users-pin-in-skype-for-business-server-control-panel"></a><span data-ttu-id="8b8c9-106">Para bloquear el PIN de un usuario en el panel de control de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="8b8c9-106">To lock a user's PIN in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="8b8c9-107">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="8b8c9-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="8b8c9-108">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="8b8c9-108">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="8b8c9-109">En la barra de navegación izquierda, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="8b8c9-109">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="8b8c9-110">Use uno de los métodos siguientes para encontrar a un usuario:</span><span class="sxs-lookup"><span data-stu-id="8b8c9-110">Use one of the following methods to locate a user:</span></span>
    
    - <span data-ttu-id="8b8c9-111">En el cuadro **Buscar usuarios**, escriba la primera porción del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de la cuenta de usuario y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="8b8c9-111">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
    - <span data-ttu-id="8b8c9-112">Si ha guardado una consulta, haga clic en el icono **Abrir consulta**, use el cuadro de diálogo **Abrir** para recuperar la consulta (un archivo .usf) y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="8b8c9-112">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="8b8c9-113">(Opcional) Especificar criterios de búsqueda adicionales para restringir los resultados:</span><span class="sxs-lookup"><span data-stu-id="8b8c9-113">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="8b8c9-114">a.</span><span class="sxs-lookup"><span data-stu-id="8b8c9-114">a.</span></span> <span data-ttu-id="8b8c9-115">Haga clic en **Agregar filtro**.</span><span class="sxs-lookup"><span data-stu-id="8b8c9-115">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="8b8c9-116">b.</span><span class="sxs-lookup"><span data-stu-id="8b8c9-116">b.</span></span> <span data-ttu-id="8b8c9-117">Especifique la propiedad de usuario. Para ello, escríbala o haga clic en la flecha de la lista desplegable para seleccionar la propiedad.</span><span class="sxs-lookup"><span data-stu-id="8b8c9-117">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="8b8c9-118">c.</span><span class="sxs-lookup"><span data-stu-id="8b8c9-118">c.</span></span> <span data-ttu-id="8b8c9-119">En la lista desplegable **Igual a**, haga clic en el operador (por ejemplo, **Igual a** o **No igual a**).</span><span class="sxs-lookup"><span data-stu-id="8b8c9-119">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="8b8c9-120">d.</span><span class="sxs-lookup"><span data-stu-id="8b8c9-120">d.</span></span> <span data-ttu-id="8b8c9-121">En función de la propiedad de usuario que haya seleccionado, especifique los criterios que desee usar para filtrar los resultados de búsqueda escribiendo o haciendo clic en la flecha de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="8b8c9-121">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="8b8c9-122">Para agregar cláusulas de búsqueda adicionales a la consulta, haga clic en **Agregar filtro**.</span><span class="sxs-lookup"><span data-stu-id="8b8c9-122">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="8b8c9-123">&.</span><span class="sxs-lookup"><span data-stu-id="8b8c9-123">e.</span></span> <span data-ttu-id="8b8c9-124">Haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="8b8c9-124">Click **Find**.</span></span>
    
   <span data-ttu-id="8b8c9-125">f.</span><span class="sxs-lookup"><span data-stu-id="8b8c9-125">f.</span></span> <span data-ttu-id="8b8c9-126">Haga clic en el usuario, en **Acción** y, a continuación, haga clic en **Bloquear PIN**.</span><span class="sxs-lookup"><span data-stu-id="8b8c9-126">Click the user, click **Action**, and then click **Lock PIN**.</span></span>
    
### <a name="to-unlock-a-users-pin-in-skype-for-business-server-control-panel"></a><span data-ttu-id="8b8c9-127">Para desbloquear el PIN de un usuario en el panel de control de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="8b8c9-127">To unlock a user's PIN in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="8b8c9-128">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="8b8c9-128">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="8b8c9-129">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="8b8c9-129">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="8b8c9-130">En la barra de navegación izquierda, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="8b8c9-130">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="8b8c9-131">Use uno de los métodos siguientes para encontrar a un usuario:</span><span class="sxs-lookup"><span data-stu-id="8b8c9-131">Use one of the following methods to locate a user:</span></span>
    
   - <span data-ttu-id="8b8c9-132">En el cuadro **Buscar usuarios**, escriba la primera porción del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de la cuenta de usuario y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="8b8c9-132">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
   - <span data-ttu-id="8b8c9-133">Si ha guardado una consulta, haga clic en el icono **Abrir consulta**, use el cuadro de diálogo **Abrir** para recuperar la consulta (un archivo .usf) y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="8b8c9-133">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="8b8c9-134">(Opcional) Especificar criterios de búsqueda adicionales para restringir los resultados:</span><span class="sxs-lookup"><span data-stu-id="8b8c9-134">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="8b8c9-135">a.</span><span class="sxs-lookup"><span data-stu-id="8b8c9-135">a.</span></span> <span data-ttu-id="8b8c9-136">Haga clic en **Agregar filtro**.</span><span class="sxs-lookup"><span data-stu-id="8b8c9-136">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="8b8c9-137">b.</span><span class="sxs-lookup"><span data-stu-id="8b8c9-137">b.</span></span> <span data-ttu-id="8b8c9-138">Especifique la propiedad de usuario. Para ello, escríbala o haga clic en la flecha de la lista desplegable para seleccionar la propiedad.</span><span class="sxs-lookup"><span data-stu-id="8b8c9-138">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="8b8c9-139">c.</span><span class="sxs-lookup"><span data-stu-id="8b8c9-139">c.</span></span> <span data-ttu-id="8b8c9-140">En la lista desplegable **Igual a**, haga clic en el operador (por ejemplo, **Igual a** o **No igual a**).</span><span class="sxs-lookup"><span data-stu-id="8b8c9-140">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="8b8c9-141">d.</span><span class="sxs-lookup"><span data-stu-id="8b8c9-141">d.</span></span> <span data-ttu-id="8b8c9-142">En función de la propiedad de usuario que haya seleccionado, especifique los criterios que desee usar para filtrar los resultados de búsqueda escribiendo o haciendo clic en la flecha de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="8b8c9-142">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="8b8c9-143">Para agregar cláusulas de búsqueda adicionales a la consulta, haga clic en **Agregar filtro**.</span><span class="sxs-lookup"><span data-stu-id="8b8c9-143">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="8b8c9-144">&.</span><span class="sxs-lookup"><span data-stu-id="8b8c9-144">e.</span></span> <span data-ttu-id="8b8c9-145">Haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="8b8c9-145">Click **Find**.</span></span>
    
   <span data-ttu-id="8b8c9-146">f.</span><span class="sxs-lookup"><span data-stu-id="8b8c9-146">f.</span></span> <span data-ttu-id="8b8c9-147">Haga clic en el usuario, en **Acción** y, a continuación, haga clic en **Desbloquear PIN**.</span><span class="sxs-lookup"><span data-stu-id="8b8c9-147">Click the user, click **Action**, and then click **Unlock PIN**.</span></span>
    
## <a name="locking-and-unlocking-user-pins-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="8b8c9-148">Bloquear y desbloquear los pin de usuario mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8b8c9-148">Locking and Unlocking User PINs by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="8b8c9-149">Puede bloquear y desbloquear los pin de usuario mediante Windows PowerShell y los cmdlets Lock-CsClientPin y Unlock-CsClientPin.</span><span class="sxs-lookup"><span data-stu-id="8b8c9-149">You can lock and unlock user PINs by using Windows PowerShell and the Lock-CsClientPin and Unlock-CsClientPin cmdlets.</span></span> <span data-ttu-id="8b8c9-150">Puede ejecutar estos cmdlets desde el shell de administración de Skype empresarial Server o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8b8c9-150">You can run these cmdlets either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="8b8c9-151">Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Skype empresarial Server, consulte el artículo del blog ["Inicio rápido: administración de Microsoft Lync Server 2010 mediante PowerShell remoto"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="8b8c9-151">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="8b8c9-152">El proceso es el mismo en Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="8b8c9-152">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-lock-a-user-pin"></a><span data-ttu-id="8b8c9-153">Para bloquear el PIN de un usuario</span><span class="sxs-lookup"><span data-stu-id="8b8c9-153">To lock a user PIN</span></span>

- <span data-ttu-id="8b8c9-154">Para bloquear el PIN de un usuario, use el cmdlet Lock-CsClientPin.</span><span class="sxs-lookup"><span data-stu-id="8b8c9-154">To lock a user's PIN, use the Lock-CsClientPin cmdlet.</span></span> <span data-ttu-id="8b8c9-155">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8b8c9-155">For example:</span></span>
    
  ```
  Lock-CsClientPin -Identity "Ken Myer"
  ```

### <a name="to-unlock-a-user-pin"></a><span data-ttu-id="8b8c9-156">Para desbloquear el PIN de un usuario</span><span class="sxs-lookup"><span data-stu-id="8b8c9-156">To unlock a user PIN</span></span>

- <span data-ttu-id="8b8c9-157">Para desbloquear el PIN de un usuario, use el cmdlet Unlock-CsClientPin.</span><span class="sxs-lookup"><span data-stu-id="8b8c9-157">To unlock a user's PIN, use the Unlock-CsClientPin cmdlet.</span></span> <span data-ttu-id="8b8c9-158">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8b8c9-158">For example:</span></span>
    
  ```
  Unlock-CsClientPin -Identity "Ken Myer"
  ```

<span data-ttu-id="8b8c9-159">Para obtener más información, consulte el tema de ayuda para los cmdlets [Lock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/lock-csclientpin?view=skype-ps) y [Unlock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/unlock-csclientpin?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="8b8c9-159">For more information, see the help topic for the [Lock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/lock-csclientpin?view=skype-ps) and [Unlock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/unlock-csclientpin?view=skype-ps) cmdlets.</span></span>
