---
title: Regla de versiones de cliente
ms.reviewer: ''
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
ms.openlocfilehash: d1de600a3907d3e981bb1f706cdedbff05e965f0
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30887753"
---
# <a name="client-version-rule"></a><span data-ttu-id="99d29-104">Regla de versiones de cliente</span><span class="sxs-lookup"><span data-stu-id="99d29-104">Client Version Rule</span></span>

<span data-ttu-id="99d29-p102">Una directiva de versión de cliente está compuesta de un conjunto de reglas de versión de cliente. Estas reglas definen las acciones que se necesitan realizar cuando los usuarios intentan iniciar sesión con clientes y versiones de clientes específicos.</span><span class="sxs-lookup"><span data-stu-id="99d29-p102">A client version policy is made up of a set of client version rules. These rules define the actions that should be taken when users attempt to log on with specific clients and client versions.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="99d29-107">Tareas que puede realizar</span><span class="sxs-lookup"><span data-stu-id="99d29-107">Tasks you can perform</span></span>

<span data-ttu-id="99d29-108">En las páginas **Nueva configuración de versión de cliente** o **Editar configuración de versión de cliente** puede realizar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="99d29-108">You can perform the following tasks on the **New Client Version Configuration** or **Edit Client Version Configuration** page:</span></span>

- <span data-ttu-id="99d29-109">Agregar nuevas reglas a una directiva de versión de cliente.</span><span class="sxs-lookup"><span data-stu-id="99d29-109">Add new rules to a client version policy.</span></span>

- <span data-ttu-id="99d29-110">Modificar las reglas que componen una directiva de versión de cliente existente.</span><span class="sxs-lookup"><span data-stu-id="99d29-110">Modify the rules that make up an existing client version policy</span></span>

## <a name="ui-reference"></a><span data-ttu-id="99d29-111">Referencia de interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="99d29-111">UI Reference</span></span>

<span data-ttu-id="99d29-112">En las siguientes listas se describen los menús, comandos, campos y propiedades de la página.</span><span class="sxs-lookup"><span data-stu-id="99d29-112">The following lists describe the menus, command, fields, and properties on the page.</span></span>

- <span data-ttu-id="99d29-113">**Agente de usuario** Puede seleccionar un tipo de cliente de la lista.</span><span class="sxs-lookup"><span data-stu-id="99d29-113">**User agent** You can select a client type from the list.</span></span> <span data-ttu-id="99d29-114">En la siguiente tabla se recogen los códigos de agente de usuario.</span><span class="sxs-lookup"><span data-stu-id="99d29-114">The following table defines user agent codes.</span></span> <span data-ttu-id="99d29-115">Esta lista incluye los tipos de cliente heredado, algunas de las cuales ya no son compatibles.</span><span class="sxs-lookup"><span data-stu-id="99d29-115">This list includes legacy client types, some of which are no longer supported.</span></span>

