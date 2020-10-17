---
title: 'Lync Server 2013: configuración de intervalos de puertos para los servidores de conferencia, aplicación y mediación'
description: 'Lync Server 2013: configuración de intervalos de puertos para los servidores de conferencia, aplicación y mediación.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring port ranges for your Conferencing, Application, and Mediation servers
ms:assetid: 4d6eaa5d-0127-453f-be6a-e55384772d83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204872(v=OCS.15)
ms:contentKeyID: 48184074
ms.date: 05/01/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eb3f51e42c86b667b6990f41640bf09e12e840c2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558766"
---
# <a name="configuring-port-ranges-in-lync-server-2013-for-your-conferencing-application-and-mediation-servers"></a><span data-ttu-id="8bd57-103">Configuración de intervalos de puertos en Lync Server 2013 para los servidores de conferencia, aplicación y mediación</span><span class="sxs-lookup"><span data-stu-id="8bd57-103">Configuring port ranges in Lync Server 2013 for your Conferencing, Application, and Mediation servers</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8bd57-104">_**Última modificación del tema:** 2015-04-30_</span><span class="sxs-lookup"><span data-stu-id="8bd57-104">_**Topic Last Modified:** 2015-04-30_</span></span>

<span data-ttu-id="8bd57-p101">Con el fin de implementar Calidad de servicio, debe configurar intervalos de puertos idénticos para audio, vídeo y aplicaciones que comparten los servidores de conferencias, aplicaciones y la mediación; además, los intervalos de puertos no deben superponerse de ninguna manera. Para usar un ejemplo sencillo, suponga que usa los puertos 10000 hasta 10999 para vídeo en los servidores de conferencias. Eso significa que también deben reservar los puertos 10000 hasta 10999 para vídeo en sus servidores de aplicaciones y mediación. Si no lo haces, QoS no funcionará como se espera.</span><span class="sxs-lookup"><span data-stu-id="8bd57-p101">In order to implement Quality of Service, you should configure identical port ranges for audio, video, and application sharing on your Conferencing, Application, and Mediation servers; furthermore, those port ranges must not overlap in any way. To use a simple example, suppose you use ports 10000 through 10999 for video on your Conferencing servers. That means that you must also reserve ports 10000 through 10999 for video on your Application and Mediation servers. If you do not, QoS will not work as expected.</span></span>

<span data-ttu-id="8bd57-p102">Del mismo modo, suponga que reserva los puertos 10000 hasta 10999 para vídeo, pero luego reserva los puertos 10500 hasta 11999 para audio. Esto puede crear problemas de Calidad de servicio, porque los intervalos de puerto se superponen. Con QoS, cada modalidad debe tener un único conjunto de puertos: si usa los puertos 10000 hasta 10999 para vídeo, luego tendrá que usar otro intervalo (por ejemplo, 11000 hasta 11999) para audio.</span><span class="sxs-lookup"><span data-stu-id="8bd57-p102">Similarly, suppose you reserve ports 10000 through 10999 for video, but then reserve ports 10500 through 11999 for audio. This can create problems for Quality of Service, because the port ranges overlap. With QoS, each modality must have a unique set of ports: if you use ports 10000 through 10999 for video, then you'll have to use a different range (for example, 11000 through 11999 for audio).</span></span>

<span data-ttu-id="8bd57-112">De forma predeterminada, los intervalos de puertos de audio y vídeo no se superponen en Microsoft Lync Server 2013; sin embargo, los intervalos de puertos asignados al uso compartido de aplicaciones se superponen con los intervalos de puertos de audio y vídeo.</span><span class="sxs-lookup"><span data-stu-id="8bd57-112">By default, audio and video port ranges do not overlap in Microsoft Lync Server 2013; however, the port ranges assigned to application sharing overlap with both the audio and video port ranges.</span></span> <span data-ttu-id="8bd57-113">(Lo que, a su vez, significa que ninguno de estos intervalos es único). Puede comprobar los intervalos de puertos existentes para los servidores de conferencia, aplicación y mediación mediante la ejecución de los siguientes tres comandos desde dentro del shell de administración de Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="8bd57-113">(Which, in turn, means that none of these ranges are unique.) You can verify the existing port ranges for your Conferencing, Application, and Mediation servers by running the following three commands from within the Lync Server 2013 Management Shell:</span></span>

    Get-CsService -ConferencingServer | Select-Object Identity, AudioPortStart, AudioPortCount, VideoPortStart, VideoPortCount, AppSharingPortStart, AppSharingPortCount
    
    Get-CsService -ApplicationServer | Select-Object Identity, AudioPortStart, AudioPortCount
    
    Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount

<div>


> [!WARNING]  
> <span data-ttu-id="8bd57-p104">Como puede ver en los comandos anteriores, a cada tipo de puerto: audio, vídeo y uso compartido de aplicaciones se les asigna dos valores de propiedad separados: el puerto de inicio y el número de puerto. El inicio de puerto indica el primer puerto que se usa para esa modalidad; por ejemplo, si el puerto de inicio de audio es igual a 50000, significa que el primer puerto que se usa para el tráfico de audio es puerto 50000. Si el recuento del puerto de audio es 2 (que no es un valor válido, pero se usa aquí para fines de ilustración) eso significa que solo se asignan para el audio 2 puertos. Si el primer puerto es el puerto 50000 y hay un total de dos puertos, eso significa que el segundo puerto debe ser el 50001 (los intervalos de puertos tienen que ser contiguos). Como resultado, el intervalo de puertos de audio sería del puerto 50000 hasta el 50001, incluidos.</span><span class="sxs-lookup"><span data-stu-id="8bd57-p104">As you can see in the preceding commands, each port type – audio, video, and application sharing – is assigned two separate property values: the port start and the port count. The port start indicates the first port used for that modality; for example, if the audio port start is equal to 50000 that means that the first port used for audio traffic is port 50000. If the audio port count is 2 (which is not a valid value, but is used here for illustration purposes) that means that only 2 ports are allocated for audio. If the first port is port 50000 and there are a total of two ports, that means the second port must be port 50001 (port ranges have to be contiguous). As a result, the port range for audio would be ports 50000 through 50001, inclusive.</span></span><BR><span data-ttu-id="8bd57-119">Tenga en cuenta que el servidor de aplicaciones y el servidor de mediación solo admiten QoS para audio; no necesita cambiar el vídeo o el uso compartido de aplicaciones de puertos en sus servidores de aplicaciones o mediación.</span><span class="sxs-lookup"><span data-stu-id="8bd57-119">Note, too that Application server and Mediation server only support QoS for audio; you do not need to change video or application sharing ports in your Application servers or Mediation servers.</span></span>



</div>

