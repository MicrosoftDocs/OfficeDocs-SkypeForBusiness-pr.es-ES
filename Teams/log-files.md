---
title: Usar los archivos de registro para solucionar problemas en Microsoft Teams
ms.reviewer: tejeshs
author: LolaJacobsen
ms.author: lolaj
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
ms.openlocfilehash: 2303082c4f1c16a28a9116047d904a5d491a535a
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085756"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a><span data-ttu-id="4fd11-103">Usar los archivos de registro para solucionar problemas en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4fd11-103">Use log files in troubleshooting Microsoft Teams</span></span>
=================================================

<span data-ttu-id="4fd11-104">Hay tres tipos de archivos de registro que el cliente genera automáticamente y que pueden usarse para ayudar en la solución de problemas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="4fd11-104">There are three types of log files automatically produced by the client that can be leveraged to assist in troubleshooting Microsoft Teams.</span></span>

-   <span data-ttu-id="4fd11-105">Registros de depuración</span><span class="sxs-lookup"><span data-stu-id="4fd11-105">Debug logs</span></span>

-   <span data-ttu-id="4fd11-106">Registros de medios</span><span class="sxs-lookup"><span data-stu-id="4fd11-106">Media logs</span></span>

-   <span data-ttu-id="4fd11-107">Registros de escritorio</span><span class="sxs-lookup"><span data-stu-id="4fd11-107">Desktop logs</span></span>

<span data-ttu-id="4fd11-108">When creating a support request with Microsoft Support, the support engineer will require the debug logs.</span><span class="sxs-lookup"><span data-stu-id="4fd11-108">When creating a support request with Microsoft Support, the support engineer will require the debug logs.</span></span> <span data-ttu-id="4fd11-109">Having these logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem.</span><span class="sxs-lookup"><span data-stu-id="4fd11-109">Having these logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem.</span></span> <span data-ttu-id="4fd11-110">Media or desktop logs are only required if requested by Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4fd11-110">Media or desktop logs are only required if requested by Microsoft.</span></span>

<span data-ttu-id="4fd11-111">The following table outlines the various clients, and their associated logs.</span><span class="sxs-lookup"><span data-stu-id="4fd11-111">The following table outlines the various clients, and their associated logs.</span></span> <span data-ttu-id="4fd11-112">Log files are stored in locations specific to the client and operating system.</span><span class="sxs-lookup"><span data-stu-id="4fd11-112">Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="4fd11-113">Cliente</span><span class="sxs-lookup"><span data-stu-id="4fd11-113">Client</span></span> |<span data-ttu-id="4fd11-114">Depuración</span><span class="sxs-lookup"><span data-stu-id="4fd11-114">Debug</span></span>|<span data-ttu-id="4fd11-115">Escritorio</span><span class="sxs-lookup"><span data-stu-id="4fd11-115">Desktop</span></span>|<span data-ttu-id="4fd11-116">Medios</span><span class="sxs-lookup"><span data-stu-id="4fd11-116">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="4fd11-117">Web</span><span class="sxs-lookup"><span data-stu-id="4fd11-117">Web</span></span>    |<span data-ttu-id="4fd11-118">X</span><span class="sxs-lookup"><span data-stu-id="4fd11-118">X</span></span>         |-         |-         |
|<span data-ttu-id="4fd11-119">Windows</span><span class="sxs-lookup"><span data-stu-id="4fd11-119">Windows</span></span>     |<span data-ttu-id="4fd11-120">X</span><span class="sxs-lookup"><span data-stu-id="4fd11-120">X</span></span>         |<span data-ttu-id="4fd11-121">X</span><span class="sxs-lookup"><span data-stu-id="4fd11-121">X</span></span>         |<span data-ttu-id="4fd11-122">X</span><span class="sxs-lookup"><span data-stu-id="4fd11-122">X</span></span>         |
|<span data-ttu-id="4fd11-123">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="4fd11-123">Mac OSX</span></span>     |<span data-ttu-id="4fd11-124">X</span><span class="sxs-lookup"><span data-stu-id="4fd11-124">X</span></span>         |<span data-ttu-id="4fd11-125">X</span><span class="sxs-lookup"><span data-stu-id="4fd11-125">X</span></span>         |<span data-ttu-id="4fd11-126">X</span><span class="sxs-lookup"><span data-stu-id="4fd11-126">X</span></span>         |
|<span data-ttu-id="4fd11-127">Linux</span><span class="sxs-lookup"><span data-stu-id="4fd11-127">Linux</span></span>     |<span data-ttu-id="4fd11-128">X</span><span class="sxs-lookup"><span data-stu-id="4fd11-128">X</span></span>         |<span data-ttu-id="4fd11-129">X</span><span class="sxs-lookup"><span data-stu-id="4fd11-129">X</span></span>         |<span data-ttu-id="4fd11-130">X</span><span class="sxs-lookup"><span data-stu-id="4fd11-130">X</span></span>         |
|<span data-ttu-id="4fd11-131">iOS</span><span class="sxs-lookup"><span data-stu-id="4fd11-131">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="4fd11-132">Android</span><span class="sxs-lookup"><span data-stu-id="4fd11-132">Android</span></span>     |-         |-         |-         |

