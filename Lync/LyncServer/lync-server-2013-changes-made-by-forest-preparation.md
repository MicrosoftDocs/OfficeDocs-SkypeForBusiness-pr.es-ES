---
title: Cambios realizados por la preparación del bosque en Lync Server 2013
TOCTitle: Cambios realizados por la preparación del bosque en Lync Server 2013
ms:assetid: 2e12613e-59f2-4810-a32d-24a9789a4a6e
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg425791(v=OCS.15)
ms:contentKeyID: 48274791
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Cambios realizados por la preparación del bosque en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

En esta sección se describe la configuración global y los objetos, así como el servicio universal y los grupos de administración, que se crean mediante el paso de preparación del bosque.

## Configuración global y objetos de Active Directory

Si almacena la configuración global en el contenedor Configuration (como ocurre con todas las implementaciones nuevas de Lync Server 2013), la preparación del bosque usa el contenedor Services existente y agrega un objeto **RTC Service** dentro del objeto Configuration\\Services. Al preparar el bosque, se agrega un objeto de **Global Settings** de tipo msRTCSIP-GlobalContainer dentro del objeto RTC Service. El objeto de configuración global contiene toda la configuración que se aplica a la implementación de Lync Server. Si almacena la configuración global en el contenedor System, al preparar el bosque se usa un contenedor Microsoft dentro del contenedor System del dominio raíz y se agrega un objeto RTC Service dentro del objeto System\\Microsoft.

Al preparar el bosque, se agrega también un nuevo objeto **msRTCSIP-Domain** para el dominio raíz en el que se ejecuta el procedimiento.

## Servicio universal y grupos de administración de Active Directory

La preparación del bosque crea grupos universales basados en el dominio especificado y agrega entradas de control de acceso (ACE) para estos grupos. Este paso crea los grupos universales en los contenedores User del dominio especificado.

Los grupos universales permiten a los administradores obtener acceso a la configuración global y los servicios y administrarlos. La preparación del bosque agrega los siguientes tipos de grupos universales:

  - **Grupos administrativos**   Estos grupos definen roles de administrador para una red de Lync Server.

  - **Grupos de infraestructura**   Estos grupos proporcionan permiso para obtener acceso a áreas específicas de la infraestructura de Lync Server. Funcionan como componentes de grupos administrativos. No debe modificar estos grupos ni agregar usuarios directamente.

  - **Grupos de servicio**   Estos grupos son cuentas de servicio necesarias para obtener acceso a diferentes servicios de Lync Server.

En la tabla siguiente se describen los grupos administrativos.

### Grupos administrativos creados durante la preparación de un bosque

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Grupo administrativo</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCUniversalServerAdmins</p></td>
<td><p>Permite a los miembros administrar la configuración de los servidores y grupos de servidores, incluidos todos los roles de servidor, la configuración global y los usuarios.</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Permite a los miembros administrar la configuración de los usuarios y mover los usuarios de un servidor o grupo de servidores a otro.</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalReadOnlyAdmins</p></td>
<td><p>Permite a los miembros leer la configuración de los servidores, grupos de servidores y usuarios.</p></td>
</tr>
</tbody>
</table>


En la tabla siguiente se describen los grupos de infraestructura.

### Grupos de infraestructura creados durante la preparación de un bosque

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Grupo de infraestructura</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCUniversalGlobalWriteGroup</p></td>
<td><p>Concede acceso de escritura a los objetos de configuración global de Lync Server.</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalGlobalReadOnlyGroup</p></td>
<td><p>Concede acceso de solo lectura a los objetos de configuración global de Lync Server.</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Concede acceso de solo lectura a la configuración de los usuarios de Lync Server.</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>Concede acceso de solo lectura a la configuración de Lync Server. Este grupo no tiene acceso a la configuración de nivel de grupo de servidores, sino únicamente a la configuración específica de un servidor individual.</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalSBATechnicians</p></td>
<td><p>Proporciona acceso de solo lectura a la configuración de Lync Server y se incorpora en el grupo Administradores locales de las aplicaciones de sucursal con funciones de supervivencia durante la instalación.</p></td>
</tr>
</tbody>
</table>


En la tabla siguiente se describen los grupos de servicio.

