---
title: 'Lync Server 2013: comprobación de registros de eventos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Checking event logs
ms:assetid: 5500720d-c628-4dbd-84bc-a5becc39b99c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720914(v=OCS.15)
ms:contentKeyID: 63969602
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1506f94f0a049a6bb4fdd90875dae50548b5f516
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842574"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="checking-event-logs-in-lync-server-2013"></a><span data-ttu-id="fc95c-102">Comprobar registros de eventos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fc95c-102">Checking event logs in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fc95c-103">_**Última modificación del tema:** 2014-08-06_</span><span class="sxs-lookup"><span data-stu-id="fc95c-103">_**Topic Last Modified:** 2014-08-06_</span></span>

<span data-ttu-id="fc95c-104">Puede usar el [visor de eventos de Windows](http://go.microsoft.com/fwlink/p/?linkid=314067) para ver registros de eventos y obtener información sobre errores de servicio, errores de replicación en AD DS y advertencias sobre recursos del sistema, como memoria virtual y espacio en disco.</span><span class="sxs-lookup"><span data-stu-id="fc95c-104">You can use [Windows Event Viewer](http://go.microsoft.com/fwlink/p/?linkid=314067) to view event logs and obtain information about service failures, replication errors in the AD DS, and warnings about system resources such as virtual memory and disk space.</span></span> <span data-ttu-id="fc95c-105">El visor de eventos se incluye en Windows Server 2008 y 2012.</span><span class="sxs-lookup"><span data-stu-id="fc95c-105">Event Viewer is included with Windows Server 2008 and 2012.</span></span>

<span data-ttu-id="fc95c-106">En la herramienta de registro de 2013 de Lync Server, al finalizar la sesión de depuración, haga clic en **analizar archivos de registro** para ver los archivos de registro con la herramienta de supervisión.</span><span class="sxs-lookup"><span data-stu-id="fc95c-106">In the Lync Server 2013 Logging Tool, when you end the debug session, click **Analyze Log Files** to view the log files by using the Snooper tool.</span></span>

<span data-ttu-id="fc95c-107">El visor de eventos mantiene registros acerca de aplicaciones, seguridad y eventos del sistema en el equipo.</span><span class="sxs-lookup"><span data-stu-id="fc95c-107">Event Viewer maintains logs about application, security, and system events on the computer.</span></span> <span data-ttu-id="fc95c-108">Lync Server 2013 y Windows notifican las advertencias y las condiciones de error a los registros de eventos.</span><span class="sxs-lookup"><span data-stu-id="fc95c-108">Both Lync Server 2013 and Windows report warnings and error conditions to the event logs.</span></span> <span data-ttu-id="fc95c-109">Por lo tanto, revise los registros de eventos todos los días.</span><span class="sxs-lookup"><span data-stu-id="fc95c-109">Therefore, review event logs daily.</span></span>

<span data-ttu-id="fc95c-110">Use el visor de eventos para:</span><span class="sxs-lookup"><span data-stu-id="fc95c-110">Use Event Viewer to:</span></span>

  - <span data-ttu-id="fc95c-111">Ver y administrar registros de eventos.</span><span class="sxs-lookup"><span data-stu-id="fc95c-111">View and manage event logs.</span></span>

  - <span data-ttu-id="fc95c-112">Obtenga información sobre los problemas de hardware, software y sistema que se deben resolver.</span><span class="sxs-lookup"><span data-stu-id="fc95c-112">Obtain information about hardware, software, and system issues that must be resolved.</span></span>

  - <span data-ttu-id="fc95c-113">Identifique tendencias que requieran una acción futura.</span><span class="sxs-lookup"><span data-stu-id="fc95c-113">Identify trends that require future action.</span></span>

<span data-ttu-id="fc95c-114">Un servidor que ejecuta Lync Server en un sistema operativo de servidor Windows registra eventos en cuatro tipos de registros:</span><span class="sxs-lookup"><span data-stu-id="fc95c-114">A server that is running Lync Server on a Windows Server operating system records events in four types of logs:</span></span>

  - <span data-ttu-id="fc95c-115">**Registros de aplicaciones**   el registro de aplicación contiene eventos registrados por aplicaciones o programas.</span><span class="sxs-lookup"><span data-stu-id="fc95c-115">**Application logs**   The Application log contains events logged by applications or programs.</span></span> <span data-ttu-id="fc95c-116">Los desarrolladores determinan los eventos que se deben registrar.</span><span class="sxs-lookup"><span data-stu-id="fc95c-116">Developers determine which events to log.</span></span> <span data-ttu-id="fc95c-117">Por ejemplo, un programa de base de datos puede grabar un error de archivo en el registro de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="fc95c-117">For example, a database program might record a file error in the Application log.</span></span> <span data-ttu-id="fc95c-118">La mayoría de los eventos relacionados con Lync Server 2013 aparecen en el registro de aplicación.</span><span class="sxs-lookup"><span data-stu-id="fc95c-118">Most Lync Server 2013-related events appear in the Application log.</span></span>

  - <span data-ttu-id="fc95c-119">**Registros de seguridad**   el registro de seguridad graba eventos como intentos válidos y no válidos de inicio de sesión, además de eventos relacionados con el uso de recursos, como crear, abrir o eliminar archivos u otros objetos.</span><span class="sxs-lookup"><span data-stu-id="fc95c-119">**Security logs**   The Security log records events such as valid and not valid logon tries in addition to events related to resource use such as creating, opening, or deleting files or other objects.</span></span> <span data-ttu-id="fc95c-120">Por ejemplo, si la auditoría de inicio de sesión está habilitada, los intentos de iniciar sesión en el sistema se grabarán en el registro de seguridad.</span><span class="sxs-lookup"><span data-stu-id="fc95c-120">For example, if logon auditing is enabled, attempts to log on to the system are recorded in the Security log.</span></span>

  - <span data-ttu-id="fc95c-121">**Registros del sistema**   el registro del sistema contiene eventos registrados por componentes del sistema de Windows.</span><span class="sxs-lookup"><span data-stu-id="fc95c-121">**System logs**   The System log contains events logged by Windows system components.</span></span> <span data-ttu-id="fc95c-122">Por ejemplo, el error de carga de un controlador u otro componente del sistema durante el inicio se graba en el registro del sistema.</span><span class="sxs-lookup"><span data-stu-id="fc95c-122">For example, the failure of a driver or other system component to load during startup is recorded in the System log.</span></span> <span data-ttu-id="fc95c-123">Los tipos de eventos registrados por los componentes del sistema están predeterminados por el servidor.</span><span class="sxs-lookup"><span data-stu-id="fc95c-123">The event types logged by system components are predetermined by the server.</span></span>

  - <span data-ttu-id="fc95c-124">**Lync Server 2013**   la herramienta de registro graba eventos importantes relacionados con la autenticación, las conexiones y las acciones de usuario.</span><span class="sxs-lookup"><span data-stu-id="fc95c-124">**Lync Server 2013**   The logging tool records significant events related to authentication, connections, and user actions.</span></span> <span data-ttu-id="fc95c-125">Después de habilitar el registro de diagnóstico, puede ver las entradas del registro en el visor de eventos.</span><span class="sxs-lookup"><span data-stu-id="fc95c-125">After enabling diagnostic logging, you can view the log entries in Event Viewer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fc95c-126">No se recomienda usar la configuración de registro máxima a menos que se le indique que lo haga el servicio de soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fc95c-126">We do not recommend that you use the maximum logging settings unless you are instructed to do this by Microsoft Customer Support Services.</span></span> <span data-ttu-id="fc95c-127">El registro máximo purga los recursos importantes y puede dar muchos "falsos positivos", es decir, los errores que se registran solo en el registro máximo pero son realmente los esperados y no son causa de preocupación.</span><span class="sxs-lookup"><span data-stu-id="fc95c-127">Maximum logging drains significant resources and can give many “false positives,” that is, errors that get logged only at maximum logging but are really expected and are not a cause of concern.</span></span> <span data-ttu-id="fc95c-128">También le recomendamos que no habilite el registro de diagnóstico de forma permanente.</span><span class="sxs-lookup"><span data-stu-id="fc95c-128">We also recommend that you do not enable diagnostic logging permanently.</span></span> <span data-ttu-id="fc95c-129">Utilícelo solo para solucionar problemas.</span><span class="sxs-lookup"><span data-stu-id="fc95c-129">Use it only when troubleshooting.</span></span>



</div>

<span data-ttu-id="fc95c-130">Dentro de cada registro del visor de eventos, Lync Server 2013 registra eventos informativos, de advertencia y de error.</span><span class="sxs-lookup"><span data-stu-id="fc95c-130">Within each Event Viewer log, Lync Server 2013 records informational, warning, and error events.</span></span> <span data-ttu-id="fc95c-131">Supervise estos registros estrechamente para realizar un seguimiento de los tipos de transacciones que se realizan en los servidores de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fc95c-131">Monitor these logs closely to track the types of transactions being conducted on the Lync Server 2013 servers.</span></span> <span data-ttu-id="fc95c-132">Debe archivar periódicamente los registros o usar la conversión automática para evitar quedarse sin espacio.</span><span class="sxs-lookup"><span data-stu-id="fc95c-132">You should periodically archive the logs or use automatic rollover to avoid running out of space.</span></span> <span data-ttu-id="fc95c-133">Puesto que los archivos de registro pueden ocupar una cantidad de espacio limitada, aumente el tamaño del registro (por ejemplo, a 50 MB) y configúrelo para que el servidor de Lync Server 2013 pueda continuar escribiendo eventos nuevos.</span><span class="sxs-lookup"><span data-stu-id="fc95c-133">Because log files can occupy a finite amount of space, increase the log size (for example, to 50 MB) and set it to overwrite so that the Lync Server 2013 Server can continue to write new events.</span></span>

<span data-ttu-id="fc95c-134">También puede automatizar la administración de registros de eventos con las siguientes herramientas y tecnologías:</span><span class="sxs-lookup"><span data-stu-id="fc95c-134">You can also automate event log administration by using the following tools and technologies:</span></span>

  - <span data-ttu-id="fc95c-135">System Center Operations Manager supervisa el estado y el uso de los servidores de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fc95c-135">System Center Operations Manager monitors the health and use of Lync Server 2013 servers.</span></span> <span data-ttu-id="fc95c-136">El paquete de administración de Lync Server 2013 para Operations Manager amplía Operations Manager al proporcionar una supervisión especializada de los servidores que ejecutan Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fc95c-136">Lync Server 2013 Management Pack for Operations Manager extends Operations Manager by providing specialized monitoring for servers that are running Lync Server 2013.</span></span>

  - <span data-ttu-id="fc95c-137">El paquete de administración de Lync Server 2013 para los monitores de Operations Manager Standard y Enterprise Edition de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fc95c-137">The Lync Server 2013 Management Pack for Operations Manager monitors Standard and Enterprise Edition of Lync Server 2013.</span></span> <span data-ttu-id="fc95c-138">Esta versión también incorpora el paquete de administración de la calidad de la experiencia (QoE), que anteriormente era un módulo de administración independiente.</span><span class="sxs-lookup"><span data-stu-id="fc95c-138">This release also incorporates the Quality of Experience (QoE) Management Pack which was previously a separate management pack.</span></span>

<span data-ttu-id="fc95c-139">Los tipos supervisados son entradas de registro de eventos, contadores de rendimiento y supervisión estatal de QoE.</span><span class="sxs-lookup"><span data-stu-id="fc95c-139">Monitored types are event log entries, performance counters and stateful monitoring of QoE.</span></span> <span data-ttu-id="fc95c-140">Esta versión del módulo de administración solo supervisa Lync Server 2013 y 2010, y no se puede usar para supervisar Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="fc95c-140">This version of the management pack only monitors Lync Server 2013 and 2010, and cannot be used to monitor Office Communications Server 2007.</span></span>

<span data-ttu-id="fc95c-141">El módulo de administración proporciona las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="fc95c-141">The management pack provides the following features:</span></span>

  - <span data-ttu-id="fc95c-142">Alertas que indican eventos que afectan al servicio</span><span class="sxs-lookup"><span data-stu-id="fc95c-142">Alerts indicating service affecting events</span></span>

  - <span data-ttu-id="fc95c-143">Alertas que indican la configuración y otros problemas de impacto sin servicio</span><span class="sxs-lookup"><span data-stu-id="fc95c-143">Alerts indicating configuration, and other non-service impacting issues</span></span>

  - <span data-ttu-id="fc95c-144">Supervisión de estado de los servicios de Lync Server</span><span class="sxs-lookup"><span data-stu-id="fc95c-144">State monitoring of Lync Server services</span></span>

  - <span data-ttu-id="fc95c-145">Conocimiento del producto: causa y solución de problemas identificados</span><span class="sxs-lookup"><span data-stu-id="fc95c-145">Product knowledge: Cause and resolution of identified issues</span></span>

<span data-ttu-id="fc95c-146">Para obtener más información sobre el paquete de administración de Lync Server 2013, consulte monitorización de [Lync server 2013 con System Center Operations Manager](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md).</span><span class="sxs-lookup"><span data-stu-id="fc95c-146">For more information about Lync Server 2013 Management Pack, refer to [Monitoring Lync Server 2013 with System Center Operations Manager](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md).</span></span>

<span data-ttu-id="fc95c-147">**Event COMB**   la herramienta Event COMB recopila eventos específicos de los registros de eventos de varios equipos a una ubicación centralizada.</span><span class="sxs-lookup"><span data-stu-id="fc95c-147">**Event Comb**   The Event Comb tool collects specific events from the event logs of several computers to one central location.</span></span> <span data-ttu-id="fc95c-148">Le permite denunciar únicamente los identificadores de eventos o los orígenes de eventos que especifique.</span><span class="sxs-lookup"><span data-stu-id="fc95c-148">It lets you report on only the event IDs or event sources it specifies.</span></span> <span data-ttu-id="fc95c-149">Para obtener más información acerca de Event COMB, consulte el sitio web de [herramientas de bloqueo y administración de cuentas](http://go.microsoft.com/fwlink/?linkid=35607) .</span><span class="sxs-lookup"><span data-stu-id="fc95c-149">For more information about Event Comb, see the [Account Lockout and Management Tools](http://go.microsoft.com/fwlink/?linkid=35607) website.</span></span>

<span data-ttu-id="fc95c-150">**Desencadenadores de eventos**   en Windows Server 2012 puede "adjuntar una tarea a este evento" dentro del visor de eventos de Windows, donde un administrador puede ejecutar un programa, enviar un mensaje de correo electrónico o mostrar un mensaje en pantalla.</span><span class="sxs-lookup"><span data-stu-id="fc95c-150">**Event triggers**   In Windows Server 2012 you can "Attach a Task to This Event" within the Windows Event Viewer—where an administrator can either run a program, send an email message or display an on-screen message.</span></span> <span data-ttu-id="fc95c-151">Para obtener más información sobre esta característica, vea el tema sobre Windows Server 2008 R2 [ejecutar una tarea en respuesta a un evento determinado](http://technet.microsoft.com/en-us/library/cc748900.aspx).</span><span class="sxs-lookup"><span data-stu-id="fc95c-151">For more information about this feature, see the Windows Server 2008 R2 topic [Run a Task in Response to a Given Event](http://technet.microsoft.com/en-us/library/cc748900.aspx).</span></span> <span data-ttu-id="fc95c-152">También puede usar herramientas de línea de comandos, como ' EventTrigger. exe ', para crear y consultar registros de eventos y asociar programas con determinados eventos registrados.</span><span class="sxs-lookup"><span data-stu-id="fc95c-152">You can also use command-line tools such as ‘Eventtrigger.exe’ to create and query event logs and associate programs with particular logged events.</span></span> <span data-ttu-id="fc95c-153">Mediante eventtriggers. exe puede crear desencadenadores de eventos que ejecuten programas cuando se produzcan eventos específicos.</span><span class="sxs-lookup"><span data-stu-id="fc95c-153">By using Eventtriggers.exe, you can create event triggers that run programs when specific events occur.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="fc95c-154">Vea también</span><span class="sxs-lookup"><span data-stu-id="fc95c-154">See Also</span></span>


[<span data-ttu-id="fc95c-155">Visor de eventos de Windows</span><span class="sxs-lookup"><span data-stu-id="fc95c-155">Windows Event Viewer</span></span>](http://go.microsoft.com/fwlink/p/?linkid=314067)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

