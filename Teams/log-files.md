---
title: Usar los archivos de registro para solucionar problemas en Microsoft Teams
ms.reviewer: tejeshs
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 05/06/2021
audience: admin
ms.topic: troubleshooting
ms.service: msteams
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
search.appverid: MET150
description: Obtenga información sobre los registros de depuración, medios y escritorio producidos por Microsoft Teams, dónde se pueden encontrar y cómo pueden ayudar con la supervisión y solución de problemas.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 58460390d9562d77ed6a4e3dfcbb3948cbe2749e
ms.sourcegitcommit: 40f76bc6b5e304faea8516a78f8576ba1cdb7f7c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2021
ms.locfileid: "52337747"
---
# <a name="use-log-files-to-monitor-and-troubleshoot-microsoft-teams"></a><span data-ttu-id="5272d-103">Use archivos de registro para supervisar y solucionar problemas Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5272d-103">Use log files to monitor and troubleshoot Microsoft Teams</span></span>

<span data-ttu-id="5272d-104">Hay tres tipos de archivos de registro generados automáticamente por el cliente, que se pueden aprovechar para ayudar a supervisar y solucionar problemas Teams:</span><span class="sxs-lookup"><span data-stu-id="5272d-104">There are three types of log files automatically produced by the client, which can be leveraged to assist in monitoring and troubleshooting Teams:</span></span>

