---
title: 'Lync Server 2013: Requisitos de Internet Information Services (IIS)'
TOCTitle: Requisitos de Internet Information Services (IIS)
ms:assetid: 4f57a605-a8a9-4c5a-9a18-05ecb3d9ab6b
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398321(v=OCS.15)
ms:contentKeyID: 48275250
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Requisitos de Internet Information Services (IIS) en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

Varios componentes de Lync Server 2013 precisan Servicios de Internet Information Server (IIS). En este tema se describen las características IIS específicas necesarias para admitir Lync Server. En los temas de esta sección se describen los requisitos de componentes específicos para IIS.

Al habilitar el rol servidor web (IIS) en Windows Server 2008, se instalan de forma predeterminada varios servicios de rol. En la siguiente tabla se describen los servicios adicionales de rol que se deben instalar al habilitar el rol servidor Web (IIS) en Windows Server 2008.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Servicio de rol</th>
<th>Característica</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Características HTTP comunes</p></td>
<td><p>Redirección HTTP</p></td>
</tr>
<tr class="even">
<td><p>Desarrollo de aplicaciones</p></td>
<td><p>ASP.NET</p></td>
</tr>
<tr class="odd">
<td><p>Desarrollo de aplicaciones</p></td>
<td><p>Extensibilidad de .NET</p></td>
</tr>
<tr class="even">
<td><p>Desarrollo de aplicaciones</p></td>
<td><p>Extensiones ISAPI</p></td>
</tr>
<tr class="odd">
<td><p>Desarrollo de aplicaciones</p></td>
<td><p>Filtros ISAPI</p></td>
</tr>
<tr class="even">
<td><p>Estado y diagnóstico</p></td>
<td><p>Herramientas de registro</p></td>
</tr>
<tr class="odd">
<td><p>Estado y diagnóstico</p></td>
<td><p>Seguimiento</p></td>
</tr>
<tr class="even">
<td><p>Seguridad</p></td>
<td><p>Autenticación básica</p></td>
</tr>
<tr class="odd">
<td><p>Seguridad</p></td>
<td><p>Autenticación de Windows</p></td>
</tr>
<tr class="even">
<td><p>Herramientas de administración</p></td>
<td><p>Scripts y herramientas de administración de IIS</p></td>
</tr>
<tr class="odd">
<td><p>Herramientas de administración</p></td>
<td><p>Compatibilidad con la administración de IIS 6</p></td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr class="header">
<th><img src="images/Gg399038.security(OCS.15).gif" title="security" alt="security" />Seguridad Nota:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Si usa IIS 7.0 con un sistema operativo Windows Server 2008, el programa de instalación de Lync Server deshabilita la autenticación en modo kernel en IIS.</td>
</tr>
</tbody>
</table>


## En esta sección

  - [Requisitos de IIS para grupos de servidores front-end y servidores Standard Edition en Lync Server 2013](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)