### Grupos de servicio creados durante la preparación de un bosque

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Grupo de servicio</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>Incluye las cuentas de servicio utilizadas para ejecutar Servidor front-end y los servidores de Standard Edition. Este grupo permite a los usuarios acceso de lectura y escritura a la configuración global de Lync Server y los objetos de usuario de Active Directory.</p></td>
</tr>
<tr class="even">
<td><p>RTCComponentUniversalServices</p></td>
<td><p>Incluye las cuentas de servicio usadas para ejecutar los servidores de conferencia A/V, Servicios web, Servidor de mediación, Servidor de archivado y Servidor de supervisión.</p></td>
</tr>
<tr class="odd">
<td><p>RTCProxyUniversalServices</p></td>
<td><p>Incluye las cuentas de servicio usadas para ejecutar los servidores perimetrales de Lync Server.</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalConfigReplicator</p></td>
<td><p>Incluye servidores que pueden participar en la replicación de Lync ServerAlmacén de administración central.</p></td>
</tr>
<tr class="odd">
<td><p>RTCSBAUniversalServices</p></td>
<td><p>Proporciona acceso de solo lectura a la configuración de Lync Server, pero permite la configuración para la instalación de un servidor de sucursal con funciones de supervivencia y la implementación de aplicaciones de sucursal de supervivencia.</p></td>
</tr>
</tbody>
</table>


A continuación, la preparación del bosque agrega los grupos de servicio y administración a los grupos de infraestructura correspondientes del siguiente modo:

  - RTCUniversalServerAdmins se agrega a RTCUniversalGlobalReadOnlyGroup, RTCUniversalGlobalWriteGroup, RTCUniversalServerReadOnlyGroup y RTCUniversalUserReadOnlyGroup.

  - RTCUniversalUserAdmins se agrega como miembro de RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup y RTCUniversalUserReadOnlyGroup.

  - RTCHSUniversalServices, RTCComponentUniversalServices y RTCUniversalReadOnlyAdmins se agregan como miembros de RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup y RTCUniversalUserReadOnlyGroup.

Durante la preparación del bosque también se crean los siguientes grupos de control de acceso basado en roles (RBAC):

  - CSAdministrator

  - CSArchivingAdministrator

  - CSHelpDesk

  - CSLocationAdministrator

  - CSResponseGroupAdministrator

  - CSServerAdministrator

  - CSUserAdministrator

  - CSViewOnlyAdministrator

  - CSVoiceAdministrator

  - CsPersistentChatAdministator

  - CsResponseGroupManager

Para obtener información detallada sobre los roles RBAC y las tareas que cada uno de ellos puede acometer, consulte [Planeación del control de acceso basado en roles en Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) en la documentación de planeación.

La preparación del bosque crea entradas ACE privadas y públicas. Crea entradas ACE privadas en el contenedor de configuración global que Lync Server usa. Este contenedor solo lo usa Lync Server, y se encuentra en el contenedor Configuration o en el contenedor System del dominio raíz, según dónde se haya almacenado la configuración global. Las entradas ACE públicas que se crean al preparar el bosque se indican en la siguiente tabla:

### Entradas ACE públicas creadas al preparar el bosque

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>ACE</th>
<th>RTCUniversalGlobalReadOnlyGroup</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Contenedor System de dominio raíz Read (no se hereda)<strong>*</strong></p></td>
<td><p>X</p></td>
</tr>
<tr class="even">
<td><p>Contenedor DisplaySpecifiers de Read Configuration (no se hereda)</p></td>
<td><p>X</p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> <STRONG>*</STRONG> Las entradas de control de acceso que no se heredan no conceden acceso a los objetos secundarios de estos contenedores. Las entradas de control de acceso que se heredan permiten el acceso a los objetos secundarios de estos contenedores.



En el contenedor Configuration, bajo el contexto de nomenclatura de configuración, el procedimiento de preparación del bosque realiza las siguientes tareas:

  - Agrega una entrada **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** para la página **RTC property** dentro de los atributos adminContextMenu y adminPropertyPages del especificador de presentación de idioma correspondiente a los objetos User, Contact e InetOrgPerson (por ejemplo, CN=user-Display,CN=409,CN=DisplaySpecifiers).

  - Agrega un objeto **RTCPropertySet** de tipo **controlAccessRight** en **Extended-Rights** que se aplica a las clases User y Contact.

  - Agrega un objeto **RTCUserSearchPropertySet** de tipo **controlAccessRight** en **Extended-Rights** que se aplica a las clases User, Contact, OU y DomainDNS.

  - Agrega **msRTCSIP-PrimaryUserAddress** en el atributo **extraColumns** de cada especificador de presentación de unidad organizativa de idioma (por ejemplo, CN=organizationalUnit-Display,CN=409,CN=DisplaySpecifiers) y copia los valores del atributo **extraColumns** de la presentación predeterminada (por ejemplo, CN=default-Display, CN=409,CN=DisplaySpecifiers).

  - Agrega los atributos de filtro **msRTCSIP-PrimaryUserAddress**, **msRTCSIP-PrimaryHomeServer** y **msRTCSIP-UserEnabled** en el atributo **attributeDisplayNames** de cada especificador de presentación de idioma de los objetos Users, Contacts e InetOrgPerson (por ejemplo, en inglés: CN=user-Display,CN=409,CN=DisplaySpecifiers).

