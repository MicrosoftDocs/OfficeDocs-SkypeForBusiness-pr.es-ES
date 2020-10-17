---
title: 'Lync Server 2013: tabla NetworkConnectionDetail'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: NetworkConnectionDetail table
ms:assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205185(v=OCS.15)
ms:contentKeyID: 48185170
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1dad115cb658289e20cf376c246c4e546bc0642
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48505447"
---
# <a name="networkconnectiondetail-table-in-lync-server-2013"></a>Tabla NetworkConnectionDetail en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-02_

La tabla NetworkConnectionDetail asigna los tipos de conexión de red a los identificadores de conexión de red usados en otra parte de la base de datos de calidad de la experiencia. Esta tabla se introdujo en Microsoft Lync Server 2013.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Columna</strong></th>
<th><strong>Tipo de datos</strong></th>
<th><strong>Clave o índice</strong></th>
<th><strong>Detalles</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>NetworkConnectionDetailKey</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Principal</p></td>
<td><p>Identificador único del tipo de conexión de red.</p></td>
</tr>
<tr class="even">
<td><p><strong>NetworkConnectionDetail</strong></p></td>
<td><p>VARCHAR (256)</p></td>
<td><p>Única</p></td>
<td><p>Tipo de conexión de red que se corresponde con NetworkConnectionDetailKey. Los valores permitidos son:</p>
<ol>
<li><p>0: cableada</p></li>
<li><p>1: Wi-Fi</p></li>
<li><p>2: Ethernet</p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

