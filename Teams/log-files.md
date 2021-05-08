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
ms.openlocfilehash: f816830f24a3d1180cb33a91a3f02d30d360cfef
ms.sourcegitcommit: 2c2176b9d32b8f7218e8d11e82c0ae01318bfdc5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2021
ms.locfileid: "52264880"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a><span data-ttu-id="5cec4-103">Usar los archivos de registro para solucionar problemas en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5cec4-103">Use log files in troubleshooting Microsoft Teams</span></span>
=================================================

<span data-ttu-id="5cec4-104">Hay tres tipos de archivos de registro generados automáticamente por el cliente, que se pueden aprovechar para ayudar a solucionar problemas de Microsoft Teams:</span><span class="sxs-lookup"><span data-stu-id="5cec4-104">There are three types of log files automatically produced by the client, which can be leveraged to assist in troubleshooting Microsoft Teams:</span></span>

-   <span data-ttu-id="5cec4-105">Registros de depuración</span><span class="sxs-lookup"><span data-stu-id="5cec4-105">Debug logs</span></span>

-   <span data-ttu-id="5cec4-106">Registros de medios</span><span class="sxs-lookup"><span data-stu-id="5cec4-106">Media logs</span></span>

-   <span data-ttu-id="5cec4-107">Registros de escritorio</span><span class="sxs-lookup"><span data-stu-id="5cec4-107">Desktop logs</span></span>

<span data-ttu-id="5cec4-108">Al crear una solicitud de soporte técnico con soporte técnico de Microsoft, el ingeniero de soporte técnico necesitará los registros de depuración.</span><span class="sxs-lookup"><span data-stu-id="5cec4-108">When creating a support request with Microsoft Support, the support engineer will require the debug logs.</span></span> <span data-ttu-id="5cec4-109">Tener los registros de depuración a mano antes de crear la solicitud de soporte técnico permitirá a Microsoft empezar rápidamente a solucionar el problema.</span><span class="sxs-lookup"><span data-stu-id="5cec4-109">Having the debug logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem.</span></span> <span data-ttu-id="5cec4-110">**Los registros** multimedia **o de** escritorio solo son necesarios si Microsoft lo solicita.</span><span class="sxs-lookup"><span data-stu-id="5cec4-110">**Media** or **Desktop** logs are only required if requested by Microsoft.</span></span>

> [!NOTE]
> <span data-ttu-id="5cec4-111">En este artículo, el término **Registros de depuración** hace referencia a los registros que se usan para la solución de problemas.</span><span class="sxs-lookup"><span data-stu-id="5cec4-111">In this article, the term **Debug logs** refers to the logs that are used for troubleshooting.</span></span> <span data-ttu-id="5cec4-112">Sin embargo, los archivos que se generan para estos registros contendrán el término registros **de diagnóstico** en sus nombres.</span><span class="sxs-lookup"><span data-stu-id="5cec4-112">However, the files that are generated for these logs will contain the term **diagnostic logs** in their names.</span></span>  

