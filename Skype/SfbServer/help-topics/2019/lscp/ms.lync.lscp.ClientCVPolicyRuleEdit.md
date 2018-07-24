---
title: Regla de versiones de cliente
ms.author: dianef
author: dianef77
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVPolicyRuleEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6e7e94c2-1475-4334-b8da-716b24a4c255
ROBOTS: NOINDEX, NOFOLLOW
description: Una directiva de versión de cliente está compuesta de un conjunto de reglas de versión de cliente. Estas reglas definen las acciones que se necesitan realizar cuando los usuarios intentan iniciar sesión con clientes y versiones de clientes específicos.
ms.openlocfilehash: cd89e0bd5bf6781ea8381563e592d57a3e68434a
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "20988737"
---
# <a name="client-version-rule"></a><span data-ttu-id="2a710-104">Regla de versiones de cliente</span><span class="sxs-lookup"><span data-stu-id="2a710-104">Client Version Rule</span></span>
 
<span data-ttu-id="2a710-p102">Una directiva de versión de cliente está compuesta de un conjunto de reglas de versión de cliente. Estas reglas definen las acciones que se necesitan realizar cuando los usuarios intentan iniciar sesión con clientes y versiones de clientes específicos.</span><span class="sxs-lookup"><span data-stu-id="2a710-p102">A client version policy is made up of a set of client version rules. These rules define the actions that should be taken when users attempt to log on with specific clients and client versions.</span></span>
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="2a710-107">Tareas que puede realizar</span><span class="sxs-lookup"><span data-stu-id="2a710-107">Tasks you can perform</span></span>

<span data-ttu-id="2a710-108">En las páginas **Nueva configuración de versión de cliente** o **Editar configuración de versión de cliente** puede realizar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="2a710-108">You can perform the following tasks on the **New Client Version Configuration** or **Edit Client Version Configuration** page:</span></span>
  
- <span data-ttu-id="2a710-109">Agregar nuevas reglas a una directiva de versión de cliente.</span><span class="sxs-lookup"><span data-stu-id="2a710-109">Add new rules to a client version policy.</span></span>
    
- <span data-ttu-id="2a710-110">Modificar las reglas que componen una directiva de versión de cliente existente.</span><span class="sxs-lookup"><span data-stu-id="2a710-110">Modify the rules that make up an existing client version policy</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="2a710-111">Referencia de interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="2a710-111">UI Reference</span></span>

<span data-ttu-id="2a710-112">En las siguientes listas se describen los menús, comandos, campos y propiedades de la página.</span><span class="sxs-lookup"><span data-stu-id="2a710-112">The following lists describe the menus, command, fields, and properties on the page.</span></span>
  
- <span data-ttu-id="2a710-113">**Agente de usuario** Puede seleccionar un tipo de cliente de la lista.</span><span class="sxs-lookup"><span data-stu-id="2a710-113">**User agent** You can select a client type from the list.</span></span> <span data-ttu-id="2a710-114">En la siguiente tabla se recogen los códigos de agente de usuario.</span><span class="sxs-lookup"><span data-stu-id="2a710-114">The following table defines user agent codes.</span></span>
    
