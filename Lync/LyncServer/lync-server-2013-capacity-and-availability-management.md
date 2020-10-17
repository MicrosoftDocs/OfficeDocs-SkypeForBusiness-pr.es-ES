---
title: 'Lync Server 2013: administración de la capacidad y la disponibilidad'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity and availability management
ms:assetid: 207a2997-f482-4bee-892d-d2b112294481
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720325(v=OCS.15)
ms:contentKeyID: 63969586
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: efef66bcac833bb67c67dc453c25f3e0f6d51ba1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512857"
---
# <a name="capacity-and-availability-management-in-lync-server-2013"></a><span data-ttu-id="a91ff-102">Administración de la capacidad y la disponibilidad en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a91ff-102">Capacity and availability management in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a91ff-103">_**Última modificación del tema:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="a91ff-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="a91ff-104">El propósito de la administración de la capacidad y la administración de la disponibilidad es medir y controlar el rendimiento del sistema.</span><span class="sxs-lookup"><span data-stu-id="a91ff-104">The purpose of capacity management and availability management is to measure and control system performance.</span></span> <span data-ttu-id="a91ff-105">Le recomendamos que implemente procedimientos de administración de la capacidad y la disponibilidad para que pueda medir y controlar el rendimiento del sistema.</span><span class="sxs-lookup"><span data-stu-id="a91ff-105">We recommend that you implement capacity management and availability management procedures so that you can measure and control system performance.</span></span> <span data-ttu-id="a91ff-106">Tiene que saber si el sistema está disponible y si puede controlar las demandas actuales y previstas estableciendo líneas de base y supervisando el sistema para buscar tendencias.</span><span class="sxs-lookup"><span data-stu-id="a91ff-106">You have to know whether the system is available and if it can handle the current and the projected demands by setting baselines and monitoring the system to look for trends.</span></span>

<div>

## <a name="capacity-management"></a><span data-ttu-id="a91ff-107">Administración de la capacidad</span><span class="sxs-lookup"><span data-stu-id="a91ff-107">Capacity management</span></span>

<span data-ttu-id="a91ff-108">La administración de la capacidad implica la planeación, el ajuste de tamaño y el control de la capacidad del servicio para ayudar a garantizar que se superen los niveles de rendimiento mínimos especificados en el SLA.</span><span class="sxs-lookup"><span data-stu-id="a91ff-108">Capacity management involves planning, sizing, and controlling service capacity to help guarantee that the minimum performance levels specified in your SLA are exceeded.</span></span> <span data-ttu-id="a91ff-109">Una buena administración de la capacidad contribuye a garantizar que puede proporcionar servicios de ti a un coste razonable y seguir cumpliendo los niveles de rendimiento definidos en los SLAs con el cliente.</span><span class="sxs-lookup"><span data-stu-id="a91ff-109">Good capacity management helps ensure that you can provide IT services at a reasonable cost and still meet the levels of performance defined in your SLAs with the client.</span></span> <span data-ttu-id="a91ff-110">Estos criterios pueden incluir lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a91ff-110">These criteria can include the following:</span></span>

  - <span data-ttu-id="a91ff-111">Tiempo de respuesta **del sistema**     Se trata del tiempo medido que el sistema lleva a cabo acciones típicas.</span><span class="sxs-lookup"><span data-stu-id="a91ff-111">**System Response Time**   This is the measured time that the system takes to do typical actions.</span></span> <span data-ttu-id="a91ff-112">Algunos ejemplos son el tiempo necesario para que el rol de servidor de audio y vídeo procese el tráfico de audio y vídeo, el tiempo necesario para que un cliente cree y se una a una conferencia, o el tiempo que se tarda en actualizar la presencia en todos los clientes de monitor.</span><span class="sxs-lookup"><span data-stu-id="a91ff-112">Examples include the time that is required for the audio/video server role to process audio/video traffic, the time that is required for a client to create and join a conference, or the time taken for presence to be updated in all watcher clients.</span></span>

  - <span data-ttu-id="a91ff-113">**Capacidad**     de almacenamiento Esta es la capacidad de un sistema de almacenamiento, ya sea una base de datos de contenido, un dispositivo de copia de seguridad o una unidad local.</span><span class="sxs-lookup"><span data-stu-id="a91ff-113">**Storage Capacity**   This is the capacity of a storage system, whether it is a content database, a backup device, or a local drive.</span></span> <span data-ttu-id="a91ff-114">Algunos ejemplos son la cantidad máxima de espacio de almacenamiento que se debe proporcionar por sitio y el tiempo que se almacenan las copias de seguridad antes de que se sobrescriban.</span><span class="sxs-lookup"><span data-stu-id="a91ff-114">Examples include the maximum amount of storage space to be provided per site and the time that backups should be stored before they are overwritten.</span></span>

