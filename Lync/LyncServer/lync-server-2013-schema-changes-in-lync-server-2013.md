---
title: Cambios en el esquema de Lync Server 2013
TOCTitle: Cambios en el esquema de Lync Server 2013
ms:assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398944(v=OCS.15)
ms:contentKeyID: 48276830
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Cambios en el esquema de Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

Antes de implementar y usar Lync Server 2013, prepare Servicios de dominio de Active Directory con la extensión del esquema. Las extensiones de esquema agregan las clases y los atributos que necesita Lync Server 2013.

Lync Server 2013 necesita varios atributos y clases nuevos y modifica algunos de los ya existentes. Además, la mayoría de la información de configuración de Lync Server 2013 se almacena en el Almacén de administración central, en lugar de en AD DS como sucedía en versiones anteriores. La información siguiente continúa almacenándose en AD DS en Lync Server 2013:

  - **Extensiones de esquema**:
    
      - Extensiones de objetos de usuario
    
      - Extensiones para las clases de Office Communications Server 2007 y de Office Communications Server 2007 R2 con el fin de mantener la compatibilidad con versiones anteriores.

<!-- end list -->

  - **Datos** (almacenados en el esquema extendido de Lync Server y en las clases de esquema existentes):
    
      - Identificador uniforme de recursos (URI) de SIP del usuario y otros parámetros de usuario
    
      - Objetos de contacto para aplicaciones como Grupo de respuesta y Operador de conferencia
    
      - Un puntero al Almacén de administración central
    
      - Cuenta de autenticación Kerberos (un objeto de equipo opcional)

En este tema se describen los cambios en el esquema de Active Directory que Lync Server 2013 necesita. No obstante, no se describen los cambios en el esquema introducidos en versiones anteriores de Office Communications Server. Para obtener una lista de clases y sus descripciones, vea [Clases de esquema y descripciones de Lync Server 2013](lync-server-2013-schema-classes-and-descriptions.md). Para obtener una lista de atributos y sus descripciones, vea [Atributos de esquema y descripciones de Lync Server 2013](lync-server-2013-schema-attributes-and-descriptions.md). Para obtener una lista de clases con los atributos que pueden contener, vea [Atributos de esquema por clase de Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).

El prefijo msRTCSIP identifica clases y atributos que son específicos de Lync Server.

## Nuevos atributos de Active Directory

En la tabla siguiente se describen los atributos de Active Directory que agrega Lync Server 2013.

### Atributos agregados por Lync Server 2013

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Atributo</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>msExchUserHoldPolicies</p></td>
<td><p>Este atributo de varios valores contiene los identificadores de las directivas de retención que se aplican al usuario. Estas directivas conservan los elementos de buzón de correo del usuario mientras dure la retención. Este atributo se comparte con Exchange 2013.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UserRoutingGroupId</p></td>
<td><p>Este es el identificador de grupo de enrutamiento SIP. Los usuarios del mismo grupo se registrarán en el mismo servidor front-end.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MirrorBackEndServer</p></td>
<td><p>Este atributo se usa para almacenar el reflejo del back-end del servidor SQL que el Grupo de servidores front-endusa.</p></td>
</tr>
</tbody>
</table>


## Clases de Active Directory modificadas

En la tabla siguiente se describen las clases de Active Directory que modifica Lync Server 2013.

### Clases modificadas por Lync Server 2013

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Clase</th>
<th>Cambio</th>
<th>Clase o atributo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>User</p></td>
<td><p>agregar: mayContain</p>
<p>agregar: mayContain</p></td>
<td><p>ProxyAddresses</p>
<p>msRTCSIP-UserRoutingGroupId</p></td>
</tr>
<tr class="even">
<td><p>Contact</p></td>
<td><p>agregar: mayContain</p>
<p>agregar: mayContain</p></td>
<td><p>ProxyAddresses</p>
<p>msRTCSIP-UserRoutingGroupId</p></td>
</tr>
<tr class="odd">
<td><p>Mail-Recipient</p></td>
<td><p>agregar: mayContain</p></td>
<td><p>msExchUserHoldPolicies</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-GlobalTopologySetting</p></td>
<td><p>agregar: mayContain</p></td>
<td><p>msRTCSIP-MirrorBackEndServer</p></td>
</tr>
</tbody>
</table>

