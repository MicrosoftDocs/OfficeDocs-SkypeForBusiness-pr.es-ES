---
title: 'Lync Server 2013: Permisos de implementación para SQL Server'
TOCTitle: Permisos de implementación para SQL Server
ms:assetid: 56ea0c02-bcf5-4d45-aa13-570531c29074
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398375(v=OCS.15)
ms:contentKeyID: 48275299
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Permisos de implementación para SQL Server en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

Microsoft SQL Server 2012 tiene requisitos específicos para la instalación e implementación de Lync Server 2013. Como Windows y SQL Server definen su seguridad de diferente manera, el inicio de sesión como administrador en el dominio de Active Directory no concede permisos de forma implícita para SQL Server. También debe ser miembro de la entidad sysadmin del servidor basado en SQL Server que se está configurando:

## Permisos necesarios para la instalación de Lync Server y base de datos

Las opciones que se muestran a continuación detallan los tres permisos y las asociaciones de pertenencia a grupo para la instalación de archivos de Lync Server 2013 y bases de datos de SQL Server. Seleccione el escenario que mejor cumpla los requisitos de su organización.

### Permisos y asociaciones de pertenencia a grupo

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>SQL Server o rol de Lync Server 2013</th>
<th>Pertenencia a grupo y permisos de SQL Server típicos del rol</th>
<th>Pertenencia a grupo y permisos de Lync Server 2013 típicos del rol</th>
<th>Resultado de permisos</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Administrador de Lync Server 2013</p></td>
<td><p>Debe haber obtenido la pertenencia al grupo de seguridad de SQL Server sysadmins y ser miembro del grupo de administradores local de SQL Server</p></td>
<td><p>Debe ser miembro del grupo RTCUniversalServerAdmins.</p></td>
<td><p>El administrador de Lync Server 2013 dispone de los permisos adecuados para instalar bases de datos de SQL Server y Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p>Administrador de SQL Server</p></td>
<td><p>Miembro del grupo sysadmin de SQL Server (o equivalente) y miembro del grupo de administradores local de SQL Server</p></td>
<td><p>Debe ser miembro del grupo RTCUniversalServerReadOnly</p></td>
<td><p>El administrador de SQL Server dispone de los permisos adecuados para instalar bases de datos de SQL Server y Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p>Ambos administradores comparten tareas de instalación</p></td>
<td><p>Un administrador de SQL Server es miembro del grupo sysadmins (o equivalente) y miembro del grupo de administradores local de SQL Server</p></td>
<td><p>Un administrador de Lync Server 2013 es miembro de RTCUniversalServerAdmins</p></td>
<td><p>El administrador de Lync Server 2013 puede instalar Lync Server 2013, pero no puede instalar las bases de datos. El administrador de SQL Server usa los cmdlets del Shell de administración de Lync Server y Windows PowerShell proporcionados por el administrador de Lync Server 2013 para instalar las bases de datos. El Shell de administración de Lync Server 2013 que usa el administrador de SQL Server se instala en el Servidor front-end. Esto elimina la necesidad de instalar herramientas administrativas de Lync Server 2013 en el servidor basado en SQL Server.</p></td>
</tr>
</tbody>
</table>