<span data-ttu-id="a91ff-115">El ajuste de la capacidad suele ser un caso para asegurarse de que haya suficientes recursos físicos disponibles, como espacio en disco y ancho de banda de la red.</span><span class="sxs-lookup"><span data-stu-id="a91ff-115">Adjusting capacity is frequently a case of making sure that enough physical resources are available, such as disk space and network bandwidth.</span></span> <span data-ttu-id="a91ff-116">En la siguiente tabla se enumeran las soluciones típicas para problemas relacionados con la capacidad.</span><span class="sxs-lookup"><span data-stu-id="a91ff-116">The following table lists typical resolutions for capacity-related issues.</span></span>

### <a name="typical-resolutions-for-capacity-related-issues"></a><span data-ttu-id="a91ff-117">Soluciones típicas para problemas relacionados con la capacidad</span><span class="sxs-lookup"><span data-stu-id="a91ff-117">Typical resolutions for capacity-related issues</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a91ff-118">Problema</span><span class="sxs-lookup"><span data-stu-id="a91ff-118">Issue</span></span></th>
<th><span data-ttu-id="a91ff-119">Posible resolución</span><span class="sxs-lookup"><span data-stu-id="a91ff-119">Possible resolution</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a91ff-120">Usuarios remotos con un rendimiento deficiente de audio y vídeo</span><span class="sxs-lookup"><span data-stu-id="a91ff-120">Remote users having poor audio/video performance</span></span></p></td>
<td><p><span data-ttu-id="a91ff-121">Compruebe si el ancho de banda adecuado está disponible en los vínculos WAN y si QoS está habilitado y configurado correctamente.</span><span class="sxs-lookup"><span data-stu-id="a91ff-121">Check to see whether appropriate bandwidth is available on the WAN links and if QoS is enabled and appropriately configured.</span></span> <span data-ttu-id="a91ff-122">Compruebe los datos de QoE.</span><span class="sxs-lookup"><span data-stu-id="a91ff-122">Check QoE data.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a91ff-123">La respuesta general del entorno de Lync es lenta.</span><span class="sxs-lookup"><span data-stu-id="a91ff-123">Overall response of the Lync environment is slow.</span></span></p></td>
<td><p><span data-ttu-id="a91ff-124">Ejecute las pruebas para comprobar que los servidores front-end existentes pueden tratar la carga.</span><span class="sxs-lookup"><span data-stu-id="a91ff-124">Run tests to check that the existing front-end servers can deal with the load.</span></span> <span data-ttu-id="a91ff-125">Introduzca un nuevo servidor front-end si es necesario. Compruebe los tiempos de respuesta de la base de datos SQL y corrija las causas de los retrasos (por ejemplo, mejorar e/s de disco).</span><span class="sxs-lookup"><span data-stu-id="a91ff-125">Introduce a new front-end server if it is needed.Check SQL database response times and fix the causes for the delays (for example, improve disk I/O).</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a91ff-126">La solución de problemas con más detalle se describe en la guía de redes de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a91ff-126">Troubleshooting in greater detail is covered in the Lync Server Networking Guide.</span></span>

<span data-ttu-id="a91ff-127">La capacidad se ve afectada por la configuración del sistema y depende de los recursos físicos, como el ancho de banda de la red.</span><span class="sxs-lookup"><span data-stu-id="a91ff-127">Capacity is affected by system configuration and depends on physical resources such as network bandwidth.</span></span> <span data-ttu-id="a91ff-128">Por ejemplo, si un entorno de Lync está configurado para realizar una copia de seguridad completa por la noche, debe tener cuidado para garantizar que se minimice el efecto en el rendimiento interactivo que experimentan los usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="a91ff-128">For example, if a Lync environment is configured to perform a full backup nightly, care must be taken to help guarantee that the effect on the interactive performance experienced by end-users is minimized.</span></span>

