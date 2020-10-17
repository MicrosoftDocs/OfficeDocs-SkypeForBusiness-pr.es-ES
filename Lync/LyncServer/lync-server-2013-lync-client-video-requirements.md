---
title: 'Lync Server 2013: requisitos de vídeo del cliente de Lync'
description: 'Lync Server 2013: requisitos de vídeo del cliente de Lync.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync client video requirements
ms:assetid: 8f68f4c2-3194-487c-bd2f-fbe71ba8ad70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688132(v=OCS.15)
ms:contentKeyID: 49733731
ms.date: 01/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea1d4a993650ec8102d8b66ea5aa936ad1613f20
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570486"
---
# <a name="lync-client-video-requirements-for-lync-server-2013"></a><span data-ttu-id="9d2b6-103">Requisitos de vídeo del cliente de Lync para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9d2b6-103">Lync client video requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9d2b6-104">_**Última modificación del tema:** 2016-01-29_</span><span class="sxs-lookup"><span data-stu-id="9d2b6-104">_**Topic Last Modified:** 2016-01-29_</span></span>

<span data-ttu-id="9d2b6-105">En esta sección se describe la compatibilidad de hardware de vídeo para llamadas de vídeo de Lync 2013 y se describe cómo determinar la calidad de vídeo prevista para varias configuraciones de equipos, tabletas y dispositivos móviles.</span><span class="sxs-lookup"><span data-stu-id="9d2b6-105">This section describes video hardware support for Lync 2013 video calls and describes how to determine the expected video quality for various computer, tablet, and mobile device configurations.</span></span>

<div>

## <a name="windows-desktop-and-tablet-video-requirements-and-capabilities"></a><span data-ttu-id="9d2b6-106">Requisitos y capacidades de vídeo de escritorio y tableta de Windows</span><span class="sxs-lookup"><span data-stu-id="9d2b6-106">Windows Desktop and Tablet Video Requirements and Capabilities</span></span>

<span data-ttu-id="9d2b6-107">Lync 2013 presenta aceleración de hardware para la codificación y descodificación de vídeo basada en el estándar de codificación de vídeo avanzado H. 264/MPEG-4 parte 10.</span><span class="sxs-lookup"><span data-stu-id="9d2b6-107">Lync 2013 introduces hardware acceleration for video encoding and decoding based on the H.264/MPEG-4 Part 10 Advanced Video Coding standard.</span></span> <span data-ttu-id="9d2b6-108">Esta característica permite a los equipos con menores velocidades de reloj de CPU codificar y descodificar vídeo de mayor resolución.</span><span class="sxs-lookup"><span data-stu-id="9d2b6-108">This feature allows computers with lower CPU clock speeds to encode and decode higher resolution video.</span></span> <span data-ttu-id="9d2b6-109">Los requisitos de hardware de vídeo varían en función de la configuración del equipo y de la resolución de vídeo que se desea.</span><span class="sxs-lookup"><span data-stu-id="9d2b6-109">Video hardware requirements vary depending on the computer configuration and the video resolution wanted.</span></span>

<div>

## <a name="video-hardware-requirements"></a><span data-ttu-id="9d2b6-110">Requisitos de hardware de vídeo</span><span class="sxs-lookup"><span data-stu-id="9d2b6-110">Video Hardware Requirements</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9d2b6-111">Característica</span><span class="sxs-lookup"><span data-stu-id="9d2b6-111">Feature</span></span></th>
<th><span data-ttu-id="9d2b6-112">Requisito</span><span class="sxs-lookup"><span data-stu-id="9d2b6-112">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9d2b6-113">Descodificación H.264 acelerada por hardware mediante DirectX Video Acceleration (DXVA)</span><span class="sxs-lookup"><span data-stu-id="9d2b6-113">Hardware accelerated H.264 decoding using DirectX Video Acceleration (DXVA)</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="9d2b6-114">La tarjeta gráfica debe admitir DirectX 9.0 y debe exponer el modo de decodificación DXVA2_ModeH264_VLD_NoFGT.</span><span class="sxs-lookup"><span data-stu-id="9d2b6-114">Graphics card must support DirectX 9.0 and must expose the DXVA2_ModeH264_VLD_NoFGT decoding mode.</span></span></p></li>
<li><p><span data-ttu-id="9d2b6-115">Debe estar instalado el controlador de la tarjeta gráfica más reciente.</span><span class="sxs-lookup"><span data-stu-id="9d2b6-115">The latest graphics card driver must be installed.</span></span></p></li>
</ul>
<div>

