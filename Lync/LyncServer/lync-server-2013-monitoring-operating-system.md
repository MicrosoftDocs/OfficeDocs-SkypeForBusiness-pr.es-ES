---
title: 'Lync Server 2013: supervisar el sistema operativo'
description: 'Lync Server 2013: supervisar el sistema operativo.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring operating system
ms:assetid: 72406d3e-54c8-4796-8d6d-2144a5b6f030
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720918(v=OCS.15)
ms:contentKeyID: 63969617
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d9454b91a5f55467f93b41752686b4b0d727d935
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548066"
---
# <a name="monitoring-operating-system-in-lync-server-2013"></a><span data-ttu-id="a7d33-103">Supervisar el sistema operativo en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a7d33-103">Monitoring operating system in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a7d33-104">_**Última modificación del tema:** 2015-01-26_</span><span class="sxs-lookup"><span data-stu-id="a7d33-104">_**Topic Last Modified:** 2015-01-26_</span></span>

<span data-ttu-id="a7d33-105">Debe supervisar el rendimiento de todos los servidores y componentes en el 2013 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a7d33-105">You must monitor the performance of all servers and components in the Lync Server 2013.</span></span> <span data-ttu-id="a7d33-106">Obviamente, uno de los componentes más importantes es el propio sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="a7d33-106">Obviously, one of the most important components is the operating system itself.</span></span> <span data-ttu-id="a7d33-107">Lync Server 2013 admite ediciones x64 de:</span><span class="sxs-lookup"><span data-stu-id="a7d33-107">Lync Server 2013 supports x64 editions of:</span></span>

  - <span data-ttu-id="a7d33-108">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="a7d33-108">Windows Server 2008 R2</span></span>

  - <span data-ttu-id="a7d33-109">Windows Server 2012 y Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="a7d33-109">Windows Server 2012 and Windows Server 2012 R2</span></span>

<span data-ttu-id="a7d33-110">La forma más transparente de supervisar un sistema operativo es mediante el módulo de administración del sistema operativo de Windows Server.</span><span class="sxs-lookup"><span data-stu-id="a7d33-110">The most transparent way to monitor an operating system is by using Windows Server Operating System Management Pack.</span></span> <span data-ttu-id="a7d33-111">Proporciona los conceptos básicos de supervisión fundamentales, como rendimiento, estado y disponibilidad para los equipos que ejecutan Windows Server 2012, Windows Server 2012 R2 y Windows Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="a7d33-111">It provides the fundamental monitoring basics, such as performance, health, and availability for computers that are running Windows Server 2012, Windows Server 2012 R2, and Windows Server 2008 R2.</span></span>

<span data-ttu-id="a7d33-112">Al detectar, alertar y responder automáticamente a eventos importantes y indicadores de rendimiento, estos módulos de administración reducen los tiempos de resolución de problemas y aumentan la disponibilidad y el rendimiento generales de los sistemas que ejecutan los sistemas operativos de Windows Server.</span><span class="sxs-lookup"><span data-stu-id="a7d33-112">By detecting, alerting, and automatically responding to important events and performance indicators, these management packs reduce resolution times for issues and increase the overall availability and performance of systems that are running the Windows Server operating systems.</span></span>

<span data-ttu-id="a7d33-113">Aparte de los paquetes de administración de Windows Server relevantes para System Center Operations Manager, se pueden usar las siguientes herramientas y recursos del sistema para supervisar el estado del sistema operativo (en función de la versión del sistema operativo).</span><span class="sxs-lookup"><span data-stu-id="a7d33-113">Apart from relevant Windows Server management packs for System Center Operations Manager, the following system tools and resources can be used to monitor the health of the operating system (depending on the operating system version).</span></span>

<div>

## <a name="windows-server2008r2"></a><span data-ttu-id="a7d33-114">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="a7d33-114">Windows Server 2008 R2</span></span>

