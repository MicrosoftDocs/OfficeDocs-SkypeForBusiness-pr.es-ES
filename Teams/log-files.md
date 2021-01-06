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
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a><span data-ttu-id="aebfd-103">Usar los archivos de registro para solucionar problemas en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="aebfd-103">Use log files in troubleshooting Microsoft Teams</span></span>
=================================================

<span data-ttu-id="aebfd-104">Hay tres tipos de archivos de registro generados automáticamente por el cliente, que se pueden aprovechar para ayudar en la solución de problemas de Microsoft Teams:</span><span class="sxs-lookup"><span data-stu-id="aebfd-104">There are three types of log files automatically produced by the client, which can be leveraged to assist in troubleshooting Microsoft Teams:</span></span>

-   <span data-ttu-id="aebfd-105">Registros de depuración</span><span class="sxs-lookup"><span data-stu-id="aebfd-105">Debug logs</span></span>

-   <span data-ttu-id="aebfd-106">Registros de medios</span><span class="sxs-lookup"><span data-stu-id="aebfd-106">Media logs</span></span>

-   <span data-ttu-id="aebfd-107">Registros de escritorio</span><span class="sxs-lookup"><span data-stu-id="aebfd-107">Desktop logs</span></span>

<span data-ttu-id="aebfd-p101">Al crear una solicitud de soporte con el soporte técnico de Microsoft, el ingeniero de soporte técnico necesitará los registros de depuración. Si cierra la sesión de depuración antes de crear la solicitud de soporte técnico, Microsoft le permitirá comenzar rápidamente a solucionar el problema. Los registros de **medios** o de **escritorio** solo son necesarios si lo solicita Microsoft.</span><span class="sxs-lookup"><span data-stu-id="aebfd-p101">When creating a support request with Microsoft Support, the support engineer will require the debug logs. Having the debug logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem. **Media** or **desktop** logs are only required if requested by Microsoft.</span></span>

> [!NOTE]
> <span data-ttu-id="aebfd-111">En este artículo, el término **registros de depuración** hace referencia a los registros que se usan para la solución de problemas.</span><span class="sxs-lookup"><span data-stu-id="aebfd-111">In this article, the term **Debug logs** refers to the logs that are used for troubleshooting.</span></span> <span data-ttu-id="aebfd-112">Sin embargo, los archivos que se generan para estos registros contendrán el término **registros de diagnóstico** en sus nombres.</span><span class="sxs-lookup"><span data-stu-id="aebfd-112">However, the files that are generated for these logs will contain the term **diagnostic logs** in their names.</span></span>  

<span data-ttu-id="aebfd-113">En la tabla siguiente se describen los distintos clientes y los registros asociados.</span><span class="sxs-lookup"><span data-stu-id="aebfd-113">The following table outlines the various clients and their associated logs.</span></span> <span data-ttu-id="aebfd-114">Los archivos de registro se almacenan en ubicaciones específicas del cliente y del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="aebfd-114">Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="aebfd-115">Cliente</span><span class="sxs-lookup"><span data-stu-id="aebfd-115">Client</span></span> |<span data-ttu-id="aebfd-116">Depuración</span><span class="sxs-lookup"><span data-stu-id="aebfd-116">Debug</span></span>|<span data-ttu-id="aebfd-117">Escritorio</span><span class="sxs-lookup"><span data-stu-id="aebfd-117">Desktop</span></span>|<span data-ttu-id="aebfd-118">Medios</span><span class="sxs-lookup"><span data-stu-id="aebfd-118">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="aebfd-119">Web</span><span class="sxs-lookup"><span data-stu-id="aebfd-119">Web</span></span>    |<span data-ttu-id="aebfd-120">X</span><span class="sxs-lookup"><span data-stu-id="aebfd-120">X</span></span>         |-         |-         |
|<span data-ttu-id="aebfd-121">Windows</span><span class="sxs-lookup"><span data-stu-id="aebfd-121">Windows</span></span>     |<span data-ttu-id="aebfd-122">X</span><span class="sxs-lookup"><span data-stu-id="aebfd-122">X</span></span>         |<span data-ttu-id="aebfd-123">X</span><span class="sxs-lookup"><span data-stu-id="aebfd-123">X</span></span>         |<span data-ttu-id="aebfd-124">X</span><span class="sxs-lookup"><span data-stu-id="aebfd-124">X</span></span>         |
|<span data-ttu-id="aebfd-125">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="aebfd-125">Mac OSX</span></span>     |<span data-ttu-id="aebfd-126">X</span><span class="sxs-lookup"><span data-stu-id="aebfd-126">X</span></span>         |<span data-ttu-id="aebfd-127">X</span><span class="sxs-lookup"><span data-stu-id="aebfd-127">X</span></span>         |<span data-ttu-id="aebfd-128">X</span><span class="sxs-lookup"><span data-stu-id="aebfd-128">X</span></span>         |
|<span data-ttu-id="aebfd-129">Linux</span><span class="sxs-lookup"><span data-stu-id="aebfd-129">Linux</span></span>     |<span data-ttu-id="aebfd-130">X</span><span class="sxs-lookup"><span data-stu-id="aebfd-130">X</span></span>         |<span data-ttu-id="aebfd-131">X</span><span class="sxs-lookup"><span data-stu-id="aebfd-131">X</span></span>         |<span data-ttu-id="aebfd-132">X</span><span class="sxs-lookup"><span data-stu-id="aebfd-132">X</span></span>         |
|<span data-ttu-id="aebfd-133">iOS</span><span class="sxs-lookup"><span data-stu-id="aebfd-133">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="aebfd-134">Android</span><span class="sxs-lookup"><span data-stu-id="aebfd-134">Android</span></span>     |-         |-         |-         |

