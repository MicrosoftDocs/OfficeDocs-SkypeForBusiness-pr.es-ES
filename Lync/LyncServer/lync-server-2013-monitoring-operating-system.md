---
title: 'Lync Server 2013: supervisar el sistema operativo'
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
ms.openlocfilehash: 42ac03f61fca5717d279d39e703a8ffa97e8c2cf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756794"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-operating-system-in-lync-server-2013"></a><span data-ttu-id="1f3da-102">Supervisar el sistema operativo en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1f3da-102">Monitoring operating system in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1f3da-103">_**Última modificación del tema:** 2015-01-26_</span><span class="sxs-lookup"><span data-stu-id="1f3da-103">_**Topic Last Modified:** 2015-01-26_</span></span>

<span data-ttu-id="1f3da-104">Debe supervisar el rendimiento de todos los servidores y componentes de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1f3da-104">You must monitor the performance of all servers and components in the Lync Server 2013.</span></span> <span data-ttu-id="1f3da-105">Como es obvio, uno de los componentes más importantes es el propio sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="1f3da-105">Obviously, one of the most important components is the operating system itself.</span></span> <span data-ttu-id="1f3da-106">Lync Server 2013 admite ediciones x64 de:</span><span class="sxs-lookup"><span data-stu-id="1f3da-106">Lync Server 2013 supports x64 editions of:</span></span>

  - <span data-ttu-id="1f3da-107">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="1f3da-107">Windows Server 2008 R2</span></span>

  - <span data-ttu-id="1f3da-108">Windows Server 2012 y Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="1f3da-108">Windows Server 2012 and Windows Server 2012 R2</span></span>

<span data-ttu-id="1f3da-109">La manera más transparente de supervisar un sistema operativo es mediante el módulo de administración de Windows Server Operating System.</span><span class="sxs-lookup"><span data-stu-id="1f3da-109">The most transparent way to monitor an operating system is by using Windows Server Operating System Management Pack.</span></span> <span data-ttu-id="1f3da-110">Proporciona los conceptos básicos de supervisión fundamentales, como el rendimiento, la salud y la disponibilidad para equipos que ejecutan Windows Server 2012, Windows Server 2012 R2 y Windows Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="1f3da-110">It provides the fundamental monitoring basics, such as performance, health, and availability for computers that are running Windows Server 2012, Windows Server 2012 R2, and Windows Server 2008 R2.</span></span>

<span data-ttu-id="1f3da-111">Al detectar, alertar y responder automáticamente a los eventos importantes y a los indicadores de rendimiento, estos módulos de administración reducen los tiempos de resolución de problemas y aumentan la disponibilidad general y el rendimiento de los sistemas que ejecutan Windows Server sistemas operativos.</span><span class="sxs-lookup"><span data-stu-id="1f3da-111">By detecting, alerting, and automatically responding to important events and performance indicators, these management packs reduce resolution times for issues and increase the overall availability and performance of systems that are running the Windows Server operating systems.</span></span>

<span data-ttu-id="1f3da-112">Aparte de los paquetes de administración de Windows Server relevantes para System Center Operations Manager, se pueden usar las siguientes herramientas y recursos del sistema para supervisar el estado del sistema operativo (según la versión del sistema operativo).</span><span class="sxs-lookup"><span data-stu-id="1f3da-112">Apart from relevant Windows Server management packs for System Center Operations Manager, the following system tools and resources can be used to monitor the health of the operating system (depending on the operating system version).</span></span>

<div>

## <a name="windows-server2008r2"></a><span data-ttu-id="1f3da-113">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="1f3da-113">Windows Server 2008 R2</span></span>

