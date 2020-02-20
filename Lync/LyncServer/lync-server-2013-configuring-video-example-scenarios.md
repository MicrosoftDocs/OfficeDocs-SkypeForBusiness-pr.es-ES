---
title: 'Lync Server 2013: configuración de escenarios de ejemplo de vídeo'
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
ms.openlocfilehash: 71eb886bb50f503b43eb757cc41310583fc11303
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154142"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-video-example-scenarios-for-lync-server-2013"></a><span data-ttu-id="6ef6a-102">Configuración de escenarios de ejemplo de vídeo para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6ef6a-102">Configuring video example scenarios for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6ef6a-103">_**Última modificación del tema:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="6ef6a-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="6ef6a-104">Lync 2013 agrega nuevas características de vídeo para admitir 1920 x 1080 completo vídeo de alta definición (HD) y vídeo de la vista de galería.</span><span class="sxs-lookup"><span data-stu-id="6ef6a-104">Lync 2013 adds new video features to support 1920 x 1080 full high definition (HD) video and Gallery View video.</span></span> <span data-ttu-id="6ef6a-105">Las medidas basadas en datos de clientes muestran que el ancho de banda de vídeo típico aumentó ligeramente en comparación con Lync 2010, pero el ancho de banda de vídeo máximo ha aumentado debido a la compatibilidad con alta definición de disco (para obtener más información, consulte la sección "uso de red de tráfico de medios" en [requisitos de ancho de banda de red para el tráfico multimedia en Lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md)).</span><span class="sxs-lookup"><span data-stu-id="6ef6a-105">Measurements based on customer data show that the typical video bandwidth increased only slightly compared to Lync 2010, but the maximum video stream bandwidth has increased due to full HD support (for details, see the "Media Traffic Network Usage" section in [Network bandwidth requirements for media traffic in Lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md)).</span></span> <span data-ttu-id="6ef6a-106">Por lo tanto, posiblemente los administradores decidan restringir el ancho de banda del vídeo a determinados usuarios (como usuarios de sucursales con menos capacidad de red) y garantizar más fácilmente la mejor calidad de vídeo posible para los demás usuarios (como ejecutivos).</span><span class="sxs-lookup"><span data-stu-id="6ef6a-106">Therefore, administrators may want to restrict video bandwidth for certain users (such as users in a branch office that has less network capacity) and help to ensure the best possible video quality for other users (such as executives).</span></span>

<span data-ttu-id="6ef6a-p102">La tabla siguiente proporciona una lista de configuraciones recomendadas de vídeo para diferentes capacidades de red. Estas configuraciones restringirán en algunos escenarios de usuario el envío y la recepción de los vídeos de mayor resolución (vea la columna situada más a la derecha). En la configuración mínima, el vídeo de la galería no estará disponible debido a que el ancho de banda de red de recepción máximo es bajo.</span><span class="sxs-lookup"><span data-stu-id="6ef6a-p102">The following table provides a list of recommended settings for configuring video for different network capacities. These settings will restrict some user scenarios from sending and receiving higher resolution videos (see rightmost column). The minimum setting will result in Gallery Video being unavailable, due to the low maximum receive network bandwidth.</span></span>

