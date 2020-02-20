---
title: Ejemplo de recopilación de los requisitos para el control de admisión de llamadas
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
ms.openlocfilehash: 64731e324b93cb4baff85f36ad342016d3b68738
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146833"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="example-gathering-your-requirements-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="10469-102">Ejemplo: recopilar los requisitos para el control de admisión de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="10469-102">Example: Gathering your requirements for call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="10469-103">_**Última modificación del tema:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="10469-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="10469-p101">Este ejemplo muestra cómo planear e implementar el control de admisión de llamadas (CAC). De forma general, esto consta de las siguientes actividades:</span><span class="sxs-lookup"><span data-stu-id="10469-p101">This example shows you how to plan for and implement call admission control (CAC). At a high level, this consists of the following activities:</span></span>

1.  <span data-ttu-id="10469-106">Identificar todos los concentradores de red y redes troncales (llamados *regiones de red*).</span><span class="sxs-lookup"><span data-stu-id="10469-106">Identify all of your network hubs and backbones (known as *network regions*).</span></span>

2.  <span data-ttu-id="10469-107">Identificar el sitio central de Lync Server que va a administrar el CAC para cada región de red.</span><span class="sxs-lookup"><span data-stu-id="10469-107">Identify the Lync Server central site that will manage CAC for each network region.</span></span>

3.  <span data-ttu-id="10469-108">Identificar y definir los *sitios de red* que están conectados a cada región de red.</span><span class="sxs-lookup"><span data-stu-id="10469-108">Identify and define the *network sites* that are connected to each network region.</span></span>

4.  <span data-ttu-id="10469-109">Para cada sitio de red cuya conexión a la WAN tiene restringido el ancho de banda, describa la capacidad de ancho de banda de la conexión WAN y los límites de ancho de banda que el administrador de red ha configurado para el tráfico de medios de Lync Server, si procede.</span><span class="sxs-lookup"><span data-stu-id="10469-109">For each network site whose connection to the WAN is bandwidth-constrained, describe the bandwidth capacity of the WAN connection and the bandwidth limits that to the network administrator has set for Lync Server media traffic, if applicable.</span></span> <span data-ttu-id="10469-110">No es necesario incluir sitios cuya conexión a la red WAN no tiene ancho de banda restringido.</span><span class="sxs-lookup"><span data-stu-id="10469-110">You do not need to include sites whose connection to the WAN is not bandwidth-constrained.</span></span>

5.  <span data-ttu-id="10469-111">Asociar cada subred de la red a un sitio de red.</span><span class="sxs-lookup"><span data-stu-id="10469-111">Associate each subnet in your network with a network site.</span></span>

6.  <span data-ttu-id="10469-112">Asignar los vínculos entre las regiones de red.</span><span class="sxs-lookup"><span data-stu-id="10469-112">Map the links between the network regions.</span></span> <span data-ttu-id="10469-113">Para cada vínculo, describa la capacidad de ancho de banda y los límites que el administrador de red haya colocado en el tráfico de medios de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="10469-113">For each link, describe its bandwidth capacity and any limits that the network administrator has placed on Lync Server media traffic.</span></span>

7.  <span data-ttu-id="10469-114">Definir una ruta entre cada par de regiones de red.</span><span class="sxs-lookup"><span data-stu-id="10469-114">Define a route between every pair of network regions.</span></span>

<div>

## <a name="gather-the-required-information"></a><span data-ttu-id="10469-115">Recopilar la información necesaria</span><span class="sxs-lookup"><span data-stu-id="10469-115">Gather the Required Information</span></span>

<span data-ttu-id="10469-116">Para preparar el control de admisión de llamadas, recopile la información descrita en los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="10469-116">To prepare for call admission control, gather the information described in the following steps:</span></span>

1.  <span data-ttu-id="10469-p104">Identificar las regiones de red. Una región de red representa una red troncal de red o un concentrador de red.</span><span class="sxs-lookup"><span data-stu-id="10469-p104">Identify your network regions. A network region represents a network backbone or a network hub.</span></span>
    
    <span data-ttu-id="10469-p105">Una red troncal de red o un concentrador de red forma parte de una infraestructura de red informática que interconecta diversas partes de red, que proporciona una ruta de acceso para el intercambio de información entre distintas redes LAN o subredes. Una red troncal puede asociar diversas redes, desde una ubicación pequeña a una amplia zona geográfica. La capacidad de la red troncal suele ser mayor que la de las redes conectadas a ella.</span><span class="sxs-lookup"><span data-stu-id="10469-p105">A network backbone or a network hub is a part of computer network infrastructure that interconnects various pieces of network, providing a path for the exchange of information between different LANs or subnets. A backbone can tie together diverse networks, from a small location to a wide geographic area. The backbone's capacity is typically greater than that of the networks connected to it.</span></span>
    
    <span data-ttu-id="10469-p106">Nuestra topología de ejemplo tiene tres regiones de red: Norteamérica, EMEA y APAC. Una región de red incluye una colección de sitios de red. Trabaje con el administrador de la red para definir las regiones de red de su empresa.</span><span class="sxs-lookup"><span data-stu-id="10469-p106">Our example topology has three network regions: North America, EMEA, and APAC. A network region contains a collection of network sites. Work with your network administrator to define the network regions for your enterprise.</span></span>

