---
title: Calculadora de planeación de capacidad 2013 de Lync Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using the Lync Server 2013 capacity planning calculator
ms:assetid: e86c1f05-1393-408a-9549-6001572ec50d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362852(v=OCS.15)
ms:contentKeyID: 56280894
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 385127f1686c2a4fa5beaf33f02d2eec6ba19500
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842689"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-capacity-planning-calculator-for-lync-server-2013"></a><span data-ttu-id="91c0f-102">Usar la calculadora de planeación de capacidad para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91c0f-102">Using the capacity planning calculator for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="91c0f-103">_**Última modificación del tema:** 2013-11-21_</span><span class="sxs-lookup"><span data-stu-id="91c0f-103">_**Topic Last Modified:** 2013-11-21_</span></span>

<span data-ttu-id="91c0f-104">La calculadora de planeación de capacidad de Microsoft® Lync™ Server 2013 está <http://www.microsoft.com/en-us/download/details.aspx?id=36828>disponible para su descarga en.</span><span class="sxs-lookup"><span data-stu-id="91c0f-104">The Microsoft® Lync™ Server 2013 capacity planning calculator is available for download at <http://www.microsoft.com/en-us/download/details.aspx?id=36828>.</span></span> <span data-ttu-id="91c0f-105">Está diseñado para ayudarle a determinar los requisitos del servidor en función de los números de usuarios y las modalidades de comunicación que están habilitadas en su organización.</span><span class="sxs-lookup"><span data-stu-id="91c0f-105">It is designed to assist you in determining server requirements based on numbers of users and communication modalities that are enabled at your organization.</span></span> <span data-ttu-id="91c0f-106">Escriba el perfil de su organización y la calculadora le ofrece recomendaciones que le ayudarán a planear su topología.</span><span class="sxs-lookup"><span data-stu-id="91c0f-106">You enter your organization’s profile, and the calculator provides recommendations that help you plan your topology.</span></span>