<span data-ttu-id="5cec4-113">En la tabla siguiente se describen los distintos clientes y sus registros asociados.</span><span class="sxs-lookup"><span data-stu-id="5cec4-113">The following table outlines the various clients and their associated logs.</span></span> <span data-ttu-id="5cec4-114">Los archivos de registro se almacenan en ubicaciones específicas del cliente y del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="5cec4-114">Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="5cec4-115">Cliente</span><span class="sxs-lookup"><span data-stu-id="5cec4-115">Client</span></span> |<span data-ttu-id="5cec4-116">Depuración</span><span class="sxs-lookup"><span data-stu-id="5cec4-116">Debug</span></span>|<span data-ttu-id="5cec4-117">Escritorio</span><span class="sxs-lookup"><span data-stu-id="5cec4-117">Desktop</span></span>|<span data-ttu-id="5cec4-118">Medios</span><span class="sxs-lookup"><span data-stu-id="5cec4-118">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="5cec4-119">Web</span><span class="sxs-lookup"><span data-stu-id="5cec4-119">Web</span></span>    |<span data-ttu-id="5cec4-120">X</span><span class="sxs-lookup"><span data-stu-id="5cec4-120">X</span></span>         |-         |-         |
|<span data-ttu-id="5cec4-121">Windows</span><span class="sxs-lookup"><span data-stu-id="5cec4-121">Windows</span></span>     |<span data-ttu-id="5cec4-122">X</span><span class="sxs-lookup"><span data-stu-id="5cec4-122">X</span></span>         |<span data-ttu-id="5cec4-123">X</span><span class="sxs-lookup"><span data-stu-id="5cec4-123">X</span></span>         |<span data-ttu-id="5cec4-124">X</span><span class="sxs-lookup"><span data-stu-id="5cec4-124">X</span></span>         |
|<span data-ttu-id="5cec4-125">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="5cec4-125">Mac OSX</span></span>     |<span data-ttu-id="5cec4-126">X</span><span class="sxs-lookup"><span data-stu-id="5cec4-126">X</span></span>         |<span data-ttu-id="5cec4-127">X</span><span class="sxs-lookup"><span data-stu-id="5cec4-127">X</span></span>         |<span data-ttu-id="5cec4-128">X</span><span class="sxs-lookup"><span data-stu-id="5cec4-128">X</span></span>         |
|<span data-ttu-id="5cec4-129">Linux</span><span class="sxs-lookup"><span data-stu-id="5cec4-129">Linux</span></span>     |<span data-ttu-id="5cec4-130">X</span><span class="sxs-lookup"><span data-stu-id="5cec4-130">X</span></span>         |<span data-ttu-id="5cec4-131">X</span><span class="sxs-lookup"><span data-stu-id="5cec4-131">X</span></span>         |<span data-ttu-id="5cec4-132">X</span><span class="sxs-lookup"><span data-stu-id="5cec4-132">X</span></span>         |
|<span data-ttu-id="5cec4-133">iOS</span><span class="sxs-lookup"><span data-stu-id="5cec4-133">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="5cec4-134">Android</span><span class="sxs-lookup"><span data-stu-id="5cec4-134">Android</span></span>     |-         |-         |-         |

<span data-ttu-id="5cec4-135">Para ver una lista completa de los sistemas operativos y los exploradores compatibles, vea [Obtener clientes para Microsoft Teams](get-clients.md).</span><span class="sxs-lookup"><span data-stu-id="5cec4-135">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

<a name="debug-logs"></a><span data-ttu-id="5cec4-136">Registros de depuración</span><span class="sxs-lookup"><span data-stu-id="5cec4-136">Debug logs</span></span>
---------------------------

<span data-ttu-id="5cec4-137">Estos son los registros más comunes y son necesarios para todos los casos de soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5cec4-137">These are the most common logs and are required for all Microsoft support cases.</span></span> <span data-ttu-id="5cec4-138">Los registros de depuración son producidos por Windows y mac clientes de escritorio, así como por clientes basados en explorador.</span><span class="sxs-lookup"><span data-stu-id="5cec4-138">Debug logs are produced by the Windows and Mac desktop clients, as well as by browser-based clients.</span></span> <span data-ttu-id="5cec4-139">Los registros se basan en texto y se leen desde abajo hacia arriba.</span><span class="sxs-lookup"><span data-stu-id="5cec4-139">The logs are text based and are read from the bottom-up.</span></span> <span data-ttu-id="5cec4-140">Se pueden leer con cualquier editor basado en texto y se crean nuevos registros al iniciar sesión en el cliente.</span><span class="sxs-lookup"><span data-stu-id="5cec4-140">They can be read using any text-based editor, and new logs are created when logging into the client.</span></span>

<span data-ttu-id="5cec4-141">Los registros de depuración muestran los siguientes flujos de datos:</span><span class="sxs-lookup"><span data-stu-id="5cec4-141">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="5cec4-142">Inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="5cec4-142">Login</span></span>

-   <span data-ttu-id="5cec4-143">Solicitudes de conexión a servicios de nivel medio</span><span class="sxs-lookup"><span data-stu-id="5cec4-143">Connection requests to middle-tier services</span></span>

-   <span data-ttu-id="5cec4-144">Llamada/conversación</span><span class="sxs-lookup"><span data-stu-id="5cec4-144">Call/conversation</span></span>

<span data-ttu-id="5cec4-145">Los registros de depuración se generan con los siguientes métodos específicos del sistema operativo:</span><span class="sxs-lookup"><span data-stu-id="5cec4-145">The debug logs are produced using the following OS-specific methods:</span></span>

