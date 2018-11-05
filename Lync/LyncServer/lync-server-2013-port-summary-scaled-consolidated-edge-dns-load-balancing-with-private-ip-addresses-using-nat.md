---
title: "Resumen puerto - Servidor perim. ampliado, equil. carga DNS con IP privadas con NAT"
TOCTitle: Resumen de puerto - Servidor perimetral consolidado ampliado, equilibrio de carga DNS con direcciones IP privadas mediante NAT
ms:assetid: a296c2af-54d4-4b4f-9795-9191baf688cb
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg412756(v=OCS.15)
ms:contentKeyID: 48276254
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Resumen de puerto - Servidor perimetral consolidado ampliado, equilibrio de carga DNS con direcciones IP privadas mediante NAT en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

La funcionalidad del servidor perimetral Lync Server 2013 descrita en la arquitectura de este escenario es muy similar a lo implementado en Lync Server 2010. La adición más notable es el puerto **5269 sobre la entrada TCP** para el protocolo extensible de mensajería y presencia (XMPP). Lync Server 2013 implementa de manera opcional un proxy XMPP proxy en Servidor perimetral o en Grupo de servidores perimetrales y el servidor de puerta de enlace XMPP en Servidor front-end o Grupo de servidores front-end.

Además de IPv4, el Servidor perimetral ahora admite IPv6. Para mayor claridad, en los escenarios solo se usa IPv4.

**Red de perímetro empresarial para servidores perimetrales consolidados escalados con direcciones IP privadas que usan NAT**

![Servidor perimetral consolidado escalado](images/Gg412756.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "Servidor perimetral consolidado escalado")

## Detalles de protocolo y puerto

Se recomienda abrir solamente los puertos necesarios para admitir la funcionalidad para la que proporcione acceso externo.

Para que el acceso remoto funcione para cualquier servicio perimetral, es obligatorio que el tráfico SIP pueda fluir de forma bidireccional, tal como se muestra en la figura Tráfico perimetral entrante/saliente. Dicho de otra forma, la mensajería SIP hacia y desde el servicio perimetral de acceso interviene en mensajería instantánea, presencia, conferencia web, audio y vídeo (A/V) y federación.