<span data-ttu-id="8bd57-120">Si ejecuta los tres comandos anteriores verá que los valores de puerto predeterminados para Lync Server 2013 son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="8bd57-120">If you run the preceding three commands you'll see that the default port values for Lync Server 2013 are configured like this:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8bd57-121">Propiedad</span><span class="sxs-lookup"><span data-stu-id="8bd57-121">Property</span></span></th>
<th><span data-ttu-id="8bd57-122">Servidor de conferencias</span><span class="sxs-lookup"><span data-stu-id="8bd57-122">Conferencing Server</span></span></th>
<th><span data-ttu-id="8bd57-123">Servidor de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="8bd57-123">Application Server</span></span></th>
<th><span data-ttu-id="8bd57-124">Servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="8bd57-124">Mediation Server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8bd57-125">AudioPortStart</span><span class="sxs-lookup"><span data-stu-id="8bd57-125">AudioPortStart</span></span></p></td>
<td><p><span data-ttu-id="8bd57-126">49152</span><span class="sxs-lookup"><span data-stu-id="8bd57-126">49152</span></span></p></td>
<td><p><span data-ttu-id="8bd57-127">49152</span><span class="sxs-lookup"><span data-stu-id="8bd57-127">49152</span></span></p></td>
<td><p><span data-ttu-id="8bd57-128">49152</span><span class="sxs-lookup"><span data-stu-id="8bd57-128">49152</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bd57-129">AudioPortCount</span><span class="sxs-lookup"><span data-stu-id="8bd57-129">AudioPortCount</span></span></p></td>
<td><p><span data-ttu-id="8bd57-130">8348</span><span class="sxs-lookup"><span data-stu-id="8bd57-130">8348</span></span></p></td>
<td><p><span data-ttu-id="8bd57-131">8348</span><span class="sxs-lookup"><span data-stu-id="8bd57-131">8348</span></span></p></td>
<td><p><span data-ttu-id="8bd57-132">8348</span><span class="sxs-lookup"><span data-stu-id="8bd57-132">8348</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8bd57-133">VideoPortStart</span><span class="sxs-lookup"><span data-stu-id="8bd57-133">VideoPortStart</span></span></p></td>
<td><p><span data-ttu-id="8bd57-134">57501</span><span class="sxs-lookup"><span data-stu-id="8bd57-134">57501</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bd57-135">VideoPortCount</span><span class="sxs-lookup"><span data-stu-id="8bd57-135">VideoPortCount</span></span></p></td>
<td><p><span data-ttu-id="8bd57-136">8034</span><span class="sxs-lookup"><span data-stu-id="8bd57-136">8034</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8bd57-137">ApplicationSharingPortStart</span><span class="sxs-lookup"><span data-stu-id="8bd57-137">ApplicationSharingPortStart</span></span></p></td>
<td><p><span data-ttu-id="8bd57-138">49152</span><span class="sxs-lookup"><span data-stu-id="8bd57-138">49152</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bd57-139">ApplicationSharingPortCount</span><span class="sxs-lookup"><span data-stu-id="8bd57-139">ApplicationSharingPortCount</span></span></p></td>
<td><p><span data-ttu-id="8bd57-140">16383</span><span class="sxs-lookup"><span data-stu-id="8bd57-140">16383</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="8bd57-141">Como se indicó anteriormente, al configurar los puertos de Lync Server para QoS, debe asegurarse de que: 1) la configuración del puerto de audio es idéntica en los servidores de conferencia, aplicación y mediación. y 2) los intervalos de puertos no se superponen.</span><span class="sxs-lookup"><span data-stu-id="8bd57-141">As noted previously, when configuring Lync Server ports for QoS, you should ensure that: 1) audio port settings are identical across yours Conferencing, Application, and Mediation servers; and, 2) port ranges do not overlap.</span></span> <span data-ttu-id="8bd57-142">Si observa detenidamente la tabla anterior, verá que los intervalos de puertos son idénticos a través de los tres tipos de servidores.</span><span class="sxs-lookup"><span data-stu-id="8bd57-142">If you look closely at the preceding table, you will see that the port ranges are identical across the three server types.</span></span> <span data-ttu-id="8bd57-143">Por ejemplo, el puerto de inicio de audio se establece en Puerto 49152 en cada tipo de servidor y el número total de puertos reservados en cada servidor de audio también es idéntico: 8348.</span><span class="sxs-lookup"><span data-stu-id="8bd57-143">For example, the starting audio port is set to port 49152 on each server type, and the total number of ports reserved for audio in each server is also identical: 8348.</span></span> <span data-ttu-id="8bd57-144">Sin embargo, el intervalo de puertos se superpone: los puertos de audio comienzan en el puerto 49152, pero, al hacerlo así, los puertos se reservan para uso compartido de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="8bd57-144">However, the port ranges overlap: audio ports start at port 49152, but so do the ports set aside for application sharing.</span></span> <span data-ttu-id="8bd57-145">Para usar correctamente la Calidad de servicio, el uso compartido de aplicaciones debe configurarse para utilizar un único intervalo de puertos.</span><span class="sxs-lookup"><span data-stu-id="8bd57-145">In order to make optimal use of Quality of Service, application sharing should be reconfigured to use a unique port range.</span></span> <span data-ttu-id="8bd57-146">Por ejemplo, podría configurar el uso compartido de aplicaciones para que se inicie en el puerto 40803 y use 8348 puertos.</span><span class="sxs-lookup"><span data-stu-id="8bd57-146">For example, you could configure application sharing to start at port 40803 and to use 8348 ports.</span></span> <span data-ttu-id="8bd57-147">¿Por qué 8348 puertos?</span><span class="sxs-lookup"><span data-stu-id="8bd57-147">(Why 8348 ports?</span></span> <span data-ttu-id="8bd57-148">Si agrega estos valores juntos--40803 + 8348, significa que el uso compartido de aplicaciones usará los puertos 40803 a través del puerto 49150.</span><span class="sxs-lookup"><span data-stu-id="8bd57-148">If you add those values together -- 40803 + 8348 -- that means that application sharing will use ports 40803 through port 49150.</span></span> <span data-ttu-id="8bd57-149">Ya que los puertos de audio no comienzan hasta el puerto 49152, ya no tendrá ningún intervalo de puertos superpuestos.</span><span class="sxs-lookup"><span data-stu-id="8bd57-149">Because audio ports do not begin until port 49152, you will no longer have any overlapping port ranges.)</span></span>

