---
title: 'Lync Server 2013: Tabla AudioClientEvent'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AudioClientEvent table
ms:assetid: fef73d8f-7261-4e5b-9769-82435b007979
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413086(v=OCS.15)
ms:contentKeyID: 48185967
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44d5146b334af83618ca2dd6261a18e72708f4f5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722630"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audioclientevent-table-in-lync-server-2013"></a><span data-ttu-id="a0468-102">Tabla AudioClientEvent en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a0468-102">AudioClientEvent table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a0468-103">_**Última modificación del tema:** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="a0468-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="a0468-104">Cada registro contiene un evento de cliente para un punto final en una llamada de audio.</span><span class="sxs-lookup"><span data-stu-id="a0468-104">Each record contains a client event for one endpoint in an audio call.</span></span> <span data-ttu-id="a0468-105">Generalmente, una llamada tiene dos registros: uno para el autor de la llamada y otro para el destinatario.</span><span class="sxs-lookup"><span data-stu-id="a0468-105">Usually, one call has two records, one for caller and one for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a0468-106"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="a0468-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="a0468-107"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="a0468-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="a0468-108"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="a0468-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="a0468-109"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="a0468-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a0468-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="a0468-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a0468-111">datetime</span><span class="sxs-lookup"><span data-stu-id="a0468-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="a0468-112">Primary</span><span class="sxs-lookup"><span data-stu-id="a0468-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="a0468-113">Se hace referencia a ellos desde la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="a0468-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0468-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="a0468-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="a0468-115">int</span><span class="sxs-lookup"><span data-stu-id="a0468-115">int</span></span></p></td>
<td><p><span data-ttu-id="a0468-116">Primary</span><span class="sxs-lookup"><span data-stu-id="a0468-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="a0468-117">Se hace referencia a ellos desde la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="a0468-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0468-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="a0468-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="a0468-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="a0468-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="a0468-120">Primary</span><span class="sxs-lookup"><span data-stu-id="a0468-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="a0468-121">Se hace referencia a ellos desde la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="a0468-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0468-122"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="a0468-122"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="a0468-123">bit</span><span class="sxs-lookup"><span data-stu-id="a0468-123">bit</span></span></p></td>
<td><p><span data-ttu-id="a0468-124">Primary</span><span class="sxs-lookup"><span data-stu-id="a0468-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="a0468-125">0: datos del destinatario de la llamada</span><span class="sxs-lookup"><span data-stu-id="a0468-125">0: Callee’s data</span></span></p>
<p><span data-ttu-id="a0468-126">1: datos del autor de la llamada</span><span class="sxs-lookup"><span data-stu-id="a0468-126">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0468-127"><strong>NetworkSendQualityEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="a0468-127"><strong>NetworkSendQualityEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="a0468-128">decimal (4,5)</span><span class="sxs-lookup"><span data-stu-id="a0468-128">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a0468-129">Porcentaje de sesión el evento NetworkSendQuality se activó por el estado "incorrecto".</span><span class="sxs-lookup"><span data-stu-id="a0468-129">Percentage of session the NetworkSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="a0468-130">La calidad de la red en términos de vibración o pérdida de paquetes es grave y afecta a la calidad del audio que se envía.</span><span class="sxs-lookup"><span data-stu-id="a0468-130">Network quality in terms of jitter or packet loss is severe and impacting the quality of audio being sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0468-131"><strong>NetworkReceiveQualityEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="a0468-131"><strong>NetworkReceiveQualityEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="a0468-132">decimal (4,5)</span><span class="sxs-lookup"><span data-stu-id="a0468-132">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a0468-133">Porcentaje de sesión el evento ReceiveSendQuality se activó por el estado "incorrecto".</span><span class="sxs-lookup"><span data-stu-id="a0468-133">Percentage of session the ReceiveSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="a0468-134">La calidad de la red en términos de vibración o pérdida de paquetes es grave y afecta la calidad de audio que se recibe.</span><span class="sxs-lookup"><span data-stu-id="a0468-134">Network quality in terms of jitter or packet loss is severe and impacting the quality of audio being received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0468-135"><strong>NetworkDelayEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="a0468-135"><strong>NetworkDelayEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="a0468-136">decimal (4,5)</span><span class="sxs-lookup"><span data-stu-id="a0468-136">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a0468-137">Porcentaje de la sesión el evento de retraso se activó para el estado "incorrecto".</span><span class="sxs-lookup"><span data-stu-id="a0468-137">Percentage of session the Delay event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="a0468-138">La latencia de la red es grave y afecta a la experiencia al evitar la comunicación interactiva</span><span class="sxs-lookup"><span data-stu-id="a0468-138">Network latency is severe and impacting the experience by preventing interactive communication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0468-139"><strong>NetworkBandwidthLowEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="a0468-139"><strong>NetworkBandwidthLowEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="a0468-140">decimal (4,5)</span><span class="sxs-lookup"><span data-stu-id="a0468-140">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a0468-141">Porcentaje de sesión el evento LowBandwidth se activó por el estado "incorrecto".</span><span class="sxs-lookup"><span data-stu-id="a0468-141">Percentage of session the LowBandwidth event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="a0468-142">El ancho de banda disponible es insuficiente para una experiencia de voz aceptable.</span><span class="sxs-lookup"><span data-stu-id="a0468-142">The available bandwidth is insufficient for an acceptable voice experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0468-143"><strong>CPUInsufficientEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="a0468-143"><strong>CPUInsufficientEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="a0468-144">decimal (4,5)</span><span class="sxs-lookup"><span data-stu-id="a0468-144">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a0468-145">Porcentaje de sesión el evento de CPU insuficiente se activó para el estado "incorrecto".</span><span class="sxs-lookup"><span data-stu-id="a0468-145">Percentage of session the insufficient CPU event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="a0468-146">No hay suficientes ciclos de CPU para procesar con las aplicaciones y las aplicaciones actuales en uso.</span><span class="sxs-lookup"><span data-stu-id="a0468-146">There are insufficient CPU cycles for processing with the current modalities and applications in use.</span></span> <span data-ttu-id="a0468-147">Esto causa distorsiones en el canal de audio.</span><span class="sxs-lookup"><span data-stu-id="a0468-147">This causes distortions with the audio channel.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0468-148"><strong>DeviceHalfDuplexAECEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="a0468-148"><strong>DeviceHalfDuplexAECEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="a0468-149">decimal (4,5)</span><span class="sxs-lookup"><span data-stu-id="a0468-149">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a0468-150">Porcentaje de sesión el evento DeviceHalfDuplexAEC se activó por el estado "incorrecto".</span><span class="sxs-lookup"><span data-stu-id="a0468-150">Percentage of session the DeviceHalfDuplexAEC event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="a0468-151">Para evitar que se produzca el eco, el sistema se introduce a doble cara.</span><span class="sxs-lookup"><span data-stu-id="a0468-151">In order to prevent echo, the system has enter half duplex.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0468-152"><strong>DeviceRenderNotFunctioningEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="a0468-152"><strong>DeviceRenderNotFunctioningEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="a0468-153">decimal (4,5)</span><span class="sxs-lookup"><span data-stu-id="a0468-153">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a0468-154">Porcentaje de sesión el evento DeviceRenderNotFunctioning se activó por el estado "incorrecto".</span><span class="sxs-lookup"><span data-stu-id="a0468-154">Percentage of session the DeviceRenderNotFunctioning event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="a0468-155">El dispositivo de representación que se usa actualmente para la sesión no funciona correctamente.</span><span class="sxs-lookup"><span data-stu-id="a0468-155">The render device currently being used for the session is not functioning correctly.</span></span> <span data-ttu-id="a0468-156">Esto puede dar lugar a problemas de audio unidireccionales.</span><span class="sxs-lookup"><span data-stu-id="a0468-156">This can cause one-way audio issues.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0468-157"><strong>DeviceCaptureNotFunctioningEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="a0468-157"><strong>DeviceCaptureNotFunctioningEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="a0468-158">decimal (4,5)</span><span class="sxs-lookup"><span data-stu-id="a0468-158">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a0468-159">Porcentaje de sesión el evento DeviceCaptureNotFunctioning se activó por el estado "incorrecto".</span><span class="sxs-lookup"><span data-stu-id="a0468-159">Percentage of session the DeviceCaptureNotFunctioning event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="a0468-160">El dispositivo de captura usado actualmente para la sesión no funciona correctamente.</span><span class="sxs-lookup"><span data-stu-id="a0468-160">The capture device currently being used for the session is not functioning correctly.</span></span> <span data-ttu-id="a0468-161">Esto puede dar lugar a problemas de audio unidireccionales.</span><span class="sxs-lookup"><span data-stu-id="a0468-161">This can cause one-way audio issues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0468-162"><strong>DeviceGlitchesEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="a0468-162"><strong>DeviceGlitchesEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="a0468-163">decimal (4,5)</span><span class="sxs-lookup"><span data-stu-id="a0468-163">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a0468-164">Porcentaje de sesión el evento DeviceGlitches se activó por el estado "incorrecto".</span><span class="sxs-lookup"><span data-stu-id="a0468-164">Percentage of session the DeviceGlitches event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="a0468-165">Hay problemas graves en la representación de audio que causan distorsiones.</span><span class="sxs-lookup"><span data-stu-id="a0468-165">There are severe glitches in the rendering of audio which is causing distortions.</span></span> <span data-ttu-id="a0468-166">Estos problemas pueden estar causados por problemas de controlador, tormentas de llamadas a procedimiento diferidas (DPC) y uso intensivo de la CPU.</span><span class="sxs-lookup"><span data-stu-id="a0468-166">These glitches can be caused by driver issues, deferred procedure calls (DPC) storm (drivers), and high CPU usage.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0468-167"><strong>DeviceLowSNREventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="a0468-167"><strong>DeviceLowSNREventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="a0468-168">decimal (4,5)</span><span class="sxs-lookup"><span data-stu-id="a0468-168">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a0468-169">Porcentaje de sesión el evento DeviceLowSNR se activó por el estado "incorrecto".</span><span class="sxs-lookup"><span data-stu-id="a0468-169">Percentage of session the DeviceLowSNR event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="a0468-170">La calidad de la captura es muy mala, ya sea muy ruidosa o el usuario habla demasiado lejos del micrófono.</span><span class="sxs-lookup"><span data-stu-id="a0468-170">The capture quality is very poor, either very noisy or user is talking too far away from the microphone.</span></span> <span data-ttu-id="a0468-171">Esto provocará distorsiones.</span><span class="sxs-lookup"><span data-stu-id="a0468-171">This will cause distortions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0468-172"><strong>DeviceLowSpeechLevelEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="a0468-172"><strong>DeviceLowSpeechLevelEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="a0468-173">decimal (4,5)</span><span class="sxs-lookup"><span data-stu-id="a0468-173">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a0468-174">Porcentaje de sesión el evento DeviceLowSpeechLevel se activó por el estado "incorrecto".</span><span class="sxs-lookup"><span data-stu-id="a0468-174">Percentage of session the DeviceLowSpeechLevel event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="a0468-175">El nivel de voz del usuario es demasiado bajo y el sistema no puede aumentarlo.</span><span class="sxs-lookup"><span data-stu-id="a0468-175">User‘s speech level is too low and the system cannot increase it any further.</span></span> <span data-ttu-id="a0468-176">Esto puede causar distorsiones o percibir como audio unidireccional.</span><span class="sxs-lookup"><span data-stu-id="a0468-176">This can either cause distortions or perceived as one-way audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0468-177"><strong>DeviceClippingEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="a0468-177"><strong>DeviceClippingEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="a0468-178">Decimal (4,5)</span><span class="sxs-lookup"><span data-stu-id="a0468-178">Decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a0468-179">Porcentaje de sesión el evento DeviceClipping se activó por el estado "incorrecto".</span><span class="sxs-lookup"><span data-stu-id="a0468-179">Percentage of session the DeviceClipping event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="a0468-180">Cuando los recortes de voz próximos se recortan, el micrófono escucha la distorsión del extremo a causa de la recorte.</span><span class="sxs-lookup"><span data-stu-id="a0468-180">When near-end speech clips the microphone, far-end hears distortion due to clipping.</span></span> <span data-ttu-id="a0468-181">Es importante evitar el recorte de micrófono cerca de la final.</span><span class="sxs-lookup"><span data-stu-id="a0468-181">It is important to avoid near-end microphone clipping.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0468-182"><strong>DeviceEchoEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="a0468-182"><strong>DeviceEchoEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="a0468-183">decimal (4,5)</span><span class="sxs-lookup"><span data-stu-id="a0468-183">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a0468-184">Porcentaje de sesión el evento DeviceEchoEvent se activó por el estado "incorrecto".</span><span class="sxs-lookup"><span data-stu-id="a0468-184">Percentage of session the DeviceEchoEvent event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="a0468-185">El dispositivo o el programa de instalación está causando eco más allá de la capacidad del sistema para compensar.</span><span class="sxs-lookup"><span data-stu-id="a0468-185">Device or setup is causing echo beyond the ability of the system to compensate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0468-186"><strong>DeviceNearEndToEchoRatioEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="a0468-186"><strong>DeviceNearEndToEchoRatioEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="a0468-187">decimal (4,5)</span><span class="sxs-lookup"><span data-stu-id="a0468-187">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a0468-188">Porcentaje de sesión el evento DeviceNearEndToEchoRatio se activó por el estado "incorrecto".</span><span class="sxs-lookup"><span data-stu-id="a0468-188">Percentage of session the DeviceNearEndToEchoRatio event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="a0468-189">La voz del usuario es demasiado baja en comparación con el eco que se está capturando y que afecta a la experiencia de los usuarios porque limita lo fácil que es interrumpir a un usuario.</span><span class="sxs-lookup"><span data-stu-id="a0468-189">The user’s speech is too low compared to the echo being captured which impacts the users experience because it limits how easy it is to interrupt a user.</span></span> <span data-ttu-id="a0468-190">Reduce el volumen del altavoz, mueve el micrófono cerca de la Talker.</span><span class="sxs-lookup"><span data-stu-id="a0468-190">Reduce speaker volume, move the microphone closer to the talker.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0468-191"><strong>DeviceMultipleEndpointsEventCount</strong></span><span class="sxs-lookup"><span data-stu-id="a0468-191"><strong>DeviceMultipleEndpointsEventCount</strong></span></span></p></td>
<td><p><span data-ttu-id="a0468-192">int</span><span class="sxs-lookup"><span data-stu-id="a0468-192">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a0468-193">Número de veces durante la sesión el evento DeviceMultipleEndpoints se activó por el estado "incorrecto".</span><span class="sxs-lookup"><span data-stu-id="a0468-193">Number of times during session the DeviceMultipleEndpoints event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="a0468-194">Se detectaron varios puntos de conexión de audio en la misma sesión y el sistema se ha compensado al reducir el volumen de representación.</span><span class="sxs-lookup"><span data-stu-id="a0468-194">Multiple audio endpoints in the same session detected and the system has compensated by reducing render volume.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0468-195"><strong>DeviceHowlingEventCount</strong></span><span class="sxs-lookup"><span data-stu-id="a0468-195"><strong>DeviceHowlingEventCount</strong></span></span></p></td>
<td><p><span data-ttu-id="a0468-196">int</span><span class="sxs-lookup"><span data-stu-id="a0468-196">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a0468-197">Número de veces durante la sesión el evento DeviceHowlingEvent se activó por el estado "incorrecto".</span><span class="sxs-lookup"><span data-stu-id="a0468-197">Number of times during session the DeviceHowlingEvent event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="a0468-198">Se detectó un bucle de comentarios de audio (causado por varios puntos de conexión que comparten la ruta de audio).</span><span class="sxs-lookup"><span data-stu-id="a0468-198">Audio feedback loop detected (caused by multiple endpoints sharing audio path).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0468-199"><strong>DeviceRenderZeroVolumeEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="a0468-199"><strong>DeviceRenderZeroVolumeEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="a0468-200">decimal (4,5)</span><span class="sxs-lookup"><span data-stu-id="a0468-200">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a0468-201">Porcentaje de sesión el evento DeviceRenderZeroVolume se activó por estar en el estado "incorrecto".</span><span class="sxs-lookup"><span data-stu-id="a0468-201">Percentage of session the DeviceRenderZeroVolume event was fired for being in the “Bad’ state.</span></span> <span data-ttu-id="a0468-202">El dispositivo de representación se estableció en un volumen de cero.</span><span class="sxs-lookup"><span data-stu-id="a0468-202">The render device was set to zero volume.</span></span></p>
<p><span data-ttu-id="a0468-203">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a0468-203">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0468-204"><strong>DeviceRenderMuteEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="a0468-204"><strong>DeviceRenderMuteEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="a0468-205">decimal (4,5)</span><span class="sxs-lookup"><span data-stu-id="a0468-205">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a0468-206">Porcentaje de sesión el evento DeviceRenderMute se activó por estar en el estado "incorrecto".</span><span class="sxs-lookup"><span data-stu-id="a0468-206">Percentage of session the DeviceRenderMute event was fired for being in the “Bad’ state.</span></span> <span data-ttu-id="a0468-207">El dispositivo de representación se ha silenciado.</span><span class="sxs-lookup"><span data-stu-id="a0468-207">The render device was muted.</span></span></p>
<p><span data-ttu-id="a0468-208">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a0468-208">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