### Resumen de firewall para servidor perimetral consolidado escalado, equilibrio de carga de DNS con direcciones IP privadas que usan NAT: interfaz externa - nodo 1 y nodo 2 (ejemplo)

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
<td><p>Acceso/HTTP/TCP/80</p></td>
<td><p>Servidor perimetral Servidor perimetral de acceso</p></td>
<td><p>Cualquiera</p></td>
<td><p>Revocación de certificados/comprobación y recuperación de CRL</p></td>
</tr>
<tr class="even">
<td><p>Acceso/DNS/TCP/53</p></td>
<td><p>Servidor perimetral Servidor perimetral de acceso</p></td>
<td><p>Cualquiera</p></td>
<td><p>Consulta DNS sobre TCP</p></td>
</tr>
<tr class="odd">
<td><p>Acceso/DNS/UDP/53</p></td>
<td><p>Servidor perimetral Servidor perimetral de acceso</p></td>
<td><p>Cualquiera</p></td>
<td><p>Consulta DNS sobre UDP</p></td>
</tr>
<tr class="even">
<td><p>SIP/TLS/443 (entrada)</p></td>
<td><p>Cualquiera</p></td>
<td><p>Servidor perimetral Servidor perimetral de acceso</p></td>
<td><p>Tráfico SIP de cliente a servidor para el acceso de usuarios remotos</p></td>
</tr>
<tr class="odd">
<td><p>Acceso/SIP(MTLS)/TCP/5061</p></td>
<td><p>Cualquiera</p></td>
<td><p>Servicio de servidor perimetral de acceso</p></td>
<td><p>Para la conectividad de MI pública y federada mediante SIP</p></td>
</tr>
<tr class="even">
<td><p>Acceso/SIP(MTLS)/TCP/5061</p></td>
<td><p>Servidor perimetral Servidor perimetral de acceso</p></td>
<td><p>Cualquiera</p></td>
<td><p>Para la conectividad de MI pública y federada mediante SIP</p></td>
</tr>
<tr class="odd">
<td><p>Conferencia web/PSOM(TLS)/TCP/443</p></td>
<td><p>Cualquiera</p></td>
<td><p>Servidor perimetral Servicio perimetral de conferencia web</p></td>
<td><p>Conferencia web</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50.000-59.999</p></td>
<td><p>Servidor perimetral Servicio perimetral A/V</p></td>
<td><p>Cualquiera</p></td>
<td><p>Necesario para federación con socios que ejecuten Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 y Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/UDP/50.000-59.999</p></td>
<td><p>Servidor perimetral Servicio perimetral A/V</p></td>
<td><p>Cualquiera</p></td>
<td><p>Solo se necesita para federación con socios que todavía ejecuten Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50.000-59.999</p></td>
<td><p>Cualquiera</p></td>
<td><p>Servidor perimetral Servicio perimetral A/V</p></td>
<td><p>Necesario solo para compartir escritorio con socios que ejecuten Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/UDP/50.000-59.999</p></td>
<td><p>Cualquiera</p></td>
<td><p>Servidor perimetral Servicio perimetral A/V</p></td>
<td><p>Necesario solo para compartir escritorio con socios que ejecuten Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/UDP/3478 (entrada/salida)</p></td>
<td><p>Servidor perimetral Servicio perimetral A/V</p></td>
<td><p>Cualquiera</p></td>
<td><p>3478 saliente se usa para averiguar la versión del Servidor perimetral con el que se está comunicando Lync ServerLync Server 2013, y también para el tráfico de medios de Servidor perimetral-a- Servidor perimetral. Necesario para federación con Lync Server 2010, Windows Live Messenger y Office Communications Server 2007 R2, y también si hay implementados varios Grupos de servidores perimetrales en una compañía.</p></td>
</tr>
<tr class="odd">
<td><p>STUN/MSTURN/UDP/3478 (entrada/salida)</p></td>
<td><p>Cualquiera</p></td>
<td><p>Servidor perimetral Servicio perimetral A/V</p></td>
<td><p>Negociación STUN/TURN de candidatos sobre UDP/3478</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/TCP/443 (entrada)</p></td>
<td><p>Cualquiera</p></td>
<td><p>Servidor perimetral Servicio perimetral A/V</p></td>
<td><p>Negociación STUN/TURN de candidatos sobre TCP/443</p></td>
</tr>
<tr class="odd">
<td><p>STUN/MSTURN/TCP/443 (entrada)</p></td>
<td><p>Servicio perimetral de A/V de Servidor perimetral</p></td>
<td><p>Cualquiera</p></td>
<td><p>Negociación STUN/TURN de candidatos sobre TCP/443</p></td>
</tr>
</tbody>
</table>