<span data-ttu-id="aebfd-135">Para ver una lista completa de los sistemas operativos y los exploradores compatibles, vea [Obtener clientes para Microsoft Teams](get-clients.md).</span><span class="sxs-lookup"><span data-stu-id="aebfd-135">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

<a name="debug-logs"></a><span data-ttu-id="aebfd-136">Registros de depuración</span><span class="sxs-lookup"><span data-stu-id="aebfd-136">Debug logs</span></span>
---------------------------

<span data-ttu-id="aebfd-137">Estos son los registros más comunes y son necesarios para todos los casos de soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="aebfd-137">These are the most common logs and are required for all Microsoft support cases.</span></span> <span data-ttu-id="aebfd-138">Los registros de depuración los generan los clientes de escritorio de Windows y Mac, así como los clientes basados en el explorador.</span><span class="sxs-lookup"><span data-stu-id="aebfd-138">Debug logs are produced by the Windows and Mac desktop clients, as well as by browser-based clients.</span></span> <span data-ttu-id="aebfd-139">Los registros se basan en texto y se leen de abajo hacia arriba.</span><span class="sxs-lookup"><span data-stu-id="aebfd-139">The logs are text based and are read from the bottom-up.</span></span> <span data-ttu-id="aebfd-140">Se pueden leer con cualquier editor basado en texto y se crean nuevos registros al iniciar sesión en el cliente.</span><span class="sxs-lookup"><span data-stu-id="aebfd-140">They can be read using any text-based editor, and new logs are created when logging into the client.</span></span>

<span data-ttu-id="aebfd-141">Los registros de depuración muestran los siguientes flujos de datos:</span><span class="sxs-lookup"><span data-stu-id="aebfd-141">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="aebfd-142">Inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="aebfd-142">Login</span></span>

-   <span data-ttu-id="aebfd-143">Solicitudes de conexión a servicios de nivel medio</span><span class="sxs-lookup"><span data-stu-id="aebfd-143">Connection requests to middle-tier services</span></span>

-   <span data-ttu-id="aebfd-144">Llamada/conversación</span><span class="sxs-lookup"><span data-stu-id="aebfd-144">Call/conversation</span></span>

<span data-ttu-id="aebfd-145">Los registros de depuración se generan con los siguientes métodos específicos del sistema operativo:</span><span class="sxs-lookup"><span data-stu-id="aebfd-145">The debug logs are produced using the following OS-specific methods:</span></span>

-   <span data-ttu-id="aebfd-146">Windows:</span><span class="sxs-lookup"><span data-stu-id="aebfd-146">Windows:</span></span>

      <span data-ttu-id="aebfd-147">Método abreviado de teclado: Ctrl + Alt + Mayús + 1</span><span class="sxs-lookup"><span data-stu-id="aebfd-147">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

-   <span data-ttu-id="aebfd-148">Mac OSX:</span><span class="sxs-lookup"><span data-stu-id="aebfd-148">Mac OSX:</span></span>

      <span data-ttu-id="aebfd-149">Método abreviado de teclado: Opción + Comando + Mayús + 1</span><span class="sxs-lookup"><span data-stu-id="aebfd-149">Keyboard shortcut: Option + Command + Shift+1</span></span>

