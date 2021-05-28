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
ms.openlocfilehash: a18dbef0441055c1202c2b77ce4f8af87040e561
ms.sourcegitcommit: 17e34d2de3d10f1d04929a695e301127db7014bd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2021
ms.locfileid: "52689698"
---
# <a name="use-log-files-to-monitor-and-troubleshoot-microsoft-teams"></a><span data-ttu-id="8c9de-103">Use archivos de registro para supervisar y solucionar problemas Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8c9de-103">Use log files to monitor and troubleshoot Microsoft Teams</span></span>

<span data-ttu-id="8c9de-104">Hay tres tipos de archivos de registro generados automáticamente por el cliente, que se pueden aprovechar para ayudar a supervisar y solucionar problemas Teams:</span><span class="sxs-lookup"><span data-stu-id="8c9de-104">There are three types of log files automatically produced by the client, which can be leveraged to assist in monitoring and troubleshooting Teams:</span></span>

-   [<span data-ttu-id="8c9de-105">Registros de depuración</span><span class="sxs-lookup"><span data-stu-id="8c9de-105">Debug logs</span></span>](#debug-logs)

-   [<span data-ttu-id="8c9de-106">Registros multimedia</span><span class="sxs-lookup"><span data-stu-id="8c9de-106">Media logs</span></span>](#media-logs)

-   [<span data-ttu-id="8c9de-107">Registros de escritorio</span><span class="sxs-lookup"><span data-stu-id="8c9de-107">Desktop logs</span></span>](#desktop-logs)

<span data-ttu-id="8c9de-108">En este artículo se describen estos registros y cómo se usan.</span><span class="sxs-lookup"><span data-stu-id="8c9de-108">This article describes these logs and how they are used.</span></span> <span data-ttu-id="8c9de-109">Para obtener información sobre cómo solucionar problemas específicos, [vea: Teams solución de problemas.](/MicrosoftTeams/troubleshoot/teams)</span><span class="sxs-lookup"><span data-stu-id="8c9de-109">For information about troubleshooting specific issues, see: [Teams Troubleshooting](/MicrosoftTeams/troubleshoot/teams).</span></span> <span data-ttu-id="8c9de-110">Para obtener información sobre cómo ponerse en contacto con el soporte técnico, vea [Obtener soporte técnico.](/microsoft-365/business-video/get-help-support)</span><span class="sxs-lookup"><span data-stu-id="8c9de-110">For information about how to contact support, see [Get support](/microsoft-365/business-video/get-help-support).</span></span> <span data-ttu-id="8c9de-111">Al crear una solicitud de soporte técnico con soporte técnico de Microsoft, el ingeniero de soporte técnico necesitará los registros de depuración.</span><span class="sxs-lookup"><span data-stu-id="8c9de-111">When creating a support request with Microsoft Support, the support engineer will require the debug logs.</span></span> <span data-ttu-id="8c9de-112">Tener los registros de depuración a mano antes de crear la solicitud de soporte técnico permitirá a Microsoft empezar rápidamente a solucionar el problema.</span><span class="sxs-lookup"><span data-stu-id="8c9de-112">Having the debug logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem.</span></span> <span data-ttu-id="8c9de-113">**Los registros** multimedia **o de** escritorio solo son necesarios si Microsoft lo solicita.</span><span class="sxs-lookup"><span data-stu-id="8c9de-113">**Media** or **Desktop** logs are only required if requested by Microsoft.</span></span>

> [!NOTE]
> <span data-ttu-id="8c9de-114">En este artículo, el término **Registros de depuración** hace referencia a los registros que se usan para la solución de problemas.</span><span class="sxs-lookup"><span data-stu-id="8c9de-114">In this article, the term **Debug logs** refers to the logs that are used for troubleshooting.</span></span> <span data-ttu-id="8c9de-115">Sin embargo, los archivos que se generan para estos registros contendrán el término registros **de diagnóstico** en sus nombres.</span><span class="sxs-lookup"><span data-stu-id="8c9de-115">However, the files that are generated for these logs will contain the term **diagnostic logs** in their names.</span></span>  

## <a name="collect-and-enable-logging"></a><span data-ttu-id="8c9de-116">Recopilar y habilitar el registro</span><span class="sxs-lookup"><span data-stu-id="8c9de-116">Collect and enable logging</span></span>

<span data-ttu-id="8c9de-117">Es importante recopilar registros tan pronto como se produzca un problema.</span><span class="sxs-lookup"><span data-stu-id="8c9de-117">It’s important to collect logs as soon as an issue occurs.</span></span> <span data-ttu-id="8c9de-118">Los registros se pueden recopilar juntos con solo un par de clics.</span><span class="sxs-lookup"><span data-stu-id="8c9de-118">The logs can be collected together with just a couple of clicks.</span></span>

<span data-ttu-id="8c9de-119">Windows: Haga clic con el botón derecho en el icono Teams en la bandeja del sistema y elija **Recopilar archivos de soporte técnico.**</span><span class="sxs-lookup"><span data-stu-id="8c9de-119">Windows: Right-click on the Teams icon in the system tray and choose **Collect support files**.</span></span> 

<span data-ttu-id="8c9de-120">Mac: seleccione el menú Ayuda y elija **Recopilar archivos de soporte técnico.**</span><span class="sxs-lookup"><span data-stu-id="8c9de-120">Mac: Select the Help menu and choose **Collect support files**.</span></span>

<span data-ttu-id="8c9de-121">Los registros de depuración, escritorio y medios se recopilarán en una carpeta con el nombre Registro de diagnóstico de MSTeams. <local data and time></span><span class="sxs-lookup"><span data-stu-id="8c9de-121">Debug, Desktop, and Media logs will be collected in one folder with the name MSTeams Diagnostics Log <local data and time>.</span></span> <span data-ttu-id="8c9de-122">Esta carpeta se puede comprimir y compartir al abrir una solicitud de soporte técnico con el soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8c9de-122">This folder can be compressed and shared when you open a support request with Microsoft Support.</span></span> <span data-ttu-id="8c9de-123">La carpeta contendrá carpetas para escritorio, reunión (multimedia) y depuración (web).</span><span class="sxs-lookup"><span data-stu-id="8c9de-123">The folder will contain folders for Desktop, Meeting (Media), and Debug (web).</span></span> <span data-ttu-id="8c9de-124">Puede recopilar los archivos con los siguientes métodos abreviados de teclado:</span><span class="sxs-lookup"><span data-stu-id="8c9de-124">You can collect the files using the following keyboard shortcuts:</span></span>

<span data-ttu-id="8c9de-125">Windows: Crtl + Alt + Mayús + 1</span><span class="sxs-lookup"><span data-stu-id="8c9de-125">Windows: Crtl + Alt + Shift + 1</span></span>

<span data-ttu-id="8c9de-126">Mac: Opción + Comando + Mayús + 1</span><span class="sxs-lookup"><span data-stu-id="8c9de-126">Mac: Option + Command + Shift + 1</span></span>

<span data-ttu-id="8c9de-127">El registro multimedia está desactivado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="8c9de-127">Media logging is turned off by default.</span></span> <span data-ttu-id="8c9de-128">Para habilitar el registro multimedia, los usuarios deben activar la opción en Teams cliente.</span><span class="sxs-lookup"><span data-stu-id="8c9de-128">To enable Media logging, users must turn on the option in the Teams client.</span></span> <span data-ttu-id="8c9de-129">Vaya a **Configuración** General y seleccione Habilitar registro para diagnósticos de reuniones  >   **(requiere reiniciar Teams).**</span><span class="sxs-lookup"><span data-stu-id="8c9de-129">Go to **Settings** > **General**, and select **Enable logging for meeting diagnostics (requires restarting Teams)**.</span></span> <span data-ttu-id="8c9de-130">El Teams cliente debe reiniciarse para que comience el registro.</span><span class="sxs-lookup"><span data-stu-id="8c9de-130">The Teams client must be restarted for logging to begin.</span></span>

> [!NOTE]
> <span data-ttu-id="8c9de-131">Si el registro multimedia está habilitado, habrá archivos adicionales incluidos en la carpeta Reunión que son necesarios para investigar problemas de audio y vídeo.</span><span class="sxs-lookup"><span data-stu-id="8c9de-131">If Media logging is enabled, there will be additional files included in the Meeting folder which are necessary for investigating audio and video issues.</span></span> <span data-ttu-id="8c9de-132">Si el registro multimedia no está habilitado, habrá un número limitado de registros disponibles.</span><span class="sxs-lookup"><span data-stu-id="8c9de-132">If Media logging is not enabled, there will be a limited number of logs available.</span></span>

<span data-ttu-id="8c9de-133">En la tabla siguiente se describen los distintos clientes y sus registros asociados.</span><span class="sxs-lookup"><span data-stu-id="8c9de-133">The following table outlines the various clients and their associated logs.</span></span> <span data-ttu-id="8c9de-134">Los archivos de registro se almacenan en ubicaciones específicas del cliente y del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="8c9de-134">Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="8c9de-135">Cliente</span><span class="sxs-lookup"><span data-stu-id="8c9de-135">Client</span></span> |<span data-ttu-id="8c9de-136">Depuración</span><span class="sxs-lookup"><span data-stu-id="8c9de-136">Debug</span></span>|<span data-ttu-id="8c9de-137">Escritorio</span><span class="sxs-lookup"><span data-stu-id="8c9de-137">Desktop</span></span>|<span data-ttu-id="8c9de-138">Medios</span><span class="sxs-lookup"><span data-stu-id="8c9de-138">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="8c9de-139">Web</span><span class="sxs-lookup"><span data-stu-id="8c9de-139">Web</span></span>    |<span data-ttu-id="8c9de-140">X</span><span class="sxs-lookup"><span data-stu-id="8c9de-140">X</span></span>         |-         |-         |
|<span data-ttu-id="8c9de-141">Windows</span><span class="sxs-lookup"><span data-stu-id="8c9de-141">Windows</span></span>     |<span data-ttu-id="8c9de-142">X</span><span class="sxs-lookup"><span data-stu-id="8c9de-142">X</span></span>         |<span data-ttu-id="8c9de-143">X</span><span class="sxs-lookup"><span data-stu-id="8c9de-143">X</span></span>         |<span data-ttu-id="8c9de-144">X</span><span class="sxs-lookup"><span data-stu-id="8c9de-144">X</span></span>         |
|<span data-ttu-id="8c9de-145">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="8c9de-145">Mac OSX</span></span>     |<span data-ttu-id="8c9de-146">X</span><span class="sxs-lookup"><span data-stu-id="8c9de-146">X</span></span>         |<span data-ttu-id="8c9de-147">X</span><span class="sxs-lookup"><span data-stu-id="8c9de-147">X</span></span>         |<span data-ttu-id="8c9de-148">X</span><span class="sxs-lookup"><span data-stu-id="8c9de-148">X</span></span>         |
|<span data-ttu-id="8c9de-149">Linux</span><span class="sxs-lookup"><span data-stu-id="8c9de-149">Linux</span></span>     |<span data-ttu-id="8c9de-150">X</span><span class="sxs-lookup"><span data-stu-id="8c9de-150">X</span></span>         |<span data-ttu-id="8c9de-151">X</span><span class="sxs-lookup"><span data-stu-id="8c9de-151">X</span></span>         |<span data-ttu-id="8c9de-152">X</span><span class="sxs-lookup"><span data-stu-id="8c9de-152">X</span></span>         |
|<span data-ttu-id="8c9de-153">iOS</span><span class="sxs-lookup"><span data-stu-id="8c9de-153">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="8c9de-154">Android</span><span class="sxs-lookup"><span data-stu-id="8c9de-154">Android</span></span>     |-         |-         |-         |

<span data-ttu-id="8c9de-155">Para ver una lista completa de los sistemas operativos y los exploradores compatibles, vea [Obtener clientes para Microsoft Teams](get-clients.md).</span><span class="sxs-lookup"><span data-stu-id="8c9de-155">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

## <a name="debug-logs"></a><span data-ttu-id="8c9de-156">Registros de depuración</span><span class="sxs-lookup"><span data-stu-id="8c9de-156">Debug logs</span></span>

<span data-ttu-id="8c9de-157">Consulte la _sección Recopilar y habilitar el registro_ para obtener Windows y Mac.</span><span class="sxs-lookup"><span data-stu-id="8c9de-157">See the _Collect and enable logging_ section for Windows and Mac instructions.</span></span> <span data-ttu-id="8c9de-158">Los registros de depuración son producidos por Windows y mac clientes de escritorio, así como por clientes basados en explorador.</span><span class="sxs-lookup"><span data-stu-id="8c9de-158">Debug logs are produced by the Windows and Mac desktop clients, as well as by browser-based clients.</span></span> <span data-ttu-id="8c9de-159">Los registros están basados en texto y se leen desde abajo hacia arriba.</span><span class="sxs-lookup"><span data-stu-id="8c9de-159">The logs are text-based and are read from the bottom-up.</span></span> <span data-ttu-id="8c9de-160">Se pueden leer con cualquier editor basado en texto y se crean nuevos registros al iniciar sesión en el cliente.</span><span class="sxs-lookup"><span data-stu-id="8c9de-160">They can be read using any text-based editor, and new logs are created when logging into the client.</span></span>

<span data-ttu-id="8c9de-161">Los registros de depuración muestran los siguientes flujos de datos:</span><span class="sxs-lookup"><span data-stu-id="8c9de-161">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="8c9de-162">Inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="8c9de-162">Login</span></span>

-   <span data-ttu-id="8c9de-163">Solicitudes de conexión a servicios de nivel medio</span><span class="sxs-lookup"><span data-stu-id="8c9de-163">Connection requests to middle-tier services</span></span>

-   <span data-ttu-id="8c9de-164">Llamada/conversación</span><span class="sxs-lookup"><span data-stu-id="8c9de-164">Call/conversation</span></span>

<span data-ttu-id="8c9de-165">Para recopilar registros para Linux: Método abreviado de teclado: Ctrl + Alt + Mayús + 1 Los archivos estarán disponibles en ~/Descargas</span><span class="sxs-lookup"><span data-stu-id="8c9de-165">To collect logs for Linux: Keyboard shortcut: Ctrl + Alt + Shift + 1 The files will be available in ~/Downloads</span></span>

<span data-ttu-id="8c9de-166">Para recopilar registros para el explorador: Método abreviado de teclado: Crtl + Alt + Mayús + 1 Los archivos estarán disponibles en %userprofile%\Downloads</span><span class="sxs-lookup"><span data-stu-id="8c9de-166">To collect logs for Browser: Keyboard shortcut: Crtl + Alt + Shift + 1 The files will be available in %userprofile%\Downloads</span></span>

## <a name="media-logs"></a><span data-ttu-id="8c9de-167">Registros de medios</span><span class="sxs-lookup"><span data-stu-id="8c9de-167">Media logs</span></span>

<span data-ttu-id="8c9de-168">Consulte la _sección Recopilar y habilitar el registro_ para obtener Windows y Mac.</span><span class="sxs-lookup"><span data-stu-id="8c9de-168">See the _Collect and enable logging_ section for Windows and Mac instructions.</span></span> <span data-ttu-id="8c9de-169">Los registros multimedia contienen datos de diagnóstico sobre audio, vídeo y uso compartido de pantalla en Teams reuniones.</span><span class="sxs-lookup"><span data-stu-id="8c9de-169">Media logs contain diagnostic data about audio, video, and screen sharing in Teams meetings.</span></span> <span data-ttu-id="8c9de-170">Son necesarios para los casos de soporte técnico vinculados a problemas relacionados con llamadas.</span><span class="sxs-lookup"><span data-stu-id="8c9de-170">They are required for support cases that are linked to call-related issues.</span></span>

<span data-ttu-id="8c9de-171">El registro multimedia está desactivado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="8c9de-171">Media logging is turned off by default.</span></span> <span data-ttu-id="8c9de-172">Para registrar datos de diagnóstico Teams reuniones, los usuarios deben activar la opción en el Teams cliente.</span><span class="sxs-lookup"><span data-stu-id="8c9de-172">To log diagnostic data for Teams meetings, users must turn on the option in the Teams client.</span></span> <span data-ttu-id="8c9de-173">Vaya **a Configuración** General , active la casilla Habilitar registro para diagnósticos de reuniones (requiere reiniciar Teams), reinicie Teams y  >  reproduzca el problema.</span><span class="sxs-lookup"><span data-stu-id="8c9de-173">Go to **Settings** > **General**, select the **Enable logging for meeting diagnostics (requires restarting Teams**) check box, restart Teams, and reproduce the issue.</span></span> 

<span data-ttu-id="8c9de-174">Cuando envíe los archivos de registro al soporte técnico de Microsoft, compruebe la marca de tiempo de los archivos de registro para asegurarse de que los registros cubren el período de tiempo cuando reproduzca el problema.</span><span class="sxs-lookup"><span data-stu-id="8c9de-174">When you send the log files to Microsoft support, please verify the timestamp of the log files to ensure the logs cover the time frame when you reproduced the issue.</span></span>

<span data-ttu-id="8c9de-175">Para recopilar registros para Linux: los archivos estarán disponibles en ~/.config/Microsoft/Microsoft Teams/media-stack/ .blog y *~/.config/Microsoft/Microsoft Teams/skylib/*.blog.</span><span class="sxs-lookup"><span data-stu-id="8c9de-175">To collect logs for Linux: The files will be available in ~/.config/Microsoft/Microsoft Teams/media-stack/*.blog and ~/.config/Microsoft/Microsoft Teams/skylib/*.blog.</span></span>

<span data-ttu-id="8c9de-176">Esta es una lista de los archivos de registro que se generan y la información que contienen.</span><span class="sxs-lookup"><span data-stu-id="8c9de-176">Here's a list of the log files that are generated and the information they contain.</span></span>

|<span data-ttu-id="8c9de-177">Nombre de archivo de registro</span><span class="sxs-lookup"><span data-stu-id="8c9de-177">Log file name</span></span>  |<span data-ttu-id="8c9de-178">Descripción</span><span class="sxs-lookup"><span data-stu-id="8c9de-178">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="8c9de-179">Teams.msrtc-0-s1039525249.blog</span><span class="sxs-lookup"><span data-stu-id="8c9de-179">Teams.msrtc-0-s1039525249.blog</span></span>     | <span data-ttu-id="8c9de-180">Contiene información relacionada con la pila de elementos multimedia.</span><span class="sxs-lookup"><span data-stu-id="8c9de-180">Contains information related to the media stack.</span></span> <span data-ttu-id="8c9de-181">Esto incluye el estado del canal, como la resolución, los descodificadores y los codificadores usados, así como el número de fotogramas enviados y recibidos, y el estado de la sesión de uso compartido de pantalla basado en cámaras y vídeo (VBSS).</span><span class="sxs-lookup"><span data-stu-id="8c9de-181">This includes channel status such as resolution, decoders and encoders used, and the number of frames sent and received, and camera and video-based screen sharing (VBSS) session status.</span></span>         |
|<span data-ttu-id="8c9de-182">rtmcontrol.msrtc-0-2415069487.blog</span><span class="sxs-lookup"><span data-stu-id="8c9de-182">rtmcontrol.msrtc-0-2415069487.blog</span></span>      |<span data-ttu-id="8c9de-183">Registra información relacionada con acciones de control remoto, como la marca de tiempo cuando se proporciona el control e información del puntero del mouse.</span><span class="sxs-lookup"><span data-stu-id="8c9de-183">Records information related to remote control actions, such as the time stamp when control is given, and mouse pointer information.</span></span>          |
|<span data-ttu-id="8c9de-184">Teams_MediaStackETW-2-U-xr-U.etl</span><span class="sxs-lookup"><span data-stu-id="8c9de-184">Teams_MediaStackETW-2-U-xr-U.etl</span></span>      |<span data-ttu-id="8c9de-185">Registros de eventos de seguimiento de la pila de medios.</span><span class="sxs-lookup"><span data-stu-id="8c9de-185">Records media stack trace events.</span></span>         |
|<span data-ttu-id="8c9de-186">Debug-0-s2790420889.blog</span><span class="sxs-lookup"><span data-stu-id="8c9de-186">Debug-0-s2790420889.blog</span></span>    | <span data-ttu-id="8c9de-187">Contiene información relacionada con el agente multimedia, incluida la calidad de representación.</span><span class="sxs-lookup"><span data-stu-id="8c9de-187">Contains information related to the media agent, including rendering quality.</span></span>          |
|<span data-ttu-id="8c9de-188">tscalling-0-2061129496.blog</span><span class="sxs-lookup"><span data-stu-id="8c9de-188">tscalling-0-2061129496.blog</span></span>   |<span data-ttu-id="8c9de-189">Registra eventos en la API de llamadas ts.</span><span class="sxs-lookup"><span data-stu-id="8c9de-189">Records events in the ts-calling API.</span></span>       |

## <a name="desktop-logs"></a><span data-ttu-id="8c9de-190">Registros de escritorio</span><span class="sxs-lookup"><span data-stu-id="8c9de-190">Desktop logs</span></span>

<span data-ttu-id="8c9de-191">Consulte la _sección Recopilar y habilitar el registro_ para obtener Windows y Mac.</span><span class="sxs-lookup"><span data-stu-id="8c9de-191">See the _Collect and enable logging_ section for Windows and Mac instructions.</span></span> <span data-ttu-id="8c9de-192">Los registros de escritorio, también conocidos como registros de arranque, contienen datos de registro que se producen entre el cliente de escritorio y el explorador.</span><span class="sxs-lookup"><span data-stu-id="8c9de-192">Desktop logs, also known as bootstrapper logs, contain log data that occurs between the desktop client and the browser.</span></span> <span data-ttu-id="8c9de-193">Al igual que los registros multimedia, estos registros solo son necesarios si Microsoft lo solicita.</span><span class="sxs-lookup"><span data-stu-id="8c9de-193">Like media logs, these logs are only needed if requested by Microsoft.</span></span> <span data-ttu-id="8c9de-194">Los registros están basados en texto y se pueden leer con cualquier editor basado en texto en un formato de arriba abajo.</span><span class="sxs-lookup"><span data-stu-id="8c9de-194">The logs are text-based and can be read using any text-based editor in a top-down format.</span></span>

<span data-ttu-id="8c9de-195">Para recopilar registros para Linux: Haga clic en el icono Microsoft Teams en la bandeja del sistema y seleccione **Obtener registros.**</span><span class="sxs-lookup"><span data-stu-id="8c9de-195">To collect logs for Linux: Click on the Microsoft Teams icon in your system tray, and select **Get Logs**.</span></span>
<span data-ttu-id="8c9de-196">Los archivos estarán disponibles en ~/.config/Microsoft/Microsoft Teams/logs.txt.</span><span class="sxs-lookup"><span data-stu-id="8c9de-196">The files will be available in ~/.config/Microsoft/Microsoft Teams/logs.txt.</span></span>  


## <a name="browser-trace"></a><span data-ttu-id="8c9de-197">Seguimiento del explorador</span><span class="sxs-lookup"><span data-stu-id="8c9de-197">Browser trace</span></span>

<span data-ttu-id="8c9de-198">Para algunas categorías de errores, es posible que el soporte técnico de Microsoft requiera que recopile un seguimiento del explorador.</span><span class="sxs-lookup"><span data-stu-id="8c9de-198">For some categories of errors, Microsoft Support might require you to collect a browser trace.</span></span> <span data-ttu-id="8c9de-199">Esta información puede proporcionar detalles importantes sobre el estado del Teams cliente cuando se produce el error.</span><span class="sxs-lookup"><span data-stu-id="8c9de-199">This information can provide important details about the state of the Teams client when the error occurs.</span></span>

<span data-ttu-id="8c9de-200">Antes de iniciar el seguimiento del explorador, asegúrese de que ha iniciado sesión en Teams.</span><span class="sxs-lookup"><span data-stu-id="8c9de-200">Before you start the browser trace, make sure that you’re signed in to Teams.</span></span> <span data-ttu-id="8c9de-201">Es importante hacer esto antes de iniciar el seguimiento para que el seguimiento no contenga información confidencial de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="8c9de-201">It's important to do this before you start the trace so that the trace doesn't contain sensitive sign-in information.</span></span>

<span data-ttu-id="8c9de-202">Después de haber iniciado sesión, seleccione uno de los vínculos siguientes, según corresponda para el explorador, y siga los pasos proporcionados.</span><span class="sxs-lookup"><span data-stu-id="8c9de-202">After you’re signed in, select one of the following links, as appropriate for your browser, and follow the provided steps.</span></span> 

-   [<span data-ttu-id="8c9de-203">Chrome & Edge (Chromium)</span><span class="sxs-lookup"><span data-stu-id="8c9de-203">Chrome & Edge (Chromium)</span></span>](/azure/azure-portal/capture-browser-trace#google-chrome-and-microsoft-edge-chromium?preserve-view=true#resolution)

-   [<span data-ttu-id="8c9de-204">Perimetral</span><span class="sxs-lookup"><span data-stu-id="8c9de-204">Edge</span></span>](/azure/azure-portal/capture-browser-trace#microsoft-edge-edgehtml?preserve-view=true#resolution)

-   [<span data-ttu-id="8c9de-205">Safari</span><span class="sxs-lookup"><span data-stu-id="8c9de-205">Safari</span></span>](/azure/azure-portal/capture-browser-trace#apple-safari?preserve-view=true#resolution)

-   [<span data-ttu-id="8c9de-206">Firefox</span><span class="sxs-lookup"><span data-stu-id="8c9de-206">Firefox</span></span>](/azure/azure-portal/capture-browser-trace#firefox?preserve-view=true#resolution)

> [!NOTE]
> <span data-ttu-id="8c9de-207">En los pasos, reemplace todas las referencias a Azure Portal por el Teams cliente.</span><span class="sxs-lookup"><span data-stu-id="8c9de-207">In the steps, replace all references to the Azure portal with the Teams client.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="8c9de-208">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="8c9de-208">Related topics</span></span>

[<span data-ttu-id="8c9de-209">Solución de problemas de Teams</span><span class="sxs-lookup"><span data-stu-id="8c9de-209">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)
