---
title: 'Lync Server 2013: permisos de implementación para SQL Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment permissions for SQL Server
ms:assetid: 56ea0c02-bcf5-4d45-aa13-570531c29074
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398375(v=OCS.15)
ms:contentKeyID: 48184197
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b38466bb3be6e03b8b434f4382b3b1d65cc05901
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038202"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-permissions-for-sql-server-in-lync-server-2013"></a>Permisos de implementación para SQL Server en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-01_

Microsoft SQL Server 2012 tiene requisitos específicos al instalar e implementar Lync Server 2013. Como Windows y SQL Server definen su seguridad de manera diferente, al iniciar sesión como administrador en el dominio de Active Directory no se conceden permisos implícitamente para SQL Server. También debe ser miembro de la entidad sysadmin del servidor basado en SQL Server que se está configurando:

<div>

## <a name="permissions-required-for-database-and-lync-server-installation"></a>Permisos necesarios para la instalación de Lync Server y base de datos

Las siguientes opciones detallan tres permisos y asociaciones de pertenencia a grupos para la instalación de archivos de Lync Server 2013 y bases de datos de SQL Server. Seleccione el escenario que mejor cumpla los requisitos de su organización.

### <a name="permissions-and-group-membership-associations"></a>Permisos y asociaciones de pertenencia a grupo

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Rol de SQL Server o Lync Server 2013</th>
<th>Pertenencia a grupo y permisos de SQL Server típicos del rol</th>
<th>Función: permisos típicos de Lync Server 2013 y pertenencia a grupos</th>
<th>Resultado de permisos</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Administrador de Lync Server 2013</p></td>
<td><p>Debe haber obtenido la pertenencia al grupo de seguridad de SQL Server sysadmins y ser miembro del grupo de administradores local de SQL Server</p></td>
<td><p>Debe ser miembro del grupo RTCUniversalServerAdmins.</p></td>
<td><p>Lync Server 2013 el administrador tiene los permisos adecuados para instalar las bases de datos de Lync Server 2013 y SQL Server.</p></td>
</tr>
<tr class="even">
<td><p>Administrador de SQL Server</p></td>
<td><p>Miembro del grupo sysadmin de SQL Server (o equivalente) y miembro del grupo de administradores local de SQL Server</p></td>
<td><p>Debe ser miembro del grupo RTCUniversalServerReadOnly</p></td>
<td><p>El administrador de SQL Server tiene los permisos adecuados para instalar las bases de datos de Lync Server 2013 y SQL Server.</p></td>
</tr>
<tr class="odd">
<td><p>Ambos administradores comparten tareas de instalación</p></td>
<td><p>Un administrador de SQL Server es miembro del grupo sysadmins (o equivalente) y miembro del grupo de administradores local de SQL Server</p></td>
<td><p>El administrador de Lync Server 2013 es miembro de RTCUniversalServerAdmins</p></td>
<td><p>El administrador de Lync Server 2013 puede instalar Lync Server 2013, pero no puede instalar las bases de datos. El administrador de SQL Server usa el shell de administración de Lync Server y los cmdlets de Windows PowerShell proporcionados por el administrador de Lync Server 2013 para instalar las bases de datos. El shell de administración de Lync Server 2013 que usa el administrador de SQL Server está instalado en el servidor front-end. Esto elimina la necesidad de instalar las herramientas administrativas de Lync Server 2013 en el servidor basado en SQL Server.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