|<span data-ttu-id="99d29-116">**Nombre de cliente**</span><span class="sxs-lookup"><span data-stu-id="99d29-116">**Client Name**</span></span>|<span data-ttu-id="99d29-117">**Agente de usuario**</span><span class="sxs-lookup"><span data-stu-id="99d29-117">**User Agent**</span></span>|
|:-----|:-----|
|<span data-ttu-id="99d29-118">Lync 2013, Lync 2010, Office Communicator</span><span class="sxs-lookup"><span data-stu-id="99d29-118">Lync 2013, Lync 2010, Office Communicator</span></span>  <br/> |<span data-ttu-id="99d29-119">OC</span><span class="sxs-lookup"><span data-stu-id="99d29-119">OC</span></span>  <br/> |
|<span data-ttu-id="99d29-120">Lync Web App, Communicator Web Access</span><span class="sxs-lookup"><span data-stu-id="99d29-120">Lync Web App, Communicator Web Access</span></span>  <br/> |<span data-ttu-id="99d29-121">CWA</span><span class="sxs-lookup"><span data-stu-id="99d29-121">CWA</span></span>  <br/> |
|<span data-ttu-id="99d29-122">Lync Phone Edition, Office Communicator Phone</span><span class="sxs-lookup"><span data-stu-id="99d29-122">Lync Phone Edition, Office Communicator Phone</span></span>  <br/> |<span data-ttu-id="99d29-123">OCPhone</span><span class="sxs-lookup"><span data-stu-id="99d29-123">OCPhone</span></span>  <br/> |
|<span data-ttu-id="99d29-124">Plataforma Communicator Phone Edition</span><span class="sxs-lookup"><span data-stu-id="99d29-124">Communicator Phone Edition Platform</span></span>  <br/> |<span data-ttu-id="99d29-125">CPE</span><span class="sxs-lookup"><span data-stu-id="99d29-125">CPE</span></span>  <br/> |
|<span data-ttu-id="99d29-126">Plataforma de comunicaciones unificadas</span><span class="sxs-lookup"><span data-stu-id="99d29-126">Unified Communications Platform</span></span>  <br/> |<span data-ttu-id="99d29-127">UCCP</span><span class="sxs-lookup"><span data-stu-id="99d29-127">UCCP</span></span>  <br/> |
|<span data-ttu-id="99d29-128">Lync 2010 Attendee</span><span class="sxs-lookup"><span data-stu-id="99d29-128">Lync 2010 Attendee</span></span>  <br/> |<span data-ttu-id="99d29-129">AOC</span><span class="sxs-lookup"><span data-stu-id="99d29-129">AOC</span></span>  <br/> |
|<span data-ttu-id="99d29-130">Complemento de Live Meeting</span><span class="sxs-lookup"><span data-stu-id="99d29-130">Live Meeting Add-In</span></span>  <br/> |<span data-ttu-id="99d29-131">LiveMeetingAddins</span><span class="sxs-lookup"><span data-stu-id="99d29-131">LiveMeetingAddins</span></span>  <br/> |
|<span data-ttu-id="99d29-132">Office Live Meeting</span><span class="sxs-lookup"><span data-stu-id="99d29-132">Office Live Meeting</span></span>  <br/> |<span data-ttu-id="99d29-133">LMC</span><span class="sxs-lookup"><span data-stu-id="99d29-133">LMC</span></span>  <br/> |
|<span data-ttu-id="99d29-134">Windows Messenger</span><span class="sxs-lookup"><span data-stu-id="99d29-134">Windows Messenger</span></span>  <br/> |<span data-ttu-id="99d29-135">WM</span><span class="sxs-lookup"><span data-stu-id="99d29-135">WM</span></span>  <br/> |
|<span data-ttu-id="99d29-136">Cliente de comunicaciones en tiempo real</span><span class="sxs-lookup"><span data-stu-id="99d29-136">Real-time Communications Client</span></span>  <br/> |<span data-ttu-id="99d29-137">RTC</span><span class="sxs-lookup"><span data-stu-id="99d29-137">RTC</span></span>  <br/> |
|<span data-ttu-id="99d29-138">Lync 2010 para iPad</span><span class="sxs-lookup"><span data-stu-id="99d29-138">Lync 2010 for iPad</span></span>  <br/> |<span data-ttu-id="99d29-139">iPadLync</span><span class="sxs-lookup"><span data-stu-id="99d29-139">iPadLync</span></span>  <br/> |
|<span data-ttu-id="99d29-140">Lync 2010 para iPhone</span><span class="sxs-lookup"><span data-stu-id="99d29-140">Lync 2010 for iPhone</span></span>  <br/> |<span data-ttu-id="99d29-141">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="99d29-141">iPhoneLync</span></span>  <br/> |
|<span data-ttu-id="99d29-142">Lync 2010 para Windows Phone</span><span class="sxs-lookup"><span data-stu-id="99d29-142">Lync 2010 for Windows Phone</span></span>  <br/> |<span data-ttu-id="99d29-143">WPLync</span><span class="sxs-lookup"><span data-stu-id="99d29-143">WPLync</span></span>  <br/> |
|<span data-ttu-id="99d29-144">Lync 2010 para Nokia</span><span class="sxs-lookup"><span data-stu-id="99d29-144">Lync 2010 for Nokia</span></span>  <br/> |<span data-ttu-id="99d29-145">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="99d29-145">NokiaLync</span></span>  <br/> |
|<span data-ttu-id="99d29-146">Lync 2010 para Android</span><span class="sxs-lookup"><span data-stu-id="99d29-146">Lync 2010 for Android</span></span>  <br/> |<span data-ttu-id="99d29-147">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="99d29-147">AndroidLync</span></span>  <br/> |
|<span data-ttu-id="99d29-148">Servicio de movilidad</span><span class="sxs-lookup"><span data-stu-id="99d29-148">Mobility service</span></span>  <br/> |<span data-ttu-id="99d29-149">McxService</span><span class="sxs-lookup"><span data-stu-id="99d29-149">McxService</span></span>  <br/> |

