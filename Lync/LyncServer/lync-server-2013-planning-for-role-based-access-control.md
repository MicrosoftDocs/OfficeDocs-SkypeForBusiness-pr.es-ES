---
title: 'Lync Server 2013: Planeación del control de acceso basado en roles'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for role-based access control (RBAC)
ms:assetid: 41204ba3-ce5b-41a8-a6c3-b444468fa328
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425917(v=OCS.15)
ms:contentKeyID: 48183962
ms.date: 01/28/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fb7a359620c7e93565c0d4ef49c813ff0966989c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046633"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-role-based-access-control-in-lync-server-2013"></a>Planeación del control de acceso basado en roles en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2015-01-27_

Para permitirle delegar tareas administrativas a la vez que se mantienen los altos estándares de seguridad, Lync Server 2013 ofrece control de acceso basado en roles (RBAC). Con el RBAC, los privilegios administrativos se conceden asignando a los usuarios roles administrativos. Lync Server 2013 incluye un amplio conjunto de funciones administrativas integradas y también permite crear nuevos roles y especificar una lista personalizada de cmdlets para cada nuevo rol. También puede añadir scripts de cmdlets a las tareas permitidas tanto de los roles RBAC predefinidos como personalizados.

<div>

## <a name="better-server-security-and-centralization"></a>Mejor seguridad y centralización de los servidores

Con RBAC, el acceso y la autorización se basan con precisión en el rol de servidor Lync de un usuario. Esto permite un mayor uso de la práctica de seguridad de "privilegios mínimos", que únicamente concede a los administradores y usuarios los derechos que son necesarios para su trabajo.

<div>


> [!IMPORTANT]  
> Las restricciones RBAC solo funcionan en los administradores que trabajan de forma remota, mediante el panel de control de Lync Server o el shell de administración de Lync Server. Un usuario que se encuentra sentado en un servidor que ejecuta Lync Server no está restringido por RBAC. Por lo tanto, es importante que la seguridad física de Lync Server Conserve las restricciones RBAC.



</div>

</div>

<div>

## <a name="roles-and-scope"></a>Roles y ámbito

En el RBAC, un *rol* permite utilizar una lista de cmdlets y está diseñado para que sea de utilidad para un determinado tipo de administrador o técnico. Un *ámbito* es el conjunto de objetos en el que pueden actuar los cmdlets definidos en un rol. Los objetos a los que afecta el ámbito pueden ser cuentas de usuario (agrupadas por unidad organizativa) o servidores (agrupados por sitio).

En la siguiente tabla se enumeran los roles predefinidos en Lync Server y se proporciona una descripción general de los tipos de tareas que puede realizar cada uno. En la cuarta columna se muestra el rol de servidor de Microsoft Exchange similar para cada rol de Lync Server, si hay alguno.

### <a name="predefined-administrative-roles"></a>Roles administrativos predefinidos

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Role</th>
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
<td><p>Puede habilitar y deshabilitar usuarios para Lync Server, mover usuarios y asignar directivas existentes a los usuarios. No puede modificar directivas.</p></td>
<td><p>CSUserAdministrator</p></td>
<td><p>Destinatarios de correo</p></td>
</tr>
<tr class="odd">
<td><p>CsVoiceAdministrator</p></td>
<td><p>Puede crear, definir y administrar las configuraciones y las directivas relacionadas con la voz.</p></td>
<td><p>CSVoiceAdministrator</p></td>
<td><p>No aplicable.</p></td>
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
<td><p>Escritorio</p></td>
</tr>
<tr class="odd">
<td><p>Rol csarchivingadministrator</p></td>
<td><p>Puede modificar la configuración y las directivas de archivado.</p></td>
<td><p>Rol csarchivingadministrator</p></td>
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
<td><p>CsResponseGroupManager</p></td>
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
</tbody>
</table>


Todos los roles predefinidos que se incluyen en Lync Server tienen un ámbito global. Para seguir las prácticas de privilegios mínimos, no se deben asignar usuarios a roles de ámbito global si solo van a administrar un conjunto limitado de servidores o usuarios. Para ello, puede crear roles basados en un rol existente pero con un ámbito más limitado.

<div>

## <a name="creating-a-scoped-role"></a>Creación de un rol con un ámbito

Cuando crea un rol con un ámbito limitado (un rol con ámbito), puede especificar el ámbito junto con el rol existente con el que se basa y el grupo de Active Directory al que se le asignará el rol. El grupo de Active Directory que se especifique debe haberse creado ya. El siguiente cmdlet es un ejemplo de una creación de un rol que tiene los privilegios de uno de los roles administrativos predefinidos, pero con un ámbito limitado. Crea un nuevo rol denominado `Site01 Server Administrators`. El rol tiene la capacidad de un rol CsServerAdministrator predefinido, pero solo para los servidores ubicados en el sitio Site01. Para que este cmdlet funcione, el sitio de Site01 debe estar ya definido y el grupo de seguridad universal `Site01 Server Administrators` debe existir previamente.

    New-CsAdminRole -Identity "Site01 Server Administrators" -Template CsServerAdministrator -ConfigScopes "site:Site01"

Después de ejecutar este cmdlet, todos los usuarios que sean miembros `Site01 Server Administrators` del grupo tendrán privilegios de administrador de servidor para los servidores de Site01. Además, los usuarios que se agreguen posteriormente a este grupo de seguridad universal también obtendrán los privilegios de esta función. Tenga en cuenta que se llama `Site01 Server Administrators`al propio rol y al grupo de seguridad universal al que está asignado.