<span data-ttu-id="a7d33-115">Windows Server 2008 R2 incluye las siguientes características y herramientas adicionales para ayudar a los administradores con la supervisión y administración básica del sistema operativo:</span><span class="sxs-lookup"><span data-stu-id="a7d33-115">Windows Server 2008 R2 includes the following additional features and tools to help administrators with basic operating system monitoring and management:</span></span>

  - <span data-ttu-id="a7d33-116">El **monitor de recursos de Windows** es una herramienta eficaz para comprender cómo los procesos y servicios usan los recursos del sistema.</span><span class="sxs-lookup"><span data-stu-id="a7d33-116">**Windows Resource Monitor** is a powerful tool for understanding how system resources are used by processes and services.</span></span> <span data-ttu-id="a7d33-117">Además de supervisar el uso de los recursos en tiempo real, el monitor de recursos puede ayudar a analizar los procesos que no responden, identificar qué aplicaciones usan los archivos y controlar los procesos y servicios.</span><span class="sxs-lookup"><span data-stu-id="a7d33-117">In addition to monitoring resource usage in real time, a Resource Monitor can help analyze unresponsive processes, identify which applications are using files, and control processes and services.</span></span>

  - <span data-ttu-id="a7d33-118">El **componente de análisis de confiabilidad** es un agente en el equipo que proporciona información detallada sobre el uso y la confiabilidad del sistema.</span><span class="sxs-lookup"><span data-stu-id="a7d33-118">**Reliability Analysis Component** is an in-box agent that provides detailed experience information on system usage and reliability.</span></span> <span data-ttu-id="a7d33-119">Esta información se expone a través de una interfaz WMI para que esté disponible para su consumo por parte de los lectores portátiles.</span><span class="sxs-lookup"><span data-stu-id="a7d33-119">This information is exposed through a WMI interface to make it available for consumption by Portable Readers Systems.</span></span> <span data-ttu-id="a7d33-120">Al exponer el componente de análisis de confiabilidad a través de una interfaz WMI, los desarrolladores pueden supervisar y analizar aplicaciones, lo que aumenta la confiabilidad y el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="a7d33-120">By exposing Reliability Analysis Component through a WMI interface, developers can monitor and analyze applications, increasing reliability and performance.</span></span>

  - <span data-ttu-id="a7d33-121">**Windows Server 2008 R2** utiliza el componente de análisis de confiabilidad integrado para calcular un índice de confiabilidad, que proporciona información sobre el uso y la estabilidad generales del sistema a lo largo del tiempo.</span><span class="sxs-lookup"><span data-stu-id="a7d33-121">**Windows Server 2008 R2** uses the built-in Reliability Analysis Component to calculate a reliability index, which provides information about overall system usage and stability over time.</span></span> <span data-ttu-id="a7d33-122">El componente de análisis de confiabilidad también realiza un seguimiento de cualquier cambio importante en el sistema que pueda afectar a la estabilidad, como las actualizaciones de Windows y las instalaciones de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="a7d33-122">The Reliability Analysis Component also keeps track of any important changes to the system that are likely to influence stability, such as Windows updates and application installations.</span></span>

</div>

<div>

## <a name="windows-server2008-windows-reliability-and-performance-monitor"></a><span data-ttu-id="a7d33-123">Monitor de confiabilidad y rendimiento de Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="a7d33-123">Windows Server 2008 Windows Reliability and Performance Monitor</span></span>

<span data-ttu-id="a7d33-124">El monitor de confiabilidad y rendimiento de Windows es un complemento MMC que combina la funcionalidad de herramientas independientes anteriores, como registros y alertas de rendimiento, asesor de rendimiento del servidor y monitor del sistema.</span><span class="sxs-lookup"><span data-stu-id="a7d33-124">Windows Reliability and Performance Monitor is an MMC Snap-in that combines the functionality of previous stand-alone tools including Performance Logs and Alerts, Server Performance Advisor, and System Monitor.</span></span> <span data-ttu-id="a7d33-125">Proporciona una interfaz gráfica para la personalización de sesiones de seguimiento de eventos y recopilación de datos de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="a7d33-125">It provides a graphical interface for customizing performance data collection and Event Trace Sessions.</span></span>

