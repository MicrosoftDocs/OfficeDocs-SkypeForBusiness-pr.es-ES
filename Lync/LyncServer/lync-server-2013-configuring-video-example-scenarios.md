---
title: Configuración de escenarios de ejemplo de vídeo
TOCTitle: Configuración de escenarios de ejemplo de vídeo
ms:assetid: da0d61a2-7ac4-4562-bf6a-18473a29acb2
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205297(v=OCS.15)
ms:contentKeyID: 48276870
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuración de escenarios de ejemplo de vídeo

 

_**Última modificación del tema:** 2015-03-09_

Lync 2013 agrega características de vídeo nuevas para admitir totalmente vídeos de alta definición (HD) de 1920 x 1080 y vídeos de la vista Galería. Las medidas basadas en los datos del cliente muestran que el ancho de banda de vídeo típico solo aumentó ligeramente en comparación con Lync 2010, pero el ancho de banda máximo de la secuencia de vídeo aumentó debido al soporte completo de HD (para más información vea la sección sobre el uso de la red para el tráfico de medios en [Requisitos de ancho de banda de red para el tráfico multimedia de Lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md)). Por lo tanto, posiblemente los administradores decidan restringir el ancho de banda del vídeo a determinados usuarios (como usuarios de sucursales con menos capacidad de red) y garantizar más fácilmente la mejor calidad de vídeo posible para los demás usuarios (como ejecutivos).

La tabla siguiente proporciona una lista de configuraciones recomendadas de vídeo para diferentes capacidades de red. Estas configuraciones restringirán en algunos escenarios de usuario el envío y la recepción de los vídeos de mayor resolución (vea la columna situada más a la derecha). En la configuración mínima, el vídeo de la galería no estará disponible debido a que el ancho de banda de red de recepción máximo es bajo.

### Configuración de vídeo recomendada

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
<th>Resolución de vídeo esperada para tener un vídeo de buena calidad</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>La mejor</p></td>
<td><p>True</p></td>
<td><p>True</p></td>
<td><p>8000</p></td>
<td><p>8000</p></td>
<td><p>Punto a punto: resolución de vídeo de hasta 1920 x 1080</p>
<p>Vista de galería: hasta dos vídeos de 1920 x 1080 o varios vídeos de menor resolución</p></td>
</tr>
<tr class="even">
<td><p>Buena</p></td>
<td><p>True</p></td>
<td><p>True</p></td>
<td><p>2500</p></td>
<td><p>2500</p></td>
<td><p>Punto a punto: resolución de vídeo de hasta 1280 x 720</p>
<p>Vista de galería: hasta cinco vídeos de resolución de 640 x 360</p></td>
</tr>
<tr class="odd">
<td><p>Medio</p></td>
<td><p>True</p></td>
<td><p>True</p></td>
<td><p>1000</p></td>
<td><p>1000</p></td>
<td><p>Punto a punto: resolución de vídeo de hasta 960 x 540</p>
<p>Vista de galería: hasta cinco vídeos de resolución de 424 x 240</p></td>
</tr>
<tr class="even">
<td><p>Mínimo</p></td>
<td><p>True</p></td>
<td><p>False</p></td>
<td><p>350</p></td>
<td><p>350</p></td>
<td><p>Punto a punto: resolución de vídeo de hasta 424 x 240</p>
<p>Vista de galería: no disponible</p></td>
</tr>
</tbody>
</table>


Use la información de la tabla anterior para implementar las nuevas características de videoconferencia de HD y de vista de galería para algunos usuarios de la organización, y permitir otras resoluciones de vídeo para otros usuarios.

En el ejemplo siguiente, el administrador implanta las nuevas características de vídeo con la mayor calidad de vídeo disponible solo a los ejecutivos. Para los empleados de una sucursal remota con poca capacidad de red, solo se implementa la configuración mínima de la tabla anterior. Para los demás empleados, implementa la configuración "Buena" de la tabla anterior.

Para implantar las nuevas características a los ejecutivos, el administrador crea una directiva de conferencia con el nombre ExecutiveVideo. Esta directiva de conferencia tiene la configuración siguiente:

  - VideoBitRateKB se configura en 8000 Kbps

  - TotalReceiveVideoBitRateKB se configura en 8000 Kbps

  - AllowMultiview se configura en True

  - EnableMultiviewJoin se configura en True

Para los empleados de la sucursal, el administrador crea una directiva de conferencia con el nombre BranchOfficeVideo. Esta directiva de conferencia tiene la configuración siguiente:

  - VideoBitRateKB se configura en 350 Kbps

  - TotalReceiveVideoBitRateKB se configura en 350 Kbps

  - AllowMultiview se configura en True

  - EnableMultiviewJoin se configura en False

Para todos los empleados, el administrador crea una directiva de conferencia con el nombre StandardVideo. Esta directiva de conferencia tiene la configuración siguiente:

  - VideoBitRateKB se configura en 2500 Kbps

  - TotalReceiveVideoBitRateKB se configura en 2500 Kbps

  - AllowMultiview se configura en True

  - EnableMultiviewJoin se configura en True

El administrador asigna la directiva de conferencia a los usuarios como sigue:

  - La directiva de conferencia ExecutiveVideo se asigna a los ejecutivos.

  - La directiva de conferencia BranchOfficeVideo se asigna a todos los empleados de la sucursal.

  - La directiva de conferencia StandardVideo se asigna a los empleados restantes.

Estas asignaciones de directiva de conferencia dan como resultado la siguiente experiencia de usuario:

  - Todas las conferencias organizadas por cualquier usuario son compatibles con la vista de galería, pero los empleados de la sucursal no pueden experimentar la vista de galería.

  - En las conferencias con dos o varios participantes, los ejecutivos pueden enviar un vídeo HD completo de 1920 x 1080, si su hardware y su vínculo de red lo admiten, y pueden recibir un vídeo HD completo de 1920 x 1080 con soporte de los demás clientes participantes.

  - Los empleados que no son ejecutivos tienen resoluciones inferiores que las de los ejecutivos en las conferencias con dos o varios participantes, aunque siguen teniendo una buena resolución.

  - Los empleados de la sucursal obtendrán una buena calidad de vídeo en las llamadas con dos participantes cuando Lync muestre el tamaño de la ventana de vídeo habitual. No obstante, si la ventana de Lync se maximiza a pantalla completa, la resolución del vídeo no aumentará. Para las conferencias con varios participantes, los empleados de la sucursal solo verán un vídeo activo.

