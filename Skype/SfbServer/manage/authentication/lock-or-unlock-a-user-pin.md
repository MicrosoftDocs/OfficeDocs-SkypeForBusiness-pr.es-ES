---
title: Bloquear o desbloquear un PIN de usuario en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 3d293a8a-e182-4547-8b06-2603c3c77329
description: 'Resumen: bloquee o desbloquee el PIN de conferencia de acceso telefónico local de un usuario para Skype Empresarial Server.'
ms.openlocfilehash: 73bd9affa159fba4ab35844896b9662eea3e1780
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828370"
---
# <a name="lock-or-unlock-a-user-pin-in-skype-for-business-server"></a><span data-ttu-id="c5493-103">Bloquear o desbloquear un PIN de usuario en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="c5493-103">Lock or unlock a user PIN in Skype for Business Server</span></span>
 
<span data-ttu-id="c5493-104">**Resumen:** Bloquear o desbloquear el PIN de conferencia de acceso telefónico local de un usuario para Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="c5493-104">**Summary:** Lock or unlock a user's dial-in conferencing PIN for Skype for Business Server.</span></span>
  
<span data-ttu-id="c5493-105">Puede bloquear o desbloquear el PIN de un usuario desde la sección **Usuarios** del Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="c5493-105">You can lock or unlock a user's PIN from the **Users** section of Skype for Business Server Control Panel.</span></span>
  
### <a name="to-lock-a-users-pin-in-skype-for-business-server-control-panel"></a><span data-ttu-id="c5493-106">Para bloquear el PIN de un usuario en el Panel de control de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="c5493-106">To lock a user's PIN in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="c5493-107">Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="c5493-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="c5493-108">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="c5493-108">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="c5493-109">En la barra de navegación izquierda, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="c5493-109">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="c5493-110">Utilice uno de los métodos siguientes para encontrar a un usuario:</span><span class="sxs-lookup"><span data-stu-id="c5493-110">Use one of the following methods to locate a user:</span></span>
    
    - <span data-ttu-id="c5493-111">En el cuadro **Buscar usuarios**, escriba la primera porción del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de la cuenta de usuario y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="c5493-111">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
    - <span data-ttu-id="c5493-112">Si ha guardado una consulta, haga clic en el icono **Abrir consulta**, utilice el cuadro de diálogo **Abrir** para recuperar la consulta (un archivo .usf) y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="c5493-112">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="c5493-113">(Opcional) Especificar criterios de búsqueda adicionales para restringir los resultados:</span><span class="sxs-lookup"><span data-stu-id="c5493-113">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="c5493-114">a.</span><span class="sxs-lookup"><span data-stu-id="c5493-114">a.</span></span> <span data-ttu-id="c5493-115">Haga clic en **Agregar filtro**.</span><span class="sxs-lookup"><span data-stu-id="c5493-115">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="c5493-116">b.</span><span class="sxs-lookup"><span data-stu-id="c5493-116">b.</span></span> <span data-ttu-id="c5493-117">Especifique la propiedad de usuario; para ello, escríbala o haga clic en la flecha de la lista desplegable para seleccionar la propiedad.</span><span class="sxs-lookup"><span data-stu-id="c5493-117">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="c5493-118">c.</span><span class="sxs-lookup"><span data-stu-id="c5493-118">c.</span></span> <span data-ttu-id="c5493-119">En la lista desplegable **Igual a**, haga clic en el operador (por ejemplo, **Igual a** o **No igual a**).</span><span class="sxs-lookup"><span data-stu-id="c5493-119">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="c5493-120">d.</span><span class="sxs-lookup"><span data-stu-id="c5493-120">d.</span></span> <span data-ttu-id="c5493-121">En función de la propiedad de usuario que haya seleccionado, especifique los criterios que desee usar para filtrar los resultados de búsqueda escribiendo o haciendo clic en la flecha de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="c5493-121">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="c5493-122">Para agregar cláusulas de búsqueda adicionales a la consulta, haga clic en **Agregar filtro**.</span><span class="sxs-lookup"><span data-stu-id="c5493-122">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="c5493-123">e.</span><span class="sxs-lookup"><span data-stu-id="c5493-123">e.</span></span> <span data-ttu-id="c5493-124">Haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="c5493-124">Click **Find**.</span></span>
    
   <span data-ttu-id="c5493-125">f.</span><span class="sxs-lookup"><span data-stu-id="c5493-125">f.</span></span> <span data-ttu-id="c5493-126">Haga clic en el usuario, en **Acción** y, a continuación, haga clic en **Bloquear PIN**.</span><span class="sxs-lookup"><span data-stu-id="c5493-126">Click the user, click **Action**, and then click **Lock PIN**.</span></span>
    
