---
title: 'Lync Server 2013: Planeación del control de acceso basado en roles'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for role-based access control (RBAC)
ms:assetid: 41204ba3-ce5b-41a8-a6c3-b444468fa328
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425917(v=OCS.15)
ms:contentKeyID: 48183962
ms.date: 01/28/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1771eb906685294e588e0c67b1fa8fb1f67a8b6e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824095"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-role-based-access-control-in-lync-server-2013"></a>Planeación del control de acceso basado en roles en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2015-01-27_

Para que pueda delegar tareas administrativas a la vez que se mantienen los altos estándares de seguridad, Lync Server 2013 ofrece control de acceso basado en roles (RBAC). Con RBAC, el privilegio administrativo se concede mediante la asignación de usuarios a roles administrativos. Lync Server 2013 incluye un conjunto completo de funciones administrativas integradas y también le permite crear nuevos roles y especificar una lista personalizada de cmdlets para cada nuevo rol. También puede agregar scripts de cmdlets a las tareas permitidas de roles de RBAC tanto predefinidos como personalizados.

<div>

## <a name="better-server-security-and-centralization"></a>Mayor seguridad del servidor y centralización

Con RBAC, el acceso y la autorización se basan de forma precisa en el rol de servidor de Lync de un usuario. Esto permite el uso de la práctica de seguridad "privilegio mínimo", que concede a los administradores y usuarios solo los derechos necesarios para su trabajo.

<div>


> [!IMPORTANT]  
> Las restricciones de RBAC solo funcionan en los administradores que trabajan de forma remota, mediante el panel de control de Lync Server o el shell de administración de Lync Server. Un usuario que está sentado en un servidor que ejecuta Lync Server no está restringido por RBAC. Por lo tanto, es importante que la seguridad física de su Lync Server Conserve las restricciones RBAC.



</div>

</div>

<div>

## <a name="roles-and-scope"></a>Roles y ámbito

En RBAC, un *rol* está habilitado para usar una lista de cmdlets, diseñada para ser útil para un determinado tipo de administrador o técnico. Un *ámbito* es el conjunto de objetos en el que pueden operar los cmdlets definidos en un rol. Los objetos a los que afecta el ámbito pueden ser cuentas de usuario (agrupadas por unidad de organización) o servidores (agrupados por sitio).

En la tabla siguiente se enumeran los roles predefinidos en Lync Server y se ofrece información general sobre los tipos de tareas que cada uno puede realizar. La cuarta columna muestra el rol de servidor de Microsoft Exchange similar para cada rol de servidor de Lync, si hay alguno.

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
<th>Rol</th>
<th>Tareas permitidas</th>
<th>Grupo de Active Directory subyacente</th>
<th>Equivalente de Exchange</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CsAdministrator</p></td>
<td><p>Permite realizar todas las tareas administrativas y modificar toda la configuración, incluida la creación de roles y la asignación de usuarios a roles. Puede expandir una implementación agregando nuevos sitios, agrupaciones y servicios.</p></td>
<td><p>CSAdministrator</p></td>
<td><p>Administración de la organización</p></td>
</tr>
<tr class="even">
<td><p>CsUserAdministrator</p></td>
<td><p>Permite habilitar y deshabilitar usuarios para Lync Server, mover usuarios y asignar directivas existentes a los usuarios. No se pueden modificar las directivas.</p></td>
<td><p>CSUserAdministrator</p></td>
<td><p>Destinatarios de correo</p></td>
</tr>
<tr class="odd">
<td><p>CsVoiceAdministrator</p></td>
<td><p>Permite crear, configurar y administrar directivas y configuración relacionadas con la voz.</p></td>
<td><p>CSVoiceAdministrator</p></td>
<td><p>No aplicable</p></td>
</tr>
<tr class="even">
<td><p>CsServerAdministrator</p></td>
<td><p>Permite administrar, supervisar y solucionar problemas con servidores y servicios. Puede evitar nuevas conexiones a los servidores, detener e iniciar servicios, y aplicar actualizaciones de software. No se pueden realizar cambios con el impacto global de la configuración.</p></td>
<td><p>CSServerAdministrator</p></td>
<td><p>Administración de servidores</p></td>
</tr>
<tr class="odd">
<td><p>CsViewOnlyAdministrator</p></td>
<td><p>Permite ver la implementación, incluida la información del usuario y del servidor, a fin de supervisar el estado de implementación.</p></td>
<td><p>CSViewOnlyAdministrator</p></td>
<td><p>Administración de la organización de solo lectura</p></td>
</tr>
<tr class="even">
<td><p>CsHelpDesk</p></td>
<td><p>Permite ver la implementación, incluidas las propiedades y directivas del usuario. Puede ejecutar tareas específicas de solución de problemas. No se pueden cambiar las propiedades o directivas del usuario, la configuración del servidor o los servicios.</p></td>
<td><p>CSHelpDesk</p></td>
<td><p>Telefónica</p></td>
</tr>
<tr class="odd">
<td><p>CsArchivingAdministrator</p></td>
<td><p>Permite modificar las directivas y la configuración de archivado.</p></td>
<td><p>CSArchivingAdministrator</p></td>
<td><p>Administración de retención, retención legal</p></td>
</tr>
<tr class="even">
<td><p>CsResponseGroupAdministrator</p></td>
<td><p>Permite administrar la configuración de la aplicación de grupo de respuesta dentro de un sitio.</p></td>
<td><p>CSResponseGroupAdministrator</p></td>
<td><p>No aplicable</p></td>
</tr>
<tr class="odd">
<td><p>CsLocationAdministrator</p></td>
<td><p>El nivel más bajo de derechos para la administración mejorada de 9-1-1 (E9-1-1), incluida la creación de ubicaciones e identificadores de red E9-1-1, y la asociación entre sí. Este rol siempre se asigna con un ámbito global.</p></td>
<td><p>CSLocationAdministrator</p></td>
<td><p>No aplicable</p></td>
</tr>
<tr class="even">
<td><p>AdministradorGrupoRespuestaCs</p></td>
<td><p>Permite administrar grupos de respuesta específicos.</p></td>
<td><p>CSResponseGroupManager</p></td>
<td><p>No aplicable</p></td>
</tr>
<tr class="odd">
<td><p>CsPersistentChatAdministrator</p></td>
<td><p>Permite administrar la característica de chat persistente y las salas de chat persistentes específicas.</p></td>
<td><p>CSPersistentChatAdministrator</p></td>
<td><p>No aplicable</p></td>
</tr>
</tbody>
</table>


