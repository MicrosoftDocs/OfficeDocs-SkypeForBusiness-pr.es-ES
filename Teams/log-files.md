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
ms.openlocfilehash: 2ff24ddb8aaf63b539959119138aebf2f5d4e81f
ms.sourcegitcommit: 3a577c07b4f399c81d8650a2bba8cfc00b695b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2020
ms.locfileid: "48650833"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a><span data-ttu-id="1f273-103">Usar los archivos de registro para solucionar problemas en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1f273-103">Use log files in troubleshooting Microsoft Teams</span></span>
=================================================

<span data-ttu-id="1f273-104">Hay tres tipos de archivos de registro que el cliente genera automáticamente y que pueden usarse para ayudar en la solución de problemas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="1f273-104">There are three types of log files automatically produced by the client that can be leveraged to assist in troubleshooting Microsoft Teams.</span></span>

-   <span data-ttu-id="1f273-105">Registros de depuración</span><span class="sxs-lookup"><span data-stu-id="1f273-105">Debug logs</span></span>

-   <span data-ttu-id="1f273-106">Registros de medios</span><span class="sxs-lookup"><span data-stu-id="1f273-106">Media logs</span></span>

-   <span data-ttu-id="1f273-107">Registros de escritorio</span><span class="sxs-lookup"><span data-stu-id="1f273-107">Desktop logs</span></span>

<span data-ttu-id="1f273-p101">Cuando se crea una solicitud de soporte técnico con Soporte técnico de Microsoft, el ingeniero de soporte técnico necesitará los registros de depuración. Disponer de estos registros con antelación, antes de crear la solicitud de soporte técnico, permitirá a Microsoft empezar rápidamente a resolver el problema. Los registros de medios o de escritorio solo son necesarios si los solicita Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1f273-p101">When creating a support request with Microsoft Support, the support engineer will require the debug logs. Having these logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem. Media or desktop logs are only required if requested by Microsoft.</span></span>

<span data-ttu-id="1f273-p102">En esta table se muestran los distintos clientes y sus registros asociados. Los archivos de registro se almacenan en ubicaciones específicas del cliente y el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="1f273-p102">The following table outlines the various clients, and their associated logs. Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="1f273-113">Cliente</span><span class="sxs-lookup"><span data-stu-id="1f273-113">Client</span></span> |<span data-ttu-id="1f273-114">Depuración</span><span class="sxs-lookup"><span data-stu-id="1f273-114">Debug</span></span>|<span data-ttu-id="1f273-115">Escritorio</span><span class="sxs-lookup"><span data-stu-id="1f273-115">Desktop</span></span>|<span data-ttu-id="1f273-116">Medios</span><span class="sxs-lookup"><span data-stu-id="1f273-116">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="1f273-117">Web</span><span class="sxs-lookup"><span data-stu-id="1f273-117">Web</span></span>    |<span data-ttu-id="1f273-118">X</span><span class="sxs-lookup"><span data-stu-id="1f273-118">X</span></span>         |-         |-         |
|<span data-ttu-id="1f273-119">Windows</span><span class="sxs-lookup"><span data-stu-id="1f273-119">Windows</span></span>     |<span data-ttu-id="1f273-120">X</span><span class="sxs-lookup"><span data-stu-id="1f273-120">X</span></span>         |<span data-ttu-id="1f273-121">X</span><span class="sxs-lookup"><span data-stu-id="1f273-121">X</span></span>         |<span data-ttu-id="1f273-122">X</span><span class="sxs-lookup"><span data-stu-id="1f273-122">X</span></span>         |
|<span data-ttu-id="1f273-123">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="1f273-123">Mac OSX</span></span>     |<span data-ttu-id="1f273-124">X</span><span class="sxs-lookup"><span data-stu-id="1f273-124">X</span></span>         |<span data-ttu-id="1f273-125">X</span><span class="sxs-lookup"><span data-stu-id="1f273-125">X</span></span>         |<span data-ttu-id="1f273-126">X</span><span class="sxs-lookup"><span data-stu-id="1f273-126">X</span></span>         |
|<span data-ttu-id="1f273-127">Linux</span><span class="sxs-lookup"><span data-stu-id="1f273-127">Linux</span></span>     |<span data-ttu-id="1f273-128">X</span><span class="sxs-lookup"><span data-stu-id="1f273-128">X</span></span>         |<span data-ttu-id="1f273-129">X</span><span class="sxs-lookup"><span data-stu-id="1f273-129">X</span></span>         |<span data-ttu-id="1f273-130">X</span><span class="sxs-lookup"><span data-stu-id="1f273-130">X</span></span>         |
|<span data-ttu-id="1f273-131">iOS</span><span class="sxs-lookup"><span data-stu-id="1f273-131">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="1f273-132">Android</span><span class="sxs-lookup"><span data-stu-id="1f273-132">Android</span></span>     |-         |-         |-         |

