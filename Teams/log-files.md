---
title: Usar los archivos de registro para solucionar problemas en Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Conozca los registros de depuración, medios y escritorio generados por Microsoft Teams, dónde se encuentran y cómo pueden ser útiles para resolver problemas.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2325532126c11e397b7aec5a6ed040b71aa659b0
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23849942"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a><span data-ttu-id="a86d2-103">Usar los archivos de registro para solucionar problemas en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a86d2-103">Use log files in troubleshooting Microsoft Teams</span></span>
=================================================

<span data-ttu-id="a86d2-104">Hay tres tipos de archivos de registro que el cliente genera automáticamente y que pueden usarse para ayudar en la solución de problemas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a86d2-104">There are three types of log files automatically produced by the client that can be leveraged to assist in troubleshooting Microsoft Teams.</span></span>

-   <span data-ttu-id="a86d2-105">Registros de depuración</span><span class="sxs-lookup"><span data-stu-id="a86d2-105">Debug logs</span></span>

-   <span data-ttu-id="a86d2-106">Registros de medios</span><span class="sxs-lookup"><span data-stu-id="a86d2-106">Media logs</span></span>

-   <span data-ttu-id="a86d2-107">Registros de escritorio</span><span class="sxs-lookup"><span data-stu-id="a86d2-107">Desktop logs</span></span>

<span data-ttu-id="a86d2-p101">Cuando se crea una solicitud de soporte técnico con Soporte técnico de Microsoft, el ingeniero de soporte técnico necesitará los registros de depuración. Disponer de estos registros con antelación, antes de crear la solicitud de soporte técnico, permitirá a Microsoft empezar rápidamente a resolver el problema. Los registros de medios o de escritorio solo son necesarios si los solicita Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a86d2-p101">When creating a support request with Microsoft Support, the support engineer will require the debug logs. Having these logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem. Media or desktop logs are only required if requested by Microsoft.</span></span>

<span data-ttu-id="a86d2-p102">En esta table se muestran los distintos clientes y sus registros asociados. Los archivos de registro se almacenan en ubicaciones específicas del cliente y el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="a86d2-p102">The following table outlines the various clients, and their associated logs. Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="a86d2-113">Cliente</span><span class="sxs-lookup"><span data-stu-id="a86d2-113">Client</span></span> |<span data-ttu-id="a86d2-114">Depuración</span><span class="sxs-lookup"><span data-stu-id="a86d2-114">Debug</span></span>|<span data-ttu-id="a86d2-115">Escritorio</span><span class="sxs-lookup"><span data-stu-id="a86d2-115">Desktop</span></span>|<span data-ttu-id="a86d2-116">Medios</span><span class="sxs-lookup"><span data-stu-id="a86d2-116">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="a86d2-117">Web</span><span class="sxs-lookup"><span data-stu-id="a86d2-117">Web</span></span>    |<span data-ttu-id="a86d2-118">X</span><span class="sxs-lookup"><span data-stu-id="a86d2-118">X</span></span>         |-         |-         |
|<span data-ttu-id="a86d2-119">Windows</span><span class="sxs-lookup"><span data-stu-id="a86d2-119">Windows</span></span>     |<span data-ttu-id="a86d2-120">X</span><span class="sxs-lookup"><span data-stu-id="a86d2-120">X</span></span>         |<span data-ttu-id="a86d2-121">X</span><span class="sxs-lookup"><span data-stu-id="a86d2-121">X</span></span>         |<span data-ttu-id="a86d2-122">X</span><span class="sxs-lookup"><span data-stu-id="a86d2-122">X</span></span>         |
|<span data-ttu-id="a86d2-123">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="a86d2-123">Mac OSX</span></span>     |<span data-ttu-id="a86d2-124">X</span><span class="sxs-lookup"><span data-stu-id="a86d2-124">X</span></span>         |<span data-ttu-id="a86d2-125">X</span><span class="sxs-lookup"><span data-stu-id="a86d2-125">X</span></span>         |<span data-ttu-id="a86d2-126">X</span><span class="sxs-lookup"><span data-stu-id="a86d2-126">X</span></span>         |
|<span data-ttu-id="a86d2-127">iOS</span><span class="sxs-lookup"><span data-stu-id="a86d2-127">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="a86d2-128">Android</span><span class="sxs-lookup"><span data-stu-id="a86d2-128">Android</span></span>     |-         |-         |-         |
|<span data-ttu-id="a86d2-129">Windows Phone</span><span class="sxs-lookup"><span data-stu-id="a86d2-129">Windows Phone</span></span>     |-         |-         |-         |