2.  <span data-ttu-id="10469-125">Identificar cada sitio central asociado a la región de red.</span><span class="sxs-lookup"><span data-stu-id="10469-125">Identify each network region’s associated central site.</span></span> <span data-ttu-id="10469-126">Un sitio central contiene al menos un servidor front-end y es la implementación de Lync Server que administrará el CAC para todo el tráfico de medios que pasa a través de la conexión WAN de la región de red.</span><span class="sxs-lookup"><span data-stu-id="10469-126">A central site contains at least one Front End Server and is the Lync Server deployment that will manage CAC for all media traffic that passes through the network region’s WAN connection.</span></span>
    
    <span data-ttu-id="10469-127">**Red de empresa de ejemplo dividida en tres regiones de red**</span><span class="sxs-lookup"><span data-stu-id="10469-127">**An example enterprise network divided into three network regions**</span></span>
    
    <span data-ttu-id="10469-128">![Ejemplo de topología de red con 3 regiones de red](images/Gg425827.08937347-250f-488f-ba5f-c256e6afcd8b(OCS.15).jpg "Ejemplo de topología de red con 3 regiones de red")</span><span class="sxs-lookup"><span data-stu-id="10469-128">![Network Topology Example with 3 Network Regions](images/Gg425827.08937347-250f-488f-ba5f-c256e6afcd8b(OCS.15).jpg "Network Topology Example with 3 Network Regions")</span></span>  
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="10469-129">Una red de conmutación de etiquetas multiprotocolo (MPLS) debe representarse como una región de red en la que cada ubicación geográfica tiene un sitio de red correspondiente.</span><span class="sxs-lookup"><span data-stu-id="10469-129">A Multiprotocol Label Switching (MPLS) network should be represented as a network region in which each geographic location has a corresponding network site.</span></span> <span data-ttu-id="10469-130">Para obtener más información, consulte el tema "<A href="lync-server-2013-call-admission-control-on-an-mpls-network.md">control de admisión de llamadas en una red MPLS con Lync Server 2013</A>" en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="10469-130">For details, see the “<A href="lync-server-2013-call-admission-control-on-an-mpls-network.md">Call admission control on an MPLS network with Lync Server 2013</A>” topic in the Planning documentation.</span></span>

    
    </div>
    
    <span data-ttu-id="10469-131">En la topología de red de ejemplo anterior, hay tres regiones de red, cada una con un sitio central de Lync Server que administra el CAC.</span><span class="sxs-lookup"><span data-stu-id="10469-131">In the preceding example network topology, there are three network regions, each with a Lync Server central site that manages CAC.</span></span> <span data-ttu-id="10469-132">El sitio central adecuado para una región de red se elige por la proximidad geográfica.</span><span class="sxs-lookup"><span data-stu-id="10469-132">The appropriate central site for a network region is chosen by the geographic vicinity.</span></span> <span data-ttu-id="10469-133">Como el tráfico de medios será mayor dentro de las regiones de red, la propiedad por proximidad geográfica lo hace independiente y seguirá siendo funcional aunque otros sitios centrales dejen de estar disponibles.</span><span class="sxs-lookup"><span data-stu-id="10469-133">Because media traffic will be heaviest within network regions, the ownership by geographic vicinity makes it self-contained and will continue to be functional even if other central sites become unavailable.</span></span>
    
    <span data-ttu-id="10469-134">En este ejemplo, una implementación de Lync Server llamada Chicago es el sitio central de la región de Norteamérica.</span><span class="sxs-lookup"><span data-stu-id="10469-134">In this example, a Lync Server deployment named Chicago is the central site for the North America region.</span></span>
    
    <span data-ttu-id="10469-135">Todos los usuarios de Lync de Norteamérica están hospedados en los servidores de la implementación de Chicago.</span><span class="sxs-lookup"><span data-stu-id="10469-135">All Lync users in North America are homed on servers in the Chicago deployment.</span></span> <span data-ttu-id="10469-136">En la tabla siguiente se muestran los sitios centrales de las tres regiones de red.</span><span class="sxs-lookup"><span data-stu-id="10469-136">The following table shows central sites for all three network regions.</span></span>
    
    ### <a name="network-regions-and-their-associated-central-sites"></a><span data-ttu-id="10469-137">Regiones de red y sus sitios centrales asociados</span><span class="sxs-lookup"><span data-stu-id="10469-137">Network Regions and their Associated Central Sites</span></span>
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="10469-138">Región de red</span><span class="sxs-lookup"><span data-stu-id="10469-138">Network Region</span></span></th>
    <th><span data-ttu-id="10469-139">Sitio central</span><span class="sxs-lookup"><span data-stu-id="10469-139">Central Site</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="10469-140">Norteamérica</span><span class="sxs-lookup"><span data-stu-id="10469-140">North America</span></span></p></td>
    <td><p><span data-ttu-id="10469-141">Guadalajara</span><span class="sxs-lookup"><span data-stu-id="10469-141">Chicago</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="10469-142">EMEA</span><span class="sxs-lookup"><span data-stu-id="10469-142">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="10469-143">México</span><span class="sxs-lookup"><span data-stu-id="10469-143">London</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="10469-144">Pacífico</span><span class="sxs-lookup"><span data-stu-id="10469-144">APAC</span></span></p></td>
    <td><p><span data-ttu-id="10469-145">Beijing</span><span class="sxs-lookup"><span data-stu-id="10469-145">Beijing</span></span></p></td>
    </tr>
    </tbody>
    </table>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="10469-146">Según la topología de Lync Server, el mismo sitio central puede asignarse a varias regiones de red.</span><span class="sxs-lookup"><span data-stu-id="10469-146">Depending on your Lync Server topology, the same central site can be assigned to multiple network regions.</span></span>

    
    </div>

3.  <span data-ttu-id="10469-p111">En cada región de red, identifique todos los sitios de red (oficinas o ubicaciones) cuyas conexiones WAN no tienen ancho de banda restringido. Como estos sitios no tienen ancho de banda restringido, no es necesario aplicarles directivas de ancho de banda de CAC.</span><span class="sxs-lookup"><span data-stu-id="10469-p111">For each network region, identify all of the network sites (offices or locations) whose WAN connections are not bandwidth-constrained. Because these sites are not bandwidth constrained, you do not need to apply CAC bandwidth policies to them.</span></span>
    
    <span data-ttu-id="10469-149">En el ejemplo que se muestra en la siguiente tabla, tres sitios de red no tienen vínculos WAN de ancho de banda restringido: Nueva York, Chicago y Detroit.</span><span class="sxs-lookup"><span data-stu-id="10469-149">In the example shown in the following table, three network sites do not have bandwidth-constrained WAN links: New York, Chicago, and Detroit.</span></span>
    
    ### <a name="network-sites-not-constrained-by-wan-bandwidth"></a><span data-ttu-id="10469-150">Sitios de red no restringidos por el ancho de banda de WAN</span><span class="sxs-lookup"><span data-stu-id="10469-150">Network Sites not Constrained by WAN Bandwidth</span></span>
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="10469-151">Sitio de red</span><span class="sxs-lookup"><span data-stu-id="10469-151">Network Site</span></span></th>
    <th><span data-ttu-id="10469-152">Región de red</span><span class="sxs-lookup"><span data-stu-id="10469-152">Network Region</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="10469-153">Nueva York</span><span class="sxs-lookup"><span data-stu-id="10469-153">New York</span></span></p></td>
    <td><p><span data-ttu-id="10469-154">Norteamérica</span><span class="sxs-lookup"><span data-stu-id="10469-154">North America</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="10469-155">Guadalajara</span><span class="sxs-lookup"><span data-stu-id="10469-155">Chicago</span></span></p></td>
    <td><p><span data-ttu-id="10469-156">Norteamérica</span><span class="sxs-lookup"><span data-stu-id="10469-156">North America</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="10469-157">Detroit</span><span class="sxs-lookup"><span data-stu-id="10469-157">Detroit</span></span></p></td>
    <td><p><span data-ttu-id="10469-158">Norteamérica</span><span class="sxs-lookup"><span data-stu-id="10469-158">North America</span></span></p></td>
    </tr>
    </tbody>
    </table>


