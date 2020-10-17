---
title: 'Lync Server 2013: requisitos de vídeo del cliente de Lync'
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
ms.openlocfilehash: 883242824a6dfc45dbae923736a7a88bc1784d62
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506067"
---
# <a name="lync-client-video-requirements-for-lync-server-2013"></a><span data-ttu-id="ce110-102">Requisitos de vídeo del cliente de Lync para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce110-102">Lync client video requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ce110-103">_**Última modificación del tema:** 2016-01-29_</span><span class="sxs-lookup"><span data-stu-id="ce110-103">_**Topic Last Modified:** 2016-01-29_</span></span>

<span data-ttu-id="ce110-104">En esta sección se describe la compatibilidad de hardware de vídeo para llamadas de vídeo de Lync 2013 y se describe cómo determinar la calidad de vídeo prevista para varias configuraciones de equipos, tabletas y dispositivos móviles.</span><span class="sxs-lookup"><span data-stu-id="ce110-104">This section describes video hardware support for Lync 2013 video calls and describes how to determine the expected video quality for various computer, tablet, and mobile device configurations.</span></span>

<div>

## <a name="windows-desktop-and-tablet-video-requirements-and-capabilities"></a><span data-ttu-id="ce110-105">Requisitos y capacidades de vídeo de escritorio y tableta de Windows</span><span class="sxs-lookup"><span data-stu-id="ce110-105">Windows Desktop and Tablet Video Requirements and Capabilities</span></span>

<span data-ttu-id="ce110-106">Lync 2013 presenta aceleración de hardware para la codificación y descodificación de vídeo basada en el estándar de codificación de vídeo avanzado H. 264/MPEG-4 parte 10.</span><span class="sxs-lookup"><span data-stu-id="ce110-106">Lync 2013 introduces hardware acceleration for video encoding and decoding based on the H.264/MPEG-4 Part 10 Advanced Video Coding standard.</span></span> <span data-ttu-id="ce110-107">Esta característica permite a los equipos con menores velocidades de reloj de CPU codificar y descodificar vídeo de mayor resolución.</span><span class="sxs-lookup"><span data-stu-id="ce110-107">This feature allows computers with lower CPU clock speeds to encode and decode higher resolution video.</span></span> <span data-ttu-id="ce110-108">Los requisitos de hardware de vídeo varían en función de la configuración del equipo y de la resolución de vídeo que se desea.</span><span class="sxs-lookup"><span data-stu-id="ce110-108">Video hardware requirements vary depending on the computer configuration and the video resolution wanted.</span></span>

<div>

## <a name="video-hardware-requirements"></a><span data-ttu-id="ce110-109">Requisitos de hardware de vídeo</span><span class="sxs-lookup"><span data-stu-id="ce110-109">Video Hardware Requirements</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ce110-110">Característica</span><span class="sxs-lookup"><span data-stu-id="ce110-110">Feature</span></span></th>
<th><span data-ttu-id="ce110-111">Requisito</span><span class="sxs-lookup"><span data-stu-id="ce110-111">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ce110-112">Descodificación H.264 acelerada por hardware mediante DirectX Video Acceleration (DXVA)</span><span class="sxs-lookup"><span data-stu-id="ce110-112">Hardware accelerated H.264 decoding using DirectX Video Acceleration (DXVA)</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="ce110-113">La tarjeta gráfica debe admitir DirectX 9.0 y debe exponer el modo de decodificación DXVA2_ModeH264_VLD_NoFGT.</span><span class="sxs-lookup"><span data-stu-id="ce110-113">Graphics card must support DirectX 9.0 and must expose the DXVA2_ModeH264_VLD_NoFGT decoding mode.</span></span></p></li>
<li><p><span data-ttu-id="ce110-114">Debe estar instalado el controlador de la tarjeta gráfica más reciente.</span><span class="sxs-lookup"><span data-stu-id="ce110-114">The latest graphics card driver must be installed.</span></span></p></li>
</ul>
<div>

