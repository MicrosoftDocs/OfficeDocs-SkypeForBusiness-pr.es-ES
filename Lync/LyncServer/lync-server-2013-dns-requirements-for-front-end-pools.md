---
title: Requisitos DNS para grupos Front-End
TOCTitle: Requisitos DNS para grupos Front-End
ms:assetid: ba28919c-fbbe-4c54-8bf9-2b0cd3fa39c7
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg412910(v=OCS.15)
ms:contentKeyID: 48276490
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Requisitos DNS para grupos Front-End

 

_**Última modificación del tema:** 2015-03-09_

Esta sección describe los registros del Sistema de nombres de dominio (DNS) necesarios para implementar grupos de servidores front-end.

## Registros DNS para grupos de servidores front-end

La tabla siguiente especifica los requisitos de DNS para la implementación de un grupo de servidores front-end de Lync Server 2013.

### Requisitos de DNS para un grupo de servidores front-end

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Escenario de implementación</th>
<th>Requisito de DNS</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Grupo de servidores front-end con varios servidores front-end y un equilibrador de carga de hardware (independientemente de si el equilibrio de carga de DNS también está implementado en este grupo)</p></td>
<td><p>Al usar tanto el equilibrio de carga de DNS como un equilibrador de carga de hardware, se necesitan registros de host (A). Cree un registro A interno que resuelva el nombre de dominio completo (FQDN) del grupo de servidores front-end para el equilibrio de carga de DNS. Cree un registro de host (A) para los servicios web internos que apunte a la dirección IP virtual (VIP) del equilibrador de carga. Debe usar el nombre de servicios web internos definido en la Generador de topologías.</p>
<p>Si, por ejemplo, usa tanto el equilibrio de carga de DNS como el equilibrio de carga de hardware, tendrá un registro A por cada Servidor front-end de un grupo para el equilibrio de carga de DNS, así como un registro A para los servicios web internos que apuntan a la IP virtual del equilibrador de carga de hardware:</p>
<ul>
<li><p>Equilibrio de carga de DNS:   Grupo01.contoso.net   Dirección IP del grupo   10.10.10.5</p>

> [!WARNING]  
> Cada Servidor front-end tendrá también un registro A distinto:

<ol>
<li><p>FE01.contoso.net    10.10.10.1</p></li>
<li><p>FE02.contoso.net    10.10.10.2</p></li>
<li><p>FE03.contoso.net    10.10.10.3</p></li>
<li><p>FE04.contoso.net    10.10.10.4</p></li>
</ol></li>
<li><p>Equilibrio de carga de hardware:   Webinterno.contoso.net   Dirección IP de HLB VIP   192.168.10.5</p></li>
</ul>
<p>Todo el tráfico, excepto el tráfico HTTP/HTTPS, usará el registro Grupo01.contoso.net. El tráfico HTTP/HTTPS utilizará la dirección de los servicios web internos, 192.168.10.5.</p></td>
</tr>
<tr class="even">
<td><p>Grupo de servidores front-end con equilibrio de carga de DNS implementado</p></td>
<td><p>Un conjunto de registros A internos que resuelven el FQDN del grupo para la dirección IP de cada uno de los servidores del grupo. Debe haber un registro A para cada servidor del grupo.</p></td>
</tr>
<tr class="odd">
<td><p>Grupo de servidores front-end con equilibrio de carga de DNS implementado</p></td>
<td><p>Un conjunto de registros A internos que resuelven el FQDN de cada uno de los servidores del grupo para la dirección IP de cada servidor. Para más información, consulte <a href="lync-server-2013-dns-load-balancing.md">Equilibrio de carga de DNS en Lync Server 2013</a> en la documentación de planeación.</p></td>
</tr>
<tr class="even">
<td><p>Un grupo de servidores front-end con un solo servidor front-end y una base de datos back-end dedicada sin equilibrador de carga</p></td>
<td><p>Un registro A interno que resuelve el FQDN del grupo de servidores front-end para la dirección IP del único servidor front-end Enterprise Edition.</p>
<p></p></td>
</tr>
<tr class="odd">
<td><p>Inicio de sesión de clientes automático</p></td>
<td><p>Por cada dominio SIP admitido, un registro SRV para _sipinternaltls._tcp.&lt;dominio&gt; en el puerto 5061 que se asigna al FQDN del grupo de servidores front-end responsable de autenticar y redirigir las solicitudes de los clientes para el inicio de sesión. Para más información, consulte <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">Requisitos DNS para inicio de sesión automática del cliente en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p>Detección del servicio web de actualización de dispositivos por los dispositivos de comunicaciones unificadas (UC)</p></td>
<td><p>Un registro A interno con el nombre ucupdates-r2.&lt;dominio SIP&gt; que se resuelve para la dirección IP del grupo de servidores front-end que hospeda el servicio web de actualización de dispositivos. En caso de que se active un dispositivo de UC en el que ningún usuario se ha registrado, el registro A permite al dispositivo detectar el grupo de servidores front-end que hospeda el servicio web de actualización de dispositivos, y obtener actualizaciones. En cualquier caso, los dispositivos obtienen esta información a través del aprovisionamiento en banda la primera vez que un usuario inicia sesión.</p>
<div>

> [!IMPORTANT]  
> Si cuenta con una implementación existente del servicio web de actualización de dispositivos en Lync Server 2010, ya habrá creado un registro A interno con el nombre ucupdates.<em>&lt;dominio SIP&gt;</em>. Para Microsoft Office Communications Server 2007 R2, debe crear otro registro DNS A con el nombre ucupdates-r2.<em>&lt;dominio SIP&gt;</em>.


</div></td>
</tr>
<tr class="odd">
<td><p>Un proxy inverso compatible con el tráfico HTTP</p></td>
<td><p>Un registro A externo que resuelve el FQDN externo de la granja de servidores web en la dirección IP externa del proxy inverso. Los clientes y los dispositivos de CU usan este registro para conectarse al proxy inverso. Para más información, consulte <a href="lync-server-2013-determine-dns-requirements.md">Determinar los requisitos DNS para Lync Server 2013</a> en la documentación de planeación.</p></td>
</tr>
</tbody>
</table>


La tabla siguiente muestra un ejemplo de los registros DNS necesarios para el FQDN interno de la granja de servidores web.

### Ejemplo de los registros DNS para el FQDN interno de la granja de servidores web

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>FQDN interno de la granja de servidores web</th>
<th>FQDN del grupo</th>
<th>Registro(s) DNS A</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>webcon.contoso.com</p></td>
<td><p>ee-pool.contoso.com</p></td>
<td><p>Registro DNS A para ee-pool.contoso.com que se resuelve para la dirección VIP del equilibrador de carga que usan los servidores front-end.</p>
<p>Registro DNS A para webcon.contoso.com que se resuelve para la dirección VIP del equilibrador de carga que usan los servidores front-end.</p></td>
</tr>
<tr class="even">
<td><p>ee-pool.contoso.com</p></td>
<td><p>ee-pool.contoso.com</p></td>
<td><p>Registro DNS A para ee-pool.contoso.com que se resuelve para la dirección IP virtual (VIP) del equilibrador de carga que usan los servidores front-end Enterprise Edition en el grupo de servidores front-end.</p>
<p>Tenga en cuenta que si usa el equilibrio de carga de DNS en este grupo, su grupo de servidores front-end y la granja de servidores web internos no podrán tener el mismo FQDN.</p></td>
</tr>
</tbody>
</table>