<span data-ttu-id="4fd11-133">Para ver una lista completa de los sistemas operativos y los exploradores compatibles, vea [Obtener clientes para Microsoft Teams](get-clients.md).</span><span class="sxs-lookup"><span data-stu-id="4fd11-133">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

<a name="debug-logs"></a><span data-ttu-id="4fd11-134">Registros de depuración</span><span class="sxs-lookup"><span data-stu-id="4fd11-134">Debug logs</span></span>
---------------------------

<span data-ttu-id="4fd11-135">Estos son los registros más comunes y son necesarios para todos los casos de soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4fd11-135">These are the most common logs and are required for all Microsoft support cases.</span></span> <span data-ttu-id="4fd11-136">Los registros de depuración los generan los clientes de escritorio de Windows y Mac, así como los clientes basados en explorador.</span><span class="sxs-lookup"><span data-stu-id="4fd11-136">Debug logs are produced by the Windows and Mac desktop clients, as well as browser based clients.</span></span> <span data-ttu-id="4fd11-137">Los registros se basan en texto y se leen de abajo hacia arriba.</span><span class="sxs-lookup"><span data-stu-id="4fd11-137">The logs are text based and are read from the bottom up.</span></span> <span data-ttu-id="4fd11-138">Se pueden leer con cualquier editor basado en texto y los nuevos registros se crean al iniciar sesión en el cliente.</span><span class="sxs-lookup"><span data-stu-id="4fd11-138">They can be read using any text based editor and new logs are created when logging into the client.</span></span>

<span data-ttu-id="4fd11-139">Los registros de depuración muestran los siguientes flujos de datos:</span><span class="sxs-lookup"><span data-stu-id="4fd11-139">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="4fd11-140">Inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="4fd11-140">Login</span></span>

-   <span data-ttu-id="4fd11-141">Solicitudes de conexión a servicios de nivel intermedio</span><span class="sxs-lookup"><span data-stu-id="4fd11-141">Connection requests to middle tier services</span></span>

-   <span data-ttu-id="4fd11-142">Llamada/conversación</span><span class="sxs-lookup"><span data-stu-id="4fd11-142">Call/conversation</span></span>

<span data-ttu-id="4fd11-143">Los registros de depuración se generan usando los siguientes métodos de SO específicos:</span><span class="sxs-lookup"><span data-stu-id="4fd11-143">The debug logs are produced using the following OS specific methods:</span></span>

-   <span data-ttu-id="4fd11-144">Windows:</span><span class="sxs-lookup"><span data-stu-id="4fd11-144">Windows:</span></span>

      <span data-ttu-id="4fd11-145">Método abreviado de teclado: Ctrl + Alt + Mayús + 1</span><span class="sxs-lookup"><span data-stu-id="4fd11-145">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

-   <span data-ttu-id="4fd11-146">Mac OSX:</span><span class="sxs-lookup"><span data-stu-id="4fd11-146">Mac OSX:</span></span>

      <span data-ttu-id="4fd11-147">Método abreviado de teclado: Opción + Comando + Mayús + 1</span><span class="sxs-lookup"><span data-stu-id="4fd11-147">Keyboard shortcut: Option + Command + Shift+1</span></span>

