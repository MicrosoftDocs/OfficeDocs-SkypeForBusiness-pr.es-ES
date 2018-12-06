---
title: "Vues détaillées de la qualité de l’exp. (QoE) dans Lync Server 2013"
TOCTitle: "Vues détaillées de la qualité de l’exp. (QoE) dans Lync Server 2013"
ms:assetid: 6a658318-a317-4546-a44c-a9c473d8e86a
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688081(v=OCS.15)
ms:contentKeyID: 49889218
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Detalles de la vista QoE de Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

Las vistas abarcan la mayoría de los escenarios en los que se recuperan datos de la base de datos de SQL de calidad de la experiencia. Se recomienda usar vistas para crear informes personalizados en lugar de acceder directamente a las tablas de la base de datos, ya que, en futuras versiones de producto, es más probable que las vistas conserven la compatibilidad con versiones anteriores.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Nombre de la vista</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-audiostreamdetail-view.md">Vista AudioStreamDetail</a></p></td>
<td><p>Almacena información sobre cada transmisión de audio en la base de datos.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-medialine-view.md">Vista MediaLine</a></p></td>
<td><p>Almacena información sobre cada línea de medios en la base de datos. Por lo general, una sesión de audio contiene una línea de medios de audio y una sesión de audio y video (A/V), una línea de medios de audio y otra de vídeo (si bien puede contener dos líneas de medios de vídeo si se usa un dispositivo de conferencia o la vista de galería).</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-networkconfigurationsettings-view.md">Vista NetworkConfigurationSettings</a></p></td>
<td><p>Almacena información sobre la configuración de red.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-session-view.md">Vista de Session</a></p></td>
<td><p>Almacena información sobre las sesiones que tienen registros en la base de datos.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-useragent-view.md">Vista UserAgent</a></p></td>
<td><p>Almacena información sobre los agentes de usuario que han participado en las sesiones que tienen registros en la base de datos.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-videostreamdetail-view.md">Vista VideoStreamDetail</a></p></td>
<td><p>Almacena información sobre cada transmisión de vídeo en la base de datos.</p></td>
</tr>
</tbody>
</table>

