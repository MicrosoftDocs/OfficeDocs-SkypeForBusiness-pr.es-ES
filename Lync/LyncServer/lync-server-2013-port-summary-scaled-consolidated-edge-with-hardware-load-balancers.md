---
title: Resumen de Puerto-servidor perimetral consolidado ampliado con equilibradores de carga de hardware
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
ms.openlocfilehash: e6af913a6be7b92a7a640a2e06537197ba21351c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183873"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a>Resumen de Puerto-servidor perimetral consolidado ampliado con equilibradores de carga de hardware en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2015-04-27_

La funcionalidad de servidor perimetral de Lync Server 2013, que se describe en esta arquitectura de escenario, es muy similar a la que se implementó en Lync Server 2010. La adición más llamativa es la entrada del puerto **5269 sobre TCP** para el protocolo extensible de mensajería y presencia (XMPP). Lync Server 2013 puede implementar opcionalmente un proxy XMPP en el servidor perimetral o en el grupo de servidores perimetrales y en el servidor de puerta de enlace XMPP en el servidor front-end o en el grupo de servidores front-end.

Además de IPv4, el servidor perimetral ahora es compatible con IPv6. En aras de la claridad, en los escenarios de ejemplo solo se usa IPv4.

**Servidor perimetral consolidado ampliado con equilibrio de carga de hardware**

![Puertos y protocolos de red perimetral del servidor perimetral](images/Gg398739.063f7dd1-16db-4cc7-8708-bca9bc41184d(OCS.15).jpg "Puertos y protocolos de red perimetral del servidor perimetral")

<div>

## <a name="port-and-protocol-details"></a>Detalles de puerto y protocolo

Se recomienda abrir solamente los puertos necesarios para admitir la funcionalidad para la que proporcione acceso externo.

Para que el acceso remoto funcione para cualquier servicio perimetral, es obligatorio que el tráfico SIP pueda fluir de forma bidireccional, tal como se muestra en la figura Tráfico perimetral entrante/saliente. Dicho de otra forma, la mensajería SIP hacia y desde el servicio perimetral de acceso interviene en mensajería instantánea, presencia, conferencia web, audio y vídeo (A/V) y federación.

### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-external-interface--node-1-and-node-2-example"></a>Resumen de Firewall para servidor perimetral consolidado escalado, carga equilibrada de hardware: interfaz externa – nodo 1 y nodo 2 (ejemplo)

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
<td><p>Acceso/HTTP/TCP/80</p></td>
<td><p>Dirección IP pública del servicio perimetral de acceso del servidor perimetral</p></td>
<td><p>Cualquiera</p></td>
<td><p>Revocación de certificados/Comprobación y recuperación de CRL</p></td>
</tr>
<tr class="even">
<td><p>Acceso/DNS/TCP/53</p></td>
<td><p>Dirección IP pública del servicio perimetral de acceso del servidor perimetral</p></td>
<td><p>Cualquiera</p></td>
<td><p>Consulta de DNS sobre TCP</p></td>
</tr>
<tr class="odd">
<td><p>Acceso/DNS/UDP/53</p></td>
<td><p>Dirección IP pública del servicio perimetral de acceso del servidor perimetral</p></td>
<td><p>Cualquiera</p></td>
<td><p>Consulta de DNS sobre UDP</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50000-59.999</p></td>
<td><p>Dirección IP del servicio perimetral del servidor perimetral A/V</p></td>
<td><p>Cualquiera</p></td>
<td><p>Necesario para la Federación con socios que ejecuten Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 y Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/UDP/50000-59.999</p></td>
<td><p>Dirección IP pública del servicio perimetral A/V del servidor perimetral</p></td>
<td><p>Cualquiera</p></td>
<td><p>Solo es necesario para la Federación con socios que ejecutan Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50000-59.999</p></td>
<td><p>Cualquiera</p></td>
<td><p>Dirección IP pública del servicio perimetral A/V del servidor perimetral</p></td>
<td><p>Solo es necesario para la Federación con socios que ejecutan Office Communications Server 2007</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/UDP/50000-59.999</p></td>
<td><p>Cualquiera</p></td>
<td><p>Dirección IP pública del servicio perimetral A/V del servidor perimetral</p></td>
<td><p>Solo es necesario para la Federación con socios que ejecutan Office Communications Server 2007</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>Dirección IP pública del servicio perimetral A/V del servidor perimetral</p></td>
<td><p>Cualquiera</p></td>
<td><p>3478 saliente se usa para determinar la versión del servidor perimetral con el que Lync Server se comunica y también para el tráfico de medios de un servidor perimetral a un servidor perimetral. Necesario para la Federación con Lync Server 2010, Windows Live Messenger y Office Communications Server 2007 R2, y también si hay varios grupos de servidores perimetrales implementados dentro de una empresa.</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>Cualquiera</p></td>
<td><p>Dirección IP pública del servicio perimetral A/V del servidor perimetral</p></td>
<td><p>Negociación STUN/TURN de candidatos sobre UDP/3478</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN, MSTURN/TCP/443</p></td>
<td><p>Cualquiera</p></td>
<td><p>Dirección IP pública del servicio perimetral A/V del servidor perimetral</p></td>
<td><p>Negociación STUN/TURN de candidatos sobre TCP/443</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN, MSTURN/TCP/443</p></td>
<td><p>Dirección IP pública del servicio perimetral A/V del servidor perimetral</p></td>
<td><p>Cualquiera</p></td>
<td><p>Negociación STUN/TURN de candidatos sobre TCP/443</p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-node-1-and-node-2"></a>Resumen de Firewall para servidor perimetral consolidado escalado, carga equilibrada de hardware: nodo 1 de interfaz interna y nodo 2

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
<td><p>XMPP/MTLS/TCP/23456</p></td>
<td><p>Cualquiera (puede definirse como dirección del servidor front-end o dirección IP virtual del grupo de servidores front-end que ejecuta el servicio de puerta de enlace XMPP)</p></td>
<td><p>Interfaz interna del servidor perimetral</p></td>
<td><p>Tráfico XMPP saliente desde el servicio de puerta de enlace XMPP que se ejecuta en el servidor front-end o grupo de servidores front-end</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>Cualquiera (puede definirse como la IP o el grupo de servidores front-end Server que contiene el almacén de administración central)</p></td>
<td><p>Interfaz interna del servidor perimetral</p></td>
<td><p>Replicación de los cambios del almacén de Administración central al servidor perimetral</p></td>
</tr>
<tr class="odd">
<td><p>PSOM/MTLS/TCP/8057</p></td>
<td><p>Cualquiera (puede definirse como IP de Director, IP de servidor front-end o IP virtual del grupo de servidores)</p></td>
<td><p>Interfaz interna del servidor perimetral</p></td>
<td><p>Tráfico de conferencia web de la implementación interna a la interfaz del servidor perimetral interno</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/UDP/3478</p></td>
<td><p>Cualquiera (puede definirse como IP de Director, IP de servidor front-end o IP virtual del grupo de servidores)</p></td>
<td><p>Interfaz interna del servidor perimetral</p></td>
<td><p>Ruta de acceso preferida para la transferencia de medios de A/V entre usuarios internos y externos, aplicación de sucursal con funciones de supervivencia o servidor de sucursal con funciones de supervivencia</p></td>
</tr>
<tr class="odd">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>Cualquiera (puede definirse como IP de Director, IP de servidor front-end o IP virtual del grupo de servidores)</p></td>
<td><p>Interfaz interna del servidor perimetral</p></td>
<td><p>Ruta de acceso de reserva para la transferencia de medios de A/V entre usuarios internos y externos, aplicación de sucursal con funciones de supervivencia o servidor de sucursal con funciones de supervivencia si no se puede establecer la comunicación UDP, se usa TCP para la transferencia de archivos y el uso compartido de escritorio</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50001</p></td>
<td><p>Cualquiera</p></td>
<td><p>Interfaz interna del servidor perimetral</p></td>
<td><p>Controlador del servicio de registro centralizado con los cmdlets del shell de administración de Lync Server y el servicio de registro centralizado, la línea de comandos de ClsController (ClsController. exe) o los comandos y la colección de registros del agente (ClsAgent. exe)</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50002</p></td>
<td><p>Cualquiera</p></td>
<td><p>Interfaz interna del servidor perimetral</p></td>
<td><p>Controlador del servicio de registro centralizado con los cmdlets del shell de administración de Lync Server y el servicio de registro centralizado, la línea de comandos de ClsController (ClsController. exe) o los comandos y la colección de registros del agente (ClsAgent. exe)</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50003</p></td>
<td><p>Cualquiera</p></td>
<td><p>Interfaz interna del servidor perimetral</p></td>
<td><p>Controlador del servicio de registro centralizado con los cmdlets del shell de administración de Lync Server y el servicio de registro centralizado, la línea de comandos de ClsController (ClsController. exe) o los comandos y la colección de registros del agente (ClsAgent. exe)</p></td>
</tr>
</tbody>
</table>


