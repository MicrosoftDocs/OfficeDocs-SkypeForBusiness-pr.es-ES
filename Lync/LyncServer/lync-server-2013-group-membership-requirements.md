---
title: 'Lync Server 2013: Requisitos para la pertenencia a grupos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Group membership requirements
ms:assetid: 01876843-8717-4e72-baf5-866ac8cceee6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204623(v=OCS.15)
ms:contentKeyID: 48183239
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44ad8c7f6eab93f3bdcd7b73d4ae05bd3b2e25ad
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743350"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="group-membership-requirements-for-lync-server-2013"></a>Requisitos para la pertenencia a grupos en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-05_

En la tabla siguiente se resume el grupo o los grupos a los que debe pertenecer una persona para poder instalar, administrar y solucionar problemas de Lync Server 2013.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Ejecutable 2013 de Lync Server</th>
<th>Se requiere pertenencia al grupo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Setup. exe</strong> : ejecutable que inicia la instalación de las herramientas administrativas 2013 de Lync Server.</p></td>
<td><p>Miembro del grupo de administradores locales en el equipo desde el que se ejecuta el ejecutable. Miembro del grupo usuarios del dominio para leer la información de los servicios de dominio de Active Directory. Este nivel de permisos es necesario porque la instalación automática de paquetes MSI necesarios en el equipo local requiere privilegios que permitan leer y escribir en recursos de equipos locales protegidos, como directorios de archivos de programa y proteger registro como, por ejemplo, el subárbol del equipo local.</p>
<div>

> [!TIP]  
> También puede delegar permisos de configuración a los usuarios o grupos a los que no desee conceder la pertenencia al grupo administradores de dominio. Para obtener más información, vea <A href="lync-server-2013-granting-setup-permissions.md">conceder permisos de configuración en Lync Server 2013</A> en la documentación de implementación.


</div></td>
</tr>
<tr class="even">
<td><p><strong>Deploy</strong> . exe: el programa Setup. exe, que llama a setup. exe, es responsable de la implementación de los componentes de software para los roles de servidor.</p></td>
<td><p>Miembro del grupo de administradores locales en el equipo desde el que se ejecuta el ejecutable. Miembro del grupo usuarios del dominio para leer la información de AD DS. Este nivel de permisos es necesario porque la instalación automática de paquetes MSI necesarios en el equipo local requiere privilegios que permitan leer y escribir en recursos de equipos locales protegidos, como directorios de archivos de programa y proteger registro como, por ejemplo, el subárbol del equipo local. Es necesario pertenecer al grupo RtcUniversalReadOnlyAdmins para leer el almacén de administración central.</p>
<div>

> [!NOTE]  
> Si está ejecutando el sistema operativo Windows Vista o Windows 7, el control de cuentas de usuario (UAC) le pedirá que continúe con la instalación. Si ha iniciado sesión con una cuenta de usuario estándar, necesitará una persona que sea miembro del grupo de administradores locales para proporcionar credenciales cuando se le pida una cuenta con permisos para instalar el software.


</div></td>
</tr>
<tr class="odd">
<td><p><strong>Bootstrapper. exe</strong> : llamado por Setup. exe, Bootstrapper. exe es responsable de la implementación y la configuración de los roles de servidor.</p></td>
<td><p>Miembro del grupo de administradores locales en el equipo desde el que se ejecuta el ejecutable. Miembro del grupo RTCUniversalServerAdmins para ejecutar Bootstrapper. exe. Miembro del grupo usuarios del dominio para leer la información de AD DS. Este nivel de permisos es necesario porque la instalación automática de paquetes MSI necesarios en el equipo local requiere privilegios que permitan leer y escribir en recursos de equipos locales protegidos, como directorios de archivos de programa y proteger registro como, por ejemplo, el subárbol del equipo local.</p></td>
</tr>
<tr class="even">
<td><p><strong>TopologyBuilder</strong> : interfaz de usuario guiada por asistente para crear, ver, ajustar y validar topologías de Lync Server 2013.</p></td>
<td><p>Miembro del grupo de administradores locales en el equipo desde el que se ejecuta el ejecutable para ver la topología. Miembro del grupo RTCUniversalServerAdmins para cambiar los valores de configuración. Miembro del grupo RTCUniversalServerAdmins y del grupo administradores de dominio, o miembro del grupo RTCUniversalServerAdmins (solo si se le han otorgado permisos de configuración de delegado), para publicar la topología. Para obtener más información sobre cómo delegar permisos de configuración para permitir que los miembros del grupo RTCUniversalServerAdmins publiquen la topología sin ser miembros del grupo administradores de dominio, vea <a href="lync-server-2013-granting-setup-permissions.md">conceder permisos de configuración en Lync Server 2013</a> en la documentación de implementación.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AdminUIHost</strong> : interfaz gráfica de usuario basada en web para administrar Lync Server 2013.</p></td>
<td><p>Miembro de CsAdministrator grupo o miembro de otra función de control de acceso basado en roles (RBAC) a la que se asigna la tarea administrativa específica. El panel de control 2013 de Lync Server implementa los cambios de configuración ejecutando los cmdlets del shell de administración de Lync Server 2013. Para obtener una lista de los roles predefinidos y permitir la ejecución de los miembros de cmdlets, consulte <a href="lync-server-2013-planning-for-role-based-access-control.md">planificación de control de acceso basado en roles en Lync Server 2013</a> en la documentación de planificación.</p></td>
</tr>
<tr class="even">
<td><p><strong>PowerShell. exe con el módulo de Lync Server 2013 cargado</strong> : herramienta administrativa de línea de comandos con cmdlets específicos para la administración de Lync Server 2013.</p></td>
<td><p>Miembro de CsAdministrator grupo o miembro de otro rol RBAC al que se ha asignado el cmdlet específico. Para obtener una lista de los roles predefinidos y permitir la ejecución de los miembros de cmdlets, consulte <a href="lync-server-2013-planning-for-role-based-access-control.md">planificación de control de acceso basado en roles en Lync Server 2013</a> en la documentación de planificación.</p>
<p>O miembro de uno o más de los siguientes grupos, según el cmdlet:</p>
<ul>
<li><p>RTCUniversalServerAdmins</p></li>
<li><p>RTCUniversalUserAdmins</p></li>
<li><p>RTCUniversalReadOnlyAdmins</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

