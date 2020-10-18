---
title: 'Lync Server 2013: configuración de escenarios de ejemplo de vídeo'
description: 'Lync Server 2013: configuración de escenarios de ejemplo de vídeo.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring video example scenarios
ms:assetid: da0d61a2-7ac4-4562-bf6a-18473a29acb2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205297(v=OCS.15)
ms:contentKeyID: 48185536
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 625899887926de9afe2e6ff94df70ab725c0190a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575146"
---
# <a name="configuring-video-example-scenarios-for-lync-server-2013"></a><span data-ttu-id="64d28-103">Configuración de escenarios de ejemplo de vídeo para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="64d28-103">Configuring video example scenarios for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="64d28-104">_**Última modificación del tema:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="64d28-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="64d28-105">Lync 2013 agrega nuevas características de vídeo para admitir 1920 x 1080 completo vídeo de alta definición (HD) y vídeo de la vista de galería.</span><span class="sxs-lookup"><span data-stu-id="64d28-105">Lync 2013 adds new video features to support 1920 x 1080 full high definition (HD) video and Gallery View video.</span></span> <span data-ttu-id="64d28-106">Las medidas basadas en datos de clientes muestran que el ancho de banda de vídeo típico aumentó ligeramente en comparación con Lync 2010, pero el ancho de banda de vídeo máximo ha aumentado debido a la compatibilidad con alta definición de disco (para obtener más información, consulte la sección "uso de red de tráfico de medios" en [requisitos de ancho de banda de red para el tráfico multimedia en Lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md)).</span><span class="sxs-lookup"><span data-stu-id="64d28-106">Measurements based on customer data show that the typical video bandwidth increased only slightly compared to Lync 2010, but the maximum video stream bandwidth has increased due to full HD support (for details, see the "Media Traffic Network Usage" section in [Network bandwidth requirements for media traffic in Lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md)).</span></span> <span data-ttu-id="64d28-107">Por lo tanto, posiblemente los administradores decidan restringir el ancho de banda del vídeo a determinados usuarios (como usuarios de sucursales con menos capacidad de red) y garantizar más fácilmente la mejor calidad de vídeo posible para los demás usuarios (como ejecutivos).</span><span class="sxs-lookup"><span data-stu-id="64d28-107">Therefore, administrators may want to restrict video bandwidth for certain users (such as users in a branch office that has less network capacity) and help to ensure the best possible video quality for other users (such as executives).</span></span>

<span data-ttu-id="64d28-p102">La tabla siguiente proporciona una lista de configuraciones recomendadas de vídeo para diferentes capacidades de red. Estas configuraciones restringirán en algunos escenarios de usuario el envío y la recepción de los vídeos de mayor resolución (vea la columna situada más a la derecha). En la configuración mínima, el vídeo de la galería no estará disponible debido a que el ancho de banda de red de recepción máximo es bajo.</span><span class="sxs-lookup"><span data-stu-id="64d28-p102">The following table provides a list of recommended settings for configuring video for different network capacities. These settings will restrict some user scenarios from sending and receiving higher resolution videos (see rightmost column). The minimum setting will result in Gallery Video being unavailable, due to the low maximum receive network bandwidth.</span></span>

