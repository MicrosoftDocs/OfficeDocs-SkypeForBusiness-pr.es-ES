---
title: 'Lync Server 2013: tabla AudioClientEvent'
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
ms.openlocfilehash: 53f43bdae2fd134e851c93be958aa671657489e1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044602"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audioclientevent-table-in-lync-server-2013"></a><span data-ttu-id="cfb1e-102">Tabla AudioClientEvent en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cfb1e-102">AudioClientEvent table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cfb1e-103">_**Última modificación del tema:** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="cfb1e-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="cfb1e-104">Cada registro contiene un evento de cliente para un punto de conexión en una llamada de audio.</span><span class="sxs-lookup"><span data-stu-id="cfb1e-104">Each record contains a client event for one endpoint in an audio call.</span></span> <span data-ttu-id="cfb1e-105">Normalmente, una llamada tiene dos registros: uno para el autor de la llamada y otro para el destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="cfb1e-105">Usually, one call has two records, one for caller and one for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cfb1e-106"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="cfb1e-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="cfb1e-107"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="cfb1e-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="cfb1e-108"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="cfb1e-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="cfb1e-109"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="cfb1e-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cfb1e-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="cfb1e-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="cfb1e-111">datetime</span><span class="sxs-lookup"><span data-stu-id="cfb1e-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="cfb1e-112">Principal</span><span class="sxs-lookup"><span data-stu-id="cfb1e-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="cfb1e-113">Referencia de la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="cfb1e-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cfb1e-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="cfb1e-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="cfb1e-115">int</span><span class="sxs-lookup"><span data-stu-id="cfb1e-115">int</span></span></p></td>
<td><p><span data-ttu-id="cfb1e-116">Principal</span><span class="sxs-lookup"><span data-stu-id="cfb1e-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="cfb1e-117">Referencia de la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="cfb1e-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cfb1e-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="cfb1e-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="cfb1e-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="cfb1e-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="cfb1e-120">Principal</span><span class="sxs-lookup"><span data-stu-id="cfb1e-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="cfb1e-121">Referencia de la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="cfb1e-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cfb1e-122"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="cfb1e-122"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="cfb1e-123">bit</span><span class="sxs-lookup"><span data-stu-id="cfb1e-123">bit</span></span></p></td>
<td><p><span data-ttu-id="cfb1e-124">Principal</span><span class="sxs-lookup"><span data-stu-id="cfb1e-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="cfb1e-125">0: datos del destinatario de la llamada</span><span class="sxs-lookup"><span data-stu-id="cfb1e-125">0: Callee’s data</span></span></p>
<p><span data-ttu-id="cfb1e-126">1: datos del autor de la llamada</span><span class="sxs-lookup"><span data-stu-id="cfb1e-126">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cfb1e-127"><strong>NetworkSendQualityEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="cfb1e-127"><strong>NetworkSendQualityEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="cfb1e-128">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="cfb1e-128">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="cfb1e-129">Porcentaje de sesión en la que se activó el evento NetworkSendQuality para un estado "incorrecto".</span><span class="sxs-lookup"><span data-stu-id="cfb1e-129">Percentage of session the NetworkSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="cfb1e-130">La calidad de la red en términos de vibración o pérdida de paquetes es grave y afecta a la calidad del audio que se envía.</span><span class="sxs-lookup"><span data-stu-id="cfb1e-130">Network quality in terms of jitter or packet loss is severe and impacting the quality of audio being sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cfb1e-131"><strong>NetworkReceiveQualityEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="cfb1e-131"><strong>NetworkReceiveQualityEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="cfb1e-132">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="cfb1e-132">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="cfb1e-133">Porcentaje de sesión en la que se activó el evento ReceiveSendQuality para un estado "incorrecto".</span><span class="sxs-lookup"><span data-stu-id="cfb1e-133">Percentage of session the ReceiveSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="cfb1e-134">La calidad de la red en términos de vibración o pérdida de paquetes es grave y afecta a la calidad del audio que se recibe.</span><span class="sxs-lookup"><span data-stu-id="cfb1e-134">Network quality in terms of jitter or packet loss is severe and impacting the quality of audio being received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cfb1e-135"><strong>NetworkDelayEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="cfb1e-135"><strong>NetworkDelayEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="cfb1e-136">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="cfb1e-136">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="cfb1e-137">Porcentaje de sesión el evento Delay se activó para el estado "Bad".</span><span class="sxs-lookup"><span data-stu-id="cfb1e-137">Percentage of session the Delay event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="cfb1e-138">La latencia de red es grave y afecta a la experiencia al evitar la comunicación interactiva</span><span class="sxs-lookup"><span data-stu-id="cfb1e-138">Network latency is severe and impacting the experience by preventing interactive communication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cfb1e-139"><strong>NetworkBandwidthLowEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="cfb1e-139"><strong>NetworkBandwidthLowEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="cfb1e-140">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="cfb1e-140">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="cfb1e-141">Porcentaje de sesión en la que se activó el evento LowBandwidth para un estado "incorrecto".</span><span class="sxs-lookup"><span data-stu-id="cfb1e-141">Percentage of session the LowBandwidth event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="cfb1e-142">El ancho de banda disponible es insuficiente para una experiencia de voz aceptable.</span><span class="sxs-lookup"><span data-stu-id="cfb1e-142">The available bandwidth is insufficient for an acceptable voice experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cfb1e-143"><strong>CPUInsufficientEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="cfb1e-143"><strong>CPUInsufficientEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="cfb1e-144">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="cfb1e-144">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="cfb1e-145">Porcentaje de sesión el evento de CPU insuficiente se activó para el estado "incorrecto".</span><span class="sxs-lookup"><span data-stu-id="cfb1e-145">Percentage of session the insufficient CPU event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="cfb1e-146">No hay ciclos de CPU suficientes para el procesamiento con las aplicaciones actuales y las aplicaciones en uso.</span><span class="sxs-lookup"><span data-stu-id="cfb1e-146">There are insufficient CPU cycles for processing with the current modalities and applications in use.</span></span> <span data-ttu-id="cfb1e-147">Esto causa distorsiones con el canal de audio.</span><span class="sxs-lookup"><span data-stu-id="cfb1e-147">This causes distortions with the audio channel.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cfb1e-148"><strong>DeviceHalfDuplexAECEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="cfb1e-148"><strong>DeviceHalfDuplexAECEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="cfb1e-149">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="cfb1e-149">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="cfb1e-150">Porcentaje de sesión en la que se activó el evento DeviceHalfDuplexAEC para un estado "incorrecto".</span><span class="sxs-lookup"><span data-stu-id="cfb1e-150">Percentage of session the DeviceHalfDuplexAEC event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="cfb1e-151">Para evitar el eco, el sistema tiene que tener un dúplex medio.</span><span class="sxs-lookup"><span data-stu-id="cfb1e-151">In order to prevent echo, the system has enter half duplex.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cfb1e-152"><strong>DeviceRenderNotFunctioningEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="cfb1e-152"><strong>DeviceRenderNotFunctioningEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="cfb1e-153">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="cfb1e-153">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="cfb1e-154">Porcentaje de sesión en la que se activó el evento DeviceRenderNotFunctioning para un estado "incorrecto".</span><span class="sxs-lookup"><span data-stu-id="cfb1e-154">Percentage of session the DeviceRenderNotFunctioning event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="cfb1e-155">El dispositivo de representación que se está usando actualmente para la sesión no funciona correctamente.</span><span class="sxs-lookup"><span data-stu-id="cfb1e-155">The render device currently being used for the session is not functioning correctly.</span></span> <span data-ttu-id="cfb1e-156">Esto puede provocar problemas de audio en una dirección.</span><span class="sxs-lookup"><span data-stu-id="cfb1e-156">This can cause one-way audio issues.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cfb1e-157"><strong>DeviceCaptureNotFunctioningEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="cfb1e-157"><strong>DeviceCaptureNotFunctioningEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="cfb1e-158">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="cfb1e-158">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="cfb1e-159">Porcentaje de sesión en la que se activó el evento DeviceCaptureNotFunctioning para un estado "incorrecto".</span><span class="sxs-lookup"><span data-stu-id="cfb1e-159">Percentage of session the DeviceCaptureNotFunctioning event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="cfb1e-160">El dispositivo de captura que se está usando actualmente para la sesión no funciona correctamente.</span><span class="sxs-lookup"><span data-stu-id="cfb1e-160">The capture device currently being used for the session is not functioning correctly.</span></span> <span data-ttu-id="cfb1e-161">Esto puede provocar problemas de audio en una dirección.</span><span class="sxs-lookup"><span data-stu-id="cfb1e-161">This can cause one-way audio issues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cfb1e-162"><strong>DeviceGlitchesEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="cfb1e-162"><strong>DeviceGlitchesEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="cfb1e-163">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="cfb1e-163">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="cfb1e-164">Porcentaje de sesión en la que se activó el evento DeviceGlitches para un estado "incorrecto".</span><span class="sxs-lookup"><span data-stu-id="cfb1e-164">Percentage of session the DeviceGlitches event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="cfb1e-165">Hay problemas graves en la representación del audio que está causando distorsiones.</span><span class="sxs-lookup"><span data-stu-id="cfb1e-165">There are severe glitches in the rendering of audio which is causing distortions.</span></span> <span data-ttu-id="cfb1e-166">Estos problemas pueden deberse a problemas de controladores, a las llamadas de procedimiento diferido (DPC) y al uso intensivo de la CPU.</span><span class="sxs-lookup"><span data-stu-id="cfb1e-166">These glitches can be caused by driver issues, deferred procedure calls (DPC) storm (drivers), and high CPU usage.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cfb1e-167"><strong>DeviceLowSNREventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="cfb1e-167"><strong>DeviceLowSNREventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="cfb1e-168">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="cfb1e-168">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="cfb1e-169">Porcentaje de sesión en la que se activó el evento DeviceLowSNR para un estado "incorrecto".</span><span class="sxs-lookup"><span data-stu-id="cfb1e-169">Percentage of session the DeviceLowSNR event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="cfb1e-170">La calidad de la captura es muy mala, ya sea muy ruidosa o el usuario está hablando demasiado lejos del micrófono.</span><span class="sxs-lookup"><span data-stu-id="cfb1e-170">The capture quality is very poor, either very noisy or user is talking too far away from the microphone.</span></span> <span data-ttu-id="cfb1e-171">Esto hará que se produzcan distorsiones.</span><span class="sxs-lookup"><span data-stu-id="cfb1e-171">This will cause distortions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cfb1e-172"><strong>DeviceLowSpeechLevelEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="cfb1e-172"><strong>DeviceLowSpeechLevelEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="cfb1e-173">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="cfb1e-173">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="cfb1e-174">Porcentaje de sesión en la que se activó el evento DeviceLowSpeechLevel para un estado "incorrecto".</span><span class="sxs-lookup"><span data-stu-id="cfb1e-174">Percentage of session the DeviceLowSpeechLevel event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="cfb1e-175">El nivel de voz del usuario es demasiado bajo y el sistema no puede aumentarlo más.</span><span class="sxs-lookup"><span data-stu-id="cfb1e-175">User‘s speech level is too low and the system cannot increase it any further.</span></span> <span data-ttu-id="cfb1e-176">Esto puede causar distorsiones o percibirse como un audio unidireccional.</span><span class="sxs-lookup"><span data-stu-id="cfb1e-176">This can either cause distortions or perceived as one-way audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cfb1e-177"><strong>DeviceClippingEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="cfb1e-177"><strong>DeviceClippingEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="cfb1e-178">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="cfb1e-178">Decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="cfb1e-179">Porcentaje de sesión en la que se activó el evento DeviceClipping para un estado "incorrecto".</span><span class="sxs-lookup"><span data-stu-id="cfb1e-179">Percentage of session the DeviceClipping event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="cfb1e-180">Cuando la voz próxima a la vez recorta el micrófono, la distorsión del extremo final oirá una distorsión debido al recorte.</span><span class="sxs-lookup"><span data-stu-id="cfb1e-180">When near-end speech clips the microphone, far-end hears distortion due to clipping.</span></span> <span data-ttu-id="cfb1e-181">Es importante evitar el recorte de micrófono cerca de la finalización.</span><span class="sxs-lookup"><span data-stu-id="cfb1e-181">It is important to avoid near-end microphone clipping.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cfb1e-182"><strong>DeviceEchoEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="cfb1e-182"><strong>DeviceEchoEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="cfb1e-183">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="cfb1e-183">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="cfb1e-184">Porcentaje de sesión en la que se activó el evento resaltó un evento para un estado "incorrecto".</span><span class="sxs-lookup"><span data-stu-id="cfb1e-184">Percentage of session the DeviceEchoEvent event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="cfb1e-185">El dispositivo o el programa de instalación está causando eco más allá de la capacidad del sistema para compensar.</span><span class="sxs-lookup"><span data-stu-id="cfb1e-185">Device or setup is causing echo beyond the ability of the system to compensate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cfb1e-186"><strong>DeviceNearEndToEchoRatioEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="cfb1e-186"><strong>DeviceNearEndToEchoRatioEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="cfb1e-187">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="cfb1e-187">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="cfb1e-188">Porcentaje de sesión en la que se activó el evento DeviceNearEndToEchoRatio para un estado "incorrecto".</span><span class="sxs-lookup"><span data-stu-id="cfb1e-188">Percentage of session the DeviceNearEndToEchoRatio event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="cfb1e-189">La voz del usuario es demasiado baja en comparación con el eco que se está capturando y que afecta a la experiencia de los usuarios, ya que limita lo fácil que resulta interrumpir a un usuario.</span><span class="sxs-lookup"><span data-stu-id="cfb1e-189">The user’s speech is too low compared to the echo being captured which impacts the users experience because it limits how easy it is to interrupt a user.</span></span> <span data-ttu-id="cfb1e-190">Reduce el volumen del altavoz, mueve el micrófono más cerca del Talker.</span><span class="sxs-lookup"><span data-stu-id="cfb1e-190">Reduce speaker volume, move the microphone closer to the talker.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cfb1e-191"><strong>DeviceMultipleEndpointsEventCount</strong></span><span class="sxs-lookup"><span data-stu-id="cfb1e-191"><strong>DeviceMultipleEndpointsEventCount</strong></span></span></p></td>
<td><p><span data-ttu-id="cfb1e-192">int</span><span class="sxs-lookup"><span data-stu-id="cfb1e-192">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cfb1e-193">Número de veces durante la sesión en que se activó el evento DeviceMultipleEndpoints para un estado "incorrecto".</span><span class="sxs-lookup"><span data-stu-id="cfb1e-193">Number of times during session the DeviceMultipleEndpoints event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="cfb1e-194">Se han detectado varios puntos de conexión de audio en la misma sesión y el sistema ha compensado mediante la reducción del volumen de representación.</span><span class="sxs-lookup"><span data-stu-id="cfb1e-194">Multiple audio endpoints in the same session detected and the system has compensated by reducing render volume.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cfb1e-195"><strong>DeviceHowlingEventCount</strong></span><span class="sxs-lookup"><span data-stu-id="cfb1e-195"><strong>DeviceHowlingEventCount</strong></span></span></p></td>
<td><p><span data-ttu-id="cfb1e-196">int</span><span class="sxs-lookup"><span data-stu-id="cfb1e-196">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="cfb1e-197">Número de veces durante la sesión en que se activó el evento DeviceHowlingEvent para un estado "incorrecto".</span><span class="sxs-lookup"><span data-stu-id="cfb1e-197">Number of times during session the DeviceHowlingEvent event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="cfb1e-198">Bucle de comentarios de audio detectado (causado por varios puntos de conexión que comparten la ruta de audio).</span><span class="sxs-lookup"><span data-stu-id="cfb1e-198">Audio feedback loop detected (caused by multiple endpoints sharing audio path).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cfb1e-199"><strong>DeviceRenderZeroVolumeEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="cfb1e-199"><strong>DeviceRenderZeroVolumeEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="cfb1e-200">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="cfb1e-200">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cfb1e-201">Porcentaje de sesión en la que se ha desencadenado el evento DeviceRenderZeroVolume para estar en el estado "incorrecto".</span><span class="sxs-lookup"><span data-stu-id="cfb1e-201">Percentage of session the DeviceRenderZeroVolume event was fired for being in the “Bad’ state.</span></span> <span data-ttu-id="cfb1e-202">El dispositivo de representación se estableció en un volumen de cero.</span><span class="sxs-lookup"><span data-stu-id="cfb1e-202">The render device was set to zero volume.</span></span></p>
<p><span data-ttu-id="cfb1e-203">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cfb1e-203">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cfb1e-204"><strong>DeviceRenderMuteEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="cfb1e-204"><strong>DeviceRenderMuteEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="cfb1e-205">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="cfb1e-205">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cfb1e-206">Porcentaje de sesión en la que se ha desencadenado el evento DeviceRenderMute para estar en el estado "incorrecto".</span><span class="sxs-lookup"><span data-stu-id="cfb1e-206">Percentage of session the DeviceRenderMute event was fired for being in the “Bad’ state.</span></span> <span data-ttu-id="cfb1e-207">El dispositivo de representación está silenciado.</span><span class="sxs-lookup"><span data-stu-id="cfb1e-207">The render device was muted.</span></span></p>
<p><span data-ttu-id="cfb1e-208">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cfb1e-208">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