-   [<span data-ttu-id="5272d-105">Registros de depuración</span><span class="sxs-lookup"><span data-stu-id="5272d-105">Debug logs</span></span>](#debug-logs)

-   [<span data-ttu-id="5272d-106">Registros multimedia</span><span class="sxs-lookup"><span data-stu-id="5272d-106">Media logs</span></span>](#media-logs)

-   [<span data-ttu-id="5272d-107">Registros de escritorio</span><span class="sxs-lookup"><span data-stu-id="5272d-107">Desktop logs</span></span>](#desktop-logs)

<span data-ttu-id="5272d-108">En este artículo se describen los tres registros y cómo se usan.</span><span class="sxs-lookup"><span data-stu-id="5272d-108">This article describes the three logs and how they are used.</span></span> 

<span data-ttu-id="5272d-109">Para obtener información sobre cómo solucionar problemas específicos, [vea: Teams solución de problemas.](/MicrosoftTeams/troubleshoot/teams)</span><span class="sxs-lookup"><span data-stu-id="5272d-109">For information about troubleshooting specific issues, see: [Teams Troubleshooting](/MicrosoftTeams/troubleshoot/teams).</span></span> <span data-ttu-id="5272d-110">Para obtener información sobre cómo ponerse en contacto con el soporte técnico, vea [Obtener soporte técnico.](/microsoft-365/business-video/get-help-support)</span><span class="sxs-lookup"><span data-stu-id="5272d-110">For information about how to contact support, see [Get support](/microsoft-365/business-video/get-help-support).</span></span>

<span data-ttu-id="5272d-111">Al crear una solicitud de soporte técnico con soporte técnico de Microsoft, el ingeniero de soporte técnico necesitará los registros de depuración.</span><span class="sxs-lookup"><span data-stu-id="5272d-111">When creating a support request with Microsoft Support, the support engineer will require the debug logs.</span></span> <span data-ttu-id="5272d-112">Tener los registros de depuración a mano antes de crear la solicitud de soporte técnico permitirá a Microsoft empezar rápidamente a solucionar el problema.</span><span class="sxs-lookup"><span data-stu-id="5272d-112">Having the debug logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem.</span></span> <span data-ttu-id="5272d-113">**Los registros** multimedia **o de** escritorio solo son necesarios si Microsoft lo solicita.</span><span class="sxs-lookup"><span data-stu-id="5272d-113">**Media** or **Desktop** logs are only required if requested by Microsoft.</span></span>

> [!NOTE]
> <span data-ttu-id="5272d-114">En este artículo, el término **Registros de depuración** hace referencia a los registros que se usan para la solución de problemas.</span><span class="sxs-lookup"><span data-stu-id="5272d-114">In this article, the term **Debug logs** refers to the logs that are used for troubleshooting.</span></span> <span data-ttu-id="5272d-115">Sin embargo, los archivos que se generan para estos registros contendrán el término registros **de diagnóstico** en sus nombres.</span><span class="sxs-lookup"><span data-stu-id="5272d-115">However, the files that are generated for these logs will contain the term **diagnostic logs** in their names.</span></span>  

<span data-ttu-id="5272d-116">En la tabla siguiente se describen los distintos clientes y sus registros asociados.</span><span class="sxs-lookup"><span data-stu-id="5272d-116">The following table outlines the various clients and their associated logs.</span></span> <span data-ttu-id="5272d-117">Los archivos de registro se almacenan en ubicaciones específicas del cliente y del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="5272d-117">Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="5272d-118">Cliente</span><span class="sxs-lookup"><span data-stu-id="5272d-118">Client</span></span> |<span data-ttu-id="5272d-119">Depuración</span><span class="sxs-lookup"><span data-stu-id="5272d-119">Debug</span></span>|<span data-ttu-id="5272d-120">Escritorio</span><span class="sxs-lookup"><span data-stu-id="5272d-120">Desktop</span></span>|<span data-ttu-id="5272d-121">Medios</span><span class="sxs-lookup"><span data-stu-id="5272d-121">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="5272d-122">Web</span><span class="sxs-lookup"><span data-stu-id="5272d-122">Web</span></span>    |<span data-ttu-id="5272d-123">X</span><span class="sxs-lookup"><span data-stu-id="5272d-123">X</span></span>         |-         |-         |
|<span data-ttu-id="5272d-124">Windows</span><span class="sxs-lookup"><span data-stu-id="5272d-124">Windows</span></span>     |<span data-ttu-id="5272d-125">X</span><span class="sxs-lookup"><span data-stu-id="5272d-125">X</span></span>         |<span data-ttu-id="5272d-126">X</span><span class="sxs-lookup"><span data-stu-id="5272d-126">X</span></span>         |<span data-ttu-id="5272d-127">X</span><span class="sxs-lookup"><span data-stu-id="5272d-127">X</span></span>         |
|<span data-ttu-id="5272d-128">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="5272d-128">Mac OSX</span></span>     |<span data-ttu-id="5272d-129">X</span><span class="sxs-lookup"><span data-stu-id="5272d-129">X</span></span>         |<span data-ttu-id="5272d-130">X</span><span class="sxs-lookup"><span data-stu-id="5272d-130">X</span></span>         |<span data-ttu-id="5272d-131">X</span><span class="sxs-lookup"><span data-stu-id="5272d-131">X</span></span>         |
|<span data-ttu-id="5272d-132">Linux</span><span class="sxs-lookup"><span data-stu-id="5272d-132">Linux</span></span>     |<span data-ttu-id="5272d-133">X</span><span class="sxs-lookup"><span data-stu-id="5272d-133">X</span></span>         |<span data-ttu-id="5272d-134">X</span><span class="sxs-lookup"><span data-stu-id="5272d-134">X</span></span>         |<span data-ttu-id="5272d-135">X</span><span class="sxs-lookup"><span data-stu-id="5272d-135">X</span></span>         |
|<span data-ttu-id="5272d-136">iOS</span><span class="sxs-lookup"><span data-stu-id="5272d-136">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="5272d-137">Android</span><span class="sxs-lookup"><span data-stu-id="5272d-137">Android</span></span>     |-         |-         |-         |

<span data-ttu-id="5272d-138">Para ver una lista completa de los sistemas operativos y los exploradores compatibles, vea [Obtener clientes para Microsoft Teams](get-clients.md).</span><span class="sxs-lookup"><span data-stu-id="5272d-138">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

## <a name="debug-logs"></a><span data-ttu-id="5272d-139">Registros de depuración</span><span class="sxs-lookup"><span data-stu-id="5272d-139">Debug logs</span></span>

<span data-ttu-id="5272d-140">Estos son los registros más comunes y son necesarios para todos los casos de soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5272d-140">These are the most common logs and are required for all Microsoft support cases.</span></span> <span data-ttu-id="5272d-141">Los registros de depuración son producidos por Windows y mac clientes de escritorio, así como por clientes basados en explorador.</span><span class="sxs-lookup"><span data-stu-id="5272d-141">Debug logs are produced by the Windows and Mac desktop clients, as well as by browser-based clients.</span></span> <span data-ttu-id="5272d-142">Los registros se basan en texto y se leen desde abajo hacia arriba.</span><span class="sxs-lookup"><span data-stu-id="5272d-142">The logs are text based and are read from the bottom-up.</span></span> <span data-ttu-id="5272d-143">Se pueden leer con cualquier editor basado en texto y se crean nuevos registros al iniciar sesión en el cliente.</span><span class="sxs-lookup"><span data-stu-id="5272d-143">They can be read using any text-based editor, and new logs are created when logging into the client.</span></span>

<span data-ttu-id="5272d-144">Los registros de depuración muestran los siguientes flujos de datos:</span><span class="sxs-lookup"><span data-stu-id="5272d-144">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="5272d-145">Inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="5272d-145">Login</span></span>

-   <span data-ttu-id="5272d-146">Solicitudes de conexión a servicios de nivel medio</span><span class="sxs-lookup"><span data-stu-id="5272d-146">Connection requests to middle-tier services</span></span>

-   <span data-ttu-id="5272d-147">Llamada/conversación</span><span class="sxs-lookup"><span data-stu-id="5272d-147">Call/conversation</span></span>

<span data-ttu-id="5272d-148">Los registros de depuración se generan con los siguientes métodos específicos del sistema operativo:</span><span class="sxs-lookup"><span data-stu-id="5272d-148">The debug logs are produced using the following OS-specific methods:</span></span>

-   <span data-ttu-id="5272d-149">Windows:</span><span class="sxs-lookup"><span data-stu-id="5272d-149">Windows:</span></span>

      <span data-ttu-id="5272d-150">Método abreviado de teclado: Ctrl + Alt + Mayús + 1</span><span class="sxs-lookup"><span data-stu-id="5272d-150">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

-   <span data-ttu-id="5272d-151">Mac OSX:</span><span class="sxs-lookup"><span data-stu-id="5272d-151">Mac OSX:</span></span>

      <span data-ttu-id="5272d-152">Método abreviado de teclado: Opción + Comando + Mayús + 1</span><span class="sxs-lookup"><span data-stu-id="5272d-152">Keyboard shortcut: Option + Command + Shift+1</span></span>

-   <span data-ttu-id="5272d-153">Linux:</span><span class="sxs-lookup"><span data-stu-id="5272d-153">Linux:</span></span>

      <span data-ttu-id="5272d-154">Método abreviado de teclado: Ctrl + Alt + Mayús + 1</span><span class="sxs-lookup"><span data-stu-id="5272d-154">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

<span data-ttu-id="5272d-155">Los registros de depuración se descargan automáticamente en las siguientes carpetas:</span><span class="sxs-lookup"><span data-stu-id="5272d-155">The debug logs are automatically downloaded to the following folders:</span></span>

-   <span data-ttu-id="5272d-156">Windows: %userprofile%\\Descargas</span><span class="sxs-lookup"><span data-stu-id="5272d-156">Windows: %userprofile%\\Downloads</span></span>

-   <span data-ttu-id="5272d-157">Mac OSX: ~/Descargas</span><span class="sxs-lookup"><span data-stu-id="5272d-157">Mac OSX: ~/Downloads</span></span>

-   <span data-ttu-id="5272d-158">Linux: ~/Descargas</span><span class="sxs-lookup"><span data-stu-id="5272d-158">Linux: ~/Downloads</span></span>

-   <span data-ttu-id="5272d-159">Explorador: Se le pedirá que guarde el registro de depuración en la ubicación predeterminada.</span><span class="sxs-lookup"><span data-stu-id="5272d-159">Browser: You will be prompted to save the debug log to default save location</span></span>

## <a name="media-logs"></a><span data-ttu-id="5272d-160">Registros de medios</span><span class="sxs-lookup"><span data-stu-id="5272d-160">Media logs</span></span>

<span data-ttu-id="5272d-161">Los registros multimedia contienen datos de diagnóstico sobre audio, vídeo y uso compartido de pantalla en Teams reuniones.</span><span class="sxs-lookup"><span data-stu-id="5272d-161">Media logs contain diagnostic data about audio, video, and screen sharing in Teams meetings.</span></span> <span data-ttu-id="5272d-162">Son necesarios para los casos de soporte técnico vinculados a problemas relacionados con llamadas.</span><span class="sxs-lookup"><span data-stu-id="5272d-162">They are required for support cases that are linked to call-related issues.</span></span>

<span data-ttu-id="5272d-163">El registro multimedia está desactivado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="5272d-163">Media logging is turned off by default.</span></span> <span data-ttu-id="5272d-164">Para registrar datos de diagnóstico Teams reuniones, los usuarios deben activar la opción en el Teams cliente.</span><span class="sxs-lookup"><span data-stu-id="5272d-164">To log diagnostic data for Teams meetings, users must turn on the option in the Teams client.</span></span> <span data-ttu-id="5272d-165">Vaya **a Configuración** General , active la casilla Habilitar registro para diagnósticos de reuniones (requiere reiniciar Teams), reinicie Teams y  >  reproduzca el problema.</span><span class="sxs-lookup"><span data-stu-id="5272d-165">Go to **Settings** > **General**, select the **Enable logging for meeting diagnostics (requires restarting Teams**) check box, restart Teams, and reproduce the issue.</span></span> 

<span data-ttu-id="5272d-166">En la tabla siguiente se describen las ubicaciones de registro multimedia.</span><span class="sxs-lookup"><span data-stu-id="5272d-166">The following table outlines the media log locations.</span></span> <span data-ttu-id="5272d-167">Cuando envíe los archivos de registro al soporte técnico de Microsoft, compruebe la marca de tiempo de los archivos de registro para asegurarse de que los registros cubren el período de tiempo cuando reproduzca el problema.</span><span class="sxs-lookup"><span data-stu-id="5272d-167">When you send the log files to Microsoft support, please verify the timestamp of the log files to ensure the logs cover the time frame when you reproduced the issue.</span></span>

|<span data-ttu-id="5272d-168">Cliente</span><span class="sxs-lookup"><span data-stu-id="5272d-168">Client</span></span> |<span data-ttu-id="5272d-169">Ubicación</span><span class="sxs-lookup"><span data-stu-id="5272d-169">Location</span></span> |
|---------|---------|
|<span data-ttu-id="5272d-170">Windows</span><span class="sxs-lookup"><span data-stu-id="5272d-170">Windows</span></span>     |<span data-ttu-id="5272d-171">%appdata%\Microsoft\Teams\media-stack \\ \*.blog</span><span class="sxs-lookup"><span data-stu-id="5272d-171">%appdata%\Microsoft\Teams\media-stack\\*.blog</span></span>         |
|            |<span data-ttu-id="5272d-172">%appdata%\Microsoft\Teams\skylib \\ \*.blog</span><span class="sxs-lookup"><span data-stu-id="5272d-172">%appdata%\Microsoft\Teams\skylib\\*.blog</span></span>
|            |<span data-ttu-id="5272d-173">%appdata%\Microsoft\Teams\media-stack \\ \*.etl</span><span class="sxs-lookup"><span data-stu-id="5272d-173">%appdata%\Microsoft\Teams\media-stack\\*.etl</span></span>         |
|<span data-ttu-id="5272d-174">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="5272d-174">Mac OSX</span></span>     |<span data-ttu-id="5272d-175">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span><span class="sxs-lookup"><span data-stu-id="5272d-175">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="5272d-176">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span><span class="sxs-lookup"><span data-stu-id="5272d-176">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span></span>         |
|<span data-ttu-id="5272d-177">Linux</span><span class="sxs-lookup"><span data-stu-id="5272d-177">Linux</span></span>       |<span data-ttu-id="5272d-178">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span><span class="sxs-lookup"><span data-stu-id="5272d-178">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="5272d-179">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span><span class="sxs-lookup"><span data-stu-id="5272d-179">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span></span>         |

<span data-ttu-id="5272d-180">Esta es una lista de los archivos de registro que se generan y la información que contienen.</span><span class="sxs-lookup"><span data-stu-id="5272d-180">Here's a list of the log files that are generated and the information they contain.</span></span>

|<span data-ttu-id="5272d-181">Nombre de archivo de registro</span><span class="sxs-lookup"><span data-stu-id="5272d-181">Log file name</span></span>  |<span data-ttu-id="5272d-182">Descripción</span><span class="sxs-lookup"><span data-stu-id="5272d-182">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="5272d-183">Teams.msrtc-0-s1039525249.blog</span><span class="sxs-lookup"><span data-stu-id="5272d-183">Teams.msrtc-0-s1039525249.blog</span></span>     | <span data-ttu-id="5272d-184">Contiene información relacionada con la pila de elementos multimedia.</span><span class="sxs-lookup"><span data-stu-id="5272d-184">Contains information related to the media stack.</span></span> <span data-ttu-id="5272d-185">Esto incluye el estado del canal, como la resolución, los descodificadores y los codificadores usados, así como el número de fotogramas enviados y recibidos, y el estado de la sesión de uso compartido de pantalla basado en cámaras y vídeo (VBSS).</span><span class="sxs-lookup"><span data-stu-id="5272d-185">This includes channel status such as resolution, decoders and encoders used, and the number of frames sent and received, and camera and video-based screen sharing (VBSS) session status.</span></span>         |
|<span data-ttu-id="5272d-186">rtmcontrol.msrtc-0-2415069487.blog</span><span class="sxs-lookup"><span data-stu-id="5272d-186">rtmcontrol.msrtc-0-2415069487.blog</span></span>      |<span data-ttu-id="5272d-187">Registra información relacionada con acciones de control remoto, como la marca de tiempo cuando se proporciona el control e información del puntero del mouse.</span><span class="sxs-lookup"><span data-stu-id="5272d-187">Records information related to remote control actions, such as the time stamp when control is given, and mouse pointer information.</span></span>          |
|<span data-ttu-id="5272d-188">Teams_MediaStackETW-2-U-xr-U.etl</span><span class="sxs-lookup"><span data-stu-id="5272d-188">Teams_MediaStackETW-2-U-xr-U.etl</span></span>      |<span data-ttu-id="5272d-189">Registros de eventos de seguimiento de la pila de medios.</span><span class="sxs-lookup"><span data-stu-id="5272d-189">Records media stack trace events.</span></span>         |
|<span data-ttu-id="5272d-190">Debug-0-s2790420889.blog</span><span class="sxs-lookup"><span data-stu-id="5272d-190">Debug-0-s2790420889.blog</span></span>    | <span data-ttu-id="5272d-191">Contiene información relacionada con el agente multimedia, incluida la calidad de representación.</span><span class="sxs-lookup"><span data-stu-id="5272d-191">Contains information related to the media agent, including rendering quality.</span></span>          |
|<span data-ttu-id="5272d-192">tscalling-0-2061129496.blog</span><span class="sxs-lookup"><span data-stu-id="5272d-192">tscalling-0-2061129496.blog</span></span>   |<span data-ttu-id="5272d-193">Registra eventos en la API de llamadas ts.</span><span class="sxs-lookup"><span data-stu-id="5272d-193">Records events in the ts-calling API.</span></span>       |

## <a name="desktop-logs"></a><span data-ttu-id="5272d-194">Registros de escritorio</span><span class="sxs-lookup"><span data-stu-id="5272d-194">Desktop logs</span></span>

<span data-ttu-id="5272d-195">Los registros de escritorio, también conocidos como registros de arranque, contienen datos de registro que se producen entre el cliente de escritorio y el explorador.</span><span class="sxs-lookup"><span data-stu-id="5272d-195">Desktop logs, also known as bootstrapper logs, contain log data that occurs between the desktop client and the browser.</span></span> <span data-ttu-id="5272d-196">Al igual que los registros multimedia, estos registros solo son necesarios si Microsoft lo solicita.</span><span class="sxs-lookup"><span data-stu-id="5272d-196">Like media logs, these logs are only needed if requested by Microsoft.</span></span> <span data-ttu-id="5272d-197">Los registros se basan en texto y se pueden leer con cualquier editor basado en texto en un formato de arriba abajo.</span><span class="sxs-lookup"><span data-stu-id="5272d-197">The logs are text based and can be read using any text-based editor in a top-down format.</span></span>

<span data-ttu-id="5272d-198">Windows:</span><span class="sxs-lookup"><span data-stu-id="5272d-198">Windows:</span></span>

 - <span data-ttu-id="5272d-199">Haga clic con el **botón Microsoft Teams** en la bandeja del sistema y seleccione **Obtener registros.**</span><span class="sxs-lookup"><span data-stu-id="5272d-199">Right-click the **Microsoft Teams** icon in your system tray, and select **Get Logs**.</span></span>

<span data-ttu-id="5272d-200">Mac OsX:</span><span class="sxs-lookup"><span data-stu-id="5272d-200">Mac OsX:</span></span>

 - <span data-ttu-id="5272d-201">Elija **Obtener registros** en el menú desplegable Ayuda. </span><span class="sxs-lookup"><span data-stu-id="5272d-201">Choose **Get Logs** from the **Help** pull-down menu.</span></span>

<span data-ttu-id="5272d-202">Linux:</span><span class="sxs-lookup"><span data-stu-id="5272d-202">Linux:</span></span>

 - <span data-ttu-id="5272d-203">Haga clic en **el Microsoft Teams** en la bandeja del sistema y seleccione **Obtener registros.**</span><span class="sxs-lookup"><span data-stu-id="5272d-203">Click on the **Microsoft Teams** icon in your system tray, and select **Get Logs**.</span></span>

|<span data-ttu-id="5272d-204">Cliente</span><span class="sxs-lookup"><span data-stu-id="5272d-204">Client</span></span> |<span data-ttu-id="5272d-205">Ubicación</span><span class="sxs-lookup"><span data-stu-id="5272d-205">Location</span></span> |
|---------|---------|
|<span data-ttu-id="5272d-206">Windows</span><span class="sxs-lookup"><span data-stu-id="5272d-206">Windows</span></span>     |<span data-ttu-id="5272d-207">%appdata%\Microsoft\Teams\logs.txt</span><span class="sxs-lookup"><span data-stu-id="5272d-207">%appdata%\Microsoft\Teams\logs.txt</span></span>         |
|<span data-ttu-id="5272d-208">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="5272d-208">Mac OSX</span></span>     |<span data-ttu-id="5272d-209">~/Library/Application Support/Microsoft/Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="5272d-209">~/Library/Application Support/Microsoft/Teams/logs.txt</span></span>         |
|<span data-ttu-id="5272d-210">Linux</span><span class="sxs-lookup"><span data-stu-id="5272d-210">Linux</span></span>       |<span data-ttu-id="5272d-211">~/.config/Microsoft/Microsoft Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="5272d-211">~/.config/Microsoft/Microsoft Teams/logs.txt</span></span>         |


## <a name="browser-trace"></a><span data-ttu-id="5272d-212">Seguimiento del explorador</span><span class="sxs-lookup"><span data-stu-id="5272d-212">Browser trace</span></span>

<span data-ttu-id="5272d-213">Para algunas categorías de errores, es posible que el soporte técnico de Microsoft requiera que recopile un seguimiento del explorador.</span><span class="sxs-lookup"><span data-stu-id="5272d-213">For some categories of errors, Microsoft Support might require you to collect a browser trace.</span></span> <span data-ttu-id="5272d-214">Esta información puede proporcionar detalles importantes sobre el estado del Teams cliente cuando se produce el error.</span><span class="sxs-lookup"><span data-stu-id="5272d-214">This information can provide important details about the state of the Teams client when the error occurs.</span></span>

<span data-ttu-id="5272d-215">Antes de iniciar el seguimiento del explorador, asegúrese de que ha iniciado sesión en Teams.</span><span class="sxs-lookup"><span data-stu-id="5272d-215">Before you start the browser trace, make sure that you’re signed in to Teams.</span></span> <span data-ttu-id="5272d-216">Es importante hacer esto antes de iniciar el seguimiento para que el seguimiento no contenga información confidencial de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="5272d-216">It's important to do this before you start the trace so that the trace doesn't contain sensitive sign-in information.</span></span>

<span data-ttu-id="5272d-217">Después de haber iniciado sesión, seleccione uno de los vínculos siguientes, según corresponda para el explorador, y siga los pasos proporcionados.</span><span class="sxs-lookup"><span data-stu-id="5272d-217">After you’re signed in, select one of the following links, as appropriate for your browser, and follow the provided steps.</span></span> 

-   [<span data-ttu-id="5272d-218">Chrome & Edge (Chromium)</span><span class="sxs-lookup"><span data-stu-id="5272d-218">Chrome & Edge (Chromium)</span></span>](/azure/azure-portal/capture-browser-trace#google-chrome-and-microsoft-edge-chromium?preserve-view=true#resolution)

-   [<span data-ttu-id="5272d-219">Perimetral</span><span class="sxs-lookup"><span data-stu-id="5272d-219">Edge</span></span>](/azure/azure-portal/capture-browser-trace#microsoft-edge-edgehtml?preserve-view=true#resolution)

-   [<span data-ttu-id="5272d-220">Safari</span><span class="sxs-lookup"><span data-stu-id="5272d-220">Safari</span></span>](/azure/azure-portal/capture-browser-trace#apple-safari?preserve-view=true#resolution)

-   [<span data-ttu-id="5272d-221">Firefox</span><span class="sxs-lookup"><span data-stu-id="5272d-221">Firefox</span></span>](/azure/azure-portal/capture-browser-trace#firefox?preserve-view=true#resolution)

> [!NOTE]
> <span data-ttu-id="5272d-222">En los pasos, reemplace todas las referencias a Azure Portal por el Teams cliente.</span><span class="sxs-lookup"><span data-stu-id="5272d-222">In the steps, replace all references to the Azure portal with the Teams client.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="5272d-223">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="5272d-223">Related topics</span></span>

[<span data-ttu-id="5272d-224">Solución de problemas de Teams</span><span class="sxs-lookup"><span data-stu-id="5272d-224">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)
