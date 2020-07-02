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
ms.openlocfilehash: 7ad44af297cdfe375f28485e1c4c4e223f616666
ms.sourcegitcommit: a94a267c421a78587b0dbbea5fa167aad2882e9b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "45012196"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a><span data-ttu-id="b5391-103">Usar los archivos de registro para solucionar problemas en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b5391-103">Use log files in troubleshooting Microsoft Teams</span></span>
=================================================

<span data-ttu-id="b5391-104">Hay tres tipos de archivos de registro que el cliente genera automáticamente y que pueden usarse para ayudar en la solución de problemas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b5391-104">There are three types of log files automatically produced by the client that can be leveraged to assist in troubleshooting Microsoft Teams.</span></span>

-   <span data-ttu-id="b5391-105">Registros de depuración</span><span class="sxs-lookup"><span data-stu-id="b5391-105">Debug logs</span></span>

-   <span data-ttu-id="b5391-106">Registros de medios</span><span class="sxs-lookup"><span data-stu-id="b5391-106">Media logs</span></span>

-   <span data-ttu-id="b5391-107">Registros de escritorio</span><span class="sxs-lookup"><span data-stu-id="b5391-107">Desktop logs</span></span>

<span data-ttu-id="b5391-108">When creating a support request with Microsoft Support, the support engineer will require the debug logs.</span><span class="sxs-lookup"><span data-stu-id="b5391-108">When creating a support request with Microsoft Support, the support engineer will require the debug logs.</span></span> <span data-ttu-id="b5391-109">Having these logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem.</span><span class="sxs-lookup"><span data-stu-id="b5391-109">Having these logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem.</span></span> <span data-ttu-id="b5391-110">Media or desktop logs are only required if requested by Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b5391-110">Media or desktop logs are only required if requested by Microsoft.</span></span>

<span data-ttu-id="b5391-111">The following table outlines the various clients, and their associated logs.</span><span class="sxs-lookup"><span data-stu-id="b5391-111">The following table outlines the various clients, and their associated logs.</span></span> <span data-ttu-id="b5391-112">Log files are stored in locations specific to the client and operating system.</span><span class="sxs-lookup"><span data-stu-id="b5391-112">Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="b5391-113">Cliente</span><span class="sxs-lookup"><span data-stu-id="b5391-113">Client</span></span> |<span data-ttu-id="b5391-114">Depuración</span><span class="sxs-lookup"><span data-stu-id="b5391-114">Debug</span></span>|<span data-ttu-id="b5391-115">Escritorio</span><span class="sxs-lookup"><span data-stu-id="b5391-115">Desktop</span></span>|<span data-ttu-id="b5391-116">Medios</span><span class="sxs-lookup"><span data-stu-id="b5391-116">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="b5391-117">Web</span><span class="sxs-lookup"><span data-stu-id="b5391-117">Web</span></span>    |<span data-ttu-id="b5391-118">X</span><span class="sxs-lookup"><span data-stu-id="b5391-118">X</span></span>         |-         |-         |
|<span data-ttu-id="b5391-119">Windows</span><span class="sxs-lookup"><span data-stu-id="b5391-119">Windows</span></span>     |<span data-ttu-id="b5391-120">X</span><span class="sxs-lookup"><span data-stu-id="b5391-120">X</span></span>         |<span data-ttu-id="b5391-121">X</span><span class="sxs-lookup"><span data-stu-id="b5391-121">X</span></span>         |<span data-ttu-id="b5391-122">X</span><span class="sxs-lookup"><span data-stu-id="b5391-122">X</span></span>         |
|<span data-ttu-id="b5391-123">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="b5391-123">Mac OSX</span></span>     |<span data-ttu-id="b5391-124">X</span><span class="sxs-lookup"><span data-stu-id="b5391-124">X</span></span>         |<span data-ttu-id="b5391-125">X</span><span class="sxs-lookup"><span data-stu-id="b5391-125">X</span></span>         |<span data-ttu-id="b5391-126">X</span><span class="sxs-lookup"><span data-stu-id="b5391-126">X</span></span>         |
|<span data-ttu-id="b5391-127">Linux</span><span class="sxs-lookup"><span data-stu-id="b5391-127">Linux</span></span>     |<span data-ttu-id="b5391-128">X</span><span class="sxs-lookup"><span data-stu-id="b5391-128">X</span></span>         |<span data-ttu-id="b5391-129">X</span><span class="sxs-lookup"><span data-stu-id="b5391-129">X</span></span>         |<span data-ttu-id="b5391-130">X</span><span class="sxs-lookup"><span data-stu-id="b5391-130">X</span></span>         |
|<span data-ttu-id="b5391-131">iOS</span><span class="sxs-lookup"><span data-stu-id="b5391-131">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="b5391-132">Android</span><span class="sxs-lookup"><span data-stu-id="b5391-132">Android</span></span>     |-         |-         |-         |

