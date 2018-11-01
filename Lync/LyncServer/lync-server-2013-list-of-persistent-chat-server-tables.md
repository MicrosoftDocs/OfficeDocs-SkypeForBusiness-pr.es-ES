---
title: 'Lync Server 2013: Lista de tablas de servidores de chat persistente'
TOCTitle: Lista de tablas de servidores de chat persistente
ms:assetid: 26c9e271-3516-4d90-b930-70fec4e359ea
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg558628(v=OCS.15)
ms:contentKeyID: 48274715
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lista de tablas de servidores de chat persistente en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

El esquema de la base de datos del Chat persistente incluye las siguientes tablas.

## Sincronización de Active Directory


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
<td><p>Contiene las cookies actuales de sincronización del Protocolo ligero de acceso a directorios (LDAP). Cada fila representa un dominio de los Servicios de dominio de Active Directory que Servidor de chat persistente supervisa de manera activa en busca de cambios. (Solamente se representan en esta tabla los dominios de Active Directory que son relevantes para Servidor de chat persistente).</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblprincipalmemberdifference.md">tblPrincipalMemberDifference en Lync Server 2013</a></p></td>
<td><p>Contiene cambios en la pertenencia a grupos (tanto de los miembros que se agregaron como los que se quitaron) que aún no se procesaron en los pasos de sincronización de Active Directory posteriores y es una de las tablas temporales (junto con la tabla tblADUpdates) que se usa en el primer paso de la sincronización de Active Directory.</p>
<p>Los cambios en la pertenencia se almacenan, se procesan, o se almacenan y procesan, únicamente para los grupos enumerados en la tabla tblPrincipal o que ya tienen miembros enumerados ahí.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tbladupdates.md">tblADUpdates en Lync Server 2013</a></p></td>
<td><p>Contiene cambios en Servicios de dominio de Active Directory que aún no se procesaron en los pasos de sincronización de Active Directory posteriores y es una de las tablas temporales (junto con la tabla tblPrincipalMemberDifference) que se usan en el primer paso de la sincronización de Active Directory.</p>
<p>Los cambios en Active Directory se almacenan, se procesan, o se almacenan y procesan, únicamente para las entidades de seguridad enumeradas en la tabla tblPrincipal.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblprincipalmembers.md">tblPrincipalMembers en Lync Server 2013</a></p></td>
<td><p>Contiene las pertenencias de entidades de seguridad.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalmeta.md">tblPrincipalMeta en Lync Server 2013</a></p></td>
<td><p>Contiene las entidades de seguridad que se deben actualizar desde Active Directory.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblskippedaffiliations.md">tblSkippedAffiliations en Lync Server 2013</a></p></td>
<td><p>Contiene las afiliaciones que no se pudieron actualizar por algún motivo, generalmente debido a errores de acceso de Active Directory.</p>
<p>Esta tabla es solo de carácter informativo. Su contenido no se utiliza.</p>
<p>Las entidades de seguridad con afiliaciones que no se pudieron actualizar correctamente se conservan en la tabla tblPrincipalMeta y tienen otra oportunidad para actualizarse.</p></td>
</tr>
</tbody>
</table>


## Entidades de seguridad, afiliaciones, nodos, ámbitos y roles


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
<td><p>Contiene tipos de entidades principales para clasificar el contenido de la tabla tblPrincipal. Esta tabla es estática. Se configura durante la creación de la base de datos y no se modifica.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblprincipal.md">tblPrincipal enn Lync Server 2013</a></p></td>
<td><p>Contiene todas las entidades principales (usuarios, carpetas, grupos, etc.). El Servidor de chat persistente las administra como una lista heterogénea plana. Existen varias columnas que se basan en el tipo de cada entidad de seguridad.</p>
<p>La mayoría de estas entidades de seguridad son copias en caché de objetos almacenados en Active Directory. La creación de la copia en caché de estos objetos de Active Directory en la tabla Principal se conoce como <em>aprovisionamiento</em> .</p>
<p>Algunas entidades principales se crean de manera más enérgica que otras, y algunos objetos de Active Directory se omiten por completo.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalaffiliations.md">tblPrincipalAffiliations en Lync Server 2013</a></p></td>
<td><p>Contiene las afiliaciones de entidades de seguridad que describen pertenencias en los grupos de seguridad de Active Directory, los contenedores de Active Directory, etc.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblnode.md">tblNode en Lync Server 2013</a></p></td>
<td><p>Contiene el nodo de categoría), según se administra en Panel de control de Lync Server.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblroletype.md">tblRoleType en Lync Server 2013</a></p></td>
<td><p>Contiene los tipos de rol y sus conjuntos de permisos asociados. Esta tabla de búsqueda es estática.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblscopeprincipal.md">tblScopePrincipal en Lync Server 2013</a></p></td>
<td><p>Contiene los ámbitos asignados a nodos.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalrole.md">tblPrincipalRole en Lync Server 2013</a></p></td>
<td><p>Contiene roles asignados a nodos.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblsiopwhitelist.md">tblSiopWhiteList en Lync Server 2013</a></p></td>
<td><p>Contiene los complementos registrados que es posible asociar con nodos.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblenumattribute.md">tblEnumAttribute en Lync Server 2013</a></p></td>
<td><p>Contiene solamente los atributos “Visibility” y “Behavior” codificados de forma rígida que se utilizan en la tabla tblNode.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblenumvalue.md">tblEnumValue en Lync Server 2013</a></p></td>
<td><p>Contiene los valores de los atributos “Visibility” y “Behavior” codificados de forma rígida que se utilizan en la tabla tblNode.</p></td>
</tr>
</tbody>
</table>


## Invitaciones, chats y compatibilidad con clientes adicional


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
<td><p>Contiene invitaciones para todos los usuarios aprovisionados del sistema, para todos los nodos con la función de invitación automática habilitada.</p></td>
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
<td><p>Contienen las preferencias de cliente del usuario (usadas únicamente por los clientes heredados).</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblfiletoken.md">tblFileToken en Lync Server 2013</a></p></td>
<td><p>Contiene tokens temporales para la transferencia de archivos. Cada vez que se carga o se descarga un archivo, el servicio de Chat persistente genera un token que el cliente utiliza para acceder al almacén de archivos del servicio web.</p></td>
</tr>
</tbody>
</table>


## Compatibilidad con servidores


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
<td><p>Contiene los servidores activos en el Grupo de servidores de chat persistente.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tbladminlock.md">tblAdminLock en Lync Server 2013</a></p></td>
<td><p>Contiene el bloqueo del administrador para ejecutar algunos comandos. La entrada de revisión del sistema de la tabla tblSystemRevision se incrementa con cada desbloqueo.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblsystemrevision.md">tblSystemRevision en Lync Server 2013</a></p></td>
<td><p>Contiene la entrada de número de revisión utilizada (junto con la tabla tblAdminLock) para mantener la coherencia entre varios servidores.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblactivepeers.md">tblActivePeers en Lync Server 2013</a></p></td>
<td><p>Contiene las conexiones punto a punto actuales entre los servicios de Chat persistente.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblconfig.md">tblConfig en Lync Server 2013</a></p></td>
<td><p>Contiene la configuración de no admitida de Servidor de chat persistente.</p></td>
</tr>
</tbody>
</table>

