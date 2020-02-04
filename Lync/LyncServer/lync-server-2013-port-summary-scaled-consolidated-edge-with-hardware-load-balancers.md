---
title: Resumen de puerto - Servidor perimetral consolidado ampliado con equilibradores de carga de hardware
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Scaled consolidated edge with hardware load balancers
ms:assetid: 91213b1e-f875-464b-83e8-fe3a351595a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398739(v=OCS.15)
ms:contentKeyID: 48184841
ms.date: 04/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6260a4ad7f2717e0b4eb2446fc5b17671c3e45a5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725040"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a>Resumen de puerto - Servidor perimetral consolidado ampliado con equilibradores de carga de hardware en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2015-04-27_

La funcionalidad del servidor de Lync Server 2013, que se describe en esta arquitectura de escenario, es muy similar a la que se ha implementado en Lync Server 2010. La adición más destacada es el puerto **5269 sobre** la entrada TCP para el protocolo de presencia y mensajería extensible (XMPP). Lync Server 2013 implementa opcionalmente un proxy XMPP en el servidor perimetral o en el grupo perimetral y el servidor de puerta de enlace XMPP en el servidor front-end o en el grupo front-end.

Además de IPv4, el servidor EDGE ahora es compatible con IPv6. Para mayor claridad, solo se usa IPv4 en los escenarios.

**Borde consolidado escalado mediante el equilibrio de carga de hardware**

![Protocolos y puertos de la red perimetral de servidores perimetrales](images/Gg398739.063f7dd1-16db-4cc7-8708-bca9bc41184d(OCS.15).jpg "Protocolos y puertos de la red perimetral de servidores perimetrales")

<div>

## <a name="port-and-protocol-details"></a>Detalles de protocolo y puerto

Le recomendamos que abra solo los puertos necesarios para admitir la funcionalidad para la que proporciona acceso externo.

Para que el acceso remoto funcione para cualquier servicio perimetral, es obligatorio que el tráfico SIP pueda fluir de forma bidireccional tal y como se muestra en la cifra de tráfico entrante o saliente. En concreto, los mensajes SIP a y desde el servicio perimetral de acceso participan en la mensajería instantánea (mi), presencia, conferencias web, audio/vídeo (A/V) y Federación.

### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-external-interface--node-1-and-node-2-example"></a>Resumen del firewall para el perímetro consolidado con escala, equilibrio de carga de hardware: interfaz externa-nodo 1 y nodo 2 (ejemplo)

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
<td><p>Access/HTTP/TCP/80</p></td>
<td><p>Dirección IP pública del servicio perimetral de acceso al servidor perimetral</p></td>
<td><p>Cualquiera</p></td>
<td><p>Comprobación y recuperación de CRL o revocación de certificados</p></td>
</tr>
<tr class="even">
<td><p>Acceso/DNS/TCP/53</p></td>
<td><p>Dirección IP pública del servicio perimetral de acceso al servidor perimetral</p></td>
<td><p>Cualquiera</p></td>
<td><p>Consulta DNS a través de TCP</p></td>
</tr>
<tr class="odd">
<td><p>Acceso/DNS/UDP/53</p></td>
<td><p>Dirección IP pública del servicio perimetral de acceso al servidor perimetral</p></td>
<td><p>Cualquiera</p></td>
<td><p>Consulta DNS a través de UDP</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50000-59.999 SESIONES</p></td>
<td><p>Dirección IP del servicio Edge del servidor perimetral A/V</p></td>
<td><p>Cualquiera</p></td>
<td><p>Necesario para la Federación con socios que ejecutan Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 y Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/UDP/50000-59.999 SESIONES</p></td>
<td><p>Dirección IP pública del servicio perimetral A/V del servidor perimetral</p></td>
<td><p>Cualquiera</p></td>
<td><p>Solo es necesario para la Federación con socios que ejecutan Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50000-59.999 SESIONES</p></td>
<td><p>Cualquiera</p></td>
<td><p>Dirección IP pública del servicio perimetral A/V del servidor perimetral</p></td>
<td><p>Necesario solo para la Federación con socios que ejecutan Office Communications Server 2007</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/UDP/50000-59.999 SESIONES</p></td>
<td><p>Cualquiera</p></td>
<td><p>Dirección IP pública del servicio perimetral A/V del servidor perimetral</p></td>
<td><p>Necesario solo para la Federación con socios que ejecutan Office Communications Server 2007</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>Dirección IP pública del servicio perimetral A/V del servidor perimetral</p></td>
<td><p>Cualquiera</p></td>
<td><p>3478 saliente se usa para determinar la versión del servidor perimetral con el que se comunica Lync Server y también para el tráfico de multimedia de un servidor perimetral a un servidor perimetral. Necesario para la Federación con Lync Server 2010, Windows Live Messenger y Office Communications Server 2007 R2, y también si se han implementado varias agrupaciones perimetrales dentro de una empresa.</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>Cualquiera</p></td>
<td><p>Dirección IP pública del servicio perimetral A/V del servidor perimetral</p></td>
<td><p>STUN/TURN negociación de candidatos a través de UDP/3478</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN, MSTURN/TCP/443</p></td>
<td><p>Cualquiera</p></td>
<td><p>Dirección IP pública del servicio perimetral A/V del servidor perimetral</p></td>
<td><p>STUN/TURN negociación de candidatos por TCP/443</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN, MSTURN/TCP/443</p></td>
<td><p>Dirección IP pública del servicio perimetral A/V del servidor perimetral</p></td>
<td><p>Cualquiera</p></td>
<td><p>STUN/TURN negociación de candidatos por TCP/443</p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-node-1-and-node-2"></a>Resumen del firewall para el perímetro consolidado con escala, equilibrio de carga de hardware: nodo 1 de interfaz interna y nodo 2

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
<td><p>XMPP/MTLS/TCP/23456</p></td>
<td><p>Cualquiera (se puede definir como la dirección del servidor front-end o la dirección IP virtual del grupo de servidores front-end que ejecuta el servicio de puerta de enlace XMPP)</p></td>
<td><p>Interfaz interna de Edge Server</p></td>
<td><p>Tráfico XMPP saliente del servicio de puerta de enlace XMPP que se ejecuta en el servidor front-end o grupo front-end</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>Cualquiera (puede definirse como la IP o el grupo de servidores front-end Server que contiene el almacén central de administración)</p></td>
<td><p>Interfaz interna de Edge Server</p></td>
<td><p>Replicación de los cambios del almacén de administración central al servidor perimetral</p></td>
</tr>
<tr class="odd">
<td><p>PSOM/MTLS/TCP/8057</p></td>
<td><p>Any (se puede definir como IP de Director, IP de servidor front end o IP virtual de grupo)</p></td>
<td><p>Interfaz interna de Edge Server</p></td>
<td><p>Tráfico de conferencias web de la implementación interna a la interfaz de servidor perimetral interno</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/UDP/3478</p></td>
<td><p>Any (se puede definir como IP de Director, IP de servidor front end o IP virtual de grupo)</p></td>
<td><p>Interfaz interna de Edge Server</p></td>
<td><p>Ruta preferida para la transferencia de medios A/V entre usuarios internos y externos, un equipo de sucursal o un servidor de sucursal con la supervivencia</p></td>
</tr>
<tr class="odd">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>Any (se puede definir como IP de Director, IP de servidor front end o IP virtual de grupo)</p></td>
<td><p>Interfaz interna de Edge Server</p></td>
<td><p>Ruta de reserva para la transferencia de medios A/V entre usuarios internos y externos, equipo de sucursal con la supervivencia o servidor de sucursal con la supervivencia, si no se puede establecer la comunicación UDP, se usa TCP para la transferencia de archivos y el uso compartido de escritorio</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50001</p></td>
<td><p>Cualquiera</p></td>
<td><p>Interfaz interna de Edge Server</p></td>
<td><p>Controlador de servicio de registro centralizado con los cmdlets del shell de administración de Lync Server y el servicio de registro centralizado, la línea de comandos de ClsController (ClsController. exe) o los comandos del agente (ClsAgent. exe) y la colección de registros</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50002</p></td>
<td><p>Cualquiera</p></td>
<td><p>Interfaz interna de Edge Server</p></td>
<td><p>Controlador de servicio de registro centralizado con los cmdlets del shell de administración de Lync Server y el servicio de registro centralizado, la línea de comandos de ClsController (ClsController. exe) o los comandos del agente (ClsAgent. exe) y la colección de registros</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50003</p></td>
<td><p>Cualquiera</p></td>
<td><p>Interfaz interna de Edge Server</p></td>
<td><p>Controlador de servicio de registro centralizado con los cmdlets del shell de administración de Lync Server y el servicio de registro centralizado, la línea de comandos de ClsController (ClsController. exe) o los comandos del agente (ClsAgent. exe) y la colección de registros</p></td>
</tr>
</tbody>
</table>


