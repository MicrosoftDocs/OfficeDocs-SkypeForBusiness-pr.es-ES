---
title: Ejemplo de recopilación de los requisitos para el control de admisión de llamadas
description: Ejemplo de recopilación de los requisitos para el control de admisión de llamadas.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Example of gathering your requirements for call admission control
ms:assetid: 3363ac53-b7c4-4a59-aea1-b2f3ee016ae1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425827(v=OCS.15)
ms:contentKeyID: 48183820
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 25c0b450070bda62c2610d98cfff8c8cd16ad2af
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564946"
---
# <a name="example-gathering-your-requirements-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="1d6d6-103">Ejemplo: recopilar los requisitos para el control de admisión de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d6d6-103">Example: Gathering your requirements for call admission control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1d6d6-104">_**Última modificación del tema:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="1d6d6-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="1d6d6-p101">Este ejemplo muestra cómo planear e implementar el control de admisión de llamadas (CAC). De forma general, esto consta de las siguientes actividades:</span><span class="sxs-lookup"><span data-stu-id="1d6d6-p101">This example shows you how to plan for and implement call admission control (CAC). At a high level, this consists of the following activities:</span></span>

1.  <span data-ttu-id="1d6d6-107">Identificar todos los concentradores de red y redes troncales (llamados *regiones de red*).</span><span class="sxs-lookup"><span data-stu-id="1d6d6-107">Identify all of your network hubs and backbones (known as *network regions*).</span></span>

2.  <span data-ttu-id="1d6d6-108">Identificar el sitio central de Lync Server que va a administrar el CAC para cada región de red.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-108">Identify the Lync Server central site that will manage CAC for each network region.</span></span>

3.  <span data-ttu-id="1d6d6-109">Identificar y definir los *sitios de red* que están conectados a cada región de red.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-109">Identify and define the *network sites* that are connected to each network region.</span></span>

4.  <span data-ttu-id="1d6d6-110">Para cada sitio de red cuya conexión a la WAN tiene restringido el ancho de banda, describa la capacidad de ancho de banda de la conexión WAN y los límites de ancho de banda que el administrador de red ha configurado para el tráfico de medios de Lync Server, si procede.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-110">For each network site whose connection to the WAN is bandwidth-constrained, describe the bandwidth capacity of the WAN connection and the bandwidth limits that to the network administrator has set for Lync Server media traffic, if applicable.</span></span> <span data-ttu-id="1d6d6-111">No es necesario incluir sitios cuya conexión a la red WAN no tiene ancho de banda restringido.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-111">You do not need to include sites whose connection to the WAN is not bandwidth-constrained.</span></span>

5.  <span data-ttu-id="1d6d6-112">Asociar cada subred de la red a un sitio de red.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-112">Associate each subnet in your network with a network site.</span></span>

6.  <span data-ttu-id="1d6d6-113">Asignar los vínculos entre las regiones de red.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-113">Map the links between the network regions.</span></span> <span data-ttu-id="1d6d6-114">Para cada vínculo, describa la capacidad de ancho de banda y los límites que el administrador de red haya colocado en el tráfico de medios de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-114">For each link, describe its bandwidth capacity and any limits that the network administrator has placed on Lync Server media traffic.</span></span>

7.  <span data-ttu-id="1d6d6-115">Definir una ruta entre cada par de regiones de red.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-115">Define a route between every pair of network regions.</span></span>

<div>

## <a name="gather-the-required-information"></a><span data-ttu-id="1d6d6-116">Recopilar la información necesaria</span><span class="sxs-lookup"><span data-stu-id="1d6d6-116">Gather the Required Information</span></span>

<span data-ttu-id="1d6d6-117">Para preparar el control de admisión de llamadas, recopile la información descrita en los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="1d6d6-117">To prepare for call admission control, gather the information described in the following steps:</span></span>

1.  <span data-ttu-id="1d6d6-p104">Identificar las regiones de red. Una región de red representa una red troncal de red o un concentrador de red.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-p104">Identify your network regions. A network region represents a network backbone or a network hub.</span></span>
    
    <span data-ttu-id="1d6d6-p105">Una red troncal de red o un concentrador de red forma parte de una infraestructura de red informática que interconecta diversas partes de red, que proporciona una ruta de acceso para el intercambio de información entre distintas redes LAN o subredes. Una red troncal puede asociar diversas redes, desde una ubicación pequeña a una amplia zona geográfica. La capacidad de la red troncal suele ser mayor que la de las redes conectadas a ella.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-p105">A network backbone or a network hub is a part of computer network infrastructure that interconnects various pieces of network, providing a path for the exchange of information between different LANs or subnets. A backbone can tie together diverse networks, from a small location to a wide geographic area. The backbone's capacity is typically greater than that of the networks connected to it.</span></span>
    
    <span data-ttu-id="1d6d6-p106">Nuestra topología de ejemplo tiene tres regiones de red: Norteamérica, EMEA y APAC. Una región de red incluye una colección de sitios de red. Trabaje con el administrador de la red para definir las regiones de red de su empresa.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-p106">Our example topology has three network regions: North America, EMEA, and APAC. A network region contains a collection of network sites. Work with your network administrator to define the network regions for your enterprise.</span></span>