### Resumen de firewall para servidor perimetral consolidado escalado, equilibrio de carga de DNS con direcciones IP privadas que usan NAT: interfaz interna - nodo 1 y nodo 2 (ejemplo)

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
<td><p>Cualquiera (se puede definir como dirección de Servidor front-end o como dirección IP de Grupo de servidores front-end que ejecuta el servicio de puerta de enlace XMPP)</p></td>
<td><p>Dirección IP de la interfaz interna de Servidor perimetral</p></td>
<td><p>Tráfico XMPP saliente desde el servicio de puerta de enlace XMPP que se ejecuta en el Servidor front-end o en el Grupo de servidores front-end</p></td>
</tr>
<tr class="even">
<td><p>SIP/MTLS/TCP/5061</p></td>
<td><p>Cualquiera (puede definirse como Director, dirección IP de Grupo de directores, Servidor front-end o dirección IP de Grupo de servidores front-end)</p></td>
<td><p>Interfaz interna del Servidor perimetral</p></td>
<td><p>Tráfico SIP saliente (desde Director, dirección IP de Grupo de directores, Servidor front-end o dirección IP de Grupo de servidores front-end) hasta la interfaz interna de Servidor perimetral</p></td>
</tr>
<tr class="odd">
<td><p>SIP/MTLS/TCP/5061</p></td>
<td><p>Interfaz interna del Servidor perimetral</p></td>
<td><p>Cualquiera (puede definirse como Director, dirección IP de Grupo de directores, Servidor front-end o dirección IP de Grupo de servidores front-end)</p></td>
<td><p>Tráfico SIP entrante (hasta Director, la dirección IP de Grupo de directores, Servidor front-end o la dirección IP de Grupo de servidores front-end) desde la interfaz interna de Servidor perimetral</p></td>
</tr>
<tr class="even">
<td><p>PSOM/MTLS/8057</p></td>
<td><p>Cualquiera (puede definirse como dirección IP de Servidor front-end o cada dirección IP de Servidor front-end en un Grupo de servidores front-end)</p></td>
<td><p>Interfaz interna del Servidor perimetral</p></td>
<td><p>Tráfico de conferencia web desde Servidor front-end o cada Servidor front-end de un grupo hasta la interfaz interna de Servidor perimetral</p></td>
</tr>
<tr class="odd">
<td><p>SIP/MTLS/TCP/5062</p></td>
<td><p>Cualquiera (puede definirse como dirección IP del Servidor front-end o dirección IP del Grupo de servidores front-end o cualquier Aplicación de sucursal con funciones de supervivencia o Servidor de sucursal con funciones de supervivencia que use este Servidor perimetral)</p></td>
<td><p>Interfaz interna del Servidor perimetral</p></td>
<td><p>Autenticación de usuarios de A/V (servicio de autenticación de A/V) desde Servidor front-end o dirección IP del Grupo de servidores front-end o cualquier Aplicación de sucursal con funciones de supervivencia o Servidor de sucursal con funciones de supervivencia que use este Servidor perimetral</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/UDP/3478</p></td>
<td><p>Cualquiera</p></td>
<td><p>Interfaz interna del Servidor perimetral</p></td>
<td><p>Ruta preferida para una transferencia de medios de A/V entre usuarios internos y externos, Aplicación de sucursal con funciones de supervivencia o Servidor de sucursal con funciones de supervivencia</p></td>
</tr>
<tr class="odd">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>Cualquiera</p></td>
<td><p>Interfaz interna del Servidor perimetral</p></td>
<td><p>Ruta de acceso de reserva para la transferencia multimedia A/V entre los usuarios internos y externos, Aplicación de sucursal con funciones de supervivencia o Servidor de sucursal con funciones de supervivencia si no se puede establecer la comunicación UDP; TCP se usa para la transferencia de archivos y el uso compartido de escritorio</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>Cualquiera (puede definirse como dirección IP de Servidor front-end o grupo de servidores que mantienen el Almacén de administración central)</p></td>
<td><p>Interfaz interna del Servidor perimetral</p></td>
<td><p>Replicación de los cambios desde el Almacén de administración central al Servidor perimetral</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50001</p></td>
<td><p>Cualquiera</p></td>
<td><p>Interfaz interna del Servidor perimetral</p></td>
<td><p>Comandos y recopilación del registro del controlador del Servicio de registro centralizado con cmdlets Shell de administración de Lync Server y Servicio de registro centralizado, línea de comandos ClsController (ClsController.exe) o comandos del agente (ClsAgent.exe)</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50002</p></td>
<td><p>Cualquiera</p></td>
<td><p>Interfaz interna del Servidor perimetral</p></td>
<td><p>Comandos y recopilación del registro del controlador del Servicio de registro centralizado con cmdlets Shell de administración de Lync Server y Servicio de registro centralizado, línea de comandos ClsController (ClsController.exe) o comandos del agente (ClsAgent.exe)</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50003</p></td>
<td><p>Cualquiera</p></td>
<td><p>Interfaz interna del Servidor perimetral</p></td>
<td><p>Comandos y recopilación del registro del controlador del Servicio de registro centralizado con cmdlets Shell de administración de Lync Server y Servicio de registro centralizado, línea de comandos ClsController (ClsController.exe) o comandos del agente (ClsAgent.exe)</p></td>
</tr>
</tbody>
</table>


