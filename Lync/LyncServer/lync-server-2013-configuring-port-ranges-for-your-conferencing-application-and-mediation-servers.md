---
title: 'Lync Server 2013: configuración de intervalos de puertos para los servidores de conferencias, aplicaciones y mediación'
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
ms.openlocfilehash: 54aab5efbca06d918cc2dbeccc0e36aee9d4abf8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756304"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-port-ranges-in-lync-server-2013-for-your-conferencing-application-and-mediation-servers"></a><span data-ttu-id="7abb6-102">Configuración de intervalos de puertos en Lync Server 2013 para sus servidores de conferencias, aplicaciones y mediación</span><span class="sxs-lookup"><span data-stu-id="7abb6-102">Configuring port ranges in Lync Server 2013 for your Conferencing, Application, and Mediation servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7abb6-103">_**Última modificación del tema:** 2015-04-30_</span><span class="sxs-lookup"><span data-stu-id="7abb6-103">_**Topic Last Modified:** 2015-04-30_</span></span>

<span data-ttu-id="7abb6-104">Para implementar la calidad de servicio, debe configurar los intervalos de puertos idénticos para el audio, el vídeo y el uso compartido de aplicaciones en sus servidores de conferencias, aplicaciones y mediación. Además, esos intervalos de puertos no deben superponerse de ninguna manera.</span><span class="sxs-lookup"><span data-stu-id="7abb6-104">In order to implement Quality of Service, you should configure identical port ranges for audio, video, and application sharing on your Conferencing, Application, and Mediation servers; furthermore, those port ranges must not overlap in any way.</span></span> <span data-ttu-id="7abb6-105">Para usar un ejemplo sencillo, suponga que usa los puertos 10000 a 10999 para vídeo en los servidores de conferencia.</span><span class="sxs-lookup"><span data-stu-id="7abb6-105">To use a simple example, suppose you use ports 10000 through 10999 for video on your Conferencing servers.</span></span> <span data-ttu-id="7abb6-106">Eso significa que también debe reservar los puertos 10000 a 10999 para vídeo en su aplicación y servidores de mediación.</span><span class="sxs-lookup"><span data-stu-id="7abb6-106">That means that you must also reserve ports 10000 through 10999 for video on your Application and Mediation servers.</span></span> <span data-ttu-id="7abb6-107">De lo contrario, QoS no funcionará de la forma esperada.</span><span class="sxs-lookup"><span data-stu-id="7abb6-107">If you do not, QoS will not work as expected.</span></span>

<span data-ttu-id="7abb6-108">De forma similar, suponga que reserva los puertos 10000 a 10999 para video, pero después reserva los puertos 10500 a 11999 para audio.</span><span class="sxs-lookup"><span data-stu-id="7abb6-108">Similarly, suppose you reserve ports 10000 through 10999 for video, but then reserve ports 10500 through 11999 for audio.</span></span> <span data-ttu-id="7abb6-109">Esto puede crear problemas de calidad de servicio porque los intervalos de puertos se superponen.</span><span class="sxs-lookup"><span data-stu-id="7abb6-109">This can create problems for Quality of Service, because the port ranges overlap.</span></span> <span data-ttu-id="7abb6-110">Con QoS, cada modalidad debe tener un único conjunto de puertos: Si usas los puertos 10000 a 10999 para video, tendrás que usar un intervalo diferente (por ejemplo, 11000 a 11999 para audio).</span><span class="sxs-lookup"><span data-stu-id="7abb6-110">With QoS, each modality must have a unique set of ports: if you use ports 10000 through 10999 for video, then you'll have to use a different range (for example, 11000 through 11999 for audio).</span></span>

<span data-ttu-id="7abb6-111">De forma predeterminada, los intervalos de puertos de audio y vídeo no se superponen en Microsoft Lync Server 2013; sin embargo, los intervalos de puertos asignados al uso compartido de aplicaciones se superponen con los intervalos de puertos de audio y vídeo.</span><span class="sxs-lookup"><span data-stu-id="7abb6-111">By default, audio and video port ranges do not overlap in Microsoft Lync Server 2013; however, the port ranges assigned to application sharing overlap with both the audio and video port ranges.</span></span> <span data-ttu-id="7abb6-112">(Que, a su vez, significa que ninguno de estos intervalos es único). Puede comprobar los intervalos de puertos existentes para los servidores de conferencia, aplicación y mediación ejecutando los siguientes tres comandos desde el shell de administración de Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="7abb6-112">(Which, in turn, means that none of these ranges are unique.) You can verify the existing port ranges for your Conferencing, Application, and Mediation servers by running the following three commands from within the Lync Server 2013 Management Shell:</span></span>

    Get-CsService -ConferencingServer | Select-Object Identity, AudioPortStart, AudioPortCount, VideoPortStart, VideoPortCount, AppSharingPortStart, AppSharingPortCount
    
    Get-CsService -ApplicationServer | Select-Object Identity, AudioPortStart, AudioPortCount
    
    Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount

<div>


> [!WARNING]  
> <span data-ttu-id="7abb6-113">Como puede ver en los comandos anteriores, cada tipo de puerto (audio, vídeo y uso compartido de aplicaciones) tiene asignados dos valores de propiedad distintos: el inicio del puerto y el recuento de puertos.</span><span class="sxs-lookup"><span data-stu-id="7abb6-113">As you can see in the preceding commands, each port type – audio, video, and application sharing – is assigned two separate property values: the port start and the port count.</span></span> <span data-ttu-id="7abb6-114">El inicio del puerto indica el primer puerto utilizado para ese modal; por ejemplo, si el inicio del puerto de audio es igual a 50000, significa que el primer puerto que se usa para el tráfico de audio es el puerto 50000.</span><span class="sxs-lookup"><span data-stu-id="7abb6-114">The port start indicates the first port used for that modality; for example, if the audio port start is equal to 50000 that means that the first port used for audio traffic is port 50000.</span></span> <span data-ttu-id="7abb6-115">Si el recuento de puertos de audio es 2 (que no es un valor válido, pero se usa aquí con fines de ilustración) significa que solo se asignan 2 puertos para el audio.</span><span class="sxs-lookup"><span data-stu-id="7abb6-115">If the audio port count is 2 (which is not a valid value, but is used here for illustration purposes) that means that only 2 ports are allocated for audio.</span></span> <span data-ttu-id="7abb6-116">Si el primer puerto es el puerto 50000 y hay un total de dos puertos, significa que el segundo puerto debe ser el puerto 50001 (los intervalos de puertos deben ser contiguos).</span><span class="sxs-lookup"><span data-stu-id="7abb6-116">If the first port is port 50000 and there are a total of two ports, that means the second port must be port 50001 (port ranges have to be contiguous).</span></span> <span data-ttu-id="7abb6-117">Como resultado, el intervalo de puertos para el audio sería los puertos 50000 a 50001, ambos incluidos.</span><span class="sxs-lookup"><span data-stu-id="7abb6-117">As a result, the port range for audio would be ports 50000 through 50001, inclusive.</span></span><BR><span data-ttu-id="7abb6-118">Ten en cuenta que el servidor de aplicaciones y el servidor de mediación solo admiten QoS para el audio; no es necesario cambiar los puertos de uso compartido de vídeo o aplicaciones en los servidores de aplicaciones o servidores de mediación.</span><span class="sxs-lookup"><span data-stu-id="7abb6-118">Note, too that Application server and Mediation server only support QoS for audio; you do not need to change video or application sharing ports in your Application servers or Mediation servers.</span></span>



</div>

