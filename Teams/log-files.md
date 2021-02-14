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
ms.openlocfilehash: 295886e7a5c50107672d17dcfa06067ba1b0ac9b
ms.sourcegitcommit: 48b8801b86a6c900c224853590daa3cb3c8d4ded
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/06/2021
ms.locfileid: "49761098"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a><span data-ttu-id="89a80-103">Usar los archivos de registro para solucionar problemas en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="89a80-103">Use log files in troubleshooting Microsoft Teams</span></span>
=================================================

<span data-ttu-id="89a80-104">Hay tres tipos de archivos de registro generados automáticamente por el cliente, que se pueden usar para ayudar a solucionar problemas de Microsoft Teams:</span><span class="sxs-lookup"><span data-stu-id="89a80-104">There are three types of log files automatically produced by the client, which can be leveraged to assist in troubleshooting Microsoft Teams:</span></span>

-   <span data-ttu-id="89a80-105">Registros de depuración</span><span class="sxs-lookup"><span data-stu-id="89a80-105">Debug logs</span></span>

-   <span data-ttu-id="89a80-106">Registros de medios</span><span class="sxs-lookup"><span data-stu-id="89a80-106">Media logs</span></span>

-   <span data-ttu-id="89a80-107">Registros de escritorio</span><span class="sxs-lookup"><span data-stu-id="89a80-107">Desktop logs</span></span>

<span data-ttu-id="89a80-p101">Al crear una solicitud de soporte técnico con soporte técnico de Microsoft, el ingeniero de soporte técnico requerirá los registros de depuración. Tener los registros de depuración a mano antes de crear la solicitud de soporte técnico permitirá a Microsoft iniciar rápidamente la solución del problema. **Los** registros multimedia **o de** escritorio solo son necesarios si los solicita Microsoft.</span><span class="sxs-lookup"><span data-stu-id="89a80-p101">When creating a support request with Microsoft Support, the support engineer will require the debug logs. Having the debug logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem. **Media** or **desktop** logs are only required if requested by Microsoft.</span></span>

> [!NOTE]
> <span data-ttu-id="89a80-111">En este artículo, el término registros **de depuración** hace referencia a los registros que se usan para la solución de problemas.</span><span class="sxs-lookup"><span data-stu-id="89a80-111">In this article, the term **Debug logs** refers to the logs that are used for troubleshooting.</span></span> <span data-ttu-id="89a80-112">Sin embargo, los archivos que se generan para estos registros contendrán los registros de **diagnóstico de términos** en sus nombres.</span><span class="sxs-lookup"><span data-stu-id="89a80-112">However, the files that are generated for these logs will contain the term **diagnostic logs** in their names.</span></span>  

<span data-ttu-id="89a80-113">En la tabla siguiente se describen los distintos clientes y sus registros asociados.</span><span class="sxs-lookup"><span data-stu-id="89a80-113">The following table outlines the various clients and their associated logs.</span></span> <span data-ttu-id="89a80-114">Los archivos de registro se almacenan en ubicaciones específicas del cliente y del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="89a80-114">Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="89a80-115">Cliente</span><span class="sxs-lookup"><span data-stu-id="89a80-115">Client</span></span> |<span data-ttu-id="89a80-116">Depuración</span><span class="sxs-lookup"><span data-stu-id="89a80-116">Debug</span></span>|<span data-ttu-id="89a80-117">Escritorio</span><span class="sxs-lookup"><span data-stu-id="89a80-117">Desktop</span></span>|<span data-ttu-id="89a80-118">Medios</span><span class="sxs-lookup"><span data-stu-id="89a80-118">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="89a80-119">Web</span><span class="sxs-lookup"><span data-stu-id="89a80-119">Web</span></span>    |<span data-ttu-id="89a80-120">X</span><span class="sxs-lookup"><span data-stu-id="89a80-120">X</span></span>         |-         |-         |
|<span data-ttu-id="89a80-121">Windows</span><span class="sxs-lookup"><span data-stu-id="89a80-121">Windows</span></span>     |<span data-ttu-id="89a80-122">X</span><span class="sxs-lookup"><span data-stu-id="89a80-122">X</span></span>         |<span data-ttu-id="89a80-123">X</span><span class="sxs-lookup"><span data-stu-id="89a80-123">X</span></span>         |<span data-ttu-id="89a80-124">X</span><span class="sxs-lookup"><span data-stu-id="89a80-124">X</span></span>         |
|<span data-ttu-id="89a80-125">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="89a80-125">Mac OSX</span></span>     |<span data-ttu-id="89a80-126">X</span><span class="sxs-lookup"><span data-stu-id="89a80-126">X</span></span>         |<span data-ttu-id="89a80-127">X</span><span class="sxs-lookup"><span data-stu-id="89a80-127">X</span></span>         |<span data-ttu-id="89a80-128">X</span><span class="sxs-lookup"><span data-stu-id="89a80-128">X</span></span>         |
|<span data-ttu-id="89a80-129">Linux</span><span class="sxs-lookup"><span data-stu-id="89a80-129">Linux</span></span>     |<span data-ttu-id="89a80-130">X</span><span class="sxs-lookup"><span data-stu-id="89a80-130">X</span></span>         |<span data-ttu-id="89a80-131">X</span><span class="sxs-lookup"><span data-stu-id="89a80-131">X</span></span>         |<span data-ttu-id="89a80-132">X</span><span class="sxs-lookup"><span data-stu-id="89a80-132">X</span></span>         |
|<span data-ttu-id="89a80-133">iOS</span><span class="sxs-lookup"><span data-stu-id="89a80-133">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="89a80-134">Android</span><span class="sxs-lookup"><span data-stu-id="89a80-134">Android</span></span>     |-         |-         |-         |

