---
title: 'Lync Server 2013: Planeación del control de acceso basado en roles'
TOCTitle: Planeación del control de acceso basado en roles (RBAC)
ms:assetid: 41204ba3-ce5b-41a8-a6c3-b444468fa328
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg425917(v=OCS.15)
ms:contentKeyID: 48275032
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Planeación del control de acceso basado en roles en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

Para permitirle delegar tareas administrativas y mantener al mismo tiempo altos estándares de seguridad, el Lync Server 2013 ofrece el control de acceso basado en roles (RBAC). Con el RBAC, los privilegios administrativos se conceden asignando a los usuarios roles administrativos. Lync Server 2013 incluye un completo conjunto de roles administrativos integrados y, además, le permite crear nuevos roles y especificar una lista personalizada de cmdlets para cada nuevo rol. También puede añadir scripts de cmdlets a las tareas permitidas tanto de los roles RBAC predefinidos como personalizados.

## Mejor seguridad y centralización de los servidores

Con el RBAC, el acceso y la autorización se basa con mayor precisión en el rol de Lync Server de un usuario. Esto permite un mayor uso de la práctica de seguridad de "privilegios mínimos", que únicamente concede a los administradores y usuarios los derechos que son necesarios para su trabajo.

> [!IMPORTANT]  
> Las restricciones RBAC solo se aplican a administradores que trabajen de forma remota, mediante el Panel de control de Lync Server o Shell de administración de Lync Server. El RBAC no restringe a un usuario que trabaje en un servidor que ejecute Lync Server. Por consiguiente, la seguridad física de Lync Server es importante para preservar las restricciones RBAC.



## Roles y ámbito

En el RBAC, un *rol* permite utilizar una lista de cmdlets y está diseñado para que sea de utilidad para un determinado tipo de administrador o técnico. Un *ámbito* es el conjunto de objetos en el que pueden actuar los cmdlets definidos en un rol. Los objetos a los que afecta el ámbito pueden ser cuentas de usuario (agrupadas por unidad organizativa) o servidores (agrupados por sitio).

En la tabla siguiente se enumeran los roles predefinidos en Lync Server y se ofrece información general sobre los tipos de tareas que cada uno puede realizar. La cuarta columna muestra el rol de Microsoft Exchange Server que es similar a cada rol de Lync Server, si existe alguno.