<span data-ttu-id="7abb6-119">Si ejecuta los tres comandos anteriores, verá que los valores de puerto predeterminados de Lync Server 2013 se han configurado de esta manera:</span><span class="sxs-lookup"><span data-stu-id="7abb6-119">If you run the preceding three commands you'll see that the default port values for Lync Server 2013 are configured like this:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7abb6-120">Propiedad</span><span class="sxs-lookup"><span data-stu-id="7abb6-120">Property</span></span></th>
<th><span data-ttu-id="7abb6-121">Servidor de conferencia</span><span class="sxs-lookup"><span data-stu-id="7abb6-121">Conferencing Server</span></span></th>
<th><span data-ttu-id="7abb6-122">Servidor de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="7abb6-122">Application Server</span></span></th>
<th><span data-ttu-id="7abb6-123">Servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="7abb6-123">Mediation Server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7abb6-124">AudioPortStart</span><span class="sxs-lookup"><span data-stu-id="7abb6-124">AudioPortStart</span></span></p></td>
<td><p><span data-ttu-id="7abb6-125">49152</span><span class="sxs-lookup"><span data-stu-id="7abb6-125">49152</span></span></p></td>
<td><p><span data-ttu-id="7abb6-126">49152</span><span class="sxs-lookup"><span data-stu-id="7abb6-126">49152</span></span></p></td>
<td><p><span data-ttu-id="7abb6-127">49152</span><span class="sxs-lookup"><span data-stu-id="7abb6-127">49152</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7abb6-128">AudioPortCount</span><span class="sxs-lookup"><span data-stu-id="7abb6-128">AudioPortCount</span></span></p></td>
<td><p><span data-ttu-id="7abb6-129">8348</span><span class="sxs-lookup"><span data-stu-id="7abb6-129">8348</span></span></p></td>
<td><p><span data-ttu-id="7abb6-130">8348</span><span class="sxs-lookup"><span data-stu-id="7abb6-130">8348</span></span></p></td>
<td><p><span data-ttu-id="7abb6-131">8348</span><span class="sxs-lookup"><span data-stu-id="7abb6-131">8348</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7abb6-132">VideoPortStart</span><span class="sxs-lookup"><span data-stu-id="7abb6-132">VideoPortStart</span></span></p></td>
<td><p><span data-ttu-id="7abb6-133">57501</span><span class="sxs-lookup"><span data-stu-id="7abb6-133">57501</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7abb6-134">VideoPortCount</span><span class="sxs-lookup"><span data-stu-id="7abb6-134">VideoPortCount</span></span></p></td>
<td><p><span data-ttu-id="7abb6-135">8034</span><span class="sxs-lookup"><span data-stu-id="7abb6-135">8034</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7abb6-136">ApplicationSharingPortStart</span><span class="sxs-lookup"><span data-stu-id="7abb6-136">ApplicationSharingPortStart</span></span></p></td>
<td><p><span data-ttu-id="7abb6-137">49152</span><span class="sxs-lookup"><span data-stu-id="7abb6-137">49152</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7abb6-138">ApplicationSharingPortCount</span><span class="sxs-lookup"><span data-stu-id="7abb6-138">ApplicationSharingPortCount</span></span></p></td>
<td><p><span data-ttu-id="7abb6-139">16383</span><span class="sxs-lookup"><span data-stu-id="7abb6-139">16383</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="7abb6-140">Como se mencionó anteriormente, al configurar los puertos de Lync Server para QoS, debe asegurarse de que: 1) la configuración del puerto de audio sea idéntica en los servidores de conferencias, aplicaciones y mediación. y 2) los intervalos de puertos no se superponen.</span><span class="sxs-lookup"><span data-stu-id="7abb6-140">As noted previously, when configuring Lync Server ports for QoS, you should ensure that: 1) audio port settings are identical across yours Conferencing, Application, and Mediation servers; and, 2) port ranges do not overlap.</span></span> <span data-ttu-id="7abb6-141">Si examina atentamente la tabla anterior, verá que los intervalos de puertos son idénticos en los tres tipos de servidor.</span><span class="sxs-lookup"><span data-stu-id="7abb6-141">If you look closely at the preceding table, you will see that the port ranges are identical across the three server types.</span></span> <span data-ttu-id="7abb6-142">Por ejemplo, el puerto de salida de audio se establece en el puerto 49152 en cada tipo de servidor, y el número total de puertos reservados para el audio en cada servidor también es idéntico: 8348.</span><span class="sxs-lookup"><span data-stu-id="7abb6-142">For example, the starting audio port is set to port 49152 on each server type, and the total number of ports reserved for audio in each server is also identical: 8348.</span></span> <span data-ttu-id="7abb6-143">Sin embargo, los intervalos de puertos se superponen: los puertos de audio comienzan en el puerto 49152, pero también hacen que los puertos reservados para uso compartido de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="7abb6-143">However, the port ranges overlap: audio ports start at port 49152, but so do the ports set aside for application sharing.</span></span> <span data-ttu-id="7abb6-144">Para hacer uso óptimo de la calidad de servicio, el uso compartido de aplicaciones debe reconfigurarse para que use un intervalo de puertos único.</span><span class="sxs-lookup"><span data-stu-id="7abb6-144">In order to make optimal use of Quality of Service, application sharing should be reconfigured to use a unique port range.</span></span> <span data-ttu-id="7abb6-145">Por ejemplo, puede configurar el uso compartido de aplicaciones para que se inicie en el puerto 40803 y para usar puertos 8348.</span><span class="sxs-lookup"><span data-stu-id="7abb6-145">For example, you could configure application sharing to start at port 40803 and to use 8348 ports.</span></span> <span data-ttu-id="7abb6-146">(¿Por qué 8348 puertos?</span><span class="sxs-lookup"><span data-stu-id="7abb6-146">(Why 8348 ports?</span></span> <span data-ttu-id="7abb6-147">Si suma esos valores juntos, 40803 + 8348, eso significa que el uso compartido de aplicaciones usará los puertos 40803 a través del puerto 49150.</span><span class="sxs-lookup"><span data-stu-id="7abb6-147">If you add those values together -- 40803 + 8348 -- that means that application sharing will use ports 40803 through port 49150.</span></span> <span data-ttu-id="7abb6-148">Puesto que los puertos de audio no comienzan hasta el puerto 49152, ya no tendrá intervalos de puertos superpuestos.)</span><span class="sxs-lookup"><span data-stu-id="7abb6-148">Because audio ports do not begin until port 49152, you will no longer have any overlapping port ranges.)</span></span>