<span data-ttu-id="a7d33-126">También incluye el monitor de confiabilidad, un complemento de MMC que realiza un seguimiento de los cambios en el sistema y los compara con los cambios en la estabilidad del sistema, y proporciona una vista gráfica de su relación.</span><span class="sxs-lookup"><span data-stu-id="a7d33-126">It also includes Reliability Monitor, an MMC Snap-in that tracks changes to the system and compares them to changes in system stability, and it provides a graphical view of their relationship.</span></span>

</div>

<div>

## <a name="windows-reliability-and-performance-monitor"></a><span data-ttu-id="a7d33-127">Monitor de confiabilidad y rendimiento de Windows</span><span class="sxs-lookup"><span data-stu-id="a7d33-127">Windows Reliability and Performance Monitor</span></span>

<span data-ttu-id="a7d33-128">Mientras que el monitor de confiabilidad y rendimiento de Windows combina funcionalidades de algunas herramientas independientes anteriores, como registros y alertas de rendimiento, y el monitor del sistema y el asesor de rendimiento del servidor, también ofrece una funcionalidad nueva a Windows Server 2008 y Windows Server 2008 R2, como las siguientes:</span><span class="sxs-lookup"><span data-stu-id="a7d33-128">While Windows Reliability and Performance Monitor combine functionalities of some former stand-alone tools such as Performance Logs and Alerts, and System Monitor and Server Performance Advisor, it also provides some new functionality to Windows Server 2008 and Windows Server 2008 R2, such as the following:</span></span>

  - <span data-ttu-id="a7d33-129">Conjuntos de recopiladores de datos</span><span class="sxs-lookup"><span data-stu-id="a7d33-129">Data Collector Sets</span></span>

  - <span data-ttu-id="a7d33-130">Vista de recursos</span><span class="sxs-lookup"><span data-stu-id="a7d33-130">Resource View</span></span>

  - <span data-ttu-id="a7d33-131">Monitor de confiabilidad</span><span class="sxs-lookup"><span data-stu-id="a7d33-131">Reliability Monitor</span></span>

  - <span data-ttu-id="a7d33-132">Asistentes y plantillas para crear registros</span><span class="sxs-lookup"><span data-stu-id="a7d33-132">Wizards and templates for creating logs</span></span>

<span data-ttu-id="a7d33-133">El **conjunto de recopiladores de datos** agrupa los recopiladores de datos en elementos reutilizables para su uso con diferentes escenarios de supervisión de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="a7d33-133">**Data Collector Set** groups data collectors into reusable elements for use with different performance monitoring scenarios.</span></span> <span data-ttu-id="a7d33-134">Una vez que se almacena un grupo de recopiladores de datos como un conjunto de recopiladores de datos, se pueden aplicar operaciones como la programación a todo el conjunto mediante un único cambio de propiedad. El monitor de confiabilidad y rendimiento de Windows incluye plantillas predeterminadas de conjunto de recopiladores de datos para ayudar a los administradores de sistema a recopilar inmediatamente datos de rendimiento específicos de un rol de servidor o un escenario de supervisión.</span><span class="sxs-lookup"><span data-stu-id="a7d33-134">After a group of data collectors are stored as a Data Collector Set, operations such as scheduling can be applied to the whole set through a single property change.Windows Reliability and Performance Monitor includes default Data Collector Set templates to help system administrators begin immediately collecting performance data that is specific to a server role or monitoring scenario.</span></span>

