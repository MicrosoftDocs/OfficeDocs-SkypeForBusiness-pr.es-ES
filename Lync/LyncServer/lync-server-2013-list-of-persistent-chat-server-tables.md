---
title: 'Lync Server 2013: Lista de tablas de servidores de chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: List of Persistent Chat Server tables
ms:assetid: 26c9e271-3516-4d90-b930-70fec4e359ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558628(v=OCS.15)
ms:contentKeyID: 48183659
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d5c16160d51373fe1eef5b7cbaefe728b904545
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834942"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-persistent-chat-server-tables-in-lync-server-2013"></a>Lista de tablas de servidores de chat persistente en Lync Server 2013

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
<th>Tabla</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tbladcookie.md">tblADCookie en Lync Server 2013</a></p></td>
<td><p>Contiene las cookies de sincronización del Protocolo ligero de acceso a directorios (LDAP). Cada fila corresponde a un dominio de servicios de dominio de Active Directory en el que el servidor de chat persistente está supervisando activamente los cambios. (En esta tabla solo se representan los dominios de Active Directory pertinentes para el servidor de chat persistente).</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblprincipalmemberdifference.md">tblPrincipalMemberDifference en Lync Server 2013</a></p></td>
<td><p>Contiene cambios en la pertenencia a grupos (miembros agregados y eliminados) que aún no han sido procesados por los pasos de sincronización de Active Directory más recientes y es una de las tablas temporales (junto con la tabla tblADUpdates) que se usa en el primer paso de la sincronización de Active Directory.</p>
<p>Los cambios de pertenencia se almacenan, se procesan o ambos, solo para los grupos que se muestran en la tabla tblPrincipal o que ya tienen miembros.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tbladupdates.md">tblADUpdates en Lync Server 2013</a></p></td>
<td><p>Contiene cambios en los servicios de dominio de Active Directory que aún no han sido procesados por los pasos de sincronización de Active Directory más recientes y es una de las tablas temporales (junto con la tabla tblPrincipalMemberDifference) que se usa en el primer paso de Active Directory. Sync.</p>
<p>Los cambios en Active Directory se almacenan, se procesan o ambos solo para los principales que ya aparecen en la tabla tblPrincipal.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblprincipalmembers.md">tblPrincipalMembers en Lync Server 2013</a></p></td>
<td><p>Contiene pertenencias principales.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalmeta.md">tblPrincipalMeta en Lync Server 2013</a></p></td>
<td><p>Contiene las entidades de identidad que deben actualizarse desde Active Directory.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblskippedaffiliations.md">tblSkippedAffiliations en Lync Server 2013</a></p></td>
<td><p>Contiene afiliaciones que no se pudieron actualizar por alguna razón, generalmente debido a errores de acceso a Active Directory.</p>
<p>Esta tabla es solo para fines informativos. No se utiliza su contenido.</p>
<p>Las principales de las afiliaciones que no se hayan actualizado correctamente se guardan en la tabla tblPrincipalMeta y se les da otra oportunidad para que se actualicen.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="principals-affiliations-nodes-scopes-and-roles"></a>Principales, afiliaciones, nodos, ámbitos y roles


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Tabla</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipaltype.md">tblPrincipalType en Lync Server 2013</a></p></td>
<td><p>Contiene tipos de principal para categorizar lo que hay en la tabla tblPrincipal. Esta tabla es estática. Se configura durante la creación de la base de datos y no cambia.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblprincipal.md">tblPrincipal enn Lync Server 2013</a></p></td>
<td><p>Contiene todos los principales (usuarios, carpetas, grupos, etc.). El servidor de chat persistente gestiona esto como una lista heterogénea plana. Varias columnas se basan en el tipo de cada principal.</p>
<p>La mayoría de estos principios son copias almacenadas en caché de los objetos almacenados en Active Directory. La creación de la copia en caché en la tabla principal de estos objetos de Active Directory se denomina <em>suministro</em>.</p>
<p>Algunas entidades de identidad se crean de forma más agresiva que otras, y algunos objetos de Active Directory se pasan por alto.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalaffiliations.md">tblPrincipalAffiliations en Lync Server 2013</a></p></td>
<td><p>Contiene las afiliaciones principales que describen las pertenencias a grupos de seguridad de Active Directory, contenedores de Active Directory, etc.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblnode.md">tblNode en Lync Server 2013</a></p></td>
<td><p>Contiene el nodo de categoría, administrado en el panel de control de Lync Server.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblroletype.md">tblRoleType en Lync Server 2013</a></p></td>
<td><p>Contiene tipos de roles y sus conjuntos de permisos asociados. Esta tabla de búsqueda es estática.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblscopeprincipal.md">tblScopePrincipal en Lync Server 2013</a></p></td>
<td><p>Contiene ámbitos asignados a los nodos.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalrole.md">tblPrincipalRole en Lync Server 2013</a></p></td>
<td><p>Contiene roles asignados a nodos.</p></td>
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
<td><p>Contiene los valores de los atributos &quot;de comportamiento&quot; de visibilidad "y" que se usan en la tabla tblNode.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="invites-chats-and-other-client-support"></a>Invitaciones, chats y otros tipos de asistencia al cliente


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Tabla</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalinvites.md">tblPrincipalInvites en Lync Server 2013</a></p></td>
<td><p>Contiene invitaciones para todos los usuarios aprovisionados del sistema en todos los nodos con la opción de invitación automática habilitada.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblchat.md">tblChat en Lync Server 2013</a></p></td>
<td><p>Contiene todos los mensajes instantáneos.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tbllastinviteid.md">tblLastInviteId en Lync Server 2013</a></p></td>
<td><p>Contiene el identificador de la última invitación que se generó (y se usó en la tabla tblPrincipalInvites) para cada usuario.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tbllastchatid.md">tblLastChatId en Lync Server 2013</a></p></td>
<td><p>Contiene el último identificador de chat generado (y usado en la tabla tblChat) para cada usuario.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblpreference.md">tblPreference en Lync Server 2013</a></p></td>
<td><p>Contiene preferencias de clientes de usuario (solo utilizadas por clientes heredados).</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblfiletoken.md">tblFileToken en Lync Server 2013</a></p></td>
<td><p>Contiene tokens temporales para la transferencia de archivos. Cada vez que se carga o descarga un archivo, el servicio de chat persistente genera un token que el cliente usa para acceder al almacén de archivos del servicio Web.</p></td>
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
<th>Tabla</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tblserveridentity.md">tblServerIdentity en Lync Server 2013</a></p></td>
<td><p>Contiene los servidores activos del grupo de servidores de chat persistente.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tbladminlock.md">tblAdminLock en Lync Server 2013</a></p></td>
<td><p>Contiene el bloqueo de administrador para ejecutar algunos comandos de administrador. La entrada de revisión del sistema de la tabla tblSystemRevision se incrementa después de cada lanzamiento de bloqueo.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblsystemrevision.md">tblSystemRevision en Lync Server 2013</a></p></td>
<td><p>Contiene la entrada del número de revisión usado (junto con la tabla tblAdminLock) para lograr la coherencia entre varios servidores.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblactivepeers.md">tblActivePeers en Lync Server 2013</a></p></td>
<td><p>Contiene conexiones de punto a punto actuales entre servicios de chat persistente.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblconfig.md">tblConfig en Lync Server 2013</a></p></td>
<td><p>Contiene la configuración no compatible del servidor de chat persistente.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

