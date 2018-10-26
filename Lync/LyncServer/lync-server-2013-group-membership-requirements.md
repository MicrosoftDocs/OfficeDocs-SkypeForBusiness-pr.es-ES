---
title: 'Lync Server 2013: Requisitos para la pertenencia a grupos'
TOCTitle: Requisitos para la pertenencia a grupos
ms:assetid: 01876843-8717-4e72-baf5-866ac8cceee6
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204623(v=OCS.15)
ms:contentKeyID: 48274234
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Requisitos para la pertenencia a grupos en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

En la siguiente tabla se resumen el grupo o los grupos a los que una persona debe pertenecer para poder instalar, administrar y solucionar los problemas de Lync Server 2013 correctamente.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Ejecutable de Lync Server 2013</th>
<th>Pertenencia a grupos necesaria</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Setup.exe</strong>: ejecutable que inicia la instalación de las herramientas administrativas de Lync Server 2013.</p></td>
<td><p>Miembro del grupo Administradores locales en el equipo desde el que se ejecuta el ejecutable. Miembro del grupo Usuarios de dominio para leer la información en Servicios de dominio de Active Directory. Este nivel de permiso es necesario porque la instalación automática de los paquetes MSI necesarios en el equipo local requiere privilegios que permitan la lectura de los recursos de equipos locales protegidos y la escritura en estos, como directorios Archivos de programa, y un registro protegido como el subárbol Local Machine.</p>
<div>

> [!TIP]  
> También puede delegar los permisos de instalación a los usuarios o grupos a los que no desea otorgar pertenencia en el grupo Admins. del dominio. Para obtener más información, consulte <a href="lync-server-2013-granting-setup-permissions.md">Concesión de permisos de instalación en Lync Server 2013</a> en la documentación sobre implementación.


</div></td>
</tr>
<tr class="even">
<td><p><strong>Deploy.exe</strong>: llamado por setup.exe, deploy.exe realiza la implementación de los componentes del software para los roles del servidor.</p></td>
<td><p>Miembro del grupo Administradores locales en el equipo desde el que se ejecuta el ejecutable. Miembro del grupo Usuarios de dominio para leer la información en los AD DS. Este nivel de permiso es necesario porque la instalación automática de los paquetes MSI necesarios en el equipo local requiere privilegios que permitan la lectura de los recursos de equipos locales protegidos y la escritura en estos, como directorios Archivos de programa, y un registro protegido como el subárbol Local Machine. La pertenencia en el grupo RtcUniversalReadOnlyAdmins es necesaria para leer el Almacén de administración central.</p>
<div>

> [!NOTE]
> Si está ejecutando los sistemas operativos Sistema operativo Windows Vista o Sistema operativo Windows 7, el Control de acceso del usuario (UAC) le solicitará que continúe con la instalación. Si ha iniciado sesión con una cuenta de usuario estándar, necesitará que alguien que sea miembro del grupo Administradores locales le proporcione las credenciales cuando se le solicite una cuenta con permisos para instalar el software.


</div></td>
</tr>
<tr class="odd">
<td><p><strong>Bootstrapper.exe</strong>: llamado por setup.exe, bootstrapper.exe realiza la implementación y la configuración de los roles del servidor.</p></td>
<td><p>Miembro del grupo Administradores locales en el equipo desde el que se ejecuta el ejecutable. Miembro del grupo RTCUniversalServerAdmins con permiso para ejecutar el archivo Bootstrapper.exe. Miembro del grupo Usuarios de dominio para leer la información en los AD DS. Este nivel de permiso es necesario porque la instalación automática de los paquetes MSI necesarios en el equipo local requiere privilegios que permitan la lectura de los recursos de equipos locales protegidos y la escritura en estos, como directorios Archivos de programa, y un registro protegido como el subárbol Local Machine.</p></td>
</tr>
<tr class="even">
<td><p><strong>TopologyBuilder</strong>: interfaz basada en asistente para crear, ver, ajustar y validar topologías de Lync Server 2013.</p></td>
<td><p>Miembro del grupo Administradores locales en el equipo desde el que se ejecuta el ejecutable para ver la topología. Miembro del grupo RTCUniversalServerAdmins para cambiar las opciones de configuración. Miembro del grupo RTCUniversalServerAdmins y del grupo Admins. del dominio, o miembro del grupo RTCUniversalServerAdmins (solo si se han otorgado permisos de instalación delegados), para publicar la topología. Para obtener más información sobre delegación de permisos de instalación para permitir a los miembros del grupo RTCUniversalServerAdmins publicar la topología sin ser miembros del grupo Admins. del dominio, consulte <a href="lync-server-2013-granting-setup-permissions.md">Concesión de permisos de instalación en Lync Server 2013</a> en la documentación sobre implementación.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AdminUIHost</strong>: interfaz gráfica de usuario basada en web para administrar Lync Server 2013.</p></td>
<td><p>Miembro del grupo CsAdministrator o miembro de otra función de control de acceso basado en roles (RBAC) donde se asigna la tarea administrativa específica. Panel de control de Lync Server 2013 implementa cambios de configuración cuando ejecuta los cmdlets de Shell de administración de Lync Server 2013. Para obtener una lista de las funciones predefinidas y los miembros de cmdlets que está permitido ejecutar, consulte <a href="lync-server-2013-planning-for-role-based-access-control.md">Planeación del control de acceso basado en roles en Lync Server 2013</a> en la documentación sobre planeación.</p></td>
</tr>
<tr class="even">
<td><p><strong>PowerShell.exe con el módulo cargado de Lync Server 2013</strong>: herramienta administrativa de línea de comandos con cmdlets específicos a la administración de Lync Server 2013.</p></td>
<td><p>Miembro del grupo CsAdministrator o miembro de otra función de RBAC donde se asignó el cmdlet específico. Para obtener una lista de las funciones predefinidas y los miembros de cmdlets que está permitido ejecutar, consulte <a href="lync-server-2013-planning-for-role-based-access-control.md">Planeación del control de acceso basado en roles en Lync Server 2013</a> en la in documentación sobre planeación.</p>
<p>O bien, miembro de uno o más de los siguientes grupos, según el cmdlet:</p>
<ul>
<li><p>RTCUniversalServerAdmins</p></li>
<li><p>RTCUniversalUserAdmins</p></li>
<li><p>RTCUniversalReadOnlyAdmins</p></li>
</ul></td>
</tr>
</tbody>
</table>

