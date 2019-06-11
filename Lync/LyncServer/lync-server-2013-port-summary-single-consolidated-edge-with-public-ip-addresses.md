---
title: Resumen de puerto - Perímetro consolidado de equipo único con direcciones IP públicas
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - Single consolidated edge with public IP addresses
ms:assetid: 28407acc-8b92-4f78-875c-fd6b4323b602
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204756(v=OCS.15)
ms:contentKeyID: 48183685
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c1a61341908bef3a3098e70b06816bbf5ea328b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824242"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a>Resumen de puerto - Perímetro consolidado de equipo único con direcciones IP públicas en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-21_

La funcionalidad del servidor de Lync Server 2013, que se describe en esta arquitectura de escenario, es muy similar a la que se ha implementado en Lync Server 2010. La adición más destacada es el puerto **5269 sobre** la entrada TCP para el protocolo de presencia y mensajería extensible (XMPP). Lync Server 2013 implementa opcionalmente un proxy XMPP en el servidor perimetral o en el grupo perimetral y el servidor de puerta de enlace XMPP en el servidor front-end o en el grupo front-end. La información de planeación del proxy inverso y la Federación se encuentra en [escenarios de inverso de proxy en Lync server 2013](lync-server-2013-scenarios-for-reverse-proxy.md) , así como en la [planeación de la Federación de SIP, la Federación de XMPP y la mensajería instantánea pública en las secciones de Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md) , respectivamente.

Además de IPv4, el servidor EDGE ahora es compatible con IPv6. Para mayor claridad, solo se usa IPv4 en los escenarios.

**Red perimetral empresarial para un solo borde consolidado con direccionamiento IP público**