### <a name="recommended-video-settings"></a><span data-ttu-id="64d28-111">Configuración de vídeo recomendada</span><span class="sxs-lookup"><span data-stu-id="64d28-111">Recommended Video Settings</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th>-</th>
<th><span data-ttu-id="64d28-112">AllowMultiView</span><span class="sxs-lookup"><span data-stu-id="64d28-112">AllowMultiView</span></span></th>
<th><span data-ttu-id="64d28-113">EnableMultiViewJoin</span><span class="sxs-lookup"><span data-stu-id="64d28-113">EnableMultiViewJoin</span></span></th>
<th><span data-ttu-id="64d28-114">VideoBitRateKB</span><span class="sxs-lookup"><span data-stu-id="64d28-114">VideoBitRateKB</span></span></th>
<th><span data-ttu-id="64d28-115">TotalReceiveVideoBitRateKB</span><span class="sxs-lookup"><span data-stu-id="64d28-115">TotalReceiveVideoBitRateKB</span></span></th>
<th><span data-ttu-id="64d28-116">Resolución de vídeo esperada para tener un vídeo de buena calidad</span><span class="sxs-lookup"><span data-stu-id="64d28-116">Expected video resolution for good quality video</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="64d28-117">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="64d28-117">Best</span></span></p></td>
<td><p><span data-ttu-id="64d28-118">True</span><span class="sxs-lookup"><span data-stu-id="64d28-118">True</span></span></p></td>
<td><p><span data-ttu-id="64d28-119">True</span><span class="sxs-lookup"><span data-stu-id="64d28-119">True</span></span></p></td>
<td><p><span data-ttu-id="64d28-120">8000</span><span class="sxs-lookup"><span data-stu-id="64d28-120">8000</span></span></p></td>
<td><p><span data-ttu-id="64d28-121">8000</span><span class="sxs-lookup"><span data-stu-id="64d28-121">8000</span></span></p></td>
<td><p><span data-ttu-id="64d28-122">Punto a punto: resolución de vídeo de hasta 1920 x 1080</span><span class="sxs-lookup"><span data-stu-id="64d28-122">Peer-to-peer: Up to 1920 x 1080 video resolution</span></span></p>
<p><span data-ttu-id="64d28-123">Vista de galería: hasta dos vídeos de 1920 x 1080 o varios vídeos de menor resolución</span><span class="sxs-lookup"><span data-stu-id="64d28-123">Gallery View: Up to two 1920 x 1080 videos or multiple smaller resolution videos</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64d28-124">Good</span><span class="sxs-lookup"><span data-stu-id="64d28-124">Good</span></span></p></td>
<td><p><span data-ttu-id="64d28-125">True</span><span class="sxs-lookup"><span data-stu-id="64d28-125">True</span></span></p></td>
<td><p><span data-ttu-id="64d28-126">True</span><span class="sxs-lookup"><span data-stu-id="64d28-126">True</span></span></p></td>
<td><p><span data-ttu-id="64d28-127">2500</span><span class="sxs-lookup"><span data-stu-id="64d28-127">2500</span></span></p></td>
<td><p><span data-ttu-id="64d28-128">2500</span><span class="sxs-lookup"><span data-stu-id="64d28-128">2500</span></span></p></td>
<td><p><span data-ttu-id="64d28-129">Punto a punto: resolución de vídeo de hasta 1280 x 720</span><span class="sxs-lookup"><span data-stu-id="64d28-129">Peer-to-peer: Up to 1280 x 720 video resolution</span></span></p>
<p><span data-ttu-id="64d28-130">Vista de galería: hasta cinco vídeos de resolución de 640 x 360</span><span class="sxs-lookup"><span data-stu-id="64d28-130">Gallery View: Up to five 640 x 360 resolution videos</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64d28-131">Mediano</span><span class="sxs-lookup"><span data-stu-id="64d28-131">Medium</span></span></p></td>
<td><p><span data-ttu-id="64d28-132">True</span><span class="sxs-lookup"><span data-stu-id="64d28-132">True</span></span></p></td>
<td><p><span data-ttu-id="64d28-133">True</span><span class="sxs-lookup"><span data-stu-id="64d28-133">True</span></span></p></td>
<td><p><span data-ttu-id="64d28-134">1000</span><span class="sxs-lookup"><span data-stu-id="64d28-134">1000</span></span></p></td>
<td><p><span data-ttu-id="64d28-135">1000</span><span class="sxs-lookup"><span data-stu-id="64d28-135">1000</span></span></p></td>
<td><p><span data-ttu-id="64d28-136">Punto a punto: resolución de vídeo de hasta 960 x 540</span><span class="sxs-lookup"><span data-stu-id="64d28-136">Peer-to-peer: Up to 960 x 540 video resolution</span></span></p>
<p><span data-ttu-id="64d28-137">Vista de galería: hasta cinco vídeos de resolución de 424 x 240</span><span class="sxs-lookup"><span data-stu-id="64d28-137">Gallery View: Up to five 424 x 240 resolution videos</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64d28-138">Mínimo</span><span class="sxs-lookup"><span data-stu-id="64d28-138">Minimum</span></span></p></td>
<td><p><span data-ttu-id="64d28-139">Verdadero</span><span class="sxs-lookup"><span data-stu-id="64d28-139">True</span></span></p></td>
<td><p><span data-ttu-id="64d28-140">False</span><span class="sxs-lookup"><span data-stu-id="64d28-140">False</span></span></p></td>
<td><p><span data-ttu-id="64d28-141">350</span><span class="sxs-lookup"><span data-stu-id="64d28-141">350</span></span></p></td>
<td><p><span data-ttu-id="64d28-142">350</span><span class="sxs-lookup"><span data-stu-id="64d28-142">350</span></span></p></td>
<td><p><span data-ttu-id="64d28-143">Punto a punto: resolución de vídeo de hasta 424 x 240</span><span class="sxs-lookup"><span data-stu-id="64d28-143">Peer-to-peer: Up to 424 x 240 video resolution</span></span></p>
<p><span data-ttu-id="64d28-144">Vista de galería: no disponible</span><span class="sxs-lookup"><span data-stu-id="64d28-144">Gallery View: Unavailable</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="64d28-145">Use la información de la tabla anterior para implementar las nuevas características de videoconferencia de HD y de vista de galería para algunos usuarios de la organización, y permitir otras resoluciones de vídeo para otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="64d28-145">You can use the information in the preceding table to deploy the new HD video and Gallery View video conferencing features for some users in your organization, while allowing different video resolutions for others.</span></span>