> [!NOTE]  
> <span data-ttu-id="ce110-115">Para obtener más información sobre los modos de descodificación, consulte <A href="https://go.microsoft.com/fwlink/p/?linkid=268530">https://go.microsoft.com/fwlink/p/?LinkId=268530</A> .</span><span class="sxs-lookup"><span data-stu-id="ce110-115">For details about decoding modes, see <A href="https://go.microsoft.com/fwlink/p/?linkid=268530">https://go.microsoft.com/fwlink/p/?LinkId=268530</A>.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce110-116">Codificación H.264 acelerada por hardware: requisitos del conjunto de chips</span><span class="sxs-lookup"><span data-stu-id="ce110-116">Hardware accelerated H.264 encoding: Chipset Requirements</span></span></p></td>
<td><p><span data-ttu-id="ce110-117">Se admiten las siguientes soluciones de codificación de vídeo acelerada por hardware Intel:</span><span class="sxs-lookup"><span data-stu-id="ce110-117">The following Intel hardware accelerated video encoding solutions are supported:</span></span></p>
<ul>
<li><p><span data-ttu-id="ce110-118">Conjuntos de chips Intel HD Graphics 2000, 2500, 3000 y 4000 de segunda y tercera generación (o versiones posteriores) con codificadores de vídeo de hardware integrados.</span><span class="sxs-lookup"><span data-stu-id="ce110-118">Second and third generation Intel HD Graphics 2000, 2500, 3000, and 4000 chipsets (or later versions) with integrated hardware video encoders.</span></span> <span data-ttu-id="ce110-119">Es necesario instalar el controlador de gráficos Intel HD 15.28.9.2884 o el último controlador que contenga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ce110-119">Installation of the Intel HD Graphics driver 15.28.9.2884 or the latest driver containing the following is required:</span></span></p>
<ul>
<li><p><span data-ttu-id="ce110-120">Controlador de pantalla 9.17.10.2884 o el controlador más reciente</span><span class="sxs-lookup"><span data-stu-id="ce110-120">Display driver 9.17.10.2884 or the latest driver</span></span></p></li>
<li><p><span data-ttu-id="ce110-121">Hardware Media Foundation Transform (HMFT) versión 3.12.10.31 o la última HMFT</span><span class="sxs-lookup"><span data-stu-id="ce110-121">Hardware media foundation transform (HMFT) version 3.12.10.31 or the latest HMFT</span></span></p></li>
</ul></li>
</ul>
<p><span data-ttu-id="ce110-122">Se admiten las siguientes soluciones de codificación de vídeo acelerada por hardware AMD (requiere actualizaciones de CU1 para Lync Server 2013):</span><span class="sxs-lookup"><span data-stu-id="ce110-122">The following AMD hardware accelerated video encoding solutions are supported (requires CU1 Updates for Lync Server 2013):</span></span></p>
<ul>
<li><p><span data-ttu-id="ce110-123">Procesador AMD video codec, que está disponible en varias tarjetas gráficas independientes y en unidades de procesamiento aceleradas integradas de procesadores acelerados AMD A-Series.</span><span class="sxs-lookup"><span data-stu-id="ce110-123">AMD Video Codec Engine, which is available in several discrete graphics cards and in integrated accelerated processing units of AMD A-Series Accelerated Processors.</span></span> <span data-ttu-id="ce110-124">Debe estar instalado el controlador del motor de códecs de vídeo AMD 9.12.0.0 o superior.</span><span class="sxs-lookup"><span data-stu-id="ce110-124">The AMD Video Codec Engine driver 9.12.0.0 or higher must be installed.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce110-125">Codificación H.264 acelerada por hardware: requisitos de la cámara</span><span class="sxs-lookup"><span data-stu-id="ce110-125">Hardware accelerated H.264 encoding: Camera Requirements</span></span></p></td>
<td><p><span data-ttu-id="ce110-126">Cámaras de vídeo USB con codificador de hardware H.264 integrado que cumplan la especificación USB Video Class (UVC) versión 1.5.</span><span class="sxs-lookup"><span data-stu-id="ce110-126">USB video cameras with integrated H.264 hardware encoder that conforms to the USB Video Class (UVC) specification version 1.5.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="ce110-127">Lync 2013 admite cámaras UVC 1,5 con Windows 8 o Windows 8,1, que incluye compatibilidad con UVC 1,5.</span><span class="sxs-lookup"><span data-stu-id="ce110-127">Lync 2013 supports UVC 1.5 cameras with Windows 8 or Windows 8.1, which includes support for UVC 1.5.</span></span> <span data-ttu-id="ce110-128">Como Windows 7 no incluye compatibilidad para UVC 1.5, Lync 2013 trata las cámaras UVC 1.5 como cámaras normales sin compatibilidad para codificación de hardware.</span><span class="sxs-lookup"><span data-stu-id="ce110-128">Because Windows 7 does not include support for UVC 1.5, Lync 2013 treats UVC 1.5 cameras as regular cameras with no hardware encoding support.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="determining-h264-video-encoding-and-decoding-capabilities"></a><span data-ttu-id="ce110-129">Determinación de la capacidad de codificación y descodificación de vídeo H.264</span><span class="sxs-lookup"><span data-stu-id="ce110-129">Determining H.264 Video Encoding and Decoding Capabilities</span></span>