-   <span data-ttu-id="4fd11-148">Linux</span><span class="sxs-lookup"><span data-stu-id="4fd11-148">Linux:</span></span>

      <span data-ttu-id="4fd11-149">Método abreviado de teclado: Ctrl + Alt + Mayús + 1</span><span class="sxs-lookup"><span data-stu-id="4fd11-149">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

<span data-ttu-id="4fd11-150">Los registros de depuración se descargan automáticamente en las siguientes carpetas.</span><span class="sxs-lookup"><span data-stu-id="4fd11-150">The debug logs are automatically downloaded to the following folders.</span></span>

-   <span data-ttu-id="4fd11-151">Windows: %userprofile%\\Descargas</span><span class="sxs-lookup"><span data-stu-id="4fd11-151">Windows: %userprofile%\\Downloads</span></span>

-   <span data-ttu-id="4fd11-152">Mac OSX: Descargas</span><span class="sxs-lookup"><span data-stu-id="4fd11-152">Mac OSX: Downloads</span></span>

-   <span data-ttu-id="4fd11-153">Linux: ~/downloads</span><span class="sxs-lookup"><span data-stu-id="4fd11-153">Linux: ~/Downloads</span></span>

-   <span data-ttu-id="4fd11-154">Explorador: Se le pedirá que guarde el registro de depuración en la ubicación predeterminada.</span><span class="sxs-lookup"><span data-stu-id="4fd11-154">Browser: You will be prompted to save the debug log to default save location</span></span>

<a name="media-logs"></a><span data-ttu-id="4fd11-155">Registros de medios</span><span class="sxs-lookup"><span data-stu-id="4fd11-155">Media Logs</span></span>
---------------------------

<span data-ttu-id="4fd11-156">Media logs contain diagnostic data about audio, video and screen sharing.</span><span class="sxs-lookup"><span data-stu-id="4fd11-156">Media logs contain diagnostic data about audio, video and screen sharing.</span></span> <span data-ttu-id="4fd11-157">They are required for support cases only upon request and can only be inspected by Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4fd11-157">They are required for support cases only upon request and can only be inspected by Microsoft.</span></span> <span data-ttu-id="4fd11-158">The following table outlines the log location.</span><span class="sxs-lookup"><span data-stu-id="4fd11-158">The following table outlines the log location.</span></span>


|<span data-ttu-id="4fd11-159">Cliente</span><span class="sxs-lookup"><span data-stu-id="4fd11-159">Client</span></span> |<span data-ttu-id="4fd11-160">Ubicación</span><span class="sxs-lookup"><span data-stu-id="4fd11-160">Location</span></span> |
|---------|---------|
|<span data-ttu-id="4fd11-161">Windows</span><span class="sxs-lookup"><span data-stu-id="4fd11-161">Windows</span></span>     |<span data-ttu-id="4fd11-162">%appdata%\Microsoft\Teams\media-stack \\ \*. blog</span><span class="sxs-lookup"><span data-stu-id="4fd11-162">%appdata%\Microsoft\Teams\media-stack\\*.blog</span></span>         |
|            |<span data-ttu-id="4fd11-163">%appdata%\Microsoft\Teams\skylib \\ \*. blog</span><span class="sxs-lookup"><span data-stu-id="4fd11-163">%appdata%\Microsoft\Teams\skylib\\*.blog</span></span>
|            |<span data-ttu-id="4fd11-164">%appdata%\Microsoft\Teams\media-stack \\ \*. ETL</span><span class="sxs-lookup"><span data-stu-id="4fd11-164">%appdata%\Microsoft\Teams\media-stack\\*.etl</span></span>         |
|<span data-ttu-id="4fd11-165">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="4fd11-165">Mac OSX</span></span>     |<span data-ttu-id="4fd11-166">~/Library/Application Support/Microsoft/Teams/media-Stack/\*. blog</span><span class="sxs-lookup"><span data-stu-id="4fd11-166">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="4fd11-167">~/Library/Application Support/Microsoft/Teams/skylib/\*. blog</span><span class="sxs-lookup"><span data-stu-id="4fd11-167">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span></span>         |
|<span data-ttu-id="4fd11-168">Linux</span><span class="sxs-lookup"><span data-stu-id="4fd11-168">Linux</span></span>       |<span data-ttu-id="4fd11-169">~/.config/Microsoft/Microsoft Teams/media-Stack/\*. blog</span><span class="sxs-lookup"><span data-stu-id="4fd11-169">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="4fd11-170">~/.config/Microsoft/Microsoft Teams/skylib/\*. blog</span><span class="sxs-lookup"><span data-stu-id="4fd11-170">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span></span>         |



