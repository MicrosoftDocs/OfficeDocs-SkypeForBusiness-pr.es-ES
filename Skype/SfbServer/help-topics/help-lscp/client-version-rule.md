---
title: Regla de versiones de cliente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Una directiva de versión de cliente está compuesta de un conjunto de reglas de versión de cliente. Estas reglas definen las acciones que se deben realizar cuando los usuarios intentan iniciar sesión con clientes y versiones de clientes específicos.
ms.openlocfilehash: 4c46a93e46e1e07865a466a666a450a766c6897e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103456"
---
# <a name="client-version-rule"></a><span data-ttu-id="5c811-104">Regla de versiones de cliente</span><span class="sxs-lookup"><span data-stu-id="5c811-104">Client Version Rule</span></span>

<span data-ttu-id="5c811-p102">Una directiva de versión de cliente está compuesta de un conjunto de reglas de versión de cliente. Estas reglas definen las acciones que se deben realizar cuando los usuarios intentan iniciar sesión con clientes y versiones de clientes específicos.</span><span class="sxs-lookup"><span data-stu-id="5c811-p102">A client version policy is made up of a set of client version rules. These rules define the actions that should be taken when users attempt to log on with specific clients and client versions.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="5c811-107">Tareas que puede realizar</span><span class="sxs-lookup"><span data-stu-id="5c811-107">Tasks you can perform</span></span>

<span data-ttu-id="5c811-108">Puede realizar las siguientes tareas en la página **Nueva configuración de versión de cliente** o **Editar configuración de versión de cliente**:</span><span class="sxs-lookup"><span data-stu-id="5c811-108">You can perform the following tasks on the **New Client Version Configuration** or **Edit Client Version Configuration** page:</span></span>

- <span data-ttu-id="5c811-109">Agregar nuevas reglas a una directiva de versión de cliente.</span><span class="sxs-lookup"><span data-stu-id="5c811-109">Add new rules to a client version policy.</span></span>

- <span data-ttu-id="5c811-110">Modificar las reglas que componen una directiva de versión de cliente existente.</span><span class="sxs-lookup"><span data-stu-id="5c811-110">Modify the rules that make up an existing client version policy</span></span>

## <a name="ui-reference"></a><span data-ttu-id="5c811-111">Referencia de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="5c811-111">UI Reference</span></span>

<span data-ttu-id="5c811-112">Las siguientes listas describen los menús, comandos, campos y propiedades de la página.</span><span class="sxs-lookup"><span data-stu-id="5c811-112">The following lists describe the menus, command, fields, and properties on the page.</span></span>

- <span data-ttu-id="5c811-113">**Agente de usuario** Puede seleccionar un tipo de cliente de la lista.</span><span class="sxs-lookup"><span data-stu-id="5c811-113">**User agent** You can select a client type from the list.</span></span> <span data-ttu-id="5c811-114">La siguiente tabla define los códigos de agente de usuario.</span><span class="sxs-lookup"><span data-stu-id="5c811-114">The following table defines user agent codes.</span></span>

