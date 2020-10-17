---
title: 'Lync Server 2013: cambios de esquema en Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Schema changes in Lync Server 2013
ms:assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398944(v=OCS.15)
ms:contentKeyID: 48185575
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c3733eee90fb1ea0bb3e0a67be88243dee56aa7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510787"
---
# <a name="schema-changes-in-lync-server-2013"></a>Cambios de esquema en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-18_

Antes de implementar y usar Lync Server 2013, debe preparar los servicios de dominio de Active Directory extendiendo el esquema. Las extensiones de esquema agregan las clases y atributos que necesita Lync Server 2013.

Lync Server 2013 requiere varias clases y atributos nuevos y modifica algunas clases y atributos existentes. Además, la información de configuración de Lync Server 2013 se almacena en el almacén de administración central, en lugar de en AD DS como en versiones anteriores. La siguiente información todavía se almacena en AD DS en Lync Server 2013:

  - **Extensiones de esquema**:
    
      - Extensiones de objetos de usuario
    
      - Extensiones para las clases de Office Communications Server 2007 y Office Communications Server 2007 R2 para mantener la compatibilidad con versiones anteriores compatibles

<!-- end list -->

  - **Datos** (almacenados en el esquema extendido de Lync Server y en las clases de esquema existentes):
    
      - Identificador uniforme de recursos (URI) de SIP del usuario y otros parámetros de usuario
    
      - Objetos de contacto para aplicaciones como Grupo de respuesta y Operador de conferencia
    
      - Una referencia al almacén de administración central
    
      - Cuenta de autenticación Kerberos (un objeto de equipo opcional)

En este tema se describen los cambios en el esquema de Active Directory que necesita Lync Server 2013. No se describen los cambios de esquema que se introdujeron en versiones anteriores de Office Communications Server. Para obtener una lista de las clases y sus descripciones, vea [clases de esquema y descripciones en Lync Server 2013](lync-server-2013-schema-classes-and-descriptions.md). Para obtener una lista de atributos y sus descripciones, consulte [atributos y descripciones del esquema en Lync Server 2013](lync-server-2013-schema-attributes-and-descriptions.md). Para obtener una lista de las clases con los atributos que pueden contener, consulte [atributos de esquema por clase en Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).

El prefijo msRTCSIP identifica clases y atributos que son específicos de Lync Server.

<div>

## <a name="new-active-directory-attributes"></a>Nuevos atributos de Active Directory

En la tabla siguiente se describen los atributos de Active Directory que se agregan con Lync Server 2013.

### <a name="attributes-added-by-lync-server-2013"></a>Atributos agregados por Lync Server 2013

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Atributo</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>msExchUserHoldPolicies</p></td>
<td><p>Este atributo de varios valores contiene los identificadores de las directivas de retención que se aplican al usuario. Las directivas de retención conservan los elementos del buzón del usuario durante toda la retención. Este atributo se comparte con Exchange 2013.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UserRoutingGroupId</p></td>
<td><p>Este es el identificador de grupo de enrutamiento SIP. Los usuarios del mismo grupo se registrarán en el mismo servidor front-end.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MirrorBackEndServer</p></td>
<td><p>Este atributo se usa para almacenar el back-end de SQL Server reflejado usado por el grupo de servidores front-end.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="modified-active-directory-classes"></a>Clases de Active Directory modificadas

En la tabla siguiente se describen las clases de Active Directory que se modifican en Lync Server 2013.

### <a name="classes-modified-by-lync-server-2013"></a>Clases modificadas por Lync Server 2013

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Class</th>
<th>Cambio</th>
<th>Clase o atributo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Usuario</p></td>
<td><p>agregar: mayContain</p>
<p>agregar: mayContain</p></td>
<td><p>ProxyAddresses</p>
<p>msRTCSIP-UserRoutingGroupId</p></td>
</tr>
<tr class="even">
<td><p>Contacto</p></td>
<td><p>agregar: mayContain</p>
<p>agregar: mayContain</p></td>
<td><p>ProxyAddresses</p>
<p>msRTCSIP-UserRoutingGroupId</p></td>
</tr>
<tr class="odd">
<td><p>Mail-Recipient</p></td>
<td><p>add: mayContain</p></td>
<td><p>msExchUserHoldPolicies</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-GlobalTopologySetting</p></td>
<td><p>agregar: mayContain</p></td>
<td><p>msRTCSIP-MirrorBackEndServer</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