Los equilibradores de carga de hardware tienen requisitos específicos cuando se implementan para proporcionar disponibilidad y equilibrio de carga para Lync Server. Los requisitos se definen en la siguiente ilustración y tablas. Los proveedores de terceros pueden usar terminología diferente para los requisitos que se definen aquí. Será necesario asignar los requisitos de Lync Server a las características y opciones de configuración proporcionadas por el proveedor de equilibrador de carga del hardware.

Al configurar equilibradores de carga de hardware, tenga en cuenta los siguientes requisitos:

  - La traducción de direcciones de red de origen (SNAT) se puede configurar en el equilibrio de carga de hardware (HLB) para el servicio perimetral de Access y el servicio perimetral de conferencia Web

  - SNAT no se puede configurar en el servicio perimetral A/V: el servicio perimetral A/V debe responder con la dirección real del servidor, no con la IP virtual de HLB (VIP), para un recorrido simple de UDP sobre NAT (STUN)/Traversal mediante la opción de retransmisión NAT (TURN)/Federation (FAPAGAR) para funcionar correctamente
    
      - Si el cliente envía una solicitud al HLB, la respuesta debe devolverse a la dirección VIP de HLB.
    
      - Si el cliente envía una solicitud al borde, la respuesta debe volver de la IP de borde.

  - Las direcciones IP públicas se usan en cada interfaz de servidor y en los VIP de la HLB, y los requisitos de dirección IP pública son N + 1, donde hay una dirección IP pública para cada interfaz de servidor real y otra para cada VIP de HLB. Cuando tiene dos servidores perimetrales en el grupo, se producen 9 direcciones IP públicas, donde 3 se usan para los VIP de HLB y una para cada interfaz de servidor perimetral (un total de seis para los servidores)

  - Para el servicio perimetral de Access y el servicio perimetral de conferencias web, (y uso de NAT en la HLB) el cliente se conecta a la dirección VIP, la VIP cambia la dirección IP de origen del cliente a su propia dirección IP. La interfaz de servidor dirige la dirección de remite a la dirección VIP, la VIP cambia la dirección de origen de la dirección IP de la interfaz del servidor y envía el paquete al cliente.

  - Para el servicio perimetral A/V, la dirección VIP no debe cambiar la dirección IP de origen, y la dirección del servidor real se devuelve directamente al cliente; no puede configurar NAT en el HLB para el tráfico audiovisual
    
      - Si el cliente envía una solicitud a la dirección VIP de HLB, la respuesta debe regresar a la HLB VIP
    
      - Si el cliente envía una solicitud a la IP de borde, la respuesta debe devolverse a la IP de borde.

  - Para AV, el firewall externo retendrá la dirección IP pública real del servidor para todos los paquetes

  - Una vez que se haya establecido, la comunicación entre el cliente y el servicio perimetral a/V es al servidor real, no a la HLB

  - El borde interno de los servidores internos y los clientes debe enrutarse y se establecen rutas persistentes para todas las redes internas que hospedan servidores o clientes.

  - La dirección VIP del servicio perimetral de acceso de HLB actuará como puerta de enlace predeterminada para cada interfaz de servidor perimetral.

<div>


> [!NOTE]
> Para obtener más información sobre el planeamiento y la funcionalidad de NAT, consulte <A href="lync-server-2013-hardware-load-balancer-requirements.md">requisitos del equilibrador de carga de hardware para Lync Server 2013</A>.



</div>

![Detalles de puertos y protocolos de servidores perimetrales](images/Gg398739.1c193b80-98ab-4d59-a854-dbfdb5e209e2(OCS.15).jpg "Detalles de puertos y protocolos de servidores perimetrales")

