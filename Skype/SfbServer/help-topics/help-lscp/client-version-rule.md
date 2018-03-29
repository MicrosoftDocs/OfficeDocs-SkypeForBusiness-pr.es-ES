---
title: Regla de versiones de cliente
ms.author: dianef
author: dianef77
manager: serdars
ms.date: 3/23/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVPolicyRuleEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6e7e94c2-1475-4334-b8da-716b24a4c255
description: Una directiva de versión de cliente está compuesta de un conjunto de reglas de versión de cliente. Estas reglas definen las acciones que se necesitan realizar cuando los usuarios intentan iniciar sesión con clientes y versiones de clientes específicos.
ms.openlocfilehash: 88316487ccd6f061127f92a762ac2d8c17b6a9c7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="client-version-rule"></a><span data-ttu-id="953c4-104">Regla de versiones de cliente</span><span class="sxs-lookup"><span data-stu-id="953c4-104">Client Version Rule</span></span>
 
<span data-ttu-id="953c4-p102">Una directiva de versión de cliente está compuesta de un conjunto de reglas de versión de cliente. Estas reglas definen las acciones que se necesitan realizar cuando los usuarios intentan iniciar sesión con clientes y versiones de clientes específicos.</span><span class="sxs-lookup"><span data-stu-id="953c4-p102">A client version policy is made up of a set of client version rules. These rules define the actions that should be taken when users attempt to log on with specific clients and client versions.</span></span>
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="953c4-107">Tareas que puede realizar</span><span class="sxs-lookup"><span data-stu-id="953c4-107">Tasks you can perform</span></span>

<span data-ttu-id="953c4-108">En las páginas **Nueva configuración de versión de cliente** o **Editar configuración de versión de cliente** puede realizar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="953c4-108">You can perform the following tasks on the **New Client Version Configuration** or **Edit Client Version Configuration** page:</span></span>
  
- <span data-ttu-id="953c4-109">Agregar nuevas reglas a una directiva de versión de cliente.</span><span class="sxs-lookup"><span data-stu-id="953c4-109">Add new rules to a client version policy.</span></span>
    
- <span data-ttu-id="953c4-110">Modificar las reglas que componen una directiva de versión de cliente existente.</span><span class="sxs-lookup"><span data-stu-id="953c4-110">Modify the rules that make up an existing client version policy</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="953c4-111">Referencia de interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="953c4-111">UI Reference</span></span>

<span data-ttu-id="953c4-112">En las siguientes listas se describen los menús, comandos, campos y propiedades de la página.</span><span class="sxs-lookup"><span data-stu-id="953c4-112">The following lists describe the menus, command, fields, and properties on the page.</span></span>
  
- <span data-ttu-id="953c4-113">**Agente de usuario** Puede seleccionar un tipo de cliente de la lista.</span><span class="sxs-lookup"><span data-stu-id="953c4-113">**User agent** You can select a client type from the list.</span></span> <span data-ttu-id="953c4-114">En la siguiente tabla se recogen los códigos de agente de usuario.</span><span class="sxs-lookup"><span data-stu-id="953c4-114">The following table defines user agent codes.</span></span>
    
