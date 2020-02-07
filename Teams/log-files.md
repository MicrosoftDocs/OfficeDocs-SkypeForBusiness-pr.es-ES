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
ms.openlocfilehash: 2c8da7e60e785d765e77e17935b60382e864a83b
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41833380"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a><span data-ttu-id="7fc14-103">Usar los archivos de registro para solucionar problemas en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7fc14-103">Use log files in troubleshooting Microsoft Teams</span></span>
=================================================

<span data-ttu-id="7fc14-104">Hay tres tipos de archivos de registro que el cliente genera automáticamente y que pueden usarse para ayudar en la solución de problemas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7fc14-104">There are three types of log files automatically produced by the client that can be leveraged to assist in troubleshooting Microsoft Teams.</span></span>

-   <span data-ttu-id="7fc14-105">Registros de depuración</span><span class="sxs-lookup"><span data-stu-id="7fc14-105">Debug logs</span></span>

-   <span data-ttu-id="7fc14-106">Registros de medios</span><span class="sxs-lookup"><span data-stu-id="7fc14-106">Media logs</span></span>

-   <span data-ttu-id="7fc14-107">Registros de escritorio</span><span class="sxs-lookup"><span data-stu-id="7fc14-107">Desktop logs</span></span>

<span data-ttu-id="7fc14-p101">Cuando se crea una solicitud de soporte técnico con Soporte técnico de Microsoft, el ingeniero de soporte técnico necesitará los registros de depuración. Disponer de estos registros con antelación, antes de crear la solicitud de soporte técnico, permitirá a Microsoft empezar rápidamente a resolver el problema. Los registros de medios o de escritorio solo son necesarios si los solicita Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7fc14-p101">When creating a support request with Microsoft Support, the support engineer will require the debug logs. Having these logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem. Media or desktop logs are only required if requested by Microsoft.</span></span>

<span data-ttu-id="7fc14-p102">En esta table se muestran los distintos clientes y sus registros asociados. Los archivos de registro se almacenan en ubicaciones específicas del cliente y el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="7fc14-p102">The following table outlines the various clients, and their associated logs. Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="7fc14-113">Cliente</span><span class="sxs-lookup"><span data-stu-id="7fc14-113">Client</span></span> |<span data-ttu-id="7fc14-114">Depuración</span><span class="sxs-lookup"><span data-stu-id="7fc14-114">Debug</span></span>|<span data-ttu-id="7fc14-115">Escritorio</span><span class="sxs-lookup"><span data-stu-id="7fc14-115">Desktop</span></span>|<span data-ttu-id="7fc14-116">Medios</span><span class="sxs-lookup"><span data-stu-id="7fc14-116">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="7fc14-117">Web</span><span class="sxs-lookup"><span data-stu-id="7fc14-117">Web</span></span>    |<span data-ttu-id="7fc14-118">X</span><span class="sxs-lookup"><span data-stu-id="7fc14-118">X</span></span>         |-         |-         |
|<span data-ttu-id="7fc14-119">Windows</span><span class="sxs-lookup"><span data-stu-id="7fc14-119">Windows</span></span>     |<span data-ttu-id="7fc14-120">X</span><span class="sxs-lookup"><span data-stu-id="7fc14-120">X</span></span>         |<span data-ttu-id="7fc14-121">X</span><span class="sxs-lookup"><span data-stu-id="7fc14-121">X</span></span>         |<span data-ttu-id="7fc14-122">X</span><span class="sxs-lookup"><span data-stu-id="7fc14-122">X</span></span>         |
|<span data-ttu-id="7fc14-123">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="7fc14-123">Mac OSX</span></span>     |<span data-ttu-id="7fc14-124">X</span><span class="sxs-lookup"><span data-stu-id="7fc14-124">X</span></span>         |<span data-ttu-id="7fc14-125">X</span><span class="sxs-lookup"><span data-stu-id="7fc14-125">X</span></span>         |<span data-ttu-id="7fc14-126">X</span><span class="sxs-lookup"><span data-stu-id="7fc14-126">X</span></span>         |
|<span data-ttu-id="7fc14-127">iOS</span><span class="sxs-lookup"><span data-stu-id="7fc14-127">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="7fc14-128">Android</span><span class="sxs-lookup"><span data-stu-id="7fc14-128">Android</span></span>     |-         |-         |-         |

<span data-ttu-id="7fc14-129">Para ver una lista completa de los sistemas operativos y los exploradores compatibles, vea [Obtener clientes para Microsoft Teams](get-clients.md).</span><span class="sxs-lookup"><span data-stu-id="7fc14-129">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