-   <span data-ttu-id="aebfd-150">Linux</span><span class="sxs-lookup"><span data-stu-id="aebfd-150">Linux:</span></span>

      <span data-ttu-id="aebfd-151">Método abreviado de teclado: Ctrl + Alt + Mayús + 1</span><span class="sxs-lookup"><span data-stu-id="aebfd-151">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

<span data-ttu-id="aebfd-152">Los registros de depuración se descargan automáticamente en las siguientes carpetas:</span><span class="sxs-lookup"><span data-stu-id="aebfd-152">The debug logs are automatically downloaded to the following folders:</span></span>

-   <span data-ttu-id="aebfd-153">Windows: %userprofile%\\Descargas</span><span class="sxs-lookup"><span data-stu-id="aebfd-153">Windows: %userprofile%\\Downloads</span></span>

-   <span data-ttu-id="aebfd-154">Mac OSX: ~/downloads</span><span class="sxs-lookup"><span data-stu-id="aebfd-154">Mac OSX: ~/Downloads</span></span>

-   <span data-ttu-id="aebfd-155">Linux: ~/downloads</span><span class="sxs-lookup"><span data-stu-id="aebfd-155">Linux: ~/Downloads</span></span>

-   <span data-ttu-id="aebfd-156">Explorador: Se le pedirá que guarde el registro de depuración en la ubicación predeterminada.</span><span class="sxs-lookup"><span data-stu-id="aebfd-156">Browser: You will be prompted to save the debug log to default save location</span></span>

<a name="media-logs"></a><span data-ttu-id="aebfd-157">Registros de medios</span><span class="sxs-lookup"><span data-stu-id="aebfd-157">Media logs</span></span>
---------------------------

<span data-ttu-id="aebfd-158">Los registros multimedia contienen datos de diagnóstico sobre el audio, el vídeo y la pantalla compartida en reuniones de Teams.</span><span class="sxs-lookup"><span data-stu-id="aebfd-158">Media logs contain diagnostic data about audio, video, and screen sharing in Teams meetings.</span></span> <span data-ttu-id="aebfd-159">Son necesarios para los casos de soporte técnico que están vinculados a problemas relacionados con la llamada.</span><span class="sxs-lookup"><span data-stu-id="aebfd-159">They are required for support cases that are linked to call-related issues.</span></span>

<span data-ttu-id="aebfd-160">El registro multimedia está desactivado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="aebfd-160">Media logging is turned off by default.</span></span> <span data-ttu-id="aebfd-161">Para registrar los datos de diagnóstico de las reuniones de Teams, los usuarios deben activar la opción en el cliente de Teams.</span><span class="sxs-lookup"><span data-stu-id="aebfd-161">To log diagnostic data for Teams meetings, users must turn on the option in the Teams client.</span></span> <span data-ttu-id="aebfd-162">Vaya a **configuración**  >  **General**, active la casilla **Habilitar el registro de diagnósticos de reunión (debe reiniciar Teams**), reinicie Teams y reproduzca el problema.</span><span class="sxs-lookup"><span data-stu-id="aebfd-162">Go to **Settings** > **General**, select the **Enable logging for meeting diagnostics (requires restarting Teams**) check box, restart Teams, and reproduce the issue.</span></span> 

<span data-ttu-id="aebfd-163">En la tabla siguiente se describen las ubicaciones de los registros de medios.</span><span class="sxs-lookup"><span data-stu-id="aebfd-163">The following table outlines the media log locations.</span></span> <span data-ttu-id="aebfd-164">Cuando envíe los archivos de registro al soporte técnico de Microsoft, Compruebe la marca de tiempo de los archivos de registro para asegurarse de que los registros cubren el intervalo de tiempo cuando reproducido el problema.</span><span class="sxs-lookup"><span data-stu-id="aebfd-164">When you send the log files to Microsoft support, please verify the timestamp of the log files to ensure the logs cover the time frame when you reproduced the issue.</span></span>

