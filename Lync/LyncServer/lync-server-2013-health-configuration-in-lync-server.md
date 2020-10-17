---
title: 'Lync Server 2013: configuración de mantenimiento en Lync Server'
description: 'Lync Server 2013: configuración de mantenimiento en Lync Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Health configuration in Lync Server 2013
ms:assetid: c00a8c8e-c2d2-4557-8c42-211c7cc96550
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205234(v=OCS.15)
ms:contentKeyID: 48185305
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 999a6d5401cb34382a4120f9255c91c846f72422
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552856"
---
# <a name="health-configuration-in-lync-server-2013"></a><span data-ttu-id="1ae45-103">Configuración de mantenimiento en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ae45-103">Health configuration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ae45-104">_**Última modificación del tema:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="1ae45-104">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="1ae45-105">Entre los diversos sitios web, los artículos de Microsoft Knowledge base y las herramientas del kit de recursos de Lync Server, los administradores que se enfrentan a problemas al ejecutar Lync Server nunca están lejos de una forma de resolver estos problemas.</span><span class="sxs-lookup"><span data-stu-id="1ae45-105">Between various websites, Microsoft Knowledge Base articles, and Lync Server Resource Kit tools, administrators who encounter problems when running Lync Server are never far from a way to solve those problems.</span></span>

<span data-ttu-id="1ae45-106">Obviamente, no hay forma de garantizar que nunca se produzcan problemas con Lync Server 2013 porque Lync Server se puede ver afectado por muchas cosas, como los bloqueos de red y los errores de hardware, que el producto en sí no puede controlar.</span><span class="sxs-lookup"><span data-stu-id="1ae45-106">Obviously there is no way to guarantee that you will never encounter problems with Lync Server 2013 because Lync Server can be affected by many things—like network crashes and hardware failures—that the product itself cannot control.</span></span> <span data-ttu-id="1ae45-107">Mediante la implementación de la supervisión de estado, los administradores pueden identificar posibles problemas antes de que se conviertan en problemas reales.</span><span class="sxs-lookup"><span data-stu-id="1ae45-107">By implementing health monitoring, administrators can identify potential problems before they turn into actual problems.</span></span> <span data-ttu-id="1ae45-108">Por ejemplo, los administradores pueden usar la supervisión de Lync Server para identificar tendencias y Tendencies.</span><span class="sxs-lookup"><span data-stu-id="1ae45-108">For example, administrators can use Lync Server monitoring to identify trends and tendencies.</span></span> <span data-ttu-id="1ae45-109">Por ejemplo, un aumento constante en el número de conferencias de audio y vídeo puede sugerir una necesidad de agregar capacidad antes de que el sistema se sobrecargue.</span><span class="sxs-lookup"><span data-stu-id="1ae45-109">For example, a steady increase in the number of audio/video conferences might suggest a need to add capacity before the system becomes overloaded.</span></span>

<span data-ttu-id="1ae45-110">De manera similar, los administradores pueden usar System Center Operations Manager para realizar tareas como emitir alertas en tiempo real cuando se produzcan eventos específicos y ejecutar transacciones sintéticas que prueben proactivamente el sistema.</span><span class="sxs-lookup"><span data-stu-id="1ae45-110">In a similar fashion, administrators can use System Center Operations Manager to do such things as issue real-time alerts when specified events occur, and to run synthetic transactions that proactively test the system.</span></span> <span data-ttu-id="1ae45-111">Las transacciones sintéticas se usan en Lync Server para comprobar que los usuarios puedan completar correctamente tareas comunes como iniciar sesión en el sistema, intercambiar mensajes instantáneos o realizar llamadas a un teléfono ubicado en la red telefónica conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="1ae45-111">Synthetic transactions are used in Lync Server to verify that users are able to successfully complete common tasks such as logging on to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="1ae45-112">Por ejemplo, la ejecución periódica de estas pruebas puede alertarle de posibles problemas con los usuarios que inician sesión en Lync Server y le da la oportunidad de corregir el problema antes de que su equipo de soporte se inunde con llamadas de los usuarios que no pueden establecer una conexión.</span><span class="sxs-lookup"><span data-stu-id="1ae45-112">For example, periodically running these tests can alert you to potential problems with users logging on to Lync Server, and give you a chance to correct the problem before your support team is flooded with calls from users unable to make a connection.</span></span> <span data-ttu-id="1ae45-113">Mediante el uso de System Center Operations Manager para ejecutar estas transacciones sintéticas, los administradores pueden supervisar de forma rutinaria su implementación de Lync Server continuamente durante 24 horas al día, sin tener que hacer nada más allá de responder a las alertas que se puedan emitir.</span><span class="sxs-lookup"><span data-stu-id="1ae45-113">By using System Center Operations Manager to run these synthetic transactions, administrators can routinely monitor their deployment of Lync Server continuously for 24 hours every day without having to do much of anything beyond responding to any alerts that might be issued.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1ae45-114">Para Lync Server 2013, el módulo de administración de System Center Operations Manager también puede detectar problemas "externos" que pueden afectar negativamente a Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1ae45-114">For Lync Server 2013, the Management Pack for System Center Operations Manager is also able to detect "external" issues that can adversely affect Lync Server.</span></span> <span data-ttu-id="1ae45-115">Por ejemplo, se puede notificar a los administradores si Internet Information Services (IIS) se desconecta, los recursos del sistema en un equipo de Lync Server están por debajo de una cantidad determinada o un equipo de Lync Server experimenta un error de hardware.</span><span class="sxs-lookup"><span data-stu-id="1ae45-115">For example, administrators can be notified if Internet Information Services (IIS) goes offline, system resources on a Lync Server computer fall below a specified amount, or a Lync Server computer experiences a hardware failure.</span></span>