|<span data-ttu-id="953c4-115">**Nombre del cliente**</span><span class="sxs-lookup"><span data-stu-id="953c4-115">**Client Name**</span></span>|<span data-ttu-id="953c4-116">**Agente de usuario**</span><span class="sxs-lookup"><span data-stu-id="953c4-116">**User Agent**</span></span>|
|:-----|:-----|
|<span data-ttu-id="953c4-117">2013 de Lync, Lync 2010, Office Communicator</span><span class="sxs-lookup"><span data-stu-id="953c4-117">Lync 2013, Lync 2010, Office Communicator</span></span>  <br/> |<span data-ttu-id="953c4-118">Componente opcional</span><span class="sxs-lookup"><span data-stu-id="953c4-118">OC</span></span>  <br/> |
|<span data-ttu-id="953c4-119">Aplicación Web de Lync, Communicator Web Access</span><span class="sxs-lookup"><span data-stu-id="953c4-119">Lync Web App, Communicator Web Access</span></span>  <br/> |<span data-ttu-id="953c4-120">CWA</span><span class="sxs-lookup"><span data-stu-id="953c4-120">CWA</span></span>  <br/> |
|<span data-ttu-id="953c4-121">Lync Phone Edition, Office Communicator Phone</span><span class="sxs-lookup"><span data-stu-id="953c4-121">Lync Phone Edition, Office Communicator Phone</span></span>  <br/> |<span data-ttu-id="953c4-122">OCPhone</span><span class="sxs-lookup"><span data-stu-id="953c4-122">OCPhone</span></span>  <br/> |
|<span data-ttu-id="953c4-123">Plataforma Communicator Phone Edition</span><span class="sxs-lookup"><span data-stu-id="953c4-123">Communicator Phone Edition Platform</span></span>  <br/> |<span data-ttu-id="953c4-124">CPE</span><span class="sxs-lookup"><span data-stu-id="953c4-124">CPE</span></span>  <br/> |
|<span data-ttu-id="953c4-125">Plataforma de comunicaciones unificadas</span><span class="sxs-lookup"><span data-stu-id="953c4-125">Unified Communications Platform</span></span>  <br/> |<span data-ttu-id="953c4-126">UCCP</span><span class="sxs-lookup"><span data-stu-id="953c4-126">UCCP</span></span>  <br/> |
|<span data-ttu-id="953c4-127">Lync 2010 Attendee</span><span class="sxs-lookup"><span data-stu-id="953c4-127">Lync 2010 Attendee</span></span>  <br/> |<span data-ttu-id="953c4-128">AOC</span><span class="sxs-lookup"><span data-stu-id="953c4-128">AOC</span></span>  <br/> |
|<span data-ttu-id="953c4-129">Complemento de Live Meeting</span><span class="sxs-lookup"><span data-stu-id="953c4-129">Live Meeting Add-In</span></span>  <br/> |<span data-ttu-id="953c4-130">LiveMeetingAddins</span><span class="sxs-lookup"><span data-stu-id="953c4-130">LiveMeetingAddins</span></span>  <br/> |
|<span data-ttu-id="953c4-131">Office Live Meeting</span><span class="sxs-lookup"><span data-stu-id="953c4-131">Office Live Meeting</span></span>  <br/> |<span data-ttu-id="953c4-132">LMC</span><span class="sxs-lookup"><span data-stu-id="953c4-132">LMC</span></span>  <br/> |
|<span data-ttu-id="953c4-133">Windows Messenger</span><span class="sxs-lookup"><span data-stu-id="953c4-133">Windows Messenger</span></span>  <br/> |<span data-ttu-id="953c4-134">WM</span><span class="sxs-lookup"><span data-stu-id="953c4-134">WM</span></span>  <br/> |
|<span data-ttu-id="953c4-135">Cliente de comunicaciones en tiempo real</span><span class="sxs-lookup"><span data-stu-id="953c4-135">Real-time Communications Client</span></span>  <br/> |<span data-ttu-id="953c4-136">RTC</span><span class="sxs-lookup"><span data-stu-id="953c4-136">RTC</span></span>  <br/> |
|<span data-ttu-id="953c4-137">Lync 2010 para iPad</span><span class="sxs-lookup"><span data-stu-id="953c4-137">Lync 2010 for iPad</span></span>  <br/> |<span data-ttu-id="953c4-138">iPadLync</span><span class="sxs-lookup"><span data-stu-id="953c4-138">iPadLync</span></span>  <br/> |
|<span data-ttu-id="953c4-139">Lync 2010 para iPhone</span><span class="sxs-lookup"><span data-stu-id="953c4-139">Lync 2010 for iPhone</span></span>  <br/> |<span data-ttu-id="953c4-140">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="953c4-140">iPhoneLync</span></span>  <br/> |
|<span data-ttu-id="953c4-141">Lync 2010 para Windows Phone</span><span class="sxs-lookup"><span data-stu-id="953c4-141">Lync 2010 for Windows Phone</span></span>  <br/> |<span data-ttu-id="953c4-142">WPLync</span><span class="sxs-lookup"><span data-stu-id="953c4-142">WPLync</span></span>  <br/> |
|<span data-ttu-id="953c4-143">Lync 2010 para Nokia</span><span class="sxs-lookup"><span data-stu-id="953c4-143">Lync 2010 for Nokia</span></span>  <br/> |<span data-ttu-id="953c4-144">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="953c4-144">NokiaLync</span></span>  <br/> |
|<span data-ttu-id="953c4-145">Lync 2010 para Android</span><span class="sxs-lookup"><span data-stu-id="953c4-145">Lync 2010 for Android</span></span>  <br/> |<span data-ttu-id="953c4-146">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="953c4-146">AndroidLync</span></span>  <br/> |
|<span data-ttu-id="953c4-147">Servicio de movilidad</span><span class="sxs-lookup"><span data-stu-id="953c4-147">Mobility service</span></span>  <br/> |<span data-ttu-id="953c4-148">McxService</span><span class="sxs-lookup"><span data-stu-id="953c4-148">McxService</span></span>  <br/> |
   