![f8c144c5-e5fb-498a-823e-eb39f26b6847] (images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")

<div>

## <a name="port-and-protocol-details"></a>Detalles de protocolo y puerto

Le recomendamos que abra solo los puertos necesarios para admitir la funcionalidad para la que proporciona acceso externo.

Para que el acceso remoto funcione para cualquier servicio perimetral, es obligatorio que el tráfico SIP pueda fluir de forma bidireccional tal y como se muestra en la cifra de tráfico entrante o saliente. En concreto, los mensajes SIP a y desde el servicio perimetral de acceso participan en la mensajería instantánea (mi), presencia, conferencias web, audio/vídeo (A/V) y Federación.

### <a name="firewall-summary-for-single-consolidated-edge-with-public-ip-addresses-external-interface"></a>Resumen del firewall para un solo borde consolidado con direcciones IP públicas: interfaz externa

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Función/protocolo/TCP o UDP/puerto</th>
<th>Dirección IP de origen</th>
<th>Dirección IP de destino</th>
<th>Notas</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XMPP/TCP/5269</p></td>
<td><p>Cualquiera</p></td>
<td><p>Servicio de proxy XMPP (comparte dirección IP con servicio perimetral de acceso)</p></td>
<td><p>El servicio Proxy XMPP acepta el tráfico de los contactos XMPP en las federaciones XMPP definidas</p></td>
</tr>
<tr class="even">
<td><p>Access/HTTP/TCP/80</p></td>
<td><p>Dirección IP pública del servicio perimetral de acceso al servidor perimetral</p></td>
<td><p>Cualquiera</p></td>
<td><p>Comprobación y recuperación de CRL o revocación de certificados</p></td>
</tr>
<tr class="odd">
<td><p>Acceso/DNS/TCP/53</p></td>
<td><p>Dirección IP pública del servicio perimetral de acceso al servidor perimetral</p></td>
<td><p>Cualquiera</p></td>
<td><p>Consulta DNS a través de TCP</p></td>
</tr>
<tr class="even">
<td><p>Acceso/DNS/UDP/53</p></td>
<td><p>Dirección IP pública del servicio perimetral de acceso al servidor perimetral</p></td>
<td><p>Cualquiera</p></td>
<td><p>Consulta DNS a través de UDP</p></td>
</tr>
<tr class="odd">
<td><p>Acceso/SIP (TLS)/TCP/443</p></td>
<td><p>Cualquiera</p></td>
<td><p>Dirección IP pública del servicio perimetral de acceso al servidor perimetral</p></td>
<td><p>Tráfico SIP de cliente a servidor para el acceso de usuarios externos</p></td>
</tr>
<tr class="even">
<td><p>Acceso/SIP (MTLS)/TCP/5061</p></td>
<td><p>Cualquiera</p></td>
<td><p>Dirección IP pública del servicio perimetral de acceso al servidor perimetral</p></td>
<td><p>Para conectividad de mensajería instantánea pública y federada con SIP</p></td>
</tr>
<tr class="odd">
<td><p>Acceso/SIP (MTLS)/TCP/5061</p></td>
<td><p>Dirección IP pública del servicio perimetral de acceso al servidor perimetral</p></td>
<td><p>Cualquiera</p></td>
<td><p>Para conectividad de mensajería instantánea pública y federada con SIP</p></td>
</tr>
<tr class="even">
<td><p>Conferencias web/PSOM (TLS)/TCP/443</p></td>
<td><p>Cualquiera</p></td>
<td><p>Dirección IP pública del servicio perimetral de conferencias web del servidor perimetral</p></td>
<td><p>Medios de conferencia Web</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/TCP/50000-59.999 SESIONES</p></td>
<td><p>Dirección IP pública del servicio perimetral de acceso al servidor perimetral</p></td>
<td><p>Cualquiera</p></td>
<td><p>Necesario para la Federación con socios que ejecutan Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 y Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/UDP/50000-59.999 SESIONES</p></td>
<td><p>Dirección IP pública del servicio perimetral A/V del servidor perimetral</p></td>
<td><p>Cualquiera</p></td>
<td><p>Necesario solo para la Federación con socios que ejecutan Office Communications Server 2007</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/TCP/50000-59.999 SESIONES</p></td>
<td><p>Cualquiera</p></td>
<td><p>Dirección IP pública del servicio perimetral A/V del servidor perimetral</p></td>
<td><p>Solo es necesario para la Federación con socios que ejecutan Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/UDP/50000-59.999 SESIONES</p></td>
<td><p>Cualquiera</p></td>
<td><p>Dirección IP pública del servicio perimetral A/V del servidor perimetral</p></td>
<td><p>Solo es necesario para la Federación con socios que ejecutan Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>Dirección IP pública del servicio perimetral A/V del servidor perimetral</p></td>
<td><p>Cualquiera</p></td>
<td><p>3478 saliente se usa para determinar la versión del servidor perimetral con el que se comunica Lync Server y también para el tráfico de multimedia de un servidor perimetral a un servidor perimetral. Necesario para la Federación con Lync Server 2010, Windows Live Messenger y Office Communications Server 2007 R2, y también si se han implementado varias agrupaciones perimetrales dentro de una empresa.</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>Cualquiera</p></td>
<td><p>Dirección IP pública del servicio perimetral A/V del servidor perimetral</p></td>
<td><p>STUN/TURN negociación de candidatos a través de UDP/3478</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN, MSTURN/TCP/443</p></td>
<td><p>Cualquiera</p></td>
<td><p>Dirección IP pública del servicio perimetral A/V del servidor perimetral</p></td>
<td><p>STUN/TURN negociación de candidatos por TCP/443</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN, MSTURN/TCP/443</p></td>
<td><p>Dirección IP pública del servicio perimetral A/V del servidor perimetral</p></td>
<td><p>Cualquiera</p></td>
<td><p>STUN/TURN negociación de candidatos por TCP/443</p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-single-consolidated-edge-with-public-ip-addresses-internal-interface"></a>Resumen del firewall para un solo borde consolidado con direcciones IP públicas: interfaz interna

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
<th>Dirección IP de origen</th>
<th>Dirección IP de destino</th>
<th>Comentarios</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XMPP/MTLS/TCP/23456</p></td>
<td><p>Cualquiera (puede definirse como IP de servidor Standard Edition, dirección IP del servidor Standard Edition o dirección IP del grupo de servidores que ejecuta el servicio de puerta de enlace XMPP)</p></td>
<td><p>Interfaz interna de Edge Server</p></td>
<td><p>Tráfico XMPP saliente del servicio de puerta de enlace XMPP que se ejecuta en el servidor front-end o grupo front-end</p></td>
</tr>
<tr class="even">
<td><p>SIP/MTLS/TCP/5061</p></td>
<td><p>Cualquiera (se puede definir como director, dirección IP del grupo de directores, servidor front-end o dirección IP del grupo de servidores front-end)</p></td>
<td><p>IP del servidor perimetral o grupo que contiene la interfaz interna</p></td>
<td><p>Tráfico SIP saliente (del Director, la dirección IP del grupo de directores, el servidor front-end o la dirección IP del grupo de servidores front-end) a la interfaz interna del servidor perimetral</p></td>
</tr>
<tr class="odd">
<td><p>SIP/MTLS/TCP/5061</p></td>
<td><p>Interfaz interna de Edge Server</p></td>
<td><p>Cualquiera (se puede definir como director, dirección IP del grupo de directores, servidor front-end o dirección de grupo frontal)</p></td>
<td><p>Tráfico SIP entrante (Director, dirección IP del grupo de directores, servidor front-end o dirección IP del grupo front-end) de la interfaz interna del servidor perimetral</p></td>
</tr>
<tr class="even">
<td><p>PSOM/MTLS/TCP/8057</p></td>
<td><p>Cualquiera (se puede definir como la dirección IP del servidor front-end o cada dirección IP del servidor front-end en un grupo de servidores front-end)</p></td>
<td><p>Interfaz interna de Edge Server</p></td>
<td><p>Tráfico de conferencias web desde el servidor front-end o cada servidor front-end si se está en un grupo, a la interfaz interna del servidor perimetral</p></td>
</tr>
<tr class="odd">
<td><p>SIP/MTLS/TCP/5062</p></td>
<td><p>Cualquiera (se puede definir como la dirección IP del servidor front-end, la dirección IP del grupo de servidores front-end o cualquier otro equipo de sucursal o servidor de sucursal con la supervivencia que use este servidor perimetral)</p></td>
<td><p>Interfaz interna de Edge Server</p></td>
<td><p>Autenticación de usuarios A/V (servicio de autenticación A/V) desde el servidor front-end o la dirección IP del grupo de servidores front-end o cualquier otro dispositivo de sucursal que sea reviviente o con el servidor de sucursal</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/UDP/3478</p></td>
<td><p>Cualquiera</p></td>
<td><p>Interfaz interna de Edge Server</p></td>
<td><p>Ruta preferida para la transferencia de medios A/V entre usuarios internos y externos, un equipo de sucursal o un servidor de sucursal con la supervivencia</p></td>
</tr>
<tr class="odd">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>Cualquiera</p></td>
<td><p>Interfaz interna de Edge Server</p></td>
<td><p>Ruta de reserva para la transferencia de medios A/V entre usuarios internos y externos, equipo de sucursal con la supervivencia o servidor de sucursal con la supervivencia, si no se puede establecer la comunicación UDP, se usa TCP para la transferencia de archivos y el uso compartido de escritorio</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>Cualquiera (puede definirse como la dirección IP del servidor front-end o el grupo que contiene el almacén de administración central)</p></td>
<td><p>Interfaz interna de Edge Server</p></td>
<td><p>Replicación de los cambios del almacén de administración central al servidor perimetral</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50001</p></td>
<td><p>Cualquiera</p></td>
<td><p>Interfaz interna de Edge Server</p></td>
<td><p>Controlador de servicio de registro centralizado con los cmdlets del shell de administración de Lync Server y el servicio de registro centralizado, la línea de comandos de ClsController (ClsController. exe) o los comandos del agente (ClsAgent. exe) y la colección de registros</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50002</p></td>
<td><p>Cualquiera</p></td>
<td><p>Interfaz interna de Edge Server</p></td>
<td><p>Controlador de servicio de registro centralizado con los cmdlets del shell de administración de Lync Server y el servicio de registro centralizado, la línea de comandos de ClsController (ClsController. exe) o los comandos del agente (ClsAgent. exe) y la colección de registros</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50003</p></td>
<td><p>Cualquiera</p></td>
<td><p>Interfaz interna de Edge Server</p></td>
<td><p>Controlador de servicio de registro centralizado con los cmdlets del shell de administración de Lync Server y el servicio de registro centralizado, la línea de comandos de ClsController (ClsController. exe) o los comandos del agente (ClsAgent. exe) y la colección de registros</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a>Resumen del firewall para la Federación


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Función/protocolo/TCP o UDP/puerto</th>
<th>Dirección IP de origen</th>
<th>Dirección IP de destino</th>
<th>Notas</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Acceso/SIP (MTLS)/TCP/5061</p></td>
<td><p>Dirección IP pública del servicio perimetral de acceso</p></td>
<td><p>Cualquiera</p></td>
<td><p>Para conectividad de mensajería instantánea pública y federada con SIP</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a>Resumen del firewall: conectividad de mensajería instantánea pública


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Función/protocolo/TCP o UDP/puerto</th>
<th>Dirección IP de origen</th>
<th>Dirección IP de destino</th>
<th>Notas</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Acceso/SIP (MTLS)/TCP/5061</p></td>
<td><p>Partners de conectividad de mensajería instantánea pública</p></td>
<td><p>Servicio perimetral de acceso al servidor perimetral</p></td>
<td><p>Para conectividad de mensajería instantánea pública y federada con SIP</p></td>
</tr>
<tr class="even">
<td><p>Acceso/SIP (MTLS)/TCP/5061</p></td>
<td><p>Servicio perimetral de acceso al servidor perimetral</p></td>
<td><p>Partners de conectividad de mensajería instantánea pública</p></td>
<td><p>Para conectividad de mensajería instantánea pública y federada con SIP</p></td>
</tr>
<tr class="odd">
<td><p>Acceso/SIP (TLS)/TCP/443</p></td>
<td><p>Clientes</p></td>
<td><p>Servicio perimetral de acceso al servidor perimetral</p></td>
<td><p>Tráfico SIP de cliente a servidor para el acceso de usuarios externos</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50000-59.999 SESIONES</p></td>
<td><p>Servidor perimetral A/V servicio perimetral</p></td>
<td><p>Clientes de Live Messenger</p></td>
<td><p>Se usa para sesiones de A/V con Windows Live Messenger si está configurada la conectividad de mensajería instantánea pública.</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>Servidor perimetral A/V servicio perimetral</p></td>
<td><p>Clientes de Live Messenger</p></td>
<td><p>Necesario para la conectividad de mensajería instantánea pública con Windows Live Messenger</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>Clientes de Live Messenger</p></td>
<td><p>Servidor perimetral A/V servicio perimetral</p></td>
<td><p>Necesario para la conectividad de mensajería instantánea pública con Windows Live Messenger</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a>Resumen de Firewall para el protocolo de presencia y mensajería extensible


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
<td><p>Dirección IP de la interfaz de servicio perimetral de acceso al servidor perimetral</p></td>
<td><p>Puerto de comunicación de servidor a servidor estándar para XMPP. Permite la comunicación con el proxy XMPP del servidor perimetral de socios de XMPP</p></td>
</tr>
<tr class="even">
<td><p>XMPP/TCP/5269</p></td>
<td><p>Dirección IP de la interfaz de servicio perimetral de acceso al servidor perimetral</p></td>
<td><p>Cualquiera</p></td>
<td><p>Puerto de comunicación de servidor a servidor estándar para XMPP. Permite la comunicación desde el proxy XMPP del servidor perimetral a socios XMPP de Federación</p></td>
</tr>
<tr class="odd">
<td><p>XMPP/MTLS/TCP/23456</p></td>
<td><p>Cualquiera</p></td>
<td><p>Cada IP de la interfaz del servidor perimetral interno</p></td>
<td><p>Tráfico de XMPP interno de la puerta de enlace XMPP en el servidor front-end o grupo front-end a la dirección IP interna del servidor perimetral o a la dirección IP interna de cada miembro del grupo perimetral</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

