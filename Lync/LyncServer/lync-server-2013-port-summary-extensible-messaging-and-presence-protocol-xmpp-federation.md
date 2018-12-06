---
title: "Resumen puertos: Federación del protocolo extensible de mensajería y presencia (XMPP)"
TOCTitle: "Résumé des ports - Féd. XMPP (Extensible Messaging and Presence Protocol)"
ms:assetid: 62e98fab-7add-4983-a3fa-dbe74e1c3849
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ618371(v=OCS.15)
ms:contentKeyID: 49115289
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Resumen de puertos - Federación del protocolo extensible de mensajería y presencia (XMPP)

 

_**Última modificación del tema:** 2015-03-09_

Los puertos y protocolos definidos en relación con el proxy de protocolo extensible de mensajería y presencia (XMPP) implementado en el Servidor perimetral posibilitan las comunicaciones entre el asociado federado XMPP y el Servidor perimetral, así como entre el Servidor perimetral y el asociado federado XMPP. También hay definida una regla en el firewall de conexión interna para las comunicaciones entre el Servidor front-end o el Grupo de servidores front-end y el Servidor perimetral o el Grupo de servidores perimetrales.

## Resumen de firewall para el protocolo extensible de mensajería y presencia


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Protocolo/TCP o UDP/puerto</th>
<th>Origen (dirección IP)</th>
<th>Destino (dirección IP)</th>
<th>Comentarios</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XMPP/TCP/5269</p></td>
<td><p>Cualquiera</p></td>
<td><p>Dirección IP interna del Servidor perimetral de acceso</p></td>
<td><p>Puerto de comunicación entre servidores estándar para XMPP. Permite la comunicación con el proxy XMPP del Servidor perimetral desde los asociados XMPP federados</p></td>
</tr>
<tr class="even">
<td><p>XMPP/TCP/5269</p></td>
<td><p>Dirección IP interna del Servidor perimetral de acceso</p></td>
<td><p>Cualquiera</p></td>
<td><p>Puerto de comunicación entre servidores estándar para XMPP. Permite la comunicación desde el proxy XMPP del Servidor perimetral con los asociados XMPP federados</p></td>
</tr>
<tr class="odd">
<td><p>XMPP/MTLS/23456</p></td>
<td><p>Cualquiera</p></td>
<td><p>IP de la interfaz del Servidor perimetral interno</p></td>
<td><p>Tráfico XMPP interno desde la puerta de enlace XMPP del Servidor front-end o del Grupo de servidores front-end hacia el Servidor perimetral</p></td>
</tr>
</tbody>
</table>


## Vea también

#### Tareas

[Configuración XMPP de ejemplo en Lync Server 2013 - Federación XMPP con Google Talk](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  

#### Otros recursos

[Administrar socios federados XMPP para su organización en Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)

