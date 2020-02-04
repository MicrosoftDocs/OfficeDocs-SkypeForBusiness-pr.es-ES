---
title: 'Lync Server 2013: cambios realizados por la preparación del bosque'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes made by forest preparation
ms:assetid: 2e12613e-59f2-4810-a32d-24a9789a4a6e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425791(v=OCS.15)
ms:contentKeyID: 48183734
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4df16ffb24c4eb4e010e2b57f6af62d3518c05b6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730100"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-forest-preparation-in-lync-server-2013"></a>Cambios realizados por la preparación del bosque en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-30_

En esta sección se describen la configuración global y los objetos, así como el servicio universal y los grupos de administración creados por el paso de preparación del bosque.

<div>

## <a name="active-directory-global-settings-and-objects"></a>Objetos y configuración global de Active Directory

Si almacena la configuración global en el contenedor de configuración (como es el caso de todas las implementaciones de Lync Server 2013 nuevas), la preparación del bosque usa el contenedor servicios existentes y agrega un objeto\\de **servicio RTC** en el objeto de servicios de configuración. En el objeto de servicio RTC, la preparación del bosque agrega un objeto de **configuración global** de tipo MsRTCSIP-GlobalContainer. El objeto configuración global contiene toda la configuración que se aplica a la implementación de Lync Server. Si almacena la configuración global en el contenedor del sistema, la preparación del bosque usa un contenedor de Microsoft en el contenedor del sistema del dominio raíz y un\\objeto de servicio RTC bajo el objeto Microsoft del sistema.

La preparación del bosque también agrega un nuevo objeto **msRTCSIP-Domain** para el dominio raíz en el que se ejecuta el procedimiento.

</div>

<div>

## <a name="active-directory-universal-service-and-administration-groups"></a>Servicio universal de Active Directory y grupos de administración

La preparación del bosque crea grupos universales basados en el dominio que especifique y agrega entradas de control de acceso (ACE) para estos grupos. Este paso crea los grupos universales en los contenedores de usuario del dominio que especifique.

Los grupos universales permiten a los administradores acceder y administrar la configuración y los servicios globales. La preparación del bosque agrega los siguientes tipos de grupos universales:

  - **Grupos administrativos estos**   grupos definen roles de administrador para una red de Lync Server.

  - **Grupos de infraestructura**   estos grupos proporcionan permiso para acceder a áreas específicas de la infraestructura de Lync Server. Funcionan como componentes de grupos administrativos. No debe modificar estos grupos ni agregar usuarios directamente.

  - **Grupos de servicio**   estos grupos son cuentas de servicio necesarias para acceder a varios servicios de Lync Server.

En la tabla siguiente se describen los grupos administrativos.

### <a name="administrative-groups-created-during-forest-preparation"></a>Grupos administrativos creados durante la preparación del bosque

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
<td><p>Permite a los miembros administrar la configuración del servidor y del grupo, incluidos los roles de servidor, la configuración global y los usuarios.</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Permite a los miembros administrar la configuración de usuario y mover los usuarios de un servidor o grupo a otro.</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalReadOnlyAdmins</p></td>
<td><p>Permite que los miembros lean la configuración del servidor, del grupo y del usuario.</p></td>
</tr>
</tbody>
</table>


En la tabla siguiente se describen los grupos de infraestructura.

### <a name="infrastructure-groups-created-during-forest-preparation"></a>Grupos de infraestructura creados durante la preparación del bosque

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
<td><p>Concede acceso de solo lectura a objetos de configuración global para Lync Server.</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Concede acceso de solo lectura a la configuración de usuario de Lync Server.</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>Concede acceso de solo lectura a la configuración de Lync Server. Este grupo no tiene acceso a la configuración del nivel de grupo, solo a la configuración específica de un servidor individual.</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalSBATechnicians</p></td>
<td><p>Concede acceso de solo lectura a la configuración de Lync Server y se coloca en el grupo de administradores locales de las aplicaciones de las sucursales que son supervivientes durante la instalación.</p></td>
</tr>
</tbody>
</table>


En la siguiente tabla se describen los grupos de servicios.

