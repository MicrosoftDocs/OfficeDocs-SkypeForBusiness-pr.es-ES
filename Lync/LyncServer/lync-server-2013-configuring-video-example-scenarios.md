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

# <a name="configuring-video-example-scenarios-for-lync-server-2013"></a>Configuración de escenarios de ejemplo de vídeo para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-02_

Lync 2013 agrega nuevas características de vídeo para admitir 1920 x 1080 de vídeo de alta definición completo (HD) y la vista de vídeo de la galería. Las medidas basadas en los datos de los clientes muestran que el ancho de banda de video típico ha aumentado ligeramente comparado con Lync 2010, pero el ancho de banda de la secuencia de vídeo máxima ha aumentado debido a una compatibilidad de alta definición completa (para obtener información detallada, consulte la sección "uso de redes de tráfico de medios" en [ Requisitos de ancho de banda de red para el tráfico multimedia en Lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md)). Por lo tanto, es posible que los administradores deseen restringir el ancho de banda de vídeo para determinados usuarios (como usuarios de una sucursal que tiene menos capacidad de red) y ayudar a garantizar la mejor calidad de video posible para otros usuarios (como ejecutivos).

En la tabla siguiente se proporciona una lista de las opciones de configuración recomendadas para configurar el vídeo para diferentes capacidades de red. Esta configuración restringirá algunos escenarios de usuario del envío y recepción de videos de mayor resolución (consulte la columna del extremo derecho). La configuración mínima provocará que el video de la galería no esté disponible debido a que el ancho de banda de la red de recepción es reducido.

### <a name="recommended-video-settings"></a>Configuración de video recomendada

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
<th>AllowMultiView</th>
<th>EnableMultiViewJoin</th>
<th>VideoBitRateKB</th>
<th>TotalReceiveVideoBitRateKB</th>
<th>Resolución de video prevista para video de buena calidad</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Muy buena</p></td>
<td><p>True</p></td>
<td><p>True</p></td>
<td><p>8000</p></td>
<td><p>8000</p></td>
<td><p>De punto a punto: hasta 1920 x 1080 de resolución de video</p>
<p>Vista de Galería: hasta 2 1920 x 1080 de vídeos o varios vídeos de resolución más pequeña</p></td>
</tr>
<tr class="even">
<td><p>Good</p></td>
<td><p>True</p></td>
<td><p>True</p></td>
<td><p>2500</p></td>
<td><p>2500</p></td>
<td><p>De punto a punto: hasta 1280 x 720 de resolución de video</p>
<p>Vista de Galería: vídeos de una resolución de hasta 5 640 x 360</p></td>
</tr>
<tr class="odd">
<td><p>Medio</p></td>
<td><p>True</p></td>
<td><p>True</p></td>
<td><p>1000</p></td>
<td><p>1000</p></td>
<td><p>De punto a punto: hasta 960 x 540 de resolución de video</p>
<p>Vista de Galería: vídeos de una resolución de hasta 5 424 x 240</p></td>
</tr>
<tr class="even">
<td><p>Minima</p></td>
<td><p>True</p></td>
<td><p>False</p></td>
<td><p>350</p></td>
<td><p>350</p></td>
<td><p>De punto a punto: hasta 424 x 240 de resolución de video</p>
<p>Vista de Galería: no disponible</p></td>
</tr>
</tbody>
</table>


Puede usar la información de la tabla anterior para implementar las nuevas características de videoconferencias en alta definición para algunos usuarios de su organización y, al mismo tiempo, permitir diferentes resoluciones de video para otras personas.

En el siguiente ejemplo, el administrador implementa las nuevas características de vídeo con la mejor calidad de video disponible solo para los ejecutivos. Para los empleados de una sucursal remota con poca capacidad de red, solo se implementa la configuración mínima de la tabla anterior. Para todos los demás empleados, se implementa la configuración "buena" de la tabla anterior.

Para implementar las nuevas características para los ejecutivos, el administrador crea una directiva de conferencia denominada ExecutiveVideo. Esta directiva de conferencia tiene la siguiente configuración:

  - VideoBitRateKB se establece en 8000 Kbps

  - TotalReceiveVideoBitRateKB se establece en 8000 Kbps

  - AllowMultiview se establece en true

  - EnableMultiviewJoin se establece en true

Para los empleados de la sucursal, el administrador crea una directiva de conferencia denominada BranchOfficeVideo. Esta directiva de conferencia tiene la siguiente configuración:

  - VideoBitRateKB se establece en 350 Kbps

  - TotalReceiveVideoBitRateKB se establece en 350 Kbps

  - AllowMultiview se establece en true

  - EnableMultiviewJoin se establece en false

Para todos los demás empleados, el administrador crea una directiva de conferencia denominada StandardVideo. Esta directiva de conferencia tiene la siguiente configuración:

  - VideoBitRateKB se establece en 2500 Kbps

  - TotalReceiveVideoBitRateKB se establece en 2500 Kbps

  - AllowMultiview se establece en true

  - EnableMultiviewJoin se establece en true

El administrador asigna la Directiva de conferencia a los usuarios de la siguiente manera:

  - La Directiva de conferencia ExecutiveVideo se asigna a los ejecutivos.

  - La Directiva de conferencia BranchOfficeVideo está asignada a todos los empleados de la sucursal.

  - La Directiva de conferencia StandardVideo se asigna a los demás empleados.

Estas asignaciones de directiva de Conferencia tienen la siguiente experiencia de usuario:

  - Todas las conferencias organizadas por cualquier usuario vista de galería de soporte técnico, pero los empleados de la sucursal no pueden usar la vista de galería.

  - Para cualquier Conferencia de dos o varias partes, los ejecutivos pueden enviar 1920 x 1080 de video de alta definición, si su hardware y su vínculo de red lo admiten, y pueden recibir 1920 x 1080 de video completo de alta definición, donde los demás clientes lo admiten.

  - Los empleados que no son ejecutivos sufren resoluciones más bajas que los ejecutivos de las conferencias de dos o varias partes, pero siguen teniendo una buena solución.

  - Los empleados que estén en la sucursal obtendrán una buena calidad de video en las llamadas de dos participantes cuando Lync muestre el tamaño predeterminado de la ventana de video; sin embargo, si la ventana de Lync se maximiza a pantalla completa, la resolución de video no aumentará. En las conferencias de varias partes, los empleados de la sucursal solo verán un vídeo activo.

</div>

<span> </span>

</div>

</div>

</div>

