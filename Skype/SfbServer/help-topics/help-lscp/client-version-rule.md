---
title: Regla de versiones de cliente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientCVPolicyRuleEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6e7e94c2-1475-4334-b8da-716b24a4c255
description: Una directiva de versión de cliente está compuesta de un conjunto de reglas de versión de cliente. Estas reglas definen las acciones que se necesitan realizar cuando los usuarios intentan iniciar sesión con clientes y versiones de clientes específicos.
ms.openlocfilehash: 870f0d46ff50b4fabab9b4f098cb569ae2c9ee82
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41823063"
---
# <a name="client-version-rule"></a><span data-ttu-id="88427-104">Regla de versiones de cliente</span><span class="sxs-lookup"><span data-stu-id="88427-104">Client Version Rule</span></span>

<span data-ttu-id="88427-p102">Una directiva de versión de cliente está compuesta de un conjunto de reglas de versión de cliente. Estas reglas definen las acciones que se necesitan realizar cuando los usuarios intentan iniciar sesión con clientes y versiones de clientes específicos.</span><span class="sxs-lookup"><span data-stu-id="88427-p102">A client version policy is made up of a set of client version rules. These rules define the actions that should be taken when users attempt to log on with specific clients and client versions.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="88427-107">Tareas que puede realizar</span><span class="sxs-lookup"><span data-stu-id="88427-107">Tasks you can perform</span></span>

<span data-ttu-id="88427-108">En las páginas **Nueva configuración de versión de cliente** o **Editar configuración de versión de cliente** puede realizar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="88427-108">You can perform the following tasks on the **New Client Version Configuration** or **Edit Client Version Configuration** page:</span></span>

- <span data-ttu-id="88427-109">Agregar nuevas reglas a una directiva de versión de cliente.</span><span class="sxs-lookup"><span data-stu-id="88427-109">Add new rules to a client version policy.</span></span>

- <span data-ttu-id="88427-110">Modificar las reglas que componen una directiva de versión de cliente existente.</span><span class="sxs-lookup"><span data-stu-id="88427-110">Modify the rules that make up an existing client version policy</span></span>

## <a name="ui-reference"></a><span data-ttu-id="88427-111">Referencia de interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="88427-111">UI Reference</span></span>

<span data-ttu-id="88427-112">En las siguientes listas se describen los menús, comandos, campos y propiedades de la página.</span><span class="sxs-lookup"><span data-stu-id="88427-112">The following lists describe the menus, command, fields, and properties on the page.</span></span>

- <span data-ttu-id="88427-113">**Agente de usuario** Puede seleccionar un tipo de cliente de la lista.</span><span class="sxs-lookup"><span data-stu-id="88427-113">**User agent** You can select a client type from the list.</span></span> <span data-ttu-id="88427-114">En la siguiente tabla se recogen los códigos de agente de usuario.</span><span class="sxs-lookup"><span data-stu-id="88427-114">The following table defines user agent codes.</span></span>

