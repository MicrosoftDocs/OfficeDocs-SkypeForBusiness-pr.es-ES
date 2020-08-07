---
title: Usar los archivos de registro para solucionar problemas en Microsoft Teams
ms.reviewer: tejeshs
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 09/25/2017
audience: admin
ms.topic: troubleshooting
ms.service: msteams
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
search.appverid: MET150
description: Conozca los registros de depuración, medios y escritorio generados por Microsoft Teams, dónde se encuentran y cómo pueden ser útiles para resolver problemas.
appliesto:
- Microsoft Teams
ms.openlocfilehash: f13acc1a401a6753b335c17fe0cd8a7984849216
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "46582117"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a><span data-ttu-id="2aa7f-103">Usar los archivos de registro para solucionar problemas en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2aa7f-103">Use log files in troubleshooting Microsoft Teams</span></span>
=================================================

<span data-ttu-id="2aa7f-104">Hay tres tipos de archivos de registro que el cliente genera automáticamente y que pueden usarse para ayudar en la solución de problemas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2aa7f-104">There are three types of log files automatically produced by the client that can be leveraged to assist in troubleshooting Microsoft Teams.</span></span>

-   <span data-ttu-id="2aa7f-105">Registros de depuración</span><span class="sxs-lookup"><span data-stu-id="2aa7f-105">Debug logs</span></span>

-   <span data-ttu-id="2aa7f-106">Registros de medios</span><span class="sxs-lookup"><span data-stu-id="2aa7f-106">Media logs</span></span>

-   <span data-ttu-id="2aa7f-107">Registros de escritorio</span><span class="sxs-lookup"><span data-stu-id="2aa7f-107">Desktop logs</span></span>

<span data-ttu-id="2aa7f-p101">Cuando se crea una solicitud de soporte técnico con Soporte técnico de Microsoft, el ingeniero de soporte técnico necesitará los registros de depuración. Disponer de estos registros con antelación, antes de crear la solicitud de soporte técnico, permitirá a Microsoft empezar rápidamente a resolver el problema. Los registros de medios o de escritorio solo son necesarios si los solicita Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2aa7f-p101">When creating a support request with Microsoft Support, the support engineer will require the debug logs. Having these logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem. Media or desktop logs are only required if requested by Microsoft.</span></span>

<span data-ttu-id="2aa7f-p102">En esta table se muestran los distintos clientes y sus registros asociados. Los archivos de registro se almacenan en ubicaciones específicas del cliente y el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="2aa7f-p102">The following table outlines the various clients, and their associated logs. Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="2aa7f-113">Cliente</span><span class="sxs-lookup"><span data-stu-id="2aa7f-113">Client</span></span> |<span data-ttu-id="2aa7f-114">Depuración</span><span class="sxs-lookup"><span data-stu-id="2aa7f-114">Debug</span></span>|<span data-ttu-id="2aa7f-115">Escritorio</span><span class="sxs-lookup"><span data-stu-id="2aa7f-115">Desktop</span></span>|<span data-ttu-id="2aa7f-116">Medios</span><span class="sxs-lookup"><span data-stu-id="2aa7f-116">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="2aa7f-117">Web</span><span class="sxs-lookup"><span data-stu-id="2aa7f-117">Web</span></span>    |<span data-ttu-id="2aa7f-118">X</span><span class="sxs-lookup"><span data-stu-id="2aa7f-118">X</span></span>         |-         |-         |
|<span data-ttu-id="2aa7f-119">Windows</span><span class="sxs-lookup"><span data-stu-id="2aa7f-119">Windows</span></span>     |<span data-ttu-id="2aa7f-120">X</span><span class="sxs-lookup"><span data-stu-id="2aa7f-120">X</span></span>         |<span data-ttu-id="2aa7f-121">X</span><span class="sxs-lookup"><span data-stu-id="2aa7f-121">X</span></span>         |<span data-ttu-id="2aa7f-122">X</span><span class="sxs-lookup"><span data-stu-id="2aa7f-122">X</span></span>         |
|<span data-ttu-id="2aa7f-123">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="2aa7f-123">Mac OSX</span></span>     |<span data-ttu-id="2aa7f-124">X</span><span class="sxs-lookup"><span data-stu-id="2aa7f-124">X</span></span>         |<span data-ttu-id="2aa7f-125">X</span><span class="sxs-lookup"><span data-stu-id="2aa7f-125">X</span></span>         |<span data-ttu-id="2aa7f-126">X</span><span class="sxs-lookup"><span data-stu-id="2aa7f-126">X</span></span>         |
|<span data-ttu-id="2aa7f-127">Linux</span><span class="sxs-lookup"><span data-stu-id="2aa7f-127">Linux</span></span>     |<span data-ttu-id="2aa7f-128">X</span><span class="sxs-lookup"><span data-stu-id="2aa7f-128">X</span></span>         |<span data-ttu-id="2aa7f-129">X</span><span class="sxs-lookup"><span data-stu-id="2aa7f-129">X</span></span>         |<span data-ttu-id="2aa7f-130">X</span><span class="sxs-lookup"><span data-stu-id="2aa7f-130">X</span></span>         |
|<span data-ttu-id="2aa7f-131">iOS</span><span class="sxs-lookup"><span data-stu-id="2aa7f-131">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="2aa7f-132">Android</span><span class="sxs-lookup"><span data-stu-id="2aa7f-132">Android</span></span>     |-         |-         |-         |