### Roles administrativos predefinidos

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Rol</th>
<th>Tareas permitidas</th>
<th>Grupo subyacente de Active Directory</th>
<th>Equivalente en Exchange</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CsAdministrator</p></td>
<td><p>Puede realizar todas las tareas administrativas y modificar todas las configuraciones, como crear roles y asignar usuarios a roles. Puede ampliar una implementación agregando nuevos sitios, grupos de servidores y servicios.</p></td>
<td><p>CSAdministrator</p></td>
<td><p>Administración de la organización</p></td>
</tr>
<tr class="even">
<td><p>CsUserAdministrator</p></td>
<td><p>Puede habilitar y deshabilitar usuarios de Lync Server, mover usuarios y asignar directivas existentes a usuarios. No puede modificar directivas.</p></td>
<td><p>CSUserAdministrator</p></td>
<td><p>Destinatarios de correo</p></td>
</tr>
<tr class="odd">
<td><p>CsVoiceAdministrator</p></td>
<td><p>Puede crear, definir y administrar las configuraciones y las directivas relacionadas con la voz.</p></td>
<td><p>CSVoiceAdministrator</p></td>
<td><p>No aplicable</p></td>
</tr>
<tr class="even">
<td><p>CsServerAdministrator</p></td>
<td><p>Puede administrar, supervisar y solucionar problemas de servidores y servicios. Puede impedir nuevas conexiones con servidores, detener e iniciar servicios y aplicar actualizaciones de software. No puede efectuar cambios que afecten a la configuración global.</p></td>
<td><p>CSServerAdministrator</p></td>
<td><p>Administración de servidores</p></td>
</tr>
<tr class="odd">
<td><p>CsViewOnlyAdministrator</p></td>
<td><p>Puede ver la implementación, incluida la información de usuarios y servidores, para supervisar el estado de la implementación.</p></td>
<td><p>CSViewOnlyAdministrator</p></td>
<td><p>Administración de la organización con derecho a solo ver</p></td>
</tr>
<tr class="even">
<td><p>CsHelpDesk</p></td>
<td><p>Puede ver la implementación, incluidas las propiedades y directivas de usuario. Puede ejecutar determinadas tareas de solución de problemas. No puede cambiar propiedades ni directivas de usuario, configuración de servidores ni servicios.</p></td>
<td><p>CSHelpDesk</p></td>
<td><p>Departamento de soporte técnico</p></td>
</tr>
<tr class="odd">
<td><p>CsArchivingAdministrator</p></td>
<td><p>Puede modificar la configuración y las directivas de archivado.</p></td>
<td><p>CSArchivingAdministrator</p></td>
<td><p>Administración de retención, Retención legal</p></td>
</tr>
<tr class="even">
<td><p>CsResponseGroupAdministrator</p></td>
<td><p>Puede administrar la configuración de la aplicación Grupo de respuesta en un sitio.</p></td>
<td><p>CSResponseGroupAdministrator</p></td>
<td><p>No aplicable</p></td>
</tr>
<tr class="odd">
<td><p>CsLocationAdministrator</p></td>
<td><p>Nivel mínimo de derechos para administración de 9-1-1 mejorado (E9-1-1), que incluye crear ubicaciones e identificadores de red de E9-1-1 y asociarlos entre sí. Este rol se asigna siempre con un ámbito global.</p></td>
<td><p>CSLocationAdministrator</p></td>
<td><p>No aplicable</p></td>
</tr>
<tr class="even">
<td><p>AdministradorGrupoRespuestaCs</p></td>
<td><p>Puede administrar las grupos de respuesta específicos.</p></td>
<td><p>CSResponseGroupManager</p></td>
<td><p>No aplicable</p></td>
</tr>
<tr class="odd">
<td><p>CsPersistentChatAdministrator</p></td>
<td><p>Puede administrar la característica de chat persistente y las salas de chat persistente específicas.</p></td>
<td><p>CSPersistentChatAdministrator</p></td>
<td><p>No aplicable</p></td>
</tr>
<tr class="even">
<td><p>CsAdministrator</p></td>
<td><p>Puede realizar todas las tareas administrativas y modificar todas las configuraciones, como crear roles y asignar usuarios a roles. Puede ampliar una implementación agregando nuevos sitios, grupos de servidores y servicios.</p></td>
<td><p>CSAdministrator</p></td>
<td><p>Administración de la organización</p></td>
</tr>
<tr class="odd">
<td><p>CsUserAdministrator</p></td>
<td><p>Puede habilitar y deshabilitar usuarios de Lync Server, mover usuarios y asignar directivas existentes a usuarios. No puede modificar directivas.</p></td>
<td><p>CSUserAdministrator</p></td>
<td><p>Destinatarios de correo</p></td>
</tr>
<tr class="even">
<td><p>CsVoiceAdministrator</p></td>
<td><p>Puede crear, definir y administrar las configuraciones y las directivas relacionadas con la voz.</p></td>
<td><p>CSVoiceAdministrator</p></td>
<td><p>No aplicable</p></td>
</tr>
<tr class="odd">
<td><p>CsServerAdministrator</p></td>
<td><p>Puede administrar, supervisar y solucionar problemas de servidores y servicios. Puede impedir nuevas conexiones con servidores, detener e iniciar servicios y aplicar actualizaciones de software. No puede efectuar cambios que afecten a la configuración global.</p></td>
<td><p>CSServerAdministrator</p></td>
<td><p>Administración de servidores</p></td>
</tr>
<tr class="even">
<td><p>CsViewOnlyAdministrator</p></td>
<td><p>Puede ver la implementación, incluida la información de usuarios y servidores, para supervisar el estado de la implementación.</p></td>
<td><p>CSViewOnlyAdministrator</p></td>
<td><p>Administración de la organización con derecho a solo ver</p></td>
</tr>
<tr class="odd">
<td><p>CsHelpDesk</p></td>
<td><p>Puede ver la implementación, incluidas las propiedades y directivas de usuario. Puede ejecutar determinadas tareas de solución de problemas. No puede cambiar propiedades ni directivas de usuario, configuración de servidores ni servicios.</p></td>
<td><p>CSHelpDesk</p></td>
<td><p>Departamento de soporte técnico</p></td>
</tr>
<tr class="even">
<td><p>CsArchivingAdministrator</p></td>
<td><p>Puede modificar la configuración y las directivas de archivado.</p></td>
<td><p>CSArchivingAdministrator</p></td>
<td><p>Administración de retención, Retención legal</p></td>
</tr>
<tr class="odd">
<td><p>CsResponseGroupAdministrator</p></td>
<td><p>Puede administrar la configuración de la aplicación Grupo de respuesta en un sitio.</p></td>
<td><p>CSResponseGroupAdministrator</p></td>
<td><p>No aplicable</p></td>
</tr>
<tr class="even">
<td><p>CsLocationAdministrator</p></td>
<td><p>Nivel mínimo de derechos para administración de 9-1-1 mejorado (E9-1-1), que incluye crear ubicaciones e identificadores de red de E9-1-1 y asociarlos entre sí. Este rol se asigna siempre con un ámbito global.</p></td>
<td><p>CSLocationAdministrator</p></td>
<td><p>No aplicable</p></td>
</tr>
<tr class="odd">
<td><p>AdministradorGrupoRespuestaCs</p></td>
<td><p>Puede administrar las grupos de respuesta específicos.</p></td>
<td><p>CSResponseGroupManager</p></td>
<td><p>No aplicable</p></td>
</tr>
<tr class="even">
<td><p>CsPersistentChatAdministrator</p></td>
<td><p>Puede administrar la característica de chat persistente y las salas de chat persistente específicas.</p></td>
<td><p>CSPersistentChatAdministrator</p></td>
<td><p>No aplicable</p></td>
</tr>
</tbody>
</table>


