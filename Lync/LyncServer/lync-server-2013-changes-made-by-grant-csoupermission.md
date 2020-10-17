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
ms.openlocfilehash: 0ff916c0b4e284f9c6ce4d5dbaf9c2e196ed4bc6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529437"
---
# <a name="changes-made-by-grant-csoupermission-in-lync-server-2013"></a>Cambios realizados por Grant-CsOUPermission en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-06-20_

Para delegar la administración de Lync Server 2013, puede Agregar permisos a unidades organizativas especificadas para que los miembros de los grupos de RTC universales creados por la preparación del bosque puedan tener acceso a las unidades organizativas sin ser miembros del grupo administradores del dominio.

El cmdlet **Grant-CsOuPermission** concede permisos a objetos en la unidad organizativa especificada como se indica en las tablas siguientes.

<div>

## <a name="granting-permission-for-user-objects"></a>Concesión de permisos para objetos de usuario

Al ejecutar el cmdlet **Grant-CsOuPermission** para objetos de usuario en una unidad organizativa, se conceden permisos a los grupos como se muestra en la tabla siguiente.

### <a name="permissions-granted-for-user-objects"></a>Permisos concedidos para objetos de usuario

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Grupo</th>
<th>Permiso</th>
<th>Se aplica a</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>Replicar los cambios de directorio</p></td>
<td><p>Solo este objeto</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>Contenidos de la lista</p>
<p>Leer todas las propiedades</p>
<p>Leer permisos</p></td>
<td><p>Solo este objeto</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Contenidos de la lista</p>
<p>Leer todas las propiedades</p>
<p>Leer permisos</p></td>
<td><p>Solo este objeto</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>RTCUserSearchPropertySet de lectura</p>
<p>RTCUserProvisioningPropertySet de lectura</p>
<p>RTCPropertySet de lectura</p>
<p>Public-Information de lectura</p>
<p>General-Information de lectura</p>
<p>User-Account-Restrictions de lectura</p></td>
<td><p>Objetos de usuario descendientes</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>RTCUserSearchPropertySet de escritura</p>
<p>msExchUCVoiceMailSettings de escritura</p>
<p>RTCUserProvisioningPropertySet de escritura</p>
<p>RTCPropertySet de escritura</p>
<p>proxyAddresses de escritura</p></td>
<td><p>Objetos de usuario descendientes</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-computer-objects"></a>Concesión de permisos para objetos de equipo

Al ejecutar el cmdlet **Grant-CsOuPermission** para objetos de equipo en una unidad organizativa, se conceden permisos a los grupos como se muestra en la tabla siguiente

### <a name="permissions-granted-for-computer-objects"></a>Permisos concedidos para objetos de equipo

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Grupo</th>
<th>Permiso</th>
<th>Se aplica a</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>Replicar los cambios de directorio</p></td>
<td><p>Solo este objeto</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>Contenidos de la lista</p>
<p>Leer todas las propiedades</p>
<p>Leer permisos</p></td>
<td><p>Solo este objeto</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Contenidos de la lista</p>
<p>Leer todas las propiedades</p>
<p>Leer permisos</p></td>
<td><p>Solo este objeto</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Public-Information de lectura</p>
<p>Validated-DNS-Host-Name de lectura</p></td>
<td><p>Objetos de equipo descendientes</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Public-Information de lectura</p>
<p>Validated-DNS-Host-Name de lectura</p></td>
<td><p>Objetos de equipo descendientes</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-contact-or-appcontact-objects"></a>Concesión de permisos para objetos Contact o AppContact

Al ejecutar el cmdlet **Grant-CsOuPermission** para objetos Contact u objetos AppContact en una unidad organizativa, se conceden permisos a los grupos como se muestra en la tabla siguiente.