-   <span data-ttu-id="5cec4-146">Windows:</span><span class="sxs-lookup"><span data-stu-id="5cec4-146">Windows:</span></span>

      <span data-ttu-id="5cec4-147">Método abreviado de teclado: Ctrl + Alt + Mayús + 1</span><span class="sxs-lookup"><span data-stu-id="5cec4-147">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

-   <span data-ttu-id="5cec4-148">Mac OSX:</span><span class="sxs-lookup"><span data-stu-id="5cec4-148">Mac OSX:</span></span>

      <span data-ttu-id="5cec4-149">Método abreviado de teclado: Opción + Comando + Mayús + 1</span><span class="sxs-lookup"><span data-stu-id="5cec4-149">Keyboard shortcut: Option + Command + Shift+1</span></span>

-   <span data-ttu-id="5cec4-150">Linux:</span><span class="sxs-lookup"><span data-stu-id="5cec4-150">Linux:</span></span>

      <span data-ttu-id="5cec4-151">Método abreviado de teclado: Ctrl + Alt + Mayús + 1</span><span class="sxs-lookup"><span data-stu-id="5cec4-151">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

<span data-ttu-id="5cec4-152">Los registros de depuración se descargan automáticamente en las siguientes carpetas:</span><span class="sxs-lookup"><span data-stu-id="5cec4-152">The debug logs are automatically downloaded to the following folders:</span></span>

-   <span data-ttu-id="5cec4-153">Windows: %userprofile%\\Descargas</span><span class="sxs-lookup"><span data-stu-id="5cec4-153">Windows: %userprofile%\\Downloads</span></span>

-   <span data-ttu-id="5cec4-154">Mac OSX: ~/Descargas</span><span class="sxs-lookup"><span data-stu-id="5cec4-154">Mac OSX: ~/Downloads</span></span>

-   <span data-ttu-id="5cec4-155">Linux: ~/Descargas</span><span class="sxs-lookup"><span data-stu-id="5cec4-155">Linux: ~/Downloads</span></span>

-   <span data-ttu-id="5cec4-156">Explorador: Se le pedirá que guarde el registro de depuración en la ubicación predeterminada.</span><span class="sxs-lookup"><span data-stu-id="5cec4-156">Browser: You will be prompted to save the debug log to default save location</span></span>

<a name="media-logs"></a><span data-ttu-id="5cec4-157">Registros de medios</span><span class="sxs-lookup"><span data-stu-id="5cec4-157">Media logs</span></span>
---------------------------

<span data-ttu-id="5cec4-158">Los registros multimedia contienen datos de diagnóstico sobre audio, vídeo y uso compartido de pantalla en Teams reuniones.</span><span class="sxs-lookup"><span data-stu-id="5cec4-158">Media logs contain diagnostic data about audio, video, and screen sharing in Teams meetings.</span></span> <span data-ttu-id="5cec4-159">Son necesarios para los casos de soporte técnico vinculados a problemas relacionados con llamadas.</span><span class="sxs-lookup"><span data-stu-id="5cec4-159">They are required for support cases that are linked to call-related issues.</span></span>

<span data-ttu-id="5cec4-160">El registro multimedia está desactivado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="5cec4-160">Media logging is turned off by default.</span></span> <span data-ttu-id="5cec4-161">Para registrar datos de diagnóstico Teams reuniones, los usuarios deben activar la opción en el Teams cliente.</span><span class="sxs-lookup"><span data-stu-id="5cec4-161">To log diagnostic data for Teams meetings, users must turn on the option in the Teams client.</span></span> <span data-ttu-id="5cec4-162">Vaya **a Configuración** General , active la casilla Habilitar registro para diagnósticos de reuniones (requiere reiniciar Teams), reinicie Teams y  >  reproduzca el problema.</span><span class="sxs-lookup"><span data-stu-id="5cec4-162">Go to **Settings** > **General**, select the **Enable logging for meeting diagnostics (requires restarting Teams**) check box, restart Teams, and reproduce the issue.</span></span> 

<span data-ttu-id="5cec4-163">En la tabla siguiente se describen las ubicaciones de registro multimedia.</span><span class="sxs-lookup"><span data-stu-id="5cec4-163">The following table outlines the media log locations.</span></span> <span data-ttu-id="5cec4-164">Cuando envíe los archivos de registro al soporte técnico de Microsoft, compruebe la marca de tiempo de los archivos de registro para asegurarse de que los registros cubren el período de tiempo cuando reproduzca el problema.</span><span class="sxs-lookup"><span data-stu-id="5cec4-164">When you send the log files to Microsoft support, please verify the timestamp of the log files to ensure the logs cover the time frame when you reproduced the issue.</span></span>