- <span data-ttu-id="953c4-149">**Número de versión** Puede especificar los números de versión para los siguientes campos, o utilizar comodines para indicar el número de versión del cliente.</span><span class="sxs-lookup"><span data-stu-id="953c4-149">**Version number** You can specify the version numbers for the following fields, or use wildcards to indicate the client version number.</span></span>
    
  - <span data-ttu-id="953c4-150">**Versión principal** Especifica el número que corresponde a la principal versión del cliente.</span><span class="sxs-lookup"><span data-stu-id="953c4-150">**Major version** Specifies the number that corresponds to the major release of the client.</span></span>
    
  - <span data-ttu-id="953c4-151">**Versión secundaria** Especifica el número que corresponde a la versión secundaria del cliente.</span><span class="sxs-lookup"><span data-stu-id="953c4-151">**Minor version** Specifies the number that corresponds to the minor release of the client.</span></span>
    
  - <span data-ttu-id="953c4-152">**Generar** Especifica el número de generación que corresponde a la versión principal y secundaria del cliente.</span><span class="sxs-lookup"><span data-stu-id="953c4-152">**Build** Specifies the build number that corresponds to the major and minor release of the client.</span></span>
    
  - <span data-ttu-id="953c4-153">**Actualización** Especifica el número que corresponde a la versión actualizada del cliente.</span><span class="sxs-lookup"><span data-stu-id="953c4-153">**Update** Specifies the number that corresponds to the updated release of the client.</span></span>
    
- <span data-ttu-id="953c4-154">**Operación de comparación** Puede especificar la operación de coincidencia para la versión de cliente especificado en los pasos anteriores.</span><span class="sxs-lookup"><span data-stu-id="953c4-154">**Comparison operation** You can specify the matching operation for the client version you specified in the preceding steps.</span></span> <span data-ttu-id="953c4-155">Las siguientes operaciones están disponibles:</span><span class="sxs-lookup"><span data-stu-id="953c4-155">The following operations are available:</span></span>
    
  - <span data-ttu-id="953c4-156">**Igual que**</span><span class="sxs-lookup"><span data-stu-id="953c4-156">**Same as**</span></span>
    
  - <span data-ttu-id="953c4-157">**No es**</span><span class="sxs-lookup"><span data-stu-id="953c4-157">**Is not**</span></span>
    
  - <span data-ttu-id="953c4-158">**Anterior a**</span><span class="sxs-lookup"><span data-stu-id="953c4-158">**Newer than**</span></span>
    
  - <span data-ttu-id="953c4-159">**Anterior a o igual que**</span><span class="sxs-lookup"><span data-stu-id="953c4-159">**Newer than or same as**</span></span>
    
  - <span data-ttu-id="953c4-160">**Posterior a**</span><span class="sxs-lookup"><span data-stu-id="953c4-160">**Older than**</span></span>
    
  - <span data-ttu-id="953c4-161">**Posterior a o igual que**</span><span class="sxs-lookup"><span data-stu-id="953c4-161">**Older than or same as**</span></span>
    