<span data-ttu-id="b5391-133">Para ver una lista completa de los sistemas operativos y los exploradores compatibles, vea [Obtener clientes para Microsoft Teams](get-clients.md).</span><span class="sxs-lookup"><span data-stu-id="b5391-133">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

<a name="debug-logs"></a><span data-ttu-id="b5391-134">Registros de depuración</span><span class="sxs-lookup"><span data-stu-id="b5391-134">Debug logs</span></span>
---------------------------

<span data-ttu-id="b5391-135">Estos son los registros más comunes y son necesarios para todos los casos de soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b5391-135">These are the most common logs and are required for all Microsoft support cases.</span></span> <span data-ttu-id="b5391-136">Los registros de depuración los generan los clientes de escritorio de Windows y Mac, así como los clientes basados en explorador.</span><span class="sxs-lookup"><span data-stu-id="b5391-136">Debug logs are produced by the Windows and Mac desktop clients, as well as browser based clients.</span></span> <span data-ttu-id="b5391-137">Los registros se basan en texto y se leen de abajo hacia arriba.</span><span class="sxs-lookup"><span data-stu-id="b5391-137">The logs are text based and are read from the bottom up.</span></span> <span data-ttu-id="b5391-138">Se pueden leer con cualquier editor basado en texto y los nuevos registros se crean al iniciar sesión en el cliente.</span><span class="sxs-lookup"><span data-stu-id="b5391-138">They can be read using any text based editor and new logs are created when logging into the client.</span></span>

<span data-ttu-id="b5391-139">Los registros de depuración muestran los siguientes flujos de datos:</span><span class="sxs-lookup"><span data-stu-id="b5391-139">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="b5391-140">Inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="b5391-140">Login</span></span>

-   <span data-ttu-id="b5391-141">Solicitudes de conexión a servicios de nivel intermedio</span><span class="sxs-lookup"><span data-stu-id="b5391-141">Connection requests to middle tier services</span></span>

-   <span data-ttu-id="b5391-142">Llamada/conversación</span><span class="sxs-lookup"><span data-stu-id="b5391-142">Call/conversation</span></span>

<span data-ttu-id="b5391-143">Los registros de depuración se generan usando los siguientes métodos de SO específicos:</span><span class="sxs-lookup"><span data-stu-id="b5391-143">The debug logs are produced using the following OS specific methods:</span></span>

-   <span data-ttu-id="b5391-144">Windows:</span><span class="sxs-lookup"><span data-stu-id="b5391-144">Windows:</span></span>

      <span data-ttu-id="b5391-145">Método abreviado de teclado: Ctrl + Alt + Mayús + 1</span><span class="sxs-lookup"><span data-stu-id="b5391-145">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

-   <span data-ttu-id="b5391-146">Mac OSX:</span><span class="sxs-lookup"><span data-stu-id="b5391-146">Mac OSX:</span></span>

      <span data-ttu-id="b5391-147">Método abreviado de teclado: Opción + Comando + Mayús + 1</span><span class="sxs-lookup"><span data-stu-id="b5391-147">Keyboard shortcut: Option + Command + Shift+1</span></span>

