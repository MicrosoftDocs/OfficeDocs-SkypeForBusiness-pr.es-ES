---
title: Usar los archivos de registro para solucionar problemas en Microsoft Teams
ms.reviewer: tejeshs
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: troubleshooting
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
description: Conozca los registros de depuración, medios y escritorio generados por Microsoft Teams, dónde se encuentran y cómo pueden ser útiles para resolver problemas.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2d210c5c2e3e2d9b3b3757c2945c504296f00788
ms.sourcegitcommit: a49caec01ff724475d6670b303d851ddd8266c2c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2019
ms.locfileid: "36206952"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a><span data-ttu-id="e4472-103">Usar los archivos de registro para solucionar problemas en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e4472-103">Use log files in troubleshooting Microsoft Teams</span></span>
=================================================

<span data-ttu-id="e4472-104">Hay tres tipos de archivos de registro que el cliente genera automáticamente y que pueden usarse para ayudar en la solución de problemas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e4472-104">There are three types of log files automatically produced by the client that can be leveraged to assist in troubleshooting Microsoft Teams.</span></span>

-   <span data-ttu-id="e4472-105">Registros de depuración</span><span class="sxs-lookup"><span data-stu-id="e4472-105">Debug logs</span></span>

-   <span data-ttu-id="e4472-106">Registros de medios</span><span class="sxs-lookup"><span data-stu-id="e4472-106">Media logs</span></span>

-   <span data-ttu-id="e4472-107">Registros de escritorio</span><span class="sxs-lookup"><span data-stu-id="e4472-107">Desktop logs</span></span>

<span data-ttu-id="e4472-p101">Cuando se crea una solicitud de soporte técnico con Soporte técnico de Microsoft, el ingeniero de soporte técnico necesitará los registros de depuración. Disponer de estos registros con antelación, antes de crear la solicitud de soporte técnico, permitirá a Microsoft empezar rápidamente a resolver el problema. Los registros de medios o de escritorio solo son necesarios si los solicita Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e4472-p101">When creating a support request with Microsoft Support, the support engineer will require the debug logs. Having these logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem. Media or desktop logs are only required if requested by Microsoft.</span></span>

<span data-ttu-id="e4472-p102">En esta table se muestran los distintos clientes y sus registros asociados. Los archivos de registro se almacenan en ubicaciones específicas del cliente y el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="e4472-p102">The following table outlines the various clients, and their associated logs. Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="e4472-113">Cliente</span><span class="sxs-lookup"><span data-stu-id="e4472-113">Client</span></span> |<span data-ttu-id="e4472-114">Depuración</span><span class="sxs-lookup"><span data-stu-id="e4472-114">Debug</span></span>|<span data-ttu-id="e4472-115">Escritorio</span><span class="sxs-lookup"><span data-stu-id="e4472-115">Desktop</span></span>|<span data-ttu-id="e4472-116">Medios</span><span class="sxs-lookup"><span data-stu-id="e4472-116">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="e4472-117">Web</span><span class="sxs-lookup"><span data-stu-id="e4472-117">Web</span></span>    |<span data-ttu-id="e4472-118">X</span><span class="sxs-lookup"><span data-stu-id="e4472-118">X</span></span>         |-         |-         |
|<span data-ttu-id="e4472-119">Windows</span><span class="sxs-lookup"><span data-stu-id="e4472-119">Windows</span></span>     |<span data-ttu-id="e4472-120">X</span><span class="sxs-lookup"><span data-stu-id="e4472-120">X</span></span>         |<span data-ttu-id="e4472-121">X</span><span class="sxs-lookup"><span data-stu-id="e4472-121">X</span></span>         |<span data-ttu-id="e4472-122">X</span><span class="sxs-lookup"><span data-stu-id="e4472-122">X</span></span>         |
|<span data-ttu-id="e4472-123">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="e4472-123">Mac OSX</span></span>     |<span data-ttu-id="e4472-124">X</span><span class="sxs-lookup"><span data-stu-id="e4472-124">X</span></span>         |<span data-ttu-id="e4472-125">X</span><span class="sxs-lookup"><span data-stu-id="e4472-125">X</span></span>         |<span data-ttu-id="e4472-126">X</span><span class="sxs-lookup"><span data-stu-id="e4472-126">X</span></span>         |
|<span data-ttu-id="e4472-127">iOS</span><span class="sxs-lookup"><span data-stu-id="e4472-127">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="e4472-128">Android</span><span class="sxs-lookup"><span data-stu-id="e4472-128">Android</span></span>     |-         |-         |-         |

<span data-ttu-id="e4472-129">Para ver una lista completa de los sistemas operativos y los exploradores compatibles, vea [Obtener clientes para Microsoft Teams](get-clients.md).</span><span class="sxs-lookup"><span data-stu-id="e4472-129">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