|<span data-ttu-id="88427-115">**Nombre de cliente**</span><span class="sxs-lookup"><span data-stu-id="88427-115">**Client Name**</span></span>|<span data-ttu-id="88427-116">**Agente de usuario**</span><span class="sxs-lookup"><span data-stu-id="88427-116">**User Agent**</span></span>|
|:-----|:-----|
|<span data-ttu-id="88427-117">Lync 2013, Lync 2010, Office Communicator</span><span class="sxs-lookup"><span data-stu-id="88427-117">Lync 2013, Lync 2010, Office Communicator</span></span>  <br/> |<span data-ttu-id="88427-118">OC</span><span class="sxs-lookup"><span data-stu-id="88427-118">OC</span></span>  <br/> |
|<span data-ttu-id="88427-119">Lync Web App, Communicator Web Access</span><span class="sxs-lookup"><span data-stu-id="88427-119">Lync Web App, Communicator Web Access</span></span>  <br/> |<span data-ttu-id="88427-120">CWA</span><span class="sxs-lookup"><span data-stu-id="88427-120">CWA</span></span>  <br/> |
|<span data-ttu-id="88427-121">Lync Phone Edition, teléfono de Office Communicator</span><span class="sxs-lookup"><span data-stu-id="88427-121">Lync Phone Edition, Office Communicator Phone</span></span>  <br/> |<span data-ttu-id="88427-122">OCPhone</span><span class="sxs-lookup"><span data-stu-id="88427-122">OCPhone</span></span>  <br/> |
|<span data-ttu-id="88427-123">Plataforma Communicator Phone Edition</span><span class="sxs-lookup"><span data-stu-id="88427-123">Communicator Phone Edition Platform</span></span>  <br/> |<span data-ttu-id="88427-124">CPE</span><span class="sxs-lookup"><span data-stu-id="88427-124">CPE</span></span>  <br/> |
|<span data-ttu-id="88427-125">Plataforma de comunicaciones unificadas</span><span class="sxs-lookup"><span data-stu-id="88427-125">Unified Communications Platform</span></span>  <br/> |<span data-ttu-id="88427-126">UCCP</span><span class="sxs-lookup"><span data-stu-id="88427-126">UCCP</span></span>  <br/> |
|<span data-ttu-id="88427-127">Lync 2010 Attendee</span><span class="sxs-lookup"><span data-stu-id="88427-127">Lync 2010 Attendee</span></span>  <br/> |<span data-ttu-id="88427-128">AOC</span><span class="sxs-lookup"><span data-stu-id="88427-128">AOC</span></span>  <br/> |
|<span data-ttu-id="88427-129">Complemento de Live Meeting</span><span class="sxs-lookup"><span data-stu-id="88427-129">Live Meeting Add-In</span></span>  <br/> |<span data-ttu-id="88427-130">LiveMeetingAddins</span><span class="sxs-lookup"><span data-stu-id="88427-130">LiveMeetingAddins</span></span>  <br/> |
|<span data-ttu-id="88427-131">Office Live Meeting</span><span class="sxs-lookup"><span data-stu-id="88427-131">Office Live Meeting</span></span>  <br/> |<span data-ttu-id="88427-132">LMC</span><span class="sxs-lookup"><span data-stu-id="88427-132">LMC</span></span>  <br/> |
|<span data-ttu-id="88427-133">Windows Messenger</span><span class="sxs-lookup"><span data-stu-id="88427-133">Windows Messenger</span></span>  <br/> |<span data-ttu-id="88427-134">WM</span><span class="sxs-lookup"><span data-stu-id="88427-134">WM</span></span>  <br/> |
|<span data-ttu-id="88427-135">Cliente de comunicaciones en tiempo real</span><span class="sxs-lookup"><span data-stu-id="88427-135">Real-time Communications Client</span></span>  <br/> |<span data-ttu-id="88427-136">RTC</span><span class="sxs-lookup"><span data-stu-id="88427-136">RTC</span></span>  <br/> |
|<span data-ttu-id="88427-137">Lync 2010 para iPad</span><span class="sxs-lookup"><span data-stu-id="88427-137">Lync 2010 for iPad</span></span>  <br/> |<span data-ttu-id="88427-138">iPadLync</span><span class="sxs-lookup"><span data-stu-id="88427-138">iPadLync</span></span>  <br/> |
|<span data-ttu-id="88427-139">Lync 2010 para iPhone</span><span class="sxs-lookup"><span data-stu-id="88427-139">Lync 2010 for iPhone</span></span>  <br/> |<span data-ttu-id="88427-140">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="88427-140">iPhoneLync</span></span>  <br/> |
|<span data-ttu-id="88427-141">Lync 2010 para Windows Phone</span><span class="sxs-lookup"><span data-stu-id="88427-141">Lync 2010 for Windows Phone</span></span>  <br/> |<span data-ttu-id="88427-142">WPLync</span><span class="sxs-lookup"><span data-stu-id="88427-142">WPLync</span></span>  <br/> |
|<span data-ttu-id="88427-143">Lync 2010 para Nokia</span><span class="sxs-lookup"><span data-stu-id="88427-143">Lync 2010 for Nokia</span></span>  <br/> |<span data-ttu-id="88427-144">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="88427-144">NokiaLync</span></span>  <br/> |
|<span data-ttu-id="88427-145">Lync 2010 para Android</span><span class="sxs-lookup"><span data-stu-id="88427-145">Lync 2010 for Android</span></span>  <br/> |<span data-ttu-id="88427-146">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="88427-146">AndroidLync</span></span>  <br/> |
|<span data-ttu-id="88427-147">Servicio de movilidad</span><span class="sxs-lookup"><span data-stu-id="88427-147">Mobility service</span></span>  <br/> |<span data-ttu-id="88427-148">McxService</span><span class="sxs-lookup"><span data-stu-id="88427-148">McxService</span></span>  <br/> |