<span data-ttu-id="1f3da-114">Windows Server 2008 R2 incluye las siguientes características y herramientas adicionales para ayudar a los administradores a supervisar y administrar sistemas operativos:</span><span class="sxs-lookup"><span data-stu-id="1f3da-114">Windows Server 2008 R2 includes the following additional features and tools to help administrators with basic operating system monitoring and management:</span></span>

  - <span data-ttu-id="1f3da-p103">El **Monitor de recursos de Windows** es una potente herramienta para entender el uso que los procesos y servicios hacen de los recursos del sistema. Además de supervisar este uso en tiempo real, el Monitor de recursos puede ayudar a analizar procesos que no responden, identificar las aplicaciones que usan archivos y controlar los procesos y servicios.</span><span class="sxs-lookup"><span data-stu-id="1f3da-p103">**Windows Resource Monitor** is a powerful tool for understanding how system resources are used by processes and services. In addition to monitoring resource usage in real time, a Resource Monitor can help analyze unresponsive processes, identify which applications are using files, and control processes and services.</span></span>

  - <span data-ttu-id="1f3da-p104">El **Componente de análisis de confiabilidad** es un agente integrado que proporciona información de experiencia detallada sobre el uso y la fiabilidad del sistema. Esta información se muestra mediante una interfaz WMI para hacerla disponible en sistemas de lectura portátil. Al mostrar el Componente de análisis de confiabilidad en una interfaz WMI, los desarrolladores pueden supervisar y analizar las aplicaciones, lo que aumenta la fiabilidad y el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="1f3da-p104">**Reliability Analysis Component** is an in-box agent that provides detailed experience information on system usage and reliability. This information is exposed through a WMI interface to make it available for consumption by Portable Readers Systems. By exposing Reliability Analysis Component through a WMI interface, developers can monitor and analyze applications, increasing reliability and performance.</span></span>

  - <span data-ttu-id="1f3da-120">**Windows Server 2008 R2** usa el componente de análisis de confiabilidad integrado para calcular un índice de confiabilidad, que proporciona información sobre el uso y la estabilidad generales del sistema a lo largo del tiempo.</span><span class="sxs-lookup"><span data-stu-id="1f3da-120">**Windows Server 2008 R2** uses the built-in Reliability Analysis Component to calculate a reliability index, which provides information about overall system usage and stability over time.</span></span> <span data-ttu-id="1f3da-121">The Reliability Analysis Component also keeps track of any important changes to the system that are likely to influence stability, such as Windows updates and application installations.</span><span class="sxs-lookup"><span data-stu-id="1f3da-121">The Reliability Analysis Component also keeps track of any important changes to the system that are likely to influence stability, such as Windows updates and application installations.</span></span>

</div>

<div>

## <a name="windows-server2008-windows-reliability-and-performance-monitor"></a><span data-ttu-id="1f3da-122">Monitor de confiabilidad y rendimiento de Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="1f3da-122">Windows Server 2008 Windows Reliability and Performance Monitor</span></span>

<span data-ttu-id="1f3da-p106">El Monitor de confiabilidad y rendimiento de Windows es un componente MMC que combina la funcionalidad de anteriores herramientas independientes, como Registros y alertas de rendimiento, Asesor de rendimiento de servidor y Monitor del sistema. Ofrece una interfaz gráfica para personalizar la obtención de datos y las sesiones de seguimiento de eventos.</span><span class="sxs-lookup"><span data-stu-id="1f3da-p106">Windows Reliability and Performance Monitor is an MMC Snap-in that combines the functionality of previous stand-alone tools including Performance Logs and Alerts, Server Performance Advisor, and System Monitor. It provides a graphical interface for customizing performance data collection and Event Trace Sessions.</span></span>

<span data-ttu-id="1f3da-125">También incluye el Monitor de confiabilidad, un componente MMC que hace un seguimiento de los cambios del sistema y los compara con los cambios en la estabilidad del mismo, ofreciendo una vista gráfica de la relación.</span><span class="sxs-lookup"><span data-stu-id="1f3da-125">It also includes Reliability Monitor, an MMC Snap-in that tracks changes to the system and compares them to changes in system stability, and it provides a graphical view of their relationship.</span></span>

</div>

<div>

## <a name="windows-reliability-and-performance-monitor"></a><span data-ttu-id="1f3da-126">Monitor de confiabilidad y rendimiento de Windows</span><span class="sxs-lookup"><span data-stu-id="1f3da-126">Windows Reliability and Performance Monitor</span></span>

<span data-ttu-id="1f3da-127">Mientras que el monitor de confiabilidad y rendimiento de Windows combina funcionalidades de algunas herramientas independientes, como registros y alertas de rendimiento, y el monitor de sistema y el rendimiento del servidor, también proporciona una nueva funcionalidad a Windows Server 2008 y Windows Server 2008 R2, como el siguiente:</span><span class="sxs-lookup"><span data-stu-id="1f3da-127">While Windows Reliability and Performance Monitor combine functionalities of some former stand-alone tools such as Performance Logs and Alerts, and System Monitor and Server Performance Advisor, it also provides some new functionality to Windows Server 2008 and Windows Server 2008 R2, such as the following:</span></span>

  - <span data-ttu-id="1f3da-128">Conjuntos de recopiladores de datos</span><span class="sxs-lookup"><span data-stu-id="1f3da-128">Data Collector Sets</span></span>

  - <span data-ttu-id="1f3da-129">Vista de recursos</span><span class="sxs-lookup"><span data-stu-id="1f3da-129">Resource View</span></span>

  - <span data-ttu-id="1f3da-130">Monitor de confiabilidad</span><span class="sxs-lookup"><span data-stu-id="1f3da-130">Reliability Monitor</span></span>

  - <span data-ttu-id="1f3da-131">Asistentes y plantillas de creación de registros</span><span class="sxs-lookup"><span data-stu-id="1f3da-131">Wizards and templates for creating logs</span></span>