<span data-ttu-id="89a80-135">Para ver una lista completa de los sistemas operativos y los exploradores compatibles, vea [Obtener clientes para Microsoft Teams](get-clients.md).</span><span class="sxs-lookup"><span data-stu-id="89a80-135">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

<a name="debug-logs"></a><span data-ttu-id="89a80-136">Registros de depuración</span><span class="sxs-lookup"><span data-stu-id="89a80-136">Debug logs</span></span>
---------------------------

<span data-ttu-id="89a80-137">Estos son los registros más comunes y son necesarios para todos los casos de soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="89a80-137">These are the most common logs and are required for all Microsoft support cases.</span></span> <span data-ttu-id="89a80-138">Los registros de depuración se producen por los clientes de escritorio de Windows y Mac, así como por clientes basados en explorador.</span><span class="sxs-lookup"><span data-stu-id="89a80-138">Debug logs are produced by the Windows and Mac desktop clients, as well as by browser-based clients.</span></span> <span data-ttu-id="89a80-139">Los registros se basan en texto y se leen desde abajo hacia arriba.</span><span class="sxs-lookup"><span data-stu-id="89a80-139">The logs are text based and are read from the bottom-up.</span></span> <span data-ttu-id="89a80-140">Se pueden leer con cualquier editor basado en texto y se crean registros nuevos al iniciar sesión en el cliente.</span><span class="sxs-lookup"><span data-stu-id="89a80-140">They can be read using any text-based editor, and new logs are created when logging into the client.</span></span>

<span data-ttu-id="89a80-141">Los registros de depuración muestran los siguientes flujos de datos:</span><span class="sxs-lookup"><span data-stu-id="89a80-141">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="89a80-142">Inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="89a80-142">Login</span></span>

-   <span data-ttu-id="89a80-143">Solicitudes de conexión a servicios de nivel medio</span><span class="sxs-lookup"><span data-stu-id="89a80-143">Connection requests to middle-tier services</span></span>

-   <span data-ttu-id="89a80-144">Llamada/conversación</span><span class="sxs-lookup"><span data-stu-id="89a80-144">Call/conversation</span></span>

<span data-ttu-id="89a80-145">Los registros de depuración se generan con los siguientes métodos específicos del sistema operativo:</span><span class="sxs-lookup"><span data-stu-id="89a80-145">The debug logs are produced using the following OS-specific methods:</span></span>

-   <span data-ttu-id="89a80-146">Windows:</span><span class="sxs-lookup"><span data-stu-id="89a80-146">Windows:</span></span>

      <span data-ttu-id="89a80-147">Método abreviado de teclado: Ctrl + Alt + Mayús + 1</span><span class="sxs-lookup"><span data-stu-id="89a80-147">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

-   <span data-ttu-id="89a80-148">Mac OSX:</span><span class="sxs-lookup"><span data-stu-id="89a80-148">Mac OSX:</span></span>

      <span data-ttu-id="89a80-149">Método abreviado de teclado: Opción + Comando + Mayús + 1</span><span class="sxs-lookup"><span data-stu-id="89a80-149">Keyboard shortcut: Option + Command + Shift+1</span></span>