<span data-ttu-id="a86d2-130">Para ver una lista completa de los sistemas operativos y los exploradores compatibles, vea [Obtener clientes para Microsoft Teams](get-clients.md).</span><span class="sxs-lookup"><span data-stu-id="a86d2-130">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

<a name="debug-logs"></a><span data-ttu-id="a86d2-131">Registros de depuración</span><span class="sxs-lookup"><span data-stu-id="a86d2-131">Debug logs</span></span>
---------------------------

<span data-ttu-id="a86d2-p103">Estos son los registros más comunes y se necesitan para todos los casos de soporte técnico de Microsoft. Los registros de depuración los generan los clientes de escritorio de Windows y Mac, así como los clientes basados en exploradores. Los registros están basados en texto y se leen de arriba abajo. Pueden leerse con cualquier editor de textos y los nuevos registros se crean cuando se inicia sesión en el cliente.</span><span class="sxs-lookup"><span data-stu-id="a86d2-p103">These are the most common logs and are required for all Microsoft support cases. Debug logs are produced by the Window and Mac desktop clients, as well as browser based clients. The logs are text based and are read from the bottom up. They can be read using any text based editor and new logs are created when logging into the client.</span></span>

<span data-ttu-id="a86d2-136">Los registros de depuración muestran los siguientes flujos de datos:</span><span class="sxs-lookup"><span data-stu-id="a86d2-136">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="a86d2-137">Inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="a86d2-137">Login</span></span>

-   <span data-ttu-id="a86d2-138">Solicitudes de conexión a servicios de nivel intermedio</span><span class="sxs-lookup"><span data-stu-id="a86d2-138">Connection requests to middle tier services</span></span>

-   <span data-ttu-id="a86d2-139">Llamada/conversación</span><span class="sxs-lookup"><span data-stu-id="a86d2-139">Call/conversation</span></span>

<span data-ttu-id="a86d2-140">Los registros de depuración se generan usando los siguientes métodos de SO específicos:</span><span class="sxs-lookup"><span data-stu-id="a86d2-140">The debug logs are produced using the following OS specific methods:</span></span>

-   <span data-ttu-id="a86d2-141">Windows:</span><span class="sxs-lookup"><span data-stu-id="a86d2-141">Windows:</span></span>

    1.  <span data-ttu-id="a86d2-142">Haga clic con el botón secundario en el **icono de Microsoft Teams** en la bandeja de la aplicación y seleccione **Obtener registros**.</span><span class="sxs-lookup"><span data-stu-id="a86d2-142">Right-click **the Microsoft Teams icon in** your application tray, select **Get Logs**</span></span>

    2.  <span data-ttu-id="a86d2-143">Elija **Obtener registros** en el menú desplegabe **Ayuda**.</span><span class="sxs-lookup"><span data-stu-id="a86d2-143">Choosing **Get Logs** from the **Help** pull-down menu</span></span>

    3.  <span data-ttu-id="a86d2-144">Método abreviado de teclado: Ctrl + Alt + Mayús + 1</span><span class="sxs-lookup"><span data-stu-id="a86d2-144">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

-   <span data-ttu-id="a86d2-145">Mac OSX:</span><span class="sxs-lookup"><span data-stu-id="a86d2-145">Mac OSX:</span></span>

    1.  <span data-ttu-id="a86d2-146">Elija **Obtener registros** en el menú desplegabe **Ayuda**.</span><span class="sxs-lookup"><span data-stu-id="a86d2-146">Choosing **Get Logs** from the **Help** pull-down menu</span></span>

    2.  <span data-ttu-id="a86d2-147">Método abreviado de teclado: Opción + Comando + Mayús + 1</span><span class="sxs-lookup"><span data-stu-id="a86d2-147">Keyboard shortcut: Option + Command + Shift+1</span></span>

<span data-ttu-id="a86d2-148">Los registros de depuración se descargan automáticamente en las siguientes carpetas.</span><span class="sxs-lookup"><span data-stu-id="a86d2-148">The debug logs are automatically downloaded to the following folders.</span></span>

-   <span data-ttu-id="a86d2-149">Windows: %userprofile%\\Descargas</span><span class="sxs-lookup"><span data-stu-id="a86d2-149">Windows: %userprofile%\\Downloads</span></span>

