---
title: 'Lync Server 2013: configuración de escenarios de ejemplo de vídeo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring video example scenarios
ms:assetid: da0d61a2-7ac4-4562-bf6a-18473a29acb2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205297(v=OCS.15)
ms:contentKeyID: 48185536
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9800f97c8ccd49780098c29c9c6c1325b072dab5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842161"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-video-example-scenarios-for-lync-server-2013"></a><span data-ttu-id="acb9a-102">Configuración de escenarios de ejemplo de vídeo para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="acb9a-102">Configuring video example scenarios for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="acb9a-103">_**Última modificación del tema:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="acb9a-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="acb9a-104">Lync 2013 agrega nuevas características de vídeo para admitir 1920 x 1080 de vídeo de alta definición completo (HD) y la vista de vídeo de la galería.</span><span class="sxs-lookup"><span data-stu-id="acb9a-104">Lync 2013 adds new video features to support 1920 x 1080 full high definition (HD) video and Gallery View video.</span></span> <span data-ttu-id="acb9a-105">Las medidas basadas en los datos de los clientes muestran que el ancho de banda de video típico ha aumentado ligeramente comparado con Lync 2010, pero el ancho de banda de la secuencia de vídeo máxima ha aumentado debido a una compatibilidad de alta definición completa (para obtener información detallada, consulte la sección "uso de redes de tráfico de medios" en [ Requisitos de ancho de banda de red para el tráfico multimedia en Lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md)).</span><span class="sxs-lookup"><span data-stu-id="acb9a-105">Measurements based on customer data show that the typical video bandwidth increased only slightly compared to Lync 2010, but the maximum video stream bandwidth has increased due to full HD support (for details, see the "Media Traffic Network Usage" section in [Network bandwidth requirements for media traffic in Lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md)).</span></span> <span data-ttu-id="acb9a-106">Por lo tanto, es posible que los administradores deseen restringir el ancho de banda de vídeo para determinados usuarios (como usuarios de una sucursal que tiene menos capacidad de red) y ayudar a garantizar la mejor calidad de video posible para otros usuarios (como ejecutivos).</span><span class="sxs-lookup"><span data-stu-id="acb9a-106">Therefore, administrators may want to restrict video bandwidth for certain users (such as users in a branch office that has less network capacity) and help to ensure the best possible video quality for other users (such as executives).</span></span>

<span data-ttu-id="acb9a-107">En la tabla siguiente se proporciona una lista de las opciones de configuración recomendadas para configurar el vídeo para diferentes capacidades de red.</span><span class="sxs-lookup"><span data-stu-id="acb9a-107">The following table provides a list of recommended settings for configuring video for different network capacities.</span></span> <span data-ttu-id="acb9a-108">Esta configuración restringirá algunos escenarios de usuario del envío y recepción de videos de mayor resolución (consulte la columna del extremo derecho).</span><span class="sxs-lookup"><span data-stu-id="acb9a-108">These settings will restrict some user scenarios from sending and receiving higher resolution videos (see rightmost column).</span></span> <span data-ttu-id="acb9a-109">La configuración mínima provocará que el video de la galería no esté disponible debido a que el ancho de banda de la red de recepción es reducido.</span><span class="sxs-lookup"><span data-stu-id="acb9a-109">The minimum setting will result in Gallery Video being unavailable, due to the low maximum receive network bandwidth.</span></span>