|<span data-ttu-id="5c811-115">**Nombre de cliente**</span><span class="sxs-lookup"><span data-stu-id="5c811-115">**Client Name**</span></span>|<span data-ttu-id="5c811-116">**Agente de usuario**</span><span class="sxs-lookup"><span data-stu-id="5c811-116">**User Agent**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5c811-117">Lync 2013, Lync 2010, Office Communicator</span><span class="sxs-lookup"><span data-stu-id="5c811-117">Lync 2013, Lync 2010, Office Communicator</span></span>  <br/> |<span data-ttu-id="5c811-118">OC</span><span class="sxs-lookup"><span data-stu-id="5c811-118">OC</span></span>  <br/> |
|<span data-ttu-id="5c811-119">Lync Web App, Communicator Web Access</span><span class="sxs-lookup"><span data-stu-id="5c811-119">Lync Web App, Communicator Web Access</span></span>  <br/> |<span data-ttu-id="5c811-120">CWA</span><span class="sxs-lookup"><span data-stu-id="5c811-120">CWA</span></span>  <br/> |
|<span data-ttu-id="5c811-121">Lync Phone Edition, Office Communicator Phone</span><span class="sxs-lookup"><span data-stu-id="5c811-121">Lync Phone Edition, Office Communicator Phone</span></span>  <br/> |<span data-ttu-id="5c811-122">OCPhone</span><span class="sxs-lookup"><span data-stu-id="5c811-122">OCPhone</span></span>  <br/> |
|<span data-ttu-id="5c811-123">Plataforma Communicator Phone Edition</span><span class="sxs-lookup"><span data-stu-id="5c811-123">Communicator Phone Edition Platform</span></span>  <br/> |<span data-ttu-id="5c811-124">CPE</span><span class="sxs-lookup"><span data-stu-id="5c811-124">CPE</span></span>  <br/> |
|<span data-ttu-id="5c811-125">Plataforma de comunicaciones unificadas</span><span class="sxs-lookup"><span data-stu-id="5c811-125">Unified Communications Platform</span></span>  <br/> |<span data-ttu-id="5c811-126">UCCP</span><span class="sxs-lookup"><span data-stu-id="5c811-126">UCCP</span></span>  <br/> |
|<span data-ttu-id="5c811-127">Lync 2010 Attendee</span><span class="sxs-lookup"><span data-stu-id="5c811-127">Lync 2010 Attendee</span></span>  <br/> |<span data-ttu-id="5c811-128">AOC</span><span class="sxs-lookup"><span data-stu-id="5c811-128">AOC</span></span>  <br/> |
|<span data-ttu-id="5c811-129">Complemento de Live Meeting</span><span class="sxs-lookup"><span data-stu-id="5c811-129">Live Meeting Add-In</span></span>  <br/> |<span data-ttu-id="5c811-130">LiveMeetingAddins</span><span class="sxs-lookup"><span data-stu-id="5c811-130">LiveMeetingAddins</span></span>  <br/> |
|<span data-ttu-id="5c811-131">Office Live Meeting</span><span class="sxs-lookup"><span data-stu-id="5c811-131">Office Live Meeting</span></span>  <br/> |<span data-ttu-id="5c811-132">LMC</span><span class="sxs-lookup"><span data-stu-id="5c811-132">LMC</span></span>  <br/> |
|<span data-ttu-id="5c811-133">Windows Messenger</span><span class="sxs-lookup"><span data-stu-id="5c811-133">Windows Messenger</span></span>  <br/> |<span data-ttu-id="5c811-134">WM</span><span class="sxs-lookup"><span data-stu-id="5c811-134">WM</span></span>  <br/> |
|<span data-ttu-id="5c811-135">Cliente de comunicaciones en tiempo real</span><span class="sxs-lookup"><span data-stu-id="5c811-135">Real-time Communications Client</span></span>  <br/> |<span data-ttu-id="5c811-136">RTC</span><span class="sxs-lookup"><span data-stu-id="5c811-136">RTC</span></span>  <br/> |
|<span data-ttu-id="5c811-137">Lync 2010 para iPad</span><span class="sxs-lookup"><span data-stu-id="5c811-137">Lync 2010 for iPad</span></span>  <br/> |<span data-ttu-id="5c811-138">iPadLync</span><span class="sxs-lookup"><span data-stu-id="5c811-138">iPadLync</span></span>  <br/> |
|<span data-ttu-id="5c811-139">Lync 2010 para iPhone</span><span class="sxs-lookup"><span data-stu-id="5c811-139">Lync 2010 for iPhone</span></span>  <br/> |<span data-ttu-id="5c811-140">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="5c811-140">iPhoneLync</span></span>  <br/> |
|<span data-ttu-id="5c811-141">Lync 2010 para Windows Phone</span><span class="sxs-lookup"><span data-stu-id="5c811-141">Lync 2010 for Windows Phone</span></span>  <br/> |<span data-ttu-id="5c811-142">WPLync</span><span class="sxs-lookup"><span data-stu-id="5c811-142">WPLync</span></span>  <br/> |
|<span data-ttu-id="5c811-143">Lync 2010 para Nokia</span><span class="sxs-lookup"><span data-stu-id="5c811-143">Lync 2010 for Nokia</span></span>  <br/> |<span data-ttu-id="5c811-144">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="5c811-144">NokiaLync</span></span>  <br/> |
|<span data-ttu-id="5c811-145">Lync 2010 para Android</span><span class="sxs-lookup"><span data-stu-id="5c811-145">Lync 2010 for Android</span></span>  <br/> |<span data-ttu-id="5c811-146">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="5c811-146">AndroidLync</span></span>  <br/> |
|<span data-ttu-id="5c811-147">Servicio de movilidad</span><span class="sxs-lookup"><span data-stu-id="5c811-147">Mobility service</span></span>  <br/> |<span data-ttu-id="5c811-148">McxService</span><span class="sxs-lookup"><span data-stu-id="5c811-148">McxService</span></span>  <br/> |

