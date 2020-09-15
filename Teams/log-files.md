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
ms.openlocfilehash: 468f0f67743f7cd0e11ff28e4484f70a71af3b64
ms.sourcegitcommit: 67c686810d37bffda72a6e92155d9c8ec86bfae6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "47766764"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a><span data-ttu-id="98d96-103">Usar los archivos de registro para solucionar problemas en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="98d96-103">Use log files in troubleshooting Microsoft Teams</span></span>
=================================================

<span data-ttu-id="98d96-104">Hay tres tipos de archivos de registro que el cliente genera automáticamente y que pueden usarse para ayudar en la solución de problemas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="98d96-104">There are three types of log files automatically produced by the client that can be leveraged to assist in troubleshooting Microsoft Teams.</span></span>

-   <span data-ttu-id="98d96-105">Registros de depuración</span><span class="sxs-lookup"><span data-stu-id="98d96-105">Debug logs</span></span>

-   <span data-ttu-id="98d96-106">Registros de medios</span><span class="sxs-lookup"><span data-stu-id="98d96-106">Media logs</span></span>

-   <span data-ttu-id="98d96-107">Registros de escritorio</span><span class="sxs-lookup"><span data-stu-id="98d96-107">Desktop logs</span></span>

<span data-ttu-id="98d96-p101">Cuando se crea una solicitud de soporte técnico con Soporte técnico de Microsoft, el ingeniero de soporte técnico necesitará los registros de depuración. Disponer de estos registros con antelación, antes de crear la solicitud de soporte técnico, permitirá a Microsoft empezar rápidamente a resolver el problema. Los registros de medios o de escritorio solo son necesarios si los solicita Microsoft.</span><span class="sxs-lookup"><span data-stu-id="98d96-p101">When creating a support request with Microsoft Support, the support engineer will require the debug logs. Having these logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem. Media or desktop logs are only required if requested by Microsoft.</span></span>

<span data-ttu-id="98d96-p102">En esta table se muestran los distintos clientes y sus registros asociados. Los archivos de registro se almacenan en ubicaciones específicas del cliente y el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="98d96-p102">The following table outlines the various clients, and their associated logs. Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="98d96-113">Cliente</span><span class="sxs-lookup"><span data-stu-id="98d96-113">Client</span></span> |<span data-ttu-id="98d96-114">Depuración</span><span class="sxs-lookup"><span data-stu-id="98d96-114">Debug</span></span>|<span data-ttu-id="98d96-115">Escritorio</span><span class="sxs-lookup"><span data-stu-id="98d96-115">Desktop</span></span>|<span data-ttu-id="98d96-116">Medios</span><span class="sxs-lookup"><span data-stu-id="98d96-116">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="98d96-117">Web</span><span class="sxs-lookup"><span data-stu-id="98d96-117">Web</span></span>    |<span data-ttu-id="98d96-118">X</span><span class="sxs-lookup"><span data-stu-id="98d96-118">X</span></span>         |-         |-         |
|<span data-ttu-id="98d96-119">Windows</span><span class="sxs-lookup"><span data-stu-id="98d96-119">Windows</span></span>     |<span data-ttu-id="98d96-120">X</span><span class="sxs-lookup"><span data-stu-id="98d96-120">X</span></span>         |<span data-ttu-id="98d96-121">X</span><span class="sxs-lookup"><span data-stu-id="98d96-121">X</span></span>         |<span data-ttu-id="98d96-122">X</span><span class="sxs-lookup"><span data-stu-id="98d96-122">X</span></span>         |
|<span data-ttu-id="98d96-123">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="98d96-123">Mac OSX</span></span>     |<span data-ttu-id="98d96-124">X</span><span class="sxs-lookup"><span data-stu-id="98d96-124">X</span></span>         |<span data-ttu-id="98d96-125">X</span><span class="sxs-lookup"><span data-stu-id="98d96-125">X</span></span>         |<span data-ttu-id="98d96-126">X</span><span class="sxs-lookup"><span data-stu-id="98d96-126">X</span></span>         |
|<span data-ttu-id="98d96-127">Linux</span><span class="sxs-lookup"><span data-stu-id="98d96-127">Linux</span></span>     |<span data-ttu-id="98d96-128">X</span><span class="sxs-lookup"><span data-stu-id="98d96-128">X</span></span>         |<span data-ttu-id="98d96-129">X</span><span class="sxs-lookup"><span data-stu-id="98d96-129">X</span></span>         |<span data-ttu-id="98d96-130">X</span><span class="sxs-lookup"><span data-stu-id="98d96-130">X</span></span>         |
|<span data-ttu-id="98d96-131">iOS</span><span class="sxs-lookup"><span data-stu-id="98d96-131">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="98d96-132">Android</span><span class="sxs-lookup"><span data-stu-id="98d96-132">Android</span></span>     |-         |-         |-         |