- <span data-ttu-id="99d29-150">**Número de versión** Puede especificar los números de versión para los siguientes campos, o usar caracteres comodín para indicar el número de versión de cliente.</span><span class="sxs-lookup"><span data-stu-id="99d29-150">**Version number** You can specify the version numbers for the following fields, or use wildcards to indicate the client version number.</span></span>

  - <span data-ttu-id="99d29-151">**Versión principal** Especifica el número que corresponde a la versión principal de versión del cliente.</span><span class="sxs-lookup"><span data-stu-id="99d29-151">**Major version** Specifies the number that corresponds to the major release of the client.</span></span>

  - <span data-ttu-id="99d29-152">**Versión secundaria** Especifica el número que corresponde a la versión secundaria del cliente.</span><span class="sxs-lookup"><span data-stu-id="99d29-152">**Minor version** Specifies the number that corresponds to the minor release of the client.</span></span>

  - <span data-ttu-id="99d29-153">**Crear** Especifica el número de compilación que corresponde a la versión principal y secundaria del cliente.</span><span class="sxs-lookup"><span data-stu-id="99d29-153">**Build** Specifies the build number that corresponds to the major and minor release of the client.</span></span>

  - <span data-ttu-id="99d29-154">**Actualización** Especifica el número que corresponde a la versión actualizada del cliente.</span><span class="sxs-lookup"><span data-stu-id="99d29-154">**Update** Specifies the number that corresponds to the updated release of the client.</span></span>

- <span data-ttu-id="99d29-155">**Operación de comparación** Puede especificar la operación coincidente para la versión de cliente que haya especificado en los pasos anteriores.</span><span class="sxs-lookup"><span data-stu-id="99d29-155">**Comparison operation** You can specify the matching operation for the client version you specified in the preceding steps.</span></span> <span data-ttu-id="99d29-156">Las siguientes operaciones están disponibles:</span><span class="sxs-lookup"><span data-stu-id="99d29-156">The following operations are available:</span></span>

  - <span data-ttu-id="99d29-157">**Igual que**</span><span class="sxs-lookup"><span data-stu-id="99d29-157">**Same as**</span></span>

  - <span data-ttu-id="99d29-158">**No es**</span><span class="sxs-lookup"><span data-stu-id="99d29-158">**Is not**</span></span>

  - <span data-ttu-id="99d29-159">**Anterior a**</span><span class="sxs-lookup"><span data-stu-id="99d29-159">**Newer than**</span></span>

  - <span data-ttu-id="99d29-160">**Anterior a o igual que**</span><span class="sxs-lookup"><span data-stu-id="99d29-160">**Newer than or same as**</span></span>

  - <span data-ttu-id="99d29-161">**Posterior a**</span><span class="sxs-lookup"><span data-stu-id="99d29-161">**Older than**</span></span>

  - <span data-ttu-id="99d29-162">**Posterior a o igual que**</span><span class="sxs-lookup"><span data-stu-id="99d29-162">**Older than or same as**</span></span>

