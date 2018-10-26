---
title: "Lync Server 2013: Resumen puerto: Servidor perim. consolidado con equilibr. carga"
TOCTitle: Resumen de puerto - Servidor perimetral consolidado ampliado con equilibradores de carga de hardware
ms:assetid: 91213b1e-f875-464b-83e8-fe3a351595a4
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398739(v=OCS.15)
ms:contentKeyID: 48276014
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Resumen de puerto - Servidor perimetral consolidado ampliado con equilibradores de carga de hardware en Lync Server 2013

 

_**Última modificación del tema:** 2015-04-27_

La funcionalidad del servidor perimetral Lync Server 2013 descrita en la arquitectura de este escenario es muy similar a lo implementado en Lync Server 2010. La adición más notable es el puerto **5269 sobre la entrada TCP** para el protocolo extensible de mensajería y presencia (XMPP). Lync Server 2013 implementa de manera opcional un proxy XMPP proxy en Servidor perimetral o en Grupo de servidores perimetrales y el servidor de puerta de enlace XMPP en Servidor front-end o Grupo de servidores front-end.

Además de IPv4, el Servidor perimetral ahora admite IPv6. Para mayor claridad, en los escenarios solo se usa IPv4.

**Servidor perimetral consolidado y ampliado con equilibrio de carga de hardware**

![Protocolos y puertos de la red perimetral de servidores perimetrales](images/Gg398739.063f7dd1-16db-4cc7-8708-bca9bc41184d(OCS.15).jpg "Protocolos y puertos de la red perimetral de servidores perimetrales")

## Detalles de protocolo y puerto

Se recomienda abrir solamente los puertos necesarios para admitir la funcionalidad para la que proporcione acceso externo.

Para que el acceso remoto funcione con cualquier servidor perimetral, es obligatorio que el tráfico SIP tenga permiso para fluir en ambos sentidos, como se muestra en la ilustración de Topología perimetral consolidada escalada (carga equilibrada con hardware). Dicho de otra forma, el Servidor perimetral de acceso interviene en mensajería instantánea, presencia, conferencia web y audio y vídeo (A/V).

### Configuración de puertos externos necesaria para la Topología perimetral consolidada escalada (carga equilibrada con hardware): Nodo de interfaz externa 2

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
<td><p>Dirección IP pública del Servidor perimetral  Servidor perimetral de acceso</p></td>
<td><p>Cualquiera</p></td>
<td><p>Revocación de certificados/comprobación y recuperación de CRL</p></td>
</tr>
<tr class="even">
<td><p>Acceso/DNS/TCP/53</p></td>
<td><p>Dirección IP pública del Servidor perimetral  Servidor perimetral de acceso</p></td>
<td><p>Cualquiera</p></td>
<td><p>Consulta DNS sobre TCP</p></td>
</tr>
<tr class="odd">
<td><p>Acceso/DNS/UDP/53</p></td>
<td><p>Dirección IP pública del Servidor perimetral  Servidor perimetral de acceso</p></td>
<td><p>Cualquiera</p></td>
<td><p>Consulta DNS sobre UDP</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50.000-59.999</p></td>
<td><p>Dirección IP del Servidor perimetral  Servicio perimetral A/V</p></td>
<td><p>Cualquiera</p></td>
<td><p>Necesario para federación con socios que ejecuten Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 y Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/UDP/50.000-59.999</p></td>
<td><p>Dirección IP pública de Servidor perimetral Servicio perimetral A/V</p></td>
<td><p>Cualquiera</p></td>
<td><p>Solo se necesita para federación con socios que todavía ejecuten Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50.000-59.999</p></td>
<td><p>Cualquiera</p></td>
<td><p>Dirección IP pública Servidor perimetral Servicio perimetral A/V</p></td>
<td><p>Necesario solo para compartir escritorio con socios que ejecuten Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/UDP/50.000-59.999</p></td>
<td><p>Cualquiera</p></td>
<td><p>Dirección IP pública de Servidor perimetral Servicio perimetral A/V</p></td>
<td><p>Necesario solo para compartir escritorio con socios que ejecuten Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/UDP/3478 (entrada/salida)</p></td>
<td><p>Dirección IP pública de Servidor perimetral Servicio perimetral A/V</p></td>
<td><p>Cualquiera</p></td>
<td><p>3478 saliente se usa para averiguar la versión del Servidor perimetral con el que se está comunicando Lync ServerLync Server 2013, y también para el tráfico de medios de Servidor perimetral-a- Servidor perimetral. Necesario para federación con Lync Server 2010, Windows Live Messenger y Office Communications Server 2007 R2, y también si hay implementados varios Grupos de servidores perimetrales en una compañía.</p></td>
</tr>
<tr class="odd">
<td><p>STUN/MSTURN/UDP/3478 (entrada/salida)</p></td>
<td><p>Cualquiera</p></td>
<td><p>Dirección IP pública de Servidor perimetral Servicio perimetral A/V</p></td>
<td><p>Negociación STUN/TURN de candidatos sobre UDP/3478</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/TCP/443 (entrada)</p></td>
<td><p>Cualquiera</p></td>
<td><p>Dirección IP pública de Servidor perimetral Servicio perimetral A/V</p></td>
<td><p>Negociación STUN/TURN de candidatos sobre TCP/443</p></td>
</tr>
<tr class="odd">
<td><p>STUN/MSTURN/TCP/443 (entrada)</p></td>
<td><p>Dirección IP pública de Servidor perimetral Servicio perimetral A/V</p></td>
<td><p>Cualquiera</p></td>
<td><p>Negociación STUN/TURN de candidatos sobre TCP/443</p></td>
</tr>
</tbody>
</table>