|<span data-ttu-id="2a710-115">**Nombre de cliente**</span><span class="sxs-lookup"><span data-stu-id="2a710-115">**Client Name**</span></span>|<span data-ttu-id="2a710-116">**Agente de usuario**</span><span class="sxs-lookup"><span data-stu-id="2a710-116">**User Agent**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2a710-117">Lync 2013, Lync 2010, Office Communicator</span><span class="sxs-lookup"><span data-stu-id="2a710-117">Lync 2013, Lync 2010, Office Communicator</span></span>  <br/> |<span data-ttu-id="2a710-118">Componente opcional</span><span class="sxs-lookup"><span data-stu-id="2a710-118">OC</span></span>  <br/> |
|<span data-ttu-id="2a710-119">Lync Web App, Communicator Web Access</span><span class="sxs-lookup"><span data-stu-id="2a710-119">Lync Web App, Communicator Web Access</span></span>  <br/> |<span data-ttu-id="2a710-120">CWA</span><span class="sxs-lookup"><span data-stu-id="2a710-120">CWA</span></span>  <br/> |
|<span data-ttu-id="2a710-121">Lync Phone Edition, Office Communicator Phone</span><span class="sxs-lookup"><span data-stu-id="2a710-121">Lync Phone Edition, Office Communicator Phone</span></span>  <br/> |<span data-ttu-id="2a710-122">OCPhone</span><span class="sxs-lookup"><span data-stu-id="2a710-122">OCPhone</span></span>  <br/> |
|<span data-ttu-id="2a710-123">Plataforma Communicator Phone Edition</span><span class="sxs-lookup"><span data-stu-id="2a710-123">Communicator Phone Edition Platform</span></span>  <br/> |<span data-ttu-id="2a710-124">CPE</span><span class="sxs-lookup"><span data-stu-id="2a710-124">CPE</span></span>  <br/> |
|<span data-ttu-id="2a710-125">Plataforma de comunicaciones unificadas</span><span class="sxs-lookup"><span data-stu-id="2a710-125">Unified Communications Platform</span></span>  <br/> |<span data-ttu-id="2a710-126">UCCP</span><span class="sxs-lookup"><span data-stu-id="2a710-126">UCCP</span></span>  <br/> |
|<span data-ttu-id="2a710-127">Lync 2010 Attendee</span><span class="sxs-lookup"><span data-stu-id="2a710-127">Lync 2010 Attendee</span></span>  <br/> |<span data-ttu-id="2a710-128">AOC</span><span class="sxs-lookup"><span data-stu-id="2a710-128">AOC</span></span>  <br/> |
|<span data-ttu-id="2a710-129">Complemento de Live Meeting</span><span class="sxs-lookup"><span data-stu-id="2a710-129">Live Meeting Add-In</span></span>  <br/> |<span data-ttu-id="2a710-130">LiveMeetingAddins</span><span class="sxs-lookup"><span data-stu-id="2a710-130">LiveMeetingAddins</span></span>  <br/> |
|<span data-ttu-id="2a710-131">Office Live Meeting</span><span class="sxs-lookup"><span data-stu-id="2a710-131">Office Live Meeting</span></span>  <br/> |<span data-ttu-id="2a710-132">LMC</span><span class="sxs-lookup"><span data-stu-id="2a710-132">LMC</span></span>  <br/> |
|<span data-ttu-id="2a710-133">Windows Messenger</span><span class="sxs-lookup"><span data-stu-id="2a710-133">Windows Messenger</span></span>  <br/> |<span data-ttu-id="2a710-134">WM</span><span class="sxs-lookup"><span data-stu-id="2a710-134">WM</span></span>  <br/> |
|<span data-ttu-id="2a710-135">Cliente de comunicaciones en tiempo real</span><span class="sxs-lookup"><span data-stu-id="2a710-135">Real-time Communications Client</span></span>  <br/> |<span data-ttu-id="2a710-136">RTC</span><span class="sxs-lookup"><span data-stu-id="2a710-136">RTC</span></span>  <br/> |
|<span data-ttu-id="2a710-137">Lync 2010 para iPad</span><span class="sxs-lookup"><span data-stu-id="2a710-137">Lync 2010 for iPad</span></span>  <br/> |<span data-ttu-id="2a710-138">iPadLync</span><span class="sxs-lookup"><span data-stu-id="2a710-138">iPadLync</span></span>  <br/> |
|<span data-ttu-id="2a710-139">Lync 2010 para iPhone</span><span class="sxs-lookup"><span data-stu-id="2a710-139">Lync 2010 for iPhone</span></span>  <br/> |<span data-ttu-id="2a710-140">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="2a710-140">iPhoneLync</span></span>  <br/> |
|<span data-ttu-id="2a710-141">Lync 2010 para Windows Phone</span><span class="sxs-lookup"><span data-stu-id="2a710-141">Lync 2010 for Windows Phone</span></span>  <br/> |<span data-ttu-id="2a710-142">WPLync</span><span class="sxs-lookup"><span data-stu-id="2a710-142">WPLync</span></span>  <br/> |
|<span data-ttu-id="2a710-143">Lync 2010 para Nokia</span><span class="sxs-lookup"><span data-stu-id="2a710-143">Lync 2010 for Nokia</span></span>  <br/> |<span data-ttu-id="2a710-144">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="2a710-144">NokiaLync</span></span>  <br/> |
|<span data-ttu-id="2a710-145">Lync 2010 para Android</span><span class="sxs-lookup"><span data-stu-id="2a710-145">Lync 2010 for Android</span></span>  <br/> |<span data-ttu-id="2a710-146">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="2a710-146">AndroidLync</span></span>  <br/> |
|<span data-ttu-id="2a710-147">Servicio de movilidad</span><span class="sxs-lookup"><span data-stu-id="2a710-147">Mobility service</span></span>  <br/> |<span data-ttu-id="2a710-148">McxService</span><span class="sxs-lookup"><span data-stu-id="2a710-148">McxService</span></span>  <br/> |
   