2.  <span data-ttu-id="1d6d6-126">Identificar cada sitio central asociado a la región de red.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-126">Identify each network region’s associated central site.</span></span> <span data-ttu-id="1d6d6-127">Un sitio central contiene al menos un servidor front-end y es la implementación de Lync Server que administrará el CAC para todo el tráfico de medios que pasa a través de la conexión WAN de la región de red.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-127">A central site contains at least one Front End Server and is the Lync Server deployment that will manage CAC for all media traffic that passes through the network region’s WAN connection.</span></span>
    
    <span data-ttu-id="1d6d6-128">**Red de empresa de ejemplo dividida en tres regiones de red**</span><span class="sxs-lookup"><span data-stu-id="1d6d6-128">**An example enterprise network divided into three network regions**</span></span>
    
    <span data-ttu-id="1d6d6-129">![Ejemplo de topología de red con 3 regiones de red](images/Gg425827.08937347-250f-488f-ba5f-c256e6afcd8b(OCS.15).jpg "Ejemplo de topología de red con 3 regiones de red")</span><span class="sxs-lookup"><span data-stu-id="1d6d6-129">![Network Topology Example with 3 Network Regions](images/Gg425827.08937347-250f-488f-ba5f-c256e6afcd8b(OCS.15).jpg "Network Topology Example with 3 Network Regions")</span></span>  
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="1d6d6-130">Una red de conmutación de etiquetas multiprotocolo (MPLS) debe representarse como una región de red en la que cada ubicación geográfica tiene un sitio de red correspondiente.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-130">A Multiprotocol Label Switching (MPLS) network should be represented as a network region in which each geographic location has a corresponding network site.</span></span> <span data-ttu-id="1d6d6-131">Para obtener más información, consulte el tema "<A href="lync-server-2013-call-admission-control-on-an-mpls-network.md">control de admisión de llamadas en una red MPLS con Lync Server 2013</A>" en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-131">For details, see the “<A href="lync-server-2013-call-admission-control-on-an-mpls-network.md">Call admission control on an MPLS network with Lync Server 2013</A>” topic in the Planning documentation.</span></span>

    
    </div>
    
    <span data-ttu-id="1d6d6-132">En la topología de red de ejemplo anterior, hay tres regiones de red, cada una con un sitio central de Lync Server que administra el CAC.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-132">In the preceding example network topology, there are three network regions, each with a Lync Server central site that manages CAC.</span></span> <span data-ttu-id="1d6d6-133">El sitio central adecuado para una región de red se elige por la proximidad geográfica.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-133">The appropriate central site for a network region is chosen by the geographic vicinity.</span></span> <span data-ttu-id="1d6d6-134">Como el tráfico de medios será mayor dentro de las regiones de red, la propiedad por proximidad geográfica lo hace independiente y seguirá siendo funcional aunque otros sitios centrales dejen de estar disponibles.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-134">Because media traffic will be heaviest within network regions, the ownership by geographic vicinity makes it self-contained and will continue to be functional even if other central sites become unavailable.</span></span>
    
    <span data-ttu-id="1d6d6-135">En este ejemplo, una implementación de Lync Server llamada Chicago es el sitio central de la región de Norteamérica.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-135">In this example, a Lync Server deployment named Chicago is the central site for the North America region.</span></span>
    
    <span data-ttu-id="1d6d6-136">Todos los usuarios de Lync de Norteamérica están hospedados en los servidores de la implementación de Chicago.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-136">All Lync users in North America are homed on servers in the Chicago deployment.</span></span> <span data-ttu-id="1d6d6-137">En la tabla siguiente se muestran los sitios centrales de las tres regiones de red.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-137">The following table shows central sites for all three network regions.</span></span>
    
    ### <a name="network-regions-and-their-associated-central-sites"></a><span data-ttu-id="1d6d6-138">Regiones de red y sus sitios centrales asociados</span><span class="sxs-lookup"><span data-stu-id="1d6d6-138">Network Regions and their Associated Central Sites</span></span>
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="1d6d6-139">Región de red</span><span class="sxs-lookup"><span data-stu-id="1d6d6-139">Network Region</span></span></th>
    <th><span data-ttu-id="1d6d6-140">Sitio central</span><span class="sxs-lookup"><span data-stu-id="1d6d6-140">Central Site</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="1d6d6-141">Norteamérica</span><span class="sxs-lookup"><span data-stu-id="1d6d6-141">North America</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-142">Guadalajara</span><span class="sxs-lookup"><span data-stu-id="1d6d6-142">Chicago</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="1d6d6-143">EMEA</span><span class="sxs-lookup"><span data-stu-id="1d6d6-143">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-144">México</span><span class="sxs-lookup"><span data-stu-id="1d6d6-144">London</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="1d6d6-145">Pacífico</span><span class="sxs-lookup"><span data-stu-id="1d6d6-145">APAC</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-146">Beijing</span><span class="sxs-lookup"><span data-stu-id="1d6d6-146">Beijing</span></span></p></td>
    </tr>
    </tbody>
    </table>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="1d6d6-147">Según la topología de Lync Server, el mismo sitio central puede asignarse a varias regiones de red.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-147">Depending on your Lync Server topology, the same central site can be assigned to multiple network regions.</span></span>

    
    </div>

3.  <span data-ttu-id="1d6d6-p111">En cada región de red, identifique todos los sitios de red (oficinas o ubicaciones) cuyas conexiones WAN no tienen ancho de banda restringido. Como estos sitios no tienen ancho de banda restringido, no es necesario aplicarles directivas de ancho de banda de CAC.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-p111">For each network region, identify all of the network sites (offices or locations) whose WAN connections are not bandwidth-constrained. Because these sites are not bandwidth constrained, you do not need to apply CAC bandwidth policies to them.</span></span>
    
    <span data-ttu-id="1d6d6-150">En el ejemplo que se muestra en la siguiente tabla, tres sitios de red no tienen vínculos WAN de ancho de banda restringido: Nueva York, Chicago y Detroit.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-150">In the example shown in the following table, three network sites do not have bandwidth-constrained WAN links: New York, Chicago, and Detroit.</span></span>
    
    ### <a name="network-sites-not-constrained-by-wan-bandwidth"></a><span data-ttu-id="1d6d6-151">Sitios de red no restringidos por el ancho de banda de WAN</span><span class="sxs-lookup"><span data-stu-id="1d6d6-151">Network Sites not Constrained by WAN Bandwidth</span></span>
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="1d6d6-152">Sitio de red</span><span class="sxs-lookup"><span data-stu-id="1d6d6-152">Network Site</span></span></th>
    <th><span data-ttu-id="1d6d6-153">Región de red</span><span class="sxs-lookup"><span data-stu-id="1d6d6-153">Network Region</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="1d6d6-154">Nueva York</span><span class="sxs-lookup"><span data-stu-id="1d6d6-154">New York</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-155">Norteamérica</span><span class="sxs-lookup"><span data-stu-id="1d6d6-155">North America</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="1d6d6-156">Guadalajara</span><span class="sxs-lookup"><span data-stu-id="1d6d6-156">Chicago</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-157">Norteamérica</span><span class="sxs-lookup"><span data-stu-id="1d6d6-157">North America</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="1d6d6-158">Detroit</span><span class="sxs-lookup"><span data-stu-id="1d6d6-158">Detroit</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-159">Norteamérica</span><span class="sxs-lookup"><span data-stu-id="1d6d6-159">North America</span></span></p></td>
    </tr>
    </tbody>
    </table>