-   <span data-ttu-id="89a80-150">Linux:</span><span class="sxs-lookup"><span data-stu-id="89a80-150">Linux:</span></span>

      <span data-ttu-id="89a80-151">Método abreviado de teclado: Ctrl + Alt + Mayús + 1</span><span class="sxs-lookup"><span data-stu-id="89a80-151">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

<span data-ttu-id="89a80-152">Los registros de depuración se descargan automáticamente en las carpetas siguientes:</span><span class="sxs-lookup"><span data-stu-id="89a80-152">The debug logs are automatically downloaded to the following folders:</span></span>

-   <span data-ttu-id="89a80-153">Windows: %userprofile%\\Descargas</span><span class="sxs-lookup"><span data-stu-id="89a80-153">Windows: %userprofile%\\Downloads</span></span>

-   <span data-ttu-id="89a80-154">Mac OSX: ~/Descargas</span><span class="sxs-lookup"><span data-stu-id="89a80-154">Mac OSX: ~/Downloads</span></span>

-   <span data-ttu-id="89a80-155">Linux: ~/Descargas</span><span class="sxs-lookup"><span data-stu-id="89a80-155">Linux: ~/Downloads</span></span>

-   <span data-ttu-id="89a80-156">Explorador: Se le pedirá que guarde el registro de depuración en la ubicación predeterminada.</span><span class="sxs-lookup"><span data-stu-id="89a80-156">Browser: You will be prompted to save the debug log to default save location</span></span>

<a name="media-logs"></a><span data-ttu-id="89a80-157">Registros de medios</span><span class="sxs-lookup"><span data-stu-id="89a80-157">Media logs</span></span>
---------------------------

<span data-ttu-id="89a80-158">Los registros multimedia contienen datos de diagnóstico sobre el audio, el vídeo y el uso compartido de la pantalla en las reuniones de Teams.</span><span class="sxs-lookup"><span data-stu-id="89a80-158">Media logs contain diagnostic data about audio, video, and screen sharing in Teams meetings.</span></span> <span data-ttu-id="89a80-159">Son necesarios para los casos de soporte técnico vinculados a problemas relacionados con la llamada.</span><span class="sxs-lookup"><span data-stu-id="89a80-159">They are required for support cases that are linked to call-related issues.</span></span>

<span data-ttu-id="89a80-160">El registro de medios está desactivado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="89a80-160">Media logging is turned off by default.</span></span> <span data-ttu-id="89a80-161">Para registrar datos de diagnóstico para las reuniones de Teams, los usuarios deben activar la opción en el cliente de Teams.</span><span class="sxs-lookup"><span data-stu-id="89a80-161">To log diagnostic data for Teams meetings, users must turn on the option in the Teams client.</span></span> <span data-ttu-id="89a80-162">Vaya a **Configuración** General, seleccione la casilla Habilitar registro para diagnóstico de reuniones (debe reiniciar Teams), reinicie Teams y  >  reproducir el problema. </span><span class="sxs-lookup"><span data-stu-id="89a80-162">Go to **Settings** > **General**, select the **Enable logging for meeting diagnostics (requires restarting Teams**) check box, restart Teams, and reproduce the issue.</span></span> 

<span data-ttu-id="89a80-163">En la tabla siguiente se describen las ubicaciones del registro multimedia.</span><span class="sxs-lookup"><span data-stu-id="89a80-163">The following table outlines the media log locations.</span></span> <span data-ttu-id="89a80-164">Cuando envíe los archivos de registro al soporte técnico de Microsoft, compruebe la marca de tiempo de los archivos de registro para asegurarse de que los registros cubren el período de tiempo en el que se ha reproducido el problema.</span><span class="sxs-lookup"><span data-stu-id="89a80-164">When you send the log files to Microsoft support, please verify the timestamp of the log files to ensure the logs cover the time frame when you reproduced the issue.</span></span>

