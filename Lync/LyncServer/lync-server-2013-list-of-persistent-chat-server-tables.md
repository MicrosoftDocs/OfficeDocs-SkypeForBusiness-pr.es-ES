---
title: 'Lync Server 2013: lista de tablas del servidor de chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: List of Persistent Chat Server tables
ms:assetid: 26c9e271-3516-4d90-b930-70fec4e359ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558628(v=OCS.15)
ms:contentKeyID: 48183659
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4327e2a72f91e17fd71cd198940ea01d10423b00
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034712"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-persistent-chat-server-tables-in-lync-server-2013"></a>Lista de tablas del servidor de chat persistente en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-06_

El esquema de base de datos de chat persistente consta de las siguientes tablas.

<div>

## <a name="active-directory-sync"></a>Sincronización de Active Directory


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Table</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tbladcookie.md">tblADCookie en Lync Server 2013</a></p></td>
<td><p>Contiene las cookies de sincronización del Protocolo ligero de acceso a directorios (LDAP) actual. Cada fila corresponde a un dominio de servicios de dominio de Active Directory que el servidor de chat persistente supervisa activamente los cambios. (En esta tabla solo se representan los dominios de Active Directory relevantes para el servidor de chat persistente).</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblprincipalmemberdifference.md">tblPrincipalMemberDifference en Lync Server 2013</a></p></td>
<td><p>Contiene los cambios en la pertenencia a grupos (miembros agregados y eliminados) que aún no han sido procesados por los pasos de sincronización de Active Directory posteriores y es una de las tablas temporales (junto con la tabla tblADUpdates) que se usa en el primer paso de la sincronización de Active Directory.</p>
<p>Los cambios de pertenencia se almacenan, se procesan o ambos solo para los grupos que se enumeran en la tabla tblPrincipal o que ya tienen miembros en la lista.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tbladupdates.md">tblADUpdates en Lync Server 2013</a></p></td>
<td><p>Contiene cambios en los servicios de dominio de Active Directory que todavía no han sido procesados por los pasos de sincronización de Active Directory posteriores y es una de las tablas temporales (junto con la tabla tblPrincipalMemberDifference) que se usa en el primer paso de Active Directory Sincronizándose.</p>
<p>Los cambios en Active Directory se almacenan, se procesan o ambos solo para las entidades de identidad que ya aparecen en la tabla tblPrincipal.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblprincipalmembers.md">tblPrincipalMembers en Lync Server 2013</a></p></td>
<td><p>Contiene pertenencias principales.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalmeta.md">tblPrincipalMeta en Lync Server 2013</a></p></td>
<td><p>Contiene las entidades de identidad que se deben actualizar desde Active Directory.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblskippedaffiliations.md">tblSkippedAffiliations en Lync Server 2013</a></p></td>
<td><p>Contiene las afiliaciones que no se pudieron actualizar por algún motivo, normalmente debido a errores de acceso de Active Directory.</p>
<p>Esta tabla es solo para fines informativos. Su contenido no se usa.</p>
<p>Las identidades con las afiliaciones que no se pudieron actualizar correctamente se conservan en la tabla tblPrincipalMeta y tienen otra posibilidad de actualizarse.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="principals-affiliations-nodes-scopes-and-roles"></a>Entidades de identidad, afiliaciones, nodos, ámbitos y roles


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Table</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipaltype.md">tblPrincipalType en Lync Server 2013</a></p></td>
<td><p>Contiene los tipos de entidad de tipo para categorizar lo que se encuentra en la tabla tblPrincipal. Esta tabla es estática. Se configura durante la creación de la base de datos y no cambia.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblprincipal.md">tblPrincipal en Lync Server 2013</a></p></td>
<td><p>Contiene todas las entidades de identidad (usuarios, carpetas, grupos, etc.). El servidor de chat persistente administra esto como una lista heterogénea plana. Varias columnas se basan en el tipo de cada entidad de tipo.</p>
<p>La mayoría de estas entidades son copias en caché de los objetos almacenados en Active Directory. La creación de la copia en caché en la tabla principal de estos objetos de Active Directory se denomina <em>aprovisionamiento</em>.</p>
<p>Algunas entidades de identidad se crean de forma más agresiva que otras, y algunos objetos de Active Directory se omiten por completo.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalaffiliations.md">tblPrincipalAffiliations en Lync Server 2013</a></p></td>
<td><p>Contiene las afiliaciones principales que describen las pertenencias a grupos de seguridad de Active Directory, contenedores de Active Directory, etc.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblnode.md">tblNode en Lync Server 2013</a></p></td>
<td><p>Contiene el nodo Category, tal como se administra en el panel de control de Lync Server.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblroletype.md">tblRoleType en Lync Server 2013</a></p></td>
<td><p>Contiene los tipos de funciones y sus conjuntos de permisos asociados. Esta tabla de búsqueda es estática.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblscopeprincipal.md">tblScopePrincipal en Lync Server 2013</a></p></td>
<td><p>Contiene ámbitos asignados a nodos.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalrole.md">tblPrincipalRole en Lync Server 2013</a></p></td>
<td><p>Contiene los roles asignados a los nodos.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblsiopwhitelist.md">tblSiopWhiteList en Lync Server 2013</a></p></td>
<td><p>Contiene los complementos registrados que se pueden asociar con nodos.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblenumattribute.md">tblEnumAttribute en Lync Server 2013</a></p></td>
<td><p>Contiene solo los atributos &quot;de&quot; visibilidad &quot;y&quot; comportamiento codificados que se usan en la tabla tblNode.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblenumvalue.md">tblEnumValue en Lync Server 2013</a></p></td>
<td><p>Contiene los valores de los atributos &quot;de comportamiento&quot; de visibilidad de contenido codificado "y" que se usan en la tabla tblNode.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="invites-chats-and-other-client-support"></a>Invitaciones, chats y otros tipos de compatibilidad con clientes


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Table</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalinvites.md">tblPrincipalInvites en Lync Server 2013</a></p></td>
<td><p>Contiene invitaciones para todos los usuarios aprovisionados del sistema para todos los nodos con la invitación automática habilitada.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblchat.md">tblChat en Lync Server 2013</a></p></td>
<td><p>Contiene todos los mensajes de chat.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tbllastinviteid.md">tblLastInviteId en Lync Server 2013</a></p></td>
<td><p>Contiene el último identificador de invitación generado (y utilizado en la tabla tblPrincipalInvites) para cada usuario.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tbllastchatid.md">tblLastChatId en Lync Server 2013</a></p></td>
<td><p>Contiene el último identificador de chat generado (y utilizado en la tabla tblChat) para cada usuario.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblpreference.md">tblPreference en Lync Server 2013</a></p></td>
<td><p>Contiene las preferencias del cliente de usuario (solo las usan los clientes heredados).</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblfiletoken.md">tblFileToken en Lync Server 2013</a></p></td>
<td><p>Contiene tokens temporales para propósitos de transferencia de archivos. Cada vez que se carga o descarga un archivo, el servicio de chat persistente genera un token que el cliente usa para obtener acceso al almacén de archivos del servicio Web.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="server-support"></a>Compatibilidad con servidores


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Table</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tblserveridentity.md">Tabla tblserveridentity en Lync Server 2013</a></p></td>
<td><p>Contiene los servidores activos en el grupo de servidores de chat persistente.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tbladminlock.md">tblAdminLock en Lync Server 2013</a></p></td>
<td><p>Contiene el bloqueo de administrador para ejecutar algunos comandos de administrador. La entrada de revisión del sistema en la tabla tblSystemRevision se incrementa después de cada versión del bloqueo.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblsystemrevision.md">tblSystemRevision en Lync Server 2013</a></p></td>
<td><p>Contiene la entrada del número de revisión usado (junto con la tabla tblAdminLock) para lograr la coherencia entre varios servidores.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblactivepeers.md">tblActivePeers en Lync Server 2013</a></p></td>
<td><p>Contiene las conexiones punto a punto actuales entre los servicios de chat persistente.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblconfig.md">tblConfig en Lync Server 2013</a></p></td>
<td><p>Contiene la configuración no admitida del servidor de chat persistente.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