### Configuración de puertos del firewall interno necesaria para la Topología perimetral consolidada escalada (carga equilibrada con hardware): Nodo de interfaz interna 2

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
<td><p>Cualquiera (se puede definir como dirección de Servidor front-end o dirección IP virtual del Grupo de servidores front-end que ejecuta el servicio de puerta de enlace XMPP)</p></td>
<td><p>Interfaz interna del Servidor perimetral</p></td>
<td><p>Tráfico XMPP saliente desde el servicio de puerta de enlace XMPP que se ejecuta en el Servidor front-end o en el Grupo de servidores front-end</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>Cualquiera (puede definirse como la dirección IP de servidor del Servidor front-end o el grupo que contiene Almacén de administración central)</p></td>
<td><p>Interfaz interna del Servidor perimetral</p></td>
<td><p>Replicación de los cambios desde el Almacén de administración central al Servidor perimetral</p></td>
</tr>
<tr class="odd">
<td><p>PSOM/MTLS/8057</p></td>
<td><p>Cualquiera (puede definirse como la dirección IP del Director, la dirección IP del Servidor front-end o la dirección IP virtual del grupo)</p></td>
<td><p>Interfaz interna del Servidor perimetral</p></td>
<td><p>Tráfico de conferencia web de la implementación interna a la interfaz interna del Servidor perimetral</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/UDP/3478</p></td>
<td><p>Cualquiera (puede definirse como la dirección IP del Director, la dirección IP del Servidor front-end o la dirección IP virtual del grupo)</p></td>
<td><p>Interfaz interna del Servidor perimetral</p></td>
<td><p>Ruta preferida para una transferencia de medios de A/V entre usuarios internos y externos, Aplicación de sucursal con funciones de supervivencia o Servidor de sucursal con funciones de supervivencia</p></td>
</tr>
<tr class="odd">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>Cualquiera (puede definirse como la dirección IP del Director, la dirección IP del Servidor front-end o la dirección IP virtual del grupo)</p></td>
<td><p>Interfaz interna del Servidor perimetral</p></td>
<td><p>Ruta de acceso de reserva para la transferencia multimedia A/V entre los usuarios internos y externos, Aplicación de sucursal con funciones de supervivencia o Servidor de sucursal con funciones de supervivencia si no se puede establecer la comunicación UDP; TCP se usa para la transferencia de archivos y el uso compartido de escritorio</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50001</p></td>
<td><p>Cualquiera</p></td>
<td><p>Interfaz interna del Servidor perimetral</p></td>
<td><p>Comandos y recopilación del registro del controlador del Servicio de registro centralizado con cmdlets Shell de administración de Lync Server y Servicio de registro centralizado, línea de comandos ClsController (ClsController.exe) o comandos del agente (ClsAgent.exe)</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50002</p></td>
<td><p>Cualquiera</p></td>
<td><p>Interfaz interna del Servidor perimetral</p></td>
<td><p>Comandos y recopilación del registro del controlador del Servicio de registro centralizado con cmdlets Shell de administración de Lync Server y Servicio de registro centralizado, línea de comandos ClsController (ClsController.exe) o comandos del agente (ClsAgent.exe)</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50003</p></td>
<td><p>Cualquiera</p></td>
<td><p>Interfaz interna del Servidor perimetral</p></td>
<td><p>Comandos y recopilación del registro del controlador del Servicio de registro centralizado con cmdlets Shell de administración de Lync Server y Servicio de registro centralizado, línea de comandos ClsController (ClsController.exe) o comandos del agente (ClsAgent.exe)</p></td>
</tr>
</tbody>
</table>


