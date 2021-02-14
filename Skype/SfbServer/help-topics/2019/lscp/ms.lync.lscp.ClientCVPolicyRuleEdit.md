---
title: Regla de versiones de cliente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientCVPolicyRuleEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 6e7e94c2-1475-4334-b8da-716b24a4c255
ROBOTS: NOINDEX, NOFOLLOW
description: Una directiva de versión de cliente está compuesta de un conjunto de reglas de versión de cliente. Estas reglas definen las acciones que se deben realizar cuando los usuarios intentan iniciar sesión con clientes y versiones de clientes específicos.
ms.openlocfilehash: 26f37c77886ac9f9fe7fb8d8680fb0dad642a9cf
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812380"
---
# <a name="client-version-rule"></a><span data-ttu-id="9dd75-104">Regla de versiones de cliente</span><span class="sxs-lookup"><span data-stu-id="9dd75-104">Client Version Rule</span></span>

<span data-ttu-id="9dd75-p102">Una directiva de versión de cliente está compuesta de un conjunto de reglas de versión de cliente. Estas reglas definen las acciones que se deben realizar cuando los usuarios intentan iniciar sesión con clientes y versiones de clientes específicos.</span><span class="sxs-lookup"><span data-stu-id="9dd75-p102">A client version policy is made up of a set of client version rules. These rules define the actions that should be taken when users attempt to log on with specific clients and client versions.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="9dd75-107">Tareas que puede realizar</span><span class="sxs-lookup"><span data-stu-id="9dd75-107">Tasks you can perform</span></span>

<span data-ttu-id="9dd75-108">Puede realizar las siguientes tareas en la página **Nueva configuración de versión de cliente** o **Editar configuración de versión de cliente**:</span><span class="sxs-lookup"><span data-stu-id="9dd75-108">You can perform the following tasks on the **New Client Version Configuration** or **Edit Client Version Configuration** page:</span></span>

- <span data-ttu-id="9dd75-109">Agregar nuevas reglas a una directiva de versión de cliente.</span><span class="sxs-lookup"><span data-stu-id="9dd75-109">Add new rules to a client version policy.</span></span>

- <span data-ttu-id="9dd75-110">Modificar las reglas que componen una directiva de versión de cliente existente.</span><span class="sxs-lookup"><span data-stu-id="9dd75-110">Modify the rules that make up an existing client version policy</span></span>

## <a name="ui-reference"></a><span data-ttu-id="9dd75-111">Referencia de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="9dd75-111">UI Reference</span></span>

<span data-ttu-id="9dd75-112">Las siguientes listas describen los menús, comandos, campos y propiedades de la página.</span><span class="sxs-lookup"><span data-stu-id="9dd75-112">The following lists describe the menus, command, fields, and properties on the page.</span></span>

- <span data-ttu-id="9dd75-113">**Agente de usuario** Puede seleccionar un tipo de cliente de la lista.</span><span class="sxs-lookup"><span data-stu-id="9dd75-113">**User agent** You can select a client type from the list.</span></span> <span data-ttu-id="9dd75-114">La siguiente tabla define los códigos de agente de usuario.</span><span class="sxs-lookup"><span data-stu-id="9dd75-114">The following table defines user agent codes.</span></span> <span data-ttu-id="9dd75-115">Esta lista incluye tipos de cliente heredados, algunos de los cuales ya no son compatibles.</span><span class="sxs-lookup"><span data-stu-id="9dd75-115">This list includes legacy client types, some of which are no longer supported.</span></span>

