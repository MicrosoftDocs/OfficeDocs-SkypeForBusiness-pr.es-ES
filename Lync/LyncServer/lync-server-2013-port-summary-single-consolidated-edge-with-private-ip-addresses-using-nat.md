---
title: Resumen de Puerto-perímetro consolidado de un solo servidor con direcciones IP privadas con NAT
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Single consolidated edge with private IP addresses using NAT
ms:assetid: 3c1a389f-5f42-4719-a05b-e0b84aa3eb9e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425891(v=OCS.15)
ms:contentKeyID: 48183877
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f03be5f30b3d196d491fdcbe803ceb9b5f482f4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139191"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---single-consolidated-edge-with-private-ip-addresses-using-nat-in-lync-server-2013"></a>Resumen de Puerto-perímetro consolidado de un solo servidor con direcciones IP privadas mediante NAT en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-04-03_

La funcionalidad de servidor perimetral de Lync Server 2013, que se describe en esta arquitectura de escenario, es muy similar a la que se implementó en Lync Server 2010. La adición más llamativa es la entrada del puerto **5269 sobre TCP** para el protocolo extensible de mensajería y presencia (XMPP). Lync Server 2013 puede implementar opcionalmente un proxy XMPP en el servidor perimetral o en el grupo de servidores perimetrales y en el servidor de puerta de enlace XMPP en el servidor front-end o en el grupo de servidores front-end.

Además de IPv4, el servidor perimetral ahora es compatible con IPv6. En aras de la claridad, en los escenarios de ejemplo solo se usa IPv4.

**Perímetro de red de un solo servidor perimetral consolidado con direccionamiento IP privado mediante NAT**

