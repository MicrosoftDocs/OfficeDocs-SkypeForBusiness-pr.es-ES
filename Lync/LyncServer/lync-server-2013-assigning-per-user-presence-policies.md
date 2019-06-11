---
title: 'Lync Server 2013: asignación de directivas de presencia por usuario'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assigning per-user presence policies
ms:assetid: fd1097b7-248d-4b78-8c43-456b03257c18
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182614(v=OCS.15)
ms:contentKeyID: 48185955
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 905065e231869b4b6075fc1894e51c91df8f0aee
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842917"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assigning-per-user-presence-policies-in-lync-server-2013"></a>Asignar directivas de presencia por usuario en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-11_

Una directiva de presencia es un conjunto de límites y restricciones que afectan a la presencia. La siguiente tabla describe la configuración de la Directiva de presencia disponible en Lync Server 2013.

### <a name="presence-policy-settings"></a>Configuración de la Directiva de presencia

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
<td><p>Número máximo de suscripciones de categorías de suscriptores</p></td>
<td><p>Limita la cantidad de suscripciones de categorías de abonados. Por ejemplo, cuando Communicator se suscribe a la presencia de un usuario, obtiene una suscripción de categoría para cada una de las categorías de tarjeta de contacto, datos de calendario, notas, servicios y estado.</p>
<p>El valor 0 significa que otros usuarios no pueden suscribirse al objeto de usuario o contacto.</p>
<div>

> [!NOTE]  
> Esta configuración puede tener un impacto significativo en el rendimiento si se establece en un número alto y el usuario promedio tiene un gran número de usuarios que se suscriben a su presencia.


</div></td>
<td><p>Entero</p></td>
<td><p>0-3000</p></td>
</tr>
<tr class="even">
<td><p>PromptedSubscribers</p></td>
<td><p>Número máximo de alertas de suscripción de presencia en cola</p></td>
<td><p>Limita el número de entradas de la tabla suscriptores solicitada. Esta configuración determina el número máximo de mensajes que se pueden poner en cola para un usuario dado. Por ejemplo, cuando el usuario se suscribe a la presencia del usuario B, recibe un mensaje que indica que el usuario A ya está suscrito al usuario B y se crea un mensaje de confirmación en la tabla de suscriptores solicitada por el usuario B. Después de que el usuario B acepte o confirme la suscripción, se eliminará la solicitud de confirmación de la tabla de suscriptores solicitada por el usuario B.</p>
<p>Un valor de 0 significa que no se le pide confirmación al usuario cuando alguien se suscribe a su presencia.</p></td>
<td><p>Entero o token</p></td>
<td><p>0-500</p></td>
</tr>
</tbody>
</table>


De forma predeterminada, la **Directiva** y el servicio predeterminados: las directivas de presencia **media** se instalan al implementar Lync Server. En la siguiente tabla se describen las opciones específicas de las dos directivas de presencia.

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
<th>Nombre de la directiva</th>
<th>Descripción</th>
<th>CategorySubscriptions</th>
<th>PromptedSubscribers</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Directiva predeterminada</p></td>
<td><p>Directiva para usuarios típicos. Esta es la Directiva de presencia predeterminada.</p></td>
<td><p>1000</p></td>
<td><p>200</p></td>
</tr>
<tr class="even">
<td><p>Servicio: medio</p></td>
<td><p>Directiva para las aplicaciones que requieren más usuarios para suscribirse a la presencia del objeto.</p></td>
<td><p>1000</p></td>
<td><p>,0</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

