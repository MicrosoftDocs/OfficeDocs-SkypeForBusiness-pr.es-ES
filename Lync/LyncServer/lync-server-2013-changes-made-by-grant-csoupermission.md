---
title: 'Lync Server 2013: cambios realizados por Grant-CsOUPermission'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes made by Grant-CsOUPermission
ms:assetid: d744d352-1ad9-4447-8e2b-28e768d2ed1b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205310(v=OCS.15)
ms:contentKeyID: 48185564
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9056753e57f57b131a05d13eb2862611ba34f966
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729940"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-csoupermission-in-lync-server-2013"></a>Cambios realizados por Grant-CsOUPermission en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-06-20_

Para delegar la administración de Lync Server 2013, puede Agregar permisos a unidades organizativas (OU) especificadas de modo que los miembros de los grupos RTC universales creados por la preparación del bosque puedan tener acceso a las unidades organizativas sin ser miembros del grupo administradores de dominio.

El cmdlet **Grant-CsOuPermission** otorga permisos a objetos en la ou especificada, tal como se especifica en las tablas siguientes.

<div>

## <a name="granting-permission-for-user-objects"></a>Conceder permisos a los objetos de usuario

Al ejecutar el cmdlet **Grant-CsOuPermission** para objetos de usuario en una unidad organizativa, se conceden permisos a los grupos como se muestra en la tabla siguiente.

### <a name="permissions-granted-for-user-objects"></a>Permisos otorgados para objetos de usuario

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Mesa</th>
<th>Permiso</th>
<th>Se aplica a</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>Replicar cambios de directorio</p></td>
<td><p>Solo este objeto</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>Contenido de la lista</p>
<p>Leer todas las propiedades</p>
<p>Permisos de lectura</p></td>
<td><p>Solo este objeto</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Contenido de la lista</p>
<p>Leer todas las propiedades</p>
<p>Permisos de lectura</p></td>
<td><p>Solo este objeto</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Leer RTCUserSearchPropertySet</p>
<p>Leer RTCUserProvisioningPropertySet</p>
<p>Leer RTCPropertySet</p>
<p>Leer información pública</p>
<p>Leer información general</p>
<p>Leer las restricciones de la cuenta de usuario</p></td>
<td><p>Objetos de usuario descendientes</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Escribir RTCUserSearchPropertySet</p>
<p>Escribir msExchUCVoiceMailSettings</p>
<p>Escribir RTCUserProvisioningPropertySet</p>
<p>Escribir RTCPropertySet</p>
<p>Escribir proxyAddresses</p></td>
<td><p>Objetos de usuario descendientes</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-computer-objects"></a>Concesión de permisos para objetos de equipo

Al ejecutar el cmdlet **Grant-CsOuPermission** para objetos de equipo en una unidad organizativa, se conceden permisos a los grupos como se muestra en la tabla siguiente.

### <a name="permissions-granted-for-computer-objects"></a>Permisos otorgados para objetos de equipo

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Mesa</th>
<th>Permiso</th>
<th>Se aplica a</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>Replicar cambios de directorio</p></td>
<td><p>Solo este objeto</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>Contenido de la lista</p>
<p>Leer todas las propiedades</p>
<p>Permisos de lectura</p></td>
<td><p>Solo este objeto</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Contenido de la lista</p>
<p>Leer todas las propiedades</p>
<p>Permisos de lectura</p></td>
<td><p>Solo este objeto</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Leer información pública</p>
<p>Lectura validada: nombre-DNS-host</p></td>
<td><p>Objetos de equipo descendientes</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Leer información pública</p>
<p>Lectura validada: nombre-DNS-host</p></td>
<td><p>Objetos de equipo descendientes</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-contact-or-appcontact-objects"></a>Concesión de permisos para objetos de contacto o de AppContact

Al ejecutar el cmdlet **Grant-CsOuPermission** para objetos de contacto o objetos de AppContact en una unidad organizativa, se conceden permisos a los grupos como se muestra en la tabla siguiente.