- <span data-ttu-id="2a710-149">**Número de versión** Puede especificar los números de versión para los siguientes campos, o usar caracteres comodín para indicar el número de versión de cliente.</span><span class="sxs-lookup"><span data-stu-id="2a710-149">**Version number** You can specify the version numbers for the following fields, or use wildcards to indicate the client version number.</span></span>
    
  - <span data-ttu-id="2a710-150">**Versión principal** Especifica el número que corresponde a la versión principal de versión del cliente.</span><span class="sxs-lookup"><span data-stu-id="2a710-150">**Major version** Specifies the number that corresponds to the major release of the client.</span></span>
    
  - <span data-ttu-id="2a710-151">**Versión secundaria** Especifica el número que corresponde a la versión secundaria del cliente.</span><span class="sxs-lookup"><span data-stu-id="2a710-151">**Minor version** Specifies the number that corresponds to the minor release of the client.</span></span>
    
  - <span data-ttu-id="2a710-152">**Crear** Especifica el número de compilación que corresponde a la versión principal y secundaria del cliente.</span><span class="sxs-lookup"><span data-stu-id="2a710-152">**Build** Specifies the build number that corresponds to the major and minor release of the client.</span></span>
    
  - <span data-ttu-id="2a710-153">**Actualización** Especifica el número que corresponde a la versión actualizada del cliente.</span><span class="sxs-lookup"><span data-stu-id="2a710-153">**Update** Specifies the number that corresponds to the updated release of the client.</span></span>
    
- <span data-ttu-id="2a710-154">**Operación de comparación** Puede especificar la operación coincidente para la versión de cliente que haya especificado en los pasos anteriores.</span><span class="sxs-lookup"><span data-stu-id="2a710-154">**Comparison operation** You can specify the matching operation for the client version you specified in the preceding steps.</span></span> <span data-ttu-id="2a710-155">Las siguientes operaciones están disponibles:</span><span class="sxs-lookup"><span data-stu-id="2a710-155">The following operations are available:</span></span>
    
  - <span data-ttu-id="2a710-156">**Igual que**</span><span class="sxs-lookup"><span data-stu-id="2a710-156">**Same as**</span></span>
    
  - <span data-ttu-id="2a710-157">**No es**</span><span class="sxs-lookup"><span data-stu-id="2a710-157">**Is not**</span></span>
    
  - <span data-ttu-id="2a710-158">**Anterior a**</span><span class="sxs-lookup"><span data-stu-id="2a710-158">**Newer than**</span></span>
    
  - <span data-ttu-id="2a710-159">**Anterior a o igual que**</span><span class="sxs-lookup"><span data-stu-id="2a710-159">**Newer than or same as**</span></span>
    
  - <span data-ttu-id="2a710-160">**Posterior a**</span><span class="sxs-lookup"><span data-stu-id="2a710-160">**Older than**</span></span>
    
  - <span data-ttu-id="2a710-161">**Posterior a o igual que**</span><span class="sxs-lookup"><span data-stu-id="2a710-161">**Older than or same as**</span></span>
    
