---
title: Calculadora de planeación de capacidad 2013 de Lync Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Lync Server 2013 capacity planning calculator
ms:assetid: e86c1f05-1393-408a-9549-6001572ec50d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362852(v=OCS.15)
ms:contentKeyID: 56280894
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 230b731bf7b63a1ce86b5652d9e3d3b2956c94a3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512827"
---
# <a name="using-the-capacity-planning-calculator-for-lync-server-2013"></a><span data-ttu-id="e9c35-102">Uso de la calculadora de planeación de capacidad para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9c35-102">Using the capacity planning calculator for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e9c35-103">_**Última modificación del tema:** 2013-11-21_</span><span class="sxs-lookup"><span data-stu-id="e9c35-103">_**Topic Last Modified:** 2013-11-21_</span></span>

<span data-ttu-id="e9c35-104">La calculadora de planeación de capacidad de Microsoft® Lync™ Server 2013 está disponible para su descarga en <https://www.microsoft.com/download/details.aspx?id=36828> .</span><span class="sxs-lookup"><span data-stu-id="e9c35-104">The Microsoft® Lync™ Server 2013 capacity planning calculator is available for download at <https://www.microsoft.com/download/details.aspx?id=36828>.</span></span> <span data-ttu-id="e9c35-105">Está diseñado para ayudarle a determinar los requisitos del servidor en función de las cantidades de usuarios y las modalidades de comunicación que están habilitadas en su organización.</span><span class="sxs-lookup"><span data-stu-id="e9c35-105">It is designed to assist you in determining server requirements based on numbers of users and communication modalities that are enabled at your organization.</span></span> <span data-ttu-id="e9c35-106">Escriba el perfil de su organización y la calculadora le proporcionará recomendaciones que le ayudarán a planear la topología.</span><span class="sxs-lookup"><span data-stu-id="e9c35-106">You enter your organization’s profile, and the calculator provides recommendations that help you plan your topology.</span></span>

