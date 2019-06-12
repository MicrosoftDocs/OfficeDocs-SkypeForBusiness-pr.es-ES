---
title: 'Lync Server 2013: reglas de traducción'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Translation rules
ms:assetid: 6e067bd4-4931-4385-81ac-2acae45a16d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398520(v=OCS.15)
ms:contentKeyID: 48184460
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 22b6fbacf068f6a1a388a968989259afec81d17a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850298"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="translation-rules-in-lync-server-2013"></a>Reglas de traducción en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-05_

Lync Server 2013 Enterprise Voice requiere que todas las cadenas de marcado se normalizaran al formato E. 164 con el fin de realizar la búsqueda de números inversos (RNL). En Microsoft Lync Server 2010, las reglas de traducción solo se admiten para números llamados. En Microsoft Lync Server 2013, también se admiten las reglas de traducción para llamar a los números. El *tronco del mismo nivel* (es decir, la puerta de enlace asociada, la central de conmutación [PBX] o el tronco SIP) puede necesitar que los números estén en un formato de marcado local. Para convertir números del formato E.164 a un formato de marcado local, puede definir una o más reglas de conversión para manipular el URI de solicitud antes de redirigirlo al tronco del mismo nivel que el tronco. Por ejemplo, puede escribir una regla de conversión para quitar +44 del inicio de la cadena de marcado y cambiarlo por 0144.

Con la conversión de la ruta saliente del servidor, puedes reducir los requisitos de configuración de cada tronco del mismo nivel individual para convertir los números de teléfono en un formato de marcado local. Cuando se planean las puertas de enlace y el número de puertas de enlace para asociarlas con un clúster de servidor de mediación específico, puede resultar útil agrupar los pares de troncales con requisitos de marcado local similares. Así, se puede reducir la cantidad de reglas de conversión necesarias y el tiempo necesario para escribirlas.

<div>


> [!IMPORTANT]  
> La Asociación de una o más reglas de traducción con una configuración de telefonía IP empresarial debe utilizarse como alternativa a la configuración de reglas de traducción en el sistema troncal. No asociar reglas de traducción con una configuración de troncal empresarial de voz si ha configurado reglas de traducción en el sistema troncal del mismo nivel, porque las dos reglas podrían entrar en conflicto.



</div>

<div>

## <a name="example-translation-rules"></a>Reglas de conversión de ejemplo

Los siguientes ejemplos de reglas de conversión muestran cómo se pueden desarrollar reglas en el servidor para convertir números del formato E.164 a un formato local para el tronco del mismo nivel.

Para obtener más información sobre cómo implementar reglas de traducción, consulte [definición de reglas de traducción en Lync Server 2013](lync-server-2013-defining-translation-rules.md) en la documentación de implementación.


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
<th>Longitud</th>
<th>Dígitos que se van a quitar</th>
<th>Dígitos que se van a agregar</th>
<th>Patrón de comparación</th>
<th>Conversión</th>
<th>Ejemplo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Marcado convencional de larga distancia de EE. UU.</p>
<p>(quita el "+")</p></td>
<td><p>+1</p></td>
<td><p>Exactamente 12</p></td>
<td><p>1</p></td>
<td><p>,0</p></td>
<td><p>^\+(1 \ d{10}) $</p></td>
<td><p>$1</p></td>
<td><p>+14255551010 se convierte en 14255551010</p></td>
</tr>
<tr class="even">
<td><p>Marcado internacional de larga distancia de EE. UU.</p>
<p>(quita el "+" y agrega 011)</p></td>
<td><p>+</p></td>
<td><p>11 como mínimo</p></td>
<td><p>1</p></td>
<td><p>011</p></td>
<td><p>^\+(\d{9}\d +) $</p></td>
<td><p>011$1</p></td>
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