<span data-ttu-id="a7d33-135">La Página principal del monitor de confiabilidad y rendimiento de Windows es la nueva pantalla **vista de recursos** , que proporciona una introducción gráfica en tiempo real del uso de la CPU, el disco, la red y la memoria.</span><span class="sxs-lookup"><span data-stu-id="a7d33-135">The home page of Windows Reliability and Performance Monitor is the new **Resource View** screen, which provides a real-time graphical overview of CPU, disk, network, and memory usage.</span></span> <span data-ttu-id="a7d33-136">Expandiendo cada uno de estos elementos supervisados, los administradores del sistema pueden identificar qué recursos usan qué recursos.</span><span class="sxs-lookup"><span data-stu-id="a7d33-136">By expanding each of these monitored elements, system administrators can identify which processes are using which resources.</span></span> <span data-ttu-id="a7d33-137">En versiones anteriores de Windows, estos datos en tiempo real y específicos del proceso solo estaban disponibles en un formulario limitado en el administrador de tareas.</span><span class="sxs-lookup"><span data-stu-id="a7d33-137">In earlier versions of Windows, this real-time, process-specific data was available only in limited form in Task Manager.</span></span>

<span data-ttu-id="a7d33-138">El **monitor de confiabilidad** calcula un índice de estabilidad del sistema que refleja si los problemas inesperados han reducido la confiabilidad del sistema.</span><span class="sxs-lookup"><span data-stu-id="a7d33-138">**Reliability Monitor** calculates a System Stability Index that reflects whether unexpected issues reduced the reliability of the system.</span></span> <span data-ttu-id="a7d33-139">Un gráfico del índice de estabilidad a lo largo del tiempo identifica rápidamente las fechas en las que comenzaron a producirse los problemas.</span><span class="sxs-lookup"><span data-stu-id="a7d33-139">A graph of the Stability Index over time quickly identifies dates when issues began to occur.</span></span> <span data-ttu-id="a7d33-140">El informe de estabilidad del sistema adjunto proporciona detalles para ayudar a solucionar la causa de la menor confiabilidad.</span><span class="sxs-lookup"><span data-stu-id="a7d33-140">The accompanying System Stability Report provides details to help troubleshoot the cause of reduced reliability.</span></span> <span data-ttu-id="a7d33-141">Mediante la visualización de los cambios en el sistema (instalación o eliminación de aplicaciones, actualizaciones del sistema operativo, o adición o modificación de controladores) en paralelo con los errores (errores de aplicaciones, bloqueos del sistema operativo o errores de hardware), se puede desarrollar rápidamente una estrategia para solucionar los problemas.</span><span class="sxs-lookup"><span data-stu-id="a7d33-141">By viewing changes to the system (installation or removal of applications, updates to the operating system, or addition or modification of drivers) side by side with failures (application failures, operating system crashes, or hardware failures), a strategy for addressing the issues can be developed quickly.</span></span>

<span data-ttu-id="a7d33-142">La adición de contadores a los archivos de registro y la programación de inicio, detención y duración se pueden realizar ahora a través de una **interfaz de asistente**.</span><span class="sxs-lookup"><span data-stu-id="a7d33-142">Adding counters to log files and scheduling their start, stop, and duration can now be performed through a **Wizard interface**.</span></span> <span data-ttu-id="a7d33-143">Además, si se guarda esta configuración como una plantilla, los administradores del sistema pueden recopilar el mismo registro en otros equipos sin repetir los procesos de programación y selección del recopilador de datos.</span><span class="sxs-lookup"><span data-stu-id="a7d33-143">In addition, saving this configuration as a template enables system administrators to collect the same log on other computers without repeating the data collector selection and scheduling processes.</span></span> <span data-ttu-id="a7d33-144">Las características de registros y alertas de rendimiento se incorporaron en el monitor de confiabilidad y rendimiento de Windows para su uso con cualquier conjunto de recopiladores de datos.</span><span class="sxs-lookup"><span data-stu-id="a7d33-144">Performance Logs and Alerts features were incorporated into the Windows Reliability and Performance Monitor for use with any Data Collector Set.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