<span data-ttu-id="64d28-p103">En el ejemplo siguiente, el administrador implanta las nuevas características de vídeo con la mayor calidad de vídeo disponible solo a los ejecutivos. Para los empleados de una sucursal remota con poca capacidad de red, solo se implementa la configuración mínima de la tabla anterior. Para los demás empleados, implementa la configuración "Buena" de la tabla anterior.</span><span class="sxs-lookup"><span data-stu-id="64d28-p103">In the following example, the administrator rolls out the new video features with the highest video quality available only to executives. For employees in a remote branch office that has low network capacity, only the minimum setting from the preceding table is deployed. For all other employees, the "Good" setting from the preceding table is deployed.</span></span>

<span data-ttu-id="64d28-p104">Para implantar las nuevas características a los ejecutivos, el administrador crea una directiva de conferencia con el nombre ExecutiveVideo. Esta directiva de conferencia tiene la configuración siguiente:</span><span class="sxs-lookup"><span data-stu-id="64d28-p104">To roll out the new features to the executives, the administrator creates a conferencing policy named ExecutiveVideo. This conferencing policy has the following settings:</span></span>

  - <span data-ttu-id="64d28-151">VideoBitRateKB se configura en 8000 Kbps</span><span class="sxs-lookup"><span data-stu-id="64d28-151">VideoBitRateKB is set to 8000 Kbps</span></span>

  - <span data-ttu-id="64d28-152">TotalReceiveVideoBitRateKB se configura en 8000 Kbps</span><span class="sxs-lookup"><span data-stu-id="64d28-152">TotalReceiveVideoBitRateKB is set to 8000 Kbps</span></span>

  - <span data-ttu-id="64d28-153">AllowMultiview se configura en True</span><span class="sxs-lookup"><span data-stu-id="64d28-153">AllowMultiview is set to True</span></span>

  - <span data-ttu-id="64d28-154">EnableMultiviewJoin se configura en True</span><span class="sxs-lookup"><span data-stu-id="64d28-154">EnableMultiviewJoin is set to True</span></span>

<span data-ttu-id="64d28-p105">Para los empleados de la sucursal, el administrador crea una directiva de conferencia con el nombre BranchOfficeVideo. Esta directiva de conferencia tiene la configuración siguiente:</span><span class="sxs-lookup"><span data-stu-id="64d28-p105">For employees in the branch office, the administrator creates a conferencing policy named BranchOfficeVideo. This conferencing policy has the following settings:</span></span>

  - <span data-ttu-id="64d28-157">VideoBitRateKB se configura en 350 Kbps</span><span class="sxs-lookup"><span data-stu-id="64d28-157">VideoBitRateKB is set to 350 Kbps</span></span>

  - <span data-ttu-id="64d28-158">TotalReceiveVideoBitRateKB se configura en 350 Kbps</span><span class="sxs-lookup"><span data-stu-id="64d28-158">TotalReceiveVideoBitRateKB is set to 350 Kbps</span></span>

  - <span data-ttu-id="64d28-159">AllowMultiview se configura en True</span><span class="sxs-lookup"><span data-stu-id="64d28-159">AllowMultiview is set to True</span></span>

  - <span data-ttu-id="64d28-160">EnableMultiviewJoin se configura en False</span><span class="sxs-lookup"><span data-stu-id="64d28-160">EnableMultiviewJoin is set to False</span></span>