4.  <span data-ttu-id="10469-159">En cada región de red, identifique todos los sitios de red que se conectan a la región de red a través de vínculos WAN de ancho de banda restringido.</span><span class="sxs-lookup"><span data-stu-id="10469-159">For each network region, identify all of the network sites that connect to the network region through bandwidth-constrained WAN links.</span></span>
    
    <span data-ttu-id="10469-160">Para asegurar la calidad de audio y vídeo, se recomienda que estos sitios de red de ancho de banda restringido tengan las redes WAN supervisadas y directivas de ancho de banda del CAC que limiten el flujo del tráfico de medios (voz o vídeo) hacia la región de red y desde ella.</span><span class="sxs-lookup"><span data-stu-id="10469-160">To help ensure audio and video quality, we recommend that these bandwidth-constrained network sites have their WANs monitored and CAC bandwidth policies that limit media (voice or video) traffic flow to and from the network region.</span></span>
    
    <span data-ttu-id="10469-161">En el ejemplo que se muestra en la siguiente tabla, hay tres sitios de red que están restringidos por el ancho de banda de WAN: Portland, Reno y Albuquerque.</span><span class="sxs-lookup"><span data-stu-id="10469-161">In the example shown in the following table, there are three network sites that are constrained by WAN bandwidth: Portland, Reno and Albuquerque.</span></span>
    
    ### <a name="network-sites-constrained-by-wan-bandwidth"></a><span data-ttu-id="10469-162">Sitios de red restringidos por el ancho de banda de WAN</span><span class="sxs-lookup"><span data-stu-id="10469-162">Network Sites Constrained by WAN Bandwidth</span></span>
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="10469-163">Sitio de red</span><span class="sxs-lookup"><span data-stu-id="10469-163">Network Site</span></span></th>
    <th><span data-ttu-id="10469-164">Región de red</span><span class="sxs-lookup"><span data-stu-id="10469-164">Network Region</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="10469-165">Albuquerque</span><span class="sxs-lookup"><span data-stu-id="10469-165">Albuquerque</span></span></p></td>
    <td><p><span data-ttu-id="10469-166">Norteamérica</span><span class="sxs-lookup"><span data-stu-id="10469-166">North America</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="10469-167">Reno</span><span class="sxs-lookup"><span data-stu-id="10469-167">Reno</span></span></p></td>
    <td><p><span data-ttu-id="10469-168">Norteamérica</span><span class="sxs-lookup"><span data-stu-id="10469-168">North America</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="10469-169">Portland</span><span class="sxs-lookup"><span data-stu-id="10469-169">Portland</span></span></p></td>
    <td><p><span data-ttu-id="10469-170">Norteamérica</span><span class="sxs-lookup"><span data-stu-id="10469-170">North America</span></span></p></td>
    </tr>
    </tbody>
    </table>
    
    <span data-ttu-id="10469-171">**Región de red para CAC Norteamérica con tres sitios de red que no están restringidos por el ancho de banda (Chicago, Nueva York y Detroit) y tres sitios de red que están restringidos por el ancho de banda de WAN (Portland, Reno y Albuquerque)**</span><span class="sxs-lookup"><span data-stu-id="10469-171">**CAC network region North America with three network sites that are unconstrained by bandwidth (Chicago, New York, and Detroit) and three network sites that are constrained by WAN bandwidth (Portland, Reno, and Albuquerque)**</span></span>
    
    <span data-ttu-id="10469-172">![Sitios de red de ejemplo restringidos por el ancho de banda de WAN](images/Gg425827.d9d1f231-db4d-4dd7-8fbc-eb0b6d1e705d(OCS.15).jpg "Sitios de red de ejemplo restringidos por el ancho de banda de WAN")</span><span class="sxs-lookup"><span data-stu-id="10469-172">![Example network sites constrained by WAN bandwidth](images/Gg425827.d9d1f231-db4d-4dd7-8fbc-eb0b6d1e705d(OCS.15).jpg "Example network sites constrained by WAN bandwidth")</span></span>  

5.  <span data-ttu-id="10469-173">Para cada vínculo WAN de ancho de banda restringido, determine lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="10469-173">For each bandwidth-constrained WAN link, determine the following:</span></span>
    
      - <span data-ttu-id="10469-174">Límite general de ancho de banda que desea establecer para todas las sesiones simultáneas de audio.</span><span class="sxs-lookup"><span data-stu-id="10469-174">Overall bandwidth limit that you want to set for all concurrent audio sessions.</span></span> <span data-ttu-id="10469-175">Si una nueva sesión de audio provoca que se supere este límite, Lync Server no permite que se inicie la sesión.</span><span class="sxs-lookup"><span data-stu-id="10469-175">If a new audio session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="10469-p113">Límite de ancho de banda que desea establecer para cada sesión individual de audio. El límite predeterminado de ancho de banda para CAC es de 175 kbps, pero el administrador puede modificarlo.</span><span class="sxs-lookup"><span data-stu-id="10469-p113">Bandwidth limit that you want to set for each individual audio session. The default CAC bandwidth limit is 175 kbps, but it can be modified by the administrator.</span></span>
    
      - <span data-ttu-id="10469-178">Límite general de ancho de banda que desea establecer para todas las sesiones simultáneas de vídeo.</span><span class="sxs-lookup"><span data-stu-id="10469-178">Overall bandwidth limit that you want to set for all concurrent video sessions.</span></span> <span data-ttu-id="10469-179">Si una nueva sesión de vídeo provoca que se supere este límite, Lync Server no permite que se inicie la sesión.</span><span class="sxs-lookup"><span data-stu-id="10469-179">If a new video session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="10469-p115">Límite de ancho de banda que desea establecer para cada sesión individual de vídeo. El límite predeterminado de ancho de banda para CAC es de 700 kbps, pero el administrador puede modificarlo.</span><span class="sxs-lookup"><span data-stu-id="10469-p115">Bandwidth limit that you want to set for each individual video session. The default CAC bandwidth limit is 700 kbps, but it can be modified by the administrator.</span></span>
    
    ### <a name="network-sites-with-wan-bandwidth-constraint-information-bandwidth-in-kbps"></a><span data-ttu-id="10469-182">Sitios de red con información de restricción de ancho de banda de WAN (ancho de banda en kbps)</span><span class="sxs-lookup"><span data-stu-id="10469-182">Network Sites with WAN Bandwidth Constraint Information (Bandwidth in kbps)</span></span>
    
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
    <th><span data-ttu-id="10469-183">Sitio de red</span><span class="sxs-lookup"><span data-stu-id="10469-183">Network Site</span></span></th>
    <th><span data-ttu-id="10469-184">Región de red</span><span class="sxs-lookup"><span data-stu-id="10469-184">Network Region</span></span></th>
    <th><span data-ttu-id="10469-185">Límite de ancho de banda</span><span class="sxs-lookup"><span data-stu-id="10469-185">BW Limit</span></span></th>
    <th><span data-ttu-id="10469-186">Límite de audio</span><span class="sxs-lookup"><span data-stu-id="10469-186">Audio Limit</span></span></th>
    <th><span data-ttu-id="10469-187">Límite de sesión de audio</span><span class="sxs-lookup"><span data-stu-id="10469-187">Audio Session Limit</span></span></th>
    <th><span data-ttu-id="10469-188">Límite de vídeo</span><span class="sxs-lookup"><span data-stu-id="10469-188">Video Limit</span></span></th>
    <th><span data-ttu-id="10469-189">Límite de sesión de vídeo</span><span class="sxs-lookup"><span data-stu-id="10469-189">Video Session Limit</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="10469-190">Albuquerque</span><span class="sxs-lookup"><span data-stu-id="10469-190">Albuquerque</span></span></p></td>
    <td><p><span data-ttu-id="10469-191">Norteamérica</span><span class="sxs-lookup"><span data-stu-id="10469-191">North America</span></span></p></td>
    <td><p><span data-ttu-id="10469-192">5,000</span><span class="sxs-lookup"><span data-stu-id="10469-192">5,000</span></span></p></td>
    <td><p><span data-ttu-id="10469-193">2,000</span><span class="sxs-lookup"><span data-stu-id="10469-193">2,000</span></span></p></td>
    <td><p><span data-ttu-id="10469-194">175</span><span class="sxs-lookup"><span data-stu-id="10469-194">175</span></span></p></td>
    <td><p><span data-ttu-id="10469-195">1.400</span><span class="sxs-lookup"><span data-stu-id="10469-195">1,400</span></span></p></td>
    <td><p><span data-ttu-id="10469-196">700</span><span class="sxs-lookup"><span data-stu-id="10469-196">700</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="10469-197">Reno</span><span class="sxs-lookup"><span data-stu-id="10469-197">Reno</span></span></p></td>
    <td><p><span data-ttu-id="10469-198">Norteamérica</span><span class="sxs-lookup"><span data-stu-id="10469-198">North America</span></span></p></td>
    <td><p><span data-ttu-id="10469-199">10 000</span><span class="sxs-lookup"><span data-stu-id="10469-199">10,000</span></span></p></td>
    <td><p><span data-ttu-id="10469-200">4.000</span><span class="sxs-lookup"><span data-stu-id="10469-200">4,000</span></span></p></td>
    <td><p><span data-ttu-id="10469-201">175</span><span class="sxs-lookup"><span data-stu-id="10469-201">175</span></span></p></td>
    <td><p><span data-ttu-id="10469-202">2.800</span><span class="sxs-lookup"><span data-stu-id="10469-202">2,800</span></span></p></td>
    <td><p><span data-ttu-id="10469-203">700</span><span class="sxs-lookup"><span data-stu-id="10469-203">700</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="10469-204">Portland</span><span class="sxs-lookup"><span data-stu-id="10469-204">Portland</span></span></p></td>
    <td><p><span data-ttu-id="10469-205">Norteamérica</span><span class="sxs-lookup"><span data-stu-id="10469-205">North America</span></span></p></td>
    <td><p><span data-ttu-id="10469-206">5,000</span><span class="sxs-lookup"><span data-stu-id="10469-206">5,000</span></span></p></td>
    <td><p><span data-ttu-id="10469-207">4.000</span><span class="sxs-lookup"><span data-stu-id="10469-207">4,000</span></span></p></td>
    <td><p><span data-ttu-id="10469-208">175</span><span class="sxs-lookup"><span data-stu-id="10469-208">175</span></span></p></td>
    <td><p><span data-ttu-id="10469-209">2.800</span><span class="sxs-lookup"><span data-stu-id="10469-209">2,800</span></span></p></td>
    <td><p><span data-ttu-id="10469-210">700</span><span class="sxs-lookup"><span data-stu-id="10469-210">700</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="10469-211">Nueva York</span><span class="sxs-lookup"><span data-stu-id="10469-211">New York</span></span></p></td>
    <td><p><span data-ttu-id="10469-212">Norteamérica</span><span class="sxs-lookup"><span data-stu-id="10469-212">North America</span></span></p></td>
    <td><p><span data-ttu-id="10469-213">(sin límite)</span><span class="sxs-lookup"><span data-stu-id="10469-213">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="10469-214">(sin límite)</span><span class="sxs-lookup"><span data-stu-id="10469-214">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="10469-215">(sin límite)</span><span class="sxs-lookup"><span data-stu-id="10469-215">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="10469-216">(sin límite)</span><span class="sxs-lookup"><span data-stu-id="10469-216">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="10469-217">(sin límite)</span><span class="sxs-lookup"><span data-stu-id="10469-217">(no limit)</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="10469-218">Guadalajara</span><span class="sxs-lookup"><span data-stu-id="10469-218">Chicago</span></span></p></td>
    <td><p><span data-ttu-id="10469-219">Norteamérica</span><span class="sxs-lookup"><span data-stu-id="10469-219">North America</span></span></p></td>
    <td><p><span data-ttu-id="10469-220">(sin límite)</span><span class="sxs-lookup"><span data-stu-id="10469-220">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="10469-221">(sin límite)</span><span class="sxs-lookup"><span data-stu-id="10469-221">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="10469-222">(sin límite)</span><span class="sxs-lookup"><span data-stu-id="10469-222">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="10469-223">(sin límite)</span><span class="sxs-lookup"><span data-stu-id="10469-223">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="10469-224">(sin límite)</span><span class="sxs-lookup"><span data-stu-id="10469-224">(no limit)</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="10469-225">Detroit</span><span class="sxs-lookup"><span data-stu-id="10469-225">Detroit</span></span></p></td>
    <td><p><span data-ttu-id="10469-226">Norteamérica</span><span class="sxs-lookup"><span data-stu-id="10469-226">North America</span></span></p></td>
    <td><p><span data-ttu-id="10469-227">(sin límite)</span><span class="sxs-lookup"><span data-stu-id="10469-227">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="10469-228">(sin límite)</span><span class="sxs-lookup"><span data-stu-id="10469-228">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="10469-229">(sin límite)</span><span class="sxs-lookup"><span data-stu-id="10469-229">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="10469-230">(sin límite)</span><span class="sxs-lookup"><span data-stu-id="10469-230">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="10469-231">(sin límite)</span><span class="sxs-lookup"><span data-stu-id="10469-231">(no limit)</span></span></p></td>
    </tr>
    </tbody>
    </table>