## Resumen del firewall para federación


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
<td><p>Dirección IP pública de Servidor perimetral de acceso</p></td>
<td><p>Cualquiera</p></td>
<td><p>Para la conectividad de MI pública y federada mediante SIP</p></td>
</tr>
</tbody>
</table>


## Resumen de firewall: Conectividad de mensajería instantánea pública


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
<td><p>Socios de conectividad de MI pública</p></td>
<td><p>Servidor perimetral Servidor perimetral de acceso</p></td>
<td><p>Para la conectividad de MI pública y federada mediante SIP</p></td>
</tr>
<tr class="even">
<td><p>Acceso/SIP(MTLS)/TCP/5061</p></td>
<td><p>Servidor perimetral Servidor perimetral de acceso</p></td>
<td><p>Socios de conectividad de MI pública</p></td>
<td><p>Para la conectividad de MI pública y federada mediante SIP</p></td>
</tr>
<tr class="odd">
<td><p>SIP/TLS/443 (entrada)</p></td>
<td><p>Clientes</p></td>
<td><p>Servidor perimetral Servidor perimetral de acceso</p></td>
<td><p>Tráfico SIP de cliente a servidor para el acceso de usuarios remotos</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50.000-59.999</p></td>
<td><p>Servidor perimetral Servicio perimetral A/V</p></td>
<td><p>Clientes de Live Messenger</p></td>
<td><p>Usado para sesiones de A/V con Windows Live Messenger si se ha configurado la conectividad de MI.</p></td>
</tr>
<tr class="odd">
<td><p>STUN/MSTURN/UDP/3478 (entrada/salida)</p></td>
<td><p>Servidor perimetral Servicio perimetral A/V</p></td>
<td><p>Clientes de Live Messenger</p></td>
<td><p>Obligatorio para la conectividad de MI pública con Windows Live Messenger</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/UDP/3478 (entrada/salida)</p></td>
<td><p>Clientes de Live Messenger</p></td>
<td><p>Servidor perimetral Servicio perimetral A/V</p></td>
<td><p>Obligatorio para la conectividad de MI pública con Windows Live Messenger</p></td>
</tr>
</tbody>
</table>


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
<td><p>Dirección IP de interfaz de Servidor perimetral   Servidor perimetral de acceso</p></td>
<td><p>Puerto de comunicación estándar de servidor a servidor para XMPP. Permite la comunicación con el servidor proxy XMPP de Servidor perimetral desde socios XMPP federados</p></td>
</tr>
<tr class="even">
<td><p>XMPP/TCP/5269</p></td>
<td><p>Dirección IP de interfaz de Servidor perimetral   Servidor perimetral de acceso</p></td>
<td><p>Cualquiera</p></td>
<td><p>Puerto de comunicación estándar de servidor a servidor para XMPP. Permite la comunicación con el servidor proxy XMPP de Servidor perimetral para socios XMPP federados</p></td>
</tr>
<tr class="odd">
<td><p>XMPP/MTLS/TCP/23456</p></td>
<td><p>Cualquiera</p></td>
<td><p>Cada IP de interfaz interna de Servidor perimetral</p></td>
<td><p>Tráfico XMPP interno desde la puerta de enlace XMPP en el Servidor front-end o Grupo de servidores front-end, a la dirección IP interna de Servidor perimetral o la dirección IP interna de cada miembro de Grupo de servidores perimetrales</p></td>
</tr>
</tbody>
</table>