> [!NOTE]  
> <span data-ttu-id="9d2b6-116">Para obtener más información sobre los modos de descodificación, consulte <A href="https://go.microsoft.com/fwlink/p/?linkid=268530">https://go.microsoft.com/fwlink/p/?LinkId=268530</A> .</span><span class="sxs-lookup"><span data-stu-id="9d2b6-116">For details about decoding modes, see <A href="https://go.microsoft.com/fwlink/p/?linkid=268530">https://go.microsoft.com/fwlink/p/?LinkId=268530</A>.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d2b6-117">Codificación H.264 acelerada por hardware: requisitos del conjunto de chips</span><span class="sxs-lookup"><span data-stu-id="9d2b6-117">Hardware accelerated H.264 encoding: Chipset Requirements</span></span></p></td>
<td><p><span data-ttu-id="9d2b6-118">Se admiten las siguientes soluciones de codificación de vídeo acelerada por hardware Intel:</span><span class="sxs-lookup"><span data-stu-id="9d2b6-118">The following Intel hardware accelerated video encoding solutions are supported:</span></span></p>
<ul>
<li><p><span data-ttu-id="9d2b6-119">Conjuntos de chips Intel HD Graphics 2000, 2500, 3000 y 4000 de segunda y tercera generación (o versiones posteriores) con codificadores de vídeo de hardware integrados.</span><span class="sxs-lookup"><span data-stu-id="9d2b6-119">Second and third generation Intel HD Graphics 2000, 2500, 3000, and 4000 chipsets (or later versions) with integrated hardware video encoders.</span></span> <span data-ttu-id="9d2b6-120">Es necesario instalar el controlador de gráficos Intel HD 15.28.9.2884 o el último controlador que contenga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9d2b6-120">Installation of the Intel HD Graphics driver 15.28.9.2884 or the latest driver containing the following is required:</span></span></p>
<ul>
<li><p><span data-ttu-id="9d2b6-121">Controlador de pantalla 9.17.10.2884 o el controlador más reciente</span><span class="sxs-lookup"><span data-stu-id="9d2b6-121">Display driver 9.17.10.2884 or the latest driver</span></span></p></li>
<li><p><span data-ttu-id="9d2b6-122">Hardware Media Foundation Transform (HMFT) versión 3.12.10.31 o la última HMFT</span><span class="sxs-lookup"><span data-stu-id="9d2b6-122">Hardware media foundation transform (HMFT) version 3.12.10.31 or the latest HMFT</span></span></p></li>
</ul></li>
</ul>
<p><span data-ttu-id="9d2b6-123">Se admiten las siguientes soluciones de codificación de vídeo acelerada por hardware AMD (requiere actualizaciones de CU1 para Lync Server 2013):</span><span class="sxs-lookup"><span data-stu-id="9d2b6-123">The following AMD hardware accelerated video encoding solutions are supported (requires CU1 Updates for Lync Server 2013):</span></span></p>
<ul>
<li><p><span data-ttu-id="9d2b6-124">Procesador AMD video codec, que está disponible en varias tarjetas gráficas independientes y en unidades de procesamiento aceleradas integradas de procesadores acelerados AMD A-Series.</span><span class="sxs-lookup"><span data-stu-id="9d2b6-124">AMD Video Codec Engine, which is available in several discrete graphics cards and in integrated accelerated processing units of AMD A-Series Accelerated Processors.</span></span> <span data-ttu-id="9d2b6-125">Debe estar instalado el controlador del motor de códecs de vídeo AMD 9.12.0.0 o superior.</span><span class="sxs-lookup"><span data-stu-id="9d2b6-125">The AMD Video Codec Engine driver 9.12.0.0 or higher must be installed.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d2b6-126">Codificación H.264 acelerada por hardware: requisitos de la cámara</span><span class="sxs-lookup"><span data-stu-id="9d2b6-126">Hardware accelerated H.264 encoding: Camera Requirements</span></span></p></td>
<td><p><span data-ttu-id="9d2b6-127">Cámaras de vídeo USB con codificador de hardware H.264 integrado que cumplan la especificación USB Video Class (UVC) versión 1.5.</span><span class="sxs-lookup"><span data-stu-id="9d2b6-127">USB video cameras with integrated H.264 hardware encoder that conforms to the USB Video Class (UVC) specification version 1.5.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="9d2b6-128">Lync 2013 admite cámaras UVC 1,5 con Windows 8 o Windows 8,1, que incluye compatibilidad con UVC 1,5.</span><span class="sxs-lookup"><span data-stu-id="9d2b6-128">Lync 2013 supports UVC 1.5 cameras with Windows 8 or Windows 8.1, which includes support for UVC 1.5.</span></span> <span data-ttu-id="9d2b6-129">Como Windows 7 no incluye compatibilidad para UVC 1.5, Lync 2013 trata las cámaras UVC 1.5 como cámaras normales sin compatibilidad para codificación de hardware.</span><span class="sxs-lookup"><span data-stu-id="9d2b6-129">Because Windows 7 does not include support for UVC 1.5, Lync 2013 treats UVC 1.5 cameras as regular cameras with no hardware encoding support.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="determining-h264-video-encoding-and-decoding-capabilities"></a><span data-ttu-id="9d2b6-130">Determinación de la capacidad de codificación y descodificación de vídeo H.264</span><span class="sxs-lookup"><span data-stu-id="9d2b6-130">Determining H.264 Video Encoding and Decoding Capabilities</span></span>