### <a name="recommended-video-settings"></a><span data-ttu-id="acb9a-110">Configuración de video recomendada</span><span class="sxs-lookup"><span data-stu-id="acb9a-110">Recommended Video Settings</span></span>

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
<th><span data-ttu-id="acb9a-111">AllowMultiView</span><span class="sxs-lookup"><span data-stu-id="acb9a-111">AllowMultiView</span></span></th>
<th><span data-ttu-id="acb9a-112">EnableMultiViewJoin</span><span class="sxs-lookup"><span data-stu-id="acb9a-112">EnableMultiViewJoin</span></span></th>
<th><span data-ttu-id="acb9a-113">VideoBitRateKB</span><span class="sxs-lookup"><span data-stu-id="acb9a-113">VideoBitRateKB</span></span></th>
<th><span data-ttu-id="acb9a-114">TotalReceiveVideoBitRateKB</span><span class="sxs-lookup"><span data-stu-id="acb9a-114">TotalReceiveVideoBitRateKB</span></span></th>
<th><span data-ttu-id="acb9a-115">Resolución de video prevista para video de buena calidad</span><span class="sxs-lookup"><span data-stu-id="acb9a-115">Expected video resolution for good quality video</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="acb9a-116">Muy buena</span><span class="sxs-lookup"><span data-stu-id="acb9a-116">Best</span></span></p></td>
<td><p><span data-ttu-id="acb9a-117">True</span><span class="sxs-lookup"><span data-stu-id="acb9a-117">True</span></span></p></td>
<td><p><span data-ttu-id="acb9a-118">True</span><span class="sxs-lookup"><span data-stu-id="acb9a-118">True</span></span></p></td>
<td><p><span data-ttu-id="acb9a-119">8000</span><span class="sxs-lookup"><span data-stu-id="acb9a-119">8000</span></span></p></td>
<td><p><span data-ttu-id="acb9a-120">8000</span><span class="sxs-lookup"><span data-stu-id="acb9a-120">8000</span></span></p></td>
<td><p><span data-ttu-id="acb9a-121">De punto a punto: hasta 1920 x 1080 de resolución de video</span><span class="sxs-lookup"><span data-stu-id="acb9a-121">Peer-to-peer: Up to 1920 x 1080 video resolution</span></span></p>
<p><span data-ttu-id="acb9a-122">Vista de Galería: hasta 2 1920 x 1080 de vídeos o varios vídeos de resolución más pequeña</span><span class="sxs-lookup"><span data-stu-id="acb9a-122">Gallery View: Up to two 1920 x 1080 videos or multiple smaller resolution videos</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="acb9a-123">Good</span><span class="sxs-lookup"><span data-stu-id="acb9a-123">Good</span></span></p></td>
<td><p><span data-ttu-id="acb9a-124">True</span><span class="sxs-lookup"><span data-stu-id="acb9a-124">True</span></span></p></td>
<td><p><span data-ttu-id="acb9a-125">True</span><span class="sxs-lookup"><span data-stu-id="acb9a-125">True</span></span></p></td>
<td><p><span data-ttu-id="acb9a-126">2500</span><span class="sxs-lookup"><span data-stu-id="acb9a-126">2500</span></span></p></td>
<td><p><span data-ttu-id="acb9a-127">2500</span><span class="sxs-lookup"><span data-stu-id="acb9a-127">2500</span></span></p></td>
<td><p><span data-ttu-id="acb9a-128">De punto a punto: hasta 1280 x 720 de resolución de video</span><span class="sxs-lookup"><span data-stu-id="acb9a-128">Peer-to-peer: Up to 1280 x 720 video resolution</span></span></p>
<p><span data-ttu-id="acb9a-129">Vista de Galería: vídeos de una resolución de hasta 5 640 x 360</span><span class="sxs-lookup"><span data-stu-id="acb9a-129">Gallery View: Up to five 640 x 360 resolution videos</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="acb9a-130">Medio</span><span class="sxs-lookup"><span data-stu-id="acb9a-130">Medium</span></span></p></td>
<td><p><span data-ttu-id="acb9a-131">True</span><span class="sxs-lookup"><span data-stu-id="acb9a-131">True</span></span></p></td>
<td><p><span data-ttu-id="acb9a-132">True</span><span class="sxs-lookup"><span data-stu-id="acb9a-132">True</span></span></p></td>
<td><p><span data-ttu-id="acb9a-133">1000</span><span class="sxs-lookup"><span data-stu-id="acb9a-133">1000</span></span></p></td>
<td><p><span data-ttu-id="acb9a-134">1000</span><span class="sxs-lookup"><span data-stu-id="acb9a-134">1000</span></span></p></td>
<td><p><span data-ttu-id="acb9a-135">De punto a punto: hasta 960 x 540 de resolución de video</span><span class="sxs-lookup"><span data-stu-id="acb9a-135">Peer-to-peer: Up to 960 x 540 video resolution</span></span></p>
<p><span data-ttu-id="acb9a-136">Vista de Galería: vídeos de una resolución de hasta 5 424 x 240</span><span class="sxs-lookup"><span data-stu-id="acb9a-136">Gallery View: Up to five 424 x 240 resolution videos</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="acb9a-137">Minima</span><span class="sxs-lookup"><span data-stu-id="acb9a-137">Minimum</span></span></p></td>
<td><p><span data-ttu-id="acb9a-138">True</span><span class="sxs-lookup"><span data-stu-id="acb9a-138">True</span></span></p></td>
<td><p><span data-ttu-id="acb9a-139">False</span><span class="sxs-lookup"><span data-stu-id="acb9a-139">False</span></span></p></td>
<td><p><span data-ttu-id="acb9a-140">350</span><span class="sxs-lookup"><span data-stu-id="acb9a-140">350</span></span></p></td>
<td><p><span data-ttu-id="acb9a-141">350</span><span class="sxs-lookup"><span data-stu-id="acb9a-141">350</span></span></p></td>
<td><p><span data-ttu-id="acb9a-142">De punto a punto: hasta 424 x 240 de resolución de video</span><span class="sxs-lookup"><span data-stu-id="acb9a-142">Peer-to-peer: Up to 424 x 240 video resolution</span></span></p>
<p><span data-ttu-id="acb9a-143">Vista de Galería: no disponible</span><span class="sxs-lookup"><span data-stu-id="acb9a-143">Gallery View: Unavailable</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="acb9a-144">Puede usar la información de la tabla anterior para implementar las nuevas características de videoconferencias en alta definición para algunos usuarios de su organización y, al mismo tiempo, permitir diferentes resoluciones de video para otras personas.</span><span class="sxs-lookup"><span data-stu-id="acb9a-144">You can use the information in the preceding table to deploy the new HD video and Gallery View video conferencing features for some users in your organization, while allowing different video resolutions for others.</span></span>