4.  <span data-ttu-id="1d6d6-160">En cada región de red, identifique todos los sitios de red que se conectan a la región de red a través de vínculos WAN de ancho de banda restringido.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-160">For each network region, identify all of the network sites that connect to the network region through bandwidth-constrained WAN links.</span></span>
    
    <span data-ttu-id="1d6d6-161">Para asegurar la calidad de audio y vídeo, se recomienda que estos sitios de red de ancho de banda restringido tengan las redes WAN supervisadas y directivas de ancho de banda del CAC que limiten el flujo del tráfico de medios (voz o vídeo) hacia la región de red y desde ella.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-161">To help ensure audio and video quality, we recommend that these bandwidth-constrained network sites have their WANs monitored and CAC bandwidth policies that limit media (voice or video) traffic flow to and from the network region.</span></span>
    
    <span data-ttu-id="1d6d6-162">En el ejemplo que se muestra en la siguiente tabla, hay tres sitios de red que están restringidos por el ancho de banda de WAN: Portland, Reno y Albuquerque.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-162">In the example shown in the following table, there are three network sites that are constrained by WAN bandwidth: Portland, Reno and Albuquerque.</span></span>
    
    ### <a name="network-sites-constrained-by-wan-bandwidth"></a><span data-ttu-id="1d6d6-163">Sitios de red restringidos por el ancho de banda de WAN</span><span class="sxs-lookup"><span data-stu-id="1d6d6-163">Network Sites Constrained by WAN Bandwidth</span></span>
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="1d6d6-164">Sitio de red</span><span class="sxs-lookup"><span data-stu-id="1d6d6-164">Network Site</span></span></th>
    <th><span data-ttu-id="1d6d6-165">Región de red</span><span class="sxs-lookup"><span data-stu-id="1d6d6-165">Network Region</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="1d6d6-166">Albuquerque</span><span class="sxs-lookup"><span data-stu-id="1d6d6-166">Albuquerque</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-167">Norteamérica</span><span class="sxs-lookup"><span data-stu-id="1d6d6-167">North America</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="1d6d6-168">Reno</span><span class="sxs-lookup"><span data-stu-id="1d6d6-168">Reno</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-169">Norteamérica</span><span class="sxs-lookup"><span data-stu-id="1d6d6-169">North America</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="1d6d6-170">Portland</span><span class="sxs-lookup"><span data-stu-id="1d6d6-170">Portland</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-171">Norteamérica</span><span class="sxs-lookup"><span data-stu-id="1d6d6-171">North America</span></span></p></td>
    </tr>
    </tbody>
    </table>
    
    <span data-ttu-id="1d6d6-172">**Región de red para CAC Norteamérica con tres sitios de red que no están restringidos por el ancho de banda (Chicago, Nueva York y Detroit) y tres sitios de red que están restringidos por el ancho de banda de WAN (Portland, Reno y Albuquerque)**</span><span class="sxs-lookup"><span data-stu-id="1d6d6-172">**CAC network region North America with three network sites that are unconstrained by bandwidth (Chicago, New York, and Detroit) and three network sites that are constrained by WAN bandwidth (Portland, Reno, and Albuquerque)**</span></span>
    
    <span data-ttu-id="1d6d6-173">![Sitios de red de ejemplo restringidos por el ancho de banda de WAN](images/Gg425827.d9d1f231-db4d-4dd7-8fbc-eb0b6d1e705d(OCS.15).jpg "Sitios de red de ejemplo restringidos por el ancho de banda de WAN")</span><span class="sxs-lookup"><span data-stu-id="1d6d6-173">![Example network sites constrained by WAN bandwidth](images/Gg425827.d9d1f231-db4d-4dd7-8fbc-eb0b6d1e705d(OCS.15).jpg "Example network sites constrained by WAN bandwidth")</span></span>  

5.  <span data-ttu-id="1d6d6-174">Para cada vínculo WAN de ancho de banda restringido, determine lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1d6d6-174">For each bandwidth-constrained WAN link, determine the following:</span></span>
    
      - <span data-ttu-id="1d6d6-175">Límite general de ancho de banda que desea establecer para todas las sesiones simultáneas de audio.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-175">Overall bandwidth limit that you want to set for all concurrent audio sessions.</span></span> <span data-ttu-id="1d6d6-176">Si una nueva sesión de audio provoca que se supere este límite, Lync Server no permite que se inicie la sesión.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-176">If a new audio session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="1d6d6-p113">Límite de ancho de banda que desea establecer para cada sesión individual de audio. El límite predeterminado de ancho de banda para CAC es de 175 kbps, pero el administrador puede modificarlo.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-p113">Bandwidth limit that you want to set for each individual audio session. The default CAC bandwidth limit is 175 kbps, but it can be modified by the administrator.</span></span>
    
      - <span data-ttu-id="1d6d6-179">Límite general de ancho de banda que desea establecer para todas las sesiones simultáneas de vídeo.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-179">Overall bandwidth limit that you want to set for all concurrent video sessions.</span></span> <span data-ttu-id="1d6d6-180">Si una nueva sesión de vídeo provoca que se supere este límite, Lync Server no permite que se inicie la sesión.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-180">If a new video session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="1d6d6-p115">Límite de ancho de banda que desea establecer para cada sesión individual de vídeo. El límite predeterminado de ancho de banda para CAC es de 700 kbps, pero el administrador puede modificarlo.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-p115">Bandwidth limit that you want to set for each individual video session. The default CAC bandwidth limit is 700 kbps, but it can be modified by the administrator.</span></span>
    
    ### <a name="network-sites-with-wan-bandwidth-constraint-information-bandwidth-in-kbps"></a><span data-ttu-id="1d6d6-183">Sitios de red con información de restricción de ancho de banda de WAN (ancho de banda en kbps)</span><span class="sxs-lookup"><span data-stu-id="1d6d6-183">Network Sites with WAN Bandwidth Constraint Information (Bandwidth in kbps)</span></span>
    
    <table style="width:100%;">
    <colgroup>
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="1d6d6-184">Sitio de red</span><span class="sxs-lookup"><span data-stu-id="1d6d6-184">Network Site</span></span></th>
    <th><span data-ttu-id="1d6d6-185">Región de red</span><span class="sxs-lookup"><span data-stu-id="1d6d6-185">Network Region</span></span></th>
    <th><span data-ttu-id="1d6d6-186">Límite de ancho de banda</span><span class="sxs-lookup"><span data-stu-id="1d6d6-186">BW Limit</span></span></th>
    <th><span data-ttu-id="1d6d6-187">Límite de audio</span><span class="sxs-lookup"><span data-stu-id="1d6d6-187">Audio Limit</span></span></th>
    <th><span data-ttu-id="1d6d6-188">Límite de sesión de audio</span><span class="sxs-lookup"><span data-stu-id="1d6d6-188">Audio Session Limit</span></span></th>
    <th><span data-ttu-id="1d6d6-189">Límite de vídeo</span><span class="sxs-lookup"><span data-stu-id="1d6d6-189">Video Limit</span></span></th>
    <th><span data-ttu-id="1d6d6-190">Límite de sesión de vídeo</span><span class="sxs-lookup"><span data-stu-id="1d6d6-190">Video Session Limit</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="1d6d6-191">Albuquerque</span><span class="sxs-lookup"><span data-stu-id="1d6d6-191">Albuquerque</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-192">Norteamérica</span><span class="sxs-lookup"><span data-stu-id="1d6d6-192">North America</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-193">5,000</span><span class="sxs-lookup"><span data-stu-id="1d6d6-193">5,000</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-194">2,000</span><span class="sxs-lookup"><span data-stu-id="1d6d6-194">2,000</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-195">175</span><span class="sxs-lookup"><span data-stu-id="1d6d6-195">175</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-196">1.400</span><span class="sxs-lookup"><span data-stu-id="1d6d6-196">1,400</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-197">700</span><span class="sxs-lookup"><span data-stu-id="1d6d6-197">700</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="1d6d6-198">Reno</span><span class="sxs-lookup"><span data-stu-id="1d6d6-198">Reno</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-199">Norteamérica</span><span class="sxs-lookup"><span data-stu-id="1d6d6-199">North America</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-200">10 000</span><span class="sxs-lookup"><span data-stu-id="1d6d6-200">10,000</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-201">4.000</span><span class="sxs-lookup"><span data-stu-id="1d6d6-201">4,000</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-202">175</span><span class="sxs-lookup"><span data-stu-id="1d6d6-202">175</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-203">2.800</span><span class="sxs-lookup"><span data-stu-id="1d6d6-203">2,800</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-204">700</span><span class="sxs-lookup"><span data-stu-id="1d6d6-204">700</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="1d6d6-205">Portland</span><span class="sxs-lookup"><span data-stu-id="1d6d6-205">Portland</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-206">Norteamérica</span><span class="sxs-lookup"><span data-stu-id="1d6d6-206">North America</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-207">5,000</span><span class="sxs-lookup"><span data-stu-id="1d6d6-207">5,000</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-208">4.000</span><span class="sxs-lookup"><span data-stu-id="1d6d6-208">4,000</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-209">175</span><span class="sxs-lookup"><span data-stu-id="1d6d6-209">175</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-210">2.800</span><span class="sxs-lookup"><span data-stu-id="1d6d6-210">2,800</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-211">700</span><span class="sxs-lookup"><span data-stu-id="1d6d6-211">700</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="1d6d6-212">Nueva York</span><span class="sxs-lookup"><span data-stu-id="1d6d6-212">New York</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-213">Norteamérica</span><span class="sxs-lookup"><span data-stu-id="1d6d6-213">North America</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-214">(sin límite)</span><span class="sxs-lookup"><span data-stu-id="1d6d6-214">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-215">(sin límite)</span><span class="sxs-lookup"><span data-stu-id="1d6d6-215">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-216">(sin límite)</span><span class="sxs-lookup"><span data-stu-id="1d6d6-216">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-217">(sin límite)</span><span class="sxs-lookup"><span data-stu-id="1d6d6-217">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-218">(sin límite)</span><span class="sxs-lookup"><span data-stu-id="1d6d6-218">(no limit)</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="1d6d6-219">Guadalajara</span><span class="sxs-lookup"><span data-stu-id="1d6d6-219">Chicago</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-220">Norteamérica</span><span class="sxs-lookup"><span data-stu-id="1d6d6-220">North America</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-221">(sin límite)</span><span class="sxs-lookup"><span data-stu-id="1d6d6-221">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-222">(sin límite)</span><span class="sxs-lookup"><span data-stu-id="1d6d6-222">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-223">(sin límite)</span><span class="sxs-lookup"><span data-stu-id="1d6d6-223">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-224">(sin límite)</span><span class="sxs-lookup"><span data-stu-id="1d6d6-224">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-225">(sin límite)</span><span class="sxs-lookup"><span data-stu-id="1d6d6-225">(no limit)</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="1d6d6-226">Detroit</span><span class="sxs-lookup"><span data-stu-id="1d6d6-226">Detroit</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-227">Norteamérica</span><span class="sxs-lookup"><span data-stu-id="1d6d6-227">North America</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-228">(sin límite)</span><span class="sxs-lookup"><span data-stu-id="1d6d6-228">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-229">(sin límite)</span><span class="sxs-lookup"><span data-stu-id="1d6d6-229">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-230">(sin límite)</span><span class="sxs-lookup"><span data-stu-id="1d6d6-230">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-231">(sin límite)</span><span class="sxs-lookup"><span data-stu-id="1d6d6-231">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-232">(sin límite)</span><span class="sxs-lookup"><span data-stu-id="1d6d6-232">(no limit)</span></span></p></td>
    </tr>
    </tbody>
    </table>