</div>

<span data-ttu-id="1ae45-116">La configuración de mantenimiento de Lync Server 2013 se basa en System Center Operations Manager y el uso de los paquetes de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1ae45-116">Health configuration in Lync Server 2013 is built around System Center Operations Manager and the use of Lync Server Management Packs.</span></span> <span data-ttu-id="1ae45-117">Estos módulos de administración incluyen varias características y mejoras nuevas, como:</span><span class="sxs-lookup"><span data-stu-id="1ae45-117">These Management Packs include a number of new features and enhancements, including:</span></span>

  - <span data-ttu-id="1ae45-118">**Disponibilidad de escenario desde cualquier ubicación.**</span><span class="sxs-lookup"><span data-stu-id="1ae45-118">**Scenario availability from any location.**</span></span> <span data-ttu-id="1ae45-119">El módulo de administración de Lync Server 2010 incorporó el concepto de supervisión de disponibilidad de escenario de usuario final con transacciones sintéticas.</span><span class="sxs-lookup"><span data-stu-id="1ae45-119">The Lync Server 2010 Management Pack introduced the concept of monitoring end user scenario availability with synthetic transactions.</span></span> <span data-ttu-id="1ae45-120">En Lync Server 2013, estos agentes tienen más transacciones sintéticas y se pueden ejecutar desde una amplia variedad de ubicaciones dentro de la empresa, desde ubicaciones geográficas remotas fuera de la empresa, a los dispositivos de sucursales y a las implementaciones de Lync Server 2010 para agregar cobertura a las implementaciones perimetrales heredadas.</span><span class="sxs-lookup"><span data-stu-id="1ae45-120">In Lync Server 2013, these agents have more synthetic transactions and can be run from a variety of locations inside the enterprise, from remote geographic locations outside of the enterprise, against branch office appliances and against Lync Server 2010 deployments to add coverage to legacy Edge deployments.</span></span>

  - <span data-ttu-id="1ae45-121">**Registros de transacciones sintéticas.**</span><span class="sxs-lookup"><span data-stu-id="1ae45-121">**Synthetic transaction logs.**</span></span> <span data-ttu-id="1ae45-122">Cuando se producen errores en una transacción sintética, los administradores tienen acceso a los registros de HTML para determinar dónde se ha producido el error.</span><span class="sxs-lookup"><span data-stu-id="1ae45-122">When a synthetic transaction fails, administrators have access to HTML logs to help determine what failed.</span></span> <span data-ttu-id="1ae45-123">Esto incluye comprender qué acción ha generado errores, la latencia de cada acción, la línea de comandos que se ha usado para ejecutar la prueba y el error que se ha detectado.</span><span class="sxs-lookup"><span data-stu-id="1ae45-123">This includes understanding which action failed, the latency of each action, the command-line used to run the test, and the error that was encountered.</span></span>

  - <span data-ttu-id="1ae45-124">**Mayor cobertura de confiabilidad de llamadas.**</span><span class="sxs-lookup"><span data-stu-id="1ae45-124">**Increased call reliability coverage.**</span></span> <span data-ttu-id="1ae45-125">El módulo de administración de Lync Server 2010 ha creado alertas de confiabilidad de llamadas para detectar problemas de conectividad graves que afectan a las llamadas de audio de los usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="1ae45-125">The Lync Server 2010 Management Pack introduced call reliability alerting to detect severe connectivity issues that affect the audio calls of end users.</span></span> <span data-ttu-id="1ae45-126">Los paquetes de administración de Lync Server 2013 agregan cobertura para la mensajería instantánea de punto a punto (mi) y otras características de conferencia básicas para maximizar la cobertura mientras se reduce el ruido.</span><span class="sxs-lookup"><span data-stu-id="1ae45-126">The Lync Server 2013 Management Packs add coverage for peer-to-peer instant messaging (IM) and other basic conferencing features to maximize coverage while reducing noise.</span></span>

  - <span data-ttu-id="1ae45-127">**Supervisión de dependencia.**</span><span class="sxs-lookup"><span data-stu-id="1ae45-127">**Dependency monitoring.**</span></span> <span data-ttu-id="1ae45-128">Los escenarios de Lync Server pueden fallar debido a varios factores externos, como IIS sin conexión, recursos de memoria y CPU limitados, y problemas de disco.</span><span class="sxs-lookup"><span data-stu-id="1ae45-128">Lync Server scenarios can fail due to a variety of external factors such as IIS being offline, limited CPU and memory resources, and disk issues.</span></span> <span data-ttu-id="1ae45-129">Los nuevos módulos de administración comprueban varias dependencias fundamentales para que los administradores sean conscientes de su impacto.</span><span class="sxs-lookup"><span data-stu-id="1ae45-129">The new management packs check several critical dependencies to ensure administrators are aware of their impact.</span></span>

  - <span data-ttu-id="1ae45-130">**Generación de informes mejorada.**</span><span class="sxs-lookup"><span data-stu-id="1ae45-130">**Enhanced reporting.**</span></span> <span data-ttu-id="1ae45-131">Un conjunto de informes para ayudar a los administradores a calcular la disponibilidad de escenarios, planear la capacidad y averiguar qué componentes experimentan la mayoría de los problemas.</span><span class="sxs-lookup"><span data-stu-id="1ae45-131">A set of reports to help administrators estimate scenario availability, plan for capacity, and see which components are experiencing the most issues.</span></span>