Los equilibradores de carga de hardware tienen requisitos específicos cuando se implementan para proporcionar disponibilidad y equilibrio de carga para Lync Server. Los requisitos se definen en la figura y las tablas siguientes. Los proveedores de terceros pueden usar terminología diferente para los requisitos que se definen aquí. Será necesario asignar los requisitos de Lync Server a las características y opciones de configuración proporcionadas por el proveedor del equilibrador de carga de hardware.

Al configurar equilibradores de carga de hardware, tenga en cuenta los siguientes requisitos:

  - La traducción de direcciones de red de origen (SNAT) se puede configurar en el equilibrador de carga de hardware (HLB) para el servicio perimetral de acceso y el servicio perimetral de conferencia Web.

  - No se puede configurar SNAT en el servicio perimetral A/V: el servicio perimetral A/V debe responder con la dirección real del servidor, no la IP virtual (VIP) de HLB, para un recorrido sencillo de UDP sobre NAT (STUN)/Traversal mediante la NAT de retransmisión (TURN)/Federation TURN (FTURN) para que funcione correctamente
    
      - Si el cliente envía una solicitud a HLB, la respuesta debe volver de la dirección VIP HLB
    
      - Si el cliente envía una solicitud al servidor perimetral, la respuesta debe volver de la IP del servidor perimetral.

  - Las direcciones IP públicas se usan en cada interfaz de servidor y en las direcciones VIP de HLB, y los requisitos de dirección IP pública son N + 1, donde hay una dirección IP pública para cada interfaz de servidor real y otra para cada VIP de HLB. Si tiene 2 servidores perimetrales en el grupo, se obtendrán 9 direcciones IP públicas, donde 3 se usan para los VIP de HLB y una para cada interfaz del servidor perimetral (un total de seis para los servidores)

  - Para el servicio perimetral de acceso y el servicio perimetral de conferencia web (y el uso de NAT en el HLB), el cliente se pone en contacto con la VIP, la VIP cambia la dirección IP de origen del cliente a su propia dirección IP. La interfaz del servidor dirige la dirección de retorno a la VIP, la VIP cambia la dirección de origen de la dirección IP de la interfaz del servidor y envía el paquete al cliente.

  - En el caso del servicio perimetral a/V, la VIP no debe cambiar la dirección IP de origen y la dirección del servidor real se devuelve al cliente directamente; no puede configurar NAT en el HLB para el tráfico audiovisual
    
      - Si el cliente envía una solicitud a la VIP de HLB, la respuesta debe volver de la VIP de HLB.
    
      - Si el cliente envía una solicitud a la IP perimetral, la respuesta debe devolverse a la dirección IP del servidor perimetral.

  - Para AV, el firewall externo mantendrá la dirección IP pública del servidor real para todos los paquetes

  - Una vez establecida, la comunicación del cliente con el servicio perimetral a/V es al servidor real, no a la HLB

  - El perímetro interno de los servidores internos y los clientes debe enrutarse, y las rutas persistentes se establecen para todas las redes internas que hospedan servidores o clientes.

  - La VIP del servicio perimetral de acceso HLB funcionará como puerta de enlace predeterminada para cada interfaz del servidor perimetral

<div>


> [!NOTE]
> Para obtener más información sobre la planeación y la funcionalidad de NAT, consulte <A href="lync-server-2013-hardware-load-balancer-requirements.md">requisitos del equilibrador de carga de hardware para Lync Server 2013</A>.



</div>

![Detalles de protocolos y puertos del servidor perimetral](images/Gg398739.1c193b80-98ab-4d59-a854-dbfdb5e209e2(OCS.15).jpg "Detalles de protocolos y puertos del servidor perimetral")

