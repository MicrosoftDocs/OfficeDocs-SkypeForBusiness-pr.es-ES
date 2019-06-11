---
title: 'Lync Server 2013: requisitos de DNS para las agrupaciones front end'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS requirements for Front End pools
ms:assetid: ba28919c-fbbe-4c54-8bf9-2b0cd3fa39c7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412910(v=OCS.15)
ms:contentKeyID: 48185228
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03759267ea10a4eaf7046fd25390b45265e479f6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835368"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-front-end-pools-in-lync-server-2013"></a>Requisitos de DNS para las agrupaciones front-end en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-07_

En esta sección se describen los registros del Sistema de nombres de dominio (DNS) necesarios para implementar grupos de servidores front-end.

<div>

## <a name="dns-records-for-front-end-pools"></a>Registros de DNS para grupos de servidores front-end

En la tabla siguiente se especifican los requisitos de DNS para una implementación de grupo front-end de Lync Server 2013.

### <a name="dns-requirements-for-a-front-end-pool"></a>Requisitos de DNS para un grupo de servidores front-end

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
<td><p>Cuando se usa el equilibrio de carga de DNS y un equilibrador de carga de hardware, es necesario hospedar (A) los registros. Cree un registro A interno que resuelva el nombre de dominio completo (FQDN) del grupo de servidores front-end para el equilibrio de carga de DNS. Crear un registro de host (A) interno para los servicios Web internos en la dirección IP virtual (VIP) del equilibrador de carga. Debe usar el nombre de los servicios Web internos tal como se define en el generador de topología.</p>
<p>Por ejemplo, si usa el equilibrio de carga DNS y el equilibrio de carga de hardware, tendrá un registro A para cada servidor front-end de un grupo para el equilibrio de carga DNS y un registro A para los servicios Web internos que apuntan a la IP virtual del equilibrador de carga de hardware. :</p>
<ul>
<li><p>Equilibrio de carga de DNS: Pool01.contoso.net Dirección IP del grupo 10.10.10.5</p>
<div>

> [!WARNING]  
> Cada servidor front-end también tendrá un registro A específico:


</div>
<ol>
<li><p>FE01.contoso.net 10.10.10.1</p></li>
<li><p>FE02.contoso.net 10.10.10.2</p></li>
<li><p>FE03.contoso.net 10.10.10.3</p></li>
<li><p>FE04.contoso.net 10.10.10.4</p></li>
</ol></li>
<li><p>Equilibrio de carga de hardware: WebInternal.contoso.net Dirección IP de HLB VIP 192.168.10.5</p></li>
</ul>
<p>Todo el tráfico, excepto el tráfico HTTP/HTTPS, usará el registro Pool01.contoso.net. El tráfico HTTP/HTTPS utilizará la dirección definida de los servicios web internos, 192.168.10.5.</p></td>
</tr>
<tr class="even">
<td><p>Grupo de servidores front-end con equilibrio de carga de DNS implementado</p></td>
<td><p>Un conjunto de registros A internos que resuelven el FQDN del grupo para la dirección IP de cada uno de los servidores del grupo. Tiene que haber un registro A para cada servidor del grupo.</p></td>
</tr>
<tr class="odd">
<td><p>Grupo de servidores front-end con equilibrio de carga de DNS implementado</p></td>
<td><p>Un conjunto de registros A internos que resuelven el FQDN de cada servidor del grupo a la dirección IP de ese servidor. Para obtener más información, consulte <a href="lync-server-2013-dns-load-balancing.md">equilibrio de carga de DNS en Lync Server 2013</a> en la documentación de planeación.</p></td>
</tr>
<tr class="even">
<td><p>Un grupo de servidores front-end con un solo servidor front-end y una base de datos back-end dedicada sin equilibrador de carga</p></td>
<td><p>Un registro A interno que resuelve el FQDN del grupo de servidores front-end para la dirección IP del único servidor front-end Enterprise Edition.</p></td>
</tr>
<tr class="odd">
<td><p>Inicio de sesión de clientes automático</p></td>
<td><p>Para cada dominio SIP admitido, un registro SRV para _sipinternaltls. _ TCP. &lt;dominio&gt; sobre el puerto 5061 que se asigna al FQDN del grupo de servidores front-end que autentica y redirige las solicitudes de inicio de sesión de los clientes. Para obtener más información, consulte <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">requisitos de DNS para el inicio de sesión automático de cliente en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p>Detección del servicio web de actualización de dispositivos por los dispositivos de comunicaciones unificadas (UC)</p></td>
<td><p>Un registro A interno con el nombre ucupdates-R2. &lt;Dominio&gt; SIP que se resuelve en la dirección IP del grupo de servidores front-end que hospeda el servicio Web de actualización de dispositivos. En caso de que se active un dispositivo de UC en el que nunca ningún usuario inició sesión, el registro A permite al dispositivo detectar el grupo de servidores front-end que hospeda el servicio web de actualización de dispositivos y obtener actualizaciones. De lo contrario, los dispositivos obtienen esta información a través del aprovisionamiento en banda la primera vez que un usuario inicia sesión.</p>
<div>

> [!IMPORTANT]  
> Si tiene una implementación existente de servicio Web de actualización de dispositivos en Lync Server 2010, ya ha creado un registro A interno con el nombre ucupdates. &lt;Dominio&gt;SIP. Para Microsoft Office Communications Server 2007 R2, debe crear un registro DNS adicional con el nombre ucupdates-R2. &lt;Dominio&gt;SIP.


</div></td>
</tr>
<tr class="odd">
<td><p>Un proxy inverso compatible con el tráfico HTTP</p></td>
<td><p>Un registro A externo que resuelve el FQDN externo de la granja de servidores web en la dirección IP externa del proxy inverso. Los clientes y los dispositivos de UC usan este registro para conectarse al proxy inverso. Para obtener más información, consulte <a href="lync-server-2013-determine-dns-requirements.md">determinar los requisitos de DNS para Lync Server 2013</a> en la documentación de planeación.</p></td>
</tr>
</tbody>
</table>


La tabla siguiente muestra un ejemplo de los registros de DNS necesarios para el FQDN interno de la granja de servidores web.

### <a name="example-dns-records-for-internal-web-farm-fqdn"></a>Ejemplo de los registros de DNS para el FQDN interno de la granja de servidores web

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>FQDN interno de la granja de servidores web</th>
<th>FQDN del grupo de servidores</th>
<th>Registro(s) A de DNS</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>webcon.contoso.com</p></td>
<td><p>ee-pool.contoso.com</p></td>
<td><p>Registro A de DNS para ee-pool.contoso.com que se resuelve en la dirección VIP del equilibrador de carga que usan los servidores front-end.</p>
<p>Registro A de DNS para webcon.contoso.com que se resuelve en la dirección VIP del equilibrador de carga que usan los servidores front-end.</p></td>
</tr>
<tr class="even">
<td><p>ee-pool.contoso.com</p></td>
<td><p>ee-pool.contoso.com</p></td>
<td><p>Registro A de DNS para ee-pool.contoso.com que se resuelve en la dirección IP virtual (VIP) del equilibrador de carga que usan los servidores front-end Enterprise Edition en el grupo de servidores front-end.</p>
<p>Tenga en cuenta que si usa el equilibrio de carga de DNS en este grupo, su grupo de servidores front-end y la granja de servidores web internos no podrán tener el mismo FQDN.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