- <span data-ttu-id="88427-149">**Número de versión** Puede especificar los números de versión de los siguientes campos, o usar caracteres comodín para indicar el número de versión del cliente.</span><span class="sxs-lookup"><span data-stu-id="88427-149">**Version number** You can specify the version numbers for the following fields, or use wildcards to indicate the client version number.</span></span>

  - <span data-ttu-id="88427-150">**Versión principal** Especifica el número que corresponde a la versión principal del cliente.</span><span class="sxs-lookup"><span data-stu-id="88427-150">**Major version** Specifies the number that corresponds to the major release of the client.</span></span>

  - <span data-ttu-id="88427-151">**Versión secundaria** Especifica el número que corresponde a la versión secundaria del cliente.</span><span class="sxs-lookup"><span data-stu-id="88427-151">**Minor version** Specifies the number that corresponds to the minor release of the client.</span></span>

  - <span data-ttu-id="88427-152">**Crear** Especifica el número de compilación que corresponde a la versión principal y secundaria del cliente.</span><span class="sxs-lookup"><span data-stu-id="88427-152">**Build** Specifies the build number that corresponds to the major and minor release of the client.</span></span>

  - <span data-ttu-id="88427-153">**Actualizar** Especifica el número que corresponde a la versión actualizada del cliente.</span><span class="sxs-lookup"><span data-stu-id="88427-153">**Update** Specifies the number that corresponds to the updated release of the client.</span></span>

- <span data-ttu-id="88427-154">**Operación de comparación** Puede especificar la operación correspondiente a la versión del cliente que especificó en los pasos anteriores.</span><span class="sxs-lookup"><span data-stu-id="88427-154">**Comparison operation** You can specify the matching operation for the client version you specified in the preceding steps.</span></span> <span data-ttu-id="88427-155">Las siguientes operaciones están disponibles:</span><span class="sxs-lookup"><span data-stu-id="88427-155">The following operations are available:</span></span>

  - <span data-ttu-id="88427-156">**Igual que**</span><span class="sxs-lookup"><span data-stu-id="88427-156">**Same as**</span></span>

  - <span data-ttu-id="88427-157">**No es**</span><span class="sxs-lookup"><span data-stu-id="88427-157">**Is not**</span></span>

  - <span data-ttu-id="88427-158">**Anterior a**</span><span class="sxs-lookup"><span data-stu-id="88427-158">**Newer than**</span></span>

  - <span data-ttu-id="88427-159">**Anterior a o igual que**</span><span class="sxs-lookup"><span data-stu-id="88427-159">**Newer than or same as**</span></span>

  - <span data-ttu-id="88427-160">**Posterior a**</span><span class="sxs-lookup"><span data-stu-id="88427-160">**Older than**</span></span>

  - <span data-ttu-id="88427-161">**Posterior a o igual que**</span><span class="sxs-lookup"><span data-stu-id="88427-161">**Older than or same as**</span></span>