6.  <span data-ttu-id="10469-232">Para cada subred de la red, especifique el sitio de red asociado.</span><span class="sxs-lookup"><span data-stu-id="10469-232">For every subnet in your network, specify its associated network site.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="10469-p116">Cada subred de la red debe estar asociada a un sitio de red, aunque el sitio de red no esté restringido por el ancho de banda. Esto se debe a que el control de admisión de llamadas usa la información de la subred para determinar el sitio de red en que está situado un extremo. Cuando se determinan las ubicaciones de ambas partes de la sesión, el control de admisión de llamadas puede determinar si existe suficiente ancho de banda para establecer una llamada. Cuando se establece una sesión a través de un vínculo que no tiene límites de ancho de banda, se genera una alerta.</span><span class="sxs-lookup"><span data-stu-id="10469-p116">Every subnet in your network must be associated with a network site, even if the network site is not bandwidth constrained. This is because call admission control uses subnet information to determine at which network site an endpoint is located. When the locations of both parties in the session are determined, call admission control can determine if there is sufficient bandwidth to establish a call. When a session is established over a link that has no bandwidth limits, an alert is generated.</span></span><BR><span data-ttu-id="10469-237">Si implementa servidores perimetrales de audio/vídeo, las direcciones IP públicas de cada servidor perimetral deben estar asociadas al sitio de red en el que se implementa el servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="10469-237">If you deploy Audio/Video Edge Servers, the public IP addresses of each Edge Server must be associated with the network site where the Edge Server is deployed.</span></span> <span data-ttu-id="10469-238">Cada dirección IP pública del servidor perimetral A/V debe agregarse a las opciones de configuración de la red como subred con una máscara de subred de 32.</span><span class="sxs-lookup"><span data-stu-id="10469-238">Each public IP address of the A/V Edge Server must be added to your network configuration settings as a subnet with a subnet mask of 32.</span></span> <span data-ttu-id="10469-239">Por ejemplo, si implementa servidores perimetrales A/V en Chicago, para cada dirección IP externa de los servidores, cree una subred con una máscara de subred de 32 y asocie el sitio de red Chicago a dichas subredes.</span><span class="sxs-lookup"><span data-stu-id="10469-239">For example, if you deploy A/V Edge Servers in Chicago, then for each external IP address of those servers create a subnet with a subnet mask of 32 and associate network site Chicago with those subnets.</span></span> <span data-ttu-id="10469-240">Para obtener más información acerca de las direcciones IP públicas, consulte <A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">determinar el firewall externo a/V y los requisitos de puerto para Lync Server 2013</A> en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="10469-240">For details about public IP addresses, see <A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">Determine external A/V firewall and port requirements for Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="10469-p118">Aparecerá una alerta de indicador de estado clave (KHI), que especifica una lista de direcciones IP que están incluidas en la red pero que no están asociadas a una subred, o bien la subred que incluye las direcciones IP no está asociada a un sitio de red. Esta alerta no aparecerá más que una vez en un período de ocho horas. A continuación se ofrece la información de alerta relevante y un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="10469-p118">A Key Health Indicator (KHI) alert is raised, specifying a list of IP addresses that are present in your network but are either not associated with a subnet, or the subnet that includes the IP addresses is not associated with a network site. This alert will not be raised more than once within an 8 hour period. The relevant alert information and an example are as follows:</span></span><BR><span data-ttu-id="10469-244"><STRONG>Origen:</STRONG> Servicio de directivas de ancho de banda (principal) de CS</span><span class="sxs-lookup"><span data-stu-id="10469-244"><STRONG>Source:</STRONG> CS Bandwidth Policy Service (Core)</span></span><BR><span data-ttu-id="10469-245"><STRONG>Número de evento:</STRONG> 36034</span><span class="sxs-lookup"><span data-stu-id="10469-245"><STRONG>Event number:</STRONG> 36034</span></span><BR><span data-ttu-id="10469-246"><STRONG>Nivel:</STRONG> 2</span><span class="sxs-lookup"><span data-stu-id="10469-246"><STRONG>Level:</STRONG> 2</span></span><BR><span data-ttu-id="10469-247"><STRONG>Descripción:</STRONG> Las subredes de las siguientes direcciones IP: &lt;la lista de direcciones&gt; IP no está configurada o las subredes no están asociadas a un sitio de red.</span><span class="sxs-lookup"><span data-stu-id="10469-247"><STRONG>Description:</STRONG> The subnets for the following IP Addresses: &lt;List of IP Addresses&gt; are either not configured or the subnets are not associated to a network site.</span></span><BR><span data-ttu-id="10469-248"><STRONG>Causa:</STRONG> Las subredes de las direcciones IP correspondientes faltan en las opciones de configuración de red o las subredes no están asociadas a un sitio de red.</span><span class="sxs-lookup"><span data-stu-id="10469-248"><STRONG>Cause:</STRONG> The subnets for the corresponding IP addresses are missing from the network configuration settings or the subnets are not associated to a network site.</span></span><BR><span data-ttu-id="10469-249"><STRONG>Solución:</STRONG> Agregue subredes correspondientes a la lista anterior de direcciones IP a las opciones de configuración de red y asocie cada subred a un sitio de red.</span><span class="sxs-lookup"><span data-stu-id="10469-249"><STRONG>Resolution:</STRONG> Add subnets corresponding to the preceding list of IP addresses into the network configuration settings and associate every subnet to a network site.</span></span><BR><span data-ttu-id="10469-p119">Por ejemplo, si la lista de direcciones IP de la alerta especifica 10.121.248.226 y 10.121.249.20, estas direcciones IP no están asociadas a una subred o la subred a la que están asociadas no pertenece a un sitio de red. Si 10.121.248.0/24 y 10.121.249.0/24 son las subredes correspondientes a estas direcciones, este problema se puede resolver de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="10469-p119">For example, if the IP address list in the alert specifies 10.121.248.226 and 10.121.249.20, either these IP addresses are not associated with a subnet, or the subnet that they are associated with does not belong to a network site. If 10.121.248.0/24 and 10.121.249.0/24 are the corresponding subnets for these addresses, you can resolve this issue as follows:</span></span> 
    > <OL>
    > <LI>
    > <P><span data-ttu-id="10469-252">Asegúrese de que la dirección IP 10.121.248.226 está asociada a la subred 10.121.248.0/24 y la dirección IP 10.121.249.20 está asociada a la subred 10.121.249.0/24.</span><span class="sxs-lookup"><span data-stu-id="10469-252">Be sure that IP address 10.121.248.226 is associated with the 10.121.248.0/24 subnet and IP address 10.121.249.20 is associated with the 10.121.249.0/24 subnet.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="10469-253">Asegúrese de que cada una de las subredes 10.121.248.0/24 y 10.121.249.0/24 está asociada a un sitio de red.</span><span class="sxs-lookup"><span data-stu-id="10469-253">Be sure that the 10.121.248.0/24 and 10.121.249.0/24 subnets are each associated with a network site.</span></span></P></LI></OL>

    
    </div>
    
    ### <a name="network-sites-and-associated-subnets-bandwidth-in-kbps"></a><span data-ttu-id="10469-254">Sitios de red y subredes asociadas (ancho de banda en kbps)</span><span class="sxs-lookup"><span data-stu-id="10469-254">Network Sites and Associated Subnets (Bandwidth in kbps)</span></span>
    
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
    <th><span data-ttu-id="10469-255">Sitio de red</span><span class="sxs-lookup"><span data-stu-id="10469-255">Network Site</span></span></th>
    <th><span data-ttu-id="10469-256">Región de red</span><span class="sxs-lookup"><span data-stu-id="10469-256">Network Region</span></span></th>
    <th><span data-ttu-id="10469-257">Límite de ancho de banda</span><span class="sxs-lookup"><span data-stu-id="10469-257">BW Limit</span></span></th>
    <th><span data-ttu-id="10469-258">Límite de audio</span><span class="sxs-lookup"><span data-stu-id="10469-258">Audio Limit</span></span></th>
    <th><span data-ttu-id="10469-259">Límite de sesión de audio</span><span class="sxs-lookup"><span data-stu-id="10469-259">Audio Session Limit</span></span></th>
    <th><span data-ttu-id="10469-260">Límite de vídeo</span><span class="sxs-lookup"><span data-stu-id="10469-260">Video Limit</span></span></th>
    <th><span data-ttu-id="10469-261">Límite de sesión de vídeo</span><span class="sxs-lookup"><span data-stu-id="10469-261">Video Session Limit</span></span></th>
    <th><span data-ttu-id="10469-262">Subredes</span><span class="sxs-lookup"><span data-stu-id="10469-262">Subnets</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="10469-263">Albuquerque</span><span class="sxs-lookup"><span data-stu-id="10469-263">Albuquerque</span></span></p></td>
    <td><p><span data-ttu-id="10469-264">Norteamérica</span><span class="sxs-lookup"><span data-stu-id="10469-264">North America</span></span></p></td>
    <td><p><span data-ttu-id="10469-265">5,000</span><span class="sxs-lookup"><span data-stu-id="10469-265">5,000</span></span></p></td>
    <td><p><span data-ttu-id="10469-266">2,000</span><span class="sxs-lookup"><span data-stu-id="10469-266">2,000</span></span></p></td>
    <td><p><span data-ttu-id="10469-267">175</span><span class="sxs-lookup"><span data-stu-id="10469-267">175</span></span></p></td>
    <td><p><span data-ttu-id="10469-268">1.400</span><span class="sxs-lookup"><span data-stu-id="10469-268">1,400</span></span></p></td>
    <td><p><span data-ttu-id="10469-269">700</span><span class="sxs-lookup"><span data-stu-id="10469-269">700</span></span></p></td>
    <td><p><span data-ttu-id="10469-270">172.29.79.0/23, 157.57.215.0/25, 172.29.90.0/23, 172.29.80.0/24</span><span class="sxs-lookup"><span data-stu-id="10469-270">172.29.79.0/23, 157.57.215.0/25, 172.29.90.0/23, 172.29.80.0/24</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="10469-271">Reno</span><span class="sxs-lookup"><span data-stu-id="10469-271">Reno</span></span></p></td>
    <td><p><span data-ttu-id="10469-272">Norteamérica</span><span class="sxs-lookup"><span data-stu-id="10469-272">North America</span></span></p></td>
    <td><p><span data-ttu-id="10469-273">10 000</span><span class="sxs-lookup"><span data-stu-id="10469-273">10,000</span></span></p></td>
    <td><p><span data-ttu-id="10469-274">4.000</span><span class="sxs-lookup"><span data-stu-id="10469-274">4,000</span></span></p></td>
    <td><p><span data-ttu-id="10469-275">175</span><span class="sxs-lookup"><span data-stu-id="10469-275">175</span></span></p></td>
    <td><p><span data-ttu-id="10469-276">2.800</span><span class="sxs-lookup"><span data-stu-id="10469-276">2,800</span></span></p></td>
    <td><p><span data-ttu-id="10469-277">700</span><span class="sxs-lookup"><span data-stu-id="10469-277">700</span></span></p></td>
    <td><p><span data-ttu-id="10469-278">157.57.210.0/23, 172.28.151.128/25</span><span class="sxs-lookup"><span data-stu-id="10469-278">157.57.210.0/23, 172.28.151.128/25</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="10469-279">Portland</span><span class="sxs-lookup"><span data-stu-id="10469-279">Portland</span></span></p></td>
    <td><p><span data-ttu-id="10469-280">Norteamérica</span><span class="sxs-lookup"><span data-stu-id="10469-280">North America</span></span></p></td>
    <td><p><span data-ttu-id="10469-281">5,000</span><span class="sxs-lookup"><span data-stu-id="10469-281">5,000</span></span></p></td>
    <td><p><span data-ttu-id="10469-282">4.000</span><span class="sxs-lookup"><span data-stu-id="10469-282">4,000</span></span></p></td>
    <td><p><span data-ttu-id="10469-283">175</span><span class="sxs-lookup"><span data-stu-id="10469-283">175</span></span></p></td>
    <td><p><span data-ttu-id="10469-284">2.800</span><span class="sxs-lookup"><span data-stu-id="10469-284">2,800</span></span></p></td>
    <td><p><span data-ttu-id="10469-285">700</span><span class="sxs-lookup"><span data-stu-id="10469-285">700</span></span></p></td>
    <td><p><span data-ttu-id="10469-286">172.29.77.0/24 10.71.108.0/24, 157.57.208.0/23</span><span class="sxs-lookup"><span data-stu-id="10469-286">172.29.77.0/24 10.71.108.0/24, 157.57.208.0/23</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="10469-287">Nueva York</span><span class="sxs-lookup"><span data-stu-id="10469-287">New York</span></span></p></td>
    <td><p><span data-ttu-id="10469-288">Norteamérica</span><span class="sxs-lookup"><span data-stu-id="10469-288">North America</span></span></p></td>
    <td><p><span data-ttu-id="10469-289">(sin límite)</span><span class="sxs-lookup"><span data-stu-id="10469-289">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="10469-290">(sin límite)</span><span class="sxs-lookup"><span data-stu-id="10469-290">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="10469-291">(sin límite)</span><span class="sxs-lookup"><span data-stu-id="10469-291">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="10469-292">(sin límite)</span><span class="sxs-lookup"><span data-stu-id="10469-292">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="10469-293">(sin límite)</span><span class="sxs-lookup"><span data-stu-id="10469-293">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="10469-294">172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24</span><span class="sxs-lookup"><span data-stu-id="10469-294">172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="10469-295">Guadalajara</span><span class="sxs-lookup"><span data-stu-id="10469-295">Chicago</span></span></p></td>
    <td><p><span data-ttu-id="10469-296">Norteamérica</span><span class="sxs-lookup"><span data-stu-id="10469-296">North America</span></span></p></td>
    <td><p><span data-ttu-id="10469-297">(sin límite)</span><span class="sxs-lookup"><span data-stu-id="10469-297">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="10469-298">(sin límite)</span><span class="sxs-lookup"><span data-stu-id="10469-298">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="10469-299">(sin límite)</span><span class="sxs-lookup"><span data-stu-id="10469-299">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="10469-300">(sin límite)</span><span class="sxs-lookup"><span data-stu-id="10469-300">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="10469-301">(sin límite)</span><span class="sxs-lookup"><span data-stu-id="10469-301">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="10469-302">157.57.211.0/23, 172.28.152.128/25</span><span class="sxs-lookup"><span data-stu-id="10469-302">157.57.211.0/23, 172.28.152.128/25</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="10469-303">Detroit</span><span class="sxs-lookup"><span data-stu-id="10469-303">Detroit</span></span></p></td>
    <td><p><span data-ttu-id="10469-304">Norteamérica</span><span class="sxs-lookup"><span data-stu-id="10469-304">North America</span></span></p></td>
    <td><p><span data-ttu-id="10469-305">(sin límite)</span><span class="sxs-lookup"><span data-stu-id="10469-305">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="10469-306">(sin límite)</span><span class="sxs-lookup"><span data-stu-id="10469-306">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="10469-307">(sin límite)</span><span class="sxs-lookup"><span data-stu-id="10469-307">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="10469-308">(sin límite)</span><span class="sxs-lookup"><span data-stu-id="10469-308">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="10469-309">(sin límite)</span><span class="sxs-lookup"><span data-stu-id="10469-309">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="10469-310">172.29.78.0/24 10.71.109.0/24, 157.57.209.0/23</span><span class="sxs-lookup"><span data-stu-id="10469-310">172.29.78.0/24 10.71.109.0/24, 157.57.209.0/23</span></span></p></td>
    </tr>
    </tbody>
    </table>