6.  <span data-ttu-id="1d6d6-233">Para cada subred de la red, especifique el sitio de red asociado.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-233">For every subnet in your network, specify its associated network site.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="1d6d6-p116">Cada subred de la red debe estar asociada a un sitio de red, aunque el sitio de red no esté restringido por el ancho de banda. Esto se debe a que el control de admisión de llamadas usa la información de la subred para determinar el sitio de red en que está situado un extremo. Cuando se determinan las ubicaciones de ambas partes de la sesión, el control de admisión de llamadas puede determinar si existe suficiente ancho de banda para establecer una llamada. Cuando se establece una sesión a través de un vínculo que no tiene límites de ancho de banda, se genera una alerta.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-p116">Every subnet in your network must be associated with a network site, even if the network site is not bandwidth constrained. This is because call admission control uses subnet information to determine at which network site an endpoint is located. When the locations of both parties in the session are determined, call admission control can determine if there is sufficient bandwidth to establish a call. When a session is established over a link that has no bandwidth limits, an alert is generated.</span></span><BR><span data-ttu-id="1d6d6-238">Si implementa servidores perimetrales de audio/vídeo, las direcciones IP públicas de cada servidor perimetral deben estar asociadas al sitio de red en el que se implementa el servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-238">If you deploy Audio/Video Edge Servers, the public IP addresses of each Edge Server must be associated with the network site where the Edge Server is deployed.</span></span> <span data-ttu-id="1d6d6-239">Cada dirección IP pública del servidor perimetral A/V debe agregarse a las opciones de configuración de la red como subred con una máscara de subred de 32.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-239">Each public IP address of the A/V Edge Server must be added to your network configuration settings as a subnet with a subnet mask of 32.</span></span> <span data-ttu-id="1d6d6-240">Por ejemplo, si implementa servidores perimetrales A/V en Chicago, para cada dirección IP externa de los servidores, cree una subred con una máscara de subred de 32 y asocie el sitio de red Chicago a dichas subredes.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-240">For example, if you deploy A/V Edge Servers in Chicago, then for each external IP address of those servers create a subnet with a subnet mask of 32 and associate network site Chicago with those subnets.</span></span> <span data-ttu-id="1d6d6-241">Para obtener más información acerca de las direcciones IP públicas, consulte <A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">determinar el firewall externo a/V y los requisitos de puerto para Lync Server 2013</A> en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-241">For details about public IP addresses, see <A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">Determine external A/V firewall and port requirements for Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="1d6d6-p118">Aparecerá una alerta de indicador de estado clave (KHI), que especifica una lista de direcciones IP que están incluidas en la red pero que no están asociadas a una subred, o bien la subred que incluye las direcciones IP no está asociada a un sitio de red. Esta alerta no aparecerá más que una vez en un período de ocho horas. A continuación se ofrece la información de alerta relevante y un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="1d6d6-p118">A Key Health Indicator (KHI) alert is raised, specifying a list of IP addresses that are present in your network but are either not associated with a subnet, or the subnet that includes the IP addresses is not associated with a network site. This alert will not be raised more than once within an 8 hour period. The relevant alert information and an example are as follows:</span></span><BR><span data-ttu-id="1d6d6-245"><STRONG>Origen:</STRONG> Servicio de directivas de ancho de banda (principal) de CS</span><span class="sxs-lookup"><span data-stu-id="1d6d6-245"><STRONG>Source:</STRONG> CS Bandwidth Policy Service (Core)</span></span><BR><span data-ttu-id="1d6d6-246"><STRONG>Número de evento:</STRONG> 36034</span><span class="sxs-lookup"><span data-stu-id="1d6d6-246"><STRONG>Event number:</STRONG> 36034</span></span><BR><span data-ttu-id="1d6d6-247"><STRONG>Nivel:</STRONG> 2</span><span class="sxs-lookup"><span data-stu-id="1d6d6-247"><STRONG>Level:</STRONG> 2</span></span><BR><span data-ttu-id="1d6d6-248"><STRONG>Descripción:</STRONG> Las subredes de las siguientes direcciones IP: &lt; la lista de direcciones IP &gt; no está configurada o las subredes no están asociadas a un sitio de red.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-248"><STRONG>Description:</STRONG> The subnets for the following IP Addresses: &lt;List of IP Addresses&gt; are either not configured or the subnets are not associated to a network site.</span></span><BR><span data-ttu-id="1d6d6-249"><STRONG>Causa:</STRONG> Las subredes de las direcciones IP correspondientes faltan en las opciones de configuración de red o las subredes no están asociadas a un sitio de red.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-249"><STRONG>Cause:</STRONG> The subnets for the corresponding IP addresses are missing from the network configuration settings or the subnets are not associated to a network site.</span></span><BR><span data-ttu-id="1d6d6-250"><STRONG>Solución:</STRONG> Agregue subredes correspondientes a la lista anterior de direcciones IP a las opciones de configuración de red y asocie cada subred a un sitio de red.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-250"><STRONG>Resolution:</STRONG> Add subnets corresponding to the preceding list of IP addresses into the network configuration settings and associate every subnet to a network site.</span></span><BR><span data-ttu-id="1d6d6-p119">Por ejemplo, si la lista de direcciones IP de la alerta especifica 10.121.248.226 y 10.121.249.20, estas direcciones IP no están asociadas a una subred o la subred a la que están asociadas no pertenece a un sitio de red. Si 10.121.248.0/24 y 10.121.249.0/24 son las subredes correspondientes a estas direcciones, este problema se puede resolver de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="1d6d6-p119">For example, if the IP address list in the alert specifies 10.121.248.226 and 10.121.249.20, either these IP addresses are not associated with a subnet, or the subnet that they are associated with does not belong to a network site. If 10.121.248.0/24 and 10.121.249.0/24 are the corresponding subnets for these addresses, you can resolve this issue as follows:</span></span> 
    > <OL>
    > <LI>
    > <P><span data-ttu-id="1d6d6-253">Asegúrese de que la dirección IP 10.121.248.226 está asociada a la subred 10.121.248.0/24 y la dirección IP 10.121.249.20 está asociada a la subred 10.121.249.0/24.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-253">Be sure that IP address 10.121.248.226 is associated with the 10.121.248.0/24 subnet and IP address 10.121.249.20 is associated with the 10.121.249.0/24 subnet.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="1d6d6-254">Asegúrese de que cada una de las subredes 10.121.248.0/24 y 10.121.249.0/24 está asociada a un sitio de red.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-254">Be sure that the 10.121.248.0/24 and 10.121.249.0/24 subnets are each associated with a network site.</span></span></P></LI></OL>

    
    </div>
    
    ### <a name="network-sites-and-associated-subnets-bandwidth-in-kbps"></a><span data-ttu-id="1d6d6-255">Sitios de red y subredes asociadas (ancho de banda en kbps)</span><span class="sxs-lookup"><span data-stu-id="1d6d6-255">Network Sites and Associated Subnets (Bandwidth in kbps)</span></span>
    
    <table>
    <colgroup>
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="1d6d6-256">Sitio de red</span><span class="sxs-lookup"><span data-stu-id="1d6d6-256">Network Site</span></span></th>
    <th><span data-ttu-id="1d6d6-257">Región de red</span><span class="sxs-lookup"><span data-stu-id="1d6d6-257">Network Region</span></span></th>
    <th><span data-ttu-id="1d6d6-258">Límite de ancho de banda</span><span class="sxs-lookup"><span data-stu-id="1d6d6-258">BW Limit</span></span></th>
    <th><span data-ttu-id="1d6d6-259">Límite de audio</span><span class="sxs-lookup"><span data-stu-id="1d6d6-259">Audio Limit</span></span></th>
    <th><span data-ttu-id="1d6d6-260">Límite de sesión de audio</span><span class="sxs-lookup"><span data-stu-id="1d6d6-260">Audio Session Limit</span></span></th>
    <th><span data-ttu-id="1d6d6-261">Límite de vídeo</span><span class="sxs-lookup"><span data-stu-id="1d6d6-261">Video Limit</span></span></th>
    <th><span data-ttu-id="1d6d6-262">Límite de sesión de vídeo</span><span class="sxs-lookup"><span data-stu-id="1d6d6-262">Video Session Limit</span></span></th>
    <th><span data-ttu-id="1d6d6-263">Subredes</span><span class="sxs-lookup"><span data-stu-id="1d6d6-263">Subnets</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="1d6d6-264">Albuquerque</span><span class="sxs-lookup"><span data-stu-id="1d6d6-264">Albuquerque</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-265">Norteamérica</span><span class="sxs-lookup"><span data-stu-id="1d6d6-265">North America</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-266">5,000</span><span class="sxs-lookup"><span data-stu-id="1d6d6-266">5,000</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-267">2,000</span><span class="sxs-lookup"><span data-stu-id="1d6d6-267">2,000</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-268">175</span><span class="sxs-lookup"><span data-stu-id="1d6d6-268">175</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-269">1.400</span><span class="sxs-lookup"><span data-stu-id="1d6d6-269">1,400</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-270">700</span><span class="sxs-lookup"><span data-stu-id="1d6d6-270">700</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-271">172.29.79.0/23, 157.57.215.0/25, 172.29.90.0/23, 172.29.80.0/24</span><span class="sxs-lookup"><span data-stu-id="1d6d6-271">172.29.79.0/23, 157.57.215.0/25, 172.29.90.0/23, 172.29.80.0/24</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="1d6d6-272">Reno</span><span class="sxs-lookup"><span data-stu-id="1d6d6-272">Reno</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-273">Norteamérica</span><span class="sxs-lookup"><span data-stu-id="1d6d6-273">North America</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-274">10 000</span><span class="sxs-lookup"><span data-stu-id="1d6d6-274">10,000</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-275">4.000</span><span class="sxs-lookup"><span data-stu-id="1d6d6-275">4,000</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-276">175</span><span class="sxs-lookup"><span data-stu-id="1d6d6-276">175</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-277">2.800</span><span class="sxs-lookup"><span data-stu-id="1d6d6-277">2,800</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-278">700</span><span class="sxs-lookup"><span data-stu-id="1d6d6-278">700</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-279">157.57.210.0/23, 172.28.151.128/25</span><span class="sxs-lookup"><span data-stu-id="1d6d6-279">157.57.210.0/23, 172.28.151.128/25</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="1d6d6-280">Portland</span><span class="sxs-lookup"><span data-stu-id="1d6d6-280">Portland</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-281">Norteamérica</span><span class="sxs-lookup"><span data-stu-id="1d6d6-281">North America</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-282">5,000</span><span class="sxs-lookup"><span data-stu-id="1d6d6-282">5,000</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-283">4.000</span><span class="sxs-lookup"><span data-stu-id="1d6d6-283">4,000</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-284">175</span><span class="sxs-lookup"><span data-stu-id="1d6d6-284">175</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-285">2.800</span><span class="sxs-lookup"><span data-stu-id="1d6d6-285">2,800</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-286">700</span><span class="sxs-lookup"><span data-stu-id="1d6d6-286">700</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-287">172.29.77.0/24 10.71.108.0/24, 157.57.208.0/23</span><span class="sxs-lookup"><span data-stu-id="1d6d6-287">172.29.77.0/24 10.71.108.0/24, 157.57.208.0/23</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="1d6d6-288">Nueva York</span><span class="sxs-lookup"><span data-stu-id="1d6d6-288">New York</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-289">Norteamérica</span><span class="sxs-lookup"><span data-stu-id="1d6d6-289">North America</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-290">(sin límite)</span><span class="sxs-lookup"><span data-stu-id="1d6d6-290">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-291">(sin límite)</span><span class="sxs-lookup"><span data-stu-id="1d6d6-291">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-292">(sin límite)</span><span class="sxs-lookup"><span data-stu-id="1d6d6-292">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-293">(sin límite)</span><span class="sxs-lookup"><span data-stu-id="1d6d6-293">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-294">(sin límite)</span><span class="sxs-lookup"><span data-stu-id="1d6d6-294">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-295">172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24</span><span class="sxs-lookup"><span data-stu-id="1d6d6-295">172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="1d6d6-296">Guadalajara</span><span class="sxs-lookup"><span data-stu-id="1d6d6-296">Chicago</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-297">Norteamérica</span><span class="sxs-lookup"><span data-stu-id="1d6d6-297">North America</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-298">(sin límite)</span><span class="sxs-lookup"><span data-stu-id="1d6d6-298">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-299">(sin límite)</span><span class="sxs-lookup"><span data-stu-id="1d6d6-299">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-300">(sin límite)</span><span class="sxs-lookup"><span data-stu-id="1d6d6-300">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-301">(sin límite)</span><span class="sxs-lookup"><span data-stu-id="1d6d6-301">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-302">(sin límite)</span><span class="sxs-lookup"><span data-stu-id="1d6d6-302">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-303">157.57.211.0/23, 172.28.152.128/25</span><span class="sxs-lookup"><span data-stu-id="1d6d6-303">157.57.211.0/23, 172.28.152.128/25</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="1d6d6-304">Detroit</span><span class="sxs-lookup"><span data-stu-id="1d6d6-304">Detroit</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-305">Norteamérica</span><span class="sxs-lookup"><span data-stu-id="1d6d6-305">North America</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-306">(sin límite)</span><span class="sxs-lookup"><span data-stu-id="1d6d6-306">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-307">(sin límite)</span><span class="sxs-lookup"><span data-stu-id="1d6d6-307">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-308">(sin límite)</span><span class="sxs-lookup"><span data-stu-id="1d6d6-308">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-309">(sin límite)</span><span class="sxs-lookup"><span data-stu-id="1d6d6-309">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-310">(sin límite)</span><span class="sxs-lookup"><span data-stu-id="1d6d6-310">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-311">172.29.78.0/24 10.71.109.0/24, 157.57.209.0/23</span><span class="sxs-lookup"><span data-stu-id="1d6d6-311">172.29.78.0/24 10.71.109.0/24, 157.57.209.0/23</span></span></p></td>
    </tr>
    </tbody>
    </table>