<span data-ttu-id="2aa7f-133">Para ver una lista completa de los sistemas operativos y los exploradores compatibles, vea [Obtener clientes para Microsoft Teams](get-clients.md).</span><span class="sxs-lookup"><span data-stu-id="2aa7f-133">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

<a name="debug-logs"></a><span data-ttu-id="2aa7f-134">Registros de depuración</span><span class="sxs-lookup"><span data-stu-id="2aa7f-134">Debug logs</span></span>
---------------------------

<span data-ttu-id="2aa7f-135">Estos son los registros más comunes y son necesarios para todos los casos de soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2aa7f-135">These are the most common logs and are required for all Microsoft support cases.</span></span> <span data-ttu-id="2aa7f-136">Los registros de depuración los generan los clientes de escritorio de Windows y Mac, así como los clientes basados en explorador.</span><span class="sxs-lookup"><span data-stu-id="2aa7f-136">Debug logs are produced by the Windows and Mac desktop clients, as well as browser based clients.</span></span> <span data-ttu-id="2aa7f-137">Los registros se basan en texto y se leen de abajo hacia arriba.</span><span class="sxs-lookup"><span data-stu-id="2aa7f-137">The logs are text based and are read from the bottom up.</span></span> <span data-ttu-id="2aa7f-138">Se pueden leer con cualquier editor basado en texto y los nuevos registros se crean al iniciar sesión en el cliente.</span><span class="sxs-lookup"><span data-stu-id="2aa7f-138">They can be read using any text based editor and new logs are created when logging into the client.</span></span>

<span data-ttu-id="2aa7f-139">Los registros de depuración muestran los siguientes flujos de datos:</span><span class="sxs-lookup"><span data-stu-id="2aa7f-139">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="2aa7f-140">Inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="2aa7f-140">Login</span></span>

-   <span data-ttu-id="2aa7f-141">Solicitudes de conexión a servicios de nivel intermedio</span><span class="sxs-lookup"><span data-stu-id="2aa7f-141">Connection requests to middle tier services</span></span>

-   <span data-ttu-id="2aa7f-142">Llamada/conversación</span><span class="sxs-lookup"><span data-stu-id="2aa7f-142">Call/conversation</span></span>

<span data-ttu-id="2aa7f-143">Los registros de depuración se generan usando los siguientes métodos de SO específicos:</span><span class="sxs-lookup"><span data-stu-id="2aa7f-143">The debug logs are produced using the following OS specific methods:</span></span>

-   <span data-ttu-id="2aa7f-144">Windows:</span><span class="sxs-lookup"><span data-stu-id="2aa7f-144">Windows:</span></span>

      <span data-ttu-id="2aa7f-145">Método abreviado de teclado: Ctrl + Alt + Mayús + 1</span><span class="sxs-lookup"><span data-stu-id="2aa7f-145">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

-   <span data-ttu-id="2aa7f-146">Mac OSX:</span><span class="sxs-lookup"><span data-stu-id="2aa7f-146">Mac OSX:</span></span>

      <span data-ttu-id="2aa7f-147">Método abreviado de teclado: Opción + Comando + Mayús + 1</span><span class="sxs-lookup"><span data-stu-id="2aa7f-147">Keyboard shortcut: Option + Command + Shift+1</span></span>

