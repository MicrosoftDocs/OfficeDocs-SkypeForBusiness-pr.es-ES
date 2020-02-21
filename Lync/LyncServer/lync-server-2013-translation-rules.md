---
title: 'Lync Server 2013: reglas de conversión'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Translation rules
ms:assetid: 6e067bd4-4931-4385-81ac-2acae45a16d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398520(v=OCS.15)
ms:contentKeyID: 48184460
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d1576b9c0c7286150c62f1491960bf9beef5d700
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193443"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="translation-rules-in-lync-server-2013"></a>Reglas de conversión en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-05_

Lync Server 2013 Enterprise Voice requiere que todas las cadenas de marcado se normalizan al formato E. 164 con el propósito de realizar la búsqueda inversa de números (RNL). En Microsoft Lync Server 2010, las reglas de conversión solo se admiten para números con nombre. New in Microsoft Lync Server 2013, también se admiten las reglas de conversión para números de llamada. La *entidad del mismo nivel que el tronco* (esto es, la puerta de enlace asociada, la central de comunicación (PBX) o el tronco SIP) puede requerir que los números estén en un formato de marcado local. Para convertir números del formato E.164 a un formato de marcado local, puede definir una o más reglas de conversión para manipular el URI de solicitud antes de enrutarlo a la entidad del mismo nivel que el tronco. Por ejemplo, puede escribir una regla de conversión para quitar +44 del inicio de la cadena de marcado y sustituirlo por 0144.

Mediante la conversión de la ruta saliente del servidor, se pueden reducir los requisitos de configuración de cada entidad del mismo nivel que el tronco individual para convertir los números de teléfono en un formato de marcado local. Al planear qué puertas de enlace y cuántas puertas de enlace, para asociar con un clúster de servidor de mediación específico, puede resultar útil agrupar los pares de tronco con requisitos de marcado local similares. De este modo, se puede reducir el número de reglas de conversión requeridas y el tiempo necesario para escribirlas.

<div>


> [!IMPORTANT]  
> La Asociación de una o más reglas de traducción con una configuración de tronco de Enterprise Voice debe usarse como alternativa a la configuración de reglas de conversión en el tronco del mismo nivel. No asocie reglas de conversión a una configuración de tronco de telefonía IP empresarial si ha configurado reglas de conversión en el sistema de tronco del mismo nivel, ya que las dos reglas podrían entrar en conflicto.



</div>

<div>

## <a name="example-translation-rules"></a>Reglas de conversión de ejemplo

Los siguientes ejemplos de reglas de conversión muestran cómo se pueden desarrollar reglas en el servidor para convertir números del formato E.164 a un formato local para la entidad del mismo nivel que el tronco.

Para obtener más información sobre cómo implementar reglas de conversión, consulte [Defining Translation Rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) en la documentación sobre implementación.


<table>
<colgroup>
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
</colgroup>
<thead>
<tr class="header">
<th>Descripción</th>
<th>Dígitos iniciales</th>
<th>Length</th>
<th>Dígitos que se van a quitar</th>
<th>Dígitos que se van a agregar</th>
<th>Patrón de comparación</th>
<th>Translation</th>
<th>Ejemplo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Marcado convencional de larga distancia en EE.UU.</p>
<p>(quite el "+")</p></td>
<td><p>+ 1</p></td>
<td><p>Exactamente 12</p></td>
<td><p>1</p></td>
<td><p>comprendi</p></td>
<td><p>^\+(1 \ d{10}) $</p></td>
<td><p>$1</p></td>
<td><p>+14255551010 se convierte en 14255551010</p></td>
</tr>
<tr class="even">
<td><p>Marcado internacional de larga distancia de EE.UU.</p>
<p>(quite el "+" y agregue 011)</p></td>
<td><p>+</p></td>
<td><p>11 como mínimo</p></td>
<td><p>1</p></td>
<td><p>011</p></td>
<td><p>^\+(\d{9}\d +) $</p></td>
<td><p>011 $1</p></td>
<td><p>+441235551010 se convierte en 011441235551010</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