### <a name="to-unlock-a-users-pin-in-skype-for-business-server-control-panel"></a><span data-ttu-id="c5493-127">Para desbloquear el PIN de un usuario en el Panel de control de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="c5493-127">To unlock a user's PIN in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="c5493-128">Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="c5493-128">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="c5493-129">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="c5493-129">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="c5493-130">En la barra de navegación izquierda, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="c5493-130">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="c5493-131">Utilice uno de los métodos siguientes para encontrar a un usuario:</span><span class="sxs-lookup"><span data-stu-id="c5493-131">Use one of the following methods to locate a user:</span></span>
    
   - <span data-ttu-id="c5493-132">En el cuadro **Buscar usuarios**, escriba la primera porción del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de la cuenta de usuario y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="c5493-132">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
   - <span data-ttu-id="c5493-133">Si ha guardado una consulta, haga clic en el icono **Abrir consulta**, utilice el cuadro de diálogo **Abrir** para recuperar la consulta (un archivo .usf) y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="c5493-133">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="c5493-134">(Opcional) Especificar criterios de búsqueda adicionales para restringir los resultados:</span><span class="sxs-lookup"><span data-stu-id="c5493-134">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="c5493-135">a.</span><span class="sxs-lookup"><span data-stu-id="c5493-135">a.</span></span> <span data-ttu-id="c5493-136">Haga clic en **Agregar filtro**.</span><span class="sxs-lookup"><span data-stu-id="c5493-136">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="c5493-137">b.</span><span class="sxs-lookup"><span data-stu-id="c5493-137">b.</span></span> <span data-ttu-id="c5493-138">Especifique la propiedad de usuario; para ello, escríbala o haga clic en la flecha de la lista desplegable para seleccionar la propiedad.</span><span class="sxs-lookup"><span data-stu-id="c5493-138">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="c5493-139">c.</span><span class="sxs-lookup"><span data-stu-id="c5493-139">c.</span></span> <span data-ttu-id="c5493-140">En la lista desplegable **Igual a**, haga clic en el operador (por ejemplo, **Igual a** o **No igual a**).</span><span class="sxs-lookup"><span data-stu-id="c5493-140">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="c5493-141">d.</span><span class="sxs-lookup"><span data-stu-id="c5493-141">d.</span></span> <span data-ttu-id="c5493-142">En función de la propiedad de usuario que haya seleccionado, especifique los criterios que desee usar para filtrar los resultados de búsqueda escribiendo o haciendo clic en la flecha de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="c5493-142">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="c5493-143">Para agregar cláusulas de búsqueda adicionales a la consulta, haga clic en **Agregar filtro**.</span><span class="sxs-lookup"><span data-stu-id="c5493-143">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="c5493-144">e.</span><span class="sxs-lookup"><span data-stu-id="c5493-144">e.</span></span> <span data-ttu-id="c5493-145">Haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="c5493-145">Click **Find**.</span></span>
    
   <span data-ttu-id="c5493-146">f.</span><span class="sxs-lookup"><span data-stu-id="c5493-146">f.</span></span> <span data-ttu-id="c5493-147">Haga clic en el usuario, en **Acción** y, a continuación, haga clic en **Desbloquear PIN**.</span><span class="sxs-lookup"><span data-stu-id="c5493-147">Click the user, click **Action**, and then click **Unlock PIN**.</span></span>
    
## <a name="locking-and-unlocking-user-pins-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="c5493-148">Bloqueo y desbloqueo de LOS PIN de usuario mediante cmdlets Windows PowerShell de usuario</span><span class="sxs-lookup"><span data-stu-id="c5493-148">Locking and Unlocking User PINs by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="c5493-149">Puede bloquear y desbloquear los PIN de usuario con los Windows PowerShell y los cmdlets Lock-CsClientPin y Unlock-CsClientPin usuario.</span><span class="sxs-lookup"><span data-stu-id="c5493-149">You can lock and unlock user PINs by using Windows PowerShell and the Lock-CsClientPin and Unlock-CsClientPin cmdlets.</span></span> <span data-ttu-id="c5493-150">Puede ejecutar estos cmdlets desde el Shell de administración de Skype Empresarial Server o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c5493-150">You can run these cmdlets either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="c5493-151">Para obtener más información sobre el uso de Windows PowerShell remoto para conectarse a Skype Empresarial Server, consulte el artículo del blog "Inicio rápido: administración de [Microsoft Lync Server 2010 con PowerShell remoto".](https://go.microsoft.com/fwlink/p/?linkId=255876)</span><span class="sxs-lookup"><span data-stu-id="c5493-151">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="c5493-152">El proceso es el mismo en Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="c5493-152">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-lock-a-user-pin"></a><span data-ttu-id="c5493-153">Para bloquear el PIN de un usuario</span><span class="sxs-lookup"><span data-stu-id="c5493-153">To lock a user PIN</span></span>

- <span data-ttu-id="c5493-154">Para bloquear el PIN de un usuario, use el cmdlet Lock-CsClientPin usuario.</span><span class="sxs-lookup"><span data-stu-id="c5493-154">To lock a user's PIN, use the Lock-CsClientPin cmdlet.</span></span> <span data-ttu-id="c5493-155">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c5493-155">For example:</span></span>
    
  ```PowerShell
  Lock-CsClientPin -Identity "Ken Myer"
  ```

### <a name="to-unlock-a-user-pin"></a><span data-ttu-id="c5493-156">Para desbloquear el PIN de un usuario</span><span class="sxs-lookup"><span data-stu-id="c5493-156">To unlock a user PIN</span></span>

- <span data-ttu-id="c5493-157">Para desbloquear el PIN de un usuario, use el cmdlet Unlock-CsClientPin usuario.</span><span class="sxs-lookup"><span data-stu-id="c5493-157">To unlock a user's PIN, use the Unlock-CsClientPin cmdlet.</span></span> <span data-ttu-id="c5493-158">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c5493-158">For example:</span></span>
    
  ```PowerShell
  Unlock-CsClientPin -Identity "Ken Myer"
  ```

<span data-ttu-id="c5493-159">Para obtener más información, consulte el tema de ayuda para los [cmdlets Lock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/lock-csclientpin?view=skype-ps) y [Unlock-CsClientPin.](https://docs.microsoft.com/powershell/module/skype/unlock-csclientpin?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="c5493-159">For more information, see the help topic for the [Lock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/lock-csclientpin?view=skype-ps) and [Unlock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/unlock-csclientpin?view=skype-ps) cmdlets.</span></span>
