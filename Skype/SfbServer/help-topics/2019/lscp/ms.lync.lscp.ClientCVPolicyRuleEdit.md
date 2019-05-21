---
title: Regla de versiones de cliente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVPolicyRuleEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6e7e94c2-1475-4334-b8da-716b24a4c255
ROBOTS: NOINDEX, NOFOLLOW
description: Una directiva de versión de cliente está compuesta de un conjunto de reglas de versión de cliente. Estas reglas definen las acciones que se necesitan realizar cuando los usuarios intentan iniciar sesión con clientes y versiones de clientes específicos.
ms.openlocfilehash: ab67f926f7a2e0ddc91f33bc9657d8fd4104e3a0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34300527"
---
# <a name="client-version-rule"></a><span data-ttu-id="23d86-104">Regla de versiones de cliente</span><span class="sxs-lookup"><span data-stu-id="23d86-104">Client Version Rule</span></span>

<span data-ttu-id="23d86-p102">Una directiva de versión de cliente está compuesta de un conjunto de reglas de versión de cliente. Estas reglas definen las acciones que se necesitan realizar cuando los usuarios intentan iniciar sesión con clientes y versiones de clientes específicos.</span><span class="sxs-lookup"><span data-stu-id="23d86-p102">A client version policy is made up of a set of client version rules. These rules define the actions that should be taken when users attempt to log on with specific clients and client versions.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="23d86-107">Tareas que puede realizar</span><span class="sxs-lookup"><span data-stu-id="23d86-107">Tasks you can perform</span></span>

<span data-ttu-id="23d86-108">En las páginas **Nueva configuración de versión de cliente** o **Editar configuración de versión de cliente** puede realizar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="23d86-108">You can perform the following tasks on the **New Client Version Configuration** or **Edit Client Version Configuration** page:</span></span>

- <span data-ttu-id="23d86-109">Agregar nuevas reglas a una directiva de versión de cliente.</span><span class="sxs-lookup"><span data-stu-id="23d86-109">Add new rules to a client version policy.</span></span>

- <span data-ttu-id="23d86-110">Modificar las reglas que componen una directiva de versión de cliente existente.</span><span class="sxs-lookup"><span data-stu-id="23d86-110">Modify the rules that make up an existing client version policy</span></span>

## <a name="ui-reference"></a><span data-ttu-id="23d86-111">Referencia de interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="23d86-111">UI Reference</span></span>

<span data-ttu-id="23d86-112">En las siguientes listas se describen los menús, comandos, campos y propiedades de la página.</span><span class="sxs-lookup"><span data-stu-id="23d86-112">The following lists describe the menus, command, fields, and properties on the page.</span></span>

- <span data-ttu-id="23d86-113">**Agente de usuario** Puede seleccionar un tipo de cliente de la lista.</span><span class="sxs-lookup"><span data-stu-id="23d86-113">**User agent** You can select a client type from the list.</span></span> <span data-ttu-id="23d86-114">En la siguiente tabla se recogen los códigos de agente de usuario.</span><span class="sxs-lookup"><span data-stu-id="23d86-114">The following table defines user agent codes.</span></span> <span data-ttu-id="23d86-115">Esta lista incluye tipos de clientes heredados, algunos de los cuales ya no se admiten.</span><span class="sxs-lookup"><span data-stu-id="23d86-115">This list includes legacy client types, some of which are no longer supported.</span></span>