### <a name="external-port-settings-required-for-scaled-consolidated-edge-hardware-load-balanced-external-interface-virtual-ips"></a>Configuración de puertos externos necesaria para el perímetro consolidado con escala, equilibrio de carga de hardware: IPs virtual de interfaz externa

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
<td><p>XMPP/TCP/5269</p></td>
<td><p>Servicio de proxy XMPP (comparte dirección IP con servicio perimetral de acceso)</p></td>
<td><p>Cualquiera</p></td>
<td><p>El servicio Proxy XMPP envía tráfico a los contactos XMPP en las federaciones XMPP definidas</p></td>
</tr>
<tr class="odd">
<td><p>Acceso/SIP (TLS)/TCP/443</p></td>
<td><p>Cualquiera</p></td>
<td><p>Dirección VIP pública de servicio perimetral de acceso</p></td>
<td><p>Tráfico SIP de cliente a servidor para el acceso de usuarios externos</p></td>
</tr>
<tr class="even">
<td><p>Acceso/SIP (MTLS)/TCP/5061</p></td>
<td><p>Cualquiera</p></td>
<td><p>Dirección VIP pública de servicio perimetral de acceso</p></td>
<td><p>Señalización SIP, Federación y conectividad de mensajería instantánea pública con SIP</p></td>
</tr>
<tr class="odd">
<td><p>Acceso/SIP (MTLS)/TCP/5061</p></td>
<td><p>Dirección VIP pública de servicio perimetral de acceso</p></td>
<td><p>Socio federado</p></td>
<td><p>Señalización SIP, Federación y conectividad de mensajería instantánea pública con SIP</p></td>
</tr>
<tr class="even">
<td><p>Conferencias web/PSOM (TLS)/TCP/443</p></td>
<td><p>Cualquiera</p></td>
<td><p>Dirección VIP pública del servicio perimetral de conferencias web del servidor perimetral</p></td>
<td><p>Medios de conferencia Web</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>Cualquiera</p></td>
<td><p>Dirección VIP pública del servicio perimetral A/V del servidor perimetral</p></td>
<td><p>STUN/TURN negociación de candidatos a través de UDP/3478</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN, MSTURN/TCP/443</p></td>
<td><p>Cualquiera</p></td>
<td><p>Dirección VIP pública del servicio perimetral A/V del servidor perimetral</p></td>
<td><p>STUN/TURN negociación de candidatos por TCP/443</p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-virtual-ips"></a>Resumen del firewall para la tecnología perimetral consolidada con escala, equilibrio de carga de hardware: interfaz IP virtual interna

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
<td><p>Cualquiera (se puede definir como director, dirección IP virtual del grupo de directores, servidor front-end o dirección IP virtual del grupo de servidores front-end)</p></td>
<td><p>Interfaz VIP interna de Edge Server</p></td>
<td><p>Tráfico SIP saliente (de Director, grupo de directores, dirección IP virtual, servidor front-end o dirección IP virtual del grupo de servidores front-end) hasta VIP interna</p></td>
</tr>
<tr class="even">
<td><p>Acceso/SIP (MTLS)/TCP/5061</p></td>
<td><p>Interfaz VIP interna de Edge Server</p></td>
<td><p>Cualquiera (se puede definir como director, dirección IP virtual del grupo de directores, servidor front-end o dirección IP virtual del grupo de servidores front-end)</p></td>
<td><p>Tráfico SIP entrante (Director, grupo de directores, dirección IP virtual, servidor front-end o dirección IP virtual del grupo de servidores front-end) de la interfaz interna del servidor perimetral</p></td>
</tr>
<tr class="odd">
<td><p>SIP/MTLS/TCP/5062</p></td>
<td><p>Cualquiera (se puede definir como la dirección IP del servidor front-end, la dirección IP del grupo de servidores front-end o cualquier otro equipo de sucursal o servidor de sucursal con la supervivencia que use este servidor perimetral)</p></td>
<td><p>Interfaz VIP interna de Edge Server</p></td>
<td><p>Autenticación de usuarios A/V (servicio de autenticación A/V) desde el servidor front-end o la dirección IP del grupo de servidores front-end o cualquier otro dispositivo de sucursal que sea reviviente o con el servidor de sucursal</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/UDP/3478</p></td>
<td><p>Cualquiera</p></td>
<td><p>Interfaz VIP interna de Edge Server</p></td>
<td><p>Ruta preferida para la transferencia de medios A/V entre usuarios internos y externos</p></td>
</tr>
<tr class="odd">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>Cualquiera</p></td>
<td><p>Interfaz VIP interna de Edge Server</p></td>
<td><p>Ruta de reserva para la transferencia de medios A/V entre usuarios internos y externos si no se puede establecer la comunicación UDP, se usa TCP para la transferencia de archivos y el uso compartido de escritorio</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>Interfaz VIP interna de Edge Server</p></td>
<td><p>Cualquiera</p></td>
<td><p>Ruta de reserva para la transferencia de medios A/V entre usuarios internos y externos si no se puede establecer la comunicación UDP, se usa TCP para la transferencia de archivos y el uso compartido de escritorio</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