-   <span data-ttu-id="2aa7f-148">Linux</span><span class="sxs-lookup"><span data-stu-id="2aa7f-148">Linux:</span></span>

      <span data-ttu-id="2aa7f-149">Método abreviado de teclado: Ctrl + Alt + Mayús + 1</span><span class="sxs-lookup"><span data-stu-id="2aa7f-149">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

<span data-ttu-id="2aa7f-150">Los registros de depuración se descargan automáticamente en las siguientes carpetas.</span><span class="sxs-lookup"><span data-stu-id="2aa7f-150">The debug logs are automatically downloaded to the following folders.</span></span>

-   <span data-ttu-id="2aa7f-151">Windows: %userprofile%\\Descargas</span><span class="sxs-lookup"><span data-stu-id="2aa7f-151">Windows: %userprofile%\\Downloads</span></span>

-   <span data-ttu-id="2aa7f-152">Mac OSX: Descargas</span><span class="sxs-lookup"><span data-stu-id="2aa7f-152">Mac OSX: Downloads</span></span>

-   <span data-ttu-id="2aa7f-153">Linux: ~/downloads</span><span class="sxs-lookup"><span data-stu-id="2aa7f-153">Linux: ~/Downloads</span></span>

-   <span data-ttu-id="2aa7f-154">Explorador: Se le pedirá que guarde el registro de depuración en la ubicación predeterminada.</span><span class="sxs-lookup"><span data-stu-id="2aa7f-154">Browser: You will be prompted to save the debug log to default save location</span></span>

<a name="media-logs"></a><span data-ttu-id="2aa7f-155">Registros de medios</span><span class="sxs-lookup"><span data-stu-id="2aa7f-155">Media Logs</span></span>
---------------------------

<span data-ttu-id="2aa7f-p104">Los registros de medios contienen datos de diagnóstico sobre el uso compartido de pantalla, audio, vídeo. Son necesarios para resolver casos de soporte técnico. Se generan únicamente bajo petición y solo pueden ser inspeccionados por Microsoft. En la siguiente tabla se muestra la ubicación del registro.</span><span class="sxs-lookup"><span data-stu-id="2aa7f-p104">Media logs contain diagnostic data about audio, video and screen sharing. They are required for support cases only upon request and can only be inspected by Microsoft. The following table outlines the log location.</span></span>


|<span data-ttu-id="2aa7f-159">Cliente</span><span class="sxs-lookup"><span data-stu-id="2aa7f-159">Client</span></span> |<span data-ttu-id="2aa7f-160">Ubicación</span><span class="sxs-lookup"><span data-stu-id="2aa7f-160">Location</span></span> |
|---------|---------|
|<span data-ttu-id="2aa7f-161">Windows</span><span class="sxs-lookup"><span data-stu-id="2aa7f-161">Windows</span></span>     |<span data-ttu-id="2aa7f-162">%appdata%\Microsoft\Teams\media-stack \\ \*. blog</span><span class="sxs-lookup"><span data-stu-id="2aa7f-162">%appdata%\Microsoft\Teams\media-stack\\*.blog</span></span>         |
|            |<span data-ttu-id="2aa7f-163">%appdata%\Microsoft\Teams\skylib \\ \*. blog</span><span class="sxs-lookup"><span data-stu-id="2aa7f-163">%appdata%\Microsoft\Teams\skylib\\*.blog</span></span>
|            |<span data-ttu-id="2aa7f-164">%appdata%\Microsoft\Teams\media-stack \\ \*. ETL</span><span class="sxs-lookup"><span data-stu-id="2aa7f-164">%appdata%\Microsoft\Teams\media-stack\\*.etl</span></span>         |
|<span data-ttu-id="2aa7f-165">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="2aa7f-165">Mac OSX</span></span>     |<span data-ttu-id="2aa7f-166">~/Library/Application Support/Microsoft/Teams/media-Stack/\*. blog</span><span class="sxs-lookup"><span data-stu-id="2aa7f-166">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="2aa7f-167">~/Library/Application Support/Microsoft/Teams/skylib/\*. blog</span><span class="sxs-lookup"><span data-stu-id="2aa7f-167">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span></span>         |
|<span data-ttu-id="2aa7f-168">Linux</span><span class="sxs-lookup"><span data-stu-id="2aa7f-168">Linux</span></span>       |<span data-ttu-id="2aa7f-169">~/.config/Microsoft/Microsoft Teams/media-Stack/\*. blog</span><span class="sxs-lookup"><span data-stu-id="2aa7f-169">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="2aa7f-170">~/.config/Microsoft/Microsoft Teams/skylib/\*. blog</span><span class="sxs-lookup"><span data-stu-id="2aa7f-170">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span></span>         |