### <a name="recommended-video-settings"></a><span data-ttu-id="6ef6a-110">Configuración de vídeo recomendada</span><span class="sxs-lookup"><span data-stu-id="6ef6a-110">Recommended Video Settings</span></span>

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
<th><span data-ttu-id="6ef6a-111">AllowMultiView</span><span class="sxs-lookup"><span data-stu-id="6ef6a-111">AllowMultiView</span></span></th>
<th><span data-ttu-id="6ef6a-112">EnableMultiViewJoin</span><span class="sxs-lookup"><span data-stu-id="6ef6a-112">EnableMultiViewJoin</span></span></th>
<th><span data-ttu-id="6ef6a-113">VideoBitRateKB</span><span class="sxs-lookup"><span data-stu-id="6ef6a-113">VideoBitRateKB</span></span></th>
<th><span data-ttu-id="6ef6a-114">TotalReceiveVideoBitRateKB</span><span class="sxs-lookup"><span data-stu-id="6ef6a-114">TotalReceiveVideoBitRateKB</span></span></th>
<th><span data-ttu-id="6ef6a-115">Resolución de vídeo esperada para tener un vídeo de buena calidad</span><span class="sxs-lookup"><span data-stu-id="6ef6a-115">Expected video resolution for good quality video</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6ef6a-116">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="6ef6a-116">Best</span></span></p></td>
<td><p><span data-ttu-id="6ef6a-117">True</span><span class="sxs-lookup"><span data-stu-id="6ef6a-117">True</span></span></p></td>
<td><p><span data-ttu-id="6ef6a-118">True</span><span class="sxs-lookup"><span data-stu-id="6ef6a-118">True</span></span></p></td>
<td><p><span data-ttu-id="6ef6a-119">8000</span><span class="sxs-lookup"><span data-stu-id="6ef6a-119">8000</span></span></p></td>
<td><p><span data-ttu-id="6ef6a-120">8000</span><span class="sxs-lookup"><span data-stu-id="6ef6a-120">8000</span></span></p></td>
<td><p><span data-ttu-id="6ef6a-121">Punto a punto: resolución de vídeo de hasta 1920 x 1080</span><span class="sxs-lookup"><span data-stu-id="6ef6a-121">Peer-to-peer: Up to 1920 x 1080 video resolution</span></span></p>
<p><span data-ttu-id="6ef6a-122">Vista de galería: hasta dos vídeos de 1920 x 1080 o varios vídeos de menor resolución</span><span class="sxs-lookup"><span data-stu-id="6ef6a-122">Gallery View: Up to two 1920 x 1080 videos or multiple smaller resolution videos</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ef6a-123">Good</span><span class="sxs-lookup"><span data-stu-id="6ef6a-123">Good</span></span></p></td>
<td><p><span data-ttu-id="6ef6a-124">True</span><span class="sxs-lookup"><span data-stu-id="6ef6a-124">True</span></span></p></td>
<td><p><span data-ttu-id="6ef6a-125">True</span><span class="sxs-lookup"><span data-stu-id="6ef6a-125">True</span></span></p></td>
<td><p><span data-ttu-id="6ef6a-126">2500</span><span class="sxs-lookup"><span data-stu-id="6ef6a-126">2500</span></span></p></td>
<td><p><span data-ttu-id="6ef6a-127">2500</span><span class="sxs-lookup"><span data-stu-id="6ef6a-127">2500</span></span></p></td>
<td><p><span data-ttu-id="6ef6a-128">Punto a punto: resolución de vídeo de hasta 1280 x 720</span><span class="sxs-lookup"><span data-stu-id="6ef6a-128">Peer-to-peer: Up to 1280 x 720 video resolution</span></span></p>
<p><span data-ttu-id="6ef6a-129">Vista de galería: hasta cinco vídeos de resolución de 640 x 360</span><span class="sxs-lookup"><span data-stu-id="6ef6a-129">Gallery View: Up to five 640 x 360 resolution videos</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ef6a-130">Medio</span><span class="sxs-lookup"><span data-stu-id="6ef6a-130">Medium</span></span></p></td>
<td><p><span data-ttu-id="6ef6a-131">True</span><span class="sxs-lookup"><span data-stu-id="6ef6a-131">True</span></span></p></td>
<td><p><span data-ttu-id="6ef6a-132">True</span><span class="sxs-lookup"><span data-stu-id="6ef6a-132">True</span></span></p></td>
<td><p><span data-ttu-id="6ef6a-133">1000</span><span class="sxs-lookup"><span data-stu-id="6ef6a-133">1000</span></span></p></td>
<td><p><span data-ttu-id="6ef6a-134">1000</span><span class="sxs-lookup"><span data-stu-id="6ef6a-134">1000</span></span></p></td>
<td><p><span data-ttu-id="6ef6a-135">Punto a punto: resolución de vídeo de hasta 960 x 540</span><span class="sxs-lookup"><span data-stu-id="6ef6a-135">Peer-to-peer: Up to 960 x 540 video resolution</span></span></p>
<p><span data-ttu-id="6ef6a-136">Vista de galería: hasta cinco vídeos de resolución de 424 x 240</span><span class="sxs-lookup"><span data-stu-id="6ef6a-136">Gallery View: Up to five 424 x 240 resolution videos</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ef6a-137">Valor</span><span class="sxs-lookup"><span data-stu-id="6ef6a-137">Minimum</span></span></p></td>
<td><p><span data-ttu-id="6ef6a-138">True</span><span class="sxs-lookup"><span data-stu-id="6ef6a-138">True</span></span></p></td>
<td><p><span data-ttu-id="6ef6a-139">False</span><span class="sxs-lookup"><span data-stu-id="6ef6a-139">False</span></span></p></td>
<td><p><span data-ttu-id="6ef6a-140">350</span><span class="sxs-lookup"><span data-stu-id="6ef6a-140">350</span></span></p></td>
<td><p><span data-ttu-id="6ef6a-141">350</span><span class="sxs-lookup"><span data-stu-id="6ef6a-141">350</span></span></p></td>
<td><p><span data-ttu-id="6ef6a-142">Punto a punto: resolución de vídeo de hasta 424 x 240</span><span class="sxs-lookup"><span data-stu-id="6ef6a-142">Peer-to-peer: Up to 424 x 240 video resolution</span></span></p>
<p><span data-ttu-id="6ef6a-143">Vista de galería: no disponible</span><span class="sxs-lookup"><span data-stu-id="6ef6a-143">Gallery View: Unavailable</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="6ef6a-144">Use la información de la tabla anterior para implementar las nuevas características de videoconferencia de HD y de vista de galería para algunos usuarios de la organización, y permitir otras resoluciones de vídeo para otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="6ef6a-144">You can use the information in the preceding table to deploy the new HD video and Gallery View video conferencing features for some users in your organization, while allowing different video resolutions for others.</span></span>