<span data-ttu-id="64d28-p106">Para todos los empleados, el administrador crea una directiva de conferencia con el nombre StandardVideo. Esta directiva de conferencia tiene la configuración siguiente:</span><span class="sxs-lookup"><span data-stu-id="64d28-p106">For all other employees, the administrator creates a conferencing policy named StandardVideo. This conferencing policy has the following settings:</span></span>

  - <span data-ttu-id="64d28-163">VideoBitRateKB se configura en 2500 Kbps</span><span class="sxs-lookup"><span data-stu-id="64d28-163">VideoBitRateKB is set to 2500 Kbps</span></span>

  - <span data-ttu-id="64d28-164">TotalReceiveVideoBitRateKB se configura en 2500 Kbps</span><span class="sxs-lookup"><span data-stu-id="64d28-164">TotalReceiveVideoBitRateKB is set to 2500 Kbps</span></span>

  - <span data-ttu-id="64d28-165">AllowMultiview se configura en True</span><span class="sxs-lookup"><span data-stu-id="64d28-165">AllowMultiview is set to True</span></span>

  - <span data-ttu-id="64d28-166">EnableMultiviewJoin se configura en True</span><span class="sxs-lookup"><span data-stu-id="64d28-166">EnableMultiviewJoin is set to True</span></span>

<span data-ttu-id="64d28-167">El administrador asigna la directiva de conferencia a los usuarios como sigue:</span><span class="sxs-lookup"><span data-stu-id="64d28-167">The administrator assigns conferencing policy to users as follows:</span></span>

  - <span data-ttu-id="64d28-168">La directiva de conferencia ExecutiveVideo se asigna a los ejecutivos.</span><span class="sxs-lookup"><span data-stu-id="64d28-168">The ExecutiveVideo conferencing policy is assigned to the executives.</span></span>

  - <span data-ttu-id="64d28-169">La directiva de conferencia BranchOfficeVideo se asigna a todos los empleados de la sucursal.</span><span class="sxs-lookup"><span data-stu-id="64d28-169">The BranchOfficeVideo conferencing policy is assigned to all employees in the branch office.</span></span>

  - <span data-ttu-id="64d28-170">La directiva de conferencia StandardVideo se asigna a los empleados restantes.</span><span class="sxs-lookup"><span data-stu-id="64d28-170">The StandardVideo conferencing policy is assigned to all other employees.</span></span>

<span data-ttu-id="64d28-171">Estas asignaciones de directiva de conferencia dan como resultado la siguiente experiencia de usuario:</span><span class="sxs-lookup"><span data-stu-id="64d28-171">These conferencing policy assignments result in the following user experience:</span></span>

  - <span data-ttu-id="64d28-172">Todas las conferencias organizadas por cualquier usuario son compatibles con la vista de galería, pero los empleados de la sucursal no pueden experimentar la vista de galería.</span><span class="sxs-lookup"><span data-stu-id="64d28-172">All conferences organized by any user support Gallery View, but employees in the branch office cannot experience Gallery View.</span></span>

  - <span data-ttu-id="64d28-173">En las conferencias con dos o varios participantes, los ejecutivos pueden enviar un vídeo HD completo de 1920 x 1080, si su hardware y su vínculo de red lo admiten, y pueden recibir un vídeo HD completo de 1920 x 1080 con soporte de los demás clientes participantes.</span><span class="sxs-lookup"><span data-stu-id="64d28-173">For any two-party or multiparty conferences, executives can send 1920 x 1080 full HD video, if their hardware and network link supports it, and can receive 1920 x 1080 full HD video where the other participant clients support it.</span></span>

  - <span data-ttu-id="64d28-174">Los empleados que no son ejecutivos tienen resoluciones inferiores que las de los ejecutivos en las conferencias con dos o varios participantes, aunque siguen teniendo una buena resolución.</span><span class="sxs-lookup"><span data-stu-id="64d28-174">Employees who are not executives experience lower resolutions than the executives in their two-party or multiparty conferences, but still get good resolution.</span></span>

  - <span data-ttu-id="64d28-175">Los empleados que están en la sucursal obtendrán una buena calidad de vídeo en llamadas de dos participantes cuando Lync muestre el tamaño de la ventana de vídeo predeterminada; sin embargo, si la ventana de Lync se maximiza a pantalla completa, la resolución de vídeo no se incrementará.</span><span class="sxs-lookup"><span data-stu-id="64d28-175">Employees who are in the branch office will get good video quality in two-party calls when Lync displays the default video window size; however, if the Lync window is maximized to full screen, the video resolution will not increase.</span></span> <span data-ttu-id="64d28-176">En las conferencias con varios participantes, los empleados de la sucursal solo verán un vídeo activo.</span><span class="sxs-lookup"><span data-stu-id="64d28-176">For multiparty conferences, the employees in the branch office will see only one active video.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