<span data-ttu-id="1f273-133">Para ver una lista completa de los sistemas operativos y los exploradores compatibles, vea [Obtener clientes para Microsoft Teams](get-clients.md).</span><span class="sxs-lookup"><span data-stu-id="1f273-133">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

<a name="debug-logs"></a><span data-ttu-id="1f273-134">Registros de depuración</span><span class="sxs-lookup"><span data-stu-id="1f273-134">Debug logs</span></span>
---------------------------

<span data-ttu-id="1f273-135">Estos son los registros más comunes y son necesarios para todos los casos de soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1f273-135">These are the most common logs and are required for all Microsoft support cases.</span></span> <span data-ttu-id="1f273-136">Los registros de depuración los generan los clientes de escritorio de Windows y Mac, así como los clientes basados en explorador.</span><span class="sxs-lookup"><span data-stu-id="1f273-136">Debug logs are produced by the Windows and Mac desktop clients, as well as browser based clients.</span></span> <span data-ttu-id="1f273-137">Los registros se basan en texto y se leen de abajo hacia arriba.</span><span class="sxs-lookup"><span data-stu-id="1f273-137">The logs are text based and are read from the bottom up.</span></span> <span data-ttu-id="1f273-138">Se pueden leer con cualquier editor basado en texto y los nuevos registros se crean al iniciar sesión en el cliente.</span><span class="sxs-lookup"><span data-stu-id="1f273-138">They can be read using any text based editor and new logs are created when logging into the client.</span></span>

<span data-ttu-id="1f273-139">Los registros de depuración muestran los siguientes flujos de datos:</span><span class="sxs-lookup"><span data-stu-id="1f273-139">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="1f273-140">Inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="1f273-140">Login</span></span>

-   <span data-ttu-id="1f273-141">Solicitudes de conexión a servicios de nivel intermedio</span><span class="sxs-lookup"><span data-stu-id="1f273-141">Connection requests to middle tier services</span></span>

-   <span data-ttu-id="1f273-142">Llamada/conversación</span><span class="sxs-lookup"><span data-stu-id="1f273-142">Call/conversation</span></span>

<span data-ttu-id="1f273-143">Los registros de depuración se generan usando los siguientes métodos de SO específicos:</span><span class="sxs-lookup"><span data-stu-id="1f273-143">The debug logs are produced using the following OS specific methods:</span></span>

-   <span data-ttu-id="1f273-144">Windows:</span><span class="sxs-lookup"><span data-stu-id="1f273-144">Windows:</span></span>

      <span data-ttu-id="1f273-145">Método abreviado de teclado: Ctrl + Alt + Mayús + 1</span><span class="sxs-lookup"><span data-stu-id="1f273-145">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

-   <span data-ttu-id="1f273-146">Mac OSX:</span><span class="sxs-lookup"><span data-stu-id="1f273-146">Mac OSX:</span></span>

      <span data-ttu-id="1f273-147">Método abreviado de teclado: Opción + Comando + Mayús + 1</span><span class="sxs-lookup"><span data-stu-id="1f273-147">Keyboard shortcut: Option + Command + Shift+1</span></span>

-   <span data-ttu-id="1f273-148">Linux</span><span class="sxs-lookup"><span data-stu-id="1f273-148">Linux:</span></span>

      <span data-ttu-id="1f273-149">Método abreviado de teclado: Ctrl + Alt + Mayús + 1</span><span class="sxs-lookup"><span data-stu-id="1f273-149">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

<span data-ttu-id="1f273-150">Los registros de depuración se descargan automáticamente en las siguientes carpetas.</span><span class="sxs-lookup"><span data-stu-id="1f273-150">The debug logs are automatically downloaded to the following folders.</span></span>