<span data-ttu-id="9d2b6-131">Por lo general, son cuatro los factores principales que determinan la capacidad máxima de codificación y descodificación de una configuración de equipo determinada:</span><span class="sxs-lookup"><span data-stu-id="9d2b6-131">Generally, there are four major factors that determine the maximum encoding and decoding capability of a particular computer configuration:</span></span>

  - <span data-ttu-id="9d2b6-132">Compatibilidad para descodificación acelerada por hardware mediante DXVA</span><span class="sxs-lookup"><span data-stu-id="9d2b6-132">Support for hardware accelerated decoding by using DXVA</span></span>

  - <span data-ttu-id="9d2b6-133">Compatibilidad para codificación acelerada por hardware</span><span class="sxs-lookup"><span data-stu-id="9d2b6-133">Support for hardware accelerated encoding</span></span>

  - <span data-ttu-id="9d2b6-134">Número de núcleos físicos</span><span class="sxs-lookup"><span data-stu-id="9d2b6-134">Number of physical cores</span></span>

  - <span data-ttu-id="9d2b6-135">Evaluación de la experiencia de Windows (WEI)</span><span class="sxs-lookup"><span data-stu-id="9d2b6-135">Windows Experience Index (WEI)</span></span>

<span data-ttu-id="9d2b6-136">La Herramienta de evaluación del sistema de Windows (WinSAT) determina la WEI.</span><span class="sxs-lookup"><span data-stu-id="9d2b6-136">The Windows System Assessment Tool (WinSAT) determines the WEI.</span></span> <span data-ttu-id="9d2b6-137">Cuando ejecuta la herramienta de WinSAT, genera un documento XML formal. Assessment en el equipo en el directorio% WINDIR% \\ performance de \\ WinSAT de WinSAT \\ .</span><span class="sxs-lookup"><span data-stu-id="9d2b6-137">When you run the WinSAT tool, it generates a Formal.Assessment XML document on the computer in the %windir%\\Performance\\WinSAT\\DataStore directory.</span></span> <span data-ttu-id="9d2b6-138">Este archivo XML contiene las siguientes dos puntuaciones que son especialmente importantes para determinar la capacidad de codificación y descodificación:</span><span class="sxs-lookup"><span data-stu-id="9d2b6-138">This XML file contains the following two scores that are of particular importance for determining encoding and decoding capabilities:</span></span>

  - <span data-ttu-id="9d2b6-139">VideoEncodeScore indica la capacidad de codificación de vídeo basada en software del equipo.</span><span class="sxs-lookup"><span data-stu-id="9d2b6-139">The VideoEncodeScore indicates the software-based video encoding capability of the computer.</span></span>

  - <span data-ttu-id="9d2b6-140">El valor de GraphicsScore indica la capacidad de codificación acelerada por hardware del equipo.</span><span class="sxs-lookup"><span data-stu-id="9d2b6-140">The GraphicsScore value indicates the hardware accelerated encoding capability of the computer.</span></span>