-   <span data-ttu-id="b5391-148">Linux</span><span class="sxs-lookup"><span data-stu-id="b5391-148">Linux:</span></span>

      <span data-ttu-id="b5391-149">Método abreviado de teclado: Ctrl + Alt + Mayús + 1</span><span class="sxs-lookup"><span data-stu-id="b5391-149">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

<span data-ttu-id="b5391-150">Los registros de depuración se descargan automáticamente en las siguientes carpetas.</span><span class="sxs-lookup"><span data-stu-id="b5391-150">The debug logs are automatically downloaded to the following folders.</span></span>

-   <span data-ttu-id="b5391-151">Windows: %userprofile%\\Descargas</span><span class="sxs-lookup"><span data-stu-id="b5391-151">Windows: %userprofile%\\Downloads</span></span>

-   <span data-ttu-id="b5391-152">Mac OSX: Descargas</span><span class="sxs-lookup"><span data-stu-id="b5391-152">Mac OSX: Downloads</span></span>

-   <span data-ttu-id="b5391-153">Linux: ~/downloads</span><span class="sxs-lookup"><span data-stu-id="b5391-153">Linux: ~/Downloads</span></span>

-   <span data-ttu-id="b5391-154">Explorador: Se le pedirá que guarde el registro de depuración en la ubicación predeterminada.</span><span class="sxs-lookup"><span data-stu-id="b5391-154">Browser: You will be prompted to save the debug log to default save location</span></span>

<a name="media-logs"></a><span data-ttu-id="b5391-155">Registros de medios</span><span class="sxs-lookup"><span data-stu-id="b5391-155">Media Logs</span></span>
---------------------------

<span data-ttu-id="b5391-156">Media logs contain diagnostic data about audio, video and screen sharing.</span><span class="sxs-lookup"><span data-stu-id="b5391-156">Media logs contain diagnostic data about audio, video and screen sharing.</span></span> <span data-ttu-id="b5391-157">They are required for support cases only upon request and can only be inspected by Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b5391-157">They are required for support cases only upon request and can only be inspected by Microsoft.</span></span> <span data-ttu-id="b5391-158">The following table outlines the log location.</span><span class="sxs-lookup"><span data-stu-id="b5391-158">The following table outlines the log location.</span></span>


|<span data-ttu-id="b5391-159">Cliente</span><span class="sxs-lookup"><span data-stu-id="b5391-159">Client</span></span> |<span data-ttu-id="b5391-160">Ubicación</span><span class="sxs-lookup"><span data-stu-id="b5391-160">Location</span></span> |
|---------|---------|
|<span data-ttu-id="b5391-161">Windows</span><span class="sxs-lookup"><span data-stu-id="b5391-161">Windows</span></span>     |<span data-ttu-id="b5391-162">%appdata%\Microsoft\Teams\media-stack \\ \*. blog</span><span class="sxs-lookup"><span data-stu-id="b5391-162">%appdata%\Microsoft\Teams\media-stack\\*.blog</span></span>         |
|            |<span data-ttu-id="b5391-163">%appdata%\Microsoft\Teams\skylib \\ \*. blog</span><span class="sxs-lookup"><span data-stu-id="b5391-163">%appdata%\Microsoft\Teams\skylib\\*.blog</span></span>
|            |<span data-ttu-id="b5391-164">%appdata%\Microsoft\Teams\media-stack \\ \*. ETL</span><span class="sxs-lookup"><span data-stu-id="b5391-164">%appdata%\Microsoft\Teams\media-stack\\*.etl</span></span>         |
|<span data-ttu-id="b5391-165">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="b5391-165">Mac OSX</span></span>     |<span data-ttu-id="b5391-166">~/Library/Application Support/Microsoft/Teams/media-Stack/\*. blog</span><span class="sxs-lookup"><span data-stu-id="b5391-166">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="b5391-167">~/Library/Application Support/Microsoft/Teams/skylib/\*. blog</span><span class="sxs-lookup"><span data-stu-id="b5391-167">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span></span>         |
|<span data-ttu-id="b5391-168">Linux</span><span class="sxs-lookup"><span data-stu-id="b5391-168">Linux</span></span>       |<span data-ttu-id="b5391-169">~/.config/Microsoft/Microsoft Teams/media-Stack/\*. blog</span><span class="sxs-lookup"><span data-stu-id="b5391-169">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="b5391-170">~/.config/Microsoft/Microsoft Teams/skylib/\*. blog</span><span class="sxs-lookup"><span data-stu-id="b5391-170">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span></span>         |