### <a name="permissions-granted-for-contact-or-appcontact-objects"></a>Permisos concedidos para objetos Contact o AppContact

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Grupo</th>
<th>Permiso</th>
<th>Se aplica a</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>Replicar los cambios de directorio</p></td>
<td><p>Solo este objeto</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>Contenidos de la lista</p>
<p>Leer todas las propiedades</p>
<p>Leer permisos</p></td>
<td><p>Solo este objeto</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Contenidos de la lista</p>
<p>Leer todas las propiedades</p>
<p>Leer permisos</p></td>
<td><p>Solo este objeto</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>RTCUserSearchPropertySet de lectura</p>
<p>RTCUserProvisioningPropertySet de lectura</p>
<p>RTCPropertySet de lectura</p>
<p>Public-Information de lectura</p>
<p>General-Information de lectura</p>
<p>Personal-Information de lectura</p>
<p>User-Account-Restrictions de lectura</p></td>
<td><p>Objetos de contacto descendientes</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>RTCUserSearchPropertySet de escritura</p>
<p>otherIpPhone de escritura</p>
<p>displayName de escritura</p>
<p>description de escritura</p>
<p>telephoneNumber de escritura</p>
<p>msExchUCVoiceMailSettings de escritura</p>
<p>RTCUserProvisioningPropertySet de escritura</p>
<p>RTCPropertySet de escritura</p>
<p>proxyAddresses de escritura</p></td>
<td><p>Objetos de contacto descendientes</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-device-objects"></a>Concesión de permisos para objetos de dispositivo

Al ejecutar el cmdlet **Grant-CsOuPermission** para objetos de dispositivo en una unidad organizativa, se conceden permisos a los grupos como se muestra en la tabla siguiente.

### <a name="permissions-granted-for-device-objects"></a>Permisos concedidos para objetos de dispositivo

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Grupo</th>
<th>Permiso</th>
<th>Se aplica a</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>Replicar los cambios de directorio</p></td>
<td><p>Solo este objeto</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>Contenidos de la lista</p>
<p>Leer todas las propiedades</p>
<p>Leer permisos</p></td>
<td><p>Solo este objeto</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Contenidos de la lista</p>
<p>Leer todas las propiedades</p>
<p>Leer permisos</p></td>
<td><p>Solo este objeto</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>RTCUserSearchPropertySet de lectura</p>
<p>RTCUserProvisioningPropertySet de lectura</p>
<p>RTCPropertySet de lectura</p>
<p>Public-Information de lectura</p>
<p>Personal-Information de lectura</p>
<p>General-Information de lectura</p>
<p>User-Account-Restrictions de lectura</p></td>
<td><p>Objetos de contacto descendientes</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Crear secundario</p>
<p>Eliminar secundario</p>
<p>Eliminar árbol</p></td>
<td><p>Contacto</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>displayName de escritura</p>
<p>description de escritura</p>
<p>telephoneNumber de escritura</p></td>
<td><p>Objetos de usuario descendientes</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>RTCUserSearchPropertySet de escritura</p>
<p>otherIpPhone de escritura</p>
<p>displayName de escritura</p>
<p>description de escritura</p>
<p>telephoneNumber de escritura</p>
<p>msExchUCVoiceMailSettings de escritura</p>
<p>RTCUserProvisioningPropertySet de escritura</p>
<p>RTCPropertySet de escritura</p>
<p>proxyAddresses de escritura</p></td>
<td><p>Objetos de contacto descendientes</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-inetorgperson-objects"></a>Concesión de permisos para objetos InetOrgPerson

Al ejecutar el cmdlet **Grant-CsOuPermission** para objetos InetOrgPerson en una unidad organizativa, se conceden permisos a los grupos como se muestra en la tabla siguiente.

### <a name="permissions-granted-for-inetorgperson-objects"></a>Permisos concedidos para objetos InetOrgPerson

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Grupo</th>
<th>Permiso</th>
<th>Se aplica a</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>Replicar los cambios de directorio</p></td>
<td><p>Solo este objeto</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>Contenidos de la lista</p>
<p>Leer todas las propiedades</p>
<p>Leer permisos</p></td>
<td><p>Solo este objeto</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Contenidos de la lista</p>
<p>Leer todas las propiedades</p>
<p>Leer permisos</p></td>
<td><p>Solo este objeto</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>RTCUserSearchPropertySet de lectura</p>
<p>RTCUserProvisioningPropertySet de lectura</p>
<p>RTCPropertySet de lectura</p>
<p>Personal-Information de lectura</p>
<p>Public-Information de lectura</p>
<p>General-Information de lectura</p>
<p>User-Account-Restrictions de lectura</p></td>
<td><p>Objetos inetOrgPerson descendientes</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>RTCUserSearchPropertySet de escritura</p>
<p>RTCUserProvisioningPropertySet de escritura</p>
<p>RTCPropertySet de escritura</p>
<p>proxyAddresses de escritura</p></td>
<td><p>Objetos inetOrgPerson descendientes</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