<span data-ttu-id="6ef6a-p103">En el ejemplo siguiente, el administrador implanta las nuevas características de vídeo con la mayor calidad de vídeo disponible solo a los ejecutivos. Para los empleados de una sucursal remota con poca capacidad de red, solo se implementa la configuración mínima de la tabla anterior. Para los demás empleados, implementa la configuración "Buena" de la tabla anterior.</span><span class="sxs-lookup"><span data-stu-id="6ef6a-p103">In the following example, the administrator rolls out the new video features with the highest video quality available only to executives. For employees in a remote branch office that has low network capacity, only the minimum setting from the preceding table is deployed. For all other employees, the "Good" setting from the preceding table is deployed.</span></span>

<span data-ttu-id="6ef6a-p104">Para implantar las nuevas características a los ejecutivos, el administrador crea una directiva de conferencia con el nombre ExecutiveVideo. Esta directiva de conferencia tiene la configuración siguiente:</span><span class="sxs-lookup"><span data-stu-id="6ef6a-p104">To roll out the new features to the executives, the administrator creates a conferencing policy named ExecutiveVideo. This conferencing policy has the following settings:</span></span>

  - <span data-ttu-id="6ef6a-150">VideoBitRateKB se configura en 8000 Kbps</span><span class="sxs-lookup"><span data-stu-id="6ef6a-150">VideoBitRateKB is set to 8000 Kbps</span></span>

  - <span data-ttu-id="6ef6a-151">TotalReceiveVideoBitRateKB se configura en 8000 Kbps</span><span class="sxs-lookup"><span data-stu-id="6ef6a-151">TotalReceiveVideoBitRateKB is set to 8000 Kbps</span></span>

  - <span data-ttu-id="6ef6a-152">AllowMultiview se configura en True</span><span class="sxs-lookup"><span data-stu-id="6ef6a-152">AllowMultiview is set to True</span></span>

  - <span data-ttu-id="6ef6a-153">EnableMultiviewJoin se configura en True</span><span class="sxs-lookup"><span data-stu-id="6ef6a-153">EnableMultiviewJoin is set to True</span></span>

<span data-ttu-id="6ef6a-p105">Para los empleados de la sucursal, el administrador crea una directiva de conferencia con el nombre BranchOfficeVideo. Esta directiva de conferencia tiene la configuración siguiente:</span><span class="sxs-lookup"><span data-stu-id="6ef6a-p105">For employees in the branch office, the administrator creates a conferencing policy named BranchOfficeVideo. This conferencing policy has the following settings:</span></span>

  - <span data-ttu-id="6ef6a-156">VideoBitRateKB se configura en 350 Kbps</span><span class="sxs-lookup"><span data-stu-id="6ef6a-156">VideoBitRateKB is set to 350 Kbps</span></span>

  - <span data-ttu-id="6ef6a-157">TotalReceiveVideoBitRateKB se configura en 350 Kbps</span><span class="sxs-lookup"><span data-stu-id="6ef6a-157">TotalReceiveVideoBitRateKB is set to 350 Kbps</span></span>

  - <span data-ttu-id="6ef6a-158">AllowMultiview se configura en True</span><span class="sxs-lookup"><span data-stu-id="6ef6a-158">AllowMultiview is set to True</span></span>

  - <span data-ttu-id="6ef6a-159">EnableMultiviewJoin se configura en False</span><span class="sxs-lookup"><span data-stu-id="6ef6a-159">EnableMultiviewJoin is set to False</span></span>

