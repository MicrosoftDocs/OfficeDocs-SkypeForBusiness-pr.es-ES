---
title: 'Lync Server 2013: requisitos de pertenencia a grupos'
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
ms.openlocfilehash: 93c1a79d39a70c21e353799a43c76599cc7af2b5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140303"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="group-membership-requirements-for-lync-server-2013"></a>Requisitos de pertenencia a grupo para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-05_

La siguiente tabla resume el grupo o los grupos a los que debe pertenecer una persona para instalar, administrar y solucionar correctamente Lync Server 2013.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Lync Server 2013 ejecutable</th>
<th>Pertenencia a grupos necesaria</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Setup. exe</strong> : ejecutable que inicia la instalación de las herramientas administrativas de Lync Server 2013.</p></td>
<td><p>Miembro del grupo Administradores locales en el equipo desde el que se ejecuta el ejecutable. Miembro del grupo usuarios del dominio para leer la información de los servicios de dominio de Active Directory. Este nivel de permiso es necesario porque la instalación automática de los paquetes MSI necesarios en el equipo local requiere privilegios que permitan la lectura de los recursos de equipos locales protegidos y la escritura en estos, como directorios Archivos de programa, y un registro protegido como el subárbol Local Machine.</p>
<div>

> [!TIP]  
> También puede delegar permisos de configuración a usuarios o grupos a los que no desee conceder pertenencia en el grupo administradores del dominio. Para obtener más información, consulte <A href="lync-server-2013-granting-setup-permissions.md">concediendo Setup Permissions in Lync Server 2013</A> en la documentación sobre implementación.


</div></td>
</tr>
<tr class="even">
<td><p><strong>Deploy.exe</strong>: llamado por setup.exe, deploy.exe realiza la implementación de los componentes del software para los roles del servidor.</p></td>
<td><p>Miembro del grupo Administradores locales en el equipo desde el que se ejecuta el ejecutable. Miembro del grupo Usuarios de dominio para leer la información en los AD DS. Este nivel de permiso es necesario porque la instalación automática de los paquetes MSI necesarios en el equipo local requiere privilegios que permitan la lectura de los recursos de equipos locales protegidos y la escritura en estos, como directorios Archivos de programa, y un registro protegido como el subárbol Local Machine. Es necesario pertenecer al grupo RtcUniversalReadOnlyAdmins para leer el almacén de administración central.</p>
<div>

> [!NOTE]  
> Si ejecuta el sistema operativo Windows Vista o Windows 7, el control de cuentas de usuario (UAC) le pedirá que continúe con la instalación. Si ha iniciado sesión con una cuenta de usuario estándar, necesitará que alguien que sea miembro del grupo Administradores locales le proporcione las credenciales cuando se le solicite una cuenta con permisos para instalar el software.


</div></td>
</tr>
<tr class="odd">
<td><p><strong>Bootstrapper.exe</strong>: llamado por setup.exe, bootstrapper.exe realiza la implementación y la configuración de los roles del servidor.</p></td>
<td><p>Miembro del grupo Administradores locales en el equipo desde el que se ejecuta el ejecutable. Miembro del grupo RTCUniversalServerAdmins con permiso para ejecutar el archivo Bootstrapper.exe. Miembro del grupo Usuarios de dominio para leer la información en los AD DS. Este nivel de permiso es necesario porque la instalación automática de los paquetes MSI necesarios en el equipo local requiere privilegios que permitan la lectura de los recursos de equipos locales protegidos y la escritura en estos, como directorios Archivos de programa, y un registro protegido como el subárbol Local Machine.</p></td>
</tr>
<tr class="even">
<td><p><strong>TopologyBuilder</strong> : interfaz de usuario guiada por asistente para crear, ver, ajustar y validar topologías de Lync Server 2013.</p></td>
<td><p>Miembro del grupo de administradores locales en el equipo desde el que se ejecuta el archivo ejecutable para ver la topología. Miembro del grupo RTCUniversalServerAdmins para cambiar los valores de configuración. Miembro del grupo RTCUniversalServerAdmins y el grupo administradores de dominio, o miembro del grupo RTCUniversalServerAdmins (solo si se han concedido al grupo permisos para delegar la instalación), para publicar la topología. Para obtener más información sobre cómo delegar permisos de instalación para permitir que los miembros del grupo RTCUniversalServerAdmins publiquen la topología sin ser miembros del grupo administradores de dominio, consulte <a href="lync-server-2013-granting-setup-permissions.md">concediendo Setup Permissions in Lync Server 2013</a> en la documentación sobre implementación.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AdminUIHost</strong> – interfaz gráfica de usuario basada en web para la administración de Lync Server 2013.</p></td>
<td><p>Miembro del grupo CsAdministrator o miembro de otra función de control de acceso basado en roles (RBAC) donde se asigna la tarea administrativa específica. Lync Server 2013 el panel de control implementa los cambios de configuración mediante la ejecución de los cmdlets del shell de administración de Lync Server 2013. Para obtener una lista de las funciones predefinidas y permitir que se ejecuten los miembros de cmdlets, consulte <a href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</a> en la documentación referente a la planeación.</p></td>
</tr>
<tr class="even">
<td><p><strong>PowerShell. exe con el módulo Lync Server 2013 cargado</strong> : herramienta administrativa de línea de comandos con cmdlets específicos para la administración de Lync Server 2013.</p></td>
<td><p>Miembro del grupo CsAdministrator o miembro de otra función de RBAC donde se asignó el cmdlet específico. Para obtener una lista de las funciones predefinidas y permitir que se ejecuten los miembros de cmdlets, consulte <a href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</a> en la documentación referente a la planeación.</p>
<p>O bien, miembro de uno o más de los siguientes grupos, según el cmdlet:</p>
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

