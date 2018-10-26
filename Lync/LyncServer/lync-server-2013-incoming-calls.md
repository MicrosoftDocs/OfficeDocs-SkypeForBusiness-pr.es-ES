---
title: 'Lync Server 2013: Llamadas entrantes'
TOCTitle: Llamadas entrantes
ms:assetid: 65b9c1b4-6af7-4527-8c33-22c4442bd209
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ994038(v=OCS.15)
ms:contentKeyID: 52061651
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Llamadas entrantes en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

El enrutamiento de llamadas entrantes a los usuarios habilitados para el enrutamiento según ubicación depende de la ubicación del extremo del usuario. El enrutamiento de llamadas entrantes se ve afectado de la siguiente manera. Si un usuario tiene una llamada entrante a un extremo ubicado en un sitio de red habilitado para el enrutamiento según ubicación, y el extremo se encuentra en el mismo sitio de red que la puerta de enlace RTC, la llamada se enrutará. Si un usuario tiene una llamada entrante a un extremo ubicado en un sitio de red habilitado para el enrutamiento según ubicación, y el extremo se encuentra en un sitio de red distinto a la puerta de enlace RTC, la llamada no se enrutará. Cuando un usuario no tenga extremos ubicados en el mismo sitio de red que la puerta de enlace RTC desde la que se origina la llamada entrante, la llamada entrante se enrutará directamente al correo de voz del usuario y se enviará una notificación de llamada perdida a la persona a la que se está llamando.

La configuración de reenvío de llamada de un usuario habilitado para el enrutamiento según ubicación se seguirá aplicando. Sin embargo, las llamadas reenviadas estarán sujetas a las restricciones de enrutamiento según ubicación del usuario.

En la siguiente tabla se ilustra cómo afecta el enrutamiento según ubicación al enrutamiento de las llamadas entrantes según la ubicación del extremo del destinatario de la llamada. El sitio de red de la puerta de enlace RTC está habilitado para el enrutamiento según ubicación y este solo permite enrutamiento de llamadas RTC a extremos dentro del mismo sitio de red.

### El destinatario recibe una llamada entrante desde el RTC

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>El extremo del destinatario se encuentra en el mismo sitio de red que la puerta de enlace RTC</th>
<th>El extremo del destinatario no se encuentra en el mismo sitio de red que la puerta de enlace RTC</th>
<th>El extremo del destinatario se encuentra en un sitio de red desconocido o no habilitado para el enrutamiento según ubicación</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Enrutamiento de una llamada RTC entrante</p></td>
<td><p>La llamada entrante se enruta a los extremos del destinatario</p></td>
<td><p>La llamada entrante no se enruta a los extremos del destinatario</p></td>
<td><p>La llamada entrante no se enruta a los extremos del destinatario</p></td>
</tr>
</tbody>
</table>

  

## Vea también

#### Otros recursos

[Escenarios para el enrutamiento basado en ubicación en Lync Server 2013](lync-server-2013-scenarios-for-location-based-routing.md)