<a name="debug-logs"></a><span data-ttu-id="e4472-130">Registros de depuración</span><span class="sxs-lookup"><span data-stu-id="e4472-130">Debug logs</span></span>
---------------------------

<span data-ttu-id="e4472-131">Estos son los registros más comunes y son necesarios para todos los casos de soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e4472-131">These are the most common logs and are required for all Microsoft support cases.</span></span> <span data-ttu-id="e4472-132">Los registros de depuración los generan los clientes de escritorio de Windows y Mac, así como los clientes basados en explorador.</span><span class="sxs-lookup"><span data-stu-id="e4472-132">Debug logs are produced by the Windows and Mac desktop clients, as well as browser based clients.</span></span> <span data-ttu-id="e4472-133">Los registros se basan en texto y se leen de abajo hacia arriba.</span><span class="sxs-lookup"><span data-stu-id="e4472-133">The logs are text based and are read from the bottom up.</span></span> <span data-ttu-id="e4472-134">Se pueden leer con cualquier editor basado en texto y los nuevos registros se crean al iniciar sesión en el cliente.</span><span class="sxs-lookup"><span data-stu-id="e4472-134">They can be read using any text based editor and new logs are created when logging into the client.</span></span>

<span data-ttu-id="e4472-135">Los registros de depuración muestran los siguientes flujos de datos:</span><span class="sxs-lookup"><span data-stu-id="e4472-135">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="e4472-136">Inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="e4472-136">Login</span></span>

-   <span data-ttu-id="e4472-137">Solicitudes de conexión a servicios de nivel intermedio</span><span class="sxs-lookup"><span data-stu-id="e4472-137">Connection requests to middle tier services</span></span>

-   <span data-ttu-id="e4472-138">Llamada/conversación</span><span class="sxs-lookup"><span data-stu-id="e4472-138">Call/conversation</span></span>

<span data-ttu-id="e4472-139">Los registros de depuración se generan usando los siguientes métodos de SO específicos:</span><span class="sxs-lookup"><span data-stu-id="e4472-139">The debug logs are produced using the following OS specific methods:</span></span>

-   <span data-ttu-id="e4472-140">Windows:</span><span class="sxs-lookup"><span data-stu-id="e4472-140">Windows:</span></span>

      <span data-ttu-id="e4472-141">Método abreviado de teclado: Ctrl + Alt + Mayús + 1</span><span class="sxs-lookup"><span data-stu-id="e4472-141">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

-   <span data-ttu-id="e4472-142">Mac OSX:</span><span class="sxs-lookup"><span data-stu-id="e4472-142">Mac OSX:</span></span>

      <span data-ttu-id="e4472-143">Método abreviado de teclado: Opción + Comando + Mayús + 1</span><span class="sxs-lookup"><span data-stu-id="e4472-143">Keyboard shortcut: Option + Command + Shift+1</span></span>

<span data-ttu-id="e4472-144">Los registros de depuración se descargan automáticamente en las siguientes carpetas.</span><span class="sxs-lookup"><span data-stu-id="e4472-144">The debug logs are automatically downloaded to the following folders.</span></span>

-   <span data-ttu-id="e4472-145">Windows: %userprofile%\\Descargas</span><span class="sxs-lookup"><span data-stu-id="e4472-145">Windows: %userprofile%\\Downloads</span></span>

-   <span data-ttu-id="e4472-146">Mac OSX: Descargas</span><span class="sxs-lookup"><span data-stu-id="e4472-146">Mac OSX: Downloads</span></span>

-   <span data-ttu-id="e4472-147">Explorador: Se le pedirá que guarde el registro de depuración en la ubicación predeterminada.</span><span class="sxs-lookup"><span data-stu-id="e4472-147">Browser: You will be prompted to save the debug log to default save location</span></span>

<a name="media-logs"></a><span data-ttu-id="e4472-148">Registros de medios</span><span class="sxs-lookup"><span data-stu-id="e4472-148">Media Logs</span></span>
---------------------------

<span data-ttu-id="e4472-p104">Los registros de medios contienen datos de diagnóstico sobre el uso compartido de pantalla, audio, vídeo. Son necesarios para resolver casos de soporte técnico. Se generan únicamente bajo petición y solo pueden ser inspeccionados por Microsoft. En la siguiente tabla se muestra la ubicación del registro.</span><span class="sxs-lookup"><span data-stu-id="e4472-p104">Media logs contain diagnostic data about audio, video and screen sharing. They are required for support cases only upon request and can only be inspected by Microsoft. The following table outlines the log location.</span></span>