<span data-ttu-id="ce110-130">Por lo general, son cuatro los factores principales que determinan la capacidad máxima de codificación y descodificación de una configuración de equipo determinada:</span><span class="sxs-lookup"><span data-stu-id="ce110-130">Generally, there are four major factors that determine the maximum encoding and decoding capability of a particular computer configuration:</span></span>

  - <span data-ttu-id="ce110-131">Compatibilidad para descodificación acelerada por hardware mediante DXVA</span><span class="sxs-lookup"><span data-stu-id="ce110-131">Support for hardware accelerated decoding by using DXVA</span></span>

  - <span data-ttu-id="ce110-132">Compatibilidad para codificación acelerada por hardware</span><span class="sxs-lookup"><span data-stu-id="ce110-132">Support for hardware accelerated encoding</span></span>

  - <span data-ttu-id="ce110-133">Número de núcleos físicos</span><span class="sxs-lookup"><span data-stu-id="ce110-133">Number of physical cores</span></span>

  - <span data-ttu-id="ce110-134">Evaluación de la experiencia de Windows (WEI)</span><span class="sxs-lookup"><span data-stu-id="ce110-134">Windows Experience Index (WEI)</span></span>

<span data-ttu-id="ce110-135">La Herramienta de evaluación del sistema de Windows (WinSAT) determina la WEI.</span><span class="sxs-lookup"><span data-stu-id="ce110-135">The Windows System Assessment Tool (WinSAT) determines the WEI.</span></span> <span data-ttu-id="ce110-136">Cuando ejecuta la herramienta de WinSAT, genera un documento XML formal. Assessment en el equipo en el directorio% WINDIR% \\ performance de \\ WinSAT de WinSAT \\ .</span><span class="sxs-lookup"><span data-stu-id="ce110-136">When you run the WinSAT tool, it generates a Formal.Assessment XML document on the computer in the %windir%\\Performance\\WinSAT\\DataStore directory.</span></span> <span data-ttu-id="ce110-137">Este archivo XML contiene las siguientes dos puntuaciones que son especialmente importantes para determinar la capacidad de codificación y descodificación:</span><span class="sxs-lookup"><span data-stu-id="ce110-137">This XML file contains the following two scores that are of particular importance for determining encoding and decoding capabilities:</span></span>

  - <span data-ttu-id="ce110-138">VideoEncodeScore indica la capacidad de codificación de vídeo basada en software del equipo.</span><span class="sxs-lookup"><span data-stu-id="ce110-138">The VideoEncodeScore indicates the software-based video encoding capability of the computer.</span></span>

  - <span data-ttu-id="ce110-139">El valor de GraphicsScore indica la capacidad de codificación acelerada por hardware del equipo.</span><span class="sxs-lookup"><span data-stu-id="ce110-139">The GraphicsScore value indicates the hardware accelerated encoding capability of the computer.</span></span>

