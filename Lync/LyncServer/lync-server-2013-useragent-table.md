---
title: 'Lync Server 2013: Tabla UserAgent'
TOCTitle: Tabla UserAgent
ms:assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398939(v=OCS.15)
ms:contentKeyID: 48276826
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Tabla UserAgent en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

La tabla UserAgent es una tabla auxiliar que almacena una lista de los diversos agentes de usuario que participaron en sesiones registradas en la base de datos. Cada registro en la tabla representa un agente de usuario


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Columna</strong></th>
<th><strong>Tipo de datos</strong></th>
<th><strong>Clave o índice</strong></th>
<th><strong>Detalles</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>UserAgentKey</strong></p></td>
<td><p>int</p></td>
<td><p>Principal</p></td>
<td><p>Número único que identifica este agente de usuario.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserAgent</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Única</p></td>
<td><p>Cadena de agente de usuario.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UAType</strong></p></td>
<td><p>smallint</p></td>
<td><p> </p></td>
<td><p>1 es Servidor de mediación.</p>
<p>2 es Servidor de conferencia A/V.</p>
<p>4 es Lync.</p>
<p>8 es Teléfono IP.</p>
<p>16 es Consola de Live Meeting.</p>
<p>32 es Herramienta de validación de implementación (DVT).</p>
<p>64 es Lync en equipos Macintosh.</p>
<p>128 es Operador de Office Communications Server 2007 R2.</p>
<p>256 es el servicio Anuncio de conferencia.</p>
<p>512 es Operador automático de conferencia.</p>
<p>1024 es la aplicación Grupo de respuesta.</p>
<p>2048 es Control de voz externa.</p></td>
</tr>
</tbody>
</table>