|<span data-ttu-id="5cec4-165">Cliente</span><span class="sxs-lookup"><span data-stu-id="5cec4-165">Client</span></span> |<span data-ttu-id="5cec4-166">Ubicación</span><span class="sxs-lookup"><span data-stu-id="5cec4-166">Location</span></span> |
|---------|---------|
|<span data-ttu-id="5cec4-167">Windows</span><span class="sxs-lookup"><span data-stu-id="5cec4-167">Windows</span></span>     |<span data-ttu-id="5cec4-168">%appdata%\Microsoft\Teams\media-stack \\ \*.blog</span><span class="sxs-lookup"><span data-stu-id="5cec4-168">%appdata%\Microsoft\Teams\media-stack\\*.blog</span></span>         |
|            |<span data-ttu-id="5cec4-169">%appdata%\Microsoft\Teams\skylib \\ \*.blog</span><span class="sxs-lookup"><span data-stu-id="5cec4-169">%appdata%\Microsoft\Teams\skylib\\*.blog</span></span>
|            |<span data-ttu-id="5cec4-170">%appdata%\Microsoft\Teams\media-stack \\ \*.etl</span><span class="sxs-lookup"><span data-stu-id="5cec4-170">%appdata%\Microsoft\Teams\media-stack\\*.etl</span></span>         |
|<span data-ttu-id="5cec4-171">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="5cec4-171">Mac OSX</span></span>     |<span data-ttu-id="5cec4-172">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span><span class="sxs-lookup"><span data-stu-id="5cec4-172">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="5cec4-173">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span><span class="sxs-lookup"><span data-stu-id="5cec4-173">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span></span>         |
|<span data-ttu-id="5cec4-174">Linux</span><span class="sxs-lookup"><span data-stu-id="5cec4-174">Linux</span></span>       |<span data-ttu-id="5cec4-175">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span><span class="sxs-lookup"><span data-stu-id="5cec4-175">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="5cec4-176">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span><span class="sxs-lookup"><span data-stu-id="5cec4-176">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span></span>         |

<span data-ttu-id="5cec4-177">Esta es una lista de los archivos de registro que se generan y la información que contienen.</span><span class="sxs-lookup"><span data-stu-id="5cec4-177">Here's a list of the log files that are generated and the information they contain.</span></span>

|<span data-ttu-id="5cec4-178">Nombre de archivo de registro</span><span class="sxs-lookup"><span data-stu-id="5cec4-178">Log file name</span></span>  |<span data-ttu-id="5cec4-179">Descripción</span><span class="sxs-lookup"><span data-stu-id="5cec4-179">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="5cec4-180">Teams.msrtc-0-s1039525249.blog</span><span class="sxs-lookup"><span data-stu-id="5cec4-180">Teams.msrtc-0-s1039525249.blog</span></span>     | <span data-ttu-id="5cec4-181">Contiene información relacionada con la pila de elementos multimedia.</span><span class="sxs-lookup"><span data-stu-id="5cec4-181">Contains information related to the media stack.</span></span> <span data-ttu-id="5cec4-182">Esto incluye el estado del canal, como la resolución, los descodificadores y los codificadores usados, así como el número de fotogramas enviados y recibidos, y el estado de la sesión de uso compartido de pantalla basado en cámaras y vídeo (VBSS).</span><span class="sxs-lookup"><span data-stu-id="5cec4-182">This includes channel status such as resolution, decoders and encoders used, and the number of frames sent and received, and camera and video-based screen sharing (VBSS) session status.</span></span>         |
|<span data-ttu-id="5cec4-183">rtmcontrol.msrtc-0-2415069487.blog</span><span class="sxs-lookup"><span data-stu-id="5cec4-183">rtmcontrol.msrtc-0-2415069487.blog</span></span>      |<span data-ttu-id="5cec4-184">Registra información relacionada con acciones de control remoto, como la marca de tiempo cuando se proporciona el control e información del puntero del mouse.</span><span class="sxs-lookup"><span data-stu-id="5cec4-184">Records information related to remote control actions, such as the time stamp when control is given, and mouse pointer information.</span></span>          |
|<span data-ttu-id="5cec4-185">Teams_MediaStackETW-2-U-xr-U.etl</span><span class="sxs-lookup"><span data-stu-id="5cec4-185">Teams_MediaStackETW-2-U-xr-U.etl</span></span>      |<span data-ttu-id="5cec4-186">Registros de eventos de seguimiento de la pila de medios.</span><span class="sxs-lookup"><span data-stu-id="5cec4-186">Records media stack trace events.</span></span>         |
|<span data-ttu-id="5cec4-187">Debug-0-s2790420889.blog</span><span class="sxs-lookup"><span data-stu-id="5cec4-187">Debug-0-s2790420889.blog</span></span>    | <span data-ttu-id="5cec4-188">Contiene información relacionada con el agente multimedia, incluida la calidad de representación.</span><span class="sxs-lookup"><span data-stu-id="5cec4-188">Contains information related to the media agent, including rendering quality.</span></span>          |
|<span data-ttu-id="5cec4-189">tscalling-0-2061129496.blog</span><span class="sxs-lookup"><span data-stu-id="5cec4-189">tscalling-0-2061129496.blog</span></span>   |<span data-ttu-id="5cec4-190">Registra eventos en la API de llamadas ts.</span><span class="sxs-lookup"><span data-stu-id="5cec4-190">Records events in the ts-calling API.</span></span>       |