|<span data-ttu-id="aebfd-165">Cliente</span><span class="sxs-lookup"><span data-stu-id="aebfd-165">Client</span></span> |<span data-ttu-id="aebfd-166">Ubicación</span><span class="sxs-lookup"><span data-stu-id="aebfd-166">Location</span></span> |
|---------|---------|
|<span data-ttu-id="aebfd-167">Windows</span><span class="sxs-lookup"><span data-stu-id="aebfd-167">Windows</span></span>     |<span data-ttu-id="aebfd-168">%appdata%\Microsoft\Teams\media-stack \\ \*. blog</span><span class="sxs-lookup"><span data-stu-id="aebfd-168">%appdata%\Microsoft\Teams\media-stack\\*.blog</span></span>         |
|            |<span data-ttu-id="aebfd-169">%appdata%\Microsoft\Teams\skylib \\ \*. blog</span><span class="sxs-lookup"><span data-stu-id="aebfd-169">%appdata%\Microsoft\Teams\skylib\\*.blog</span></span>
|            |<span data-ttu-id="aebfd-170">%appdata%\Microsoft\Teams\media-stack \\ \*. ETL</span><span class="sxs-lookup"><span data-stu-id="aebfd-170">%appdata%\Microsoft\Teams\media-stack\\*.etl</span></span>         |
|<span data-ttu-id="aebfd-171">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="aebfd-171">Mac OSX</span></span>     |<span data-ttu-id="aebfd-172">~/Library/Application Support/Microsoft/Teams/media-Stack/\*. blog</span><span class="sxs-lookup"><span data-stu-id="aebfd-172">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="aebfd-173">~/Library/Application Support/Microsoft/Teams/skylib/\*. blog</span><span class="sxs-lookup"><span data-stu-id="aebfd-173">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span></span>         |
|<span data-ttu-id="aebfd-174">Linux</span><span class="sxs-lookup"><span data-stu-id="aebfd-174">Linux</span></span>       |<span data-ttu-id="aebfd-175">~/.config/Microsoft/Microsoft Teams/media-Stack/\*. blog</span><span class="sxs-lookup"><span data-stu-id="aebfd-175">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="aebfd-176">~/.config/Microsoft/Microsoft Teams/skylib/\*. blog</span><span class="sxs-lookup"><span data-stu-id="aebfd-176">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span></span>         |

<span data-ttu-id="aebfd-177">Esta es una lista de los archivos de registro que se generan y la información que contienen.</span><span class="sxs-lookup"><span data-stu-id="aebfd-177">Here's a list of the log files that are generated and the information they contain.</span></span>

|<span data-ttu-id="aebfd-178">Nombre de archivo de registro</span><span class="sxs-lookup"><span data-stu-id="aebfd-178">Log file name</span></span>  |<span data-ttu-id="aebfd-179">Descripción</span><span class="sxs-lookup"><span data-stu-id="aebfd-179">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="aebfd-180">Teams. MSRTC-0-s1039525249. blog</span><span class="sxs-lookup"><span data-stu-id="aebfd-180">Teams.msrtc-0-s1039525249.blog</span></span>     | <span data-ttu-id="aebfd-181">Contiene información relacionada con la pila de medios.</span><span class="sxs-lookup"><span data-stu-id="aebfd-181">Contains information related to the media stack.</span></span> <span data-ttu-id="aebfd-182">Esto incluye el estado del canal, como la resolución, los descodificadores y los codificadores que se usan, así como el número de tramas enviadas y recibidas y el estado de sesión de pantalla compartida basada en vídeo y en vídeo (VBSS).</span><span class="sxs-lookup"><span data-stu-id="aebfd-182">This includes channel status such as resolution, decoders and encoders used, and the number of frames sent and received, and camera and video-based screen sharing (VBSS) session status.</span></span>         |
|<span data-ttu-id="aebfd-183">rtmcontrol. MSRTC-0-2415069487. blog</span><span class="sxs-lookup"><span data-stu-id="aebfd-183">rtmcontrol.msrtc-0-2415069487.blog</span></span>      |<span data-ttu-id="aebfd-184">Registra información relacionada con acciones de control remoto, como la marca de tiempo cuando se proporciona el control e información sobre el puntero del mouse.</span><span class="sxs-lookup"><span data-stu-id="aebfd-184">Records information related to remote control actions, such as the time stamp when control is given, and mouse pointer information.</span></span>          |
|<span data-ttu-id="aebfd-185">Teams_MediaStackETW -2-U-xr-U. ETL</span><span class="sxs-lookup"><span data-stu-id="aebfd-185">Teams_MediaStackETW-2-U-xr-U.etl</span></span>      |<span data-ttu-id="aebfd-186">Registra eventos de seguimiento de pila de medios.</span><span class="sxs-lookup"><span data-stu-id="aebfd-186">Records media stack trace events.</span></span>         |
|<span data-ttu-id="aebfd-187">Depurar: 0-s2790420889. blog</span><span class="sxs-lookup"><span data-stu-id="aebfd-187">Debug-0-s2790420889.blog</span></span>    | <span data-ttu-id="aebfd-188">Contiene información relacionada con el agente multimedia, incluida la calidad de representación.</span><span class="sxs-lookup"><span data-stu-id="aebfd-188">Contains information related to the media agent, including rendering quality.</span></span>          |
|<span data-ttu-id="aebfd-189">tscalling-0-2061129496. blog</span><span class="sxs-lookup"><span data-stu-id="aebfd-189">tscalling-0-2061129496.blog</span></span>   |<span data-ttu-id="aebfd-190">Registra eventos en la API de llamadas de TS.</span><span class="sxs-lookup"><span data-stu-id="aebfd-190">Records events in the ts-calling API.</span></span>       |