<span data-ttu-id="ce110-p106">Las siguientes tres tablas explican la capacidad máxima de codificación y descodificación de diferentes tipos de PC en función de la aceleración de hardware que admitan. Para resoluciones de 640x360 y superiores, la velocidad de fotogramas máxima admitida es de 30 fotogramas por segundo (fps). Para resoluciones inferiores a 640x360, la velocidad de fotogramas máxima admitida es de 15 fps.</span><span class="sxs-lookup"><span data-stu-id="ce110-p106">The following three tables explain the maximum encoding and decoding capability for different PC types depending on what hardware acceleration they support. For resolutions of 640x360 and higher, the maximum supported frame rate is 30 frames per second (fps). For resolutions lower than 640x360, the maximum supported frame rate is 15 fps.</span></span>

### <a name="computer-without-dxva-and-without-hardware-accelerated-encoder"></a><span data-ttu-id="ce110-143">Equipo sin DXVA y sin codificador acelerado por hardware</span><span class="sxs-lookup"><span data-stu-id="ce110-143">Computer Without DXVA And Without Hardware Accelerated Encoder</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ce110-144">Resolución del codificador habilitado</span><span class="sxs-lookup"><span data-stu-id="ce110-144">Capable Encoder Resolution</span></span></th>
<th><span data-ttu-id="ce110-145">Resolución del descodificador habilitado</span><span class="sxs-lookup"><span data-stu-id="ce110-145">Capable Decoder Resolution</span></span></th>
<th><span data-ttu-id="ce110-146">Requisito</span><span class="sxs-lookup"><span data-stu-id="ce110-146">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ce110-147">424x240</span><span class="sxs-lookup"><span data-stu-id="ce110-147">424x240</span></span></p></td>
<td><p><span data-ttu-id="ce110-148">424x240 (640x360 a 15 fps para escenarios solo de recepción)</span><span class="sxs-lookup"><span data-stu-id="ce110-148">424x240 (640x360 at 15fps for receive only scenarios)</span></span></p></td>
<td><p><span data-ttu-id="ce110-149">1 núcleo y VideoEncodeScore ≥ 4,0</span><span class="sxs-lookup"><span data-stu-id="ce110-149">1 Core and VideoEncodeScore ≥ 4.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce110-150">640 x 360</span><span class="sxs-lookup"><span data-stu-id="ce110-150">640x360</span></span></p></td>
<td><p><span data-ttu-id="ce110-151">640 x 360</span><span class="sxs-lookup"><span data-stu-id="ce110-151">640x360</span></span></p></td>
<td><p><span data-ttu-id="ce110-152">2 núcleos y VideoEncodeScore = 4,5</span><span class="sxs-lookup"><span data-stu-id="ce110-152">2 Cores and VideoEncodeScore ≥ 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce110-153">640 x 360</span><span class="sxs-lookup"><span data-stu-id="ce110-153">640x360</span></span></p></td>
<td><p><span data-ttu-id="ce110-154">1280x720</span><span class="sxs-lookup"><span data-stu-id="ce110-154">1280x720</span></span></p></td>
<td><p><span data-ttu-id="ce110-155">2 núcleos y VideoEncodeScore ≥ 4,5</span><span class="sxs-lookup"><span data-stu-id="ce110-155">2 Cores and VideoEncodeScore ≥ 4.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce110-156">640 x 360</span><span class="sxs-lookup"><span data-stu-id="ce110-156">640x360</span></span></p></td>
<td><p><span data-ttu-id="ce110-157">1920</span><span class="sxs-lookup"><span data-stu-id="ce110-157">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="ce110-158">4 núcleos y VideoEncodeScore ≥ 4,5</span><span class="sxs-lookup"><span data-stu-id="ce110-158">4 Cores and VideoEncodeScore ≥ 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce110-159">1280x720</span><span class="sxs-lookup"><span data-stu-id="ce110-159">1280x720</span></span></p></td>
<td><p><span data-ttu-id="ce110-160">1280x720</span><span class="sxs-lookup"><span data-stu-id="ce110-160">1280x720</span></span></p></td>
<td><p><span data-ttu-id="ce110-161">4 núcleos y VideoEncodeScore ≥ 7,3</span><span class="sxs-lookup"><span data-stu-id="ce110-161">4 Cores and VideoEncodeScore ≥ 7.3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce110-162">1280x720</span><span class="sxs-lookup"><span data-stu-id="ce110-162">1280x720</span></span></p></td>
<td><p><span data-ttu-id="ce110-163">1920</span><span class="sxs-lookup"><span data-stu-id="ce110-163">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="ce110-164">4 núcleos y VideoEncodeScore ≥ 7,3</span><span class="sxs-lookup"><span data-stu-id="ce110-164">4 Cores and VideoEncodeScore ≥ 7.3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce110-165">1920</span><span class="sxs-lookup"><span data-stu-id="ce110-165">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="ce110-166">1920</span><span class="sxs-lookup"><span data-stu-id="ce110-166">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="ce110-167">N/D</span><span class="sxs-lookup"><span data-stu-id="ce110-167">N/A</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="computer-with-dxva-but-without-hardware-accelerated-encoder"></a><span data-ttu-id="ce110-168">Equipo con DXVA pero sin codificador acelerado por hardware</span><span class="sxs-lookup"><span data-stu-id="ce110-168">Computer With DXVA But Without Hardware Accelerated Encoder</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ce110-169">Resolución del codificador habilitado</span><span class="sxs-lookup"><span data-stu-id="ce110-169">Capable Encoder Resolution</span></span></th>
<th><span data-ttu-id="ce110-170">Resolución del descodificador habilitado</span><span class="sxs-lookup"><span data-stu-id="ce110-170">Capable Decoder Resolution</span></span></th>
<th><span data-ttu-id="ce110-171">Requisito</span><span class="sxs-lookup"><span data-stu-id="ce110-171">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ce110-172">424x240</span><span class="sxs-lookup"><span data-stu-id="ce110-172">424x240</span></span></p></td>
<td><p><span data-ttu-id="ce110-173">1920</span><span class="sxs-lookup"><span data-stu-id="ce110-173">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="ce110-174">1 núcleo y VideoEncodeScore ≥ 3,0</span><span class="sxs-lookup"><span data-stu-id="ce110-174">1 Core and VideoEncodeScore ≥ 3.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce110-175">640 x 360</span><span class="sxs-lookup"><span data-stu-id="ce110-175">640x360</span></span></p></td>
<td><p><span data-ttu-id="ce110-176">1920</span><span class="sxs-lookup"><span data-stu-id="ce110-176">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="ce110-177">2 núcleos y VideoEncodeScore ≥ 4,5</span><span class="sxs-lookup"><span data-stu-id="ce110-177">2 Cores and VideoEncodeScore ≥ 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce110-178">960x540</span><span class="sxs-lookup"><span data-stu-id="ce110-178">960x540</span></span></p></td>
<td><p><span data-ttu-id="ce110-179">1920</span><span class="sxs-lookup"><span data-stu-id="ce110-179">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="ce110-180">2 núcleos y VideoEncodeScore ≥ 6,0</span><span class="sxs-lookup"><span data-stu-id="ce110-180">2 Cores and VideoEncodeScore ≥ 6.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce110-181">1280x720</span><span class="sxs-lookup"><span data-stu-id="ce110-181">1280x720</span></span></p></td>
<td><p><span data-ttu-id="ce110-182">1920</span><span class="sxs-lookup"><span data-stu-id="ce110-182">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="ce110-183">4 núcleos y VideoEncodeScore ≥ 6,7</span><span class="sxs-lookup"><span data-stu-id="ce110-183">4 Cores and VideoEncodeScore ≥ 6.7</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce110-184">1920</span><span class="sxs-lookup"><span data-stu-id="ce110-184">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="ce110-185">1920</span><span class="sxs-lookup"><span data-stu-id="ce110-185">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="ce110-186">4 núcleos y VideoEncodeScore ≥ 8,2</span><span class="sxs-lookup"><span data-stu-id="ce110-186">4 Cores and VideoEncodeScore ≥ 8.2</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="ce110-187">La puntuación de WinSAT en Windows 7 se limita a un máximo de 7,9.</span><span class="sxs-lookup"><span data-stu-id="ce110-187">The WinSAT score on Windows 7 is limited to a maximum of 7.9.</span></span> <span data-ttu-id="ce110-188">Por lo tanto, la capacidad de codificación de un equipo sin un codificador acelerado por hardware solo se puede lograr en Windows 8 o Windows 8,1, donde la puntuación máxima de WinSAT es de 9,9.</span><span class="sxs-lookup"><span data-stu-id="ce110-188">Therefore, the encoding capability for a computer without a hardware accelerated encoder can only be achieved on Windows 8 or Windows 8.1, where the maximum WinSAT score is 9.9.</span></span>