|<span data-ttu-id="23d86-116">**Nombre de cliente**</span><span class="sxs-lookup"><span data-stu-id="23d86-116">**Client Name**</span></span>|<span data-ttu-id="23d86-117">**Agente de usuario**</span><span class="sxs-lookup"><span data-stu-id="23d86-117">**User Agent**</span></span>|
|:-----|:-----|
|<span data-ttu-id="23d86-118">Lync 2013, Lync 2010, Office Communicator</span><span class="sxs-lookup"><span data-stu-id="23d86-118">Lync 2013, Lync 2010, Office Communicator</span></span>  <br/> |<span data-ttu-id="23d86-119">OC</span><span class="sxs-lookup"><span data-stu-id="23d86-119">OC</span></span>  <br/> |
|<span data-ttu-id="23d86-120">Lync Web App, Communicator Web Access</span><span class="sxs-lookup"><span data-stu-id="23d86-120">Lync Web App, Communicator Web Access</span></span>  <br/> |<span data-ttu-id="23d86-121">CWA</span><span class="sxs-lookup"><span data-stu-id="23d86-121">CWA</span></span>  <br/> |
|<span data-ttu-id="23d86-122">Lync Phone Edition, teléfono de Office Communicator</span><span class="sxs-lookup"><span data-stu-id="23d86-122">Lync Phone Edition, Office Communicator Phone</span></span>  <br/> |<span data-ttu-id="23d86-123">OCPhone</span><span class="sxs-lookup"><span data-stu-id="23d86-123">OCPhone</span></span>  <br/> |
|<span data-ttu-id="23d86-124">Plataforma Communicator Phone Edition</span><span class="sxs-lookup"><span data-stu-id="23d86-124">Communicator Phone Edition Platform</span></span>  <br/> |<span data-ttu-id="23d86-125">CPE</span><span class="sxs-lookup"><span data-stu-id="23d86-125">CPE</span></span>  <br/> |
|<span data-ttu-id="23d86-126">Plataforma de comunicaciones unificadas</span><span class="sxs-lookup"><span data-stu-id="23d86-126">Unified Communications Platform</span></span>  <br/> |<span data-ttu-id="23d86-127">UCCP</span><span class="sxs-lookup"><span data-stu-id="23d86-127">UCCP</span></span>  <br/> |
|<span data-ttu-id="23d86-128">Lync 2010 Attendee</span><span class="sxs-lookup"><span data-stu-id="23d86-128">Lync 2010 Attendee</span></span>  <br/> |<span data-ttu-id="23d86-129">AOC</span><span class="sxs-lookup"><span data-stu-id="23d86-129">AOC</span></span>  <br/> |
|<span data-ttu-id="23d86-130">Complemento de Live Meeting</span><span class="sxs-lookup"><span data-stu-id="23d86-130">Live Meeting Add-In</span></span>  <br/> |<span data-ttu-id="23d86-131">LiveMeetingAddins</span><span class="sxs-lookup"><span data-stu-id="23d86-131">LiveMeetingAddins</span></span>  <br/> |
|<span data-ttu-id="23d86-132">Office Live Meeting</span><span class="sxs-lookup"><span data-stu-id="23d86-132">Office Live Meeting</span></span>  <br/> |<span data-ttu-id="23d86-133">LMC</span><span class="sxs-lookup"><span data-stu-id="23d86-133">LMC</span></span>  <br/> |
|<span data-ttu-id="23d86-134">Windows Messenger</span><span class="sxs-lookup"><span data-stu-id="23d86-134">Windows Messenger</span></span>  <br/> |<span data-ttu-id="23d86-135">WM</span><span class="sxs-lookup"><span data-stu-id="23d86-135">WM</span></span>  <br/> |
|<span data-ttu-id="23d86-136">Cliente de comunicaciones en tiempo real</span><span class="sxs-lookup"><span data-stu-id="23d86-136">Real-time Communications Client</span></span>  <br/> |<span data-ttu-id="23d86-137">RTC</span><span class="sxs-lookup"><span data-stu-id="23d86-137">RTC</span></span>  <br/> |
|<span data-ttu-id="23d86-138">Lync 2010 para iPad</span><span class="sxs-lookup"><span data-stu-id="23d86-138">Lync 2010 for iPad</span></span>  <br/> |<span data-ttu-id="23d86-139">iPadLync</span><span class="sxs-lookup"><span data-stu-id="23d86-139">iPadLync</span></span>  <br/> |
|<span data-ttu-id="23d86-140">Lync 2010 para iPhone</span><span class="sxs-lookup"><span data-stu-id="23d86-140">Lync 2010 for iPhone</span></span>  <br/> |<span data-ttu-id="23d86-141">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="23d86-141">iPhoneLync</span></span>  <br/> |
|<span data-ttu-id="23d86-142">Lync 2010 para Windows Phone</span><span class="sxs-lookup"><span data-stu-id="23d86-142">Lync 2010 for Windows Phone</span></span>  <br/> |<span data-ttu-id="23d86-143">WPLync</span><span class="sxs-lookup"><span data-stu-id="23d86-143">WPLync</span></span>  <br/> |
|<span data-ttu-id="23d86-144">Lync 2010 para Nokia</span><span class="sxs-lookup"><span data-stu-id="23d86-144">Lync 2010 for Nokia</span></span>  <br/> |<span data-ttu-id="23d86-145">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="23d86-145">NokiaLync</span></span>  <br/> |
|<span data-ttu-id="23d86-146">Lync 2010 para Android</span><span class="sxs-lookup"><span data-stu-id="23d86-146">Lync 2010 for Android</span></span>  <br/> |<span data-ttu-id="23d86-147">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="23d86-147">AndroidLync</span></span>  <br/> |
|<span data-ttu-id="23d86-148">Servicio de movilidad</span><span class="sxs-lookup"><span data-stu-id="23d86-148">Mobility service</span></span>  <br/> |<span data-ttu-id="23d86-149">McxService</span><span class="sxs-lookup"><span data-stu-id="23d86-149">McxService</span></span>  <br/> |