7.  <span data-ttu-id="10469-311">En el control de admisión de llamadas de Lync Server, las conexiones entre regiones de red se denominan *vínculos de región*.</span><span class="sxs-lookup"><span data-stu-id="10469-311">In Lync Server call admission control, the connections between network regions are called *region links*.</span></span> <span data-ttu-id="10469-312">Para cada vínculo de región, determine lo siguiente, tal como hizo para los sitios de red:</span><span class="sxs-lookup"><span data-stu-id="10469-312">For each region link, determine the following, just as you did for the network sites:</span></span>
    
      - <span data-ttu-id="10469-313">Límite general de ancho de banda que desea establecer para todas las sesiones simultáneas de audio.</span><span class="sxs-lookup"><span data-stu-id="10469-313">Overall bandwidth limit that you want to set for all concurrent audio sessions.</span></span> <span data-ttu-id="10469-314">Si una nueva sesión de audio provoca que se supere este límite, Lync Server no permite que se inicie la sesión.</span><span class="sxs-lookup"><span data-stu-id="10469-314">If a new audio session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="10469-p122">Límite de ancho de banda que desea establecer para cada sesión individual de audio. El límite predeterminado de ancho de banda para CAC es de 175 kbps, pero el administrador puede modificarlo.</span><span class="sxs-lookup"><span data-stu-id="10469-p122">Bandwidth limit that you want to set for each individual audio session. The default CAC bandwidth limit is 175 kbps, but it can be modified by the administrator.</span></span>
    
      - <span data-ttu-id="10469-317">Límite general de ancho de banda que desea establecer para todas las sesiones simultáneas de vídeo.</span><span class="sxs-lookup"><span data-stu-id="10469-317">Overall bandwidth limit that you want to set for all concurrent video sessions.</span></span> <span data-ttu-id="10469-318">Si una nueva sesión de vídeo provoca que se supere este límite, Lync Server no permite que se inicie la sesión.</span><span class="sxs-lookup"><span data-stu-id="10469-318">If a new video session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="10469-p124">Límite de ancho de banda que desea establecer para cada sesión individual de vídeo. El límite predeterminado de ancho de banda para CAC es de 700 kbps, pero el administrador puede modificarlo.</span><span class="sxs-lookup"><span data-stu-id="10469-p124">Bandwidth limit that you want to set for each individual video session. The default CAC bandwidth limit is 700 kbps, but it can be modified by the administrator.</span></span>
    
    <span data-ttu-id="10469-321">**Vínculos de región de red con límites de ancho de banda asociados**</span><span class="sxs-lookup"><span data-stu-id="10469-321">**Network Region links with associated bandwidth limits**</span></span>
    
    <span data-ttu-id="10469-322">![Ejemplo de limitaciones entre 3 regiones](images/Gg425827.25259afa-ee7c-4d26-bc41-92ba9cb56dec(OCS.15).jpg "Ejemplo de limitaciones entre 3 regiones")</span><span class="sxs-lookup"><span data-stu-id="10469-322">![Example of Limitations between 3 Regions](images/Gg425827.25259afa-ee7c-4d26-bc41-92ba9cb56dec(OCS.15).jpg "Example of Limitations between 3 Regions")</span></span>  
    
    ### <a name="region-link-bandwidth-information-bandwidth-in-kbps"></a><span data-ttu-id="10469-323">Información de ancho de banda de vínculos de región (ancho de banda en kbps)</span><span class="sxs-lookup"><span data-stu-id="10469-323">Region Link Bandwidth Information (Bandwidth in kbps)</span></span>
    
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
    <th><span data-ttu-id="10469-324">Nombre del vínculo de región</span><span class="sxs-lookup"><span data-stu-id="10469-324">Region Link Name</span></span></th>
    <th><span data-ttu-id="10469-325">Primera región</span><span class="sxs-lookup"><span data-stu-id="10469-325">First Region</span></span></th>
    <th><span data-ttu-id="10469-326">Segunda región</span><span class="sxs-lookup"><span data-stu-id="10469-326">Second Region</span></span></th>
    <th><span data-ttu-id="10469-327">Límite de ancho de banda</span><span class="sxs-lookup"><span data-stu-id="10469-327">BW Limit</span></span></th>
    <th><span data-ttu-id="10469-328">Límite de audio</span><span class="sxs-lookup"><span data-stu-id="10469-328">Audio Limit</span></span></th>
    <th><span data-ttu-id="10469-329">Límite de sesión de audio</span><span class="sxs-lookup"><span data-stu-id="10469-329">Audio Session Limit</span></span></th>
    <th><span data-ttu-id="10469-330">Límite de vídeo</span><span class="sxs-lookup"><span data-stu-id="10469-330">Video Limit</span></span></th>
    <th><span data-ttu-id="10469-331">Límite de sesión de vídeo</span><span class="sxs-lookup"><span data-stu-id="10469-331">Video Session Limit</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="10469-332">NA-EMEA-LINK</span><span class="sxs-lookup"><span data-stu-id="10469-332">NA-EMEA-LINK</span></span></p></td>
    <td><p><span data-ttu-id="10469-333">Norteamérica</span><span class="sxs-lookup"><span data-stu-id="10469-333">North America</span></span></p></td>
    <td><p><span data-ttu-id="10469-334">EMEA</span><span class="sxs-lookup"><span data-stu-id="10469-334">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="10469-335">50 000</span><span class="sxs-lookup"><span data-stu-id="10469-335">50,000</span></span></p></td>
    <td><p><span data-ttu-id="10469-336">20,000</span><span class="sxs-lookup"><span data-stu-id="10469-336">20,000</span></span></p></td>
    <td><p><span data-ttu-id="10469-337">175</span><span class="sxs-lookup"><span data-stu-id="10469-337">175</span></span></p></td>
    <td><p><span data-ttu-id="10469-338">14.000</span><span class="sxs-lookup"><span data-stu-id="10469-338">14,000</span></span></p></td>
    <td><p><span data-ttu-id="10469-339">700</span><span class="sxs-lookup"><span data-stu-id="10469-339">700</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="10469-340">EMEA-APAC-LINK</span><span class="sxs-lookup"><span data-stu-id="10469-340">EMEA-APAC-LINK</span></span></p></td>
    <td><p><span data-ttu-id="10469-341">EMEA</span><span class="sxs-lookup"><span data-stu-id="10469-341">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="10469-342">Pacífico</span><span class="sxs-lookup"><span data-stu-id="10469-342">APAC</span></span></p></td>
    <td><p><span data-ttu-id="10469-343">25 000</span><span class="sxs-lookup"><span data-stu-id="10469-343">25,000</span></span></p></td>
    <td><p><span data-ttu-id="10469-344">10 000</span><span class="sxs-lookup"><span data-stu-id="10469-344">10,000</span></span></p></td>
    <td><p><span data-ttu-id="10469-345">175</span><span class="sxs-lookup"><span data-stu-id="10469-345">175</span></span></p></td>
    <td><p><span data-ttu-id="10469-346">7.000</span><span class="sxs-lookup"><span data-stu-id="10469-346">7,000</span></span></p></td>
    <td><p><span data-ttu-id="10469-347">700</span><span class="sxs-lookup"><span data-stu-id="10469-347">700</span></span></p></td>
    </tr>
    </tbody>
    </table>