<a name="debug-logs"></a><span data-ttu-id="7fc14-130">Registros de depuración</span><span class="sxs-lookup"><span data-stu-id="7fc14-130">Debug logs</span></span>
---------------------------

<span data-ttu-id="7fc14-131">Estos son los registros más comunes y son necesarios para todos los casos de soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7fc14-131">These are the most common logs and are required for all Microsoft support cases.</span></span> <span data-ttu-id="7fc14-132">Los registros de depuración los generan los clientes de escritorio de Windows y Mac, así como los clientes basados en explorador.</span><span class="sxs-lookup"><span data-stu-id="7fc14-132">Debug logs are produced by the Windows and Mac desktop clients, as well as browser based clients.</span></span> <span data-ttu-id="7fc14-133">Los registros se basan en texto y se leen de abajo hacia arriba.</span><span class="sxs-lookup"><span data-stu-id="7fc14-133">The logs are text based and are read from the bottom up.</span></span> <span data-ttu-id="7fc14-134">Se pueden leer con cualquier editor basado en texto y los nuevos registros se crean al iniciar sesión en el cliente.</span><span class="sxs-lookup"><span data-stu-id="7fc14-134">They can be read using any text based editor and new logs are created when logging into the client.</span></span>

<span data-ttu-id="7fc14-135">Los registros de depuración muestran los siguientes flujos de datos:</span><span class="sxs-lookup"><span data-stu-id="7fc14-135">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="7fc14-136">Inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="7fc14-136">Login</span></span>

-   <span data-ttu-id="7fc14-137">Solicitudes de conexión a servicios de nivel intermedio</span><span class="sxs-lookup"><span data-stu-id="7fc14-137">Connection requests to middle tier services</span></span>

-   <span data-ttu-id="7fc14-138">Llamada/conversación</span><span class="sxs-lookup"><span data-stu-id="7fc14-138">Call/conversation</span></span>

<span data-ttu-id="7fc14-139">Los registros de depuración se generan usando los siguientes métodos de SO específicos:</span><span class="sxs-lookup"><span data-stu-id="7fc14-139">The debug logs are produced using the following OS specific methods:</span></span>

-   <span data-ttu-id="7fc14-140">Windows:</span><span class="sxs-lookup"><span data-stu-id="7fc14-140">Windows:</span></span>

      <span data-ttu-id="7fc14-141">Método abreviado de teclado: Ctrl + Alt + Mayús + 1</span><span class="sxs-lookup"><span data-stu-id="7fc14-141">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

-   <span data-ttu-id="7fc14-142">Mac OSX:</span><span class="sxs-lookup"><span data-stu-id="7fc14-142">Mac OSX:</span></span>

      <span data-ttu-id="7fc14-143">Método abreviado de teclado: Opción + Comando + Mayús + 1</span><span class="sxs-lookup"><span data-stu-id="7fc14-143">Keyboard shortcut: Option + Command + Shift+1</span></span>

<span data-ttu-id="7fc14-144">Los registros de depuración se descargan automáticamente en las siguientes carpetas.</span><span class="sxs-lookup"><span data-stu-id="7fc14-144">The debug logs are automatically downloaded to the following folders.</span></span>

-   <span data-ttu-id="7fc14-145">Windows: %userprofile%\\Descargas</span><span class="sxs-lookup"><span data-stu-id="7fc14-145">Windows: %userprofile%\\Downloads</span></span>

-   <span data-ttu-id="7fc14-146">Mac OSX: Descargas</span><span class="sxs-lookup"><span data-stu-id="7fc14-146">Mac OSX: Downloads</span></span>

-   <span data-ttu-id="7fc14-147">Explorador: Se le pedirá que guarde el registro de depuración en la ubicación predeterminada.</span><span class="sxs-lookup"><span data-stu-id="7fc14-147">Browser: You will be prompted to save the debug log to default save location</span></span>

<a name="media-logs"></a><span data-ttu-id="7fc14-148">Registros de medios</span><span class="sxs-lookup"><span data-stu-id="7fc14-148">Media Logs</span></span>
---------------------------

<span data-ttu-id="7fc14-p104">Los registros de medios contienen datos de diagnóstico sobre el uso compartido de pantalla, audio, vídeo. Son necesarios para resolver casos de soporte técnico. Se generan únicamente bajo petición y solo pueden ser inspeccionados por Microsoft. En la siguiente tabla se muestra la ubicación del registro.</span><span class="sxs-lookup"><span data-stu-id="7fc14-p104">Media logs contain diagnostic data about audio, video and screen sharing. They are required for support cases only upon request and can only be inspected by Microsoft. The following table outlines the log location.</span></span>


