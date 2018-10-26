---
title: Cambios realizados por Grant-CsSetupPermission en Lync Server 2013
TOCTitle: Cambios realizados por Grant-CsSetupPermission en Lync Server 2013
ms:assetid: c5801f48-14e3-4fdd-8f14-d52e7af07a57
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205250(v=OCS.15)
ms:contentKeyID: 48276612
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Cambios realizados por Grant-CsSetupPermission en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

Para delegar la instalación, puede otorgar permisos al grupo universal RTCUniversalServerAdmins para una unidad organizativa (OU) específica de Active Directory, lo que permite a los miembros del grupo RTCUniversalServerAdmins de esta unidad organizativa instalar Lync Server 2013 en el dominio específico sin ser miembros del grupo de administradores de dominio.

El cmdlet **Grant-CsSetupPermission** otorga los permisos del grupo RTCUniversalServerAdmins en una unidad organizativa, como se especifica en la siguiente tabla:

### Permisos otorgados a los objetos en la unidad organizativa

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Los permisos se aplican a:</th>
<th>Los permisos otorgados son:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCUniversalServerAdmins</p></td>
<td><p>Acceso especial:</p>
<ul>
<li><p>Leer servicePrincipalName</p></li>
<li><p>Escribir servicePrincipalName</p></li>
<li><p>Eliminar árbol</p></li>
<li><p>Cambios de directorio de replicación</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Objetos serviceConnectionPoint descendientes</p></td>
<td><p>Acceso especial:</p>
<ul>
<li><p>Leer permisos</p></li>
<li><p>Escribir permisos</p></li>
<li><p>Crear elemento secundario</p></li>
<li><p>Eliminar elemento secundario</p></li>
<li><p>Mostrar contenido</p></li>
<li><p>Escribir propiedad</p></li>
<li><p>Leer propiedad</p></li>
<li><p>Eliminar árbol</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Objetos msRTCSIP-Server descendientes</p></td>
<td><p>Acceso especial:</p>
<ul>
<li><p>Escribir propiedad</p></li>
<li><p>Leer propiedad</p></li>
<li><p>Eliminar árbol</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Objetos msRTCSIP-WebComponents descendientes</p></td>
<td><p>Acceso especial:</p>
<ul>
<li><p>Escribir propiedad</p></li>
<li><p>Leer propiedad</p></li>
<li><p>Eliminar árbol</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Objetos msRTCSIP-MCU descendientes</p></td>
<td><p>Acceso especial:</p>
<ul>
<li><p>Escribir propiedad</p></li>
<li><p>Leer propiedad</p></li>
<li><p>Eliminar árbol</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Objetos msRTCSIP-MediationServer descendientes</p></td>
<td><p>Acceso especial:</p>
<ul>
<li><p>Escribir propiedad</p></li>
<li><p>Leer propiedad</p></li>
<li><p>Eliminar árbol</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Objetos msRTCSIP-ApplicationServer descendientes</p></td>
<td><p>Acceso especial:</p>
<ul>
<li><p>Escribir propiedad</p></li>
<li><p>Leer propiedad</p></li>
<li><p>Eliminar árbol</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Objetos msRTCSIP-ConnectionPoint descendientes</p></td>
<td><p>Acceso especial:</p>
<ul>
<li><p>Escribir propiedad</p></li>
<li><p>Leer propiedad</p></li>
<li><p>Eliminar árbol</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Objetos de equipo descendientes</p></td>
<td><p>Acceso especial para serviceConnectionPoint:</p>
<ul>
<li><p>Crear objetos secundarios</p></li>
<li><p>Eliminar objetos secundarios</p></li>
<li><p>Eliminar árbol</p></li>
</ul>
<p>Acceso especial a la información pública:</p>
<ul>
<li><p>Leer propiedad</p></li>
</ul>
<p>Acceso especial para el nombre de host DNS:</p>
<ul>
<li><p>Leer propiedad</p></li>
</ul></td>
</tr>
</tbody>
</table>

