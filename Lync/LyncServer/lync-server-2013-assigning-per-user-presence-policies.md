---
title: Asignación de directivas de presencia por usuario en Lync Server 2013
TOCTitle: Asignación de directivas de presencia por usuario en Lync Server 2013
ms:assetid: fd1097b7-248d-4b78-8c43-456b03257c18
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg182614(v=OCS.15)
ms:contentKeyID: 48277295
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Asignación de directivas de presencia por usuario en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

Una directiva de presencia es un conjunto de límites y restricciones que afectan a la presencia. La siguiente tabla describe las configuraciones de directivas de presencia disponibles en Lync Server 2013.

### Configuración de directivas de presencia

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


De forma predeterminada, las directivas de presencia **Directiva predeterminada** y **Service: Medium** se instalan al implementar Lync Server. En la siguiente tabla se describe la configuración concreta de estas dos directivas de presencia.

### Directivas de presencia

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
<td><p>0</p></td>
</tr>
</tbody>
</table>