|<span data-ttu-id="7fc14-152">Cliente</span><span class="sxs-lookup"><span data-stu-id="7fc14-152">Client</span></span> |<span data-ttu-id="7fc14-153">Ubicación</span><span class="sxs-lookup"><span data-stu-id="7fc14-153">Location</span></span> |
|---------|---------|
|<span data-ttu-id="7fc14-154">Windows</span><span class="sxs-lookup"><span data-stu-id="7fc14-154">Windows</span></span>     |<span data-ttu-id="7fc14-155">%appdata%\Microsoft\Teams\media-stack\\*. blog</span><span class="sxs-lookup"><span data-stu-id="7fc14-155">%appdata%\Microsoft\Teams\media-stack\\*.blog</span></span>         |
|            |<span data-ttu-id="7fc14-156">%appdata%\Microsoft\Teams\skylib\\*. blog</span><span class="sxs-lookup"><span data-stu-id="7fc14-156">%appdata%\Microsoft\Teams\skylib\\*.blog</span></span>
|            |<span data-ttu-id="7fc14-157">%appdata%\Microsoft\Teams\media-stack\\*. ETL</span><span class="sxs-lookup"><span data-stu-id="7fc14-157">%appdata%\Microsoft\Teams\media-stack\\*.etl</span></span>         |
|<span data-ttu-id="7fc14-158">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="7fc14-158">Mac OSX</span></span>     |<span data-ttu-id="7fc14-159">~/Library/Application Support/Microsoft/Teams/media-Stack/\*. blog</span><span class="sxs-lookup"><span data-stu-id="7fc14-159">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="7fc14-160">~/Library/Application Support/Microsoft/Teams/skylib/\*. blog</span><span class="sxs-lookup"><span data-stu-id="7fc14-160">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span></span>         |



<a name="desktop-logs"></a><span data-ttu-id="7fc14-161">Registros de escritorio</span><span class="sxs-lookup"><span data-stu-id="7fc14-161">Desktop logs</span></span>
---------------------

<span data-ttu-id="7fc14-p105">Los registros de escritorio, también conocidos como registros de programa previo, contienen datos de registro que se producen entre el cliente de escritorio y el explorador. Al igual que los registros de medios, estos registros solo son necesarios si los solicita Microsoft. Los registros son archivos de texto y se pueden leer con cualquier editor de texto de arriba abajo.</span><span class="sxs-lookup"><span data-stu-id="7fc14-p105">Desktop logs, also known as bootstrapper logs, contains log data that occurs between the desktop client and the browser. Like media logs, these logs are only needed if requested by Microsoft. The logs are text based and can be read using any text based editor in a top down format.</span></span>

<span data-ttu-id="7fc14-165">Windows:</span><span class="sxs-lookup"><span data-stu-id="7fc14-165">Windows:</span></span>

1.  <span data-ttu-id="7fc14-166">Haga clic con el botón secundario en el **icono de Microsoft Teams** en la bandeja de la aplicación y seleccione **Obtener registros**.</span><span class="sxs-lookup"><span data-stu-id="7fc14-166">Right-click **the Microsoft Teams icon in** your application tray, select **Get Logs**</span></span>

<span data-ttu-id="7fc14-167">Mac OsX:</span><span class="sxs-lookup"><span data-stu-id="7fc14-167">Mac OsX:</span></span>

1.  <span data-ttu-id="7fc14-168">Elija **Obtener registros** en el menú desplegabe **Ayuda**.</span><span class="sxs-lookup"><span data-stu-id="7fc14-168">Choosing **Get Logs** from the **Help** pull-down menu</span></span>

|<span data-ttu-id="7fc14-169">Cliente</span><span class="sxs-lookup"><span data-stu-id="7fc14-169">Client</span></span> |<span data-ttu-id="7fc14-170">Ubicación</span><span class="sxs-lookup"><span data-stu-id="7fc14-170">Location</span></span> |
|---------|---------|
|<span data-ttu-id="7fc14-171">Windows</span><span class="sxs-lookup"><span data-stu-id="7fc14-171">Windows</span></span>     |<span data-ttu-id="7fc14-172">%appdata%\Microsoft\Teams\logs.txt</span><span class="sxs-lookup"><span data-stu-id="7fc14-172">%appdata%\Microsoft\Teams\logs.txt</span></span>         |
|<span data-ttu-id="7fc14-173">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="7fc14-173">Mac OSX</span></span>     |<span data-ttu-id="7fc14-174">~/Library/Application Support/Microsoft/Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="7fc14-174">~/Library/Application Support/Microsoft/Teams/logs.txt</span></span>         |
