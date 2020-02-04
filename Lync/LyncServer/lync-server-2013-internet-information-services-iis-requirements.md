---
title: 'Lync Server 2013: Requisitos de Internet Information Services (IIS)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Internet Information Services (IIS) requirements
ms:assetid: 4f57a605-a8a9-4c5a-9a18-05ecb3d9ab6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398321(v=OCS.15)
ms:contentKeyID: 48184128
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f4b51ac4996e2556ced3ad91e15a6cc58a1623c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725810"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="internet-information-services-iis-requirements-in-lync-server-2013"></a>Requisitos de Internet Information Services (IIS) en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-06-19_

Varios componentes de Lync Server 2013 requieren servicios de Internet Information Server (IIS). En este tema se describen las características específicas de IIS necesarias para admitir Lync Server. En los temas de esta sección se describen los requisitos de los componentes específicos de IIS.

Cuando el rol servidor Web (IIS) está habilitado en Windows Server 2008, se instalan varios servicios de rol de forma predeterminada. En la siguiente tabla se describen los servicios de rol adicionales que deben instalarse cuando el rol servidor Web (IIS) está habilitado en Windows Server 2008.


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
<td><p>Redireccionamiento HTTP</p></td>
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


<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="seguridad" alt="security" />Nota de seguridad:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Si está usando IIS 7,0 en un sistema operativo Windows Server 2008, el programa de instalación de Lync Server deshabilita la autenticación de modo kernel en IIS.</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="in-this-section"></a>En esta sección

  - [Requisitos de IIS para grupos de servidores front-end y servidores Standard Edition en Lync Server 2013](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