|<span data-ttu-id="89a80-165">Cliente</span><span class="sxs-lookup"><span data-stu-id="89a80-165">Client</span></span> |<span data-ttu-id="89a80-166">Ubicación</span><span class="sxs-lookup"><span data-stu-id="89a80-166">Location</span></span> |
|---------|---------|
|<span data-ttu-id="89a80-167">Windows</span><span class="sxs-lookup"><span data-stu-id="89a80-167">Windows</span></span>     |<span data-ttu-id="89a80-168">%appdata%\Microsoft\Teams\media-stack \\ \*.blog</span><span class="sxs-lookup"><span data-stu-id="89a80-168">%appdata%\Microsoft\Teams\media-stack\\*.blog</span></span>         |
|            |<span data-ttu-id="89a80-169">%appdata%\Microsoft\Teams\skylib \\ \*.blog</span><span class="sxs-lookup"><span data-stu-id="89a80-169">%appdata%\Microsoft\Teams\skylib\\*.blog</span></span>
|            |<span data-ttu-id="89a80-170">%appdata%\Microsoft\Teams\media-stack \\ \*.etl</span><span class="sxs-lookup"><span data-stu-id="89a80-170">%appdata%\Microsoft\Teams\media-stack\\*.etl</span></span>         |
|<span data-ttu-id="89a80-171">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="89a80-171">Mac OSX</span></span>     |<span data-ttu-id="89a80-172">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span><span class="sxs-lookup"><span data-stu-id="89a80-172">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="89a80-173">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span><span class="sxs-lookup"><span data-stu-id="89a80-173">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span></span>         |
|<span data-ttu-id="89a80-174">Linux</span><span class="sxs-lookup"><span data-stu-id="89a80-174">Linux</span></span>       |<span data-ttu-id="89a80-175">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span><span class="sxs-lookup"><span data-stu-id="89a80-175">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="89a80-176">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span><span class="sxs-lookup"><span data-stu-id="89a80-176">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span></span>         |

<span data-ttu-id="89a80-177">Esta es una lista de los archivos de registro que se generan y la información que contienen.</span><span class="sxs-lookup"><span data-stu-id="89a80-177">Here's a list of the log files that are generated and the information they contain.</span></span>

|<span data-ttu-id="89a80-178">Nombre de archivo de registro</span><span class="sxs-lookup"><span data-stu-id="89a80-178">Log file name</span></span>  |<span data-ttu-id="89a80-179">Descripción</span><span class="sxs-lookup"><span data-stu-id="89a80-179">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="89a80-180">Teams.msrtc-0-s1039525249.blog</span><span class="sxs-lookup"><span data-stu-id="89a80-180">Teams.msrtc-0-s1039525249.blog</span></span>     | <span data-ttu-id="89a80-181">Contiene información relacionada con la pila de medios.</span><span class="sxs-lookup"><span data-stu-id="89a80-181">Contains information related to the media stack.</span></span> <span data-ttu-id="89a80-182">Esto incluye el estado de canal, como la resolución, los descodificadores y codificadores usados, el número de fotogramas enviados y recibidos, y el estado de sesión de pantalla compartida basada en vídeo y cámara (VBSS).</span><span class="sxs-lookup"><span data-stu-id="89a80-182">This includes channel status such as resolution, decoders and encoders used, and the number of frames sent and received, and camera and video-based screen sharing (VBSS) session status.</span></span>         |
|<span data-ttu-id="89a80-183">rtmcontrol.msrtc-0-2415069487.blog</span><span class="sxs-lookup"><span data-stu-id="89a80-183">rtmcontrol.msrtc-0-2415069487.blog</span></span>      |<span data-ttu-id="89a80-184">Registra información relacionada con acciones de control remoto, como la marca de tiempo cuando se proporciona el control e información del puntero del mouse.</span><span class="sxs-lookup"><span data-stu-id="89a80-184">Records information related to remote control actions, such as the time stamp when control is given, and mouse pointer information.</span></span>          |
|<span data-ttu-id="89a80-185">Teams_MediaStackETW-2-U-xr-U.etl</span><span class="sxs-lookup"><span data-stu-id="89a80-185">Teams_MediaStackETW-2-U-xr-U.etl</span></span>      |<span data-ttu-id="89a80-186">Registros de eventos de seguimiento de la pila de medios.</span><span class="sxs-lookup"><span data-stu-id="89a80-186">Records media stack trace events.</span></span>         |
|<span data-ttu-id="89a80-187">Debug-0-s2790420889.blog</span><span class="sxs-lookup"><span data-stu-id="89a80-187">Debug-0-s2790420889.blog</span></span>    | <span data-ttu-id="89a80-188">Contiene información relacionada con el agente multimedia, incluida la calidad de representación.</span><span class="sxs-lookup"><span data-stu-id="89a80-188">Contains information related to the media agent, including rendering quality.</span></span>          |
|<span data-ttu-id="89a80-189">tscalling-0-2061129496.blog</span><span class="sxs-lookup"><span data-stu-id="89a80-189">tscalling-0-2061129496.blog</span></span>   |<span data-ttu-id="89a80-190">Registra eventos en la API de llamada ts.</span><span class="sxs-lookup"><span data-stu-id="89a80-190">Records events in the ts-calling API.</span></span>       |