8.  <span data-ttu-id="10469-348">Definir una ruta entre cada par de regiones de red.</span><span class="sxs-lookup"><span data-stu-id="10469-348">Define a route between every pair of network regions.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="10469-349">Se requieren dos vínculos para la ruta entre las regiones Norteamérica y APAC porque no existe ningún vínculo de región que las conecte directamente.</span><span class="sxs-lookup"><span data-stu-id="10469-349">Two links are required for the route between the North America and APAC regions because there is no region link that directly connects them.</span></span>

    
    </div>
    
    ### <a name="region-routes"></a><span data-ttu-id="10469-350">Rutas de región</span><span class="sxs-lookup"><span data-stu-id="10469-350">Region Routes</span></span>
    
    <table>
    <colgroup>
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="10469-351">Nombre de la ruta de región</span><span class="sxs-lookup"><span data-stu-id="10469-351">Region Route Name</span></span></th>
    <th><span data-ttu-id="10469-352">Primera región</span><span class="sxs-lookup"><span data-stu-id="10469-352">First Region</span></span></th>
    <th><span data-ttu-id="10469-353">Segunda región</span><span class="sxs-lookup"><span data-stu-id="10469-353">Second Region</span></span></th>
    <th><span data-ttu-id="10469-354">Vínculos de región</span><span class="sxs-lookup"><span data-stu-id="10469-354">Region Links</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="10469-355">NA-EMEA-ROUTE</span><span class="sxs-lookup"><span data-stu-id="10469-355">NA-EMEA-ROUTE</span></span></p></td>
    <td><p><span data-ttu-id="10469-356">Norteamérica</span><span class="sxs-lookup"><span data-stu-id="10469-356">North America</span></span></p></td>
    <td><p><span data-ttu-id="10469-357">EMEA</span><span class="sxs-lookup"><span data-stu-id="10469-357">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="10469-358">NA-EMEA-LINK</span><span class="sxs-lookup"><span data-stu-id="10469-358">NA-EMEA-LINK</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="10469-359">EMEA-APAC-ROUTE</span><span class="sxs-lookup"><span data-stu-id="10469-359">EMEA-APAC-ROUTE</span></span></p></td>
    <td><p><span data-ttu-id="10469-360">EMEA</span><span class="sxs-lookup"><span data-stu-id="10469-360">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="10469-361">Pacífico</span><span class="sxs-lookup"><span data-stu-id="10469-361">APAC</span></span></p></td>
    <td><p><span data-ttu-id="10469-362">EMEA-APAC-LINK</span><span class="sxs-lookup"><span data-stu-id="10469-362">EMEA-APAC-LINK</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="10469-363">NA-APAC-ROUTE</span><span class="sxs-lookup"><span data-stu-id="10469-363">NA-APAC-ROUTE</span></span></p></td>
    <td><p><span data-ttu-id="10469-364">Norteamérica</span><span class="sxs-lookup"><span data-stu-id="10469-364">North America</span></span></p></td>
    <td><p><span data-ttu-id="10469-365">Pacífico</span><span class="sxs-lookup"><span data-stu-id="10469-365">APAC</span></span></p></td>
    <td><p><span data-ttu-id="10469-366">NA-EMEA-LINK, EMEA-APAC-LINK</span><span class="sxs-lookup"><span data-stu-id="10469-366">NA-EMEA-LINK, EMEA-APAC-LINK</span></span></p></td>
    </tr>
    </tbody>
    </table>


