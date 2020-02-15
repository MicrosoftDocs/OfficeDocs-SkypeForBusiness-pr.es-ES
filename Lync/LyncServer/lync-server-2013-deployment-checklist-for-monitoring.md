---
title: 'Lync Server 2013: lista de comprobación de implementación para supervisión'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for monitoring
ms:assetid: 4e798370-277c-4391-84b4-13a972b45ca6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204874(v=OCS.15)
ms:contentKeyID: 48184080
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26fd0c34d51445902e7f00439dd210ddfd64f392
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049472"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-monitoring-in-lync-server-2013"></a>Lista de comprobación de implementación para la supervisión en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-05_

Aunque la supervisión ya está instalada y activa en cada servidor front-end, existen varios pasos que debe realizar antes de poder recopilar datos de supervisión para Microsoft Lync Server 2013. Estos pasos se describen en la siguiente lista de comprobación:


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Fase</p></td>
<td><p>Pasos</p></td>
<td><p>Roles y pertenencia a grupos</p></td>
<td><p>Documentación</p></td>
</tr>
<tr class="even">
<td><p><strong>Instalar el hardware y el software necesario como requisito previo</strong></p></td>
<td><p>Instalar una versión compatible de Microsoft SQL Server en el PC que actuará como almacén de datos back-end para la supervisión.</p></td>
<td><p>Usuario de dominio que también es miembro del grupo de administradores locales</p></td>
<td><p><a href="lync-server-2013-supported-hardware.md">Hardware compatible para Lync Server 2013</a> en la guía de compatibilidad</p>
<p><a href="lync-server-2013-server-software-and-infrastructure-support.md">Software de servidor y compatibilidad con la infraestructura en Lync Server 2013</a> en la guía de compatibilidad</p></td>
</tr>
<tr class="odd">
<td><p><strong>Crear la topología interna adecuada para admitir la supervisión</strong></p></td>
<td><p>Use el generador de topologías de Lync Server 2013 para agregar bases de datos de supervisión a la topología y, a continuación, publique la topología actualizada.</p></td>
<td><p>Para definir una topología, un usuario que sea miembro del grupo de usuarios locales</p>
<p>Para publicar la topología, un usuario que sea miembro del grupo de administradores del dominio y del grupo RTCUniversalServerAdmins.</p></td>
<td><p><a href="lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md">Asociar un almacén de supervisión a un grupo de servidores front-end en Lync Server 2013</a> en la guía de implementación</p></td>
</tr>
<tr class="even">
<td><p><strong>Habilitar la configuración de supervisión adecuada</strong></p></td>
<td><p>Habilitar el registro detallado de llamadas (CDR) y/o la supervisión de la calidad de la experiencia (QoE) en los ámbitos del sitio y/o global.</p></td>
<td><p>Un usuario que sea miembro del grupo RTCUniversalServerAdmins o que tiene asignado un rol RBAC que proporciona acceso a los cmdlets de CsCdrConfiguration y CsQoEConfiguration.</p></td>
<td><p><a href="lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md">Configurar el registro de detalles de llamadas y la configuración de la calidad de la experiencia en Lync Server 2013</a> en la guía de operaciones</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