</div>

### <a name="computer-with-dxva-and-with-intel-hd-graphics-hardware-accelerated-encoder"></a><span data-ttu-id="ce110-189">Equipo con DXVA y con codificador acelerado por hardware Intel HD Graphics</span><span class="sxs-lookup"><span data-stu-id="ce110-189">Computer With DXVA And With Intel HD Graphics Hardware Accelerated Encoder</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ce110-190">Resolución del codificador habilitado</span><span class="sxs-lookup"><span data-stu-id="ce110-190">Capable Encoder Resolution</span></span></th>
<th><span data-ttu-id="ce110-191">Resolución del descodificador habilitado</span><span class="sxs-lookup"><span data-stu-id="ce110-191">Capable Decoder Resolution</span></span></th>
<th><span data-ttu-id="ce110-192">Requisito</span><span class="sxs-lookup"><span data-stu-id="ce110-192">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ce110-193">1280x720</span><span class="sxs-lookup"><span data-stu-id="ce110-193">1280x720</span></span></p></td>
<td><p><span data-ttu-id="ce110-194">1920</span><span class="sxs-lookup"><span data-stu-id="ce110-194">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="ce110-195">Todos los modelos de Intel HD Graphics de segunda y tercera generación</span><span class="sxs-lookup"><span data-stu-id="ce110-195">All 2nd and 3rd generation Intel HD Graphics</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce110-196">1920</span><span class="sxs-lookup"><span data-stu-id="ce110-196">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="ce110-197">1920</span><span class="sxs-lookup"><span data-stu-id="ce110-197">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="ce110-198">Todos los modelos de Intel HD Graphics de segunda y tercera generación y GraphicsScore ≥ 5,0</span><span class="sxs-lookup"><span data-stu-id="ce110-198">2nd and 3rd generation Intel HD Graphics and GraphicsScore ≥ 5.0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="mobile-device-video-capabilities"></a><span data-ttu-id="ce110-199">Capacidades de vídeo de dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="ce110-199">Mobile Device Video Capabilities</span></span>

