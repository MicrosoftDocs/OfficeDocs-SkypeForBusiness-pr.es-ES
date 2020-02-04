---
title: 'Lync Server 2013: tblPrincipalAffiliations'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalAffiliations
ms:assetid: 45fd8484-5837-44d2-85bb-45c83546607c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558642(v=OCS.15)
ms:contentKeyID: 48183993
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3976b98fddc96ad08f3de4413bf8f38ec3525496
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764156"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalaffiliations-in-lync-server-2013"></a>tblPrincipalAffiliations en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-12_

tblPrincipalAffiliations contiene las afiliaciones principales que describen las pertenencias en ubicaciones, incluidos los grupos de seguridad de los servicios de dominio de Active Directory, en contenedores de Active Directory, en dominios.

### <a name="columns"></a>Columnas

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Columna</th>
<th>Tipo</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>principalID</p></td>
<td><p>int, not null</p></td>
<td><p>IDENTIFICADOR de la entidad de identidad afiliada.</p></td>
</tr>
<tr class="even">
<td><p>affiliationID</p></td>
<td><p>int, not null</p></td>
<td><p>IDENTIFICADOR de la identidad que representa la afiliación. Cada principal (excepto los tipos de usuario del sistema) tiene también una afiliación propia.</p></td>
</tr>
<tr class="odd">
<td><p>clasificación</p></td>
<td><p>int, not null</p></td>
<td><p>Clasificación. El valor de las afiliaciones automáticas es de-1 y para las otras afiliaciones que aumenta secuencialmente de 1 en cada &lt;PrincipalID, affiliationId&gt; bucket.</p></td>
</tr>
<tr class="even">
<td><p>updatedBy</p></td>
<td><p>int, not null</p></td>
<td><p>Principal que realizó la actualización más reciente. Esto suele ser 1, que significa sincronización de Active Directory.</p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a>Sus

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Columnas</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&lt;principalID, Indice, affiliationID&gt;</p></td>
<td><p>Clave principal.</p></td>
</tr>
<tr class="even">
<td><p>principalID</p></td>
<td><p>Clave externa con la búsqueda en la tabla tblPrincipal. prinID.</p></td>
</tr>
<tr class="odd">
<td><p>affiliationID</p></td>
<td><p>Clave externa con la búsqueda en la tabla tblPrincipal. prinID.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