<a name="desktop-logs"></a><span data-ttu-id="b5391-171">Registros de escritorio</span><span class="sxs-lookup"><span data-stu-id="b5391-171">Desktop logs</span></span>
---------------------

<span data-ttu-id="b5391-172">Desktop logs, also known as bootstrapper logs, contains log data that occurs between the desktop client and the browser.</span><span class="sxs-lookup"><span data-stu-id="b5391-172">Desktop logs, also known as bootstrapper logs, contains log data that occurs between the desktop client and the browser.</span></span> <span data-ttu-id="b5391-173">Like media logs, these logs are only needed if requested by Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b5391-173">Like media logs, these logs are only needed if requested by Microsoft.</span></span> <span data-ttu-id="b5391-174">The logs are text based and can be read using any text based editor in a top down format.</span><span class="sxs-lookup"><span data-stu-id="b5391-174">The logs are text based and can be read using any text based editor in a top down format.</span></span>

<span data-ttu-id="b5391-175">Windows:</span><span class="sxs-lookup"><span data-stu-id="b5391-175">Windows:</span></span>

1.  <span data-ttu-id="b5391-176">Haga clic con el botón derecho en el icono de **Microsoft Teams** de la bandeja del sistema y seleccione **obtener registros** .</span><span class="sxs-lookup"><span data-stu-id="b5391-176">Right-click the **Microsoft Teams** icon in your system tray, select **Get Logs**</span></span>

<span data-ttu-id="b5391-177">Mac OsX:</span><span class="sxs-lookup"><span data-stu-id="b5391-177">Mac OsX:</span></span>

1.  <span data-ttu-id="b5391-178">Elija **Obtener registros** en el menú desplegabe **Ayuda**.</span><span class="sxs-lookup"><span data-stu-id="b5391-178">Choosing **Get Logs** from the **Help** pull-down menu</span></span>

<span data-ttu-id="b5391-179">Linux</span><span class="sxs-lookup"><span data-stu-id="b5391-179">Linux:</span></span>

1.  <span data-ttu-id="b5391-180">Haga clic en el icono de **Microsoft Teams** de la bandeja del sistema y seleccione **obtener registros** .</span><span class="sxs-lookup"><span data-stu-id="b5391-180">Click on the **Microsoft Teams** icon in your system tray, select **Get Logs**</span></span>

|<span data-ttu-id="b5391-181">Cliente</span><span class="sxs-lookup"><span data-stu-id="b5391-181">Client</span></span> |<span data-ttu-id="b5391-182">Ubicación</span><span class="sxs-lookup"><span data-stu-id="b5391-182">Location</span></span> |
|---------|---------|
|<span data-ttu-id="b5391-183">Windows</span><span class="sxs-lookup"><span data-stu-id="b5391-183">Windows</span></span>     |<span data-ttu-id="b5391-184">% appdata% \Microsoft\Teams\logs.txt</span><span class="sxs-lookup"><span data-stu-id="b5391-184">%appdata%\Microsoft\Teams\logs.txt</span></span>         |
|<span data-ttu-id="b5391-185">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="b5391-185">Mac OSX</span></span>     |<span data-ttu-id="b5391-186">~/Library/Application Support/Microsoft/Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="b5391-186">~/Library/Application Support/Microsoft/Teams/logs.txt</span></span>         |
|<span data-ttu-id="b5391-187">Linux</span><span class="sxs-lookup"><span data-stu-id="b5391-187">Linux</span></span>       |<span data-ttu-id="b5391-188">~/.config/Microsoft/Microsoft Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="b5391-188">~/.config/Microsoft/Microsoft Teams/logs.txt</span></span>         |