### <a name="service-groups-created-during-forest-preparation"></a>Grupos de servicio creados durante la preparación del bosque

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
<td><p>Incluye cuentas de servicio que se usan para ejecutar servidores front-end y servidores Standard Edition. Este grupo permite que los servidores tengan acceso de lectura y escritura a la configuración global de Lync Server y a los objetos de usuario de Active Directory.</p></td>
</tr>
<tr class="even">
<td><p>RTCComponentUniversalServices</p></td>
<td><p>Incluye cuentas de servicio que se usan para ejecutar servidores de conferencia A/V, servicios Web, servidor de mediación, servidor de archivado y servidor de supervisión.</p></td>
</tr>
<tr class="odd">
<td><p>RTCProxyUniversalServices</p></td>
<td><p>Incluye cuentas de servicio que se usan para ejecutar servidores perimetrales de Lync Server.</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalConfigReplicator</p></td>
<td><p>Incluye servidores que pueden participar en la replicación del almacén central de administración de Lync Server.</p></td>
</tr>
<tr class="odd">
<td><p>RTCSBAUniversalServices</p></td>
<td><p>Concede acceso de solo lectura a la configuración del servidor de Lync, pero permite la configuración de la instalación de un servidor de sucursal y una implementación de dispositivos de rama supervivientes.</p></td>
</tr>
</tbody>
</table>


La preparación del bosque, a continuación, agrega grupos de servicio y administración a los grupos de infraestructura adecuados, de la siguiente manera:

  - RTCUniversalServerAdmins se agrega a RTCUniversalGlobalReadOnlyGroup, RTCUniversalGlobalWriteGroup, RTCUniversalServerReadOnlyGroup y RTCUniversalUserReadOnlyGroup.

  - RTCUniversalUserAdmins se agrega como miembro de RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup y RTCUniversalUserReadOnlyGroup.

  - RTCHSUniversalServices, RTCComponentUniversalServices y RTCUniversalReadOnlyAdmins se agregan como miembros de RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup y RTCUniversalUserReadOnlyGroup.

La preparación del bosque también crea los siguientes grupos de control de acceso basado en roles (RBAC):

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

  - AdministradorGrupoRespuestaCs

Para obtener más información sobre los roles RBAC y las tareas permitidas para cada uno, vea [planear el control de acceso basado en roles en Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) en la documentación de planeación.

La preparación del bosque crea entradas de acceso privadas y públicas. Crea ACE privadas en el contenedor de configuración global usado por Lync Server. Este contenedor solo es utilizado por Lync Server y se encuentra en el contenedor configuración o en el contenedor del sistema en el dominio raíz, según dónde se almacene la configuración global. Las ACE públicas creadas por la preparación del bosque se enumeran en la tabla siguiente.

### <a name="public-aces-created-by-forest-preparation"></a>ACE públicas creadas por la preparación del bosque

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>ENTRADA</th>
<th>RTCUniversalGlobalReadOnlyGroup</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Leer el contenedor del sistema del dominio raíz (no heredado)<strong>*</strong></p></td>
<td><p>X</p></td>
</tr>
<tr class="even">
<td><p>Contenedor DisplaySpecifiers de lectura de la configuración (no heredado)</p></td>
<td><p>X</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <STRONG>*</STRONG>Las ACE que no se heredan no conceden acceso a objetos secundarios en estos contenedores. Las ACE que se heredan otorgan acceso a objetos secundarios en estos contenedores.



</div>

En el contenedor configuración, en el contexto de nomenclatura de configuración, la preparación del bosque realiza las siguientes tareas:

  - Agrega una entrada **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** para la página de **propiedades RTC** en los atributos adminContextMenu y adminPropertyPages del especificador de presentación de idioma para usuarios, contactos y InetOrgPersons (por ejemplo, CN = user-Display, CN = 409, CN = DisplaySpecifiers).

  - Agrega un objeto **RTCPropertySet** de tipo **controlAccessRight** bajo **Extended-Rights** que se aplica a las clases User y contact.

  - Agrega un objeto **RTCUserSearchPropertySet** de tipo **controlAccessRight** bajo **Extended-Rights** que se aplica a las clases User, Contact, ou y DomainDNS.

  - Agrega **msRTCSIP-PrimaryUserAddress** en el atributo **extracolumns** del especificador de pantalla de cada idioma de unidad organizativa (OU) (por ejemplo, CN = ORGANIZATIONALUNIT-display, CN = 409, CN = DisplaySpecifiers) y copia los valores del atributo **extracolumns** de la presentación predeterminada (por ejemplo, CN = default-display, CN = 409, CN = DisplaySpecifiers).

  - Agrega **atributos msRTCSIP-PrimaryUserAddress**, **msRTCSIP-PrimaryHomeServer**y **msRTCSIP-UserEnabled** al atributo **attributeDisplayNames** de cada especificador de visualización de idioma para los objetos users, Contacts e INETORGPERSON (por ejemplo, en Inglés: CN = user-Display, CN = 409, CN = DisplaySpecifiers).

</div>

</div>

<span> </span>

</div>

</div>

</div>