7.  <span data-ttu-id="1d6d6-312">En el control de admisión de llamadas de Lync Server, las conexiones entre regiones de red se denominan *vínculos de región*.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-312">In Lync Server call admission control, the connections between network regions are called *region links*.</span></span> <span data-ttu-id="1d6d6-313">Para cada vínculo de región, determine lo siguiente, tal como hizo para los sitios de red:</span><span class="sxs-lookup"><span data-stu-id="1d6d6-313">For each region link, determine the following, just as you did for the network sites:</span></span>
    
      - <span data-ttu-id="1d6d6-314">Límite general de ancho de banda que desea establecer para todas las sesiones simultáneas de audio.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-314">Overall bandwidth limit that you want to set for all concurrent audio sessions.</span></span> <span data-ttu-id="1d6d6-315">Si una nueva sesión de audio provoca que se supere este límite, Lync Server no permite que se inicie la sesión.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-315">If a new audio session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="1d6d6-p122">Límite de ancho de banda que desea establecer para cada sesión individual de audio. El límite predeterminado de ancho de banda para CAC es de 175 kbps, pero el administrador puede modificarlo.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-p122">Bandwidth limit that you want to set for each individual audio session. The default CAC bandwidth limit is 175 kbps, but it can be modified by the administrator.</span></span>
    
      - <span data-ttu-id="1d6d6-318">Límite general de ancho de banda que desea establecer para todas las sesiones simultáneas de vídeo.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-318">Overall bandwidth limit that you want to set for all concurrent video sessions.</span></span> <span data-ttu-id="1d6d6-319">Si una nueva sesión de vídeo provoca que se supere este límite, Lync Server no permite que se inicie la sesión.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-319">If a new video session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="1d6d6-p124">Límite de ancho de banda que desea establecer para cada sesión individual de vídeo. El límite predeterminado de ancho de banda para CAC es de 700 kbps, pero el administrador puede modificarlo.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-p124">Bandwidth limit that you want to set for each individual video session. The default CAC bandwidth limit is 700 kbps, but it can be modified by the administrator.</span></span>
    
    <span data-ttu-id="1d6d6-322">**Vínculos de región de red con límites de ancho de banda asociados**</span><span class="sxs-lookup"><span data-stu-id="1d6d6-322">**Network Region links with associated bandwidth limits**</span></span>
    
    <span data-ttu-id="1d6d6-323">![Ejemplo de limitaciones entre 3 regiones](images/Gg425827.25259afa-ee7c-4d26-bc41-92ba9cb56dec(OCS.15).jpg "Ejemplo de limitaciones entre 3 regiones")</span><span class="sxs-lookup"><span data-stu-id="1d6d6-323">![Example of Limitations between 3 Regions](images/Gg425827.25259afa-ee7c-4d26-bc41-92ba9cb56dec(OCS.15).jpg "Example of Limitations between 3 Regions")</span></span>  
    
    ### <a name="region-link-bandwidth-information-bandwidth-in-kbps"></a><span data-ttu-id="1d6d6-324">Información de ancho de banda de vínculos de región (ancho de banda en kbps)</span><span class="sxs-lookup"><span data-stu-id="1d6d6-324">Region Link Bandwidth Information (Bandwidth in kbps)</span></span>
    
    <table>
    <colgroup>
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="1d6d6-325">Nombre del vínculo de región</span><span class="sxs-lookup"><span data-stu-id="1d6d6-325">Region Link Name</span></span></th>
    <th><span data-ttu-id="1d6d6-326">Primera región</span><span class="sxs-lookup"><span data-stu-id="1d6d6-326">First Region</span></span></th>
    <th><span data-ttu-id="1d6d6-327">Segunda región</span><span class="sxs-lookup"><span data-stu-id="1d6d6-327">Second Region</span></span></th>
    <th><span data-ttu-id="1d6d6-328">Límite de ancho de banda</span><span class="sxs-lookup"><span data-stu-id="1d6d6-328">BW Limit</span></span></th>
    <th><span data-ttu-id="1d6d6-329">Límite de audio</span><span class="sxs-lookup"><span data-stu-id="1d6d6-329">Audio Limit</span></span></th>
    <th><span data-ttu-id="1d6d6-330">Límite de sesión de audio</span><span class="sxs-lookup"><span data-stu-id="1d6d6-330">Audio Session Limit</span></span></th>
    <th><span data-ttu-id="1d6d6-331">Límite de vídeo</span><span class="sxs-lookup"><span data-stu-id="1d6d6-331">Video Limit</span></span></th>
    <th><span data-ttu-id="1d6d6-332">Límite de sesión de vídeo</span><span class="sxs-lookup"><span data-stu-id="1d6d6-332">Video Session Limit</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="1d6d6-333">NA-EMEA-LINK</span><span class="sxs-lookup"><span data-stu-id="1d6d6-333">NA-EMEA-LINK</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-334">Norteamérica</span><span class="sxs-lookup"><span data-stu-id="1d6d6-334">North America</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-335">EMEA</span><span class="sxs-lookup"><span data-stu-id="1d6d6-335">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-336">50 000</span><span class="sxs-lookup"><span data-stu-id="1d6d6-336">50,000</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-337">20,000</span><span class="sxs-lookup"><span data-stu-id="1d6d6-337">20,000</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-338">175</span><span class="sxs-lookup"><span data-stu-id="1d6d6-338">175</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-339">14.000</span><span class="sxs-lookup"><span data-stu-id="1d6d6-339">14,000</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-340">700</span><span class="sxs-lookup"><span data-stu-id="1d6d6-340">700</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="1d6d6-341">EMEA-APAC-LINK</span><span class="sxs-lookup"><span data-stu-id="1d6d6-341">EMEA-APAC-LINK</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-342">EMEA</span><span class="sxs-lookup"><span data-stu-id="1d6d6-342">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-343">Pacífico</span><span class="sxs-lookup"><span data-stu-id="1d6d6-343">APAC</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-344">25 000</span><span class="sxs-lookup"><span data-stu-id="1d6d6-344">25,000</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-345">10 000</span><span class="sxs-lookup"><span data-stu-id="1d6d6-345">10,000</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-346">175</span><span class="sxs-lookup"><span data-stu-id="1d6d6-346">175</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-347">7.000</span><span class="sxs-lookup"><span data-stu-id="1d6d6-347">7,000</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-348">700</span><span class="sxs-lookup"><span data-stu-id="1d6d6-348">700</span></span></p></td>
    </tr>
    </tbody>
    </table>