<a name="desktop-logs"></a><span data-ttu-id="5cec4-191">Registros de escritorio</span><span class="sxs-lookup"><span data-stu-id="5cec4-191">Desktop logs</span></span>
---------------------

<span data-ttu-id="5cec4-192">Los registros de escritorio, también conocidos como registros de arranque, contienen datos de registro que se producen entre el cliente de escritorio y el explorador.</span><span class="sxs-lookup"><span data-stu-id="5cec4-192">Desktop logs, also known as bootstrapper logs, contain log data that occurs between the desktop client and the browser.</span></span> <span data-ttu-id="5cec4-193">Al igual que los registros multimedia, estos registros solo son necesarios si Microsoft lo solicita.</span><span class="sxs-lookup"><span data-stu-id="5cec4-193">Like media logs, these logs are only needed if requested by Microsoft.</span></span> <span data-ttu-id="5cec4-194">Los registros se basan en texto y se pueden leer con cualquier editor basado en texto en un formato de arriba abajo.</span><span class="sxs-lookup"><span data-stu-id="5cec4-194">The logs are text based and can be read using any text-based editor in a top-down format.</span></span>

<span data-ttu-id="5cec4-195">Windows:</span><span class="sxs-lookup"><span data-stu-id="5cec4-195">Windows:</span></span>

 - <span data-ttu-id="5cec4-196">Haga clic con el **botón Microsoft Teams** en la bandeja del sistema y seleccione **Obtener registros.**</span><span class="sxs-lookup"><span data-stu-id="5cec4-196">Right-click the **Microsoft Teams** icon in your system tray, and select **Get Logs**.</span></span>

<span data-ttu-id="5cec4-197">Mac OsX:</span><span class="sxs-lookup"><span data-stu-id="5cec4-197">Mac OsX:</span></span>

 - <span data-ttu-id="5cec4-198">Elija **Obtener registros** en el menú desplegable Ayuda. </span><span class="sxs-lookup"><span data-stu-id="5cec4-198">Choose **Get Logs** from the **Help** pull-down menu.</span></span>

<span data-ttu-id="5cec4-199">Linux:</span><span class="sxs-lookup"><span data-stu-id="5cec4-199">Linux:</span></span>

 - <span data-ttu-id="5cec4-200">Haga clic en **el Microsoft Teams** en la bandeja del sistema y seleccione **Obtener registros.**</span><span class="sxs-lookup"><span data-stu-id="5cec4-200">Click on the **Microsoft Teams** icon in your system tray, and select **Get Logs**.</span></span>

