---
title: 'Lync Server 2013: tareas necesarias'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: As-needed tasks
ms:assetid: b66bc6fe-f138-4cf4-ba7f-aee9a3e0497e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn722431(v=OCS.15)
ms:contentKeyID: 63969643
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 344512a1dd4db44b8290efdcc726275b4a6898de
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738410"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="as-needed-tasks-in-lync-server-2013"></a><span data-ttu-id="d896e-102">Tareas necesarias en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d896e-102">As-needed tasks in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d896e-103">_**Última modificación del tema:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="d896e-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="d896e-104">Realice las siguientes tareas según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="d896e-104">Perform the following tasks as necessary.</span></span> <span data-ttu-id="d896e-105">Suelen estar cubiertos por procedimientos estándar:</span><span class="sxs-lookup"><span data-stu-id="d896e-105">They are frequently also covered by standard procedures:</span></span>

  - <span data-ttu-id="d896e-106">**Auditoría de seguridad completa   ** Puede realizar esta auditoría regularmente, en respuesta a una actualización o un nuevo diseño del sistema de mensajería, o en respuesta a una infracción de seguridad intentada (o exitosa).</span><span class="sxs-lookup"><span data-stu-id="d896e-106">**Full Security Auditing   **You can perform this audit regularly, in response to an upgrade or redesign of the messaging system, or in response to an attempted (or successful) security breach.</span></span> <span data-ttu-id="d896e-107">El procedimiento puede implicar recorridos de puertos en servidores y firewalls, auditorías de correcciones de seguridad y pruebas de penetración de terceros.</span><span class="sxs-lookup"><span data-stu-id="d896e-107">The procedure may involve port scans on servers and firewalls, audits of security fixes, and third-party penetration tests.</span></span>

  - <span data-ttu-id="d896e-108">**Reemplazar certificados a punto de expirar**   la comprobación de certificados de Lync Server es una de las tareas semanales normales y, como parte del procedimiento, un administrador debe tener un registro de todas las fechas de vencimiento de los certificados.</span><span class="sxs-lookup"><span data-stu-id="d896e-108">**Replace Certificates about to Expire**   Checking Lync Server Certificates is one of regular weekly tasks, and as part of the procedure an administrator should have a record of all certificates’ expiry dates.</span></span> <span data-ttu-id="d896e-109">Este registro permite a un administrador crear una notificación cuando un certificado determinado va a expirar y sustituirse según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="d896e-109">This record enables an administrator to create a notification when a particular certificate is about to be expired and replaced as needed.</span></span>

  - <span data-ttu-id="d896e-110">\*\*\*\*   La actualización de líneas de base de rendimiento actualiza las líneas de rendimiento después de un cambio de configuración o actualización.</span><span class="sxs-lookup"><span data-stu-id="d896e-110">**Updating Performance Baselines**   Update performance baselines after an upgrade or configuration change.</span></span> <span data-ttu-id="d896e-111">Su organización puede usar líneas base para medir los cambios de rendimiento y detectar problemas que afectan al rendimiento del sistema.</span><span class="sxs-lookup"><span data-stu-id="d896e-111">Your organization can use baselines to measure performance changes and to detect issues that affect system performance.</span></span>

  - <span data-ttu-id="d896e-112">**La administración**   de la configuración inicial del grupo de servidores Enterprise de grupos empresariales, servidores Standard Edition y cualquier otro servidor del entorno de la organización se realizó durante la implementación de los servidores individuales.</span><span class="sxs-lookup"><span data-stu-id="d896e-112">**Managing Enterprise Pool**   Initial configuration of Enterprise pools, Standard Edition servers, and any other servers in your organization's environment were done during deployment of the individual servers.</span></span> <span data-ttu-id="d896e-113">La administración posterior a la implementación de servidores y grupos de servidores Standard Edition y grupos de servidores Enterprise incluye las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="d896e-113">Post-deployment management of servers and pools for Standard Edition servers and Enterprise pools includes the following tasks:</span></span>
    
      - <span data-ttu-id="d896e-114">Administración de servidores front-end</span><span class="sxs-lookup"><span data-stu-id="d896e-114">Managing Front End Servers</span></span>
    
      - <span data-ttu-id="d896e-115">Administrar conferencias web</span><span class="sxs-lookup"><span data-stu-id="d896e-115">Managing Web Conferencing</span></span>
    
      - <span data-ttu-id="d896e-116">Administrar conferencias</span><span class="sxs-lookup"><span data-stu-id="d896e-116">Managing Conferencing</span></span>
    
      - <span data-ttu-id="d896e-117">Cambiar las credenciales de la cuenta de servicio</span><span class="sxs-lookup"><span data-stu-id="d896e-117">Changing Service Account Credentials</span></span>
    
      - <span data-ttu-id="d896e-118">Administración de bases de datos</span><span class="sxs-lookup"><span data-stu-id="d896e-118">Managing Databases</span></span>
    
      - <span data-ttu-id="d896e-119">Iniciar y detener servicios y desactivar roles de servidor</span><span class="sxs-lookup"><span data-stu-id="d896e-119">Starting and Stopping Services and Deactivating Server Roles</span></span>
    
      - <span data-ttu-id="d896e-120">Quitar servidores y roles de servidor, quitar grupos y retirar servidores y grupos de servidores</span><span class="sxs-lookup"><span data-stu-id="d896e-120">Removing Servers and Server Roles, Removing Pools, and Decommissioning Servers and Pools</span></span>

  - <span data-ttu-id="d896e-121">**Administrar el uso**   puede configurar Lync Server 2013 para proporcionar las características y funcionalidades más apropiadas para su organización.</span><span class="sxs-lookup"><span data-stu-id="d896e-121">**Managing Usage**   You can configure Lync Server 2013 to provide the features and functionality that are most appropriate for your organization.</span></span> <span data-ttu-id="d896e-122">Entre estas directivas se incluyen:</span><span class="sxs-lookup"><span data-stu-id="d896e-122">This includes the following:</span></span>
    
      - <span data-ttu-id="d896e-123">Administración de la compatibilidad de las reuniones de conferencias web locales</span><span class="sxs-lookup"><span data-stu-id="d896e-123">Managing Support for On-Premise Web Conferencing Meetings</span></span>
    
      - <span data-ttu-id="d896e-124">Administrar el uso de grupos de distribución para enviar mensajes instantáneos</span><span class="sxs-lookup"><span data-stu-id="d896e-124">Managing the Use of Distribution Groups to Send Instant Messages</span></span>
    
      - <span data-ttu-id="d896e-125">Administración de contactos, presencia y consultas</span><span class="sxs-lookup"><span data-stu-id="d896e-125">Managing Contacts, Presence, and Queries</span></span>
    
      - <span data-ttu-id="d896e-126">Configuración del filtrado de versiones de cliente</span><span class="sxs-lookup"><span data-stu-id="d896e-126">Configuring Client Version Filtering</span></span>
    
      - <span data-ttu-id="d896e-127">Configuración del filtrado inteligente de mensajes instantáneos</span><span class="sxs-lookup"><span data-stu-id="d896e-127">Configuring Intelligent IM Filtering</span></span>
    
      - <span data-ttu-id="d896e-128">Configurar el archivado, grabación de llamadas en profundidad y cumplimiento de las reuniones</span><span class="sxs-lookup"><span data-stu-id="d896e-128">Configuring Archiving, Call Detail Recording, and Meeting Compliance</span></span>

  - <span data-ttu-id="d896e-129">**Administración**   de la Conectividad del servidor perimetral la administración continua de los servidores y la configuración necesaria para proporcionar conectividad externa incluye lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d896e-129">**Managing Edge Server Connectivity**   Ongoing management of the servers and settings required to provide external connectivity includes the following:</span></span>
    
      - <span data-ttu-id="d896e-130">Administración de la conectividad entre servidores internos y servidores perimetrales</span><span class="sxs-lookup"><span data-stu-id="d896e-130">Managing Connectivity between Internal Servers and Edge Servers</span></span>
    
      - <span data-ttu-id="d896e-131">Configuración de interfaces y certificados internos y externos para servidores perimetrales</span><span class="sxs-lookup"><span data-stu-id="d896e-131">Configuring Internal and External Interfaces and Certificates for Edge Servers</span></span>
    
      - <span data-ttu-id="d896e-132">Administrar el acceso de socios federados</span><span class="sxs-lookup"><span data-stu-id="d896e-132">Managing Federated Partner Access</span></span>

  - <span data-ttu-id="d896e-133">**La administración de la libreta**   de direcciones con la administración de los servidores de la libreta de direcciones incluye lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d896e-133">**Administering the Address Book**   Administering Address Book Servers includes the following:</span></span>
    
      - <span data-ttu-id="d896e-134">Configuración de la normalización del teléfono del servidor de libreta de direcciones</span><span class="sxs-lookup"><span data-stu-id="d896e-134">Configuring Address Book Server phone normalization</span></span>
    
      - <span data-ttu-id="d896e-135">Administrar el servidor de la libreta de direcciones desde la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="d896e-135">Managing the Address Book Server from the command line</span></span>

  - <span data-ttu-id="d896e-136">**Administrar cuentas**   de usuario la administración de cuentas de usuario incluye lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d896e-136">**Managing User Accounts**   Management of user accounts includes the following:</span></span>
    
      - <span data-ttu-id="d896e-137">Habilitar cuentas de usuario para Lync Server</span><span class="sxs-lookup"><span data-stu-id="d896e-137">Enabling User Accounts for Lync Server</span></span>
    
      - <span data-ttu-id="d896e-138">Configuración de usuarios de Lync Server mediante el asistente</span><span class="sxs-lookup"><span data-stu-id="d896e-138">Configuring Lync Server Users using the Wizard</span></span>
    
      - <span data-ttu-id="d896e-139">Configuración de las propiedades de la cuenta de usuario de Lync Server</span><span class="sxs-lookup"><span data-stu-id="d896e-139">Configuring Individual Lync Server User Account Properties</span></span>
    
      - <span data-ttu-id="d896e-140">Buscar usuarios de Lync Server</span><span class="sxs-lookup"><span data-stu-id="d896e-140">Searching for Lync Server Users</span></span>
    
      - <span data-ttu-id="d896e-141">Mover usuarios de Lync Server</span><span class="sxs-lookup"><span data-stu-id="d896e-141">Moving Lync Server Users</span></span>
    
      - <span data-ttu-id="d896e-142">Eliminar usuarios de Lync Server</span><span class="sxs-lookup"><span data-stu-id="d896e-142">Deleting Lync Server Users</span></span>

  - <span data-ttu-id="d896e-143">**Analizar los archivos**   de registro de 2013 de Lync Server una herramienta muy útil para la solución de problemas, es la herramienta de registro de Lync Server 2013 que se describe en detalle en [usar la herramienta de registro de Lync Server 2013](http://technet.microsoft.com/en-us/library/gg558599.aspx).</span><span class="sxs-lookup"><span data-stu-id="d896e-143">**Analyzing Lync Server 2013 Log Files**   One very helpful tool, generally used for troubleshooting, is the Lync Server 2013 Logging Tool described in detail in [Using Lync Server 2013 Logging Tool](http://technet.microsoft.com/en-us/library/gg558599.aspx).</span></span>

<span data-ttu-id="d896e-144">Como la herramienta de registro genera archivos de registro (en cada servidor), estos archivos de registro se pueden ver y analizar mediante la herramienta de supervisión, si las herramientas del kit de recursos de Microsoft Office Server 12 están instaladas en el equipo.</span><span class="sxs-lookup"><span data-stu-id="d896e-144">Because the Logging Tool generates log files (on a per-server basis), these log files can be viewed and analyzed by using the Snooper tool, if the Microsoft Office Server 12 Resource Kit Tools are installed on the computer.</span></span> <span data-ttu-id="d896e-145">De lo contrario, los registros también se pueden analizar con un editor de texto, que es mucho menos transparente y más complejo que el uso de la utilidad de supervisión.</span><span class="sxs-lookup"><span data-stu-id="d896e-145">Otherwise, logs can also be analyzed by using a text editor, which is much less transparent and more complex than using the Snooper utility.</span></span>

<span data-ttu-id="d896e-146">Para ver y analizar los mensajes de protocolo</span><span class="sxs-lookup"><span data-stu-id="d896e-146">To View and Analyze Protocol Messages</span></span>

<span data-ttu-id="d896e-147">En la herramienta de registro, cuando haya finalizado la sesión de depuración, haga clic en analizar archivos de registro para ver los archivos de registro con la herramienta de supervisión.</span><span class="sxs-lookup"><span data-stu-id="d896e-147">In the Logging Tool, when you have ended the debug session, click Analyze Log Files to view the log files by using the Snooper tool.</span></span> <span data-ttu-id="d896e-148">Puede analizar los registros de protocolo para los siguientes componentes:</span><span class="sxs-lookup"><span data-stu-id="d896e-148">You can analyze protocol logs for the following components:</span></span>

  - <span data-ttu-id="d896e-149">Lync Server SipStack (SIP)</span><span class="sxs-lookup"><span data-stu-id="d896e-149">Lync Server SipStack (SIP)</span></span>

  - <span data-ttu-id="d896e-150">Lync Server S4 (SIP)</span><span class="sxs-lookup"><span data-stu-id="d896e-150">Lync Server S4 (SIP)</span></span>

  - <span data-ttu-id="d896e-151">El tráfico de señalización de conferencias de Lync Server (C3P), incluido el C3P de infrarrojos y el foco C3P</span><span class="sxs-lookup"><span data-stu-id="d896e-151">Lync Server Conferencing signaling traffic (C3P), including MCU Infra C3P and Focus C3P</span></span>

  - <span data-ttu-id="d896e-152">Tráfico de conferencias web de Lync Server (PSOM)</span><span class="sxs-lookup"><span data-stu-id="d896e-152">Lync Server Web conferencing traffic (PSOM)</span></span>

  - <span data-ttu-id="d896e-153">Cliente de la plataforma de cliente de comunicaciones unificadas de Lync Server (UCCP)</span><span class="sxs-lookup"><span data-stu-id="d896e-153">Lync Server Unified Communications Client Platform client (UCCP)</span></span>

  - <span data-ttu-id="d896e-154">Informes de errores de la base de datos de archivado</span><span class="sxs-lookup"><span data-stu-id="d896e-154">Error reports from the archiving database</span></span>

<span data-ttu-id="d896e-155">Para ayudarle a organizar el rendimiento de las tareas necesarias, vea lista de comprobación de operaciones necesarias.</span><span class="sxs-lookup"><span data-stu-id="d896e-155">To help organize the performance of as-needed tasks, see As-Needed Operations Checklist.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d896e-156">Para obtener información detallada sobre la administración y los procedimientos de administración, consulte la guía de administración de Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d896e-156">For detailed administration and management procedures, see the Microsoft Lync Server 2013 Administration Guide.</span></span>



</div>

<div>

## <a name="backup-and-restore-policies-or-configuration-settings"></a><span data-ttu-id="d896e-157">Directivas de copia de seguridad (y restauración) o configuración</span><span class="sxs-lookup"><span data-stu-id="d896e-157">Backup (and restore) policies or configuration settings</span></span>

<span data-ttu-id="d896e-158">Lync Server 2013 le permite realizar copias de seguridad y restaurar todo el sistema.</span><span class="sxs-lookup"><span data-stu-id="d896e-158">Lync Server 2013 lets you back up and restore the whole system.</span></span> <span data-ttu-id="d896e-159">IIF quiere hacer una copia de seguridad (y, a continuación, quizás una vez restaurada) una sola directiva o una sola recopilación de parámetros de configuración, recuperar la directiva correspondiente y, a continuación, canalizar ese objeto al cmdlet Export-Clixml, que guarda la información de la Directiva como un archivo XML:</span><span class="sxs-lookup"><span data-stu-id="d896e-159">Iif you want to back up (and then maybe someday restore) a single policy or a single collection of configuration settings, retrieve the appropriate policy, and then pipe that object to the Export-Clixml cmdlet, which saves the policy information as an XML file:</span></span>

`Get-CsClientPolicy -Identity "RedmondClientPolicy" | Export-Clixml -Path C:\Backup\RedmondClientPolicy.xml`

<span data-ttu-id="d896e-160">Ahora puede experimentar con RedmondClientPolicy y cambiar la configuración.</span><span class="sxs-lookup"><span data-stu-id="d896e-160">You may now experiment with RedmondClientPolicy and change lots of the settings.</span></span> <span data-ttu-id="d896e-161">Si, en su lugar, decide restaurar la directiva anterior, escriba:</span><span class="sxs-lookup"><span data-stu-id="d896e-161">If you decide instead to restore the old policy, enter:</span></span>

`$x = Import-Clixml -Path C:\Backup\RedmondClientPolicy.xml`

`Set-CsClientPolicy -Instance $x`

<span data-ttu-id="d896e-162">Tenga en cuenta que este enfoque funcionará para la mayoría de las directivas y la configuración, pero no funcionará con algunos de los elementos más complejos (elementos que contienen varios subobjetos, como las opciones de configuración de enrutamiento, que contienen distintas rutas de voz).</span><span class="sxs-lookup"><span data-stu-id="d896e-162">Note that this approach will work for most policies and settings but it won't work with some of the more complex items—items that contain multiple sub-objects (like routing configuration settings, which contain many separate voice routes).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