8.  <span data-ttu-id="1d6d6-349">Definir una ruta entre cada par de regiones de red.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-349">Define a route between every pair of network regions.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="1d6d6-350">Se requieren dos vínculos para la ruta entre las regiones Norteamérica y APAC porque no existe ningún vínculo de región que las conecte directamente.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-350">Two links are required for the route between the North America and APAC regions because there is no region link that directly connects them.</span></span>

    
    </div>
    
    ### <a name="region-routes"></a><span data-ttu-id="1d6d6-351">Rutas de región</span><span class="sxs-lookup"><span data-stu-id="1d6d6-351">Region Routes</span></span>
    
    <table>
    <colgroup>
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="1d6d6-352">Nombre de la ruta de región</span><span class="sxs-lookup"><span data-stu-id="1d6d6-352">Region Route Name</span></span></th>
    <th><span data-ttu-id="1d6d6-353">Primera región</span><span class="sxs-lookup"><span data-stu-id="1d6d6-353">First Region</span></span></th>
    <th><span data-ttu-id="1d6d6-354">Segunda región</span><span class="sxs-lookup"><span data-stu-id="1d6d6-354">Second Region</span></span></th>
    <th><span data-ttu-id="1d6d6-355">Vínculos de región</span><span class="sxs-lookup"><span data-stu-id="1d6d6-355">Region Links</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="1d6d6-356">NA-EMEA-ROUTE</span><span class="sxs-lookup"><span data-stu-id="1d6d6-356">NA-EMEA-ROUTE</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-357">Norteamérica</span><span class="sxs-lookup"><span data-stu-id="1d6d6-357">North America</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-358">EMEA</span><span class="sxs-lookup"><span data-stu-id="1d6d6-358">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-359">NA-EMEA-LINK</span><span class="sxs-lookup"><span data-stu-id="1d6d6-359">NA-EMEA-LINK</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="1d6d6-360">EMEA-APAC-ROUTE</span><span class="sxs-lookup"><span data-stu-id="1d6d6-360">EMEA-APAC-ROUTE</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-361">EMEA</span><span class="sxs-lookup"><span data-stu-id="1d6d6-361">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-362">Pacífico</span><span class="sxs-lookup"><span data-stu-id="1d6d6-362">APAC</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-363">EMEA-APAC-LINK</span><span class="sxs-lookup"><span data-stu-id="1d6d6-363">EMEA-APAC-LINK</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="1d6d6-364">NA-APAC-ROUTE</span><span class="sxs-lookup"><span data-stu-id="1d6d6-364">NA-APAC-ROUTE</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-365">Norteamérica</span><span class="sxs-lookup"><span data-stu-id="1d6d6-365">North America</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-366">Pacífico</span><span class="sxs-lookup"><span data-stu-id="1d6d6-366">APAC</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-367">NA-EMEA-LINK, EMEA-APAC-LINK</span><span class="sxs-lookup"><span data-stu-id="1d6d6-367">NA-EMEA-LINK, EMEA-APAC-LINK</span></span></p></td>
    </tr>
    </tbody>
    </table>