<span data-ttu-id="7abb6-149">Una vez que haya seleccionado el nuevo intervalo de puertos para compartir aplicaciones, puede realizar su cambio con el cmdlet Set-CsConferencingServer.</span><span class="sxs-lookup"><span data-stu-id="7abb6-149">After you have selected the new port range for application sharing you can make your change by using the Set-CsConferencingServer cmdlet.</span></span> <span data-ttu-id="7abb6-150">No es necesario realizar este cambio en los servidores de aplicaciones o en los servidores de mediación, ya que estos servidores no manejan tráfico de uso compartido de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="7abb6-150">This change does not need to be made on your Application servers or on your Mediation servers, because these servers do not handle application sharing traffic.</span></span> <span data-ttu-id="7abb6-151">Solo necesita cambiar los valores de puerto en estos servidores si decide reasignar los puertos usados para el tráfico de audio.</span><span class="sxs-lookup"><span data-stu-id="7abb6-151">You only need to change port values on these servers if you decide to reassign the ports used for audio traffic.</span></span>

<span data-ttu-id="7abb6-152">Para modificar los valores de puerto para el uso compartido de aplicaciones en un solo servidor de conferencia ejecute un comando similar a este desde el shell de administración de Lync Server:</span><span class="sxs-lookup"><span data-stu-id="7abb6-152">To modify the port values for application sharing on a single Conferencing server run a command similar to this from within the Lync Server Management Shell:</span></span>

    Set-CsConferenceServer -Identity ConferencingServer:atl-cs-001.litwareinc.com -AppSharingPortStart 40803 -AppSharingPortCount 8348

<span data-ttu-id="7abb6-153">Si desea realizar estos cambios en todos los servidores de conferencia, puede ejecutar este comando en su lugar:</span><span class="sxs-lookup"><span data-stu-id="7abb6-153">If you want to make these changes on all your Conferencing servers you can run this command instead:</span></span>

    Get-CsService -ConferencingServer | ForEach-Object {Set-CsConferenceServer -Identity $_.Identity -AppSharingPortStart 40803 -AppSharingPortCount 8348}

<span data-ttu-id="7abb6-154">Después de cambiar la configuración del puerto, debe detener y reiniciar cada servicio afectado por los cambios.</span><span class="sxs-lookup"><span data-stu-id="7abb6-154">After changing port settings you should stop and then restart each service affected by the changes.</span></span>

<span data-ttu-id="7abb6-155">No es obligatorio que los servidores de conferencia, los servidores de aplicaciones y los servidores de mediación compartan exactamente el mismo intervalo de puertos; el único requisito es que se reserven intervalos de puertos exclusivos en todos los servidores.</span><span class="sxs-lookup"><span data-stu-id="7abb6-155">It is not mandatory that your Conferencing servers, Application servers, and Mediation servers share the exact same port range; the only true requirement is that you set aside unique port ranges on all your servers.</span></span> <span data-ttu-id="7abb6-156">Sin embargo, la administración generalmente será más fácil si usa el mismo conjunto de puertos en todos los servidores.</span><span class="sxs-lookup"><span data-stu-id="7abb6-156">However, administration will typically be easier if you use the same set of ports on all your servers.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

