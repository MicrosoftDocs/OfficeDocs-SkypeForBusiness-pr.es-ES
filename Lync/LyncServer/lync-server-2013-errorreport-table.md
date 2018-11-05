---
title: 'Lync Server 2013: Tabla ErrorReport'
TOCTitle: Tabla ErrorReport
ms:assetid: ae0287b4-e8ca-4f8c-84ef-502897dcaa2a
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg412826(v=OCS.15)
ms:contentKeyID: 48276353
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Tabla ErrorReport en Lync Server 2013

 

_**Última modificación del tema:** 2015-06-22_

La tabla ErrorReport almacena información sobre los errores generados. Cada registro corresponde a una repetición de un error. Los errores o bien los captura el agente CDR que se ejecuta en el servidor front-end o los envía el cliente.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Columna</th>
<th>Tipo de datos</th>
<th>Clave o índice</th>
<th>Detalles</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ErrorTime</strong></p></td>
<td><p>Datetime</p></td>
<td><p>Principal</p></td>
<td><p>Fecha y hora en que se produjo el error.</p></td>
</tr>
<tr class="even">
<td><p><strong>ErrorReportSeq</strong></p></td>
<td><p>Int</p></td>
<td><p>Principal</p></td>
<td><p>Número para identificar el informe de errores. Se usa junto con <strong>ErrorTime</strong> como identificación única de un informe de errores.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ErrorId</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>Identificador único del tipo de error. Para más información, vea la <a href="lync-server-2013-errordef-table.md">Tabla ErrorDef en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>FromUserId</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>Usuario de origen de la solicitud que generó el error. Para más información, vea la <a href="lync-server-2013-users-table.md">Tabla Users en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToUserId</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>Usuario de destino de la solicitud que generó el error. Para más información, vea la <a href="lync-server-2013-users-table.md">Tabla Users en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceUriId</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>URI de conferencia relacionado con el error. Para más información, vea la <a href="lync-server-2013-conferenceuris-table.md">Tabla ConferenceUris en Lync Server 2013</a>. Normalmente, si ConferenceUriId no tiene un valor NULL, FromUserId o ToUserId sí lo tendrán.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>Datetime</p></td>
<td><p>Externa</p></td>
<td><p>Se usa junto con <strong>SessionIdSeq</strong> como identificación única de una sesión. Para más información, vea la <a href="lync-server-2013-dialogs-table.md">Tabla Dialogs en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>Número para identificar la sesión. Se usa junto con <strong>SessionIdTime</strong> como identificación única de una sesión. Para más información, vea la <a href="lync-server-2013-dialogs-table.md">Tabla Dialogs en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SourceId</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>Servidor que envió el informe de errores (si el informe se envía desde un componente de servidor). Para más información, vea la <a href="lync-server-2013-servers-table.md">Tabla Servers en Lync Server 2013</a>.</p>
<p>Este campo se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>ApplicationId</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>Servidor que envió el informe de errores (si el informe se envía desde un componente de servidor). Para más información, vea la <a href="lync-server-2013-application-table.md">Tabla Application en Lync Server 2013</a>.</p>
<p>Este campo se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagHeader</strong></p></td>
<td><p>imagen</p></td>
<td><p> </p></td>
<td><p>Más información sobre el error.</p>
<p>Estos datos pueden convertirse en formato de texto con esta sintaxis:</p>
<p><code>cast(cast(Detail as varbinary(max)) as varchar(max)) </code></p></td>
</tr>
<tr class="even">
<td><p><strong>ClientVersionId</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>La versión de cliente del extremo que envía el informe de errores. Para más información, vea la <a href="lync-server-2013-clientversions-table.md">Tabla ClientVersions en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsCapturedByServer</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>Indica si el informe de errores se capturó mediante el agente CDR que se ejecuta en el servidor front-end o si lo envió el cliente.</p></td>
</tr>
<tr class="even">
<td><p><strong>Flag</strong></p></td>
<td><p>smallint</p></td>
<td><p></p></td>
<td><p>Reservado para uso futuro.</p></td>
</tr>
<tr class="odd">
<td><p><strong>TelemetryId</strong></p></td>
<td><p>uniqueIdentifier</p></td>
<td><p></p></td>
<td><p>Identificador único que correlaciona la información de la hora de unión de los componentes que participan en una conferencia.</p>
<p>Este campo se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSetupTime</strong></p></td>
<td><p>Int</p></td>
<td><p></p></td>
<td><p>Tiempo (en milisegundos) que necesita un componente determinado para unirse a una conferencia.</p>
<p>Este campo se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ServerId</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>Representa el nombre de dominio completo del servidor que generó el informe de errores.</p></td>
</tr>
<tr class="even">
<td><p><strong>PoolId</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>Representa el nombre de dominio completo del grupo en el que se generó el informe de errores.</p></td>
</tr>
</tbody>
</table>