-   <span data-ttu-id="1f273-151">Windows: %userprofile%\\Descargas</span><span class="sxs-lookup"><span data-stu-id="1f273-151">Windows: %userprofile%\\Downloads</span></span>

-   <span data-ttu-id="1f273-152">Mac OSX: ~/downloads</span><span class="sxs-lookup"><span data-stu-id="1f273-152">Mac OSX: ~/Downloads</span></span>

-   <span data-ttu-id="1f273-153">Linux: ~/downloads</span><span class="sxs-lookup"><span data-stu-id="1f273-153">Linux: ~/Downloads</span></span>

-   <span data-ttu-id="1f273-154">Explorador: Se le pedirá que guarde el registro de depuración en la ubicación predeterminada.</span><span class="sxs-lookup"><span data-stu-id="1f273-154">Browser: You will be prompted to save the debug log to default save location</span></span>

<a name="media-logs"></a><span data-ttu-id="1f273-155">Registros de medios</span><span class="sxs-lookup"><span data-stu-id="1f273-155">Media logs</span></span>
---------------------------

<span data-ttu-id="1f273-156">Los registros multimedia contienen datos de diagnóstico sobre el audio, el vídeo y la pantalla compartida en reuniones de Teams.</span><span class="sxs-lookup"><span data-stu-id="1f273-156">Media logs contain diagnostic data about audio, video, and screen sharing in Teams meetings.</span></span> <span data-ttu-id="1f273-157">Son necesarios para los casos de soporte técnico que están vinculados a problemas relacionados con la llamada.</span><span class="sxs-lookup"><span data-stu-id="1f273-157">They are required for support cases that are linked to call-related issues.</span></span>

<span data-ttu-id="1f273-158">El registro multimedia está desactivado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="1f273-158">Media logging is turned off by default.</span></span> <span data-ttu-id="1f273-159">Para registrar los datos de diagnóstico de las reuniones de Teams, los usuarios deben activar la opción en el cliente de Teams.</span><span class="sxs-lookup"><span data-stu-id="1f273-159">To log diagnostic data for Teams meetings, users must turn on the option in the Teams client.</span></span> <span data-ttu-id="1f273-160">Vaya a **configuración**  >  **General**, active la casilla **Habilitar el registro de diagnósticos de reunión (debe reiniciar Teams**) y, a continuación, reinicie Teams y reproduzca el problema.</span><span class="sxs-lookup"><span data-stu-id="1f273-160">Go to **Settings** > **General**, select the **Enable logging for meeting diagnostics (requires restarting Teams**) check box, and then restart Teams and reproduce the issue.</span></span> 

<span data-ttu-id="1f273-161">En la tabla siguiente se describen las ubicaciones de los registros de medios.</span><span class="sxs-lookup"><span data-stu-id="1f273-161">The following table outlines the media log locations.</span></span> <span data-ttu-id="1f273-162">Cuando envíe los archivos de registro al soporte técnico de Microsoft, Compruebe la marca de tiempo de los archivos de registro para asegurarse de que los registros cubren el intervalo de tiempo cuando reproducido el problema.</span><span class="sxs-lookup"><span data-stu-id="1f273-162">When you send the log files to Microsoft support, please verify the timestamp of the log files to make sure the logs cover the time frame when you reproduced the issue.</span></span>