<span data-ttu-id="6ef6a-p106">Para todos los empleados, el administrador crea una directiva de conferencia con el nombre StandardVideo. Esta directiva de conferencia tiene la configuración siguiente:</span><span class="sxs-lookup"><span data-stu-id="6ef6a-p106">For all other employees, the administrator creates a conferencing policy named StandardVideo. This conferencing policy has the following settings:</span></span>

  - <span data-ttu-id="6ef6a-162">VideoBitRateKB se configura en 2500 Kbps</span><span class="sxs-lookup"><span data-stu-id="6ef6a-162">VideoBitRateKB is set to 2500 Kbps</span></span>

  - <span data-ttu-id="6ef6a-163">TotalReceiveVideoBitRateKB se configura en 2500 Kbps</span><span class="sxs-lookup"><span data-stu-id="6ef6a-163">TotalReceiveVideoBitRateKB is set to 2500 Kbps</span></span>

  - <span data-ttu-id="6ef6a-164">AllowMultiview se configura en True</span><span class="sxs-lookup"><span data-stu-id="6ef6a-164">AllowMultiview is set to True</span></span>

  - <span data-ttu-id="6ef6a-165">EnableMultiviewJoin se configura en True</span><span class="sxs-lookup"><span data-stu-id="6ef6a-165">EnableMultiviewJoin is set to True</span></span>

<span data-ttu-id="6ef6a-166">El administrador asigna la directiva de conferencia a los usuarios como sigue:</span><span class="sxs-lookup"><span data-stu-id="6ef6a-166">The administrator assigns conferencing policy to users as follows:</span></span>

  - <span data-ttu-id="6ef6a-167">La directiva de conferencia ExecutiveVideo se asigna a los ejecutivos.</span><span class="sxs-lookup"><span data-stu-id="6ef6a-167">The ExecutiveVideo conferencing policy is assigned to the executives.</span></span>

  - <span data-ttu-id="6ef6a-168">La directiva de conferencia BranchOfficeVideo se asigna a todos los empleados de la sucursal.</span><span class="sxs-lookup"><span data-stu-id="6ef6a-168">The BranchOfficeVideo conferencing policy is assigned to all employees in the branch office.</span></span>

  - <span data-ttu-id="6ef6a-169">La directiva de conferencia StandardVideo se asigna a los empleados restantes.</span><span class="sxs-lookup"><span data-stu-id="6ef6a-169">The StandardVideo conferencing policy is assigned to all other employees.</span></span>

<span data-ttu-id="6ef6a-170">Estas asignaciones de directiva de conferencia dan como resultado la siguiente experiencia de usuario:</span><span class="sxs-lookup"><span data-stu-id="6ef6a-170">These conferencing policy assignments result in the following user experience:</span></span>

  - <span data-ttu-id="6ef6a-171">Todas las conferencias organizadas por cualquier usuario son compatibles con la vista de galería, pero los empleados de la sucursal no pueden experimentar la vista de galería.</span><span class="sxs-lookup"><span data-stu-id="6ef6a-171">All conferences organized by any user support Gallery View, but employees in the branch office cannot experience Gallery View.</span></span>

  - <span data-ttu-id="6ef6a-172">En las conferencias con dos o varios participantes, los ejecutivos pueden enviar un vídeo HD completo de 1920 x 1080, si su hardware y su vínculo de red lo admiten, y pueden recibir un vídeo HD completo de 1920 x 1080 con soporte de los demás clientes participantes.</span><span class="sxs-lookup"><span data-stu-id="6ef6a-172">For any two-party or multiparty conferences, executives can send 1920 x 1080 full HD video, if their hardware and network link supports it, and can receive 1920 x 1080 full HD video where the other participant clients support it.</span></span>

  - <span data-ttu-id="6ef6a-173">Los empleados que no son ejecutivos tienen resoluciones inferiores que las de los ejecutivos en las conferencias con dos o varios participantes, aunque siguen teniendo una buena resolución.</span><span class="sxs-lookup"><span data-stu-id="6ef6a-173">Employees who are not executives experience lower resolutions than the executives in their two-party or multiparty conferences, but still get good resolution.</span></span>

  - <span data-ttu-id="6ef6a-174">Los empleados que están en la sucursal obtendrán una buena calidad de vídeo en llamadas de dos participantes cuando Lync muestre el tamaño de la ventana de vídeo predeterminada; sin embargo, si la ventana de Lync se maximiza a pantalla completa, la resolución de vídeo no se incrementará.</span><span class="sxs-lookup"><span data-stu-id="6ef6a-174">Employees who are in the branch office will get good video quality in two-party calls when Lync displays the default video window size; however, if the Lync window is maximized to full screen, the video resolution will not increase.</span></span> <span data-ttu-id="6ef6a-175">En las conferencias con varios participantes, los empleados de la sucursal solo verán un vídeo activo.</span><span class="sxs-lookup"><span data-stu-id="6ef6a-175">For multiparty conferences, the employees in the branch office will see only one active video.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