En el siguiente ejemplo se limita el ámbito de usuario en lugar del ámbito de servidor. Crea una `Sales Users Administrator` función para administrar las cuentas de usuario en la unidad organizativa ventas. El grupo de seguridad universal de SalesUsersAdministrator ya debe estar creado para que funcione este cmdlet.

    New-CsAdminRole -Identity "Sales Users Administrator " -Template CsUserAdministrator -UserScopes "OU:OU=Sales, OU=Lync Tenants, DC=Domain, DC=com"

</div>

<div>

## <a name="creating-a-new-role"></a>Creación de un nuevo rol

Para crear un rol que tenga acceso a un conjunto de cmdlets no incluido en uno de los roles predefinidos, o a un conjunto de scripts o módulos, debe empezar de nuevo utilizando uno de los roles predefinidos como plantilla. Tenga en cuenta que los scripts y los módulos que pueden ejecutar estos roles se deben almacenar en las ubicaciones siguientes:

  - La ruta del módulo de Lync, que de forma predeterminada\\es C\\: archivos\\de programa Archivos comunes\\Microsoft\\Lync Server 2013 módulos Lync

  - La ruta de acceso del script de usuario, que es\\de forma\\predeterminada C\\: archivos de programa\\archivos comunes Microsoft Lync Server 2013 AdminScripts

Para crear un nuevo rol, debe utilizar el cmdlet **New-CsAdminRole**. Antes **de ejecutar New-CsAdminRole**, debe crear primero el grupo de seguridad universal subyacente que se asociará a este rol.

Los siguientes cmdlets constituyen un ejemplo de la creación de un nuevo rol. Crean un nuevo tipo de rol denominado `MyHelpDeskScriptRole`. El nuevo rol tiene la capacidad del rol CsHelpDesk predefinido, y se puede ejecutar adicionalmente las funciones en un script denominado “testscript”.

    New-CsAdminRole -Identity "MyHelpDeskScriptRole" -Template CsHelpDesk -ScriptModules @{Add="testScript.ps1"}

Para que este cmdlet funcione, primero debe haber creado el grupo de seguridad universal MyHelpDeskScriptRole.

Después de ejecutar este cmdlet, puede asignar usuarios directamente a este rol (en ese caso tendrán un ámbito global), o crear un rol con ámbito basado en este rol, tal como se explica en el apartado Creación de un rol con ámbito, anteriormente en este documento.

</div>

<div>

## <a name="assigning-roles-to-users"></a>Asignar roles a usuarios

Cada rol de Lync Server está asociado a un grupo de seguridad universal de Active Directory subyacente. Los usuarios que se agreguen al grupo subyacente obtendrán las capacidades del rol.

En los ejemplos de las secciones anteriores se creó un nuevo rol y se asignó un grupo de seguridad universal existente a la nueva función. Para asignar un rol existente a uno o más usuarios, agregue los usuarios al grupo asociado al rol. Puede Agregar usuarios individuales y grupos de seguridad universal a estos grupos.

Por ejemplo, el rol **CsAdministrator** se concede automáticamente al grupo de seguridad universal **administradores de CS** en Active Directory. Este grupo de seguridad universal se crea en Active Directory al implementar Lync Server. Para conceder este privilegio a un usuario o grupo, basta con agregarlos al grupo **Administradores CS**.

A un usuario se le pueden asignar varios roles RBAC siempre que se agregue a los grupos subyacentes de Active Directory correspondientes a cada rol.

Tenga en cuenta que cuando se crea un rol, los usuarios que se agreguen más adelante al grupo subyacente de Active Directory obtendrán las capacidades de dicho rol.

</div>

<div>

## <a name="modifying-the-abilities-of-a-role"></a>Modificación de las capacidades de un rol

Puede modificar la lista de cmdlets y scripts que un rol puede ejecutar. Puede modificar tanto los cmdlets como los scripts que pueden ejecutar los roles personalizados, pero solo puede modificar los scripts de roles predefinidos. En cada cmdlet que escriba, puede agregar, quitar o cambiar cmdlets o scripts.

Para modificar un rol, utilice el cmdlet **Set-CsAdminRole**. El siguiente cmdlet quita un script del rol.

    Set-CsAdminRole -Identity "MyHelpDeskScriptRole" -ScriptModules @{Remove="testScript.ps1"}

</div>

</div>

<div>

## <a name="planning-for-rbac"></a>Planeación del RBAC

Para cada persona a la que se va a conceder cualquier tipo de derechos administrativos para la implementación de Lync Server, tenga en cuenta exactamente qué tareas deben realizar y, a continuación, asígnelas a funciones con el menor privilegio y el ámbito necesario para su trabajo. Si es necesario, puede utilizar el cmdlet **Set-CsAdminRole** para crear un nuevo rol con solo los cmdlets necesarios para las tareas de esa persona.

Los usuarios que dispongan del rol CsAdministrator pueden crear todo tipo de roles, incluidos los roles que se basan en CsAdministrator, y asignarles usuarios. Se recomienda asignar el rol CsAdministrator a un conjunto muy pequeño de usuarios de confianza.

</div>

</div>

<span> </span>

</div>

</div>

</div>