<span data-ttu-id="8bd57-p106">Después de haber seleccionado el nuevo intervalo de puertos para uso compartido de aplicaciones, puede hacer el cambio con el cmdlet Set-CsConferencingServer. Este cambio no tiene que hacerse en los servidores de aplicaciones o en los servidores de mediación, porque estos servidores no controlan tráfico de uso compartido de aplicaciones. Solo necesita cambiar los valores del puerto en estos servidores si decide volver a asignar los puertos usados para el tráfico de audio.</span><span class="sxs-lookup"><span data-stu-id="8bd57-p106">After you have selected the new port range for application sharing you can make your change by using the Set-CsConferencingServer cmdlet. This change does not need to be made on your Application servers or on your Mediation servers, because these servers do not handle application sharing traffic. You only need to change port values on these servers if you decide to reassign the ports used for audio traffic.</span></span>

<span data-ttu-id="8bd57-153">Para modificar los valores de puerto para el uso compartido de aplicaciones en un solo servidor de conferencia, ejecute un comando similar a este desde dentro del shell de administración de Lync Server:</span><span class="sxs-lookup"><span data-stu-id="8bd57-153">To modify the port values for application sharing on a single Conferencing server run a command similar to this from within the Lync Server Management Shell:</span></span>

    Set-CsConferenceServer -Identity ConferencingServer:atl-cs-001.litwareinc.com -AppSharingPortStart 40803 -AppSharingPortCount 8348

<span data-ttu-id="8bd57-154">Si desea realizar estos cambios en todos los servidores de conferencias, puede ejecutar este comando en su lugar:</span><span class="sxs-lookup"><span data-stu-id="8bd57-154">If you want to make these changes on all your Conferencing servers you can run this command instead:</span></span>

    Get-CsService -ConferencingServer | ForEach-Object {Set-CsConferenceServer -Identity $_.Identity -AppSharingPortStart 40803 -AppSharingPortCount 8348}

<span data-ttu-id="8bd57-155">Después de cambiar la configuración del puerto debe detener y reiniciar cada servicio afectado por los cambios.</span><span class="sxs-lookup"><span data-stu-id="8bd57-155">After changing port settings you should stop and then restart each service affected by the changes.</span></span>

<span data-ttu-id="8bd57-p107">No es obligatorio que los servidores de conferencias, servidores de aplicaciones y servidores de mediación compartan el mismo intervalo de puertos exacto; el único requisito real es que reserve intervalos de puertos únicos en todos los servidores. Sin embargo, la administración suele ser más fácil si se usa el mismo conjunto de puertos en todos los servidores.</span><span class="sxs-lookup"><span data-stu-id="8bd57-p107">It is not mandatory that your Conferencing servers, Application servers, and Mediation servers share the exact same port range; the only true requirement is that you set aside unique port ranges on all your servers. However, administration will typically be easier if you use the same set of ports on all your servers.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