<span data-ttu-id="a91ff-129">La administración de la capacidad es el proceso de mantener la capacidad de un sistema dentro de los niveles aceptables y resuelve los problemas siguientes:</span><span class="sxs-lookup"><span data-stu-id="a91ff-129">Capacity management is the process of keeping the capacity of a system within acceptable levels and addresses the following issues:</span></span>

  - <span data-ttu-id="a91ff-130">**Reaccionar ante los cambios en los requisitos**     Los requisitos de capacidad deben ajustarse para tener en cuenta los cambios en el sistema o la organización.</span><span class="sxs-lookup"><span data-stu-id="a91ff-130">**Reacting to changes in requirements**   Capacity requirements have to be adjusted to account for changes in the system or the organization.</span></span> <span data-ttu-id="a91ff-131">Por ejemplo, si su entorno decide implementar la telefonía IP empresarial, la cantidad y la ubicación de los servidores de mediación y las puertas de enlace de la red telefónica conmutada (RTC) serán muy importantes.</span><span class="sxs-lookup"><span data-stu-id="a91ff-131">For example, if your environment decides to implement Enterprise Voice, the number and placement of Mediation Servers and public switched telephone network (PSTN) gateways will be very important.</span></span> <span data-ttu-id="a91ff-132">Si va a realizar un enlace troncal del Protocolo de inicio de sesión (SIP) o un SIP directo, el diseño general se cambiará significativamente para proporcionar el mejor rendimiento de la telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="a91ff-132">If you'll be doing Session Initiation Protocol (SIP) trunking or direct SIP, the overall design will be significantly changed to provide the best Enterprise Voice performance.</span></span>

  - <span data-ttu-id="a91ff-133">**Predecir los requisitos futuros**     Algunos requisitos de capacidad cambian de forma predecible a lo largo del tiempo.</span><span class="sxs-lookup"><span data-stu-id="a91ff-133">**Predicting future requirements**   Some capacity requirements change predictably over time.</span></span> <span data-ttu-id="a91ff-134">Al realizar un seguimiento de las tendencias, puede planear actualizaciones por adelantado.</span><span class="sxs-lookup"><span data-stu-id="a91ff-134">By tracking trends you can plan upgrades in advance.</span></span> <span data-ttu-id="a91ff-135">Por ejemplo, el ancho de banda disponible entre varios sitios de Lync debe supervisarse para crear una línea base.</span><span class="sxs-lookup"><span data-stu-id="a91ff-135">For example, available bandwidth between various Lync sites must be monitored to create a baseline.</span></span> <span data-ttu-id="a91ff-136">Esta línea base le permitirá predecir cuándo tiene que agregar más ancho de banda a estos vínculos, ya que el recuento de usuarios en estos sitios remotos aumenta con el tiempo.</span><span class="sxs-lookup"><span data-stu-id="a91ff-136">This baseline will allow you to predict when you have to add more bandwidth to these links as user count in these remote sites increases with time.</span></span>

</div>

<div>

## <a name="availability-management"></a><span data-ttu-id="a91ff-137">Administración de la disponibilidad</span><span class="sxs-lookup"><span data-stu-id="a91ff-137">Availability management</span></span>

<span data-ttu-id="a91ff-138">La administración de la disponibilidad es el proceso de garantizar que cualquier servicio de ti ofrezca de forma coherente y rentable el nivel de servicio coherente y fiable que requiera el cliente.</span><span class="sxs-lookup"><span data-stu-id="a91ff-138">Availability management is the process of making sure that any IT service consistently and cost effectively delivers the level of consistent, reliable service that is required by the customer.</span></span> <span data-ttu-id="a91ff-139">La administración de la disponibilidad se ocupa de minimizar la pérdida de servicio y asegurarse de que se realiza la acción apropiada si se pierde el servicio.</span><span class="sxs-lookup"><span data-stu-id="a91ff-139">Availability management deals with minimizing loss of service and with making sure that appropriate action is taken if service is lost.</span></span> <span data-ttu-id="a91ff-140">En un entorno de Lync, puede que le preocupe saber si el servicio de telefonía IP empresarial está disponible, si los usuarios pueden unirse a conferencias programadas, etc.</span><span class="sxs-lookup"><span data-stu-id="a91ff-140">In a Lync environment, you may be concerned about whether the Enterprise Voice service is available, whether users can join scheduled conferences, and so on.</span></span> <span data-ttu-id="a91ff-141">Un SLA define una frecuencia aceptable y la duración de las interrupciones, y permite períodos determinados cuando el sistema no está disponible para el mantenimiento planeado.</span><span class="sxs-lookup"><span data-stu-id="a91ff-141">An SLA defines an acceptable frequency and length of outages and allows for certain periods when the system is unavailable for planned maintenance.</span></span>