![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")

<div>

## <a name="port-and-protocol-details"></a>Detalles de puerto y protocolo

Se recomienda abrir únicamente los puertos necesarios para admitir la funcionalidad para la que se proporciona acceso externo.

Para que el acceso remoto funcione para cualquier servicio perimetral, es obligatorio que el tráfico SIP pueda fluir de forma bidireccional, tal como se muestra en la figura Tráfico perimetral entrante/saliente. En otra forma, los mensajes SIP hacia y desde el servicio perimetral de acceso están relacionados con la mensajería instantánea (mi), la presencia, la conferencia Web, el audio/vídeo (A/V) y la Federación.

### <a name="firewall-summary-for-single-consolidated-edge-with-private-ip-addresses-using-nat-external-interface"></a>Resumen del firewall para un solo servidor perimetral consolidado con direcciones IP privadas mediante NAT: interfaz externa

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Rol/Protocolo/TCP o UDP/Puerto</th>
<th>Dirección IP de origen</th>
<th>Dirección IP de destino</th>
<th>Notas</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XMPP/TCP/5269</p></td>
<td><p>Cualquiera</p></td>
<td><p>Servicio de proxy XMPP (comparte la dirección IP con el servicio perimetral de acceso)</p></td>
<td><p>El servicio proxy XMPP acepta tráfico desde contactos XMPP definidos en las federaciones XMPP</p></td>
</tr>
<tr class="even">
<td><p>Acceso/HTTP/TCP/80</p></td>
<td><p>Servicio perimetral de acceso del servidor perimetral</p></td>
<td><p>Cualquiera</p></td>
<td><p>Revocación de certificados/Comprobación y recuperación de CRL</p></td>
</tr>
<tr class="odd">
<td><p>Acceso/DNS/TCP/53</p></td>
<td><p>Servicio perimetral de acceso del servidor perimetral</p></td>
<td><p>Cualquiera</p></td>
<td><p>Consulta de DNS sobre TCP</p></td>
</tr>
<tr class="even">
<td><p>Acceso/DNS/UDP/53</p></td>
<td><p>Servicio perimetral de acceso del servidor perimetral</p></td>
<td><p>Cualquiera</p></td>
<td><p>Consulta de DNS sobre UDP</p></td>
</tr>
<tr class="odd">
<td><p>Acceso/SIP (TLS)/TCP/443</p></td>
<td><p>Cualquiera</p></td>
<td><p>Servicio perimetral de acceso del servidor perimetral</p></td>
<td><p>Tráfico SIP de cliente a servidor para acceso de usuarios externos</p></td>
</tr>
<tr class="even">
<td><p>Acceso/SIP (MTLS)/TCP/5061</p></td>
<td><p>Cualquiera</p></td>
<td><p>Servicio perimetral de acceso del servidor perimetral</p></td>
<td><p>Para conectividad de mensajería instantánea pública y federada mediante SIP</p></td>
</tr>
<tr class="odd">
<td><p>Acceso/SIP (MTLS)/TCP/5061</p></td>
<td><p>Servicio perimetral de acceso del servidor perimetral</p></td>
<td><p>Cualquiera</p></td>
<td><p>Para la conectividad de MI pública y federada mediante SIP</p></td>
</tr>
<tr class="even">
<td><p>Conferencia web/PSOM (TLS)/TCP/443</p></td>
<td><p>Cualquiera</p></td>
<td><p>Servicio perimetral de conferencia web del servidor perimetral</p></td>
<td><p>Medios de conferencia web</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/TCP/50000-59.999</p></td>
<td><p>Servicio perimetral A/V del servidor perimetral</p></td>
<td><p>Cualquiera</p></td>
<td><p>Necesario para la Federación con socios que ejecuten Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 y Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/UDP/50000-59.999</p></td>
<td><p>Servicio perimetral A/V del servidor perimetral</p></td>
<td><p>Cualquiera</p></td>
<td><p>Solo es necesario para la Federación con socios que ejecutan Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/TCP/50000-59.999</p></td>
<td><p>Cualquiera</p></td>
<td><p>Servicio perimetral A/V del servidor perimetral</p></td>
<td><p>Solo es necesario para la Federación con socios que ejecutan Office Communications Server 2007</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/UDP/50000-59.999</p></td>
<td><p>Cualquiera</p></td>
<td><p>Servicio perimetral A/V del servidor perimetral</p></td>
<td><p>Solo es necesario para la Federación con socios que ejecutan Office Communications Server 2007</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>Servicio perimetral A/V del servidor perimetral</p></td>
<td><p>Cualquiera</p></td>
<td><p>3478 saliente se usa para determinar la versión del servidor perimetral con el que Lync Server se comunica y también para el tráfico de medios de un servidor perimetral a un servidor perimetral. Necesario para la Federación con Lync Server 2010, Windows Live Messenger y Office Communications Server 2007 R2, y también si hay varios grupos de servidores perimetrales implementados dentro de una empresa.</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>Cualquiera</p></td>
<td><p>Servicio perimetral A/V del servidor perimetral</p></td>
<td><p>Negociación STUN/TURN de candidatos sobre UDP/3478</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN, MSTURN/TCP/443</p></td>
<td><p>Cualquiera</p></td>
<td><p>Servicio perimetral A/V del servidor perimetral</p></td>
<td><p>Negociación STUN/TURN de candidatos sobre TCP/443</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN, MSTURN/TCP/443</p></td>
<td><p>Servicio perimetral A/V del servidor perimetral</p></td>
<td><p>Cualquiera</p></td>
<td><p>Negociación STUN/TURN de candidatos sobre TCP/443</p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-single-consolidated-edge-with-private-ip-addresses-using-nat-internal-interface"></a>Resumen del firewall para un solo servidor perimetral consolidado con direcciones IP privadas mediante NAT: interfaz interna

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Protocolo/TCP o UDP/Puerto</th>
<th>Dirección IP de origen</th>
<th>Dirección IP de destino</th>
<th>Comentarios</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XMPP/MTLS/TCP/23456</p></td>
<td><p>Cualquiera (puede definirse como IP del servidor Standard Edition, dirección IP del servidor Standard Edition o dirección IP del grupo de servidores que ejecuta el servicio de puerta de enlace XMPP)</p></td>
<td><p>Interfaz interna del servidor perimetral</p></td>
<td><p>Tráfico XMPP saliente desde el servicio de puerta de enlace XMPP que se ejecuta en el servidor front-end o grupo de servidores front-end</p></td>
</tr>
<tr class="even">
<td><p>SIP/MTLS/TCP/5061</p></td>
<td><p>Cualquiera (puede definirse como director, dirección IP del grupo de directores, servidor front-end o dirección IP del grupo de servidores front-end)</p></td>
<td><p>Interfaz interna del servidor perimetral</p></td>
<td><p>Tráfico SIP saliente (del Director, la dirección IP del grupo de directores, el servidor front-end o la dirección IP del grupo de servidores front-end) a la interfaz interna del servidor perimetral</p></td>
</tr>
<tr class="odd">
<td><p>SIP/MTLS/TCP/5061</p></td>
<td><p>Interfaz interna del servidor perimetral</p></td>
<td><p>Cualquiera (puede definirse como director, dirección IP del grupo de directores, servidor front-end o dirección IP del grupo de servidores front-end)</p></td>
<td><p>Tráfico SIP entrante (Director, dirección IP del grupo de directores, servidor front-end o dirección IP del grupo de servidores front-end) de la interfaz interna del servidor perimetral</p></td>
</tr>
<tr class="even">
<td><p>PSOM/MTLS/TCP/8057</p></td>
<td><p>Cualquiera (puede definirse como una dirección IP de servidor front-end o cada dirección IP de servidor front-end en un grupo de servidores front-end)</p></td>
<td><p>Interfaz interna del servidor perimetral</p></td>
<td><p>Tráfico de conferencia web desde el servidor front-end o cada servidor front-end si en un grupo de servidores, a la interfaz interna del servidor perimetral</p></td>
</tr>
<tr class="odd">
<td><p>SIP/MTLS/TCP/5062</p></td>
<td><p>Cualquiera (puede definirse como una dirección IP de servidor front-end, una dirección IP de grupo de servidores front-end o cualquier aplicación de sucursal con funciones de supervivencia o servidor de sucursal con funciones de supervivencia que usen este servidor perimetral)</p></td>
<td><p>Interfaz interna del servidor perimetral</p></td>
<td><p>Autenticación de usuarios de A/V (servicio de autenticación A/V) desde el servidor front-end o la dirección IP del grupo de servidores front-end o cualquier aplicación de sucursal con funciones de supervivencia o servidor de sucursal con funciones de supervivencia mediante este servidor perimetral</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/UDP/3478</p></td>
<td><p>Cualquiera</p></td>
<td><p>Interfaz interna del servidor perimetral</p></td>
<td><p>Ruta de acceso preferida para la transferencia de medios de A/V entre usuarios internos y externos, aplicación de sucursal con funciones de supervivencia o servidor de sucursal con funciones de supervivencia</p></td>
</tr>
<tr class="odd">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>Cualquiera</p></td>
<td><p>Interfaz interna del servidor perimetral</p></td>
<td><p>Ruta de acceso de reserva para la transferencia de medios de A/V entre usuarios internos y externos, aplicación de sucursal con funciones de supervivencia o servidor de sucursal con funciones de supervivencia si no se puede establecer la comunicación UDP, se usa TCP para la transferencia de archivos y el uso compartido de escritorio</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>Cualquiera (puede definirse como la dirección IP del servidor front-end o el grupo de servidores que contiene el almacén de administración central)</p></td>
<td><p>Interfaz interna del servidor perimetral</p></td>
<td><p>Replicación de los cambios del almacén de Administración central al servidor perimetral</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50001</p></td>
<td><p>Cualquiera</p></td>
<td><p>Interfaz interna del servidor perimetral</p></td>
<td><p>Controlador del servicio de registro centralizado con los cmdlets del shell de administración de Lync Server y el servicio de registro centralizado, la línea de comandos de ClsController (ClsController. exe) o los comandos y la colección de registros del agente (ClsAgent. exe)</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50002</p></td>
<td><p>Cualquiera</p></td>
<td><p>Interfaz interna del servidor perimetral</p></td>
<td><p>Controlador del servicio de registro centralizado con los cmdlets del shell de administración de Lync Server y el servicio de registro centralizado, la línea de comandos de ClsController (ClsController. exe) o los comandos y la colección de registros del agente (ClsAgent. exe)</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50003</p></td>
<td><p>Cualquiera</p></td>
<td><p>Interfaz interna del servidor perimetral</p></td>
<td><p>Controlador del servicio de registro centralizado con los cmdlets del shell de administración de Lync Server y el servicio de registro centralizado, la línea de comandos de ClsController (ClsController. exe) o los comandos y la colección de registros del agente (ClsAgent. exe)</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a>Resumen del firewall para federación


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Rol/Protocolo/TCP o UDP/Puerto</th>
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
<td><p>Para conectividad de mensajería instantánea pública y federada mediante SIP</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a>Resumen de firewall: Conectividad de mensajería instantánea pública


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Rol/Protocolo/TCP o UDP/Puerto</th>
<th>Dirección IP de origen</th>
<th>Dirección IP de destino</th>
<th>Notas</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Acceso/SIP (MTLS)/TCP/5061</p></td>
<td><p>Socios de conectividad de MI pública</p></td>
<td><p>Servicio perimetral de acceso del servidor perimetral</p></td>
<td><p>Para conectividad de mensajería instantánea pública y federada mediante SIP</p></td>
</tr>
<tr class="even">
<td><p>Acceso/SIP (MTLS)/TCP/5061</p></td>
<td><p>Servicio perimetral de acceso del servidor perimetral</p></td>
<td><p>Socios de conectividad de MI pública</p></td>
<td><p>Para conectividad de mensajería instantánea pública y federada mediante SIP</p></td>
</tr>
<tr class="odd">
<td><p>Acceso/SIP (TLS)/TCP/443</p></td>
<td><p>Clientes</p></td>
<td><p>Servicio perimetral de acceso del servidor perimetral</p></td>
<td><p>Tráfico SIP de cliente a servidor para acceso de usuarios externos</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50000-59.999</p></td>
<td><p>Servicio perimetral A/V del servidor perimetral</p></td>
<td><p>Clientes de Live Messenger</p></td>
<td><p>Usado para sesiones de A/V con Windows Live Messenger si se ha configurado la conectividad de MI.</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>Servicio perimetral A/V del servidor perimetral</p></td>
<td><p>Clientes de Live Messenger</p></td>
<td><p>Obligatorio para la conectividad de MI pública con Windows Live Messenger</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>Clientes de Live Messenger</p></td>
<td><p>Servicio perimetral A/V del servidor perimetral</p></td>
<td><p>Obligatorio para la conectividad de MI pública con Windows Live Messenger</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a>Resumen de firewall para el protocolo extensible de mensajería y presencia


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Protocolo/TCP o UDP/Puerto</th>
<th>Origen (Dirección IP)</th>
<th>Destino (Dirección IP)</th>
<th>Comentarios</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XMPP/TCP/5269</p></td>
<td><p>Cualquiera</p></td>
<td><p>Dirección IP de la interfaz del servicio perimetral de acceso del servidor perimetral</p></td>
<td><p>Puerto de comunicación estándar de servidor a servidor para XMPP. Permite la comunicación con el proxy XMPP del servidor perimetral desde socios XMPP federados.</p></td>
</tr>
<tr class="even">
<td><p>XMPP/TCP/5269</p></td>
<td><p>Dirección IP de la interfaz del servicio perimetral de acceso del servidor perimetral</p></td>
<td><p>Cualquiera</p></td>
<td><p>Puerto de comunicación estándar de servidor a servidor para XMPP. Permite la comunicación desde el proxy XMPP del servidor perimetral a asociados de XMPP federados.</p></td>
</tr>
<tr class="odd">
<td><p>XMPP/MTLS/TCP/23456</p></td>
<td><p>Cualquiera</p></td>
<td><p>Cada IP de la interfaz del servidor perimetral interno</p></td>
<td><p>Tráfico XMPP interno de la puerta de enlace XMPP del servidor front-end o del grupo de servidores front-end a la dirección IP interna del servidor perimetral o la dirección IP interna de cada miembro del grupo perimetral</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