<span data-ttu-id="98d96-133">Para ver una lista completa de los sistemas operativos y los exploradores compatibles, vea [Obtener clientes para Microsoft Teams](get-clients.md).</span><span class="sxs-lookup"><span data-stu-id="98d96-133">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

<a name="debug-logs"></a><span data-ttu-id="98d96-134">Registros de depuración</span><span class="sxs-lookup"><span data-stu-id="98d96-134">Debug logs</span></span>
---------------------------

<span data-ttu-id="98d96-135">Estos son los registros más comunes y son necesarios para todos los casos de soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="98d96-135">These are the most common logs and are required for all Microsoft support cases.</span></span> <span data-ttu-id="98d96-136">Los registros de depuración los generan los clientes de escritorio de Windows y Mac, así como los clientes basados en explorador.</span><span class="sxs-lookup"><span data-stu-id="98d96-136">Debug logs are produced by the Windows and Mac desktop clients, as well as browser based clients.</span></span> <span data-ttu-id="98d96-137">Los registros se basan en texto y se leen de abajo hacia arriba.</span><span class="sxs-lookup"><span data-stu-id="98d96-137">The logs are text based and are read from the bottom up.</span></span> <span data-ttu-id="98d96-138">Se pueden leer con cualquier editor basado en texto y los nuevos registros se crean al iniciar sesión en el cliente.</span><span class="sxs-lookup"><span data-stu-id="98d96-138">They can be read using any text based editor and new logs are created when logging into the client.</span></span>

<span data-ttu-id="98d96-139">Los registros de depuración muestran los siguientes flujos de datos:</span><span class="sxs-lookup"><span data-stu-id="98d96-139">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="98d96-140">Inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="98d96-140">Login</span></span>

-   <span data-ttu-id="98d96-141">Solicitudes de conexión a servicios de nivel intermedio</span><span class="sxs-lookup"><span data-stu-id="98d96-141">Connection requests to middle tier services</span></span>

-   <span data-ttu-id="98d96-142">Llamada/conversación</span><span class="sxs-lookup"><span data-stu-id="98d96-142">Call/conversation</span></span>

<span data-ttu-id="98d96-143">Los registros de depuración se generan usando los siguientes métodos de SO específicos:</span><span class="sxs-lookup"><span data-stu-id="98d96-143">The debug logs are produced using the following OS specific methods:</span></span>

-   <span data-ttu-id="98d96-144">Windows:</span><span class="sxs-lookup"><span data-stu-id="98d96-144">Windows:</span></span>

      <span data-ttu-id="98d96-145">Método abreviado de teclado: Ctrl + Alt + Mayús + 1</span><span class="sxs-lookup"><span data-stu-id="98d96-145">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

-   <span data-ttu-id="98d96-146">Mac OSX:</span><span class="sxs-lookup"><span data-stu-id="98d96-146">Mac OSX:</span></span>

      <span data-ttu-id="98d96-147">Método abreviado de teclado: Opción + Comando + Mayús + 1</span><span class="sxs-lookup"><span data-stu-id="98d96-147">Keyboard shortcut: Option + Command + Shift+1</span></span>

-   <span data-ttu-id="98d96-148">Linux</span><span class="sxs-lookup"><span data-stu-id="98d96-148">Linux:</span></span>

      <span data-ttu-id="98d96-149">Método abreviado de teclado: Ctrl + Alt + Mayús + 1</span><span class="sxs-lookup"><span data-stu-id="98d96-149">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