<span data-ttu-id="a91ff-142">Si tiene que proporcionar informes a su administración sobre la disponibilidad de los sistemas o si tiene alguna penalización financiera u otras penalizaciones asociadas con los objetivos de disponibilidad que faltan, debe registrar los datos de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="a91ff-142">If you have to provide reports to your management about the availability of systems, or if you have financial or other penalties associated with missing availability targets, you must record availability data.</span></span> <span data-ttu-id="a91ff-143">Incluso si no tiene dichos requisitos formales, es una buena idea saber con qué frecuencia se produce un error en un sistema durante un período de tiempo determinado.</span><span class="sxs-lookup"><span data-stu-id="a91ff-143">Even if you do not have such formal requirements, it is a good idea to at least know how frequently a system has failed in a certain time period.</span></span> <span data-ttu-id="a91ff-144">Por ejemplo, la disponibilidad del sistema en los últimos 12 meses y el tiempo que tardó en recuperarse de cada error.</span><span class="sxs-lookup"><span data-stu-id="a91ff-144">For example, system availability in the last 12 months and how long it took to recover from each failure.</span></span> <span data-ttu-id="a91ff-145">Esta información le ayudará a medir y mejorar la efectividad del equipo para responder a un error del sistema.</span><span class="sxs-lookup"><span data-stu-id="a91ff-145">This information will help you measure and improve your team’s effectiveness in responding to a system failure.</span></span> <span data-ttu-id="a91ff-146">También puede darle información útil si hay una disputa.</span><span class="sxs-lookup"><span data-stu-id="a91ff-146">It can also give you useful information if there is a dispute.</span></span>

<span data-ttu-id="a91ff-147">Las medidas relacionadas con la disponibilidad son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="a91ff-147">Measures related to availability are as follows:</span></span>

  - <span data-ttu-id="a91ff-148">**Disponibilidad**     Normalmente, esto se expresa como la hora a la que se puede tener acceso a un sistema o servicio en comparación con el momento en que está inactivo.</span><span class="sxs-lookup"><span data-stu-id="a91ff-148">**Availability**   This is typically expressed as the time that a system or service can be accessed compared to the time that it is down.</span></span> <span data-ttu-id="a91ff-149">Normalmente se expresa como un porcentaje.</span><span class="sxs-lookup"><span data-stu-id="a91ff-149">It is typically expressed as a percentage.</span></span> <span data-ttu-id="a91ff-150">(Es posible que vea referencias a "tres nueves" o "cinco nueves".</span><span class="sxs-lookup"><span data-stu-id="a91ff-150">(You may see references to “three nines” or “five nines”.</span></span> <span data-ttu-id="a91ff-151">Estos hacen referencia a la disponibilidad de 99,9 por ciento o el 99,999 por ciento.)</span><span class="sxs-lookup"><span data-stu-id="a91ff-151">These refer to 99.9 percent or 99.999 percent availability.)</span></span>

  - <span data-ttu-id="a91ff-152">**Confiabilidad**     Se trata de una medida del tiempo entre errores de un sistema y a veces se expresa como media (o media) tiempo entre errores (MTBF).</span><span class="sxs-lookup"><span data-stu-id="a91ff-152">**Reliability**   This is a measure of the time between failures of a system and is sometimes expressed as mean (or average) time between failures (MTBF).</span></span>

  - <span data-ttu-id="a91ff-153">**Tiempo de reparación**     Este es el tiempo que se tarda en recuperar un servicio después de que se haya producido un error y que a menudo se expresa como media (que significa promedio) de tiempo de reparación (MTTR).</span><span class="sxs-lookup"><span data-stu-id="a91ff-153">**Time to Repair**   This is the time taken to recover a service after a failure has occurred and is often expressed as mean (meaning average) time to repair (MTTR).</span></span>

<span data-ttu-id="a91ff-154">La disponibilidad, la confiabilidad y el tiempo de reparación se relacionan de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="a91ff-154">Availability, reliability, and time to repair are related as follows:</span></span>