-   <span data-ttu-id="a86d2-150">Mac OSX: Descargas</span><span class="sxs-lookup"><span data-stu-id="a86d2-150">Mac OSX: Downloads</span></span>

-   <span data-ttu-id="a86d2-151">Explorador: Se le pedirá que guarde el registro de depuración en la ubicación predeterminada.</span><span class="sxs-lookup"><span data-stu-id="a86d2-151">Browser: You will be prompted to save the debug log to default save location</span></span>

<a name="media-logs"></a><span data-ttu-id="a86d2-152">Registros de medios</span><span class="sxs-lookup"><span data-stu-id="a86d2-152">Media Logs</span></span>
---------------------------

<span data-ttu-id="a86d2-p104">Los registros de medios contienen datos de diagnóstico sobre el uso compartido de pantalla, audio, vídeo. Son necesarios para resolver casos de soporte técnico. Se generan únicamente bajo petición y solo pueden ser inspeccionados por Microsoft. En la siguiente tabla se muestra la ubicación del registro.</span><span class="sxs-lookup"><span data-stu-id="a86d2-p104">Media logs contain diagnostic data about audio, video and screen sharing. They are required for support cases only upon request and can only be inspected by Microsoft. The following table outlines the log location.</span></span>


|<span data-ttu-id="a86d2-156">Cliente</span><span class="sxs-lookup"><span data-stu-id="a86d2-156">Client</span></span> |<span data-ttu-id="a86d2-157">Ubicación</span><span class="sxs-lookup"><span data-stu-id="a86d2-157">Location</span></span> |
|---------|---------|
|<span data-ttu-id="a86d2-158">Windows</span><span class="sxs-lookup"><span data-stu-id="a86d2-158">Windows</span></span>     |<span data-ttu-id="a86d2-159">%AppData%\Microsoft\Teams\media-Stack\*.etl</span><span class="sxs-lookup"><span data-stu-id="a86d2-159">%appdata%\Microsoft\Teams\media-stack\*.etl</span></span>         |
|<span data-ttu-id="a86d2-160">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="a86d2-160">Mac OSX</span></span>     |<span data-ttu-id="a86d2-161">~/Library/Application Support/Microsoft/Teams/media-stack\*.blog</span><span class="sxs-lookup"><span data-stu-id="a86d2-161">~/Library/Application Support/Microsoft/Teams/media-stack\*.blog</span></span>         |


<a name="desktop-logs"></a><span data-ttu-id="a86d2-162">Registros de escritorio</span><span class="sxs-lookup"><span data-stu-id="a86d2-162">Desktop logs</span></span>
---------------------

<span data-ttu-id="a86d2-p105">Los registros de escritorio, también conocidos como registros de programa previo, contienen datos de registro que se producen entre el cliente de escritorio y el explorador. Al igual que los registros de medios, estos registros solo son necesarios si los solicita Microsoft. Los registros son archivos de texto y se pueden leer con cualquier editor de texto de arriba abajo.</span><span class="sxs-lookup"><span data-stu-id="a86d2-p105">Desktop logs, also known as bootstrapper logs, contains log data that occurs between the desktop client and the browser. Like media logs, these logs are only needed if requested by Microsoft. The logs are text based and can be read using any text based editor in a top down format.</span></span>

|<span data-ttu-id="a86d2-166">Cliente</span><span class="sxs-lookup"><span data-stu-id="a86d2-166">Client</span></span> |<span data-ttu-id="a86d2-167">Ubicación</span><span class="sxs-lookup"><span data-stu-id="a86d2-167">Location</span></span> |
|---------|---------|
|<span data-ttu-id="a86d2-168">Windows</span><span class="sxs-lookup"><span data-stu-id="a86d2-168">Windows</span></span>     |<span data-ttu-id="a86d2-169">%AppData%\Microsoft\Teams\logs.txt</span><span class="sxs-lookup"><span data-stu-id="a86d2-169">%appdata%\Microsoft\Teams\logs.txt</span></span>         |
|<span data-ttu-id="a86d2-170">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="a86d2-170">Mac OSX</span></span>     |<span data-ttu-id="a86d2-171">~/Library/Application Support/Microsoft/Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="a86d2-171">~/Library/Application Support/Microsoft/Teams/logs.txt</span></span>         |