Todos los roles predefinidos en Lync Server tienen un ámbito global. Para seguir las prácticas de privilegios mínimos, no se deben asignar usuarios a roles de ámbito global si solo van a administrar un conjunto limitado de servidores o usuarios. Para ello, puede crear roles basados en un rol existente pero con un ámbito más limitado.

## Creación de un rol con un ámbito

Cuando se crea un rol con un ámbito limitado (un rol con ámbito), se especifica el ámbito junto con el rol existente en el que se basa y el grupo de Active Directory al que se le asignará el rol. El grupo de Active Directory que se especifique ya debe estar creado. El siguiente cmdlet es un ejemplo de una creación de un rol que tiene los privilegios de uno de los roles administrativos predefinidos, pero con un ámbito limitado. Crea un rol denominado `Site01 Server Administrators`. El rol tiene las capacidades de un rol CsServerAdministrator predefinido, pero solo para los servidores ubicados en el sitio Site01. Para que el cmdlet funcione, el sitio Site01 debe haberse definido previamente; además, debe existir un grupo de seguridad universal denominado `Site01 Server Administrators`.

    New-CsAdminRole -Identity "Site01 Server Administrators" -Template CsServerAdministrator -ConfigScopes "site:Site01"

Una vez ejecutado el cmdlet, todos los usuarios que son miembros del grupo `Site01 Server Administrators` tendrán privilegios de administrador de servidores en los servidores de Site01. Además, los usuarios que se agreguen más adelante a este grupo de seguridad universal también obtendrán los privilegios de este rol. Tenga en cuenta que el propio rol y el grupo de seguridad universal al que está asignado se llaman `Site01 Server Administrators`.

En el siguiente ejemplo se limita el ámbito de usuario en lugar del ámbito de servidor. Se crea un rol `Sales Users Administrator` para administrar las cuentas de usuario de la unidad organizativa de ventas. Para que este cmdlet funcione, el grupo de seguridad universal SalesUsersAdministrator debe haberse creado previamente.

    New-CsAdminRole -Identity "Sales Users Administrator " -Template CsUserAdministrator -UserScopes "OU:OU=Sales, OU=Lync Tenants, DC=Domain, DC=com"

## Creación de un nuevo rol