<a name="desktop-logs"></a><span data-ttu-id="2aa7f-171">Registros de escritorio</span><span class="sxs-lookup"><span data-stu-id="2aa7f-171">Desktop logs</span></span>
---------------------

<span data-ttu-id="2aa7f-p105">Los registros de escritorio, también conocidos como registros de programa previo, contienen datos de registro que se producen entre el cliente de escritorio y el explorador. Al igual que los registros de medios, estos registros solo son necesarios si los solicita Microsoft. Los registros son archivos de texto y se pueden leer con cualquier editor de texto de arriba abajo.</span><span class="sxs-lookup"><span data-stu-id="2aa7f-p105">Desktop logs, also known as bootstrapper logs, contains log data that occurs between the desktop client and the browser. Like media logs, these logs are only needed if requested by Microsoft. The logs are text based and can be read using any text based editor in a top down format.</span></span>

<span data-ttu-id="2aa7f-175">Windows:</span><span class="sxs-lookup"><span data-stu-id="2aa7f-175">Windows:</span></span>

1.  <span data-ttu-id="2aa7f-176">Haga clic con el botón derecho en el icono de **Microsoft Teams** de la bandeja del sistema y seleccione **obtener registros** .</span><span class="sxs-lookup"><span data-stu-id="2aa7f-176">Right-click the **Microsoft Teams** icon in your system tray, select **Get Logs**</span></span>

<span data-ttu-id="2aa7f-177">Mac OsX:</span><span class="sxs-lookup"><span data-stu-id="2aa7f-177">Mac OsX:</span></span>

1.  <span data-ttu-id="2aa7f-178">Elija **Obtener registros** en el menú desplegabe **Ayuda**.</span><span class="sxs-lookup"><span data-stu-id="2aa7f-178">Choosing **Get Logs** from the **Help** pull-down menu</span></span>

<span data-ttu-id="2aa7f-179">Linux</span><span class="sxs-lookup"><span data-stu-id="2aa7f-179">Linux:</span></span>

1.  <span data-ttu-id="2aa7f-180">Haga clic en el icono de **Microsoft Teams** de la bandeja del sistema y seleccione **obtener registros** .</span><span class="sxs-lookup"><span data-stu-id="2aa7f-180">Click on the **Microsoft Teams** icon in your system tray, select **Get Logs**</span></span>

|<span data-ttu-id="2aa7f-181">Cliente</span><span class="sxs-lookup"><span data-stu-id="2aa7f-181">Client</span></span> |<span data-ttu-id="2aa7f-182">Ubicación</span><span class="sxs-lookup"><span data-stu-id="2aa7f-182">Location</span></span> |
|---------|---------|
|<span data-ttu-id="2aa7f-183">Windows</span><span class="sxs-lookup"><span data-stu-id="2aa7f-183">Windows</span></span>     |<span data-ttu-id="2aa7f-184">% appdata% \Microsoft\Teams\logs.txt</span><span class="sxs-lookup"><span data-stu-id="2aa7f-184">%appdata%\Microsoft\Teams\logs.txt</span></span>         |
|<span data-ttu-id="2aa7f-185">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="2aa7f-185">Mac OSX</span></span>     |<span data-ttu-id="2aa7f-186">~/Library/Application Support/Microsoft/Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="2aa7f-186">~/Library/Application Support/Microsoft/Teams/logs.txt</span></span>         |
|<span data-ttu-id="2aa7f-187">Linux</span><span class="sxs-lookup"><span data-stu-id="2aa7f-187">Linux</span></span>       |<span data-ttu-id="2aa7f-188">~/.config/Microsoft/Microsoft Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="2aa7f-188">~/.config/Microsoft/Microsoft Teams/logs.txt</span></span>         |


## <a name="related-topics"></a><span data-ttu-id="2aa7f-189">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="2aa7f-189">Related topics</span></span>

[<span data-ttu-id="2aa7f-190">Solución de problemas de Teams</span><span class="sxs-lookup"><span data-stu-id="2aa7f-190">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)