|<span data-ttu-id="5cec4-201">Cliente</span><span class="sxs-lookup"><span data-stu-id="5cec4-201">Client</span></span> |<span data-ttu-id="5cec4-202">Ubicación</span><span class="sxs-lookup"><span data-stu-id="5cec4-202">Location</span></span> |
|---------|---------|
|<span data-ttu-id="5cec4-203">Windows</span><span class="sxs-lookup"><span data-stu-id="5cec4-203">Windows</span></span>     |<span data-ttu-id="5cec4-204">%appdata%\Microsoft\Teams\logs.txt</span><span class="sxs-lookup"><span data-stu-id="5cec4-204">%appdata%\Microsoft\Teams\logs.txt</span></span>         |
|<span data-ttu-id="5cec4-205">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="5cec4-205">Mac OSX</span></span>     |<span data-ttu-id="5cec4-206">~/Library/Application Support/Microsoft/Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="5cec4-206">~/Library/Application Support/Microsoft/Teams/logs.txt</span></span>         |
|<span data-ttu-id="5cec4-207">Linux</span><span class="sxs-lookup"><span data-stu-id="5cec4-207">Linux</span></span>       |<span data-ttu-id="5cec4-208">~/.config/Microsoft/Microsoft Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="5cec4-208">~/.config/Microsoft/Microsoft Teams/logs.txt</span></span>         |


<a name="browser-trace"></a><span data-ttu-id="5cec4-209">Seguimiento del explorador</span><span class="sxs-lookup"><span data-stu-id="5cec4-209">Browser trace</span></span>
---------------------------

<span data-ttu-id="5cec4-210">Para algunas categorías de errores, es posible que el soporte técnico de Microsoft requiera que recopile un seguimiento del explorador.</span><span class="sxs-lookup"><span data-stu-id="5cec4-210">For some categories of errors, Microsoft Support might require you to collect a browser trace.</span></span> <span data-ttu-id="5cec4-211">Esta información puede proporcionar detalles importantes sobre el estado del Teams cliente cuando se produce el error.</span><span class="sxs-lookup"><span data-stu-id="5cec4-211">This information can provide important details about the state of the Teams client when the error occurs.</span></span>

<span data-ttu-id="5cec4-212">Antes de iniciar el seguimiento del explorador, asegúrese de que ha iniciado sesión en Teams.</span><span class="sxs-lookup"><span data-stu-id="5cec4-212">Before you start the browser trace, make sure that you’re signed in to Teams.</span></span> <span data-ttu-id="5cec4-213">Es importante hacer esto antes de iniciar el seguimiento para que el seguimiento no contenga información confidencial de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="5cec4-213">It's important to do this before you start the trace so that the trace doesn't contain sensitive sign-in information.</span></span>

<span data-ttu-id="5cec4-214">Después de haber iniciado sesión, seleccione uno de los vínculos siguientes, según corresponda para el explorador, y siga los pasos proporcionados.</span><span class="sxs-lookup"><span data-stu-id="5cec4-214">After you’re signed in, select one of the following links, as appropriate for your browser, and follow the provided steps.</span></span> 

-   [<span data-ttu-id="5cec4-215">Chrome & Edge (Chromium)</span><span class="sxs-lookup"><span data-stu-id="5cec4-215">Chrome & Edge (Chromium)</span></span>](/azure/azure-portal/capture-browser-trace#google-chrome-and-microsoft-edge-chromium?preserve-view=true#resolution)

-   [<span data-ttu-id="5cec4-216">Perimetral</span><span class="sxs-lookup"><span data-stu-id="5cec4-216">Edge</span></span>](/azure/azure-portal/capture-browser-trace#microsoft-edge-edgehtml?preserve-view=true#resolution)

-   [<span data-ttu-id="5cec4-217">Safari</span><span class="sxs-lookup"><span data-stu-id="5cec4-217">Safari</span></span>](/azure/azure-portal/capture-browser-trace#apple-safari?preserve-view=true#resolution)

-   [<span data-ttu-id="5cec4-218">Firefox</span><span class="sxs-lookup"><span data-stu-id="5cec4-218">Firefox</span></span>](/azure/azure-portal/capture-browser-trace#firefox?preserve-view=true#resolution)

> [!NOTE]
> <span data-ttu-id="5cec4-219">En los pasos, reemplace todas las referencias a Azure Portal por el Teams cliente.</span><span class="sxs-lookup"><span data-stu-id="5cec4-219">In the steps, replace all references to the Azure portal with the Teams client.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="5cec4-220">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="5cec4-220">Related topics</span></span>

[<span data-ttu-id="5cec4-221">Solución de problemas de Teams</span><span class="sxs-lookup"><span data-stu-id="5cec4-221">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)