- <span data-ttu-id="23d86-150">**Número de versión** Puede especificar los números de versión de los siguientes campos, o usar caracteres comodín para indicar el número de versión del cliente.</span><span class="sxs-lookup"><span data-stu-id="23d86-150">**Version number** You can specify the version numbers for the following fields, or use wildcards to indicate the client version number.</span></span>

  - <span data-ttu-id="23d86-151">**Versión principal** Especifica el número que corresponde a la versión principal del cliente.</span><span class="sxs-lookup"><span data-stu-id="23d86-151">**Major version** Specifies the number that corresponds to the major release of the client.</span></span>

  - <span data-ttu-id="23d86-152">**Versión secundaria** Especifica el número que corresponde a la versión secundaria del cliente.</span><span class="sxs-lookup"><span data-stu-id="23d86-152">**Minor version** Specifies the number that corresponds to the minor release of the client.</span></span>

  - <span data-ttu-id="23d86-153">**Crear** Especifica el número de compilación que corresponde a la versión principal y secundaria del cliente.</span><span class="sxs-lookup"><span data-stu-id="23d86-153">**Build** Specifies the build number that corresponds to the major and minor release of the client.</span></span>

  - <span data-ttu-id="23d86-154">**Actualizar** Especifica el número que corresponde a la versión actualizada del cliente.</span><span class="sxs-lookup"><span data-stu-id="23d86-154">**Update** Specifies the number that corresponds to the updated release of the client.</span></span>

- <span data-ttu-id="23d86-155">**Operación de comparación** Puede especificar la operación correspondiente a la versión del cliente que especificó en los pasos anteriores.</span><span class="sxs-lookup"><span data-stu-id="23d86-155">**Comparison operation** You can specify the matching operation for the client version you specified in the preceding steps.</span></span> <span data-ttu-id="23d86-156">Las siguientes operaciones están disponibles:</span><span class="sxs-lookup"><span data-stu-id="23d86-156">The following operations are available:</span></span>

  - <span data-ttu-id="23d86-157">**Igual que**</span><span class="sxs-lookup"><span data-stu-id="23d86-157">**Same as**</span></span>

  - <span data-ttu-id="23d86-158">**No es**</span><span class="sxs-lookup"><span data-stu-id="23d86-158">**Is not**</span></span>

  - <span data-ttu-id="23d86-159">**Anterior a**</span><span class="sxs-lookup"><span data-stu-id="23d86-159">**Newer than**</span></span>

  - <span data-ttu-id="23d86-160">**Anterior a o igual que**</span><span class="sxs-lookup"><span data-stu-id="23d86-160">**Newer than or same as**</span></span>

  - <span data-ttu-id="23d86-161">**Posterior a**</span><span class="sxs-lookup"><span data-stu-id="23d86-161">**Older than**</span></span>

  - <span data-ttu-id="23d86-162">**Posterior a o igual que**</span><span class="sxs-lookup"><span data-stu-id="23d86-162">**Older than or same as**</span></span>

