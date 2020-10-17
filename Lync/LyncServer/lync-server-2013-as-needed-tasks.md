---
title: 'Lync Server 2013: tareas necesarias'
description: 'Lync Server 2013: tareas necesarias.'
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
ms.openlocfilehash: 91fe249d9615bb619426c58b22606c3ef182f9a7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560006"
---
# <a name="as-needed-tasks-in-lync-server-2013"></a><span data-ttu-id="e7987-103">Tareas necesarias en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e7987-103">As-needed tasks in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e7987-104">_**Última modificación del tema:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="e7987-104">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="e7987-105">Realice las siguientes tareas según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="e7987-105">Perform the following tasks as necessary.</span></span> <span data-ttu-id="e7987-106">Con frecuencia también se incluyen en los procedimientos estándar:</span><span class="sxs-lookup"><span data-stu-id="e7987-106">They are frequently also covered by standard procedures:</span></span>

  - <span data-ttu-id="e7987-107">**Auditoría de seguridad completa   ** Puede realizar esta auditoría con regularidad, en respuesta a una actualización o rediseño del sistema de mensajería, o en respuesta a una infracción de seguridad intentada (o exitosa).</span><span class="sxs-lookup"><span data-stu-id="e7987-107">**Full Security Auditing   **You can perform this audit regularly, in response to an upgrade or redesign of the messaging system, or in response to an attempted (or successful) security breach.</span></span> <span data-ttu-id="e7987-108">El procedimiento puede implicar análisis de puertos en servidores y firewalls, auditorías de revisiones de seguridad y pruebas de penetración de terceros.</span><span class="sxs-lookup"><span data-stu-id="e7987-108">The procedure may involve port scans on servers and firewalls, audits of security fixes, and third-party penetration tests.</span></span>

  - <span data-ttu-id="e7987-109">**Reemplazar certificados a punto de expirar**     La comprobación de los certificados de Lync Server es una tarea semanal normal y, como parte del procedimiento, un administrador debe tener un registro de todas las fechas de expiración de los certificados.</span><span class="sxs-lookup"><span data-stu-id="e7987-109">**Replace Certificates about to Expire**   Checking Lync Server Certificates is one of regular weekly tasks, and as part of the procedure an administrator should have a record of all certificates’ expiry dates.</span></span> <span data-ttu-id="e7987-110">Este registro permite a un administrador crear una notificación cuando un certificado concreto está a punto de caducar y se reemplaza según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="e7987-110">This record enables an administrator to create a notification when a particular certificate is about to be expired and replaced as needed.</span></span>

  - <span data-ttu-id="e7987-111">**Actualización de líneas de base**     de rendimiento Actualice las líneas de base de rendimiento después de un cambio en la configuración o la actualización.</span><span class="sxs-lookup"><span data-stu-id="e7987-111">**Updating Performance Baselines**   Update performance baselines after an upgrade or configuration change.</span></span> <span data-ttu-id="e7987-112">Su organización puede usar líneas de base para medir los cambios de rendimiento y detectar problemas que afectan al rendimiento del sistema.</span><span class="sxs-lookup"><span data-stu-id="e7987-112">Your organization can use baselines to measure performance changes and to detect issues that affect system performance.</span></span>

  - <span data-ttu-id="e7987-113">**Administración del grupo**     de servidores Enterprise Durante la implementación de los servidores individuales, se realizó la configuración inicial de los grupos de servidores Enterprise, los servidores Standard Edition y cualquier otro servidor del entorno de la organización.</span><span class="sxs-lookup"><span data-stu-id="e7987-113">**Managing Enterprise Pool**   Initial configuration of Enterprise pools, Standard Edition servers, and any other servers in your organization's environment were done during deployment of the individual servers.</span></span> <span data-ttu-id="e7987-114">La administración posterior a la implementación de servidores y grupos de servidores Standard Edition y grupos de servidores Enterprise incluye las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="e7987-114">Post-deployment management of servers and pools for Standard Edition servers and Enterprise pools includes the following tasks:</span></span>
    
      - <span data-ttu-id="e7987-115">Administración de servidores front-end</span><span class="sxs-lookup"><span data-stu-id="e7987-115">Managing Front End Servers</span></span>
    
      - <span data-ttu-id="e7987-116">Administración de conferencias web</span><span class="sxs-lookup"><span data-stu-id="e7987-116">Managing Web Conferencing</span></span>
    
      - <span data-ttu-id="e7987-117">Administración de conferencias</span><span class="sxs-lookup"><span data-stu-id="e7987-117">Managing Conferencing</span></span>
    
      - <span data-ttu-id="e7987-118">Cambio de las credenciales de la cuenta de servicio</span><span class="sxs-lookup"><span data-stu-id="e7987-118">Changing Service Account Credentials</span></span>
    
      - <span data-ttu-id="e7987-119">Administración de bases de datos</span><span class="sxs-lookup"><span data-stu-id="e7987-119">Managing Databases</span></span>
    
      - <span data-ttu-id="e7987-120">Inicio y detención de servicios y desactivación de roles de servidor</span><span class="sxs-lookup"><span data-stu-id="e7987-120">Starting and Stopping Services and Deactivating Server Roles</span></span>
    
      - <span data-ttu-id="e7987-121">Quitar servidores y roles de servidor, quitar grupos de servidores y retirar servidores y grupos de servidores</span><span class="sxs-lookup"><span data-stu-id="e7987-121">Removing Servers and Server Roles, Removing Pools, and Decommissioning Servers and Pools</span></span>

  - <span data-ttu-id="e7987-122">**Administración del uso**     Puede configurar Lync Server 2013 para proporcionar las características y funciones más adecuadas para su organización.</span><span class="sxs-lookup"><span data-stu-id="e7987-122">**Managing Usage**   You can configure Lync Server 2013 to provide the features and functionality that are most appropriate for your organization.</span></span> <span data-ttu-id="e7987-123">Esto incluye lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e7987-123">This includes the following:</span></span>
    
      - <span data-ttu-id="e7987-124">Administración de la compatibilidad con reuniones de conferencias web locales</span><span class="sxs-lookup"><span data-stu-id="e7987-124">Managing Support for On-Premise Web Conferencing Meetings</span></span>
    
      - <span data-ttu-id="e7987-125">Administración del uso de grupos de distribución para enviar mensajes instantáneos</span><span class="sxs-lookup"><span data-stu-id="e7987-125">Managing the Use of Distribution Groups to Send Instant Messages</span></span>
    
      - <span data-ttu-id="e7987-126">Administración de contactos, presencia y consultas</span><span class="sxs-lookup"><span data-stu-id="e7987-126">Managing Contacts, Presence, and Queries</span></span>
    
      - <span data-ttu-id="e7987-127">Configuración del filtrado de versiones de cliente</span><span class="sxs-lookup"><span data-stu-id="e7987-127">Configuring Client Version Filtering</span></span>
    
      - <span data-ttu-id="e7987-128">Configuración del filtrado inteligente de mensajería instantánea</span><span class="sxs-lookup"><span data-stu-id="e7987-128">Configuring Intelligent IM Filtering</span></span>
    
      - <span data-ttu-id="e7987-129">Configuración del archivado, registro detallado de llamadas y cumplimiento de las reuniones</span><span class="sxs-lookup"><span data-stu-id="e7987-129">Configuring Archiving, Call Detail Recording, and Meeting Compliance</span></span>

  - <span data-ttu-id="e7987-130">**Administración de la conectividad**     del servidor perimetral La administración continua de los servidores y la configuración necesaria para proporcionar conectividad externa incluye lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e7987-130">**Managing Edge Server Connectivity**   Ongoing management of the servers and settings required to provide external connectivity includes the following:</span></span>
    
      - <span data-ttu-id="e7987-131">Administración de la conectividad entre servidores internos y servidores perimetrales</span><span class="sxs-lookup"><span data-stu-id="e7987-131">Managing Connectivity between Internal Servers and Edge Servers</span></span>
    
      - <span data-ttu-id="e7987-132">Configuración de interfaces y certificados internos y externos para servidores perimetrales</span><span class="sxs-lookup"><span data-stu-id="e7987-132">Configuring Internal and External Interfaces and Certificates for Edge Servers</span></span>
    
      - <span data-ttu-id="e7987-133">Administración del acceso de socios federados</span><span class="sxs-lookup"><span data-stu-id="e7987-133">Managing Federated Partner Access</span></span>

  - <span data-ttu-id="e7987-134">**Administración de la libreta**     de direcciones La administración de los servidores de la libreta de direcciones incluye lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e7987-134">**Administering the Address Book**   Administering Address Book Servers includes the following:</span></span>
    
      - <span data-ttu-id="e7987-135">Configuración de la normalización del teléfono del servidor de libreta de direcciones</span><span class="sxs-lookup"><span data-stu-id="e7987-135">Configuring Address Book Server phone normalization</span></span>
    
      - <span data-ttu-id="e7987-136">Administración del servidor de la libreta de direcciones desde la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="e7987-136">Managing the Address Book Server from the command line</span></span>

  - <span data-ttu-id="e7987-137">**Administración de cuentas**     de usuario La administración de cuentas de usuario incluye lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e7987-137">**Managing User Accounts**   Management of user accounts includes the following:</span></span>
    
      - <span data-ttu-id="e7987-138">Habilitación de cuentas de usuario para Lync Server</span><span class="sxs-lookup"><span data-stu-id="e7987-138">Enabling User Accounts for Lync Server</span></span>
    
      - <span data-ttu-id="e7987-139">Configuración de usuarios de Lync Server mediante el asistente</span><span class="sxs-lookup"><span data-stu-id="e7987-139">Configuring Lync Server Users using the Wizard</span></span>
    
      - <span data-ttu-id="e7987-140">Configuración de propiedades de cuenta de usuario de Lync Server individual</span><span class="sxs-lookup"><span data-stu-id="e7987-140">Configuring Individual Lync Server User Account Properties</span></span>
    
      - <span data-ttu-id="e7987-141">Buscar usuarios de Lync Server</span><span class="sxs-lookup"><span data-stu-id="e7987-141">Searching for Lync Server Users</span></span>
    
      - <span data-ttu-id="e7987-142">Mover usuarios de Lync Server</span><span class="sxs-lookup"><span data-stu-id="e7987-142">Moving Lync Server Users</span></span>
    
      - <span data-ttu-id="e7987-143">Eliminación de usuarios de Lync Server</span><span class="sxs-lookup"><span data-stu-id="e7987-143">Deleting Lync Server Users</span></span>

  - <span data-ttu-id="e7987-144">**Analizar los archivos**     de registro de 2013 de Lync Server Una herramienta muy útil, generalmente usada para la solución de problemas, es la herramienta de registro de Lync Server 2013 que se describe en detalle en uso de la [herramienta de registro de Lync server 2013](https://technet.microsoft.com/library/gg558599.aspx).</span><span class="sxs-lookup"><span data-stu-id="e7987-144">**Analyzing Lync Server 2013 Log Files**   One very helpful tool, generally used for troubleshooting, is the Lync Server 2013 Logging Tool described in detail in [Using Lync Server 2013 Logging Tool](https://technet.microsoft.com/library/gg558599.aspx).</span></span>

<span data-ttu-id="e7987-145">Debido a que la herramienta de registro genera archivos de registro (en función de cada servidor), estos archivos de registro se pueden ver y analizar mediante la herramienta de supervisión, si las herramientas del kit de recursos de Microsoft Office Server 12 están instaladas en el equipo.</span><span class="sxs-lookup"><span data-stu-id="e7987-145">Because the Logging Tool generates log files (on a per-server basis), these log files can be viewed and analyzed by using the Snooper tool, if the Microsoft Office Server 12 Resource Kit Tools are installed on the computer.</span></span> <span data-ttu-id="e7987-146">De lo contrario, los registros también se pueden analizar con un editor de texto, que es mucho menos transparente y más complejo que el uso de la utilidad de supervisión.</span><span class="sxs-lookup"><span data-stu-id="e7987-146">Otherwise, logs can also be analyzed by using a text editor, which is much less transparent and more complex than using the Snooper utility.</span></span>

<span data-ttu-id="e7987-147">Para ver y analizar mensajes de protocolo</span><span class="sxs-lookup"><span data-stu-id="e7987-147">To View and Analyze Protocol Messages</span></span>

<span data-ttu-id="e7987-148">En la herramienta de registro, cuando haya finalizado la sesión de depuración, haga clic en analizar archivos de registro para ver los archivos de registro mediante la herramienta de supervisión.</span><span class="sxs-lookup"><span data-stu-id="e7987-148">In the Logging Tool, when you have ended the debug session, click Analyze Log Files to view the log files by using the Snooper tool.</span></span> <span data-ttu-id="e7987-149">Puede analizar los registros de protocolo para los siguientes componentes:</span><span class="sxs-lookup"><span data-stu-id="e7987-149">You can analyze protocol logs for the following components:</span></span>

  - <span data-ttu-id="e7987-150">Lync Server SipStack (SIP)</span><span class="sxs-lookup"><span data-stu-id="e7987-150">Lync Server SipStack (SIP)</span></span>

  - <span data-ttu-id="e7987-151">Lync Server S4 (SIP)</span><span class="sxs-lookup"><span data-stu-id="e7987-151">Lync Server S4 (SIP)</span></span>

  - <span data-ttu-id="e7987-152">Tráfico de señalización de conferencias de Lync Server (C3P), incluido el C3P de infrarrojos y el foco C3P</span><span class="sxs-lookup"><span data-stu-id="e7987-152">Lync Server Conferencing signaling traffic (C3P), including MCU Infra C3P and Focus C3P</span></span>

  - <span data-ttu-id="e7987-153">Tráfico de conferencia Web de Lync Server (PSOM)</span><span class="sxs-lookup"><span data-stu-id="e7987-153">Lync Server Web conferencing traffic (PSOM)</span></span>

  - <span data-ttu-id="e7987-154">Cliente de la plataforma de cliente de comunicaciones unificadas de Lync Server (UCCP)</span><span class="sxs-lookup"><span data-stu-id="e7987-154">Lync Server Unified Communications Client Platform client (UCCP)</span></span>

  - <span data-ttu-id="e7987-155">Informes de errores de la base de datos de archivado</span><span class="sxs-lookup"><span data-stu-id="e7987-155">Error reports from the archiving database</span></span>

<span data-ttu-id="e7987-156">Para ayudar a organizar el rendimiento de las tareas necesarias, consulte As-Needed lista de comprobación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="e7987-156">To help organize the performance of as-needed tasks, see As-Needed Operations Checklist.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e7987-157">Para obtener información detallada acerca de los procedimientos de administración y administración, consulte la guía de administración de Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e7987-157">For detailed administration and management procedures, see the Microsoft Lync Server 2013 Administration Guide.</span></span>



</div>

<div>

## <a name="backup-and-restore-policies-or-configuration-settings"></a><span data-ttu-id="e7987-158">Opciones de configuración y directivas de copia de seguridad (y restauración)</span><span class="sxs-lookup"><span data-stu-id="e7987-158">Backup (and restore) policies or configuration settings</span></span>

<span data-ttu-id="e7987-159">Lync Server 2013 permite realizar copias de seguridad y restaurar todo el sistema.</span><span class="sxs-lookup"><span data-stu-id="e7987-159">Lync Server 2013 lets you back up and restore the whole system.</span></span> <span data-ttu-id="e7987-160">IIF desea realizar una copia de seguridad (y, a continuación, quizás algún día de la restauración) una única directiva o una sola recopilación de opciones de configuración, recuperar la Directiva adecuada y, a continuación, canalizar el objeto al cmdlet Export-Clixml, que guarda la información de la Directiva como un archivo XML:</span><span class="sxs-lookup"><span data-stu-id="e7987-160">Iif you want to back up (and then maybe someday restore) a single policy or a single collection of configuration settings, retrieve the appropriate policy, and then pipe that object to the Export-Clixml cmdlet, which saves the policy information as an XML file:</span></span>

`Get-CsClientPolicy -Identity "RedmondClientPolicy" | Export-Clixml -Path C:\Backup\RedmondClientPolicy.xml`

<span data-ttu-id="e7987-161">Ahora puede experimentar con RedmondClientPolicy y cambiar una gran cantidad de opciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="e7987-161">You may now experiment with RedmondClientPolicy and change lots of the settings.</span></span> <span data-ttu-id="e7987-162">Si, en su lugar, decide restaurar la directiva anterior, escriba:</span><span class="sxs-lookup"><span data-stu-id="e7987-162">If you decide instead to restore the old policy, enter:</span></span>

`$x = Import-Clixml -Path C:\Backup\RedmondClientPolicy.xml`

`Set-CsClientPolicy -Instance $x`

<span data-ttu-id="e7987-163">Tenga en cuenta que este enfoque funcionará con la mayoría de las directivas y la configuración, pero no funcionará con algunos de los elementos más complejos (elementos que contienen varios subobjetos) (como las opciones de configuración de enrutamiento, que contienen varias rutas de voz independientes).</span><span class="sxs-lookup"><span data-stu-id="e7987-163">Note that this approach will work for most policies and settings but it won't work with some of the more complex items—items that contain multiple sub-objects (like routing configuration settings, which contain many separate voice routes).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