<span data-ttu-id="a91ff-155">**Disponibilidad = (MTBF – MTTR)/MTBF**     Por ejemplo, si se produce un error en un servidor dos veces durante un período de seis meses y no está disponible durante un promedio de 20 minutos, la MTBF es de tres meses o 90 días y el MTTR es de 20 minutos.</span><span class="sxs-lookup"><span data-stu-id="a91ff-155">**Availability = (MTBF – MTTR) / MTBF**   For example, if a server fails two times over a six-month period and is unavailable for an average of 20 minutes, the MTBF is three months or 90 days and the MTTR is 20 minutes.</span></span> <span data-ttu-id="a91ff-156">Por lo tanto, Availability = (90 días – 20 minutos)/90 días = 99,985 por ciento.</span><span class="sxs-lookup"><span data-stu-id="a91ff-156">Therefore, Availability = (90 days – 20 minutes) / 90 days = 99.985 percent.</span></span>

<span data-ttu-id="a91ff-157">La administración de la disponibilidad es el proceso de garantizar que la disponibilidad se maximice y se mantenga dentro de los parámetros definidos en los SLA.</span><span class="sxs-lookup"><span data-stu-id="a91ff-157">Availability management is the process of making sure that availability is maximized and kept within the parameters that are defined in SLAs.</span></span> <span data-ttu-id="a91ff-158">La administración de la disponibilidad incluye los siguientes procesos:</span><span class="sxs-lookup"><span data-stu-id="a91ff-158">Availability management includes the following processes:</span></span>

  - <span data-ttu-id="a91ff-159">**Supervisión**     Examinar Cuándo y durante cuánto tiempo los servicios no están disponibles.</span><span class="sxs-lookup"><span data-stu-id="a91ff-159">**Monitoring**    Examining when and for how long services are unavailable.</span></span>

  - <span data-ttu-id="a91ff-160">**Informes**     Las cifras de disponibilidad deben proporcionarse con regularidad a los equipos de administración, usuarios y operaciones.</span><span class="sxs-lookup"><span data-stu-id="a91ff-160">**Reporting**   Availability figures should be regularly provided to management, users, and operations teams.</span></span> <span data-ttu-id="a91ff-161">Estos informes deben resaltar tendencias e identificar las áreas que están haciendo bien y las que requieren atención.</span><span class="sxs-lookup"><span data-stu-id="a91ff-161">These reports should highlight trends and identify areas that are doing well and areas that require attention.</span></span> <span data-ttu-id="a91ff-162">El informe debe resumir el cumplimiento de los objetivos establecidos en los SLA.</span><span class="sxs-lookup"><span data-stu-id="a91ff-162">The report should summarize compliance with targets set in the SLAs.</span></span>

  - <span data-ttu-id="a91ff-163">**Mejora**     Si la disponibilidad no cumple con los objetivos definidos en los SLAs o donde la tendencia es a reducir la disponibilidad, el proceso de administración de la disponibilidad debe planear los pasos necesarios para los remedios.</span><span class="sxs-lookup"><span data-stu-id="a91ff-163">**Improvement**   If availability does not meet targets that are defined in the SLAs or where the trend is toward reduced availability, the availability management process should plan remedial steps.</span></span> <span data-ttu-id="a91ff-164">Esto debe incluir trabajar con otros equipos responsables para resaltar los motivos de las interrupciones y planear las acciones correctivas para evitar una reaparición de las interrupciones.</span><span class="sxs-lookup"><span data-stu-id="a91ff-164">This should include working with other responsible teams to highlight reasons for outages and to plan remedial actions to prevent a recurrence of the outages.</span></span>

<span data-ttu-id="a91ff-165">Las medidas de capacidad y disponibilidad son tareas repetitivas que resultan adecuadas para las herramientas automatizadas y scripts como Microsoft System Center Operations Manager (anteriormente Microsoft Operations Manager), que se describen más adelante en este documento.</span><span class="sxs-lookup"><span data-stu-id="a91ff-165">Capacity and availability measurements are repetitive tasks that are ideally suited to automated tools and scripts such as Microsoft System Center Operations Manager (formerly Microsoft Operations Manager), which is discussed later in this document.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a91ff-166">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a91ff-166">See Also</span></span>


[<span data-ttu-id="a91ff-167">Supervisión de Lync Server 2013 con System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="a91ff-167">Monitoring Lync Server 2013 with System Center Operations Manager</span></span>](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