<span data-ttu-id="91c0f-107">Las recomendaciones creadas por la calculadora son solo para fines de planificación.</span><span class="sxs-lookup"><span data-stu-id="91c0f-107">The recommendations created by the calculator are for planning purposes only.</span></span> <span data-ttu-id="91c0f-108">La simulación de carga real es necesaria para garantizar que Lync Server 2013 se haya aprovisionado correctamente.</span><span class="sxs-lookup"><span data-stu-id="91c0f-108">Actual load simulation is required to ensure that Lync Server 2013 is adequately provisioned.</span></span> <span data-ttu-id="91c0f-109">Para realizar pruebas de estrés bajo una carga simulada, use la [herramienta Lync Server 2013 de estrés y rendimiento](http://go.microsoft.com/fwlink/?linkid=282724).</span><span class="sxs-lookup"><span data-stu-id="91c0f-109">To perform stress testing under a simulated load, use the [Lync Server 2013 Stress and Performance Tool](http://go.microsoft.com/fwlink/?linkid=282724).</span></span>

<span data-ttu-id="91c0f-110">Una vez que haya determinado el perfil de usuario y las modalidades que quiere habilitar para los usuarios, es el momento de usar la calculadora para planear el número de servidores, la memoria y el ancho de banda que necesita.</span><span class="sxs-lookup"><span data-stu-id="91c0f-110">After you have determined your user profile and the modalities that you want to enable for your users, it is time to use the calculator to plan the number of servers, memory, and bandwidth that you need.</span></span> <span data-ttu-id="91c0f-111">Esta versión de la calculadora no ofrece instrucciones sobre los requisitos de I/O de disco.</span><span class="sxs-lookup"><span data-stu-id="91c0f-111">This version of the calculator does not provide guidance for disk I/O requirements.</span></span>

<span data-ttu-id="91c0f-112">Esta calculadora complementa [Microsoft Lync Server](http://go.microsoft.com/fwlink/?linkid=282725) y [Microsoft Lync Server](lync-server-2013-planning.md).</span><span class="sxs-lookup"><span data-stu-id="91c0f-112">This calculator complements the [Microsoft Lync Server](http://go.microsoft.com/fwlink/?linkid=282725) and [Microsoft Lync Server](lync-server-2013-planning.md).</span></span> <span data-ttu-id="91c0f-113">Use la calculadora después de que haya revisado la guía y haya creado una topología recomendada mediante el uso de la Herramienta de planeación.</span><span class="sxs-lookup"><span data-stu-id="91c0f-113">Use the calculator after you have reviewed the guide and created a recommended topology by using the Planning Tool.</span></span>

<span data-ttu-id="91c0f-p105">Para sacar el máximo partido de la calculadora necesitará información precisa y detallada sobre el perfil de usuario específico. Por ejemplo, datos como el porcentaje de usuarios habilitados para voz, la media de llamadas por usuario por hora, la duración de las llamadas y el porcentaje de usuarios simultáneos en las conferencias pueden suponer una gran diferencia en cuanto a requisitos de servidor. La precisión de las recomendaciones de la calculadora dependerá de la precisión de la información que se le suministre.</span><span class="sxs-lookup"><span data-stu-id="91c0f-p105">You can benefit most from the calculator if you have accurate, detailed information about your specific user profile. For example, the percentage of voice-enabled users, average calls per user per hour, call duration, and the percentage of concurrent users in conferences can make a huge difference in server requirements. The accuracy of the recommendations created by the calculator depends on the accuracy of the information that you provide.</span></span>

<div>

## <a name="using-the-capacity-calculator"></a><span data-ttu-id="91c0f-117">Uso de la calculadora de capacidad</span><span class="sxs-lookup"><span data-stu-id="91c0f-117">Using the Capacity Calculator</span></span>

<span data-ttu-id="91c0f-118">La calculadora es una hoja de cálculo de Microsoft Excel®.</span><span class="sxs-lookup"><span data-stu-id="91c0f-118">The calculator is a Microsoft Excel® spreadsheet.</span></span> <span data-ttu-id="91c0f-119">Las celdas de color naranja son para el usuario.</span><span class="sxs-lookup"><span data-stu-id="91c0f-119">Orange-colored cells are for input from you.</span></span> <span data-ttu-id="91c0f-120">Se escriben valores predeterminados (80.000 usuarios en un grupo con doce servidores frontales), pero puede cambiar estos valores según las necesidades de la organización.</span><span class="sxs-lookup"><span data-stu-id="91c0f-120">Default values are entered (80,000 users in one pool with twelve Front End Servers), but you can change these values according to your organization’s needs.</span></span>

<span data-ttu-id="91c0f-121">El modelo de uso contiene las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="91c0f-121">The usage model contains the following sections.</span></span> <span data-ttu-id="91c0f-122">Para calcular los requisitos de capacidad, escriba los datos según se describe:</span><span class="sxs-lookup"><span data-stu-id="91c0f-122">To calculate your capacity requirements, enter data as described:</span></span>

<span data-ttu-id="91c0f-123">**Mensajería instantánea y presencia**</span><span class="sxs-lookup"><span data-stu-id="91c0f-123">**Instant Messaging and Presence**</span></span>

  - <span data-ttu-id="91c0f-124">En número de usuarios, escriba el número de usuarios que van a iniciar sesión de forma simultánea.</span><span class="sxs-lookup"><span data-stu-id="91c0f-124">Under Number of Users, type the number of users who will be concurrently signed in.</span></span> <span data-ttu-id="91c0f-125">Por lo general, este número asciende al 80 % del número total de usuarios especificado.</span><span class="sxs-lookup"><span data-stu-id="91c0f-125">This number is typically 80% of the total number of provisioned users.</span></span> <span data-ttu-id="91c0f-126">En muchas ocasiones, el 100 % de los usuarios simultáneos estarán habilitados para mensajería instantánea y presencia.</span><span class="sxs-lookup"><span data-stu-id="91c0f-126">In most situations, 100% of your concurrent users will be enabled for IM and Presence.</span></span> <span data-ttu-id="91c0f-127">El valor predeterminado es 80 000.</span><span class="sxs-lookup"><span data-stu-id="91c0f-127">The default is 80,000.</span></span>

  - <span data-ttu-id="91c0f-128">El número medio de contactos de la Lista de contactos es el número de contactos que deberá usar para validar los requisitos del sistema.</span><span class="sxs-lookup"><span data-stu-id="91c0f-128">Average number of contacts in Contact list indicates the number of contacts that we are using to validate your system requirements.</span></span> <span data-ttu-id="91c0f-129">Este número no es modificable.</span><span class="sxs-lookup"><span data-stu-id="91c0f-129">This number is not changeable.</span></span>

<span data-ttu-id="91c0f-130">**Telefonía IP empresarial**</span><span class="sxs-lookup"><span data-stu-id="91c0f-130">**Enterprise Voice**</span></span>

  - <span data-ttu-id="91c0f-131">En usuarios habilitados para telefonía IP empresarial, escriba el porcentaje de usuarios que están habilitados para telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="91c0f-131">In Users enabled for Enterprise Voice, type the percentage of your users who are enabled for Enterprise Voice.</span></span> <span data-ttu-id="91c0f-132">El valor predeterminado es el 60 %.</span><span class="sxs-lookup"><span data-stu-id="91c0f-132">The default is 60%.</span></span>

  - <span data-ttu-id="91c0f-133">En número promedio de llamadas por usuario por hora (máximo), escriba el número de llamadas por hora que espera que el usuario promedio participe en los períodos de carga máxima.</span><span class="sxs-lookup"><span data-stu-id="91c0f-133">In Average number of calls per user per hour (peak), type the number of calls per hour that you expect the average user to participate in during times of peak load.</span></span> <span data-ttu-id="91c0f-134">El valor predeterminado es 4.</span><span class="sxs-lookup"><span data-stu-id="91c0f-134">The default is 4.</span></span>

  - <span data-ttu-id="91c0f-135">En Porcentaje de llamadas que usan el desvío de medios, escriba el porcentaje de llamadas realizadas por sus usuarios que desviarán el Servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="91c0f-135">In Percentage of calls that use media bypass, type the percentage of calls placed by your users that will bypass the Mediation Server.</span></span> <span data-ttu-id="91c0f-136">El valor predeterminado es 65%.</span><span class="sxs-lookup"><span data-stu-id="91c0f-136">The default is 65%.</span></span>

  - <span data-ttu-id="91c0f-137">En Porcentaje de usuarios de voz en llamadas de UC a RTC, escriba el porcentaje de llamadas de la organización que son llamadas telefónicas de UC a RTC.</span><span class="sxs-lookup"><span data-stu-id="91c0f-137">In Percentage of voice users involved in UC-PSTN calls, type the percentage of your organization’s calls which are UC-PSTN phone calls.</span></span> <span data-ttu-id="91c0f-138">El valor predeterminado es 60%.</span><span class="sxs-lookup"><span data-stu-id="91c0f-138">The default is 60%</span></span>

  - <span data-ttu-id="91c0f-139">En porcentaje de usuarios de voz implicados en las comunicaciones UC-UC se muestra el porcentaje de usuarios que están habilitados para telefonía IP empresarial que solo se habilitará para llamadas UC-UC.</span><span class="sxs-lookup"><span data-stu-id="91c0f-139">In Percentage of voice users involved in UC-UC calls shows the percentage of users who are enabled for Enterprise Voice who will be enabled only for UC-UC calls.</span></span> <span data-ttu-id="91c0f-140">Este número se calcula en función del dato que se ha especificado en Porcentaje de usuarios de voz en llamadas de UC a RTC.</span><span class="sxs-lookup"><span data-stu-id="91c0f-140">This number is calculated based on what you input for Percentage of voice users enabled for UC-PSTN calls.</span></span>

<span data-ttu-id="91c0f-141">**Conferencia**</span><span class="sxs-lookup"><span data-stu-id="91c0f-141">**Conferencing**</span></span>

  - <span data-ttu-id="91c0f-142">En porcentaje de usuarios en conferencias simultáneas, escriba el porcentaje de usuarios que participarán de forma simultánea en las conferencias.</span><span class="sxs-lookup"><span data-stu-id="91c0f-142">In Percentage of users in concurrent conferences, type the percentage of users who will be concurrently participating in conferences.</span></span> <span data-ttu-id="91c0f-143">El valor predeterminado es el 5 %.</span><span class="sxs-lookup"><span data-stu-id="91c0f-143">The default is 5%.</span></span>

  - <span data-ttu-id="91c0f-144">En un porcentaje de conferencias con sólo mensajería instantánea (sin voz), escriba el porcentaje de conferencias cuyas conferencias implicarán únicamente mensajería instantánea; es decir, que no incluyen un componente de audio.</span><span class="sxs-lookup"><span data-stu-id="91c0f-144">In Percentage of conferences with group IM only (no voice), type the percentage of conferences whose conferences will involve instant messaging only; that is, that do not include an audio component.</span></span> <span data-ttu-id="91c0f-145">El valor predeterminado es el 10 %.</span><span class="sxs-lookup"><span data-stu-id="91c0f-145">The default is 10%</span></span>

  - <span data-ttu-id="91c0f-146">En porcentaje de usuarios con conferencias de acceso telefónico local, escriba el porcentaje de participantes simultáneos en conferencias que usarán conferencias de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="91c0f-146">In Percentage of users using dial-in conferencing, type the percentage of concurrent participants in conferences who will be using dial-in conferencing.</span></span> <span data-ttu-id="91c0f-147">El valor predeterminado es el 15 %.</span><span class="sxs-lookup"><span data-stu-id="91c0f-147">The default is 15%.</span></span>

  - <span data-ttu-id="91c0f-148">En porcentaje de conferencias con voz, escriba el porcentaje de conferencias que incluirán un componente de audio.</span><span class="sxs-lookup"><span data-stu-id="91c0f-148">In Percentage of conferences using voice, type the percentage of conferences that will include an audio component.</span></span>
    
      - <span data-ttu-id="91c0f-149">Si el 20 % de las conferencias de voz incluirán también vídeos comunes, active la casilla Incluye vídeo (sin vista múltiple).</span><span class="sxs-lookup"><span data-stu-id="91c0f-149">If 20% of your voice conferences will also include regular video, select the Including video (no Multi View) check box.</span></span>
    
      - <span data-ttu-id="91c0f-150">Si el 20 % de las conferencias incluirán también vídeos en vista múltiple, active la casilla Incluye vista múltiple.</span><span class="sxs-lookup"><span data-stu-id="91c0f-150">If 20% of your conferences will also include Multi-View video, select the Including Multi View check box.</span></span>
    
      - <span data-ttu-id="91c0f-151">Si el 50 % de las conferencias de voz incluirán también el uso compartido de aplicaciones, active la casilla Incluye uso compartido de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="91c0f-151">If 50% of your voice conferences will also include application sharing, select the Including application sharing check box.</span></span>
    
      - <span data-ttu-id="91c0f-152">Si el 20% de las conferencias de voz incluye cargas de datos, como presentaciones de Microsoft PowerPoint®, active la casilla de verificación Incluir conferencias web.</span><span class="sxs-lookup"><span data-stu-id="91c0f-152">If 20% of your voice conferences include data uploads, such as Microsoft PowerPoint® presentations, select the Including web conferencing check box.</span></span>

<span data-ttu-id="91c0f-153">**Movilidad**</span><span class="sxs-lookup"><span data-stu-id="91c0f-153">**Mobility**</span></span>

  - <span data-ttu-id="91c0f-154">En porcentaje de usuarios habilitados para movilidad, escriba el porcentaje de usuarios que se habilitarán para conectarse a Lync Server mediante dispositivos móviles.</span><span class="sxs-lookup"><span data-stu-id="91c0f-154">In Percentage of users enabled for Mobility, type the percentage of your users who will be enabled to connect to Lync Server using mobile devices.</span></span> <span data-ttu-id="91c0f-155">El valor predeterminado es el 40 %.</span><span class="sxs-lookup"><span data-stu-id="91c0f-155">The default is 40%.</span></span>

<span data-ttu-id="91c0f-156">Cuando se especifique toda la información necesaria, la calculadora de capacidad calculará los requisitos.</span><span class="sxs-lookup"><span data-stu-id="91c0f-156">When you have entered all the necessary information, the capacity calculator estimates your requirements.</span></span> <span data-ttu-id="91c0f-157">Las celdas amarillas muestran valores calculados para los requisitos de CPU, memoria y ancho de banda según las pruebas realizadas en los laboratorios de rendimiento de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="91c0f-157">The yellow cells show calculated values for CPU, memory, and bandwidth requirements based on tests performed in Lync Server 2013 performance labs.</span></span> <span data-ttu-id="91c0f-158">Las cifras se ofrecen a título orientativo (no se han comprobado y validado todas las variaciones individuales posibles).</span><span class="sxs-lookup"><span data-stu-id="91c0f-158">The numbers are provided as a guideline, not every single variation is tested and validated.</span></span> <span data-ttu-id="91c0f-159">Se han calculado los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="91c0f-159">The following values are calculated:</span></span>

  - <span data-ttu-id="91c0f-160">CPU front-end: porcentaje de uso de CPU si un servidor front-end estaba manejando toda la carga con las mismas especificaciones que el servidor que se usó en las pruebas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="91c0f-160">Front End CPU: Percentage of CPU usage if the entire load were being handled by one Front End Server of the same specifications as the server that was used in Microsoft testing.</span></span>

  - <span data-ttu-id="91c0f-161">Red en Mbps: requisitos de ancho de banda en megabits por segundo (Mbps) para la carga de trabajo correspondiente.</span><span class="sxs-lookup"><span data-stu-id="91c0f-161">Network in Mbps: Bandwidth requirements in megabits per second (Mbps) for the corresponding workload.</span></span>

  - <span data-ttu-id="91c0f-162">Memoria en GB: memoria necesaria en gigabytes (GB) para la carga de trabajo correspondiente.</span><span class="sxs-lookup"><span data-stu-id="91c0f-162">Memory in GB: Memory required in gigabytes (GB) for the corresponding workload.</span></span>

<span data-ttu-id="91c0f-163">Las celdas verdes contienen recomendaciones para el modelo de uso que se ha especificado.</span><span class="sxs-lookup"><span data-stu-id="91c0f-163">The green cells show recommendations for the usage model that you entered.</span></span>

  - <span data-ttu-id="91c0f-164">Total de servidores front-end: el número de servidores físicos necesarios se basa en servidores dedicados que ejecutan Lync Server 2013 con dos procesadores, HEX-Core, con 2.260 megaciclos.</span><span class="sxs-lookup"><span data-stu-id="91c0f-164">Total Front End Servers: The number of physical servers required are based on dedicated servers running Lync Server 2013 with dual processor, hex-core, with 2,260 megacycles.</span></span>

  - <span data-ttu-id="91c0f-165">Tenga en cuenta que se recomienda habilitar el hyperthreading ya que se ha demostrado que mejora el rendimiento de los servidores compatibles con audio o vídeo.</span><span class="sxs-lookup"><span data-stu-id="91c0f-165">Note that enabling hyperthreading is recommended and has been proven to improve performance for servers that support audio/video.</span></span>

  - <span data-ttu-id="91c0f-166">Servidores perimetrales: número de servidores perimetrales necesarios calculado a partir del 30 % de todos los usuarios simultáneos que usan estos servidores para comunicarse.</span><span class="sxs-lookup"><span data-stu-id="91c0f-166">Edge Servers: The number of Edge Servers required, based on 30% of all concurrent users communicating through the Edge Servers.</span></span> <span data-ttu-id="91c0f-167">Este porcentaje de la calculadora no se puede modificar.</span><span class="sxs-lookup"><span data-stu-id="91c0f-167">This percentage cannot be changed in the calculator.</span></span>

  - <span data-ttu-id="91c0f-168">Almacén de los servicios de archivado/registro detallado de llamadas/calidad de la experiencia: número de almacenes necesarios para las características de archivado o supervisión (si se han habilitado en la organización).</span><span class="sxs-lookup"><span data-stu-id="91c0f-168">Archiving/Call Detail Recording/Quality of Experience services Store: The number of stores required for Archiving or Monitoring features, if they are enabled in your organization.</span></span>

  - <span data-ttu-id="91c0f-169">Servidores de base de datos back-end necesarios (grupos necesarios): número de servidores de base de datos back-end necesarios para la carga de trabajo que se ha seleccionado.</span><span class="sxs-lookup"><span data-stu-id="91c0f-169">Back End Database Server Required (Pools Required): The number of back-end database servers required to support the selected workload.</span></span>

<span data-ttu-id="91c0f-170">En la fila situada junto a Número total de servidores front-end, también se facilita información sobre la carga de los servidores y la red para todas las cargas de trabajo combinadas.</span><span class="sxs-lookup"><span data-stu-id="91c0f-170">Additionally, in the row next to Total Front End Servers, more information is provided about the load on your servers and network for all the planned workloads combined.</span></span>

  - <span data-ttu-id="91c0f-171">Carga media de CPU: uso medio de la CPU por servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="91c0f-171">Average CPU Load: The average CPU usage per Front End server.</span></span>

  - <span data-ttu-id="91c0f-172">Red en Mbps: asignación de ancho de banda necesario para el modelo de uso que se ha especificado.</span><span class="sxs-lookup"><span data-stu-id="91c0f-172">Network in Mbps: The required bandwidth allocation to support the usage model that you entered.</span></span>

  - <span data-ttu-id="91c0f-173">Memoria en GB: memoria en gigabytes necesaria para cada servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="91c0f-173">Memory in GB: Memory, in gigabytes, required for each Front End server.</span></span>

</div>

<div>

## <a name="adjusting-for-your-processors"></a><span data-ttu-id="91c0f-174">Ajustar para sus procesadores</span><span class="sxs-lookup"><span data-stu-id="91c0f-174">Adjusting For Your Processors</span></span>

<span data-ttu-id="91c0f-175">Todas las cifras de uso de CPU de la hoja de cálculo presuponen que todos los servidores cuentan con un procesador dual, 6 núcleos con 2,26 GHz, un mínimo de 32 GB de memoria, 8 unidades de disco duro de 10.000 RPM y 72 GB de espacio libre en disco.</span><span class="sxs-lookup"><span data-stu-id="91c0f-175">All the CPU usage figures in the spreadsheet assume that each server has a dual processor, hex-core with 2.26 GHz, at least 32 GB of memory, and 8 or more 10,000-RPM hard disk drives with at least 72 GB free disk space.</span></span>

<span data-ttu-id="91c0f-176">Si los servidores tienen distintos procesadores, puede ajustar las cifras a las de su hardware.</span><span class="sxs-lookup"><span data-stu-id="91c0f-176">If your servers have different processors, you can adjust the figures to match your hardware.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

