---
title: 'Lync Server 2013: Procesos de implementación para la aplicación Anuncio'
TOCTitle: Procesos de implementación para la aplicación Anuncio
ms:assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398545(v=OCS.15)
ms:contentKeyID: 48275639
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Procesos de implementación para la aplicación Anuncio en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

En esta sección se describe de forma general el proceso necesario para implementar la Aplicación de anuncio. Debe implementar Telefonía IP empresarial para poder configurar anuncios. Los componentes que la Aplicación de anuncio necesita se instalan y habilitan al implementar Telefonía IP empresarial.

### Proceso de implementación de anuncios

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Fase</th>
<th>Pasos</th>
<th>Roles</th>
<th>Documentación de implementación</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Configurar opciones de anuncio</p></td>
<td><ul>
<li><p>Cree el anuncio grabando y cargando archivos de audio, o bien usando texto a voz (TTS).</p></li>
<li><p>Configure los intervalos de números no asignados de la tabla de números no asignados y asócielos al anuncio correspondiente.</p></li>
</ul></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p>
<p>CsViewOnlyAdministrator</p></td>
<td><p><a href="lync-server-2013-create-an-announcement.md">Crear un anuncio en Lync Server 2013</a></p>
<p><a href="lync-server-2013-configure-the-unassigned-number-table.md">Configurar la tabla de números sin asignar en Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Comprobar la implementación de anuncios</p></td>
<td><p>Escuche los anuncios para comprobar que la configuración funciona correctamente.</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-optional-verify-announcement-deployment.md">(Opcional) Comprobar la implementación de Anuncio en Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>