Todos los roles predefinidos que se incluyen en Lync Server tienen un ámbito global. Para seguir las prácticas de privilegios mínimos, no debe asignar usuarios a roles con ámbito global si van a administrar únicamente un conjunto limitado de servidores o usuarios. Para ello, puede crear roles que se basen en un rol existente, pero con un ámbito más limitado.

<div>

## <a name="creating-a-scoped-role"></a>Crear un rol con ámbito

Al crear un rol con ámbito limitado (un rol con ámbito), especifique el ámbito, junto con el rol existente en el que se basa y el grupo de Active Directory al que se va a asignar el rol. El grupo de Active Directory que especifique debe estar ya creado. El siguiente cmdlet es un ejemplo de una creación de un rol que tiene los privilegios de una de las funciones administrativas predefinidas, pero con un ámbito limitado. Crea un nuevo rol denominado `Site01 Server Administrators`. El rol tiene las capacidades del rol de CsServerAdministrator predefinido, pero solo para los servidores que se encuentran en el sitio de Site01. Para que este cmdlet funcione, el sitio de Site01 debe estar ya definido y ya debe existir un grupo `Site01 Server Administrators` de seguridad universal con el nombre.

    New-CsAdminRole -Identity "Site01 Server Administrators" -Template CsServerAdministrator -ConfigScopes "site:Site01"

Después de ejecutar este cmdlet, todos los usuarios que sean miembros `Site01 Server Administrators` del grupo dispondrán de privilegios de administrador de servidor para los servidores de Site01. Además, los usuarios que se agreguen posteriormente a este grupo de seguridad universal también obtendrán los privilegios de este rol. Observe que se llama `Site01 Server Administrators`tanto a la propia función como al grupo de seguridad universal al que está asignada.

En el ejemplo siguiente se limita el ámbito de usuario en lugar del ámbito del servidor. Crea un `Sales Users Administrator` rol para administrar las cuentas de usuario en la unidad organizativa ventas. El grupo de seguridad universal de SalesUsersAdministrator ya debe crearse para que este cmdlet funcione.

    New-CsAdminRole -Identity "Sales Users Administrator " -Template CsUserAdministrator -UserScopes "OU:OU=Sales, OU=Lync Tenants, DC=Domain, DC=com"

</div>

<div>

## <a name="creating-a-new-role"></a>Crear un nuevo rol