9.  <span data-ttu-id="10469-367">Para cada par de sitios de red que estén conectados directamente por un solo vínculo (denominado vínculo *entre sitios*), determine lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="10469-367">For every pair of network sites that are directly connected by a single link (called an *inter-site* link), determine the following:</span></span>
    
      - <span data-ttu-id="10469-368">Límite general de ancho de banda que desea establecer para todas las sesiones simultáneas de audio.</span><span class="sxs-lookup"><span data-stu-id="10469-368">Overall bandwidth limit that you want to set for all concurrent audio sessions.</span></span> <span data-ttu-id="10469-369">Si una nueva sesión de audio provoca que se supere este límite, Lync Server no permite que se inicie la sesión.</span><span class="sxs-lookup"><span data-stu-id="10469-369">If a new audio session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="10469-p126">Límite de ancho de banda que desea establecer para cada sesión individual de audio. El límite predeterminado de ancho de banda para CAC es de 175 kbps, pero el administrador puede modificarlo.</span><span class="sxs-lookup"><span data-stu-id="10469-p126">Bandwidth limit that you want to set for each individual audio session. The default CAC bandwidth limit is 175 kbps, but it can be modified by the administrator.</span></span>
    
      - <span data-ttu-id="10469-372">Límite general de ancho de banda que desea establecer para todas las sesiones simultáneas de vídeo.</span><span class="sxs-lookup"><span data-stu-id="10469-372">Overall bandwidth limit that you want to set for all concurrent video sessions.</span></span> <span data-ttu-id="10469-373">Si una nueva sesión de vídeo provoca que se supere este límite, Lync Server no permite que se inicie la sesión.</span><span class="sxs-lookup"><span data-stu-id="10469-373">If a new video session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="10469-p128">Límite de ancho de banda que desea establecer para cada sesión individual de vídeo. El límite predeterminado de ancho de banda para CAC es de 700 kbps, pero el administrador puede modificarlo.</span><span class="sxs-lookup"><span data-stu-id="10469-p128">Bandwidth limit that you want to set for each individual video session. The default CAC bandwidth limit is 700 kbps, but it can be modified by the administrator.</span></span>
    
    <span data-ttu-id="10469-376">**Región de red para CAC Norteamérica con indicación de las capacidades de ancho de banda y los límites de ancho de banda del vínculo entre sitios entre Reno y Albuquerque**</span><span class="sxs-lookup"><span data-stu-id="10469-376">**CAC network region North America showing the bandwidth capacities and bandwidth limits for the inter-site link between Reno and Albuquerque**</span></span>
    
    <span data-ttu-id="10469-377">![Ejemplo de sitios de red restringidos por el ancho de banda de WAN](images/Gg425827.063e5e1d-b6c8-4e8c-98db-c227c78f671d(OCS.15).jpg "Ejemplo de sitios de red restringidos por el ancho de banda de WAN")</span><span class="sxs-lookup"><span data-stu-id="10469-377">![Network Sites Constrained by WAN Bandwidth example](images/Gg425827.063e5e1d-b6c8-4e8c-98db-c227c78f671d(OCS.15).jpg "Network Sites Constrained by WAN Bandwidth example")</span></span>  
    
    ### <a name="bandwidth-information-for-an-inter-site-link-between-two-network-sites-bandwidth-in-kbps"></a><span data-ttu-id="10469-378">Información de ancho de banda de un vínculo entre sitios entre dos sitios de red (ancho de banda en kbps)</span><span class="sxs-lookup"><span data-stu-id="10469-378">Bandwidth Information for an Inter-Site Link between Two Network Sites (Bandwidth in kbps)</span></span>
    
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
    <th><span data-ttu-id="10469-379">Nombre del vínculo entre sitios</span><span class="sxs-lookup"><span data-stu-id="10469-379">Inter-Site Link Name</span></span></th>
    <th><span data-ttu-id="10469-380">Primer sitio</span><span class="sxs-lookup"><span data-stu-id="10469-380">First Site</span></span></th>
    <th><span data-ttu-id="10469-381">Segundo sitio</span><span class="sxs-lookup"><span data-stu-id="10469-381">Second Site</span></span></th>
    <th><span data-ttu-id="10469-382">Límite de ancho de banda</span><span class="sxs-lookup"><span data-stu-id="10469-382">BW Limit</span></span></th>
    <th><span data-ttu-id="10469-383">Límite de audio</span><span class="sxs-lookup"><span data-stu-id="10469-383">Audio Limit</span></span></th>
    <th><span data-ttu-id="10469-384">Límite de sesión de audio</span><span class="sxs-lookup"><span data-stu-id="10469-384">Audio Session Limit</span></span></th>
    <th><span data-ttu-id="10469-385">Límite de vídeo</span><span class="sxs-lookup"><span data-stu-id="10469-385">Video Limit</span></span></th>
    <th><span data-ttu-id="10469-386">Límite de sesión de vídeo</span><span class="sxs-lookup"><span data-stu-id="10469-386">Video Session Limit</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="10469-387">Reno-Albu-intersite-Link</span><span class="sxs-lookup"><span data-stu-id="10469-387">Reno-Albu-Intersite-Link</span></span></p></td>
    <td><p><span data-ttu-id="10469-388">Reno</span><span class="sxs-lookup"><span data-stu-id="10469-388">Reno</span></span></p></td>
    <td><p><span data-ttu-id="10469-389">Albuquerque</span><span class="sxs-lookup"><span data-stu-id="10469-389">Albuquerque</span></span></p></td>
    <td><p><span data-ttu-id="10469-390">20,000</span><span class="sxs-lookup"><span data-stu-id="10469-390">20,000</span></span></p></td>
    <td><p><span data-ttu-id="10469-391">12.000</span><span class="sxs-lookup"><span data-stu-id="10469-391">12,000</span></span></p></td>
    <td><p><span data-ttu-id="10469-392">175</span><span class="sxs-lookup"><span data-stu-id="10469-392">175</span></span></p></td>
    <td><p><span data-ttu-id="10469-393">5,000</span><span class="sxs-lookup"><span data-stu-id="10469-393">5,000</span></span></p></td>
    <td><p><span data-ttu-id="10469-394">700</span><span class="sxs-lookup"><span data-stu-id="10469-394">700</span></span></p></td>
    </tr>
    </tbody>
    </table>


<div>

## <a name="next-steps"></a><span data-ttu-id="10469-395">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="10469-395">Next Steps</span></span>

<span data-ttu-id="10469-396">Una vez recopilada la información necesaria, puede realizar una implementación de CAC mediante el shell de administración de Lync Server o el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="10469-396">After you have gathered the required information, you can perform CAC deployment either by using the Lync Server Management Shell or Lync Server Control Panel.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="10469-397">Aunque puede realizar la mayoría de las tareas de configuración de red mediante el panel de control de Lync Server, para crear subredes y vínculos entre sitios, debe usar el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="10469-397">Although you can perform most network configuration tasks by using Lync Server Control Panel, to create subnets and intersite links, you must use Lync Server Management Shell.</span></span> <span data-ttu-id="10469-398">Para obtener más información, consulte la documentación del shell de administración de Lync Server para el cmdlet <STRONG>New-CsNetworkSubnet</STRONG> y el cmdlet <STRONG>New-CsNetworkIntersitePolicy</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="10469-398">For details, see the Lync Server Management Shell documentation for the <STRONG>New-CsNetworkSubnet</STRONG> cmdlet and the <STRONG>New-CsNetworkIntersitePolicy</STRONG> cmdlet.</span></span>



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

