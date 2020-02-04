---
title: 'Lync Server 2013: Lista de comprobación para la supervisión'
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
ms.openlocfilehash: 71b7d69054df266139f3f13ca0ca53e1803f44b4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762718"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-monitoring-in-lync-server-2013"></a>Lista de comprobación para la supervisión en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-05_

Aunque la supervisión ya está instalada y activa en cada servidor front-end, hay varios pasos que debe realizar antes de que pueda recopilar datos de supervisión para Microsoft Lync Server 2013. Estos pasos se describen en la siguiente lista de comprobación:


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
<td><p>Rol y pertenencia a grupos</p></td>
<td><p>Documentación</p></td>
</tr>
<tr class="even">
<td><p><strong>Instalar los requisitos previos de hardware y software</strong></p></td>
<td><p>Instale una versión compatible de Microsoft SQL Server en el equipo que actuará como almacén de datos back-end para la supervisión.</p></td>
<td><p>Usuario de dominio que también es miembro del grupo de administradores locales.</p></td>
<td><p><a href="lync-server-2013-supported-hardware.md">Hardware compatible para Lync Server 2013</a> en la guía de soporte técnico</p>
<p><a href="lync-server-2013-server-software-and-infrastructure-support.md">Compatibilidad con el software de servidor y la infraestructura en Lync Server 2013</a> en la guía de soporte técnico</p></td>
</tr>
<tr class="odd">
<td><p><strong>Crear la topología interna adecuada para admitir la supervisión</strong></p></td>
<td><p>Use el generador de topología de Lync Server 2013 para agregar bases de datos de supervisión a la topología y, después, publique la topología actualizada.</p></td>
<td><p>Para definir una topología, un usuario que sea miembro del grupo de usuarios locales.</p>
<p>Para publicar la topología, un usuario que sea miembro del grupo de administradores del dominio y del grupo RTCUniversalServerAdmins.</p></td>
<td><p><a href="lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md">Asociar una tienda de supervisión con un grupo de servidores front-end en Lync Server 2013</a> en la guía de implementación</p></td>
</tr>
<tr class="even">
<td><p><strong>Habilitar la configuración de supervisión adecuada</strong></p></td>
<td><p>Habilite la supervisión de la grabación de detalles de llamadas (CDR) o la calidad de la experiencia (QoE) en los ámbitos global y/o del sitio.</p></td>
<td><p>Un usuario que sea miembro del grupo RTCUniversalServerAdmins o que tiene asignado un rol RBAC que proporciona acceso a los cmdlets de CsCdrConfiguration y CsQoEConfiguration.</p></td>
<td><p>Configuración de la <a href="lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md">grabación de detalles de llamadas y la configuración de la calidad de la experiencia en Lync Server 2013</a> en la guía de operaciones</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