Para crear un rol que tenga acceso a un conjunto de cmdlets no incluido en uno de los roles predefinidos, o a un conjunto de scripts o módulos, debe empezar de nuevo utilizando uno de los roles predefinidos como plantilla. Tenga en cuenta que los scripts y los módulos que pueden ejecutar estos roles se deben almacenar en las ubicaciones siguientes:

  - La ruta del modulo Lync, que es de modo predeterminado C:\\Archivos de programa\\Archivos comunes\\Microsoft Lync Server 2013\\Modules\\Lync

  - La ruta del script del usuario, que es de modo predeterminado C:\\Archivos de programa\\Archivos comunes\\Microsoft Lync Server 2013\\AdminScripts

Para crear un nuevo rol, debe utilizar el cmdlet **New-CsAdminRole**.Antes de ejecutar **New-CsAdminRole**, debe crear el grupo de seguridad universal subyacente que se asociará a este rol.

Los siguientes cmdlets constituyen un ejemplo de la creación de un nuevo rol. Crean un nuevo tipo de rol denominado `MyHelpDeskScriptRole`. El nuevo rol tiene la capacidad del rol CsHelpDesk predefinido, y se puede ejecutar adicionalmente las funciones en un script denominado “testscript”.

    New-CsAdminRole -Identity "MyHelpDeskScriptRole" -Template CsHelpDesk -ScriptModules @{Add="testScript.ps1"}

Para que este cmdlet funcione, debe crear primero el grupo de seguridad universal MyHelpDeskScriptRole.

Después de ejecutar este cmdlet, puede asignar usuarios directamente a este rol (en ese caso tendrán un ámbito global), o crear un rol con ámbito basado en este rol, tal como se explica en el apartado Creación de un rol con ámbito, anteriormente en este documento.

## Asignar roles a usuarios

Cada rol de Lync Server está asociado a un grupo de seguridad universal subyacente de Active Directory. Los usuarios que se agreguen al grupo subyacente obtendrán las capacidades de dicho rol.

Los ejemplos de los apartados anteriores han ilustrado la creación de un nuevo rol y la asignación de un grupo de seguridad universal existente al nuevo rol. Para asignar un rol existente a uno o más usuarios, agregue los usuarios al grupo asociado al rol. Puede agregar tanto usuarios individuales como grupos de seguridad universal a estos grupos.

Por ejemplo, el rol **CsAdministrator** se concede automáticamente al grupo de seguridad universal **Administradores CS** de Active Directory. Este grupo de seguridad universal se crea en Active Directory al implementar Lync Server. Para conceder este privilegio a un usuario o grupo, basta con agregarlos al grupo **Administradores CS**.

A un usuario se le pueden asignar varios roles RBAC siempre que se agregue a los grupos subyacentes de Active Directory correspondientes a cada rol.

Tenga en cuenta que cuando se crea un rol, los usuarios que se agreguen más adelante al grupo subyacente de Active Directory obtendrán las capacidades de dicho rol.

## Modificación de las capacidades de un rol

Puede modificar la lista de cmdlets y scripts que un rol puede ejecutar. Puede modificar tanto los cmdlets como los scripts que pueden ejecutar los roles personalizados, pero solo puede modificar los scripts de roles predefinidos. En cada cmdlet que escriba, puede agregar, quitar o cambiar cmdlets o scripts.

Para modificar un rol, use el cmdlet **Set-CsAdminRole**. El cmdlet siguiente elimina un script del rol.

    Set-CsAdminRole -Identity "MyHelpDeskScriptRole" -ScriptModules @{Remove="testScript.ps1"}

## Planeación del RBAC

Para cada persona a la que se le conceda cualquier tipo de derecho administrativo para su implementación de Lync Server, considere con exactitud qué tareas debe llevar a cabo y asígnela a los roles con el mínimo privilegio y ámbito necesarios para su trabajo. Si es necesario, puede utilizar el cmdlet **Set-CsAdminRole** para crear un nuevo rol con solo los cmdlets necesarios para las tareas de esa persona.

Los usuarios que dispongan del rol CsAdministrator pueden crear todo tipo de roles, incluidos los roles que se basan en CsAdministrator, y asignarles usuarios. Se recomienda asignar el rol CsAdministrator a un conjunto muy pequeño de usuarios de confianza.