<span data-ttu-id="e9c35-107">Las recomendaciones creadas por la calculadora son solo para fines de planeación.</span><span class="sxs-lookup"><span data-stu-id="e9c35-107">The recommendations created by the calculator are for planning purposes only.</span></span> <span data-ttu-id="e9c35-108">La simulación de carga real es necesaria para garantizar que Lync Server 2013 se haya aprovisionado correctamente.</span><span class="sxs-lookup"><span data-stu-id="e9c35-108">Actual load simulation is required to ensure that Lync Server 2013 is adequately provisioned.</span></span> <span data-ttu-id="e9c35-109">Para realizar pruebas de esfuerzo con una carga simulada, use la [herramienta de esfuerzo y rendimiento de Lync Server 2013](https://go.microsoft.com/fwlink/?linkid=282724).</span><span class="sxs-lookup"><span data-stu-id="e9c35-109">To perform stress testing under a simulated load, use the [Lync Server 2013 Stress and Performance Tool](https://go.microsoft.com/fwlink/?linkid=282724).</span></span>

<span data-ttu-id="e9c35-110">Una vez que haya determinado el perfil de usuario y las modalidades que desea habilitar para los usuarios, es el momento de usar la calculadora para planear el número de servidores, la memoria y el ancho de banda que necesita.</span><span class="sxs-lookup"><span data-stu-id="e9c35-110">After you have determined your user profile and the modalities that you want to enable for your users, it is time to use the calculator to plan the number of servers, memory, and bandwidth that you need.</span></span> <span data-ttu-id="e9c35-111">Esta versión de la calculadora no proporciona instrucciones sobre los requisitos de e/s de disco.</span><span class="sxs-lookup"><span data-stu-id="e9c35-111">This version of the calculator does not provide guidance for disk I/O requirements.</span></span>

<span data-ttu-id="e9c35-112">Esta calculadora complementa a [Microsoft Lync Server](https://go.microsoft.com/fwlink/?linkid=282725) y [Microsoft Lync Server](lync-server-2013-planning.md).</span><span class="sxs-lookup"><span data-stu-id="e9c35-112">This calculator complements the [Microsoft Lync Server](https://go.microsoft.com/fwlink/?linkid=282725) and [Microsoft Lync Server](lync-server-2013-planning.md).</span></span> <span data-ttu-id="e9c35-113">Use la calculadora una vez que haya revisado la guía y haya creado una topología recomendada mediante la herramienta de planeación.</span><span class="sxs-lookup"><span data-stu-id="e9c35-113">Use the calculator after you have reviewed the guide and created a recommended topology by using the Planning Tool.</span></span>

<span data-ttu-id="e9c35-114">Puede beneficiarse de la calculadora si tiene información precisa y detallada sobre su perfil de usuario específico.</span><span class="sxs-lookup"><span data-stu-id="e9c35-114">You can benefit most from the calculator if you have accurate, detailed information about your specific user profile.</span></span> <span data-ttu-id="e9c35-115">Por ejemplo, el porcentaje de usuarios habilitados para voz, promedio de llamadas por usuario y hora, duración de las llamadas y el porcentaje de usuarios simultáneos en conferencias puede hacer una gran diferencia en los requisitos del servidor.</span><span class="sxs-lookup"><span data-stu-id="e9c35-115">For example, the percentage of voice-enabled users, average calls per user per hour, call duration, and the percentage of concurrent users in conferences can make a huge difference in server requirements.</span></span> <span data-ttu-id="e9c35-116">La precisión de las recomendaciones que crea la calculadora depende de la exactitud de la información proporcionada.</span><span class="sxs-lookup"><span data-stu-id="e9c35-116">The accuracy of the recommendations created by the calculator depends on the accuracy of the information that you provide.</span></span>

<div>

## <a name="using-the-capacity-calculator"></a><span data-ttu-id="e9c35-117">Uso de la calculadora de capacidad</span><span class="sxs-lookup"><span data-stu-id="e9c35-117">Using the Capacity Calculator</span></span>

<span data-ttu-id="e9c35-118">La calculadora es una hoja de cálculo de Microsoft Excel®.</span><span class="sxs-lookup"><span data-stu-id="e9c35-118">The calculator is a Microsoft Excel® spreadsheet.</span></span> <span data-ttu-id="e9c35-119">Las celdas de color naranja son para su entrada.</span><span class="sxs-lookup"><span data-stu-id="e9c35-119">Orange-colored cells are for input from you.</span></span> <span data-ttu-id="e9c35-120">Se especifican los valores predeterminados (80.000 usuarios en un grupo con doce servidores front-end), pero puede cambiar estos valores según las necesidades de su organización.</span><span class="sxs-lookup"><span data-stu-id="e9c35-120">Default values are entered (80,000 users in one pool with twelve Front End Servers), but you can change these values according to your organization’s needs.</span></span>

<span data-ttu-id="e9c35-121">El modelo de uso contiene las siguientes secciones.</span><span class="sxs-lookup"><span data-stu-id="e9c35-121">The usage model contains the following sections.</span></span> <span data-ttu-id="e9c35-122">Para calcular los requisitos de capacidad, escriba los datos como se describe:</span><span class="sxs-lookup"><span data-stu-id="e9c35-122">To calculate your capacity requirements, enter data as described:</span></span>

<span data-ttu-id="e9c35-123">**Mensajería instantánea y presencia**</span><span class="sxs-lookup"><span data-stu-id="e9c35-123">**Instant Messaging and Presence**</span></span>

  - <span data-ttu-id="e9c35-124">En número de usuarios, escriba el número de usuarios que van a iniciar sesión de forma simultánea.</span><span class="sxs-lookup"><span data-stu-id="e9c35-124">Under Number of Users, type the number of users who will be concurrently signed in.</span></span> <span data-ttu-id="e9c35-125">Este número suele ser el 80% del número total de usuarios aprovisionados.</span><span class="sxs-lookup"><span data-stu-id="e9c35-125">This number is typically 80% of the total number of provisioned users.</span></span> <span data-ttu-id="e9c35-126">En la mayoría de los casos, el 100% de los usuarios simultáneos estará habilitado para mensajería instantánea y presencia.</span><span class="sxs-lookup"><span data-stu-id="e9c35-126">In most situations, 100% of your concurrent users will be enabled for IM and Presence.</span></span> <span data-ttu-id="e9c35-127">El valor predeterminado es 80.000.</span><span class="sxs-lookup"><span data-stu-id="e9c35-127">The default is 80,000.</span></span>

  - <span data-ttu-id="e9c35-128">Número medio de contactos en la lista de contactos indica el número de contactos que estamos usando para validar los requisitos del sistema.</span><span class="sxs-lookup"><span data-stu-id="e9c35-128">Average number of contacts in Contact list indicates the number of contacts that we are using to validate your system requirements.</span></span> <span data-ttu-id="e9c35-129">Este número no es modificable.</span><span class="sxs-lookup"><span data-stu-id="e9c35-129">This number is not changeable.</span></span>

<span data-ttu-id="e9c35-130">**Telefonía IP empresarial**</span><span class="sxs-lookup"><span data-stu-id="e9c35-130">**Enterprise Voice**</span></span>

  - <span data-ttu-id="e9c35-131">En usuarios habilitados para telefonía IP empresarial, escriba el porcentaje de usuarios que están habilitados para telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="e9c35-131">In Users enabled for Enterprise Voice, type the percentage of your users who are enabled for Enterprise Voice.</span></span> <span data-ttu-id="e9c35-132">El valor predeterminado es 60%.</span><span class="sxs-lookup"><span data-stu-id="e9c35-132">The default is 60%.</span></span>

  - <span data-ttu-id="e9c35-133">En número medio de llamadas por usuario por hora (máximo), escriba el número de llamadas por hora que se espera que el usuario medio participe durante los períodos de carga máxima.</span><span class="sxs-lookup"><span data-stu-id="e9c35-133">In Average number of calls per user per hour (peak), type the number of calls per hour that you expect the average user to participate in during times of peak load.</span></span> <span data-ttu-id="e9c35-134">El valor predeterminado es 4.</span><span class="sxs-lookup"><span data-stu-id="e9c35-134">The default is 4.</span></span>

  - <span data-ttu-id="e9c35-135">En porcentaje de llamadas que usan la omisión de medios, escriba el porcentaje de llamadas realizadas por los usuarios que pasarán por alto el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="e9c35-135">In Percentage of calls that use media bypass, type the percentage of calls placed by your users that will bypass the Mediation Server.</span></span> <span data-ttu-id="e9c35-136">El valor predeterminado es 65%.</span><span class="sxs-lookup"><span data-stu-id="e9c35-136">The default is 65%.</span></span>

  - <span data-ttu-id="e9c35-137">En porcentaje de los usuarios de voz implicados en las llamadas de UC a RTC, escriba el porcentaje de llamadas de su organización que son llamadas telefónicas de UC a RTC.</span><span class="sxs-lookup"><span data-stu-id="e9c35-137">In Percentage of voice users involved in UC-PSTN calls, type the percentage of your organization’s calls which are UC-PSTN phone calls.</span></span> <span data-ttu-id="e9c35-138">El valor predeterminado es 60%.</span><span class="sxs-lookup"><span data-stu-id="e9c35-138">The default is 60%</span></span>

  - <span data-ttu-id="e9c35-139">En porcentaje de los usuarios de voz implicados en las llamadas de UC a UC se muestra el porcentaje de usuarios que están habilitados para telefonía IP empresarial que solo se habilitarán para las llamadas de comunicaciones unificadas.</span><span class="sxs-lookup"><span data-stu-id="e9c35-139">In Percentage of voice users involved in UC-UC calls shows the percentage of users who are enabled for Enterprise Voice who will be enabled only for UC-UC calls.</span></span> <span data-ttu-id="e9c35-140">Este número se calcula en función de lo que se especifique para el porcentaje de usuarios de voz habilitados para llamadas de UC a RTC.</span><span class="sxs-lookup"><span data-stu-id="e9c35-140">This number is calculated based on what you input for Percentage of voice users enabled for UC-PSTN calls.</span></span>

<span data-ttu-id="e9c35-141">**Conferencia**</span><span class="sxs-lookup"><span data-stu-id="e9c35-141">**Conferencing**</span></span>

  - <span data-ttu-id="e9c35-142">En porcentaje de usuarios en conferencias simultáneas, escriba el porcentaje de usuarios que se participarán simultáneamente en conferencias.</span><span class="sxs-lookup"><span data-stu-id="e9c35-142">In Percentage of users in concurrent conferences, type the percentage of users who will be concurrently participating in conferences.</span></span> <span data-ttu-id="e9c35-143">El valor predeterminado es el 5%.</span><span class="sxs-lookup"><span data-stu-id="e9c35-143">The default is 5%.</span></span>

  - <span data-ttu-id="e9c35-144">En porcentaje de conferencias con sólo mensajería instantánea del grupo (sin voz), escriba el porcentaje de conferencias cuyas conferencias implicarán únicamente mensajería instantánea; es decir, que no incluyen un componente de audio.</span><span class="sxs-lookup"><span data-stu-id="e9c35-144">In Percentage of conferences with group IM only (no voice), type the percentage of conferences whose conferences will involve instant messaging only; that is, that do not include an audio component.</span></span> <span data-ttu-id="e9c35-145">El valor predeterminado es el 10%.</span><span class="sxs-lookup"><span data-stu-id="e9c35-145">The default is 10%</span></span>

  - <span data-ttu-id="e9c35-146">En porcentaje de usuarios que usan la Conferencia de acceso telefónico local, escriba el porcentaje de participantes simultáneos en conferencias que utilizarán la Conferencia de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="e9c35-146">In Percentage of users using dial-in conferencing, type the percentage of concurrent participants in conferences who will be using dial-in conferencing.</span></span> <span data-ttu-id="e9c35-147">El valor predeterminado es el 15%.</span><span class="sxs-lookup"><span data-stu-id="e9c35-147">The default is 15%.</span></span>

  - <span data-ttu-id="e9c35-148">En porcentaje de conferencias con voz, escriba el porcentaje de conferencias que incluirán un componente de audio.</span><span class="sxs-lookup"><span data-stu-id="e9c35-148">In Percentage of conferences using voice, type the percentage of conferences that will include an audio component.</span></span>
    
      - <span data-ttu-id="e9c35-149">Si el 20% de las conferencias de voz también incluirá vídeo normal, seleccione la casilla de verificación incluir vídeo (sin vista múltiple).</span><span class="sxs-lookup"><span data-stu-id="e9c35-149">If 20% of your voice conferences will also include regular video, select the Including video (no Multi View) check box.</span></span>
    
      - <span data-ttu-id="e9c35-150">Si el 20% de las conferencias también incluirá vídeo con varias vistas, active la casilla de verificación incluir varias vistas.</span><span class="sxs-lookup"><span data-stu-id="e9c35-150">If 20% of your conferences will also include Multi-View video, select the Including Multi View check box.</span></span>
    
      - <span data-ttu-id="e9c35-151">Si el 50% de las conferencias de voz también incluirá el uso compartido de aplicaciones, active la casilla incluir uso compartido de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="e9c35-151">If 50% of your voice conferences will also include application sharing, select the Including application sharing check box.</span></span>
    
      - <span data-ttu-id="e9c35-152">Si el 20% de las conferencias de voz incluye cargas de datos, como presentaciones de Microsoft PowerPoint®, active la casilla de verificación incluir conferencia Web.</span><span class="sxs-lookup"><span data-stu-id="e9c35-152">If 20% of your voice conferences include data uploads, such as Microsoft PowerPoint® presentations, select the Including web conferencing check box.</span></span>

<span data-ttu-id="e9c35-153">**Movilidad**</span><span class="sxs-lookup"><span data-stu-id="e9c35-153">**Mobility**</span></span>

  - <span data-ttu-id="e9c35-154">En porcentaje de usuarios habilitados para movilidad, escriba el porcentaje de usuarios que se habilitarán para conectarse a Lync Server mediante dispositivos móviles.</span><span class="sxs-lookup"><span data-stu-id="e9c35-154">In Percentage of users enabled for Mobility, type the percentage of your users who will be enabled to connect to Lync Server using mobile devices.</span></span> <span data-ttu-id="e9c35-155">El valor predeterminado es 40%.</span><span class="sxs-lookup"><span data-stu-id="e9c35-155">The default is 40%.</span></span>

<span data-ttu-id="e9c35-156">Una vez que haya introducido toda la información necesaria, la calculadora de capacidad estima sus requisitos.</span><span class="sxs-lookup"><span data-stu-id="e9c35-156">When you have entered all the necessary information, the capacity calculator estimates your requirements.</span></span> <span data-ttu-id="e9c35-157">Las celdas amarillas muestran los valores calculados para los requisitos de CPU, memoria y ancho de banda en función de las pruebas realizadas en los laboratorios de rendimiento de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e9c35-157">The yellow cells show calculated values for CPU, memory, and bandwidth requirements based on tests performed in Lync Server 2013 performance labs.</span></span> <span data-ttu-id="e9c35-158">Los números se proporcionan como instrucciones, no se comprueba y valida cada variación única.</span><span class="sxs-lookup"><span data-stu-id="e9c35-158">The numbers are provided as a guideline, not every single variation is tested and validated.</span></span> <span data-ttu-id="e9c35-159">Se calculan los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="e9c35-159">The following values are calculated:</span></span>

  - <span data-ttu-id="e9c35-160">CPU front-end: porcentaje de uso de la CPU si la carga completa se administraba a través de un servidor front-end de las mismas especificaciones que el servidor que se usaba en las pruebas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e9c35-160">Front End CPU: Percentage of CPU usage if the entire load were being handled by one Front End Server of the same specifications as the server that was used in Microsoft testing.</span></span>

  - <span data-ttu-id="e9c35-161">Red en Mbps: requisitos de ancho de banda en megabits por segundo (Mbps) para la carga de trabajo correspondiente.</span><span class="sxs-lookup"><span data-stu-id="e9c35-161">Network in Mbps: Bandwidth requirements in megabits per second (Mbps) for the corresponding workload.</span></span>

  - <span data-ttu-id="e9c35-162">Memoria en GB: memoria necesaria en gigabytes (GB) para la carga de trabajo correspondiente.</span><span class="sxs-lookup"><span data-stu-id="e9c35-162">Memory in GB: Memory required in gigabytes (GB) for the corresponding workload.</span></span>

<span data-ttu-id="e9c35-163">Las celdas verdes muestran recomendaciones para el modelo de uso que se ha especificado.</span><span class="sxs-lookup"><span data-stu-id="e9c35-163">The green cells show recommendations for the usage model that you entered.</span></span>

  - <span data-ttu-id="e9c35-164">Total de servidores front-end: el número de servidores físicos necesarios se basa en servidores dedicados que ejecutan Lync Server 2013 con dos procesadores, HEX-Core, con 2.260 megaciclos.</span><span class="sxs-lookup"><span data-stu-id="e9c35-164">Total Front End Servers: The number of physical servers required are based on dedicated servers running Lync Server 2013 with dual processor, hex-core, with 2,260 megacycles.</span></span>

  - <span data-ttu-id="e9c35-165">Tenga en cuenta que se recomienda habilitar el hyperthreading y que se ha demostrado que mejora el rendimiento de los servidores compatibles con audio y vídeo.</span><span class="sxs-lookup"><span data-stu-id="e9c35-165">Note that enabling hyperthreading is recommended and has been proven to improve performance for servers that support audio/video.</span></span>

  - <span data-ttu-id="e9c35-166">Servidores perimetrales: número de servidores perimetrales necesarios, en función del 30% de todos los usuarios simultáneos que se comunican a través de los servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="e9c35-166">Edge Servers: The number of Edge Servers required, based on 30% of all concurrent users communicating through the Edge Servers.</span></span> <span data-ttu-id="e9c35-167">Este porcentaje no se puede cambiar en la calculadora.</span><span class="sxs-lookup"><span data-stu-id="e9c35-167">This percentage cannot be changed in the calculator.</span></span>

  - <span data-ttu-id="e9c35-168">Almacén de servicios y registro detallado de llamadas/calidad de la experiencia almacén: el número de almacenes necesarios para las características de archivado o supervisión, si están habilitados en la organización.</span><span class="sxs-lookup"><span data-stu-id="e9c35-168">Archiving/Call Detail Recording/Quality of Experience services Store: The number of stores required for Archiving or Monitoring features, if they are enabled in your organization.</span></span>

  - <span data-ttu-id="e9c35-169">Se requiere servidor de base de datos back-end (grupos requeridos): el número de servidores de base de datos back-end necesarios para admitir la carga de trabajo seleccionada.</span><span class="sxs-lookup"><span data-stu-id="e9c35-169">Back End Database Server Required (Pools Required): The number of back-end database servers required to support the selected workload.</span></span>

<span data-ttu-id="e9c35-170">Además, en la fila junto a total de servidores front-end, se proporciona más información acerca de la carga de los servidores y la red para todas las cargas de trabajo previstas combinadas.</span><span class="sxs-lookup"><span data-stu-id="e9c35-170">Additionally, in the row next to Total Front End Servers, more information is provided about the load on your servers and network for all the planned workloads combined.</span></span>

  - <span data-ttu-id="e9c35-171">Carga de CPU media: el uso medio de CPU por servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="e9c35-171">Average CPU Load: The average CPU usage per Front End server.</span></span>

  - <span data-ttu-id="e9c35-172">Red en Mbps: la asignación de ancho de banda necesaria para admitir el modelo de uso que ha escrito.</span><span class="sxs-lookup"><span data-stu-id="e9c35-172">Network in Mbps: The required bandwidth allocation to support the usage model that you entered.</span></span>

  - <span data-ttu-id="e9c35-173">Memoria en GB: memoria, en gigabytes, necesaria para cada servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="e9c35-173">Memory in GB: Memory, in gigabytes, required for each Front End server.</span></span>

</div>

<div>

## <a name="adjusting-for-your-processors"></a><span data-ttu-id="e9c35-174">Ajustar para sus procesadores</span><span class="sxs-lookup"><span data-stu-id="e9c35-174">Adjusting For Your Processors</span></span>

<span data-ttu-id="e9c35-175">Todas las cifras de uso de la CPU de la hoja de cálculo suponen que cada servidor tiene un procesador dual, HEX-Core con 2,26 GHz, al menos 32 GB de memoria y 8 o más unidades de disco duro 10.000-RPM con al menos 72 GB de espacio libre en disco.</span><span class="sxs-lookup"><span data-stu-id="e9c35-175">All the CPU usage figures in the spreadsheet assume that each server has a dual processor, hex-core with 2.26 GHz, at least 32 GB of memory, and 8 or more 10,000-RPM hard disk drives with at least 72 GB free disk space.</span></span>

<span data-ttu-id="e9c35-176">Si los servidores tienen distintos procesadores, puede ajustar las cifras para que se ajusten a su hardware.</span><span class="sxs-lookup"><span data-stu-id="e9c35-176">If your servers have different processors, you can adjust the figures to match your hardware.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