### <a name="permissions-granted-for-contact-or-appcontact-objects"></a>Permisos concedidos para objetos de contacto o AppContact

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Mesa</th>
<th>Permiso</th>
<th>Se aplica a</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>Replicar cambios de directorio</p></td>
<td><p>Solo este objeto</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>Contenido de la lista</p>
<p>Leer todas las propiedades</p>
<p>Permisos de lectura</p></td>
<td><p>Solo este objeto</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Contenido de la lista</p>
<p>Leer todas las propiedades</p>
<p>Permisos de lectura</p></td>
<td><p>Solo este objeto</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Leer RTCUserSearchPropertySet</p>
<p>Leer RTCUserProvisioningPropertySet</p>
<p>Leer RTCPropertySet</p>
<p>Leer información pública</p>
<p>Leer información general</p>
<p>Leer información personal</p>
<p>Leer las restricciones de la cuenta de usuario</p></td>
<td><p>Objetos de contacto descendiente</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Escribir RTCUserSearchPropertySet</p>
<p>Escribir otherIpPhone</p>
<p>Escribir displayName</p>
<p>Escribir Descripción</p>
<p>Escribir telephoneNumber</p>
<p>Escribir msExchUCVoiceMailSettings</p>
<p>Escribir RTCUserProvisioningPropertySet</p>
<p>Escribir RTCPropertySet</p>
<p>Escribir proxyAddresses</p></td>
<td><p>Objetos de contacto descendiente</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-device-objects"></a>Conceder permisos a objetos de dispositivo

Al ejecutar el cmdlet **Grant-CsOuPermission** en una unidad organizativa, se conceden permisos a los grupos, como se muestra en la tabla siguiente.

### <a name="permissions-granted-for-device-objects"></a>Permisos concedidos para objetos de dispositivo

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Mesa</th>
<th>Permiso</th>
<th>Se aplica a</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>Replicar cambios de directorio</p></td>
<td><p>Solo este objeto</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>Contenido de la lista</p>
<p>Leer todas las propiedades</p>
<p>Permisos de lectura</p></td>
<td><p>Solo este objeto</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Contenido de la lista</p>
<p>Leer todas las propiedades</p>
<p>Permisos de lectura</p></td>
<td><p>Solo este objeto</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Leer RTCUserSearchPropertySet</p>
<p>Leer RTCUserProvisioningPropertySet</p>
<p>Leer RTCPropertySet</p>
<p>Leer información pública</p>
<p>Leer información personal</p>
<p>Leer información general</p>
<p>Leer las restricciones de la cuenta de usuario</p></td>
<td><p>Objetos de contacto descendiente</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Crear elemento secundario</p>
<p>Eliminar hijo</p>
<p>Eliminar árbol</p></td>
<td><p>Con</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Escribir displayName</p>
<p>Escribir Descripción</p>
<p>Escribir telephoneNumber</p></td>
<td><p>Objetos de usuario descendientes</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Escribir RTCUserSearchPropertySet</p>
<p>Escribir otherIpPhone</p>
<p>Escribir displayName</p>
<p>Escribir Descripción</p>
<p>Escribir telephoneNumber</p>
<p>Escribir msExchUCVoiceMailSettings</p>
<p>Escribir RTCUserProvisioningPropertySet</p>
<p>Escribir RTCPropertySet</p>
<p>Escribir proxyAddresses</p></td>
<td><p>Objetos de contacto descendiente</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-inetorgperson-objects"></a>Conceder permisos a objetos InetOrgPerson

Al ejecutar el cmdlet **Grant-CsOuPermission** para los objetos InetOrgPerson de una unidad organizativa, se conceden permisos a los grupos como se muestra en la tabla siguiente.

### <a name="permissions-granted-for-inetorgperson-objects"></a>Permisos otorgados a los objetos InetOrgPerson

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Mesa</th>
<th>Permiso</th>
<th>Se aplica a</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>Replicar cambios de directorio</p></td>
<td><p>Solo este objeto</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>Contenido de la lista</p>
<p>Leer todas las propiedades</p>
<p>Permisos de lectura</p></td>
<td><p>Solo este objeto</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Contenido de la lista</p>
<p>Leer todas las propiedades</p>
<p>Permisos de lectura</p></td>
<td><p>Solo este objeto</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Leer RTCUserSearchPropertySet</p>
<p>Leer RTCUserProvisioningPropertySet</p>
<p>Leer RTCPropertySet</p>
<p>Leer información personal</p>
<p>Leer información pública</p>
<p>Leer información general</p>
<p>Leer las restricciones de la cuenta de usuario</p></td>
<td><p>Objetos descendientes de inetOrgPerson</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Escribir RTCUserSearchPropertySet</p>
<p>Escribir RTCUserProvisioningPropertySet</p>
<p>Escribir RTCPropertySet</p>
<p>Escribir proxyAddresses</p></td>
<td><p>Objetos descendientes de inetOrgPerson</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