<span data-ttu-id="acb9a-145">En el siguiente ejemplo, el administrador implementa las nuevas características de vídeo con la mejor calidad de video disponible solo para los ejecutivos.</span><span class="sxs-lookup"><span data-stu-id="acb9a-145">In the following example, the administrator rolls out the new video features with the highest video quality available only to executives.</span></span> <span data-ttu-id="acb9a-146">Para los empleados de una sucursal remota con poca capacidad de red, solo se implementa la configuración mínima de la tabla anterior.</span><span class="sxs-lookup"><span data-stu-id="acb9a-146">For employees in a remote branch office that has low network capacity, only the minimum setting from the preceding table is deployed.</span></span> <span data-ttu-id="acb9a-147">Para todos los demás empleados, se implementa la configuración "buena" de la tabla anterior.</span><span class="sxs-lookup"><span data-stu-id="acb9a-147">For all other employees, the "Good" setting from the preceding table is deployed.</span></span>

<span data-ttu-id="acb9a-148">Para implementar las nuevas características para los ejecutivos, el administrador crea una directiva de conferencia denominada ExecutiveVideo.</span><span class="sxs-lookup"><span data-stu-id="acb9a-148">To roll out the new features to the executives, the administrator creates a conferencing policy named ExecutiveVideo.</span></span> <span data-ttu-id="acb9a-149">Esta directiva de conferencia tiene la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="acb9a-149">This conferencing policy has the following settings:</span></span>

  - <span data-ttu-id="acb9a-150">VideoBitRateKB se establece en 8000 Kbps</span><span class="sxs-lookup"><span data-stu-id="acb9a-150">VideoBitRateKB is set to 8000 Kbps</span></span>

  - <span data-ttu-id="acb9a-151">TotalReceiveVideoBitRateKB se establece en 8000 Kbps</span><span class="sxs-lookup"><span data-stu-id="acb9a-151">TotalReceiveVideoBitRateKB is set to 8000 Kbps</span></span>

  - <span data-ttu-id="acb9a-152">AllowMultiview se establece en true</span><span class="sxs-lookup"><span data-stu-id="acb9a-152">AllowMultiview is set to True</span></span>

  - <span data-ttu-id="acb9a-153">EnableMultiviewJoin se establece en true</span><span class="sxs-lookup"><span data-stu-id="acb9a-153">EnableMultiviewJoin is set to True</span></span>

<span data-ttu-id="acb9a-154">Para los empleados de la sucursal, el administrador crea una directiva de conferencia denominada BranchOfficeVideo.</span><span class="sxs-lookup"><span data-stu-id="acb9a-154">For employees in the branch office, the administrator creates a conferencing policy named BranchOfficeVideo.</span></span> <span data-ttu-id="acb9a-155">Esta directiva de conferencia tiene la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="acb9a-155">This conferencing policy has the following settings:</span></span>

  - <span data-ttu-id="acb9a-156">VideoBitRateKB se establece en 350 Kbps</span><span class="sxs-lookup"><span data-stu-id="acb9a-156">VideoBitRateKB is set to 350 Kbps</span></span>

  - <span data-ttu-id="acb9a-157">TotalReceiveVideoBitRateKB se establece en 350 Kbps</span><span class="sxs-lookup"><span data-stu-id="acb9a-157">TotalReceiveVideoBitRateKB is set to 350 Kbps</span></span>

  - <span data-ttu-id="acb9a-158">AllowMultiview se establece en true</span><span class="sxs-lookup"><span data-stu-id="acb9a-158">AllowMultiview is set to True</span></span>

  - <span data-ttu-id="acb9a-159">EnableMultiviewJoin se establece en false</span><span class="sxs-lookup"><span data-stu-id="acb9a-159">EnableMultiviewJoin is set to False</span></span>

