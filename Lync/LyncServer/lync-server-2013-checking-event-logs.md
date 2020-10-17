---
title: 'Lync Server 2013: comprobación de registros de eventos'
description: 'Lync Server 2013: comprobación de registros de eventos.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Checking event logs
ms:assetid: 5500720d-c628-4dbd-84bc-a5becc39b99c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720914(v=OCS.15)
ms:contentKeyID: 63969602
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6617bde846fd38ab3282fd023b16e0a921f48920
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570986"
---
# <a name="checking-event-logs-in-lync-server-2013"></a><span data-ttu-id="5536a-103">Comprobación de registros de eventos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5536a-103">Checking event logs in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5536a-104">_**Última modificación del tema:** 2014-08-06_</span><span class="sxs-lookup"><span data-stu-id="5536a-104">_**Topic Last Modified:** 2014-08-06_</span></span>

<span data-ttu-id="5536a-105">Puede usar el [visor de eventos de Windows](https://go.microsoft.com/fwlink/p/?linkid=314067) para ver los registros de eventos y obtener información sobre errores de servicio, errores de replicación en AD DS y advertencias sobre los recursos del sistema, como la memoria virtual y el espacio en disco.</span><span class="sxs-lookup"><span data-stu-id="5536a-105">You can use [Windows Event Viewer](https://go.microsoft.com/fwlink/p/?linkid=314067) to view event logs and obtain information about service failures, replication errors in the AD DS, and warnings about system resources such as virtual memory and disk space.</span></span> <span data-ttu-id="5536a-106">El visor de eventos se incluye con Windows Server 2008 y 2012.</span><span class="sxs-lookup"><span data-stu-id="5536a-106">Event Viewer is included with Windows Server 2008 and 2012.</span></span>

<span data-ttu-id="5536a-107">En la herramienta de registro de Lync Server 2013, cuando finalice la sesión de depuración, haga clic en **analizar archivos de registro** para ver los archivos de registro mediante la herramienta de supervisión.</span><span class="sxs-lookup"><span data-stu-id="5536a-107">In the Lync Server 2013 Logging Tool, when you end the debug session, click **Analyze Log Files** to view the log files by using the Snooper tool.</span></span>

<span data-ttu-id="5536a-108">El visor de eventos mantiene registros sobre los eventos del sistema, la seguridad y la aplicación en el equipo.</span><span class="sxs-lookup"><span data-stu-id="5536a-108">Event Viewer maintains logs about application, security, and system events on the computer.</span></span> <span data-ttu-id="5536a-109">Lync Server 2013 y las condiciones de error y advertencias de los informes de Windows para los registros de eventos.</span><span class="sxs-lookup"><span data-stu-id="5536a-109">Both Lync Server 2013 and Windows report warnings and error conditions to the event logs.</span></span> <span data-ttu-id="5536a-110">Por lo tanto, revise los registros de eventos a diario.</span><span class="sxs-lookup"><span data-stu-id="5536a-110">Therefore, review event logs daily.</span></span>

<span data-ttu-id="5536a-111">Use el visor de eventos para:</span><span class="sxs-lookup"><span data-stu-id="5536a-111">Use Event Viewer to:</span></span>

  - <span data-ttu-id="5536a-112">Ver y administrar registros de eventos.</span><span class="sxs-lookup"><span data-stu-id="5536a-112">View and manage event logs.</span></span>

  - <span data-ttu-id="5536a-113">Obtenga información sobre los problemas de hardware, software y sistema que deben resolverse.</span><span class="sxs-lookup"><span data-stu-id="5536a-113">Obtain information about hardware, software, and system issues that must be resolved.</span></span>

  - <span data-ttu-id="5536a-114">Identificar las tendencias que requieren acciones futuras.</span><span class="sxs-lookup"><span data-stu-id="5536a-114">Identify trends that require future action.</span></span>

<span data-ttu-id="5536a-115">Un servidor que ejecuta Lync Server en un sistema operativo Windows Server registra eventos en cuatro tipos de registros:</span><span class="sxs-lookup"><span data-stu-id="5536a-115">A server that is running Lync Server on a Windows Server operating system records events in four types of logs:</span></span>

  - <span data-ttu-id="5536a-116">**Registros**     de aplicación El registro de aplicación contiene los eventos registrados por aplicaciones o programas.</span><span class="sxs-lookup"><span data-stu-id="5536a-116">**Application logs**   The Application log contains events logged by applications or programs.</span></span> <span data-ttu-id="5536a-117">Los desarrolladores determinan los eventos que se registrarán.</span><span class="sxs-lookup"><span data-stu-id="5536a-117">Developers determine which events to log.</span></span> <span data-ttu-id="5536a-118">Por ejemplo, un programa de base de datos podría registrar un error de archivo en el registro de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5536a-118">For example, a database program might record a file error in the Application log.</span></span> <span data-ttu-id="5536a-119">La mayoría de los eventos relacionados con Lync Server 2013 aparecen en el registro de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5536a-119">Most Lync Server 2013-related events appear in the Application log.</span></span>

  - <span data-ttu-id="5536a-120">**Registros**     de seguridad El registro de seguridad registra eventos como intentos válidos y no válidos de inicio de sesión, además de eventos relacionados con el uso de recursos, como la creación, apertura o eliminación de archivos u otros objetos.</span><span class="sxs-lookup"><span data-stu-id="5536a-120">**Security logs**   The Security log records events such as valid and not valid logon tries in addition to events related to resource use such as creating, opening, or deleting files or other objects.</span></span> <span data-ttu-id="5536a-121">Por ejemplo, si la auditoría de inicio de sesión está habilitada, los intentos de iniciar sesión en el sistema se registran en el registro de seguridad.</span><span class="sxs-lookup"><span data-stu-id="5536a-121">For example, if logon auditing is enabled, attempts to log on to the system are recorded in the Security log.</span></span>

  - <span data-ttu-id="5536a-122">**Registros**     del sistema El registro del sistema contiene los eventos registrados por los componentes del sistema de Windows.</span><span class="sxs-lookup"><span data-stu-id="5536a-122">**System logs**   The System log contains events logged by Windows system components.</span></span> <span data-ttu-id="5536a-123">Por ejemplo, el error de la carga de un controlador u otro componente del sistema durante el inicio se registra en el registro del sistema.</span><span class="sxs-lookup"><span data-stu-id="5536a-123">For example, the failure of a driver or other system component to load during startup is recorded in the System log.</span></span> <span data-ttu-id="5536a-124">Los tipos de eventos registrados por los componentes del sistema están predeterminados por el servidor.</span><span class="sxs-lookup"><span data-stu-id="5536a-124">The event types logged by system components are predetermined by the server.</span></span>

  - <span data-ttu-id="5536a-125">**Lync Server 2013**     La herramienta de registro registra eventos importantes relacionados con la autenticación, las conexiones y las acciones del usuario.</span><span class="sxs-lookup"><span data-stu-id="5536a-125">**Lync Server 2013**   The logging tool records significant events related to authentication, connections, and user actions.</span></span> <span data-ttu-id="5536a-126">Después de habilitar el registro de diagnóstico, puede ver las entradas de registro en el visor de eventos.</span><span class="sxs-lookup"><span data-stu-id="5536a-126">After enabling diagnostic logging, you can view the log entries in Event Viewer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5536a-127">No se recomienda usar la configuración de registro máxima a menos que se le indique a través de los servicios de soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5536a-127">We do not recommend that you use the maximum logging settings unless you are instructed to do this by Microsoft Customer Support Services.</span></span> <span data-ttu-id="5536a-128">El registro máximo purga los recursos importantes y puede dar varios "falsos positivos", es decir, los errores que se registran solo en el registro máximo pero se esperan realmente y no son un motivo de preocupación.</span><span class="sxs-lookup"><span data-stu-id="5536a-128">Maximum logging drains significant resources and can give many “false positives,” that is, errors that get logged only at maximum logging but are really expected and are not a cause of concern.</span></span> <span data-ttu-id="5536a-129">También le recomendamos que no habilite el registro de diagnóstico de forma permanente.</span><span class="sxs-lookup"><span data-stu-id="5536a-129">We also recommend that you do not enable diagnostic logging permanently.</span></span> <span data-ttu-id="5536a-130">Úselo solo para solucionar problemas.</span><span class="sxs-lookup"><span data-stu-id="5536a-130">Use it only when troubleshooting.</span></span>



</div>

<span data-ttu-id="5536a-131">En cada registro del visor de eventos, Lync Server 2013 registra eventos informativos, de advertencia y de error.</span><span class="sxs-lookup"><span data-stu-id="5536a-131">Within each Event Viewer log, Lync Server 2013 records informational, warning, and error events.</span></span> <span data-ttu-id="5536a-132">Supervise estos registros atentamente para realizar un seguimiento de los tipos de transacciones que se realizan en los servidores de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5536a-132">Monitor these logs closely to track the types of transactions being conducted on the Lync Server 2013 servers.</span></span> <span data-ttu-id="5536a-133">Debe archivar periódicamente los registros o usar la sustitución automática para evitar quedarse sin espacio.</span><span class="sxs-lookup"><span data-stu-id="5536a-133">You should periodically archive the logs or use automatic rollover to avoid running out of space.</span></span> <span data-ttu-id="5536a-134">Como los archivos de registro pueden ocupar una cantidad de espacio finita, aumente el tamaño del registro (por ejemplo, a 50 MB) y establézcalo en overwrite para que el servidor de Lync Server 2013 pueda seguir escribiendo nuevos eventos.</span><span class="sxs-lookup"><span data-stu-id="5536a-134">Because log files can occupy a finite amount of space, increase the log size (for example, to 50 MB) and set it to overwrite so that the Lync Server 2013 Server can continue to write new events.</span></span>

<span data-ttu-id="5536a-135">También puede automatizar la administración de registros de eventos mediante las siguientes herramientas y tecnologías:</span><span class="sxs-lookup"><span data-stu-id="5536a-135">You can also automate event log administration by using the following tools and technologies:</span></span>

  - <span data-ttu-id="5536a-136">System Center Operations Manager supervisa el estado y el uso de los servidores de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5536a-136">System Center Operations Manager monitors the health and use of Lync Server 2013 servers.</span></span> <span data-ttu-id="5536a-137">El módulo de administración de Lync Server 2013 para Operations Manager amplía Operations Manager al ofrecer una supervisión especializada para los servidores que ejecutan Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5536a-137">Lync Server 2013 Management Pack for Operations Manager extends Operations Manager by providing specialized monitoring for servers that are running Lync Server 2013.</span></span>

  - <span data-ttu-id="5536a-138">El paquete de administración de Lync Server 2013 para los monitores de Operations Manager Standard y Enterprise Edition de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5536a-138">The Lync Server 2013 Management Pack for Operations Manager monitors Standard and Enterprise Edition of Lync Server 2013.</span></span> <span data-ttu-id="5536a-139">Esta versión también incorpora el módulo de administración de calidad de la experiencia (QoE), que anteriormente era un módulo de administración independiente.</span><span class="sxs-lookup"><span data-stu-id="5536a-139">This release also incorporates the Quality of Experience (QoE) Management Pack which was previously a separate management pack.</span></span>

<span data-ttu-id="5536a-140">Los tipos supervisados son entradas de registro de eventos, contadores de rendimiento y supervisión de estado de QoE.</span><span class="sxs-lookup"><span data-stu-id="5536a-140">Monitored types are event log entries, performance counters and stateful monitoring of QoE.</span></span> <span data-ttu-id="5536a-141">Esta versión del módulo de administración solo supervisa Lync Server 2013 y 2010, y no se puede usar para supervisar Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="5536a-141">This version of the management pack only monitors Lync Server 2013 and 2010, and cannot be used to monitor Office Communications Server 2007.</span></span>

<span data-ttu-id="5536a-142">El módulo de administración proporciona las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="5536a-142">The management pack provides the following features:</span></span>

  - <span data-ttu-id="5536a-143">Alertas que indican eventos que afectan al servicio</span><span class="sxs-lookup"><span data-stu-id="5536a-143">Alerts indicating service affecting events</span></span>

  - <span data-ttu-id="5536a-144">Alertas que indican la configuración y otros problemas que no afectan al servicio</span><span class="sxs-lookup"><span data-stu-id="5536a-144">Alerts indicating configuration, and other non-service impacting issues</span></span>

  - <span data-ttu-id="5536a-145">Supervisión de estado de los servicios de Lync Server</span><span class="sxs-lookup"><span data-stu-id="5536a-145">State monitoring of Lync Server services</span></span>

  - <span data-ttu-id="5536a-146">Conocimiento del producto: causa y solución de problemas identificados</span><span class="sxs-lookup"><span data-stu-id="5536a-146">Product knowledge: Cause and resolution of identified issues</span></span>

<span data-ttu-id="5536a-147">Para obtener más información acerca del paquete de administración de Lync Server 2013, consulte [Monitoring Lync server 2013 con System Center Operations Manager](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md).</span><span class="sxs-lookup"><span data-stu-id="5536a-147">For more information about Lync Server 2013 Management Pack, refer to [Monitoring Lync Server 2013 with System Center Operations Manager](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md).</span></span>

<span data-ttu-id="5536a-148">**Event COMB**     La herramienta Event COMB recopila eventos específicos de los registros de eventos de varios equipos en una ubicación central.</span><span class="sxs-lookup"><span data-stu-id="5536a-148">**Event Comb**   The Event Comb tool collects specific events from the event logs of several computers to one central location.</span></span> <span data-ttu-id="5536a-149">Permite informar únicamente de los identificadores de evento o los orígenes de eventos que especifica.</span><span class="sxs-lookup"><span data-stu-id="5536a-149">It lets you report on only the event IDs or event sources it specifies.</span></span> <span data-ttu-id="5536a-150">Para obtener más información acerca de Event COMB, consulte el sitio web de [herramientas de bloqueo y administración de cuentas](https://go.microsoft.com/fwlink/?linkid=35607) .</span><span class="sxs-lookup"><span data-stu-id="5536a-150">For more information about Event Comb, see the [Account Lockout and Management Tools](https://go.microsoft.com/fwlink/?linkid=35607) website.</span></span>

<span data-ttu-id="5536a-151">**Desencadenadores**     de eventos En Windows Server 2012 puede "adjuntar una tarea a este evento" en el visor de eventos de Windows, donde un administrador puede ejecutar un programa, enviar un mensaje de correo electrónico o mostrar un mensaje en pantalla.</span><span class="sxs-lookup"><span data-stu-id="5536a-151">**Event triggers**   In Windows Server 2012 you can "Attach a Task to This Event" within the Windows Event Viewer—where an administrator can either run a program, send an email message or display an on-screen message.</span></span> <span data-ttu-id="5536a-152">Para obtener más información acerca de esta característica, vea el tema sobre Windows Server 2008 R2 [ejecutar una tarea en respuesta a un evento determinado](https://technet.microsoft.com/library/cc748900.aspx).</span><span class="sxs-lookup"><span data-stu-id="5536a-152">For more information about this feature, see the Windows Server 2008 R2 topic [Run a Task in Response to a Given Event](https://technet.microsoft.com/library/cc748900.aspx).</span></span> <span data-ttu-id="5536a-153">También puede usar herramientas de línea de comandos como "Eventtrigger.exe" para crear y consultar registros de eventos y asociar programas con determinados eventos registrados.</span><span class="sxs-lookup"><span data-stu-id="5536a-153">You can also use command-line tools such as ‘Eventtrigger.exe’ to create and query event logs and associate programs with particular logged events.</span></span> <span data-ttu-id="5536a-154">Mediante el uso de Eventtriggers.exe, puede crear desencadenadores de eventos que ejecutan programas cuando se producen eventos específicos.</span><span class="sxs-lookup"><span data-stu-id="5536a-154">By using Eventtriggers.exe, you can create event triggers that run programs when specific events occur.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="5536a-155">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5536a-155">See Also</span></span>


[<span data-ttu-id="5536a-156">Visor de eventos de Windows</span><span class="sxs-lookup"><span data-stu-id="5536a-156">Windows Event Viewer</span></span>](https://go.microsoft.com/fwlink/p/?linkid=314067)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