- <span data-ttu-id="5c811-149">**Número de versión** Puede especificar los números de versión de los campos siguientes o usar caracteres comodín para indicar el número de versión del cliente.</span><span class="sxs-lookup"><span data-stu-id="5c811-149">**Version number** You can specify the version numbers for the following fields, or use wildcards to indicate the client version number.</span></span>

  - <span data-ttu-id="5c811-150">**Versión principal** Especifica el número que corresponde a la versión principal del cliente.</span><span class="sxs-lookup"><span data-stu-id="5c811-150">**Major version** Specifies the number that corresponds to the major release of the client.</span></span>

  - <span data-ttu-id="5c811-151">**Versión secundaria** Especifica el número que corresponde a la versión secundaria del cliente.</span><span class="sxs-lookup"><span data-stu-id="5c811-151">**Minor version** Specifies the number that corresponds to the minor release of the client.</span></span>

  - <span data-ttu-id="5c811-152">**Compilación** Especifica el número de compilación que corresponde a la versión principal y secundaria del cliente.</span><span class="sxs-lookup"><span data-stu-id="5c811-152">**Build** Specifies the build number that corresponds to the major and minor release of the client.</span></span>

  - <span data-ttu-id="5c811-153">**Actualizar** Especifica el número que corresponde a la versión actualizada del cliente.</span><span class="sxs-lookup"><span data-stu-id="5c811-153">**Update** Specifies the number that corresponds to the updated release of the client.</span></span>

- <span data-ttu-id="5c811-154">**Operación de comparación** Puede especificar la operación de coincidencia para la versión de cliente especificada en los pasos anteriores.</span><span class="sxs-lookup"><span data-stu-id="5c811-154">**Comparison operation** You can specify the matching operation for the client version you specified in the preceding steps.</span></span> <span data-ttu-id="5c811-155">Las siguientes operaciones están disponibles:</span><span class="sxs-lookup"><span data-stu-id="5c811-155">The following operations are available:</span></span>

  - <span data-ttu-id="5c811-156">**Igual que**</span><span class="sxs-lookup"><span data-stu-id="5c811-156">**Same as**</span></span>

  - <span data-ttu-id="5c811-157">**No es**</span><span class="sxs-lookup"><span data-stu-id="5c811-157">**Is not**</span></span>

  - <span data-ttu-id="5c811-158">**Anterior a**</span><span class="sxs-lookup"><span data-stu-id="5c811-158">**Newer than**</span></span>

  - <span data-ttu-id="5c811-159">**Anterior a o igual que**</span><span class="sxs-lookup"><span data-stu-id="5c811-159">**Newer than or same as**</span></span>

  - <span data-ttu-id="5c811-160">**Posterior a**</span><span class="sxs-lookup"><span data-stu-id="5c811-160">**Older than**</span></span>

  - <span data-ttu-id="5c811-161">**Posterior a o igual que**</span><span class="sxs-lookup"><span data-stu-id="5c811-161">**Older than or same as**</span></span>

