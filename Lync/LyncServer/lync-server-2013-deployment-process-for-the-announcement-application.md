---
title: 'Lync Server 2013: proceso de implementación para la aplicación de anuncios'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for the Announcement application
ms:assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398545(v=OCS.15)
ms:contentKeyID: 48184500
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dcb56f197a32403d1207cf0a15d47e0459fc41bf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762578"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-the-announcement-application-in-lync-server-2013"></a>Proceso de implementación para la aplicación de anuncios en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-12_

Esta sección proporciona una descripción general de los pasos necesarios para implementar la aplicación de anuncios. Debe implementar la telefonía IP empresarial antes de configurar los anuncios. Los componentes requeridos por la aplicación de anuncios se instalan y se habilitan al implementar la telefonía IP empresarial.

### <a name="announcement-deployment-process"></a>Proceso de implementación de anuncios

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
<td><p><a href="lync-server-2013-optional-verify-announcement-deployment.md">Faculta Comprobar la implementación de la presentación en Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