<span data-ttu-id="98d96-150">Los registros de depuración se descargan automáticamente en las siguientes carpetas.</span><span class="sxs-lookup"><span data-stu-id="98d96-150">The debug logs are automatically downloaded to the following folders.</span></span>

-   <span data-ttu-id="98d96-151">Windows: %userprofile%\\Descargas</span><span class="sxs-lookup"><span data-stu-id="98d96-151">Windows: %userprofile%\\Downloads</span></span>

-   <span data-ttu-id="98d96-152">Mac OSX: ~/downloads</span><span class="sxs-lookup"><span data-stu-id="98d96-152">Mac OSX: ~/Downloads</span></span>

-   <span data-ttu-id="98d96-153">Linux: ~/downloads</span><span class="sxs-lookup"><span data-stu-id="98d96-153">Linux: ~/Downloads</span></span>

-   <span data-ttu-id="98d96-154">Explorador: Se le pedirá que guarde el registro de depuración en la ubicación predeterminada.</span><span class="sxs-lookup"><span data-stu-id="98d96-154">Browser: You will be prompted to save the debug log to default save location</span></span>

<a name="media-logs"></a><span data-ttu-id="98d96-155">Registros de medios</span><span class="sxs-lookup"><span data-stu-id="98d96-155">Media logs</span></span>
---------------------------

<span data-ttu-id="98d96-156">Los registros multimedia contienen datos de diagnóstico sobre el audio, el vídeo y la pantalla compartida en reuniones de Teams.</span><span class="sxs-lookup"><span data-stu-id="98d96-156">Media logs contain diagnostic data about audio, video, and screen sharing in Teams meetings.</span></span> <span data-ttu-id="98d96-157">Solo se necesitan para los casos de soporte técnico cuando se solicitan y solo Microsoft puede inspeccionarlas.</span><span class="sxs-lookup"><span data-stu-id="98d96-157">They are required for support cases only upon request and can only be inspected by Microsoft.</span></span> 

<span data-ttu-id="98d96-158">El registro multimedia está desactivado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="98d96-158">Media logging is turned off by default.</span></span> <span data-ttu-id="98d96-159">Para registrar los datos de diagnóstico de las reuniones de Teams, los usuarios deben activar la opción en el cliente de Teams.</span><span class="sxs-lookup"><span data-stu-id="98d96-159">To log diagnostic data for Teams meetings, users must turn on the option in the Teams client.</span></span> <span data-ttu-id="98d96-160">Vaya a **configuración**  >  **General**, active la casilla **Habilitar el registro de diagnóstico para la reunión (se debe reiniciar Teams**) y, a continuación, reinicie Teams.</span><span class="sxs-lookup"><span data-stu-id="98d96-160">Go to **Settings** > **General**, select the **Enable logging for meeting diagnostics (requires restarting Teams**) check box, and then restart Teams.</span></span>

<span data-ttu-id="98d96-161">En la tabla siguiente se describen las ubicaciones de registro.</span><span class="sxs-lookup"><span data-stu-id="98d96-161">The following table outlines the log locations.</span></span>