<span data-ttu-id="9d2b6-p106">Las siguientes tres tablas explican la capacidad máxima de codificación y descodificación de diferentes tipos de PC en función de la aceleración de hardware que admitan. Para resoluciones de 640x360 y superiores, la velocidad de fotogramas máxima admitida es de 30 fotogramas por segundo (fps). Para resoluciones inferiores a 640x360, la velocidad de fotogramas máxima admitida es de 15 fps.</span><span class="sxs-lookup"><span data-stu-id="9d2b6-p106">The following three tables explain the maximum encoding and decoding capability for different PC types depending on what hardware acceleration they support. For resolutions of 640x360 and higher, the maximum supported frame rate is 30 frames per second (fps). For resolutions lower than 640x360, the maximum supported frame rate is 15 fps.</span></span>

### <a name="computer-without-dxva-and-without-hardware-accelerated-encoder"></a><span data-ttu-id="9d2b6-144">Equipo sin DXVA y sin codificador acelerado por hardware</span><span class="sxs-lookup"><span data-stu-id="9d2b6-144">Computer Without DXVA And Without Hardware Accelerated Encoder</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9d2b6-145">Resolución del codificador habilitado</span><span class="sxs-lookup"><span data-stu-id="9d2b6-145">Capable Encoder Resolution</span></span></th>
<th><span data-ttu-id="9d2b6-146">Resolución del descodificador habilitado</span><span class="sxs-lookup"><span data-stu-id="9d2b6-146">Capable Decoder Resolution</span></span></th>
<th><span data-ttu-id="9d2b6-147">Requisito</span><span class="sxs-lookup"><span data-stu-id="9d2b6-147">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9d2b6-148">424x240</span><span class="sxs-lookup"><span data-stu-id="9d2b6-148">424x240</span></span></p></td>
<td><p><span data-ttu-id="9d2b6-149">424x240 (640x360 a 15 fps para escenarios solo de recepción)</span><span class="sxs-lookup"><span data-stu-id="9d2b6-149">424x240 (640x360 at 15fps for receive only scenarios)</span></span></p></td>
<td><p><span data-ttu-id="9d2b6-150">1 núcleo y VideoEncodeScore ≥ 4,0</span><span class="sxs-lookup"><span data-stu-id="9d2b6-150">1 Core and VideoEncodeScore ≥ 4.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d2b6-151">640 x 360</span><span class="sxs-lookup"><span data-stu-id="9d2b6-151">640x360</span></span></p></td>
<td><p><span data-ttu-id="9d2b6-152">640 x 360</span><span class="sxs-lookup"><span data-stu-id="9d2b6-152">640x360</span></span></p></td>
<td><p><span data-ttu-id="9d2b6-153">2 núcleos y VideoEncodeScore = 4,5</span><span class="sxs-lookup"><span data-stu-id="9d2b6-153">2 Cores and VideoEncodeScore ≥ 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d2b6-154">640 x 360</span><span class="sxs-lookup"><span data-stu-id="9d2b6-154">640x360</span></span></p></td>
<td><p><span data-ttu-id="9d2b6-155">1280x720</span><span class="sxs-lookup"><span data-stu-id="9d2b6-155">1280x720</span></span></p></td>
<td><p><span data-ttu-id="9d2b6-156">2 núcleos y VideoEncodeScore ≥ 4,5</span><span class="sxs-lookup"><span data-stu-id="9d2b6-156">2 Cores and VideoEncodeScore ≥ 4.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d2b6-157">640 x 360</span><span class="sxs-lookup"><span data-stu-id="9d2b6-157">640x360</span></span></p></td>
<td><p><span data-ttu-id="9d2b6-158">1920</span><span class="sxs-lookup"><span data-stu-id="9d2b6-158">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="9d2b6-159">4 núcleos y VideoEncodeScore ≥ 4,5</span><span class="sxs-lookup"><span data-stu-id="9d2b6-159">4 Cores and VideoEncodeScore ≥ 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d2b6-160">1280x720</span><span class="sxs-lookup"><span data-stu-id="9d2b6-160">1280x720</span></span></p></td>
<td><p><span data-ttu-id="9d2b6-161">1280x720</span><span class="sxs-lookup"><span data-stu-id="9d2b6-161">1280x720</span></span></p></td>
<td><p><span data-ttu-id="9d2b6-162">4 núcleos y VideoEncodeScore ≥ 7,3</span><span class="sxs-lookup"><span data-stu-id="9d2b6-162">4 Cores and VideoEncodeScore ≥ 7.3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d2b6-163">1280x720</span><span class="sxs-lookup"><span data-stu-id="9d2b6-163">1280x720</span></span></p></td>
<td><p><span data-ttu-id="9d2b6-164">1920</span><span class="sxs-lookup"><span data-stu-id="9d2b6-164">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="9d2b6-165">4 núcleos y VideoEncodeScore ≥ 7,3</span><span class="sxs-lookup"><span data-stu-id="9d2b6-165">4 Cores and VideoEncodeScore ≥ 7.3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d2b6-166">1920</span><span class="sxs-lookup"><span data-stu-id="9d2b6-166">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="9d2b6-167">1920</span><span class="sxs-lookup"><span data-stu-id="9d2b6-167">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="9d2b6-168">N/D</span><span class="sxs-lookup"><span data-stu-id="9d2b6-168">N/A</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="computer-with-dxva-but-without-hardware-accelerated-encoder"></a><span data-ttu-id="9d2b6-169">Equipo con DXVA pero sin codificador acelerado por hardware</span><span class="sxs-lookup"><span data-stu-id="9d2b6-169">Computer With DXVA But Without Hardware Accelerated Encoder</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9d2b6-170">Resolución del codificador habilitado</span><span class="sxs-lookup"><span data-stu-id="9d2b6-170">Capable Encoder Resolution</span></span></th>
<th><span data-ttu-id="9d2b6-171">Resolución del descodificador habilitado</span><span class="sxs-lookup"><span data-stu-id="9d2b6-171">Capable Decoder Resolution</span></span></th>
<th><span data-ttu-id="9d2b6-172">Requisito</span><span class="sxs-lookup"><span data-stu-id="9d2b6-172">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9d2b6-173">424x240</span><span class="sxs-lookup"><span data-stu-id="9d2b6-173">424x240</span></span></p></td>
<td><p><span data-ttu-id="9d2b6-174">1920</span><span class="sxs-lookup"><span data-stu-id="9d2b6-174">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="9d2b6-175">1 núcleo y VideoEncodeScore ≥ 3,0</span><span class="sxs-lookup"><span data-stu-id="9d2b6-175">1 Core and VideoEncodeScore ≥ 3.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d2b6-176">640 x 360</span><span class="sxs-lookup"><span data-stu-id="9d2b6-176">640x360</span></span></p></td>
<td><p><span data-ttu-id="9d2b6-177">1920</span><span class="sxs-lookup"><span data-stu-id="9d2b6-177">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="9d2b6-178">2 núcleos y VideoEncodeScore ≥ 4,5</span><span class="sxs-lookup"><span data-stu-id="9d2b6-178">2 Cores and VideoEncodeScore ≥ 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d2b6-179">960x540</span><span class="sxs-lookup"><span data-stu-id="9d2b6-179">960x540</span></span></p></td>
<td><p><span data-ttu-id="9d2b6-180">1920</span><span class="sxs-lookup"><span data-stu-id="9d2b6-180">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="9d2b6-181">2 núcleos y VideoEncodeScore ≥ 6,0</span><span class="sxs-lookup"><span data-stu-id="9d2b6-181">2 Cores and VideoEncodeScore ≥ 6.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d2b6-182">1280x720</span><span class="sxs-lookup"><span data-stu-id="9d2b6-182">1280x720</span></span></p></td>
<td><p><span data-ttu-id="9d2b6-183">1920</span><span class="sxs-lookup"><span data-stu-id="9d2b6-183">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="9d2b6-184">4 núcleos y VideoEncodeScore ≥ 6,7</span><span class="sxs-lookup"><span data-stu-id="9d2b6-184">4 Cores and VideoEncodeScore ≥ 6.7</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d2b6-185">1920</span><span class="sxs-lookup"><span data-stu-id="9d2b6-185">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="9d2b6-186">1920</span><span class="sxs-lookup"><span data-stu-id="9d2b6-186">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="9d2b6-187">4 núcleos y VideoEncodeScore ≥ 8,2</span><span class="sxs-lookup"><span data-stu-id="9d2b6-187">4 Cores and VideoEncodeScore ≥ 8.2</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="9d2b6-188">La puntuación de WinSAT en Windows 7 se limita a un máximo de 7,9.</span><span class="sxs-lookup"><span data-stu-id="9d2b6-188">The WinSAT score on Windows 7 is limited to a maximum of 7.9.</span></span> <span data-ttu-id="9d2b6-189">Por lo tanto, la capacidad de codificación de un equipo sin un codificador acelerado por hardware solo se puede lograr en Windows 8 o Windows 8,1, donde la puntuación máxima de WinSAT es de 9,9.</span><span class="sxs-lookup"><span data-stu-id="9d2b6-189">Therefore, the encoding capability for a computer without a hardware accelerated encoder can only be achieved on Windows 8 or Windows 8.1, where the maximum WinSAT score is 9.9.</span></span>



