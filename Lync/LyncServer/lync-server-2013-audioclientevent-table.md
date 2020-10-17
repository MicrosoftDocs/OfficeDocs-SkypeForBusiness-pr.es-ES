---
title: 'Lync Server 2013: tabla AudioClientEvent'
description: 'Lync Server 2013: tabla AudioClientEvent.'
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
ms.openlocfilehash: 2200cd9567bdd10ac4ad8f5c269062c2f5614dcb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568786"
---
# <a name="audioclientevent-table-in-lync-server-2013"></a><span data-ttu-id="fdcfa-103">Tabla AudioClientEvent en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fdcfa-103">AudioClientEvent table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fdcfa-104">_**Última modificación del tema:** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="fdcfa-104">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="fdcfa-105">Cada registro contiene un evento de cliente para un punto de conexión en una llamada de audio.</span><span class="sxs-lookup"><span data-stu-id="fdcfa-105">Each record contains a client event for one endpoint in an audio call.</span></span> <span data-ttu-id="fdcfa-106">Normalmente, una llamada tiene dos registros: uno para el autor de la llamada y otro para el destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="fdcfa-106">Usually, one call has two records, one for caller and one for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fdcfa-107"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="fdcfa-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="fdcfa-108"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="fdcfa-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="fdcfa-109"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="fdcfa-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="fdcfa-110"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="fdcfa-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fdcfa-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="fdcfa-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="fdcfa-112">datetime</span><span class="sxs-lookup"><span data-stu-id="fdcfa-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="fdcfa-113">Principal</span><span class="sxs-lookup"><span data-stu-id="fdcfa-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="fdcfa-114">Referencia de la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="fdcfa-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdcfa-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="fdcfa-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="fdcfa-116">entero</span><span class="sxs-lookup"><span data-stu-id="fdcfa-116">int</span></span></p></td>
<td><p><span data-ttu-id="fdcfa-117">Principal</span><span class="sxs-lookup"><span data-stu-id="fdcfa-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="fdcfa-118">Referencia de la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="fdcfa-118">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdcfa-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="fdcfa-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="fdcfa-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="fdcfa-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="fdcfa-121">Principal</span><span class="sxs-lookup"><span data-stu-id="fdcfa-121">Primary</span></span></p></td>
<td><p><span data-ttu-id="fdcfa-122">Referencia de la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="fdcfa-122">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdcfa-123"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="fdcfa-123"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="fdcfa-124">bit</span><span class="sxs-lookup"><span data-stu-id="fdcfa-124">bit</span></span></p></td>
<td><p><span data-ttu-id="fdcfa-125">Principal</span><span class="sxs-lookup"><span data-stu-id="fdcfa-125">Primary</span></span></p></td>
<td><p><span data-ttu-id="fdcfa-126">0: datos del destinatario de la llamada</span><span class="sxs-lookup"><span data-stu-id="fdcfa-126">0: Callee’s data</span></span></p>
<p><span data-ttu-id="fdcfa-127">1: datos del autor de la llamada</span><span class="sxs-lookup"><span data-stu-id="fdcfa-127">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdcfa-128"><strong>NetworkSendQualityEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="fdcfa-128"><strong>NetworkSendQualityEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="fdcfa-129">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="fdcfa-129">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fdcfa-130">Porcentaje de sesión en la que se activó el evento NetworkSendQuality para un estado "incorrecto".</span><span class="sxs-lookup"><span data-stu-id="fdcfa-130">Percentage of session the NetworkSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="fdcfa-131">La calidad de la red en términos de vibración o pérdida de paquetes es grave y afecta a la calidad del audio que se envía.</span><span class="sxs-lookup"><span data-stu-id="fdcfa-131">Network quality in terms of jitter or packet loss is severe and impacting the quality of audio being sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdcfa-132"><strong>NetworkReceiveQualityEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="fdcfa-132"><strong>NetworkReceiveQualityEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="fdcfa-133">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="fdcfa-133">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fdcfa-134">Porcentaje de sesión en la que se activó el evento ReceiveSendQuality para un estado "incorrecto".</span><span class="sxs-lookup"><span data-stu-id="fdcfa-134">Percentage of session the ReceiveSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="fdcfa-135">La calidad de la red en términos de vibración o pérdida de paquetes es grave y afecta a la calidad del audio que se recibe.</span><span class="sxs-lookup"><span data-stu-id="fdcfa-135">Network quality in terms of jitter or packet loss is severe and impacting the quality of audio being received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdcfa-136"><strong>NetworkDelayEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="fdcfa-136"><strong>NetworkDelayEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="fdcfa-137">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="fdcfa-137">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fdcfa-138">Porcentaje de sesión el evento Delay se activó para el estado "Bad".</span><span class="sxs-lookup"><span data-stu-id="fdcfa-138">Percentage of session the Delay event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="fdcfa-139">La latencia de red es grave y afecta a la experiencia al evitar la comunicación interactiva</span><span class="sxs-lookup"><span data-stu-id="fdcfa-139">Network latency is severe and impacting the experience by preventing interactive communication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdcfa-140"><strong>NetworkBandwidthLowEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="fdcfa-140"><strong>NetworkBandwidthLowEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="fdcfa-141">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="fdcfa-141">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fdcfa-142">Porcentaje de sesión en la que se activó el evento LowBandwidth para un estado "incorrecto".</span><span class="sxs-lookup"><span data-stu-id="fdcfa-142">Percentage of session the LowBandwidth event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="fdcfa-143">El ancho de banda disponible es insuficiente para una experiencia de voz aceptable.</span><span class="sxs-lookup"><span data-stu-id="fdcfa-143">The available bandwidth is insufficient for an acceptable voice experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdcfa-144"><strong>CPUInsufficientEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="fdcfa-144"><strong>CPUInsufficientEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="fdcfa-145">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="fdcfa-145">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fdcfa-146">Porcentaje de sesión el evento de CPU insuficiente se activó para el estado "incorrecto".</span><span class="sxs-lookup"><span data-stu-id="fdcfa-146">Percentage of session the insufficient CPU event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="fdcfa-147">No hay ciclos de CPU suficientes para el procesamiento con las aplicaciones actuales y las aplicaciones en uso.</span><span class="sxs-lookup"><span data-stu-id="fdcfa-147">There are insufficient CPU cycles for processing with the current modalities and applications in use.</span></span> <span data-ttu-id="fdcfa-148">Esto causa distorsiones con el canal de audio.</span><span class="sxs-lookup"><span data-stu-id="fdcfa-148">This causes distortions with the audio channel.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdcfa-149"><strong>DeviceHalfDuplexAECEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="fdcfa-149"><strong>DeviceHalfDuplexAECEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="fdcfa-150">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="fdcfa-150">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fdcfa-151">Porcentaje de sesión en la que se activó el evento DeviceHalfDuplexAEC para un estado "incorrecto".</span><span class="sxs-lookup"><span data-stu-id="fdcfa-151">Percentage of session the DeviceHalfDuplexAEC event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="fdcfa-152">Para evitar el eco, el sistema tiene que tener un dúplex medio.</span><span class="sxs-lookup"><span data-stu-id="fdcfa-152">In order to prevent echo, the system has enter half duplex.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdcfa-153"><strong>DeviceRenderNotFunctioningEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="fdcfa-153"><strong>DeviceRenderNotFunctioningEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="fdcfa-154">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="fdcfa-154">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fdcfa-155">Porcentaje de sesión en la que se activó el evento DeviceRenderNotFunctioning para un estado "incorrecto".</span><span class="sxs-lookup"><span data-stu-id="fdcfa-155">Percentage of session the DeviceRenderNotFunctioning event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="fdcfa-156">El dispositivo de representación que se está usando actualmente para la sesión no funciona correctamente.</span><span class="sxs-lookup"><span data-stu-id="fdcfa-156">The render device currently being used for the session is not functioning correctly.</span></span> <span data-ttu-id="fdcfa-157">Esto puede provocar problemas de audio en una dirección.</span><span class="sxs-lookup"><span data-stu-id="fdcfa-157">This can cause one-way audio issues.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdcfa-158"><strong>DeviceCaptureNotFunctioningEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="fdcfa-158"><strong>DeviceCaptureNotFunctioningEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="fdcfa-159">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="fdcfa-159">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fdcfa-160">Porcentaje de sesión en la que se activó el evento DeviceCaptureNotFunctioning para un estado "incorrecto".</span><span class="sxs-lookup"><span data-stu-id="fdcfa-160">Percentage of session the DeviceCaptureNotFunctioning event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="fdcfa-161">El dispositivo de captura que se está usando actualmente para la sesión no funciona correctamente.</span><span class="sxs-lookup"><span data-stu-id="fdcfa-161">The capture device currently being used for the session is not functioning correctly.</span></span> <span data-ttu-id="fdcfa-162">Esto puede provocar problemas de audio en una dirección.</span><span class="sxs-lookup"><span data-stu-id="fdcfa-162">This can cause one-way audio issues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdcfa-163"><strong>DeviceGlitchesEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="fdcfa-163"><strong>DeviceGlitchesEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="fdcfa-164">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="fdcfa-164">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fdcfa-165">Porcentaje de sesión en la que se activó el evento DeviceGlitches para un estado "incorrecto".</span><span class="sxs-lookup"><span data-stu-id="fdcfa-165">Percentage of session the DeviceGlitches event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="fdcfa-166">Hay problemas graves en la representación del audio que está causando distorsiones.</span><span class="sxs-lookup"><span data-stu-id="fdcfa-166">There are severe glitches in the rendering of audio which is causing distortions.</span></span> <span data-ttu-id="fdcfa-167">Estos problemas pueden deberse a problemas de controladores, a las llamadas de procedimiento diferido (DPC) y al uso intensivo de la CPU.</span><span class="sxs-lookup"><span data-stu-id="fdcfa-167">These glitches can be caused by driver issues, deferred procedure calls (DPC) storm (drivers), and high CPU usage.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdcfa-168"><strong>DeviceLowSNREventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="fdcfa-168"><strong>DeviceLowSNREventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="fdcfa-169">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="fdcfa-169">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fdcfa-170">Porcentaje de sesión en la que se activó el evento DeviceLowSNR para un estado "incorrecto".</span><span class="sxs-lookup"><span data-stu-id="fdcfa-170">Percentage of session the DeviceLowSNR event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="fdcfa-171">La calidad de la captura es muy mala, ya sea muy ruidosa o el usuario está hablando demasiado lejos del micrófono.</span><span class="sxs-lookup"><span data-stu-id="fdcfa-171">The capture quality is very poor, either very noisy or user is talking too far away from the microphone.</span></span> <span data-ttu-id="fdcfa-172">Esto hará que se produzcan distorsiones.</span><span class="sxs-lookup"><span data-stu-id="fdcfa-172">This will cause distortions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdcfa-173"><strong>DeviceLowSpeechLevelEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="fdcfa-173"><strong>DeviceLowSpeechLevelEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="fdcfa-174">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="fdcfa-174">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fdcfa-175">Porcentaje de sesión en la que se activó el evento DeviceLowSpeechLevel para un estado "incorrecto".</span><span class="sxs-lookup"><span data-stu-id="fdcfa-175">Percentage of session the DeviceLowSpeechLevel event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="fdcfa-176">El nivel de voz del usuario es demasiado bajo y el sistema no puede aumentarlo más.</span><span class="sxs-lookup"><span data-stu-id="fdcfa-176">User‘s speech level is too low and the system cannot increase it any further.</span></span> <span data-ttu-id="fdcfa-177">Esto puede causar distorsiones o percibirse como un audio unidireccional.</span><span class="sxs-lookup"><span data-stu-id="fdcfa-177">This can either cause distortions or perceived as one-way audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdcfa-178"><strong>DeviceClippingEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="fdcfa-178"><strong>DeviceClippingEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="fdcfa-179">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="fdcfa-179">Decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fdcfa-180">Porcentaje de sesión en la que se activó el evento DeviceClipping para un estado "incorrecto".</span><span class="sxs-lookup"><span data-stu-id="fdcfa-180">Percentage of session the DeviceClipping event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="fdcfa-181">Cuando la voz próxima a la vez recorta el micrófono, la distorsión del extremo final oirá una distorsión debido al recorte.</span><span class="sxs-lookup"><span data-stu-id="fdcfa-181">When near-end speech clips the microphone, far-end hears distortion due to clipping.</span></span> <span data-ttu-id="fdcfa-182">Es importante evitar el recorte de micrófono cerca de la finalización.</span><span class="sxs-lookup"><span data-stu-id="fdcfa-182">It is important to avoid near-end microphone clipping.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdcfa-183"><strong>DeviceEchoEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="fdcfa-183"><strong>DeviceEchoEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="fdcfa-184">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="fdcfa-184">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fdcfa-185">Porcentaje de sesión en la que se activó el evento resaltó un evento para un estado "incorrecto".</span><span class="sxs-lookup"><span data-stu-id="fdcfa-185">Percentage of session the DeviceEchoEvent event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="fdcfa-186">El dispositivo o el programa de instalación está causando eco más allá de la capacidad del sistema para compensar.</span><span class="sxs-lookup"><span data-stu-id="fdcfa-186">Device or setup is causing echo beyond the ability of the system to compensate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdcfa-187"><strong>DeviceNearEndToEchoRatioEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="fdcfa-187"><strong>DeviceNearEndToEchoRatioEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="fdcfa-188">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="fdcfa-188">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fdcfa-189">Porcentaje de sesión en la que se activó el evento DeviceNearEndToEchoRatio para un estado "incorrecto".</span><span class="sxs-lookup"><span data-stu-id="fdcfa-189">Percentage of session the DeviceNearEndToEchoRatio event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="fdcfa-190">La voz del usuario es demasiado baja en comparación con el eco que se está capturando y que afecta a la experiencia de los usuarios, ya que limita lo fácil que resulta interrumpir a un usuario.</span><span class="sxs-lookup"><span data-stu-id="fdcfa-190">The user’s speech is too low compared to the echo being captured which impacts the users experience because it limits how easy it is to interrupt a user.</span></span> <span data-ttu-id="fdcfa-191">Reduce el volumen del altavoz, mueve el micrófono más cerca del Talker.</span><span class="sxs-lookup"><span data-stu-id="fdcfa-191">Reduce speaker volume, move the microphone closer to the talker.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdcfa-192"><strong>DeviceMultipleEndpointsEventCount</strong></span><span class="sxs-lookup"><span data-stu-id="fdcfa-192"><strong>DeviceMultipleEndpointsEventCount</strong></span></span></p></td>
<td><p><span data-ttu-id="fdcfa-193">entero</span><span class="sxs-lookup"><span data-stu-id="fdcfa-193">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fdcfa-194">Número de veces durante la sesión en que se activó el evento DeviceMultipleEndpoints para un estado "incorrecto".</span><span class="sxs-lookup"><span data-stu-id="fdcfa-194">Number of times during session the DeviceMultipleEndpoints event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="fdcfa-195">Se han detectado varios puntos de conexión de audio en la misma sesión y el sistema ha compensado mediante la reducción del volumen de representación.</span><span class="sxs-lookup"><span data-stu-id="fdcfa-195">Multiple audio endpoints in the same session detected and the system has compensated by reducing render volume.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdcfa-196"><strong>DeviceHowlingEventCount</strong></span><span class="sxs-lookup"><span data-stu-id="fdcfa-196"><strong>DeviceHowlingEventCount</strong></span></span></p></td>
<td><p><span data-ttu-id="fdcfa-197">entero</span><span class="sxs-lookup"><span data-stu-id="fdcfa-197">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fdcfa-198">Número de veces durante la sesión en que se activó el evento DeviceHowlingEvent para un estado "incorrecto".</span><span class="sxs-lookup"><span data-stu-id="fdcfa-198">Number of times during session the DeviceHowlingEvent event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="fdcfa-199">Bucle de comentarios de audio detectado (causado por varios puntos de conexión que comparten la ruta de audio).</span><span class="sxs-lookup"><span data-stu-id="fdcfa-199">Audio feedback loop detected (caused by multiple endpoints sharing audio path).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdcfa-200"><strong>DeviceRenderZeroVolumeEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="fdcfa-200"><strong>DeviceRenderZeroVolumeEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="fdcfa-201">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="fdcfa-201">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fdcfa-202">Porcentaje de sesión en la que se ha desencadenado el evento DeviceRenderZeroVolume para estar en el estado "incorrecto".</span><span class="sxs-lookup"><span data-stu-id="fdcfa-202">Percentage of session the DeviceRenderZeroVolume event was fired for being in the “Bad’ state.</span></span> <span data-ttu-id="fdcfa-203">El dispositivo de representación se estableció en un volumen de cero.</span><span class="sxs-lookup"><span data-stu-id="fdcfa-203">The render device was set to zero volume.</span></span></p>
<p><span data-ttu-id="fdcfa-204">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fdcfa-204">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdcfa-205"><strong>DeviceRenderMuteEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="fdcfa-205"><strong>DeviceRenderMuteEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="fdcfa-206">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="fdcfa-206">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fdcfa-207">Porcentaje de sesión en la que se ha desencadenado el evento DeviceRenderMute para estar en el estado "incorrecto".</span><span class="sxs-lookup"><span data-stu-id="fdcfa-207">Percentage of session the DeviceRenderMute event was fired for being in the “Bad’ state.</span></span> <span data-ttu-id="fdcfa-208">El dispositivo de representación está silenciado.</span><span class="sxs-lookup"><span data-stu-id="fdcfa-208">The render device was muted.</span></span></p>
<p><span data-ttu-id="fdcfa-209">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fdcfa-209">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