Para crear un rol que tenga acceso a un conjunto de cmdlets que no se encuentra en una de las funciones predefinidas, o a un conjunto de scripts o módulos, vuelva a empezar a usar uno de los roles predefinidos como una plantilla. Tenga en cuenta que los scripts y los módulos que los roles pueden ejecutarse deben almacenarse en las siguientes ubicaciones:

  - La ruta de acceso del módulo de Lync, que es\\de forma\\predeterminada C\\: archivos de programa\\archivos\\comunes Microsoft Lync Server 2013 módulos Lync

  - La ruta de acceso del script de usuario, que es\\, de\\forma predeterminada\\, C: archivos\\comunes de archivos de programa Microsoft Lync Server 2013 AdminScripts

Para hacer un nuevo rol, use el cmdlet **New-CsAdminRole** . Antes **de ejecutar New-CsAdminRole**, primero debe crear el grupo de seguridad universal subyacente que se asociará con este rol.

Los siguientes cmdlets constituyen un ejemplo de la creación de un nuevo rol. Crean un nuevo tipo de función denominado `MyHelpDeskScriptRole`. El nuevo rol tiene las capacidades del rol de CsHelpDesk predefinido y, además, puede ejecutar las funciones en un script denominado "testScript".

    New-CsAdminRole -Identity "MyHelpDeskScriptRole" -Template CsHelpDesk -ScriptModules @{Add="testScript.ps1"}

Para que este cmdlet funcione, primero debe haber creado el grupo de seguridad universal MyHelpDeskScriptRole.

Después de que este cmdlet se ejecuta, puede asignar usuarios directamente a este rol (en cuyo caso tienen ámbito global) o crear un rol con ámbito basado en este rol, como se explica en creación de un rol con ámbito, anteriormente en este documento.

</div>

<div>

## <a name="assigning-roles-to-users"></a>Asignar roles a usuarios

Cada rol de Lync Server está asociado con un grupo subyacente de seguridad universal de Active Directory. Los usuarios que agregue al grupo subyacente obtienen las funciones de ese rol.

Los ejemplos de las secciones anteriores crearon un nuevo rol y asignaron un grupo de seguridad universal existente al nuevo rol. Para asignar un rol existente a uno o varios usuarios, agregue esos usuarios al grupo asociado con el rol. Puede Agregar usuarios individuales y grupos de seguridad universal a estos grupos.

Por ejemplo, el rol **CsAdministrator** se concede automáticamente al grupo de seguridad universal de **administradores de CS** en Active Directory. Este grupo de seguridad universal se crea en Active Directory al implementar Lync Server. Para conceder este privilegio a un usuario o grupo, simplemente puede agregarlos al grupo de **administradores de CS** .

A un usuario se le pueden dar varios roles RBAC mediante su adición a los grupos de Active Directory subyacentes que corresponden a cada rol.

Tenga en cuenta que, al crear un rol, los usuarios que se agreguen posteriormente al grupo de Active Directory subyacente ganarán las funciones de ese rol.

</div>

<div>

## <a name="modifying-the-abilities-of-a-role"></a>Modificar las funciones de un rol

Puede modificar la lista de cmdlets y scripts que puede ejecutar un rol. Puede modificar los cmdlets y scripts que pueden ejecutar los roles personalizados, pero solo puede modificar los scripts para roles predefinidos. Cada cmdlet que escriba puede Agregar, quitar o reemplazar cmdlets o scripts.

Para modificar un rol, use el cmdlet **set-CsAdminRole** . El siguiente cmdlet quita un script del rol.

    Set-CsAdminRole -Identity "MyHelpDeskScriptRole" -ScriptModules @{Remove="testScript.ps1"}

</div>

</div>

<div>

## <a name="planning-for-rbac"></a>Planificación de RBAC

Para cada persona a la que se va a conceder algún tipo de derecho administrativo para su implementación de Lync Server, considere exactamente qué tareas necesitan realizar y, a continuación, asígnelos a roles con el menor privilegio y el ámbito necesario para su trabajo. Si es necesario, puede usar el cmdlet **set-CsAdminRole** para crear un nuevo rol solo con los cmdlets necesarios para las tareas de esta persona.

Los usuarios que tienen el rol CsAdministrator pueden crear todos los tipos de roles, incluidos los roles basados en CsAdministrator, y asignarles usuarios. El procedimiento recomendado es asignar el rol CsAdministrator a un conjunto muy pequeño de usuarios de confianza.

</div>

</div>

<span> </span>

</div>

</div>

</div>