- <span data-ttu-id="88427-162">**Acción** Puede especificar la acción que se realizará cuando se cumplan los criterios de los pasos anteriores.</span><span class="sxs-lookup"><span data-stu-id="88427-162">**Action** You can specify the action to perform when the criteria in the preceding steps are met.</span></span> <span data-ttu-id="88427-163">Están disponibles las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="88427-163">The following actions are available:</span></span>

  - <span data-ttu-id="88427-164">**Permitir** Permite que el cliente inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="88427-164">**Allow** Allows the client to log on.</span></span>

  - <span data-ttu-id="88427-165">**Permitir y actualizar** Permite al cliente iniciar y recibir actualizaciones de Windows Server Update Services o Microsoft Update.</span><span class="sxs-lookup"><span data-stu-id="88427-165">**Allow and Upgrade** Allows the client to log on and receive updates from Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="88427-166">Esta acción solo está disponible cuando se selecciona **OC** como agente del usuario.</span><span class="sxs-lookup"><span data-stu-id="88427-166">This action is available only when user agent **OC** is selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="88427-167">Si selecciona esta acción, una notificación aparecerá la próxima vez que los usuarios inicien sesión en Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="88427-167">Selecting this action causes a notification to appear the next time users sign in to Skype for Business.</span></span> <span data-ttu-id="88427-168">La notificación comunica que hay una actualización disponible, aun cuando Windows Server Update Service o Microsoft Update todavía no la hayan publicado.</span><span class="sxs-lookup"><span data-stu-id="88427-168">The notification states that an update is available, even if updates have not yet been released to Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="88427-169">Para evitar confusiones, recomendamos elegir esta acción solo cuando las actualizaciones estén disponibles.</span><span class="sxs-lookup"><span data-stu-id="88427-169">To avoid confusion, you should choose this action only after updates become available.</span></span>

  - <span data-ttu-id="88427-170">**Permitir con URL** Permite al cliente iniciar sesión y mostrar un mensaje sobre dónde Descargar otra versión del cliente.</span><span class="sxs-lookup"><span data-stu-id="88427-170">**Allow with URL** Allows the client to log on and displays a message about where to download another client version.</span></span> <span data-ttu-id="88427-171">Puede especificar la dirección URL en el campo **Dirección URL**.</span><span class="sxs-lookup"><span data-stu-id="88427-171">You specify the URL in the **URL** field.</span></span>

  - <span data-ttu-id="88427-172">**Bloquear** Impide que el cliente inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="88427-172">**Block** Prevents the client from logging on.</span></span>

  - <span data-ttu-id="88427-173">**Bloquear y actualizar** Impide que el cliente inicie sesión y permite al cliente recibir actualizaciones de Windows Server Update Services o Microsoft Update.</span><span class="sxs-lookup"><span data-stu-id="88427-173">**Block and Upgrade** Prevents the client from logging on and allows the client to receive updates from Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="88427-174">Esta acción solo está disponible cuando se selecciona **OC** como agente del usuario.</span><span class="sxs-lookup"><span data-stu-id="88427-174">This action is available only when user agent **OC** is selected.</span></span>

  - <span data-ttu-id="88427-p110">**Bloquear con dirección URL** Impide al cliente iniciar sesión y muestra un mensaje que indica dónde descargar otra versión del cliente. Puede especificar la dirección URL en el campo **Dirección URL**.</span><span class="sxs-lookup"><span data-stu-id="88427-p110">**Block with URL** prevents the client from logging on and displays a message about where to download another client version. You specify the URL in the **URL** field.</span></span>

<span data-ttu-id="88427-p111">Para más detalles sobre la interoperabilidad entre clientes y versiones de clientes, mire [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) en la documentación de planeación. Para más detalles sobre cómo trabajar con configuraciones de versiones de clientes, mire [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="88427-p111">For details about interoperability among clients and client versions, see [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation. For details about working with client version configurations, see [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) in the Operations documentation.</span></span>