- <span data-ttu-id="99d29-163">**Acción** Puede especificar la acción a realizar cuando se cumplen los criterios en los pasos anteriores.</span><span class="sxs-lookup"><span data-stu-id="99d29-163">**Action** You can specify the action to perform when the criteria in the preceding steps are met.</span></span> <span data-ttu-id="99d29-164">Están disponibles las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="99d29-164">The following actions are available:</span></span>

  - <span data-ttu-id="99d29-165">**Permitir** Permite que el cliente inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="99d29-165">**Allow** Allows the client to log on.</span></span>

  - <span data-ttu-id="99d29-166">**Permitir y actualizar** Permite que el cliente inicie sesión y recibir actualizaciones de servicio de actualización de Windows Server o Microsoft Update.</span><span class="sxs-lookup"><span data-stu-id="99d29-166">**Allow and Upgrade** Allows the client to log on and receive updates from Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="99d29-167">Esta acción solo está disponible cuando se selecciona **OC** como agente del usuario.</span><span class="sxs-lookup"><span data-stu-id="99d29-167">This action is available only when user agent **OC** is selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="99d29-168">Si se selecciona esta acción, una notificación para que aparezca la próxima vez que los usuarios iniciar sesión en Skype para la empresa.</span><span class="sxs-lookup"><span data-stu-id="99d29-168">Selecting this action causes a notification to appear the next time users sign in to Skype for Business.</span></span> <span data-ttu-id="99d29-169">La notificación comunica que hay una actualización disponible, aun cuando Windows Server Update Service o Microsoft Update todavía no la hayan publicado.</span><span class="sxs-lookup"><span data-stu-id="99d29-169">The notification states that an update is available, even if updates have not yet been released to Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="99d29-170">Para evitar confusiones, recomendamos elegir esta acción solo cuando las actualizaciones estén disponibles.</span><span class="sxs-lookup"><span data-stu-id="99d29-170">To avoid confusion, you should choose this action only after updates become available.</span></span>

  - <span data-ttu-id="99d29-171">**Permitir con dirección URL** Permite que el cliente inicie sesión y muestra un mensaje acerca de dónde descargar otra versión de cliente.</span><span class="sxs-lookup"><span data-stu-id="99d29-171">**Allow with URL** Allows the client to log on and displays a message about where to download another client version.</span></span> <span data-ttu-id="99d29-172">Puede especificar la dirección URL en el campo **Dirección URL**.</span><span class="sxs-lookup"><span data-stu-id="99d29-172">You specify the URL in the **URL** field.</span></span>

  - <span data-ttu-id="99d29-173">**Bloque** Impide que el cliente de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="99d29-173">**Block** Prevents the client from logging on.</span></span>

  - <span data-ttu-id="99d29-174">**Bloque y actualización** Impide que al cliente de inicio de sesión y permite que el cliente recibir actualizaciones de servicio de actualización de Windows Server o Microsoft Update.</span><span class="sxs-lookup"><span data-stu-id="99d29-174">**Block and Upgrade** Prevents the client from logging on and allows the client to receive updates from Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="99d29-175">Esta acción solo está disponible cuando se selecciona **OC** como agente del usuario.</span><span class="sxs-lookup"><span data-stu-id="99d29-175">This action is available only when user agent **OC** is selected.</span></span>

  - <span data-ttu-id="99d29-p110">**Bloquear con dirección URL** Impide al cliente iniciar sesión y muestra un mensaje que indica dónde descargar otra versión del cliente. Puede especificar la dirección URL en el campo **Dirección URL**.</span><span class="sxs-lookup"><span data-stu-id="99d29-p110">**Block with URL** prevents the client from logging on and displays a message about where to download another client version. You specify the URL in the **URL** field.</span></span>

<span data-ttu-id="99d29-178">Para obtener información detallada acerca de la interoperabilidad entre clientes y versiones de cliente, consulte [Interoperabilidad del cliente](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="99d29-178">For details about interoperability among clients and client versions, see [Client Interoperability](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation.</span></span> <span data-ttu-id="99d29-179">Para más detalles sobre cómo trabajar con configuraciones de versiones de clientes, mire [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="99d29-179">For details about working with client version configurations, see [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) in the Operations documentation.</span></span>

