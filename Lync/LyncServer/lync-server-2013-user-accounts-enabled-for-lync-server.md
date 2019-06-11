---
title: 'Lync Server 2013: cuentas de usuario habilitadas para Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: User accounts enabled for Lync Server 2013
ms:assetid: 8021087e-5084-4a39-9fef-ab9376c6d371
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182543(v=OCS.15)
ms:contentKeyID: 48184651
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5b7a8935e83b79cfac1c4d3283fe0011a72aa3ba
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850268"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-accounts-enabled-for-lync-server-2013"></a>Cuentas de usuario habilitadas para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-04-18_

Los temas de esta sección proporcionan procedimientos paso a paso para configurar las opciones de usuario que puede realizar con el panel de control de Lync Server 2013.

<div>


> [!IMPORTANT]  
> No puede usar el panel de control de Lync Server para administrar los usuarios que son miembros del grupo administradores de dominio de Active Directory. Para los usuarios de administradores de dominio, puede usar el panel de control de Lync Server solo para realizar operaciones de búsqueda de solo lectura. Para realizar operaciones de escritura en los usuarios de administradores de dominio (por ejemplo, habilitar o deshabilitar el panel de control de Lync Server, cambiar las asignaciones de directivas, la configuración de telefonía, la dirección SIP), debe usar los cmdlets de Windows PowerShell al iniciar sesión como un usuario administrador de dominio. Para obtener más información sobre cómo usar los cmdlets de Windows PowerShell para administrar usuarios, consulte <A href="lync-server-2013-lync-server-management-shell.md">consola de administración de Lync Server 2013</A>.



</div>

Al realizar cualquier tarea administrativa de Lync Server 2013 que implique buscar un usuario o filtrar los resultados de la búsqueda de usuarios, hay algunas propiedades de usuario que existen como atributos en los servicios de dominio de Active Directory, pero que no se replican en el catálogo global hasta que se implemente Microsoft Exchange Server. Microsoft Exchange, no Lync Server, marca los siguientes atributos para la replicación en el catálogo global cuando está instalado:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Información de usuario</th>
<th>Dirección y teléfono</th>
<th>Organización</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Iniciales</p></td>
<td><p>Dirección</p>
<p>País o región</p>
<p>Localizador</p>
<p>Fax</p>
<p>Móvil</p></td>
<td><p>Título</p>
<p>Compañía</p>
<p>Grandes</p>
<p>Office</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a>En esta sección

  - [Ver información sobre las cuentas de usuario habilitadas para Lync Server 2013](lync-server-2013-viewing-information-about-user-accounts-enabled-for-lync-server.md)

  - [Habilitar y deshabilitar usuarios para Lync Server 2013](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)

  - [Administración de telefonía IP empresarial para usuarios en Lync Server 2013](lync-server-2013-managing-enterprise-voice-for-users.md)

  - [Modificar las propiedades de la cuenta de usuario en Lync Server 2013](lync-server-2013-modifying-user-account-properties.md)

  - [Administrar la directiva de acceso de la organización en Lync Server 2013](lync-server-2013-manage-external-access-policy-for-your-organization.md)

  - [Asignación de directivas por usuario en Lync Server 2013](lync-server-2013-assigning-per-user-policies.md)

</div>

<div>

## <a name="see-also"></a>Vea también


[Cmdlets de administración de usuarios en Lync Server 2013](lync-server-2013-user-management-cmdlets.md)  


[Administración de usuarios en Lync Server 2013](lync-server-2013-managing-users-in-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