<span data-ttu-id="1ae45-132">Los paquetes de administración también incluyen una variedad de características para ayudar a detectar y diagnosticar proporcionar visibilidad en tiempo real de la implementación de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1ae45-132">The Management Packs also include a variety of features to help detect and diagnose provide real-time visibility into the health your Lync Server deployment.</span></span> <span data-ttu-id="1ae45-133">Estas características se enumeran en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="1ae45-133">These features are listed in the following table.</span></span>

### <a name="management-pack-features"></a><span data-ttu-id="1ae45-134">Características del módulo de administración</span><span class="sxs-lookup"><span data-stu-id="1ae45-134">Management Pack Features</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1ae45-135">Característica</span><span class="sxs-lookup"><span data-stu-id="1ae45-135">Feature</span></span></th>
<th><span data-ttu-id="1ae45-136">Descripción</span><span class="sxs-lookup"><span data-stu-id="1ae45-136">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1ae45-137">Transacciones sintéticas</span><span class="sxs-lookup"><span data-stu-id="1ae45-137">Synthetic Transactions</span></span></p></td>
<td><p><span data-ttu-id="1ae45-138">Cmdlets de Windows PowerShell que se pueden ejecutar desde varias ubicaciones para garantizar que los usuarios finales, como el inicio de sesión, la presencia, la mensajería instantánea y la Conferencia, estén disponibles de forma fácil para los usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="1ae45-138">Windows PowerShell cmdlets that can be run from various locations to ensure that end user scenarios such as sign-in, presence, IM, and conferencing are readily available to end users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ae45-139">Alertas de confiabilidad de llamadas</span><span class="sxs-lookup"><span data-stu-id="1ae45-139">Call Reliability Alerts</span></span></p></td>
<td><p><span data-ttu-id="1ae45-140">Consultas de base de datos de los registros detallados de llamadas (CDR).</span><span class="sxs-lookup"><span data-stu-id="1ae45-140">Database queries for Call Detail Records (CDR).</span></span> <span data-ttu-id="1ae45-141">Estos registros los escriben los servidores front-end para reflejar si los usuarios finales podían conectarse a una llamada o por qué se terminó una llamada.</span><span class="sxs-lookup"><span data-stu-id="1ae45-141">These records are written by Front End Servers to reflect whether end users were able to connect to a call or why a call was terminated.</span></span> <span data-ttu-id="1ae45-142">Estas consultas producen alertas cuando un amplio rango de usuarios finales sufre problemas de conectividad con las llamadas punto a punto o con la funcionalidad de conferencia básica.</span><span class="sxs-lookup"><span data-stu-id="1ae45-142">These queries result in alerts that indicate when a wide range of end users are experiencing connectivity issues for peer-to-peer calls or basic conferencing functionality.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ae45-143">Alertas de calidad de medios</span><span class="sxs-lookup"><span data-stu-id="1ae45-143">Media Quality Alerts</span></span></p></td>
<td><p><span data-ttu-id="1ae45-p112">Consultas de base de datos que examinan los informes de calidad de la experiencia (QoE) que publican los clientes al finalizar cada llamada. Estas consultas producen alertas que resaltan los escenarios en los que los usuarios pueden experimentar una mala calidad de los medios durante las llamadas o conferencias. Los datos se crean a partir de métricas clave, como la pérdida y latencia de paquete, que se sabe que inciden directamente en la calidad de la llamada.</span><span class="sxs-lookup"><span data-stu-id="1ae45-p112">Database queries that look at Quality of Experience (QoE) reports published by clients at the end of each call. These queries result in alerts that pinpoint scenarios where users are likely to be experiencing poor media quality during calls and conferences. The data is built upon key metrics such as packet latency and loss, metrics that are known to directly contribute to call quality.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ae45-147">Estado de los componentes</span><span class="sxs-lookup"><span data-stu-id="1ae45-147">Component Health</span></span></p></td>
<td><p><span data-ttu-id="1ae45-p113">Los distintos componentes de servidor pueden producir alertas a través de los registros de eventos y los contadores de rendimiento. Estas alertas indican las condiciones de error que pueden incidir gravemente en uno o varios escenarios de usuario. Estas alertas también pueden indicar otras condiciones de error, como servicios que no se ejecutan, latencia de mensajes o porcentajes de errores elevados, o problemas de conectividad.</span><span class="sxs-lookup"><span data-stu-id="1ae45-p113">Individual server components raise alerts by using event logs and performance counters. These alerts indicate failure conditions that can severely impact one or more end user scenarios. These alerts can also indicate a variety of other failure conditions, including services not running, high failure rates, high message latency, or connectivity issues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ae45-151">Estado de dependencia</span><span class="sxs-lookup"><span data-stu-id="1ae45-151">Dependency Health</span></span></p></td>
<td><p><span data-ttu-id="1ae45-152">Los errores pueden producirse por diferentes motivos externos.</span><span class="sxs-lookup"><span data-stu-id="1ae45-152">Failures can occur for a variety of external reasons.</span></span> <span data-ttu-id="1ae45-153">Ahora, los módulos de administración pueden supervisar y recopilar datos de algunas dependencias externas importantes que podrían indicar problemas graves, como la disponibilidad de IIS, el uso de la memoria y la CPU de los servidores y los procesos, y métricas de disco.</span><span class="sxs-lookup"><span data-stu-id="1ae45-153">The management packs now monitor and collect data for some of the critical external dependencies that might indicate severe issues, including IIS availability, CPU and memory usage of servers and processes, and disk metrics.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="1ae45-154">Las alertas que emite el sistema se han clasificado en tres categorías generales:</span><span class="sxs-lookup"><span data-stu-id="1ae45-154">The alerts issued by the system have been classified into three general categories:</span></span>

  - <span data-ttu-id="1ae45-155">**Alertas de alta prioridad.**</span><span class="sxs-lookup"><span data-stu-id="1ae45-155">**High-priority Alerts.**</span></span> <span data-ttu-id="1ae45-156">Estas alertas indican condiciones que ocasionarán interrupciones en el servicio para grandes grupos de usuarios.</span><span class="sxs-lookup"><span data-stu-id="1ae45-156">These alerts indicate conditions that will cause service outages for large groups of users.</span></span> <span data-ttu-id="1ae45-157">Por ejemplo, un error de componente en un solo equipo no es una alerta de prioridad alta porque Lync Server 2013 tiene características integradas de alta disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="1ae45-157">For example, a component failure on a single machine is not a high-priority alert because Lync Server 2013 has built-in high availability features.</span></span> <span data-ttu-id="1ae45-158">Las alertas de alta prioridad indican problemas suficientemente graves "para que los administradores se levanten de noche".</span><span class="sxs-lookup"><span data-stu-id="1ae45-158">Instead, high-priority alerts represent problems serious enough “to wake up administrators at night.”</span></span> <span data-ttu-id="1ae45-159">Las interrupciones que detectan las transacciones sintéticas y los servicios sin conexión (por ejemplo, las conferencias de audio y vídeo) se consideran alertas de alta prioridad.</span><span class="sxs-lookup"><span data-stu-id="1ae45-159">Outages detected by synthetic transactions and offline services (for example, audio/video conferencing) qualify as high-priority alerts.</span></span>

  - <span data-ttu-id="1ae45-160">**Alertas de prioridad media.**.</span><span class="sxs-lookup"><span data-stu-id="1ae45-160">**Medium-priority alerts.**.</span></span> <span data-ttu-id="1ae45-161">Estas alertas indican condiciones que afectan a un subconjunto de usuarios o indican una disminución de la calidad de la llamada.</span><span class="sxs-lookup"><span data-stu-id="1ae45-161">These alerts indicate conditions that affect a subset of users or indicate call quality degradation.</span></span> <span data-ttu-id="1ae45-162">Esto incluye problemas como errores de componentes, latencia en el establecimiento de llamadas o una disminución de la calidad de audio en las llamadas.</span><span class="sxs-lookup"><span data-stu-id="1ae45-162">That includes problems such as component failures, latency in call establishment, or degraded audio quality in call.</span></span> <span data-ttu-id="1ae45-163">Las alertas de esta categoría son alertas con estado e indican el estado actual del problema.</span><span class="sxs-lookup"><span data-stu-id="1ae45-163">Alerts in this category are stateful and indicate the current status of the issue.</span></span> <span data-ttu-id="1ae45-164">Por ejemplo, supongamos que el tiempo de establecimiento de llamada supera el umbral de alerta.</span><span class="sxs-lookup"><span data-stu-id="1ae45-164">For example, suppose your call establishment times exceed the alert threshold.</span></span> <span data-ttu-id="1ae45-165">Si las horas de establecimiento de llamadas vuelven a su normalidad, estas alertas se resolverán automáticamente en System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="1ae45-165">If call establishment times return to normal, these alerts will be auto-resolved in System Center Operations Manager.</span></span> <span data-ttu-id="1ae45-166">Se espera que los administradores examinen estas alertas el mismo día laboral en que se producen.</span><span class="sxs-lookup"><span data-stu-id="1ae45-166">The expectation for these alerts is that an administrator will look at them on the same business day.</span></span>

  - <span data-ttu-id="1ae45-167">**Otras alertas.**</span><span class="sxs-lookup"><span data-stu-id="1ae45-167">**Other alerts.**</span></span> <span data-ttu-id="1ae45-168">Son alertas de componentes que podrían afectar a un usuario o a un subconjunto de usuarios determinado.</span><span class="sxs-lookup"><span data-stu-id="1ae45-168">These are alerts from components that might affect a specific user or subset of users.</span></span> <span data-ttu-id="1ae45-169">Por ejemplo, cuando el Servicio de libreta de direcciones no analiza la entrada de Active Directory de un usuario determinado.</span><span class="sxs-lookup"><span data-stu-id="1ae45-169">For example, perhaps the Address Book service could not parse the Active Directory entry of a given user.</span></span> <span data-ttu-id="1ae45-170">Se espera que los administradores se ocupen de estas alertas cuando tengan tiempo para ello.</span><span class="sxs-lookup"><span data-stu-id="1ae45-170">The expectation for these alerts is that administrators will get to them when they have time available.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="1ae45-171">En esta sección</span><span class="sxs-lookup"><span data-stu-id="1ae45-171">In This Section</span></span>

  - [<span data-ttu-id="1ae45-172">Configuración de Lync Server 2013 para trabajar con System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="1ae45-172">Configuring Lync Server 2013 to work with System Center Operations Manager</span></span>](lync-server-2013-configuring-lync-server-to-work-with-system-center-operations-manager.md)

  - [<span data-ttu-id="1ae45-173">Uso del registro enriquecido para transacciones sintéticas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ae45-173">Using rich logging for synthetic transactions in Lync Server 2013</span></span>](lync-server-2013-using-rich-logging-for-synthetic-transactions.md)

  - [<span data-ttu-id="1ae45-174">Uso de Microsoft SQL Server 2008 R2 como base de datos de System Center Operations Manager para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ae45-174">Using Microsoft SQL Server 2008 R2 as your System Center Operations Manager database for Lync Server 2013</span></span>](lync-server-2013-using-microsoft-sql-server-2008-r2-as-your-system-center-operations-manager-database.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