- <span data-ttu-id="2a710-162">**Acción** Puede especificar la acción a realizar cuando se cumplen los criterios en los pasos anteriores.</span><span class="sxs-lookup"><span data-stu-id="2a710-162">**Action** You can specify the action to perform when the criteria in the preceding steps are met.</span></span> <span data-ttu-id="2a710-163">Están disponibles las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="2a710-163">The following actions are available:</span></span>
    
  - <span data-ttu-id="2a710-164">**Permitir** Permite que el cliente inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="2a710-164">**Allow** Allows the client to log on.</span></span>
    
  - <span data-ttu-id="2a710-165">**Permitir y actualizar** Permite que el cliente inicie sesión y recibir actualizaciones de servicio de actualización de Windows Server o Microsoft Update.</span><span class="sxs-lookup"><span data-stu-id="2a710-165">**Allow and Upgrade** Allows the client to log on and receive updates from Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="2a710-166">Esta acción solo está disponible cuando se selecciona **OC** como agente del usuario.</span><span class="sxs-lookup"><span data-stu-id="2a710-166">This action is available only when user agent **OC** is selected.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="2a710-167">Si se selecciona esta acción, una notificación para que aparezca la próxima vez que los usuarios iniciar sesión en Skype para la empresa.</span><span class="sxs-lookup"><span data-stu-id="2a710-167">Selecting this action causes a notification to appear the next time users sign in to Skype for Business.</span></span> <span data-ttu-id="2a710-168">La notificación comunica que hay una actualización disponible, aun cuando Windows Server Update Service o Microsoft Update todavía no la hayan publicado.</span><span class="sxs-lookup"><span data-stu-id="2a710-168">The notification states that an update is available, even if updates have not yet been released to Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="2a710-169">Para evitar confusiones, recomendamos elegir esta acción solo cuando las actualizaciones estén disponibles.</span><span class="sxs-lookup"><span data-stu-id="2a710-169">To avoid confusion, you should choose this action only after updates become available.</span></span> 
  
  - <span data-ttu-id="2a710-170">**Permitir con dirección URL** Permite que el cliente inicie sesión y muestra un mensaje acerca de dónde descargar otra versión de cliente.</span><span class="sxs-lookup"><span data-stu-id="2a710-170">**Allow with URL** Allows the client to log on and displays a message about where to download another client version.</span></span> <span data-ttu-id="2a710-171">Puede especificar la dirección URL en el campo **Dirección URL**.</span><span class="sxs-lookup"><span data-stu-id="2a710-171">You specify the URL in the **URL** field.</span></span>
    
  - <span data-ttu-id="2a710-172">**Bloque** Impide que el cliente de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="2a710-172">**Block** Prevents the client from logging on.</span></span>
    
  - <span data-ttu-id="2a710-173">**Bloque y actualización** Impide que al cliente de inicio de sesión y permite que el cliente recibir actualizaciones de servicio de actualización de Windows Server o Microsoft Update.</span><span class="sxs-lookup"><span data-stu-id="2a710-173">**Block and Upgrade** Prevents the client from logging on and allows the client to receive updates from Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="2a710-174">Esta acción solo está disponible cuando se selecciona **OC** como agente del usuario.</span><span class="sxs-lookup"><span data-stu-id="2a710-174">This action is available only when user agent **OC** is selected.</span></span>
    
  - <span data-ttu-id="2a710-p110">**Bloquear con dirección URL** Impide al cliente iniciar sesión y muestra un mensaje que indica dónde descargar otra versión del cliente. Puede especificar la dirección URL en el campo **Dirección URL**.</span><span class="sxs-lookup"><span data-stu-id="2a710-p110">**Block with URL** prevents the client from logging on and displays a message about where to download another client version. You specify the URL in the **URL** field.</span></span>
    
<span data-ttu-id="2a710-177">Para obtener información detallada acerca de la interoperabilidad entre clientes y versiones de cliente, consulte [Interoperabilidad del cliente](http://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="2a710-177">For details about interoperability among clients and client versions, see [Client Interoperability](http://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation.</span></span> <span data-ttu-id="2a710-178">Para obtener información detallada sobre cómo trabajar con las configuraciones de versión de cliente, vea [modificar la acción predeterminada para los clientes no admiten explícitamente o restringidos](http://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) en la documentación sobre operaciones.</span><span class="sxs-lookup"><span data-stu-id="2a710-178">For details about working with client version configurations, see [Modify the Default Action for Clients Not Explicitly Supported or Restricted](http://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) in the Operations documentation.</span></span>