|<span data-ttu-id="1f273-163">Cliente</span><span class="sxs-lookup"><span data-stu-id="1f273-163">Client</span></span> |<span data-ttu-id="1f273-164">Ubicación</span><span class="sxs-lookup"><span data-stu-id="1f273-164">Location</span></span> |
|---------|---------|
|<span data-ttu-id="1f273-165">Windows</span><span class="sxs-lookup"><span data-stu-id="1f273-165">Windows</span></span>     |<span data-ttu-id="1f273-166">%appdata%\Microsoft\Teams\media-stack \\ \*. blog</span><span class="sxs-lookup"><span data-stu-id="1f273-166">%appdata%\Microsoft\Teams\media-stack\\*.blog</span></span>         |
|            |<span data-ttu-id="1f273-167">%appdata%\Microsoft\Teams\skylib \\ \*. blog</span><span class="sxs-lookup"><span data-stu-id="1f273-167">%appdata%\Microsoft\Teams\skylib\\*.blog</span></span>
|            |<span data-ttu-id="1f273-168">%appdata%\Microsoft\Teams\media-stack \\ \*. ETL</span><span class="sxs-lookup"><span data-stu-id="1f273-168">%appdata%\Microsoft\Teams\media-stack\\*.etl</span></span>         |
|<span data-ttu-id="1f273-169">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="1f273-169">Mac OSX</span></span>     |<span data-ttu-id="1f273-170">~/Library/Application Support/Microsoft/Teams/media-Stack/\*. blog</span><span class="sxs-lookup"><span data-stu-id="1f273-170">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="1f273-171">~/Library/Application Support/Microsoft/Teams/skylib/\*. blog</span><span class="sxs-lookup"><span data-stu-id="1f273-171">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span></span>         |
|<span data-ttu-id="1f273-172">Linux</span><span class="sxs-lookup"><span data-stu-id="1f273-172">Linux</span></span>       |<span data-ttu-id="1f273-173">~/.config/Microsoft/Microsoft Teams/media-Stack/\*. blog</span><span class="sxs-lookup"><span data-stu-id="1f273-173">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="1f273-174">~/.config/Microsoft/Microsoft Teams/skylib/\*. blog</span><span class="sxs-lookup"><span data-stu-id="1f273-174">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span></span>         |

<span data-ttu-id="1f273-175">Esta es una lista de los archivos de registro que se generan y la información que contienen.</span><span class="sxs-lookup"><span data-stu-id="1f273-175">Here's a list of the log files that are generated and the information they contain.</span></span>

|<span data-ttu-id="1f273-176">Nombre de archivo de registro</span><span class="sxs-lookup"><span data-stu-id="1f273-176">Log file name</span></span>  |<span data-ttu-id="1f273-177">Descripción</span><span class="sxs-lookup"><span data-stu-id="1f273-177">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="1f273-178">Teams. MSRTC-0-s1039525249. blog</span><span class="sxs-lookup"><span data-stu-id="1f273-178">Teams.msrtc-0-s1039525249.blog</span></span>     | <span data-ttu-id="1f273-179">Contiene información relacionada con la pila de medios.</span><span class="sxs-lookup"><span data-stu-id="1f273-179">Contains information related to the media stack.</span></span> <span data-ttu-id="1f273-180">Esto incluye el estado del canal, como la resolución, los descodificadores y los codificadores que se usan, así como el número de tramas enviadas y recibidas y el estado de sesión de pantalla compartida basada en vídeo y en vídeo (VBSS).</span><span class="sxs-lookup"><span data-stu-id="1f273-180">This includes channel status such as resolution, decoders and encoders used, and the number of frames sent and received, and camera and video-based screen sharing (VBSS) session status.</span></span>         |
|<span data-ttu-id="1f273-181">rtmcontrol. MSRTC-0-2415069487. blog</span><span class="sxs-lookup"><span data-stu-id="1f273-181">rtmcontrol.msrtc-0-2415069487.blog</span></span>      |<span data-ttu-id="1f273-182">Registra información relacionada con acciones de control remoto, como la marca de tiempo cuando se proporciona el control e información sobre el puntero del mouse.</span><span class="sxs-lookup"><span data-stu-id="1f273-182">Records information related to remote control actions, such as the time stamp when control is given, and mouse pointer information.</span></span>          |
|<span data-ttu-id="1f273-183">Teams_MediaStackETW -2-U-xr-U. ETL</span><span class="sxs-lookup"><span data-stu-id="1f273-183">Teams_MediaStackETW-2-U-xr-U.etl</span></span>      |<span data-ttu-id="1f273-184">Registra eventos de seguimiento de pila de medios.</span><span class="sxs-lookup"><span data-stu-id="1f273-184">Records media stack trace events.</span></span>         |
|<span data-ttu-id="1f273-185">Depurar: 0-s2790420889. blog</span><span class="sxs-lookup"><span data-stu-id="1f273-185">Debug-0-s2790420889.blog</span></span>    | <span data-ttu-id="1f273-186">Contiene información relacionada con el agente multimedia, incluida la calidad de representación.</span><span class="sxs-lookup"><span data-stu-id="1f273-186">Contains information related to the media agent, including rendering quality.</span></span>          |
|<span data-ttu-id="1f273-187">tscalling-0-2061129496. blog</span><span class="sxs-lookup"><span data-stu-id="1f273-187">tscalling-0-2061129496.blog</span></span>   |<span data-ttu-id="1f273-188">Registra eventos en la API de llamadas de TS.</span><span class="sxs-lookup"><span data-stu-id="1f273-188">Records events in the ts-calling API.</span></span>       |