</div>

### <a name="computer-with-dxva-and-with-intel-hd-graphics-hardware-accelerated-encoder"></a><span data-ttu-id="9d2b6-190">Equipo con DXVA y con codificador acelerado por hardware Intel HD Graphics</span><span class="sxs-lookup"><span data-stu-id="9d2b6-190">Computer With DXVA And With Intel HD Graphics Hardware Accelerated Encoder</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9d2b6-191">Resolución del codificador habilitado</span><span class="sxs-lookup"><span data-stu-id="9d2b6-191">Capable Encoder Resolution</span></span></th>
<th><span data-ttu-id="9d2b6-192">Resolución del descodificador habilitado</span><span class="sxs-lookup"><span data-stu-id="9d2b6-192">Capable Decoder Resolution</span></span></th>
<th><span data-ttu-id="9d2b6-193">Requisito</span><span class="sxs-lookup"><span data-stu-id="9d2b6-193">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9d2b6-194">1280x720</span><span class="sxs-lookup"><span data-stu-id="9d2b6-194">1280x720</span></span></p></td>
<td><p><span data-ttu-id="9d2b6-195">1920</span><span class="sxs-lookup"><span data-stu-id="9d2b6-195">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="9d2b6-196">Todos los modelos de Intel HD Graphics de segunda y tercera generación</span><span class="sxs-lookup"><span data-stu-id="9d2b6-196">All 2nd and 3rd generation Intel HD Graphics</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d2b6-197">1920</span><span class="sxs-lookup"><span data-stu-id="9d2b6-197">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="9d2b6-198">1920</span><span class="sxs-lookup"><span data-stu-id="9d2b6-198">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="9d2b6-199">Todos los modelos de Intel HD Graphics de segunda y tercera generación y GraphicsScore ≥ 5,0</span><span class="sxs-lookup"><span data-stu-id="9d2b6-199">2nd and 3rd generation Intel HD Graphics and GraphicsScore ≥ 5.0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="mobile-device-video-capabilities"></a><span data-ttu-id="9d2b6-200">Capacidades de vídeo de dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="9d2b6-200">Mobile Device Video Capabilities</span></span>