- <span data-ttu-id="23d86-163">**Acción** Puede especificar la acción que se realizará cuando se cumplan los criterios de los pasos anteriores.</span><span class="sxs-lookup"><span data-stu-id="23d86-163">**Action** You can specify the action to perform when the criteria in the preceding steps are met.</span></span> <span data-ttu-id="23d86-164">Están disponibles las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="23d86-164">The following actions are available:</span></span>

  - <span data-ttu-id="23d86-165">**Permitir** Permite que el cliente inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="23d86-165">**Allow** Allows the client to log on.</span></span>

  - <span data-ttu-id="23d86-166">**Permitir y actualizar** Permite al cliente iniciar y recibir actualizaciones de Windows Server Update Services o Microsoft Update.</span><span class="sxs-lookup"><span data-stu-id="23d86-166">**Allow and Upgrade** Allows the client to log on and receive updates from Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="23d86-167">Esta acción solo está disponible cuando se selecciona **OC** como agente del usuario.</span><span class="sxs-lookup"><span data-stu-id="23d86-167">This action is available only when user agent **OC** is selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="23d86-168">Si selecciona esta acción, una notificación aparecerá la próxima vez que los usuarios inicien sesión en Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="23d86-168">Selecting this action causes a notification to appear the next time users sign in to Skype for Business.</span></span> <span data-ttu-id="23d86-169">La notificación comunica que hay una actualización disponible, aun cuando Windows Server Update Service o Microsoft Update todavía no la hayan publicado.</span><span class="sxs-lookup"><span data-stu-id="23d86-169">The notification states that an update is available, even if updates have not yet been released to Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="23d86-170">Para evitar confusiones, recomendamos elegir esta acción solo cuando las actualizaciones estén disponibles.</span><span class="sxs-lookup"><span data-stu-id="23d86-170">To avoid confusion, you should choose this action only after updates become available.</span></span>

  - <span data-ttu-id="23d86-171">**Permitir con URL** Permite al cliente iniciar sesión y mostrar un mensaje sobre dónde Descargar otra versión del cliente.</span><span class="sxs-lookup"><span data-stu-id="23d86-171">**Allow with URL** Allows the client to log on and displays a message about where to download another client version.</span></span> <span data-ttu-id="23d86-172">Puede especificar la dirección URL en el campo **Dirección URL**.</span><span class="sxs-lookup"><span data-stu-id="23d86-172">You specify the URL in the **URL** field.</span></span>

  - <span data-ttu-id="23d86-173">**Bloquear** Impide que el cliente inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="23d86-173">**Block** Prevents the client from logging on.</span></span>

  - <span data-ttu-id="23d86-174">**Bloquear y actualizar** Impide que el cliente inicie sesión y permite al cliente recibir actualizaciones de Windows Server Update Services o Microsoft Update.</span><span class="sxs-lookup"><span data-stu-id="23d86-174">**Block and Upgrade** Prevents the client from logging on and allows the client to receive updates from Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="23d86-175">Esta acción solo está disponible cuando se selecciona **OC** como agente del usuario.</span><span class="sxs-lookup"><span data-stu-id="23d86-175">This action is available only when user agent **OC** is selected.</span></span>

  - <span data-ttu-id="23d86-p110">**Bloquear con dirección URL** Impide al cliente iniciar sesión y muestra un mensaje que indica dónde descargar otra versión del cliente. Puede especificar la dirección URL en el campo **Dirección URL**.</span><span class="sxs-lookup"><span data-stu-id="23d86-p110">**Block with URL** prevents the client from logging on and displays a message about where to download another client version. You specify the URL in the **URL** field.</span></span>

<span data-ttu-id="23d86-178">Para obtener más información sobre la interoperabilidad entre los clientes y las versiones de cliente, consulte interoperabilidad de [cliente](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) en la documentación de planificación.</span><span class="sxs-lookup"><span data-stu-id="23d86-178">For details about interoperability among clients and client versions, see [Client Interoperability](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation.</span></span> <span data-ttu-id="23d86-179">Para más detalles sobre cómo trabajar con configuraciones de versiones de clientes, mire [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="23d86-179">For details about working with client version configurations, see [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) in the Operations documentation.</span></span>