Los equilibradores de carga de hardware tienen requisitos específicos cuando se implementan para proporcionar disponibilidad y equilibrio de carga para Lync Server. En la figura y tablas siguientes se definen los requisitos. Los proveedores de terceros podrían usar una terminología diferente para los requisitos que aquí se definen. Será necesario establecer la correspondencia entre los requisitos de Lync Server y las características y opciones de configuración proporcionadas por el proveedor de su equilibrador de carga de hardware.

A la hora de configurar los equilibradores de carga de hardware, tenga en cuenta los requisitos siguientes:

  - SNAT (traducción de direcciones de red de origen) se puede configurar en el equilibrador de carga de hardware (HLB) para el Servidor perimetral de acceso y el Servicio perimetral de conferencia web

  - SNAT no se puede configurar en el Servicio perimetral A/V; el Servicio perimetral A/V debe responder con la dirección real del servidor, no la dirección IP virtual (VIP) del HLB, para que el cruce simple de UDP sobre NAT (STUN) o el cruce mediante retransmisión NAT (TURN) o federación TURN (FTURN) funcionen correctamente

  - Las direcciones IP públicas se usan en cada interfaz de servidor y en las VIP del HLB, y los requisitos de direcciones IP públicas son N+1, con una dirección IP pública para cada interfaz de servidor real y una para cada VIP de HLB. Si tiene 2 servidores perimetrales en el grupo, el resultado será 9 direcciones IP públicas, de las que 3 se utilizan para las VIP de HLB, y una para cada interfaz de servidor perimetral (un total de seis para los servidores)

  - En el caso del Servidor perimetral de acceso y el Servicio perimetral de conferencia web (y usando NAT en el HLB), el cliente se pone en contacto con la dirección VIP, la dirección VIP cambia la dirección IP de origen del cliente por su propia dirección IP. La interfaz de servidor dirige la dirección de retorno a la dirección VIP, la dirección VIP cambia la dirección de origen desde la dirección IP de la interfaz de servidor y envía el paquete al cliente

  - En el caso del Servicio perimetral A/V, la dirección VIP no debe cambiar la dirección IP de origen y la dirección real del servidor se devuelve directamente al cliente. No se puede configurar NAT en el HLB para el tráfico AV

  - En el caso de AV, el firewall externo retendrá todas las direcciones IP públicas de servidor reales para todos los paquetes

  - Una vez establecida, la comunicación del cliente con el Servicio perimetral A/V se realiza con el servidor real, no con el HLB

  - El perimetral interno hacia servidores y clientes internos deben enrutarse, y se establecen rutas persistentes para todas las redes internas que hospedan servidores o clientes

  - La VIP del Servidor perimetral de acceso del HLB actuará como puerta de enlace predeterminada para cada interfaz de servidor perimetral

![Detalles de puertos y protocolos de servidores perimetrales](images/Gg398739.1c193b80-98ab-4d59-a854-dbfdb5e209e2(OCS.15).jpg "Detalles de puertos y protocolos de servidores perimetrales")