|<span data-ttu-id="9dd75-116">**Nombre de cliente**</span><span class="sxs-lookup"><span data-stu-id="9dd75-116">**Client Name**</span></span>|<span data-ttu-id="9dd75-117">**Agente de usuario**</span><span class="sxs-lookup"><span data-stu-id="9dd75-117">**User Agent**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9dd75-118">Lync 2013, Lync 2010, Office Communicator</span><span class="sxs-lookup"><span data-stu-id="9dd75-118">Lync 2013, Lync 2010, Office Communicator</span></span>  <br/> |<span data-ttu-id="9dd75-119">OC</span><span class="sxs-lookup"><span data-stu-id="9dd75-119">OC</span></span>  <br/> |
|<span data-ttu-id="9dd75-120">Lync Web App, Communicator Web Access</span><span class="sxs-lookup"><span data-stu-id="9dd75-120">Lync Web App, Communicator Web Access</span></span>  <br/> |<span data-ttu-id="9dd75-121">CWA</span><span class="sxs-lookup"><span data-stu-id="9dd75-121">CWA</span></span>  <br/> |
|<span data-ttu-id="9dd75-122">Lync Phone Edition, Office Communicator Phone</span><span class="sxs-lookup"><span data-stu-id="9dd75-122">Lync Phone Edition, Office Communicator Phone</span></span>  <br/> |<span data-ttu-id="9dd75-123">OCPhone</span><span class="sxs-lookup"><span data-stu-id="9dd75-123">OCPhone</span></span>  <br/> |
|<span data-ttu-id="9dd75-124">Plataforma Communicator Phone Edition</span><span class="sxs-lookup"><span data-stu-id="9dd75-124">Communicator Phone Edition Platform</span></span>  <br/> |<span data-ttu-id="9dd75-125">CPE</span><span class="sxs-lookup"><span data-stu-id="9dd75-125">CPE</span></span>  <br/> |
|<span data-ttu-id="9dd75-126">Plataforma de comunicaciones unificadas</span><span class="sxs-lookup"><span data-stu-id="9dd75-126">Unified Communications Platform</span></span>  <br/> |<span data-ttu-id="9dd75-127">UCCP</span><span class="sxs-lookup"><span data-stu-id="9dd75-127">UCCP</span></span>  <br/> |
|<span data-ttu-id="9dd75-128">Lync 2010 Attendee</span><span class="sxs-lookup"><span data-stu-id="9dd75-128">Lync 2010 Attendee</span></span>  <br/> |<span data-ttu-id="9dd75-129">AOC</span><span class="sxs-lookup"><span data-stu-id="9dd75-129">AOC</span></span>  <br/> |
|<span data-ttu-id="9dd75-130">Complemento de Live Meeting</span><span class="sxs-lookup"><span data-stu-id="9dd75-130">Live Meeting Add-In</span></span>  <br/> |<span data-ttu-id="9dd75-131">LiveMeetingAddins</span><span class="sxs-lookup"><span data-stu-id="9dd75-131">LiveMeetingAddins</span></span>  <br/> |
|<span data-ttu-id="9dd75-132">Office Live Meeting</span><span class="sxs-lookup"><span data-stu-id="9dd75-132">Office Live Meeting</span></span>  <br/> |<span data-ttu-id="9dd75-133">LMC</span><span class="sxs-lookup"><span data-stu-id="9dd75-133">LMC</span></span>  <br/> |
|<span data-ttu-id="9dd75-134">Windows Messenger</span><span class="sxs-lookup"><span data-stu-id="9dd75-134">Windows Messenger</span></span>  <br/> |<span data-ttu-id="9dd75-135">WM</span><span class="sxs-lookup"><span data-stu-id="9dd75-135">WM</span></span>  <br/> |
|<span data-ttu-id="9dd75-136">Cliente de comunicaciones en tiempo real</span><span class="sxs-lookup"><span data-stu-id="9dd75-136">Real-time Communications Client</span></span>  <br/> |<span data-ttu-id="9dd75-137">RTC</span><span class="sxs-lookup"><span data-stu-id="9dd75-137">RTC</span></span>  <br/> |
|<span data-ttu-id="9dd75-138">Lync 2010 para iPad</span><span class="sxs-lookup"><span data-stu-id="9dd75-138">Lync 2010 for iPad</span></span>  <br/> |<span data-ttu-id="9dd75-139">iPadLync</span><span class="sxs-lookup"><span data-stu-id="9dd75-139">iPadLync</span></span>  <br/> |
|<span data-ttu-id="9dd75-140">Lync 2010 para iPhone</span><span class="sxs-lookup"><span data-stu-id="9dd75-140">Lync 2010 for iPhone</span></span>  <br/> |<span data-ttu-id="9dd75-141">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="9dd75-141">iPhoneLync</span></span>  <br/> |
|<span data-ttu-id="9dd75-142">Lync 2010 para Windows Phone</span><span class="sxs-lookup"><span data-stu-id="9dd75-142">Lync 2010 for Windows Phone</span></span>  <br/> |<span data-ttu-id="9dd75-143">WPLync</span><span class="sxs-lookup"><span data-stu-id="9dd75-143">WPLync</span></span>  <br/> |
|<span data-ttu-id="9dd75-144">Lync 2010 para Nokia</span><span class="sxs-lookup"><span data-stu-id="9dd75-144">Lync 2010 for Nokia</span></span>  <br/> |<span data-ttu-id="9dd75-145">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="9dd75-145">NokiaLync</span></span>  <br/> |
|<span data-ttu-id="9dd75-146">Lync 2010 para Android</span><span class="sxs-lookup"><span data-stu-id="9dd75-146">Lync 2010 for Android</span></span>  <br/> |<span data-ttu-id="9dd75-147">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="9dd75-147">AndroidLync</span></span>  <br/> |
|<span data-ttu-id="9dd75-148">Servicio de movilidad</span><span class="sxs-lookup"><span data-stu-id="9dd75-148">Mobility service</span></span>  <br/> |<span data-ttu-id="9dd75-149">McxService</span><span class="sxs-lookup"><span data-stu-id="9dd75-149">McxService</span></span>  <br/> |