<a name="desktop-logs"></a><span data-ttu-id="4fd11-171">Registros de escritorio</span><span class="sxs-lookup"><span data-stu-id="4fd11-171">Desktop logs</span></span>
---------------------

<span data-ttu-id="4fd11-172">Desktop logs, also known as bootstrapper logs, contains log data that occurs between the desktop client and the browser.</span><span class="sxs-lookup"><span data-stu-id="4fd11-172">Desktop logs, also known as bootstrapper logs, contains log data that occurs between the desktop client and the browser.</span></span> <span data-ttu-id="4fd11-173">Like media logs, these logs are only needed if requested by Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4fd11-173">Like media logs, these logs are only needed if requested by Microsoft.</span></span> <span data-ttu-id="4fd11-174">The logs are text based and can be read using any text based editor in a top down format.</span><span class="sxs-lookup"><span data-stu-id="4fd11-174">The logs are text based and can be read using any text based editor in a top down format.</span></span>

<span data-ttu-id="4fd11-175">Windows:</span><span class="sxs-lookup"><span data-stu-id="4fd11-175">Windows:</span></span>

1.  <span data-ttu-id="4fd11-176">Haga clic con el botón derecho en el icono de **Microsoft Teams** de la bandeja del sistema y seleccione **obtener registros** .</span><span class="sxs-lookup"><span data-stu-id="4fd11-176">Right-click the **Microsoft Teams** icon in your system tray, select **Get Logs**</span></span>

<span data-ttu-id="4fd11-177">Mac OsX:</span><span class="sxs-lookup"><span data-stu-id="4fd11-177">Mac OsX:</span></span>

1.  <span data-ttu-id="4fd11-178">Elija **Obtener registros** en el menú desplegabe **Ayuda**.</span><span class="sxs-lookup"><span data-stu-id="4fd11-178">Choosing **Get Logs** from the **Help** pull-down menu</span></span>

<span data-ttu-id="4fd11-179">Linux</span><span class="sxs-lookup"><span data-stu-id="4fd11-179">Linux:</span></span>

1.  <span data-ttu-id="4fd11-180">Haga clic en el icono de **Microsoft Teams** de la bandeja del sistema y seleccione **obtener registros** .</span><span class="sxs-lookup"><span data-stu-id="4fd11-180">Click on the **Microsoft Teams** icon in your system tray, select **Get Logs**</span></span>

|<span data-ttu-id="4fd11-181">Cliente</span><span class="sxs-lookup"><span data-stu-id="4fd11-181">Client</span></span> |<span data-ttu-id="4fd11-182">Ubicación</span><span class="sxs-lookup"><span data-stu-id="4fd11-182">Location</span></span> |
|---------|---------|
|<span data-ttu-id="4fd11-183">Windows</span><span class="sxs-lookup"><span data-stu-id="4fd11-183">Windows</span></span>     |<span data-ttu-id="4fd11-184">% appdata% \Microsoft\Teams\logs.txt</span><span class="sxs-lookup"><span data-stu-id="4fd11-184">%appdata%\Microsoft\Teams\logs.txt</span></span>         |
|<span data-ttu-id="4fd11-185">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="4fd11-185">Mac OSX</span></span>     |<span data-ttu-id="4fd11-186">~/Library/Application Support/Microsoft/Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="4fd11-186">~/Library/Application Support/Microsoft/Teams/logs.txt</span></span>         |
|<span data-ttu-id="4fd11-187">Linux</span><span class="sxs-lookup"><span data-stu-id="4fd11-187">Linux</span></span>       |<span data-ttu-id="4fd11-188">~/.config/Microsoft/Microsoft Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="4fd11-188">~/.config/Microsoft/Microsoft Teams/logs.txt</span></span>         |


## <a name="related-topics"></a><span data-ttu-id="4fd11-189">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="4fd11-189">Related topics</span></span>

[<span data-ttu-id="4fd11-190">Solución de problemas de Teams</span><span class="sxs-lookup"><span data-stu-id="4fd11-190">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)

