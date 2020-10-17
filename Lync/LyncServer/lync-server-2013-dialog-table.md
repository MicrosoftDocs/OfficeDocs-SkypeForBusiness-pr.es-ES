---
title: 'Lync Server 2013: tabla de cuadros de diálogo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dialog table
ms:assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398313(v=OCS.15)
ms:contentKeyID: 48184068
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a4c26c719e9d7e3cd0922813896896925a9bb6f9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519997"
---
# <a name="dialog-table-in-lync-server-2013"></a>Tabla de cuadro de diálogo en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-02_

La tabla Diálogo es una tabla de apoyo, en la que cada registro representa un cuadro de diálogo de protocolo de inicio de sesión (SIP).


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
<td><p><strong>ConferenceDateTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Principal</p></td>
<td><p>Momento en el que el agente de calidad de la experiencia (QoE) recibe el primer informe del autor o del destinatario de la llamada. Se usa junto con SessionSeq para identificar una sesión de forma exclusiva.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>entero</p></td>
<td><p>Principal</p></td>
<td><p>Número de secuencia que se usa para diferenciar sesiones cuando tienen el mismo ConferenceDateTime.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Identificador</strong></p></td>
<td><p>VARCHAR (256)</p></td>
<td></td>
<td><p>Id. de diálogo, exclusivo a nivel global.</p></td>
</tr>
<tr class="even">
<td><p><strong>DialogIDChecksum</strong></p></td>
<td><p>entero</p></td>
<td><p>index</p></td>
<td><p>Suma de comprobación del Id. de diálogo.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