9.  <span data-ttu-id="1d6d6-368">Para cada par de sitios de red que estén conectados directamente por un solo vínculo (denominado vínculo *entre sitios*), determine lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1d6d6-368">For every pair of network sites that are directly connected by a single link (called an *inter-site* link), determine the following:</span></span>
    
      - <span data-ttu-id="1d6d6-369">Límite general de ancho de banda que desea establecer para todas las sesiones simultáneas de audio.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-369">Overall bandwidth limit that you want to set for all concurrent audio sessions.</span></span> <span data-ttu-id="1d6d6-370">Si una nueva sesión de audio provoca que se supere este límite, Lync Server no permite que se inicie la sesión.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-370">If a new audio session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="1d6d6-p126">Límite de ancho de banda que desea establecer para cada sesión individual de audio. El límite predeterminado de ancho de banda para CAC es de 175 kbps, pero el administrador puede modificarlo.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-p126">Bandwidth limit that you want to set for each individual audio session. The default CAC bandwidth limit is 175 kbps, but it can be modified by the administrator.</span></span>
    
      - <span data-ttu-id="1d6d6-373">Límite general de ancho de banda que desea establecer para todas las sesiones simultáneas de vídeo.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-373">Overall bandwidth limit that you want to set for all concurrent video sessions.</span></span> <span data-ttu-id="1d6d6-374">Si una nueva sesión de vídeo provoca que se supere este límite, Lync Server no permite que se inicie la sesión.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-374">If a new video session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="1d6d6-p128">Límite de ancho de banda que desea establecer para cada sesión individual de vídeo. El límite predeterminado de ancho de banda para CAC es de 700 kbps, pero el administrador puede modificarlo.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-p128">Bandwidth limit that you want to set for each individual video session. The default CAC bandwidth limit is 700 kbps, but it can be modified by the administrator.</span></span>
    
    <span data-ttu-id="1d6d6-377">**Región de red para CAC Norteamérica con indicación de las capacidades de ancho de banda y los límites de ancho de banda del vínculo entre sitios entre Reno y Albuquerque**</span><span class="sxs-lookup"><span data-stu-id="1d6d6-377">**CAC network region North America showing the bandwidth capacities and bandwidth limits for the inter-site link between Reno and Albuquerque**</span></span>
    
    <span data-ttu-id="1d6d6-378">![Ejemplo de sitios de red restringidos por el ancho de banda de WAN](images/Gg425827.063e5e1d-b6c8-4e8c-98db-c227c78f671d(OCS.15).jpg "Ejemplo de sitios de red restringidos por el ancho de banda de WAN")</span><span class="sxs-lookup"><span data-stu-id="1d6d6-378">![Network Sites Constrained by WAN Bandwidth example](images/Gg425827.063e5e1d-b6c8-4e8c-98db-c227c78f671d(OCS.15).jpg "Network Sites Constrained by WAN Bandwidth example")</span></span>  
    
    ### <a name="bandwidth-information-for-an-inter-site-link-between-two-network-sites-bandwidth-in-kbps"></a><span data-ttu-id="1d6d6-379">Información de ancho de banda de un vínculo entre sitios entre dos sitios de red (ancho de banda en kbps)</span><span class="sxs-lookup"><span data-stu-id="1d6d6-379">Bandwidth Information for an Inter-Site Link between Two Network Sites (Bandwidth in kbps)</span></span>
    
    <table>
    <colgroup>
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="1d6d6-380">Nombre del vínculo entre sitios</span><span class="sxs-lookup"><span data-stu-id="1d6d6-380">Inter-Site Link Name</span></span></th>
    <th><span data-ttu-id="1d6d6-381">Primer sitio</span><span class="sxs-lookup"><span data-stu-id="1d6d6-381">First Site</span></span></th>
    <th><span data-ttu-id="1d6d6-382">Segundo sitio</span><span class="sxs-lookup"><span data-stu-id="1d6d6-382">Second Site</span></span></th>
    <th><span data-ttu-id="1d6d6-383">Límite de ancho de banda</span><span class="sxs-lookup"><span data-stu-id="1d6d6-383">BW Limit</span></span></th>
    <th><span data-ttu-id="1d6d6-384">Límite de audio</span><span class="sxs-lookup"><span data-stu-id="1d6d6-384">Audio Limit</span></span></th>
    <th><span data-ttu-id="1d6d6-385">Límite de sesión de audio</span><span class="sxs-lookup"><span data-stu-id="1d6d6-385">Audio Session Limit</span></span></th>
    <th><span data-ttu-id="1d6d6-386">Límite de vídeo</span><span class="sxs-lookup"><span data-stu-id="1d6d6-386">Video Limit</span></span></th>
    <th><span data-ttu-id="1d6d6-387">Límite de sesión de vídeo</span><span class="sxs-lookup"><span data-stu-id="1d6d6-387">Video Session Limit</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="1d6d6-388">Reno-Albu-intersite-Link</span><span class="sxs-lookup"><span data-stu-id="1d6d6-388">Reno-Albu-Intersite-Link</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-389">Reno</span><span class="sxs-lookup"><span data-stu-id="1d6d6-389">Reno</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-390">Albuquerque</span><span class="sxs-lookup"><span data-stu-id="1d6d6-390">Albuquerque</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-391">20,000</span><span class="sxs-lookup"><span data-stu-id="1d6d6-391">20,000</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-392">12.000</span><span class="sxs-lookup"><span data-stu-id="1d6d6-392">12,000</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-393">175</span><span class="sxs-lookup"><span data-stu-id="1d6d6-393">175</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-394">5,000</span><span class="sxs-lookup"><span data-stu-id="1d6d6-394">5,000</span></span></p></td>
    <td><p><span data-ttu-id="1d6d6-395">700</span><span class="sxs-lookup"><span data-stu-id="1d6d6-395">700</span></span></p></td>
    </tr>
    </tbody>
    </table>


<div>

## <a name="next-steps"></a><span data-ttu-id="1d6d6-396">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="1d6d6-396">Next Steps</span></span>

<span data-ttu-id="1d6d6-397">Una vez recopilada la información necesaria, puede realizar una implementación de CAC mediante el shell de administración de Lync Server o el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-397">After you have gathered the required information, you can perform CAC deployment either by using the Lync Server Management Shell or Lync Server Control Panel.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="1d6d6-398">Aunque puede realizar la mayoría de las tareas de configuración de red mediante el panel de control de Lync Server, para crear subredes y vínculos entre sitios, debe usar el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-398">Although you can perform most network configuration tasks by using Lync Server Control Panel, to create subnets and intersite links, you must use Lync Server Management Shell.</span></span> <span data-ttu-id="1d6d6-399">Para obtener más información, consulte la documentación del shell de administración de Lync Server para el cmdlet <STRONG>New-CsNetworkSubnet</STRONG> y el cmdlet <STRONG>New-CsNetworkIntersitePolicy</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="1d6d6-399">For details, see the Lync Server Management Shell documentation for the <STRONG>New-CsNetworkSubnet</STRONG> cmdlet and the <STRONG>New-CsNetworkIntersitePolicy</STRONG> cmdlet.</span></span>



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