- <span data-ttu-id="9dd75-150">**Número de versión** Puede especificar los números de versión de los siguientes campos o usar caracteres comodín para indicar el número de versión de cliente.</span><span class="sxs-lookup"><span data-stu-id="9dd75-150">**Version number** You can specify the version numbers for the following fields, or use wildcards to indicate the client version number.</span></span>

  - <span data-ttu-id="9dd75-151">**Versión principal** Especifica el número que corresponde a la versión principal del cliente.</span><span class="sxs-lookup"><span data-stu-id="9dd75-151">**Major version** Specifies the number that corresponds to the major release of the client.</span></span>

  - <span data-ttu-id="9dd75-152">**Versión secundaria** Especifica el número que corresponde a la versión secundaria del cliente.</span><span class="sxs-lookup"><span data-stu-id="9dd75-152">**Minor version** Specifies the number that corresponds to the minor release of the client.</span></span>

  - <span data-ttu-id="9dd75-153">**Compilación** Especifica el número de compilación que corresponde a la versión principal y secundaria del cliente.</span><span class="sxs-lookup"><span data-stu-id="9dd75-153">**Build** Specifies the build number that corresponds to the major and minor release of the client.</span></span>

  - <span data-ttu-id="9dd75-154">**Actualizar** Especifica el número que corresponde a la versión actualizada del cliente.</span><span class="sxs-lookup"><span data-stu-id="9dd75-154">**Update** Specifies the number that corresponds to the updated release of the client.</span></span>

- <span data-ttu-id="9dd75-155">**Operación de comparación** Puede especificar la operación de coincidencia para la versión de cliente que especificó en los pasos anteriores.</span><span class="sxs-lookup"><span data-stu-id="9dd75-155">**Comparison operation** You can specify the matching operation for the client version you specified in the preceding steps.</span></span> <span data-ttu-id="9dd75-156">Las siguientes operaciones están disponibles:</span><span class="sxs-lookup"><span data-stu-id="9dd75-156">The following operations are available:</span></span>

  - <span data-ttu-id="9dd75-157">**Igual que**</span><span class="sxs-lookup"><span data-stu-id="9dd75-157">**Same as**</span></span>

  - <span data-ttu-id="9dd75-158">**No es**</span><span class="sxs-lookup"><span data-stu-id="9dd75-158">**Is not**</span></span>

  - <span data-ttu-id="9dd75-159">**Anterior a**</span><span class="sxs-lookup"><span data-stu-id="9dd75-159">**Newer than**</span></span>

  - <span data-ttu-id="9dd75-160">**Anterior a o igual que**</span><span class="sxs-lookup"><span data-stu-id="9dd75-160">**Newer than or same as**</span></span>

  - <span data-ttu-id="9dd75-161">**Posterior a**</span><span class="sxs-lookup"><span data-stu-id="9dd75-161">**Older than**</span></span>

  - <span data-ttu-id="9dd75-162">**Posterior a o igual que**</span><span class="sxs-lookup"><span data-stu-id="9dd75-162">**Older than or same as**</span></span>