### Configuración de puertos externos necesaria para la Topología perimetral consolidada escalada (carga equilibrada con hardware): IP virtuales de la interfaz externa

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
<td><p>Servicio proxy XMPP (comparte dirección IP con el Servidor perimetral de acceso)</p></td>
<td><p>El servicio proxy XMPP acepta tráfico de los contactos XMPP en las federaciones XMPP definidas</p></td>
</tr>
<tr class="even">
<td><p>XMPP/TCP/5269</p></td>
<td><p>Servicio proxy XMPP (comparte dirección IP con el Servidor perimetral de acceso)</p></td>
<td><p>Cualquiera</p></td>
<td><p>El servicio proxy XMPP envía tráfico a contactos XMPP en federaciones XMPP definidas</p></td>
</tr>
<tr class="odd">
<td><p>SIP/TLS/443 (entrada)</p></td>
<td><p>Cualquiera</p></td>
<td><p>Dirección VIP pública del Servidor perimetral de acceso</p></td>
<td><p>Tráfico SIP de cliente a servidor para el acceso de usuarios remotos</p></td>
</tr>
<tr class="even">
<td><p>Acceso/SIP(MTLS)/TCP/5061</p></td>
<td><p>Cualquiera</p></td>
<td><p>Dirección VIP pública del Servidor perimetral de acceso</p></td>
<td><p>Para la conectividad de MI pública y federada mediante SIP (entrante)</p></td>
</tr>
<tr class="odd">
<td><p>Acceso/SIP(MTLS)/TCP/5061</p></td>
<td><p>Dirección VIP pública del Servidor perimetral de acceso</p></td>
<td><p>Socio federado</p></td>
<td><p>Para la conectividad de MI pública y federada mediante SIP (entrante)</p></td>
</tr>
<tr class="even">
<td><p>Conferencia web/PSOM(TLS)/TCP/443</p></td>
<td><p>Cualquiera</p></td>
<td><p>Dirección VIP pública del Servidor perimetral  Servicio perimetral de conferencia web</p></td>
<td><p>Conferencia web</p></td>
</tr>
<tr class="odd">
<td><p>STUN/MSTURN/UDP/3478 (entrada/salida)</p></td>
<td><p>Cualquiera</p></td>
<td><p>Dirección IP pública de Servidor perimetral Servicio perimetral A/V</p></td>
<td><p>Negociación STUN/TURN de candidatos sobre UDP/3478</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/TCP/443 (entrada)</p></td>
<td><p>Cualquiera</p></td>
<td><p>Dirección IP pública de Servidor perimetral Servicio perimetral A/V</p></td>
<td><p>Negociación STUN/TURN de candidatos sobre TCP/443</p></td>
</tr>
</tbody>
</table>


### Configuración de puertos externos necesaria para la Topología perimetral consolidada escalada (carga equilibrada con hardware): Proxy inverso

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
<td><p>Acceso/SIP(MTLS)/TCP/5061</p></td>
<td><p>Cualquiera (puede definirse como Director, dirección IP virtual de Grupo de directores, Servidor front-end o dirección IP virtual de Grupo de servidores front-end)</p></td>
<td><p>Interfaz VIP interna del Servidor perimetral</p></td>
<td><p>Tráfico SIP saliente (desde Director, dirección IP virtual del Grupo de directores, Servidor front-end o dirección IP virtual del Grupo de servidores front-end) a la dirección VIP perimetral interna</p></td>
</tr>
<tr class="even">
<td><p>Acceso/SIP(MTLS)/TCP/5061</p></td>
<td><p>Interfaz VIP interna del Servidor perimetral</p></td>
<td><p>Cualquiera (puede definirse como Director, dirección IP virtual de Grupo de directores, Servidor front-end o dirección IP virtual de Grupo de servidores front-end)</p></td>
<td><p>Tráfico SIP entrante (a Director, dirección IP virtual del Grupo de directores, Servidor front-end o dirección IP virtual del Grupo de servidores front-end) desde la interfaz interna del Servidor perimetral</p></td>
</tr>
<tr class="odd">
<td><p>SIP/MTLS/TCP/5062</p></td>
<td><p>Cualquiera (puede definirse como dirección IP del Servidor front-end o dirección IP del Grupo de servidores front-end o cualquier Aplicación de sucursal con funciones de supervivencia o Servidor de sucursal con funciones de supervivencia que use este Servidor perimetral)</p></td>
<td><p>Interfaz VIP interna del Servidor perimetral</p></td>
<td><p>Autenticación de usuarios de A/V (servicio de autenticación de A/V) desde Servidor front-end o dirección IP del Grupo de servidores front-end o cualquier Aplicación de sucursal con funciones de supervivencia o Servidor de sucursal con funciones de supervivencia que use este Servidor perimetral</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/UDP/3478</p></td>
<td><p>Cualquiera</p></td>
<td><p>Interfaz VIP interna del Servidor perimetral</p></td>
<td><p>Ruta preferida para una transferencia de medios de A/V entre usuarios internos y externos</p></td>
</tr>
<tr class="odd">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>Cualquiera</p></td>
<td><p>Interfaz VIP interna del Servidor perimetral</p></td>
<td><p>Ruta de reserva para la transferencia de medios de A/V entre usuarios internos y externos si no se puede establecer comunicación UDP, TCP se usa para la transferencia de archivos y uso compartido de escritorio.</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>Interfaz VIP interna del Servidor perimetral</p></td>
<td><p>Cualquiera</p></td>
<td><p>Ruta de reserva para la transferencia de medios de A/V entre usuarios internos y externos si no se puede establecer comunicación UDP, TCP se usa para la transferencia de archivos y uso compartido de escritorio.</p></td>
</tr>
</tbody>
</table>