- <span data-ttu-id="5c811-162">**Acción** Puede especificar la acción que se debe realizar cuando se cumplan los criterios de los pasos anteriores.</span><span class="sxs-lookup"><span data-stu-id="5c811-162">**Action** You can specify the action to perform when the criteria in the preceding steps are met.</span></span> <span data-ttu-id="5c811-163">Están disponibles las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="5c811-163">The following actions are available:</span></span>

  - <span data-ttu-id="5c811-164">**Permitir** Permite que el cliente inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="5c811-164">**Allow** Allows the client to log on.</span></span>

  - <span data-ttu-id="5c811-165">**Permitir y actualizar** Permite al cliente iniciar sesión y recibir actualizaciones de Windows Server Update Service o Microsoft Update.</span><span class="sxs-lookup"><span data-stu-id="5c811-165">**Allow and Upgrade** Allows the client to log on and receive updates from Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="5c811-166">Esta acción solo está disponible cuando se selecciona **OC** del agente del usuario.</span><span class="sxs-lookup"><span data-stu-id="5c811-166">This action is available only when user agent **OC** is selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5c811-167">Al seleccionar esta acción, aparecerá una notificación la próxima vez que los usuarios inicien sesión en Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="5c811-167">Selecting this action causes a notification to appear the next time users sign in to Skype for Business.</span></span> <span data-ttu-id="5c811-168">La notificación comunica que hay una actualización disponible, aunque las actualizaciones aún no se hayan publicado en Windows Server Update Service o en Microsoft Update.</span><span class="sxs-lookup"><span data-stu-id="5c811-168">The notification states that an update is available, even if updates have not yet been released to Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="5c811-169">Para evitar confusiones, se recomienda elegir esta acción solo después de que haya actualizaciones disponibles.</span><span class="sxs-lookup"><span data-stu-id="5c811-169">To avoid confusion, you should choose this action only after updates become available.</span></span>

  - <span data-ttu-id="5c811-170">**Permitir con dirección URL** Permite al cliente iniciar sesión y muestra un mensaje sobre dónde descargar otra versión de cliente.</span><span class="sxs-lookup"><span data-stu-id="5c811-170">**Allow with URL** Allows the client to log on and displays a message about where to download another client version.</span></span> <span data-ttu-id="5c811-171">Puede especificar la dirección URL en el campo **Dirección URL**.</span><span class="sxs-lookup"><span data-stu-id="5c811-171">You specify the URL in the **URL** field.</span></span>

  - <span data-ttu-id="5c811-172">**Bloquear** Impide que el cliente inicia sesión.</span><span class="sxs-lookup"><span data-stu-id="5c811-172">**Block** Prevents the client from logging on.</span></span>

  - <span data-ttu-id="5c811-173">**Bloquear y actualizar** Impide que el cliente se inicia sesión y permite que el cliente reciba actualizaciones del Servicio windows Server Update o Microsoft Update.</span><span class="sxs-lookup"><span data-stu-id="5c811-173">**Block and Upgrade** Prevents the client from logging on and allows the client to receive updates from Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="5c811-174">Esta acción solo está disponible cuando se selecciona **OC** del agente del usuario.</span><span class="sxs-lookup"><span data-stu-id="5c811-174">This action is available only when user agent **OC** is selected.</span></span>

  - <span data-ttu-id="5c811-p110">**Bloquear con dirección URL**   Impide al cliente iniciar sesión y muestra un mensaje sobre dónde descargar otra versión del cliente. Puede especificar la dirección URL en el campo **Dirección URL**.</span><span class="sxs-lookup"><span data-stu-id="5c811-p110">**Block with URL** prevents the client from logging on and displays a message about where to download another client version. You specify the URL in the **URL** field.</span></span>

<span data-ttu-id="5c811-177">Para obtener detalles sobre la interoperabilidad entre clientes y versiones de clientes, vea [Client Interoperability in Lync 2013 Preview](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="5c811-177">For details about interoperability among clients and client versions, see [Client Interoperability in Lync 2013 Preview](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013) in the Planning documentation.</span></span> <span data-ttu-id="5c811-178">Para obtener detalles sobre cómo trabajar con configuraciones de versiones de clientes, vea [Modify the Default Action for Clients Not Explicitly Supported or Restricted](/previous-versions/office/lync-server-2013/lync-server-2013-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted) en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="5c811-178">For details about working with client version configurations, see [Modify the Default Action for Clients Not Explicitly Supported or Restricted](/previous-versions/office/lync-server-2013/lync-server-2013-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted) in the Operations documentation.</span></span>