### <a name="external-port-settings-required-for-scaled-consolidated-edge-hardware-load-balanced-external-interface-virtual-ips"></a>Configuración de puertos externos necesaria para servidor perimetral consolidado ampliado, carga equilibrada de hardware: IP virtuales de interfaz externa

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
<td><p>XMPP/TCP/5269</p></td>
<td><p>Servicio de proxy XMPP (comparte la dirección IP con el servicio perimetral de acceso)</p></td>
<td><p>Cualquiera</p></td>
<td><p>El servicio Proxy XMPP envía tráfico a los contactos XMPP en las federaciones XMPP definidas</p></td>
</tr>
<tr class="odd">
<td><p>Acceso/SIP (TLS)/TCP/443</p></td>
<td><p>Cualquiera</p></td>
<td><p>Dirección VIP pública del servicio perimetral de acceso</p></td>
<td><p>Tráfico SIP de cliente a servidor para acceso de usuarios externos</p></td>
</tr>
<tr class="even">
<td><p>Acceso/SIP (MTLS)/TCP/5061</p></td>
<td><p>Cualquiera</p></td>
<td><p>Dirección VIP pública del servicio perimetral de acceso</p></td>
<td><p>Señalización SIP, federada y conectividad de mensajería instantánea pública con SIP</p></td>
</tr>
<tr class="odd">
<td><p>Acceso/SIP (MTLS)/TCP/5061</p></td>
<td><p>Dirección VIP pública del servicio perimetral de acceso</p></td>
<td><p>Socio federado</p></td>
<td><p>Señalización SIP, federada y conectividad de mensajería instantánea pública con SIP</p></td>
</tr>
<tr class="even">
<td><p>Conferencia web/PSOM (TLS)/TCP/443</p></td>
<td><p>Cualquiera</p></td>
<td><p>Dirección VIP pública del servicio perimetral de conferencia web del servidor perimetral</p></td>
<td><p>Medios de conferencia web</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>Cualquiera</p></td>
<td><p>Dirección VIP pública del servicio perimetral A/V del servidor perimetral A/V</p></td>
<td><p>Negociación STUN/TURN de candidatos sobre UDP/3478</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN, MSTURN/TCP/443</p></td>
<td><p>Cualquiera</p></td>
<td><p>Dirección VIP pública del servicio perimetral A/V del servidor perimetral A/V</p></td>
<td><p>Negociación STUN/TURN de candidatos sobre TCP/443</p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-virtual-ips"></a>Resumen de Firewall para servidor perimetral consolidado ampliado, carga equilibrada de hardware: IP virtuales de interfaz interna

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
<td><p>Cualquiera (puede definirse como director, dirección IP virtual del grupo de directores, servidor front-end o dirección IP virtual del grupo de servidores front-end)</p></td>
<td><p>Interfaz VIP interna del servidor perimetral</p></td>
<td><p>Tráfico SIP saliente (del Director, la dirección IP virtual del grupo de directores, el servidor front-end o la dirección IP virtual del grupo de servidores front-end) a la VIP de perímetro interno</p></td>
</tr>
<tr class="even">
<td><p>Acceso/SIP (MTLS)/TCP/5061</p></td>
<td><p>Interfaz VIP interna del servidor perimetral</p></td>
<td><p>Cualquiera (puede definirse como director, dirección IP virtual del grupo de directores, servidor front-end o dirección IP virtual del grupo de servidores front-end)</p></td>
<td><p>Tráfico SIP entrante (Director, dirección IP virtual del grupo de directores, servidor front-end o dirección IP virtual del grupo de servidores front-end) de la interfaz interna del servidor perimetral</p></td>
</tr>
<tr class="odd">
<td><p>SIP/MTLS/TCP/5062</p></td>
<td><p>Cualquiera (puede definirse como una dirección IP de servidor front-end, una dirección IP de grupo de servidores front-end o cualquier aplicación de sucursal con funciones de supervivencia o servidor de sucursal con funciones de supervivencia que usen este servidor perimetral)</p></td>
<td><p>Interfaz VIP interna del servidor perimetral</p></td>
<td><p>Autenticación de usuarios de A/V (servicio de autenticación A/V) desde el servidor front-end o la dirección IP del grupo de servidores front-end o cualquier aplicación de sucursal con funciones de supervivencia o servidor de sucursal con funciones de supervivencia mediante este servidor perimetral</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/UDP/3478</p></td>
<td><p>Cualquiera</p></td>
<td><p>Interfaz VIP interna del servidor perimetral</p></td>
<td><p>Ruta de acceso preferida para la transferencia de multimedia de A/V entre usuarios internos y externos</p></td>
</tr>
<tr class="odd">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>Cualquiera</p></td>
<td><p>Interfaz VIP interna del servidor perimetral</p></td>
<td><p>Ruta de conmutación por recuperación para transferencia de multimedia de A/V entre usuarios internos y externos si no se puede establecer la comunicación UDP, se usa TCP para la transferencia de archivos y el uso compartido de escritorios</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>Interfaz VIP interna del servidor perimetral</p></td>
<td><p>Cualquiera</p></td>
<td><p>Ruta de conmutación por recuperación para transferencia de multimedia de A/V entre usuarios internos y externos si no se puede establecer la comunicación UDP, se usa TCP para la transferencia de archivos y el uso compartido de escritorios</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