|<span data-ttu-id="e4472-152">Cliente</span><span class="sxs-lookup"><span data-stu-id="e4472-152">Client</span></span> |<span data-ttu-id="e4472-153">Ubicación</span><span class="sxs-lookup"><span data-stu-id="e4472-153">Location</span></span> |
|---------|---------|
|<span data-ttu-id="e4472-154">Windows</span><span class="sxs-lookup"><span data-stu-id="e4472-154">Windows</span></span>     |<span data-ttu-id="e4472-155">%appdata%\Microsoft\Teams\media-stack\*. blog</span><span class="sxs-lookup"><span data-stu-id="e4472-155">%appdata%\Microsoft\Teams\media-stack\*.blog</span></span>         |
|            |<span data-ttu-id="e4472-156">%appdata%\Microsoft\Teams\skylib\*. blog</span><span class="sxs-lookup"><span data-stu-id="e4472-156">%appdata%\Microsoft\Teams\skylib\*.blog</span></span>
|            |<span data-ttu-id="e4472-157">%appdata%\Microsoft\Teams\media-stack\*. ETL</span><span class="sxs-lookup"><span data-stu-id="e4472-157">%appdata%\Microsoft\Teams\media-stack\*.etl</span></span>         |
|<span data-ttu-id="e4472-158">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="e4472-158">Mac OSX</span></span>     |<span data-ttu-id="e4472-159">~/Library/Application Support/Microsoft/Teams/media-stack\*.blog</span><span class="sxs-lookup"><span data-stu-id="e4472-159">~/Library/Application Support/Microsoft/Teams/media-stack\*.blog</span></span>         |
|            |<span data-ttu-id="e4472-160">~/Library/Application Support/Microsoft/Teams/\*skylib. blog</span><span class="sxs-lookup"><span data-stu-id="e4472-160">~/Library/Application Support/Microsoft/Teams/skylib\*.blog</span></span>         |



<a name="desktop-logs"></a><span data-ttu-id="e4472-161">Registros de escritorio</span><span class="sxs-lookup"><span data-stu-id="e4472-161">Desktop logs</span></span>
---------------------

<span data-ttu-id="e4472-p105">Los registros de escritorio, también conocidos como registros de programa previo, contienen datos de registro que se producen entre el cliente de escritorio y el explorador. Al igual que los registros de medios, estos registros solo son necesarios si los solicita Microsoft. Los registros son archivos de texto y se pueden leer con cualquier editor de texto de arriba abajo.</span><span class="sxs-lookup"><span data-stu-id="e4472-p105">Desktop logs, also known as bootstrapper logs, contains log data that occurs between the desktop client and the browser. Like media logs, these logs are only needed if requested by Microsoft. The logs are text based and can be read using any text based editor in a top down format.</span></span>

<span data-ttu-id="e4472-165">Windows:</span><span class="sxs-lookup"><span data-stu-id="e4472-165">Windows:</span></span>

1.  <span data-ttu-id="e4472-166">Haga clic con el botón secundario en el **icono de Microsoft Teams** en la bandeja de la aplicación y seleccione **Obtener registros**.</span><span class="sxs-lookup"><span data-stu-id="e4472-166">Right-click **the Microsoft Teams icon in** your application tray, select **Get Logs**</span></span>

<span data-ttu-id="e4472-167">Mac OsX:</span><span class="sxs-lookup"><span data-stu-id="e4472-167">Mac OsX:</span></span>

1.  <span data-ttu-id="e4472-168">Elija **Obtener registros** en el menú desplegabe **Ayuda**.</span><span class="sxs-lookup"><span data-stu-id="e4472-168">Choosing **Get Logs** from the **Help** pull-down menu</span></span>

|<span data-ttu-id="e4472-169">Cliente</span><span class="sxs-lookup"><span data-stu-id="e4472-169">Client</span></span> |<span data-ttu-id="e4472-170">Ubicación</span><span class="sxs-lookup"><span data-stu-id="e4472-170">Location</span></span> |
|---------|---------|
|<span data-ttu-id="e4472-171">Windows</span><span class="sxs-lookup"><span data-stu-id="e4472-171">Windows</span></span>     |<span data-ttu-id="e4472-172">%appdata%\Microsoft\Teams\logs.txt</span><span class="sxs-lookup"><span data-stu-id="e4472-172">%appdata%\Microsoft\Teams\logs.txt</span></span>         |
|<span data-ttu-id="e4472-173">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="e4472-173">Mac OSX</span></span>     |<span data-ttu-id="e4472-174">~/Library/Application Support/Microsoft/Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="e4472-174">~/Library/Application Support/Microsoft/Teams/logs.txt</span></span>         |
