---
title: Cuentas de usuario habilitadas para Lync Server 2013
TOCTitle: Cuentas de usuario habilitadas para Lync Server 2013
ms:assetid: 8021087e-5084-4a39-9fef-ab9376c6d371
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg182543(v=OCS.15)
ms:contentKeyID: 48275828
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Cuentas de usuario habilitadas para Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

Los temas de esta sección ofrecen procedimientos paso a paso para configurar las opciones de usuario que puede realizar a través de la página con el Panel de control de Lync Server 2013.

> [!IMPORTANT]  
> No puede usar Panel de control de Lync Server para administrar usuarios que son miembros del grupo Administradores de dominio de Active Directory. Para los usuarios Administradores de dominio, puede usar Panel de control de Lync Server solamente para realizar operaciones de búsqueda de solo lectura. Para efectuar operaciones de escritura en usuarios de Administradores de dominio (por ejemplo, habilitar o deshabilitar para Panel de control de Lync Server, cambiar asignaciones de grupo o directiva, configuración de telefonía, dirección SIP), es preciso que use los cmdlets de Windows PowerShell mientras esté registrado como usuario Administrador de dominio. Para obtener detalles sobre cómo usar los cmdlets de Windows PowerShell con el fin de administrar usuarios, consulte <a href="lync-server-2013-lync-server-management-shell.md">Shell de administración de Lync Server</a>.



Al realizar cualquier tarea administrativa de Lync Server 2013 que conlleve buscar un usuario o filtrar los resultados de búsqueda de usuario, hay una serie de propiedades de usuario que son atributos en Servicios de dominio de Active Directory, pero que no se replican en el catálogo global hasta que se implemente Microsoft Exchange Server. Microsoft Exchange (no Lync Server) marca los siguientes atributos para que se repliquen en el catálogo global cuando se instale:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Información del usuario</th>
<th>Dirección y teléfono</th>
<th>Organización</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Iniciales</p></td>
<td><p>Dirección</p>
<p>País o región</p>
<p>Buscapersonas</p>
<p>Fax</p>
<p>Móvil</p></td>
<td><p>Título</p>
<p>Compañía</p>
<p>Departamento</p>
<p>Office</p></td>
</tr>
</tbody>
</table>


## En esta sección

  - [Ver información sobre las cuentas de usuario habilitadas para Lync Server 2013](lync-server-2013-viewing-information-about-user-accounts-enabled-for-lync-server.md)

  - [Habilitar y deshabilitar usuarios para Lync Server 2013](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)

  - [Administración de Enterprise Voice para usuarios](lync-server-2013-managing-enterprise-voice-for-users.md)

  - [Modificación de las propiedades de cuentas de usuario](lync-server-2013-modifying-user-account-properties.md)

  - [Administrar la directiva de acceso de la organización en Lync Server 2013](lync-server-2013-manage-external-access-policy-for-your-organization.md)

  - [Asignación de directivas por usuario](lync-server-2013-assigning-per-user-policies.md)

## Vea también

#### Conceptos

[Cmdlets de administración de usuarios](lync-server-2013-user-management-cmdlets.md)  

#### Otros recursos

[Administración de usuarios en Lync Server 2013](lync-server-2013-managing-users-in-lync-server.md)