- <span data-ttu-id="953c4-162">**Acción** Puede especificar la acción a realizar cuando se cumplan los criterios en los pasos anteriores.</span><span class="sxs-lookup"><span data-stu-id="953c4-162">**Action** You can specify the action to perform when the criteria in the preceding steps are met.</span></span> <span data-ttu-id="953c4-163">Están disponibles las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="953c4-163">The following actions are available:</span></span>
    
  - <span data-ttu-id="953c4-164">**Permitir** Permite al cliente iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="953c4-164">**Allow** Allows the client to log on.</span></span>
    
  - <span data-ttu-id="953c4-165">**Permitir y actualizar** Permite al cliente iniciar sesión y recibir actualizaciones desde Microsoft Update o de Windows Server Update Services.</span><span class="sxs-lookup"><span data-stu-id="953c4-165">**Allow and Upgrade** Allows the client to log on and receive updates from Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="953c4-166">Esta acción solo está disponible cuando se selecciona **OC** como agente del usuario.</span><span class="sxs-lookup"><span data-stu-id="953c4-166">This action is available only when user agent **OC** is selected.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="953c4-167">Si se selecciona esta acción, una notificación para que aparezca la próxima vez que los usuarios iniciar sesión en Skype para empresas.</span><span class="sxs-lookup"><span data-stu-id="953c4-167">Selecting this action causes a notification to appear the next time users sign in to Skype for Business.</span></span> <span data-ttu-id="953c4-168">La notificación comunica que hay una actualización disponible, aun cuando Windows Server Update Service o Microsoft Update todavía no la hayan publicado.</span><span class="sxs-lookup"><span data-stu-id="953c4-168">The notification states that an update is available, even if updates have not yet been released to Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="953c4-169">Para evitar confusiones, recomendamos elegir esta acción solo cuando las actualizaciones estén disponibles.</span><span class="sxs-lookup"><span data-stu-id="953c4-169">To avoid confusion, you should choose this action only after updates become available.</span></span> 
  
  - <span data-ttu-id="953c4-170">**Permitir con dirección URL** Permite al cliente iniciar sesión y muestra un mensaje acerca de dónde descargar otra versión del cliente.</span><span class="sxs-lookup"><span data-stu-id="953c4-170">**Allow with URL** Allows the client to log on and displays a message about where to download another client version.</span></span> <span data-ttu-id="953c4-171">Puede especificar la dirección URL en el campo **Dirección URL**.</span><span class="sxs-lookup"><span data-stu-id="953c4-171">You specify the URL in the **URL** field.</span></span>
    
  - <span data-ttu-id="953c4-172">**Bloque** Impide que el cliente iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="953c4-172">**Block** Prevents the client from logging on.</span></span>
    
  - <span data-ttu-id="953c4-173">**Bloque y actualización** Impide que el cliente de inicio de sesión y permite al cliente recibir actualizaciones desde Microsoft Update o de Windows Server Update Services.</span><span class="sxs-lookup"><span data-stu-id="953c4-173">**Block and Upgrade** Prevents the client from logging on and allows the client to receive updates from Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="953c4-174">Esta acción solo está disponible cuando se selecciona **OC** como agente del usuario.</span><span class="sxs-lookup"><span data-stu-id="953c4-174">This action is available only when user agent **OC** is selected.</span></span>
    
  - <span data-ttu-id="953c4-p110">**Bloquear con dirección URL** Impide al cliente iniciar sesión y muestra un mensaje que indica dónde descargar otra versión del cliente. Puede especificar la dirección URL en el campo **Dirección URL**.</span><span class="sxs-lookup"><span data-stu-id="953c4-p110">**Block with URL** prevents the client from logging on and displays a message about where to download another client version. You specify the URL in the **URL** field.</span></span>
    
<span data-ttu-id="953c4-177">Para obtener más información acerca de la interoperabilidad entre los clientes y las versiones de cliente, vea [Interoperabilidad de cliente en la vista previa de 2013 Lync](http://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) en la documentación de planeamiento.</span><span class="sxs-lookup"><span data-stu-id="953c4-177">For details about interoperability among clients and client versions, see [Client Interoperability in Lync 2013 Preview](http://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation.</span></span> <span data-ttu-id="953c4-178">Para obtener más información sobre cómo trabajar con las configuraciones de versión de cliente, vea [modificar la acción predeterminada para clientes no admitidas explícitamente o restringido](http://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) en la documentación de las operaciones.</span><span class="sxs-lookup"><span data-stu-id="953c4-178">For details about working with client version configurations, see [Modify the Default Action for Clients Not Explicitly Supported or Restricted](http://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) in the Operations documentation.</span></span>