<a name="desktop-logs"></a><span data-ttu-id="1f273-189">Registros de escritorio</span><span class="sxs-lookup"><span data-stu-id="1f273-189">Desktop logs</span></span>
---------------------

<span data-ttu-id="1f273-p108">Los registros de escritorio, también conocidos como registros de programa previo, contienen datos de registro que se producen entre el cliente de escritorio y el explorador. Al igual que los registros de medios, estos registros solo son necesarios si los solicita Microsoft. Los registros son archivos de texto y se pueden leer con cualquier editor de texto de arriba abajo.</span><span class="sxs-lookup"><span data-stu-id="1f273-p108">Desktop logs, also known as bootstrapper logs, contains log data that occurs between the desktop client and the browser. Like media logs, these logs are only needed if requested by Microsoft. The logs are text based and can be read using any text based editor in a top down format.</span></span>

<span data-ttu-id="1f273-193">Windows:</span><span class="sxs-lookup"><span data-stu-id="1f273-193">Windows:</span></span>

1.  <span data-ttu-id="1f273-194">Haga clic con el botón derecho en el icono de **Microsoft Teams** de la bandeja del sistema y seleccione **obtener registros** .</span><span class="sxs-lookup"><span data-stu-id="1f273-194">Right-click the **Microsoft Teams** icon in your system tray, select **Get Logs**</span></span>

<span data-ttu-id="1f273-195">Mac OsX:</span><span class="sxs-lookup"><span data-stu-id="1f273-195">Mac OsX:</span></span>

1.  <span data-ttu-id="1f273-196">Elija **Obtener registros** en el menú desplegabe **Ayuda**.</span><span class="sxs-lookup"><span data-stu-id="1f273-196">Choosing **Get Logs** from the **Help** pull-down menu</span></span>

<span data-ttu-id="1f273-197">Linux</span><span class="sxs-lookup"><span data-stu-id="1f273-197">Linux:</span></span>

1.  <span data-ttu-id="1f273-198">Haga clic en el icono de **Microsoft Teams** de la bandeja del sistema y seleccione **obtener registros** .</span><span class="sxs-lookup"><span data-stu-id="1f273-198">Click on the **Microsoft Teams** icon in your system tray, select **Get Logs**</span></span>

|<span data-ttu-id="1f273-199">Cliente</span><span class="sxs-lookup"><span data-stu-id="1f273-199">Client</span></span> |<span data-ttu-id="1f273-200">Ubicación</span><span class="sxs-lookup"><span data-stu-id="1f273-200">Location</span></span> |
|---------|---------|
|<span data-ttu-id="1f273-201">Windows</span><span class="sxs-lookup"><span data-stu-id="1f273-201">Windows</span></span>     |<span data-ttu-id="1f273-202">% appdata% \Microsoft\Teams\logs.txt</span><span class="sxs-lookup"><span data-stu-id="1f273-202">%appdata%\Microsoft\Teams\logs.txt</span></span>         |
|<span data-ttu-id="1f273-203">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="1f273-203">Mac OSX</span></span>     |<span data-ttu-id="1f273-204">~/Library/Application Support/Microsoft/Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="1f273-204">~/Library/Application Support/Microsoft/Teams/logs.txt</span></span>         |
|<span data-ttu-id="1f273-205">Linux</span><span class="sxs-lookup"><span data-stu-id="1f273-205">Linux</span></span>       |<span data-ttu-id="1f273-206">~/.config/Microsoft/Microsoft Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="1f273-206">~/.config/Microsoft/Microsoft Teams/logs.txt</span></span>         |


## <a name="related-topics"></a><span data-ttu-id="1f273-207">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="1f273-207">Related topics</span></span>

[<span data-ttu-id="1f273-208">Solución de problemas de Teams</span><span class="sxs-lookup"><span data-stu-id="1f273-208">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