|<span data-ttu-id="98d96-162">Cliente</span><span class="sxs-lookup"><span data-stu-id="98d96-162">Client</span></span> |<span data-ttu-id="98d96-163">Ubicación</span><span class="sxs-lookup"><span data-stu-id="98d96-163">Location</span></span> |
|---------|---------|
|<span data-ttu-id="98d96-164">Windows</span><span class="sxs-lookup"><span data-stu-id="98d96-164">Windows</span></span>     |<span data-ttu-id="98d96-165">%appdata%\Microsoft\Teams\media-stack \\ \*. blog</span><span class="sxs-lookup"><span data-stu-id="98d96-165">%appdata%\Microsoft\Teams\media-stack\\*.blog</span></span>         |
|            |<span data-ttu-id="98d96-166">%appdata%\Microsoft\Teams\skylib \\ \*. blog</span><span class="sxs-lookup"><span data-stu-id="98d96-166">%appdata%\Microsoft\Teams\skylib\\*.blog</span></span>
|            |<span data-ttu-id="98d96-167">%appdata%\Microsoft\Teams\media-stack \\ \*. ETL</span><span class="sxs-lookup"><span data-stu-id="98d96-167">%appdata%\Microsoft\Teams\media-stack\\*.etl</span></span>         |
|<span data-ttu-id="98d96-168">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="98d96-168">Mac OSX</span></span>     |<span data-ttu-id="98d96-169">~/Library/Application Support/Microsoft/Teams/media-Stack/\*. blog</span><span class="sxs-lookup"><span data-stu-id="98d96-169">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="98d96-170">~/Library/Application Support/Microsoft/Teams/skylib/\*. blog</span><span class="sxs-lookup"><span data-stu-id="98d96-170">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span></span>         |
|<span data-ttu-id="98d96-171">Linux</span><span class="sxs-lookup"><span data-stu-id="98d96-171">Linux</span></span>       |<span data-ttu-id="98d96-172">~/.config/Microsoft/Microsoft Teams/media-Stack/\*. blog</span><span class="sxs-lookup"><span data-stu-id="98d96-172">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="98d96-173">~/.config/Microsoft/Microsoft Teams/skylib/\*. blog</span><span class="sxs-lookup"><span data-stu-id="98d96-173">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span></span>         |

<span data-ttu-id="98d96-174">Esta es una lista de los archivos de registro que se generan y la información que contienen.</span><span class="sxs-lookup"><span data-stu-id="98d96-174">Here's a list of the log files that are generated and the information they contain.</span></span>

|<span data-ttu-id="98d96-175">Nombre de archivo de registro</span><span class="sxs-lookup"><span data-stu-id="98d96-175">Log file name</span></span>  |<span data-ttu-id="98d96-176">Descripción</span><span class="sxs-lookup"><span data-stu-id="98d96-176">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="98d96-177">Teams. MSRTC-0-s1039525249. blog</span><span class="sxs-lookup"><span data-stu-id="98d96-177">Teams.msrtc-0-s1039525249.blog</span></span>     | <span data-ttu-id="98d96-178">Contiene información relacionada con la pila de medios.</span><span class="sxs-lookup"><span data-stu-id="98d96-178">Contains information related to the media stack.</span></span> <span data-ttu-id="98d96-179">Esto incluye el estado del canal, como la resolución, los descodificadores y los codificadores que se usan, así como el número de tramas enviadas y recibidas y el estado de sesión de pantalla compartida basada en vídeo y en vídeo (VBSS).</span><span class="sxs-lookup"><span data-stu-id="98d96-179">This includes channel status such as resolution, decoders and encoders used, and the number of frames sent and received, and camera and video-based screen sharing (VBSS) session status.</span></span>         |
|<span data-ttu-id="98d96-180">rtmcontrol. MSRTC-0-2415069487. blog</span><span class="sxs-lookup"><span data-stu-id="98d96-180">rtmcontrol.msrtc-0-2415069487.blog</span></span>      |<span data-ttu-id="98d96-181">Registra información relacionada con acciones de control remoto, como la marca de tiempo cuando se proporciona el control e información sobre el puntero del mouse.</span><span class="sxs-lookup"><span data-stu-id="98d96-181">Records information related to remote control actions, such as the time stamp when control is given, and mouse pointer information.</span></span>          |
|<span data-ttu-id="98d96-182">Teams_MediaStackETW -2-U-xr-U. ETL</span><span class="sxs-lookup"><span data-stu-id="98d96-182">Teams_MediaStackETW-2-U-xr-U.etl</span></span>      |<span data-ttu-id="98d96-183">Registra eventos de seguimiento de pila de medios.</span><span class="sxs-lookup"><span data-stu-id="98d96-183">Records media stack trace events.</span></span>         |
|<span data-ttu-id="98d96-184">Depurar: 0-s2790420889. blog</span><span class="sxs-lookup"><span data-stu-id="98d96-184">Debug-0-s2790420889.blog</span></span>    | <span data-ttu-id="98d96-185">Contiene información relacionada con el agente multimedia, incluida la calidad de representación.</span><span class="sxs-lookup"><span data-stu-id="98d96-185">Contains information related to the media agent, including rendering quality.</span></span>          |
|<span data-ttu-id="98d96-186">tscalling-0-2061129496. blog</span><span class="sxs-lookup"><span data-stu-id="98d96-186">tscalling-0-2061129496.blog</span></span>   |<span data-ttu-id="98d96-187">Registra eventos en la API de llamadas de TS.</span><span class="sxs-lookup"><span data-stu-id="98d96-187">Records events in the ts-calling API.</span></span>       |