- <span data-ttu-id="9dd75-163">**Acción** Puede especificar la acción que se realizará cuando se cumplan los criterios de los pasos anteriores.</span><span class="sxs-lookup"><span data-stu-id="9dd75-163">**Action** You can specify the action to perform when the criteria in the preceding steps are met.</span></span> <span data-ttu-id="9dd75-164">Están disponibles las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="9dd75-164">The following actions are available:</span></span>

  - <span data-ttu-id="9dd75-165">**Permitir** Permite que el cliente inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="9dd75-165">**Allow** Allows the client to log on.</span></span>

  - <span data-ttu-id="9dd75-166">**Permitir y actualizar** Permite al cliente iniciar sesión y recibir actualizaciones de Windows Server Update Service o Microsoft Update.</span><span class="sxs-lookup"><span data-stu-id="9dd75-166">**Allow and Upgrade** Allows the client to log on and receive updates from Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="9dd75-167">Esta acción solo está disponible cuando se selecciona **OC** del agente del usuario.</span><span class="sxs-lookup"><span data-stu-id="9dd75-167">This action is available only when user agent **OC** is selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9dd75-168">Si selecciona esta acción, aparecerá una notificación la próxima vez que los usuarios inicien sesión en Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="9dd75-168">Selecting this action causes a notification to appear the next time users sign in to Skype for Business.</span></span> <span data-ttu-id="9dd75-169">La notificación comunica que hay una actualización disponible, aunque las actualizaciones aún no se hayan publicado en Windows Server Update Service o en Microsoft Update.</span><span class="sxs-lookup"><span data-stu-id="9dd75-169">The notification states that an update is available, even if updates have not yet been released to Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="9dd75-170">Para evitar confusiones, se recomienda elegir esta acción solo después de que haya actualizaciones disponibles.</span><span class="sxs-lookup"><span data-stu-id="9dd75-170">To avoid confusion, you should choose this action only after updates become available.</span></span>

  - <span data-ttu-id="9dd75-171">**Permitir con dirección URL** Permite al cliente iniciar sesión y muestra un mensaje sobre dónde descargar otra versión de cliente.</span><span class="sxs-lookup"><span data-stu-id="9dd75-171">**Allow with URL** Allows the client to log on and displays a message about where to download another client version.</span></span> <span data-ttu-id="9dd75-172">Puede especificar la dirección URL en el campo **Dirección URL**.</span><span class="sxs-lookup"><span data-stu-id="9dd75-172">You specify the URL in the **URL** field.</span></span>

  - <span data-ttu-id="9dd75-173">**Bloquear** Impide que el cliente inicia sesión.</span><span class="sxs-lookup"><span data-stu-id="9dd75-173">**Block** Prevents the client from logging on.</span></span>

  - <span data-ttu-id="9dd75-174">**Bloquear y actualizar** Impide que el cliente inicia sesión y permite que el cliente reciba actualizaciones de Windows Server Update Service o Microsoft Update.</span><span class="sxs-lookup"><span data-stu-id="9dd75-174">**Block and Upgrade** Prevents the client from logging on and allows the client to receive updates from Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="9dd75-175">Esta acción solo está disponible cuando se selecciona **OC** del agente del usuario.</span><span class="sxs-lookup"><span data-stu-id="9dd75-175">This action is available only when user agent **OC** is selected.</span></span>

  - <span data-ttu-id="9dd75-p110">**Bloquear con dirección URL**   Impide al cliente iniciar sesión y muestra un mensaje sobre dónde descargar otra versión del cliente. Puede especificar la dirección URL en el campo **Dirección URL**.</span><span class="sxs-lookup"><span data-stu-id="9dd75-p110">**Block with URL** prevents the client from logging on and displays a message about where to download another client version. You specify the URL in the **URL** field.</span></span>

<span data-ttu-id="9dd75-178">Para obtener más información sobre la interoperabilidad entre clientes y versiones de cliente, consulte [Interoperabilidad de](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) clientes en la documentación sobre planeación.</span><span class="sxs-lookup"><span data-stu-id="9dd75-178">For details about interoperability among clients and client versions, see [Client Interoperability](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation.</span></span> <span data-ttu-id="9dd75-179">Para obtener detalles sobre cómo trabajar con configuraciones de versiones de clientes, vea [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="9dd75-179">For details about working with client version configurations, see [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) in the Operations documentation.</span></span>