<span data-ttu-id="acb9a-160">Para todos los demás empleados, el administrador crea una directiva de conferencia denominada StandardVideo.</span><span class="sxs-lookup"><span data-stu-id="acb9a-160">For all other employees, the administrator creates a conferencing policy named StandardVideo.</span></span> <span data-ttu-id="acb9a-161">Esta directiva de conferencia tiene la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="acb9a-161">This conferencing policy has the following settings:</span></span>

  - <span data-ttu-id="acb9a-162">VideoBitRateKB se establece en 2500 Kbps</span><span class="sxs-lookup"><span data-stu-id="acb9a-162">VideoBitRateKB is set to 2500 Kbps</span></span>

  - <span data-ttu-id="acb9a-163">TotalReceiveVideoBitRateKB se establece en 2500 Kbps</span><span class="sxs-lookup"><span data-stu-id="acb9a-163">TotalReceiveVideoBitRateKB is set to 2500 Kbps</span></span>

  - <span data-ttu-id="acb9a-164">AllowMultiview se establece en true</span><span class="sxs-lookup"><span data-stu-id="acb9a-164">AllowMultiview is set to True</span></span>

  - <span data-ttu-id="acb9a-165">EnableMultiviewJoin se establece en true</span><span class="sxs-lookup"><span data-stu-id="acb9a-165">EnableMultiviewJoin is set to True</span></span>

<span data-ttu-id="acb9a-166">El administrador asigna la Directiva de conferencia a los usuarios de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="acb9a-166">The administrator assigns conferencing policy to users as follows:</span></span>

  - <span data-ttu-id="acb9a-167">La Directiva de conferencia ExecutiveVideo se asigna a los ejecutivos.</span><span class="sxs-lookup"><span data-stu-id="acb9a-167">The ExecutiveVideo conferencing policy is assigned to the executives.</span></span>

  - <span data-ttu-id="acb9a-168">La Directiva de conferencia BranchOfficeVideo está asignada a todos los empleados de la sucursal.</span><span class="sxs-lookup"><span data-stu-id="acb9a-168">The BranchOfficeVideo conferencing policy is assigned to all employees in the branch office.</span></span>

  - <span data-ttu-id="acb9a-169">La Directiva de conferencia StandardVideo se asigna a los demás empleados.</span><span class="sxs-lookup"><span data-stu-id="acb9a-169">The StandardVideo conferencing policy is assigned to all other employees.</span></span>

<span data-ttu-id="acb9a-170">Estas asignaciones de directiva de Conferencia tienen la siguiente experiencia de usuario:</span><span class="sxs-lookup"><span data-stu-id="acb9a-170">These conferencing policy assignments result in the following user experience:</span></span>

  - <span data-ttu-id="acb9a-171">Todas las conferencias organizadas por cualquier usuario vista de galería de soporte técnico, pero los empleados de la sucursal no pueden usar la vista de galería.</span><span class="sxs-lookup"><span data-stu-id="acb9a-171">All conferences organized by any user support Gallery View, but employees in the branch office cannot experience Gallery View.</span></span>

  - <span data-ttu-id="acb9a-172">Para cualquier Conferencia de dos o varias partes, los ejecutivos pueden enviar 1920 x 1080 de video de alta definición, si su hardware y su vínculo de red lo admiten, y pueden recibir 1920 x 1080 de video completo de alta definición, donde los demás clientes lo admiten.</span><span class="sxs-lookup"><span data-stu-id="acb9a-172">For any two-party or multiparty conferences, executives can send 1920 x 1080 full HD video, if their hardware and network link supports it, and can receive 1920 x 1080 full HD video where the other participant clients support it.</span></span>

  - <span data-ttu-id="acb9a-173">Los empleados que no son ejecutivos sufren resoluciones más bajas que los ejecutivos de las conferencias de dos o varias partes, pero siguen teniendo una buena solución.</span><span class="sxs-lookup"><span data-stu-id="acb9a-173">Employees who are not executives experience lower resolutions than the executives in their two-party or multiparty conferences, but still get good resolution.</span></span>

  - <span data-ttu-id="acb9a-174">Los empleados que estén en la sucursal obtendrán una buena calidad de video en las llamadas de dos participantes cuando Lync muestre el tamaño predeterminado de la ventana de video; sin embargo, si la ventana de Lync se maximiza a pantalla completa, la resolución de video no aumentará.</span><span class="sxs-lookup"><span data-stu-id="acb9a-174">Employees who are in the branch office will get good video quality in two-party calls when Lync displays the default video window size; however, if the Lync window is maximized to full screen, the video resolution will not increase.</span></span> <span data-ttu-id="acb9a-175">En las conferencias de varias partes, los empleados de la sucursal solo verán un vídeo activo.</span><span class="sxs-lookup"><span data-stu-id="acb9a-175">For multiparty conferences, the employees in the branch office will see only one active video.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