<a name="desktop-logs"></a><span data-ttu-id="89a80-191">Registros de escritorio</span><span class="sxs-lookup"><span data-stu-id="89a80-191">Desktop logs</span></span>
---------------------

<span data-ttu-id="89a80-192">Los registros de escritorio, también conocidos como registros de programa previo, contienen datos de registro que se producen entre el cliente de escritorio y el explorador.</span><span class="sxs-lookup"><span data-stu-id="89a80-192">Desktop logs, also known as bootstrapper logs, contain log data that occurs between the desktop client and the browser.</span></span> <span data-ttu-id="89a80-193">Al igual que los registros multimedia, estos registros solo son necesarios si los solicita Microsoft.</span><span class="sxs-lookup"><span data-stu-id="89a80-193">Like media logs, these logs are only needed if requested by Microsoft.</span></span> <span data-ttu-id="89a80-194">Los registros se basan en texto y se pueden leer con cualquier editor basado en texto en formato desplegable.</span><span class="sxs-lookup"><span data-stu-id="89a80-194">The logs are text based and can be read using any text-based editor in a top-down format.</span></span>

<span data-ttu-id="89a80-195">Windows:</span><span class="sxs-lookup"><span data-stu-id="89a80-195">Windows:</span></span>

 - <span data-ttu-id="89a80-196">Haga clic con el botón **derecho en el** icono de Microsoft Teams en la bandeja del sistema y seleccione Obtener **registros.**</span><span class="sxs-lookup"><span data-stu-id="89a80-196">Right-click the **Microsoft Teams** icon in your system tray, and select **Get Logs**.</span></span>

<span data-ttu-id="89a80-197">Mac OsX:</span><span class="sxs-lookup"><span data-stu-id="89a80-197">Mac OsX:</span></span>

 - <span data-ttu-id="89a80-198">Elija **Obtener registros** en el menú desplegable Ayuda. </span><span class="sxs-lookup"><span data-stu-id="89a80-198">Choose **Get Logs** from the **Help** pull-down menu.</span></span>

<span data-ttu-id="89a80-199">Linux:</span><span class="sxs-lookup"><span data-stu-id="89a80-199">Linux:</span></span>

 - <span data-ttu-id="89a80-200">Haga clic en **el icono de Microsoft Teams** en la bandeja del sistema y seleccione Obtener **registros.**</span><span class="sxs-lookup"><span data-stu-id="89a80-200">Click on the **Microsoft Teams** icon in your system tray, and select **Get Logs**.</span></span>

|<span data-ttu-id="89a80-201">Cliente</span><span class="sxs-lookup"><span data-stu-id="89a80-201">Client</span></span> |<span data-ttu-id="89a80-202">Ubicación</span><span class="sxs-lookup"><span data-stu-id="89a80-202">Location</span></span> |
|---------|---------|
|<span data-ttu-id="89a80-203">Windows</span><span class="sxs-lookup"><span data-stu-id="89a80-203">Windows</span></span>     |<span data-ttu-id="89a80-204">%appdata%\Microsoft\Teams\logs.txt</span><span class="sxs-lookup"><span data-stu-id="89a80-204">%appdata%\Microsoft\Teams\logs.txt</span></span>         |
|<span data-ttu-id="89a80-205">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="89a80-205">Mac OSX</span></span>     |<span data-ttu-id="89a80-206">~/Library/Application Support/Microsoft/Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="89a80-206">~/Library/Application Support/Microsoft/Teams/logs.txt</span></span>         |
|<span data-ttu-id="89a80-207">Linux</span><span class="sxs-lookup"><span data-stu-id="89a80-207">Linux</span></span>       |<span data-ttu-id="89a80-208">~/.config/Microsoft/Microsoft Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="89a80-208">~/.config/Microsoft/Microsoft Teams/logs.txt</span></span>         |


## <a name="related-topics"></a><span data-ttu-id="89a80-209">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="89a80-209">Related topics</span></span>

[<span data-ttu-id="89a80-210">Solución de problemas de Teams</span><span class="sxs-lookup"><span data-stu-id="89a80-210">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
