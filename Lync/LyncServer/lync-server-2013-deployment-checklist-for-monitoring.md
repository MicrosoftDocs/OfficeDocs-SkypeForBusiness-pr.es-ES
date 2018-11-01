---
title: 'Lync Server 2013: Lista de comprobación para la supervisión'
TOCTitle: Lista de comprobación para la supervisión
ms:assetid: 4e798370-277c-4391-84b4-13a972b45ca6
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204874(v=OCS.15)
ms:contentKeyID: 48275237
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lista de comprobación para la supervisión en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

Aunque la supervisión ya esté instalada y activada en cada servidor front-end, todavía hay varios pasos que debe realizar antes de que realmente pueda recopilar datos de supervisión para Microsoft Lync Server 2013. Estos pasos se describen en la siguiente lista de comprobación:


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
<td><p><strong>Instalar los requisitos previos de hardware y software</strong></p></td>
<td><p>Instalar una versión compatible de Microsoft SQL Server en el PC que actuará como almacén de datos back-end para la supervisión.</p></td>
<td><p>Usuario de dominio que también es miembro del grupo de administradores locales</p></td>
<td><p><a href="lync-server-2013-supported-hardware.md">Hardware admitido en Lync Server 2013</a> en la Guía sobre compatibilidad</p>
<p><a href="lync-server-2013-server-software-and-infrastructure-support.md">Software de servidor y compatibilidad con la infraestructura en Lync Server 2013</a> en la Guía sobre compatibilidad</p></td>
</tr>
<tr class="odd">
<td><p><strong>Crear la topología interna adecuada para admitir la supervisión</strong></p></td>
<td><p>Usar el Generador de topologías de Lync Server 2013 para agregar la supervisión de bases de datos para la topología, después publicar la topología actualizada.</p></td>
<td><p>Para definir una topología, un usuario que sea miembro del grupo de usuarios locales</p>
<p>Para publicar la topología, un usuario que sea miembro del grupo de administradores del dominio y del grupo RTCUniversalServerAdmins.</p></td>
<td><p><a href="lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md">Asociación de un almacén de supervisión a un grupo de servidores front-end en Lync Server 2013</a> en la Guía de implementación</p></td>
</tr>
<tr class="even">
<td><p><strong>Habilitar la configuración de supervisión adecuada</strong></p></td>
<td><p>Habilitar el registro detallado de llamadas (CDR) y/o la supervisión de la calidad de la experiencia (QoE) en los ámbitos del sitio y/o global.</p></td>
<td><p>Un usuario que sea miembro del grupo RTCUniversalServerAdmins o que tiene asignado un rol RBAC que proporciona acceso a los cmdlets de CsCdrConfiguration y CsQoEConfiguration.</p></td>
<td><p><a href="lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md">Configuración de la grabación de detalles de llamada y la calidad de la experiencia en Lync Server 2013</a> en la Guía de operaciones</p></td>
</tr>
</tbody>
</table>

