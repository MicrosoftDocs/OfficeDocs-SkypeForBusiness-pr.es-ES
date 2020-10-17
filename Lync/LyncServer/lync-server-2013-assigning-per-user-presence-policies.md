---
title: 'Lync Server 2013: asignación de directivas de presencia por usuario'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assigning per-user presence policies
ms:assetid: fd1097b7-248d-4b78-8c43-456b03257c18
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182614(v=OCS.15)
ms:contentKeyID: 48185955
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c4f561189b72cf19fad28879711e3a1da0da8fb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527127"
---
# <a name="assigning-per-user-presence-policies-in-lync-server-2013"></a>Asignación de directivas de presencia por usuario en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-11_

Una directiva de presencia es un conjunto de límites y restricciones que afectan a la presencia. En la tabla siguiente se describe la configuración de la Directiva de presencia disponible en Lync Server 2013.

### <a name="presence-policy-settings"></a>Configuración de directivas de presencia

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>Nombre XML</th>
<th>Nombre para mostrar</th>
<th>Descripción</th>
<th>Tipo</th>
<th>Valor</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CategorySubscriptions</p></td>
<td><p>Número máximo de suscripciones a categorías de suscriptores</p></td>
<td><p>Limita el número de suscripciones a categorías de suscriptores. Por ejemplo, cuando Communicator se suscribe a la presencia de un usuario, obtiene una suscripción de categoría por cada categoría de tarjeta de contacto, datos de calendario, notas, servicios y estado.</p>
<p>Si el valor es 0, significa que no se puede suscribir al objeto de contacto o usuario.</p>
<div>

> [!NOTE]  
> Esta configuración puede influir en gran medida en el rendimiento si se configura con un número alto y cada usuario suele tener una gran cantidad de usuarios suscritos a su presencia.


</div></td>
<td><p>Entero</p></td>
<td><p>0-3000</p></td>
</tr>
<tr class="even">
<td><p>PromptedSubscribers</p></td>
<td><p>Número máximo de alertas de suscripción de presencia en la cola</p></td>
<td><p>Limita el número de entradas de la tabla de suscriptores avisados. Esta configuración determina la cantidad máxima de avisos que se pueden colocar en la cola de un usuario determinado. Por ejemplo, cuando el usuario A se suscribe a la presencia del usuario B, el usuario B recibe un aviso de que el usuario A se ha suscrito al usuario B, y un aviso de reconocimiento se crea en la tabla de suscriptores avisados del usuario B. Cuando el usuario B acepta, o reconoce, la suscripción, el aviso de reconocimiento se quita de la tabla de suscriptores avisados del usuario B.</p>
<p>Si el valor es 0, significa que no se avisará al usuario cuando alguien se suscriba a su presencia.</p></td>
<td><p>Entero o token</p></td>
<td><p>0-500</p></td>
</tr>
</tbody>
</table>


De forma predeterminada, la **Directiva** y el servicio predeterminado: las directivas de presencia **mediana** se instalan al implementar Lync Server. En la siguiente tabla se describe la configuración concreta de estas dos directivas de presencia.

### <a name="presence-policies"></a>Directivas de presencia

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Nombre de directiva</th>
<th>Descripción</th>
<th>CategorySubscriptions</th>
<th>PromptedSubscribers</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Directiva predeterminada</p></td>
<td><p>Directiva para usuarios normales. Es la directiva de presencia predeterminada.</p></td>
<td><p>1000</p></td>
<td><p>200</p></td>
</tr>
<tr class="even">
<td><p>Service: Medium</p></td>
<td><p>Directiva para las aplicaciones que requieren la suscripción de más usuarios a la presencia del objeto.</p></td>
<td><p>1000</p></td>
<td><p>comprendi</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