<span data-ttu-id="9d2b6-201">En la tabla siguiente se describen las capacidades de vídeo máximas para los dispositivos móviles compatibles.</span><span class="sxs-lookup"><span data-stu-id="9d2b6-201">The following table describes the maximum video capabilities for supported mobile devices.</span></span> <span data-ttu-id="9d2b6-202">Para obtener más información acerca de la compatibilidad de dispositivos móviles, consulte [Planning for Mobile clients in Lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).</span><span class="sxs-lookup"><span data-stu-id="9d2b6-202">For more information about mobile device support, see [Planning for mobile clients in Lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).</span></span>


<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9d2b6-203">Característica</span><span class="sxs-lookup"><span data-stu-id="9d2b6-203">Feature</span></span></th>
<th><span data-ttu-id="9d2b6-204">Windows Phone</span><span class="sxs-lookup"><span data-stu-id="9d2b6-204">Windows Phone</span></span></th>
<th><span data-ttu-id="9d2b6-205">iPhone</span><span class="sxs-lookup"><span data-stu-id="9d2b6-205">iPhone</span></span></th>
<th><span data-ttu-id="9d2b6-206">iPad</span><span class="sxs-lookup"><span data-stu-id="9d2b6-206">iPad</span></span></th>
<th><span data-ttu-id="9d2b6-207">Android</span><span class="sxs-lookup"><span data-stu-id="9d2b6-207">Android</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9d2b6-208">Resolución máxima de codificación H. 264</span><span class="sxs-lookup"><span data-stu-id="9d2b6-208">H.264 encoding maximum resolution</span></span></p></td>
<td><p><span data-ttu-id="9d2b6-209">VGA</span><span class="sxs-lookup"><span data-stu-id="9d2b6-209">VGA</span></span></p></td>
<td><p><span data-ttu-id="9d2b6-210">QVGA: iPhone 4S</span><span class="sxs-lookup"><span data-stu-id="9d2b6-210">QVGA: iPhone 4S</span></span></p>
<p><span data-ttu-id="9d2b6-211">VGA: iPhone 5</span><span class="sxs-lookup"><span data-stu-id="9d2b6-211">VGA: iPhone 5</span></span></p>
<p><span data-ttu-id="9d2b6-212">720p: iPhone 5S y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="9d2b6-212">720p: iPhone 5S and later</span></span></p></td>
<td><p><span data-ttu-id="9d2b6-213">VGA: iPad 2 y posterior/iPad mini 1 y posterior</span><span class="sxs-lookup"><span data-stu-id="9d2b6-213">VGA: iPad 2 and later/iPad mini 1 and later</span></span></p>
<p><span data-ttu-id="9d2b6-214">720p: dispositivo para iPad Air/iPad mini 2/iPad Pro y posterior</span><span class="sxs-lookup"><span data-stu-id="9d2b6-214">720p: iPad Air/iPad mini 2/iPad Pro and later</span></span></p></td>
<td><p><span data-ttu-id="9d2b6-215">Hasta VGA en función del modelo de dispositivo</span><span class="sxs-lookup"><span data-stu-id="9d2b6-215">Up to VGA depending on device model</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d2b6-216">Resolución máxima de codificación H. 264</span><span class="sxs-lookup"><span data-stu-id="9d2b6-216">H.264 decoding maximum resolution</span></span></p></td>
<td><p><span data-ttu-id="9d2b6-217">VGA</span><span class="sxs-lookup"><span data-stu-id="9d2b6-217">VGA</span></span></p></td>
<td><p><span data-ttu-id="9d2b6-218">QVGA: iPhone 4S</span><span class="sxs-lookup"><span data-stu-id="9d2b6-218">QVGA: iPhone 4S</span></span></p>
<p><span data-ttu-id="9d2b6-219">VGA: iPhone 5</span><span class="sxs-lookup"><span data-stu-id="9d2b6-219">VGA: iPhone 5</span></span></p>
<p><span data-ttu-id="9d2b6-220">720p: iPhone 5S y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="9d2b6-220">720p: iPhone 5S and later</span></span></p></td>
<td><p><span data-ttu-id="9d2b6-221">VGA: iPad 2 y posterior/iPad mini 1 y posterior</span><span class="sxs-lookup"><span data-stu-id="9d2b6-221">VGA: iPad 2 and later/iPad mini 1 and later</span></span></p>
<p><span data-ttu-id="9d2b6-222">720p: dispositivo para iPad Air/iPad mini 2/iPad Pro y posterior</span><span class="sxs-lookup"><span data-stu-id="9d2b6-222">720p: iPad Air/iPad mini 2/iPad Pro and later</span></span></p></td>
<td><p><span data-ttu-id="9d2b6-223">Hasta VGA en función del modelo de dispositivo</span><span class="sxs-lookup"><span data-stu-id="9d2b6-223">Up to VGA depending on device model</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