<span data-ttu-id="1f3da-p107">Un **conjunto de recopiladores de datos** agrupa estos recopiladores en elementos reutilizables para su uso con distintos entornos de supervisión del rendimiento. Cuando un grupo se guarda como conjunto de recopiladores de datos, con solo cambiar una propiedad es posible aplicar al conjunto entero operaciones tales como la programación. El Monitor de confiabilidad y rendimiento de Windows incluye plantillas predeterminadas de conjuntos de recopiladores de datos para ayudar a los administradores del sistema a comenzar de inmediato a recopilar datos de rendimiento de un rol de servidor o un entorno de supervisión específicos.</span><span class="sxs-lookup"><span data-stu-id="1f3da-p107">**Data Collector Set** groups data collectors into reusable elements for use with different performance monitoring scenarios. After a group of data collectors are stored as a Data Collector Set, operations such as scheduling can be applied to the whole set through a single property change.Windows Reliability and Performance Monitor includes default Data Collector Set templates to help system administrators begin immediately collecting performance data that is specific to a server role or monitoring scenario.</span></span>

<span data-ttu-id="1f3da-p108">La página de inicio del Monitor de confiabilidad y rendimiento de Windows es la nueva pantalla **Vista de recursos**, que proporciona una imagen gráfica y en tiempo real del uso de CPU, discos, red y memoria. Los administradores del sistema pueden expandir cada uno de estos elementos para identificar qué recursos emplea cada proceso. En versiones anteriores de Windows, estos datos en tiempo real de procesos concretos solo estaban disponibles, y de forma limitada, desde el Administrador de tareas.</span><span class="sxs-lookup"><span data-stu-id="1f3da-p108">The home page of Windows Reliability and Performance Monitor is the new **Resource View** screen, which provides a real-time graphical overview of CPU, disk, network, and memory usage. By expanding each of these monitored elements, system administrators can identify which processes are using which resources. In earlier versions of Windows, this real-time, process-specific data was available only in limited form in Task Manager.</span></span>

<span data-ttu-id="1f3da-p109">El **Monitor de confiabilidad** calcula un índice de estabilidad que refleja si alguna incidencia inesperada ha reducido la fiabilidad del sistema. Un gráfico del índice a lo largo del tiempo identifica rápidamente el momento en que comenzaron a producirse incidencias. El informe de estabilidad del sistema proporciona detalles que ayudan a determinar la causa de la pérdida de fiabilidad. Ver los cambios producidos (instalación o eliminación de aplicaciones, actualizaciones del sistema operativo o agregación o modificación de controladores) junto a los errores (errores de aplicaciones, bloqueos del sistema operativo o errores de hardware) permite desarrollar rápidamente una estrategia para abordar las incidencias.</span><span class="sxs-lookup"><span data-stu-id="1f3da-p109">**Reliability Monitor** calculates a System Stability Index that reflects whether unexpected issues reduced the reliability of the system. A graph of the Stability Index over time quickly identifies dates when issues began to occur. The accompanying System Stability Report provides details to help troubleshoot the cause of reduced reliability. By viewing changes to the system (installation or removal of applications, updates to the operating system, or addition or modification of drivers) side by side with failures (application failures, operating system crashes, or hardware failures), a strategy for addressing the issues can be developed quickly.</span></span>

<span data-ttu-id="1f3da-p110">Una **interfaz de asistente** permite ahora agregar contadores a archivos de registro y programar su inicio, finalización y duración. Además, los administradores del sistema pueden guardar esta configuración como plantilla para recopilar el mismo registro en otro equipo sin necesidad de repetir la selección de recopiladores de datos y la programación de procesos. En el Monitor de confiabilidad y rendimiento de Windows si incorporaron características de Registros y alertas de rendimiento para su uso con cualquier conjunto de recopiladores de datos.</span><span class="sxs-lookup"><span data-stu-id="1f3da-p110">Adding counters to log files and scheduling their start, stop, and duration can now be performed through a **Wizard interface**. In addition, saving this configuration as a template enables system administrators to collect the same log on other computers without repeating the data collector selection and scheduling processes. Performance Logs and Alerts features were incorporated into the Windows Reliability and Performance Monitor for use with any Data Collector Set.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