<span data-ttu-id="ce110-200">En la tabla siguiente se describen las capacidades de vídeo máximas para los dispositivos móviles compatibles.</span><span class="sxs-lookup"><span data-stu-id="ce110-200">The following table describes the maximum video capabilities for supported mobile devices.</span></span> <span data-ttu-id="ce110-201">Para obtener más información acerca de la compatibilidad de dispositivos móviles, consulte [Planning for Mobile clients in Lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).</span><span class="sxs-lookup"><span data-stu-id="ce110-201">For more information about mobile device support, see [Planning for mobile clients in Lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).</span></span>


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
<th><span data-ttu-id="ce110-202">Característica</span><span class="sxs-lookup"><span data-stu-id="ce110-202">Feature</span></span></th>
<th><span data-ttu-id="ce110-203">Windows Phone</span><span class="sxs-lookup"><span data-stu-id="ce110-203">Windows Phone</span></span></th>
<th><span data-ttu-id="ce110-204">iPhone</span><span class="sxs-lookup"><span data-stu-id="ce110-204">iPhone</span></span></th>
<th><span data-ttu-id="ce110-205">iPad</span><span class="sxs-lookup"><span data-stu-id="ce110-205">iPad</span></span></th>
<th><span data-ttu-id="ce110-206">Android</span><span class="sxs-lookup"><span data-stu-id="ce110-206">Android</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ce110-207">Resolución máxima de codificación H. 264</span><span class="sxs-lookup"><span data-stu-id="ce110-207">H.264 encoding maximum resolution</span></span></p></td>
<td><p><span data-ttu-id="ce110-208">VGA</span><span class="sxs-lookup"><span data-stu-id="ce110-208">VGA</span></span></p></td>
<td><p><span data-ttu-id="ce110-209">QVGA: iPhone 4S</span><span class="sxs-lookup"><span data-stu-id="ce110-209">QVGA: iPhone 4S</span></span></p>
<p><span data-ttu-id="ce110-210">VGA: iPhone 5</span><span class="sxs-lookup"><span data-stu-id="ce110-210">VGA: iPhone 5</span></span></p>
<p><span data-ttu-id="ce110-211">720p: iPhone 5S y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="ce110-211">720p: iPhone 5S and later</span></span></p></td>
<td><p><span data-ttu-id="ce110-212">VGA: iPad 2 y posterior/iPad mini 1 y posterior</span><span class="sxs-lookup"><span data-stu-id="ce110-212">VGA: iPad 2 and later/iPad mini 1 and later</span></span></p>
<p><span data-ttu-id="ce110-213">720p: dispositivo para iPad Air/iPad mini 2/iPad Pro y posterior</span><span class="sxs-lookup"><span data-stu-id="ce110-213">720p: iPad Air/iPad mini 2/iPad Pro and later</span></span></p></td>
<td><p><span data-ttu-id="ce110-214">Hasta VGA en función del modelo de dispositivo</span><span class="sxs-lookup"><span data-stu-id="ce110-214">Up to VGA depending on device model</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce110-215">Resolución máxima de codificación H. 264</span><span class="sxs-lookup"><span data-stu-id="ce110-215">H.264 decoding maximum resolution</span></span></p></td>
<td><p><span data-ttu-id="ce110-216">VGA</span><span class="sxs-lookup"><span data-stu-id="ce110-216">VGA</span></span></p></td>
<td><p><span data-ttu-id="ce110-217">QVGA: iPhone 4S</span><span class="sxs-lookup"><span data-stu-id="ce110-217">QVGA: iPhone 4S</span></span></p>
<p><span data-ttu-id="ce110-218">VGA: iPhone 5</span><span class="sxs-lookup"><span data-stu-id="ce110-218">VGA: iPhone 5</span></span></p>
<p><span data-ttu-id="ce110-219">720p: iPhone 5S y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="ce110-219">720p: iPhone 5S and later</span></span></p></td>
<td><p><span data-ttu-id="ce110-220">VGA: iPad 2 y posterior/iPad mini 1 y posterior</span><span class="sxs-lookup"><span data-stu-id="ce110-220">VGA: iPad 2 and later/iPad mini 1 and later</span></span></p>
<p><span data-ttu-id="ce110-221">720p: dispositivo para iPad Air/iPad mini 2/iPad Pro y posterior</span><span class="sxs-lookup"><span data-stu-id="ce110-221">720p: iPad Air/iPad mini 2/iPad Pro and later</span></span></p></td>
<td><p><span data-ttu-id="ce110-222">Hasta VGA en función del modelo de dispositivo</span><span class="sxs-lookup"><span data-stu-id="ce110-222">Up to VGA depending on device model</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