<a name="desktop-logs"></a><span data-ttu-id="aebfd-191">Registros de escritorio</span><span class="sxs-lookup"><span data-stu-id="aebfd-191">Desktop logs</span></span>
---------------------

<span data-ttu-id="aebfd-192">Los registros de escritorio, también conocidos como registros del programa previo, contienen datos de registro que se producen entre el cliente de escritorio y el explorador.</span><span class="sxs-lookup"><span data-stu-id="aebfd-192">Desktop logs, also known as bootstrapper logs, contain log data that occurs between the desktop client and the browser.</span></span> <span data-ttu-id="aebfd-193">Al igual que los registros de medios, estos registros solo son necesarios si lo solicita Microsoft.</span><span class="sxs-lookup"><span data-stu-id="aebfd-193">Like media logs, these logs are only needed if requested by Microsoft.</span></span> <span data-ttu-id="aebfd-194">Los registros se basan en texto y se pueden leer con cualquier editor basado en texto en un formato descendente.</span><span class="sxs-lookup"><span data-stu-id="aebfd-194">The logs are text based and can be read using any text-based editor in a top-down format.</span></span>

<span data-ttu-id="aebfd-195">Windows:</span><span class="sxs-lookup"><span data-stu-id="aebfd-195">Windows:</span></span>

 - <span data-ttu-id="aebfd-196">Haga clic con el botón derecho en el icono de **Microsoft Teams** de la bandeja del sistema y seleccione **obtener registros**.</span><span class="sxs-lookup"><span data-stu-id="aebfd-196">Right-click the **Microsoft Teams** icon in your system tray, and select **Get Logs**.</span></span>

<span data-ttu-id="aebfd-197">Mac OsX:</span><span class="sxs-lookup"><span data-stu-id="aebfd-197">Mac OsX:</span></span>

 - <span data-ttu-id="aebfd-198">Elija **obtener registros** en el menú desplegable **ayuda** .</span><span class="sxs-lookup"><span data-stu-id="aebfd-198">Choose **Get Logs** from the **Help** pull-down menu.</span></span>

<span data-ttu-id="aebfd-199">Linux</span><span class="sxs-lookup"><span data-stu-id="aebfd-199">Linux:</span></span>

 - <span data-ttu-id="aebfd-200">Haga clic en el icono de **Microsoft Teams** de la bandeja del sistema y seleccione **obtener registros**.</span><span class="sxs-lookup"><span data-stu-id="aebfd-200">Click on the **Microsoft Teams** icon in your system tray, and select **Get Logs**.</span></span>

|<span data-ttu-id="aebfd-201">Cliente</span><span class="sxs-lookup"><span data-stu-id="aebfd-201">Client</span></span> |<span data-ttu-id="aebfd-202">Ubicación</span><span class="sxs-lookup"><span data-stu-id="aebfd-202">Location</span></span> |
|---------|---------|
|<span data-ttu-id="aebfd-203">Windows</span><span class="sxs-lookup"><span data-stu-id="aebfd-203">Windows</span></span>     |<span data-ttu-id="aebfd-204">% appdata% \Microsoft\Teams\logs.txt</span><span class="sxs-lookup"><span data-stu-id="aebfd-204">%appdata%\Microsoft\Teams\logs.txt</span></span>         |
|<span data-ttu-id="aebfd-205">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="aebfd-205">Mac OSX</span></span>     |<span data-ttu-id="aebfd-206">~/Library/Application Support/Microsoft/Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="aebfd-206">~/Library/Application Support/Microsoft/Teams/logs.txt</span></span>         |
|<span data-ttu-id="aebfd-207">Linux</span><span class="sxs-lookup"><span data-stu-id="aebfd-207">Linux</span></span>       |<span data-ttu-id="aebfd-208">~/.config/Microsoft/Microsoft Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="aebfd-208">~/.config/Microsoft/Microsoft Teams/logs.txt</span></span>         |


## <a name="related-topics"></a><span data-ttu-id="aebfd-209">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="aebfd-209">Related topics</span></span>

[<span data-ttu-id="aebfd-210">Solución de problemas de Teams</span><span class="sxs-lookup"><span data-stu-id="aebfd-210">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