<a name="desktop-logs"></a><span data-ttu-id="98d96-188">Registros de escritorio</span><span class="sxs-lookup"><span data-stu-id="98d96-188">Desktop logs</span></span>
---------------------

<span data-ttu-id="98d96-p107">Los registros de escritorio, también conocidos como registros de programa previo, contienen datos de registro que se producen entre el cliente de escritorio y el explorador. Al igual que los registros de medios, estos registros solo son necesarios si los solicita Microsoft. Los registros son archivos de texto y se pueden leer con cualquier editor de texto de arriba abajo.</span><span class="sxs-lookup"><span data-stu-id="98d96-p107">Desktop logs, also known as bootstrapper logs, contains log data that occurs between the desktop client and the browser. Like media logs, these logs are only needed if requested by Microsoft. The logs are text based and can be read using any text based editor in a top down format.</span></span>

<span data-ttu-id="98d96-192">Windows:</span><span class="sxs-lookup"><span data-stu-id="98d96-192">Windows:</span></span>

1.  <span data-ttu-id="98d96-193">Haga clic con el botón derecho en el icono de **Microsoft Teams** de la bandeja del sistema y seleccione **obtener registros** .</span><span class="sxs-lookup"><span data-stu-id="98d96-193">Right-click the **Microsoft Teams** icon in your system tray, select **Get Logs**</span></span>

<span data-ttu-id="98d96-194">Mac OsX:</span><span class="sxs-lookup"><span data-stu-id="98d96-194">Mac OsX:</span></span>

1.  <span data-ttu-id="98d96-195">Elija **Obtener registros** en el menú desplegabe **Ayuda**.</span><span class="sxs-lookup"><span data-stu-id="98d96-195">Choosing **Get Logs** from the **Help** pull-down menu</span></span>

<span data-ttu-id="98d96-196">Linux</span><span class="sxs-lookup"><span data-stu-id="98d96-196">Linux:</span></span>

1.  <span data-ttu-id="98d96-197">Haga clic en el icono de **Microsoft Teams** de la bandeja del sistema y seleccione **obtener registros** .</span><span class="sxs-lookup"><span data-stu-id="98d96-197">Click on the **Microsoft Teams** icon in your system tray, select **Get Logs**</span></span>

|<span data-ttu-id="98d96-198">Cliente</span><span class="sxs-lookup"><span data-stu-id="98d96-198">Client</span></span> |<span data-ttu-id="98d96-199">Ubicación</span><span class="sxs-lookup"><span data-stu-id="98d96-199">Location</span></span> |
|---------|---------|
|<span data-ttu-id="98d96-200">Windows</span><span class="sxs-lookup"><span data-stu-id="98d96-200">Windows</span></span>     |<span data-ttu-id="98d96-201">% appdata% \Microsoft\Teams\logs.txt</span><span class="sxs-lookup"><span data-stu-id="98d96-201">%appdata%\Microsoft\Teams\logs.txt</span></span>         |
|<span data-ttu-id="98d96-202">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="98d96-202">Mac OSX</span></span>     |<span data-ttu-id="98d96-203">~/Library/Application Support/Microsoft/Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="98d96-203">~/Library/Application Support/Microsoft/Teams/logs.txt</span></span>         |
|<span data-ttu-id="98d96-204">Linux</span><span class="sxs-lookup"><span data-stu-id="98d96-204">Linux</span></span>       |<span data-ttu-id="98d96-205">~/.config/Microsoft/Microsoft Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="98d96-205">~/.config/Microsoft/Microsoft Teams/logs.txt</span></span>         |


## <a name="related-topics"></a><span data-ttu-id="98d96-206">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="98d96-206">Related topics</span></span>

[<span data-ttu-id="98d96-207">Solución de problemas de Teams</span><span class="sxs-lookup"><span data-stu-id="98d96-207">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)

