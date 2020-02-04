---
title: 'Lync Server 2013: Requisitos de DNS para el grupo de servidores front-end'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for Front End pool
ms:assetid: 02d2aa6b-9e01-437b-a2df-00590280150d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398082(v=OCS.15)
ms:contentKeyID: 48183249
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 252bacd9818676155dcab0f84e3e1c5fcdb31b5d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765298"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-front-end-pool-in-lync-server-2013"></a>Requisitos de DNS para el grupo de servidores front-end en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-07_

Para completar correctamente este procedimiento, debe haber iniciado sesión en el servidor o dominio como miembro del grupo administradores de dominio o en miembro del grupo DnsAdmins.

Debe configurar los registros de sistema de nombres de dominio (DNS) necesarios antes de publicar su topología en el generador de topología. Además, algunos de los nombres de dominio completos (FQDN) que se usan en la configuración de una implementación de Lync Server 2013 son lógicos y no FQDN de servidor físico, por lo que es necesaria una configuración DNS adicional antes de la publicación.

<div>


> [!WARNING]  
> Lync Server 2013 no admite dominios con etiqueta única. Por ejemplo, un bosque con un dominio raíz denominado <STRONG>contoso. local</STRONG> es compatible, pero no se admite un dominio raíz denominado <STRONG>local</STRONG> . Para obtener más información, consulte el artículo 300684 de Microsoft Knowledge base, "información sobre la configuración de Windows para dominios con nombres DNS de etiqueta única", en <A class=uri href="http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=300684"> http://go.microsoft.com/fwlink/p/?linkid=3052&amp; kbid = 300684</A>.



</div>

<div>


> [!IMPORTANT]  
> El nombre que especifique debe ser idéntico al nombre de equipo configurado en el servidor. De forma predeterminada, el nombre de equipo de un equipo que no está unido a un dominio es un nombre corto, no un FQDN. El Generador de topologías usa nombres de dominio completos, no nombres cortos. <STRONG>Use solo caracteres estándar</STRONG> (incluidos A-z, a-z, 0-9 y guiones) al asignar FQDN de los servidores que ejecutan Lync Server, servidores perimetrales y grupos. No utilice caracteres Unicode ni de subrayado. A menudo, los caracteres no estándar de un FQDN no son admitidos por el DNS externo y las entidades de certificación públicas (CA) (cuando se debe asignar el FQDN al SN en el certificado).



</div>

Antes de operar la topología después de haberla implementado, asegúrese de crear los siguientes registros de Active Directory y DNS (según las necesidades de características específicas que determinen):

  - Cada rol de servidor que existirá en la topología se publica como un objeto de Active Directory (una vez que se une el equipo con el dominio).

  - Existe un registro A de DNS para cada servidor.

  - Existe un registro SRV de DNS para cada dominio SIP si piensa usar el inicio de sesión automático para clientes en forma \_de\_sipinternaltls TCP. \<Dominio\>SIP. Si va a usar la configuración manual para clientes, este registro no es necesario.

  - Un registro A de DNS para cada dirección URL simple configurada, de la que normalmente hay cuatro: reunirse, marcación, LWA y programador. Además, existe la dirección URL simple de administrador, que es una dirección URL especial para el acceso al panel de control de Lync Server 2013.

  - El servidor que ejecuta SQL Server debe estar unido al dominio y ser accesible desde el equipo desde el que se está publicando el generador de topología.

La tabla sigue las arquitecturas de referencia presentadas en la sección de planificación. Para obtener más información, vea [escenarios de acceso de usuarios externos en Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) en la documentación de planeación.

<div id="sectionSection0" class="section">

### <a name="dns-records-required-for-the-front-end-pool"></a>Registros DNS necesarios para el grupo de servidores front-end

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Ubicación</th>
<th>Tipo</th>
<th>FQDN</th>
<th>Se asigna a/comentarios</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS interno</p></td>
<td><p>A</p></td>
<td><p>pool01.contoso.net</p></td>
<td><p>Pool01 (equilibrio de carga de DNS). Requiere un registro DNS A para la dirección IP de cada servidor front-end dentro del grupo, que se asigna al FQDN del grupo.</p></td>
</tr>
<tr class="even">
<td><p>DNS interno</p></td>
<td><p>A</p></td>
<td><p>pool01.contoso.net</p></td>
<td><p>Pool01 (IP virtual (VIP) de equilibrador de carga de hardware).</p></td>
</tr>
<tr class="odd">
<td><p>DNS interno</p></td>
<td><p>A</p></td>
<td><p>fe01.contoso.net</p>
<p>fe02.contoso.net</p>
<p>fe03.contoso.net</p>
<p>…</p></td>
<td><p>Servidor front-end de Pool01 (nodo 1).</p>
<p>Servidor front-end Pool01 (nodo 2).</p>
<p>Servidor front-end Pool01 (nodo 3).</p>
<p>…</p></td>
</tr>
<tr class="even">
<td><p>DNS interno</p></td>
<td><p>A</p></td>
<td><p>fe02.contoso.net</p></td>
<td><p>Servidor front-end Pool01 (nodo 2).</p></td>
</tr>
<tr class="odd">
<td><p>DNS interno</p></td>
<td><p>A</p></td>
<td><p>lsweb.contoso.net</p></td>
<td><p>Pool01 (VIP) para el tráfico web entre clientes y servidores.</p></td>
</tr>
<tr class="even">
<td><p>DNS interno</p></td>
<td><p>A</p></td>
<td><p>sqlbe.contoso.net</p></td>
<td><p>Servidor de Pool01 back end con SQL Server 2008 R2.</p></td>
</tr>
<tr class="odd">
<td><p>DNS interno</p></td>
<td><p>A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Necesario para Lync Phone Edition o el inicio de sesión automático de clientes sin registros SRV de DNS y para una coincidencia de dominios estricta. No se requiere en todos los casos.</p></td>
</tr>
<tr class="even">
<td><p>DNS interno</p></td>
<td><p>A</p></td>
<td><p>sip.fabrikam.com</p></td>
<td><p>Supone que se trata de un segundo dominio SIP. Necesario para Lync Phone Edition, el inicio de sesión automático de clientes sin los registros SRV de DNS y para la coincidencia estricta de dominios. No se requiere en todos los casos.</p></td>
</tr>
<tr class="odd">
<td><p>DNS interno</p></td>
<td><p>A</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>Dirección URL simple para conferencias de acceso telefónico local publicadas internamente: el servidor front-end (o director, si está instalado) responde a consultas de URL simples.</p></td>
</tr>
<tr class="even">
<td><p>DNS interno</p></td>
<td><p>A</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>Dirección URL simple para conferencias publicadas internamente: el servidor front-end (o director, si está instalado) responde a consultas de URL simples.</p></td>
</tr>
<tr class="odd">
<td><p>DNS interno</p></td>
<td><p>A</p></td>
<td><p>admin.contoso.com</p>
<p>administradores</p></td>
<td><p>Registro opcional, dirección URL simple para Lync Server 2013 panel de control publicado internamente: el servidor front-end (o director, si está instalado) responde a consultas de URL simples. Se recomienda usar solo el nombre de host (sin nombre de dominio).</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> VIP = dirección IP virtual de equilibrador de carga de hardware



</div>

</div>

<div>

## <a name="dns-srv-records-for-the-front-end-pool"></a>Registros SRV de DNS para el grupo de servidores front-end


<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th>Ubicación</th>
<th>Tipo</th>
<th>FQDN</th>
<th>FQDN de destino</th>
<th>Puerto</th>
<th>Se asigna a/comentarios</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS interno</p></td>
<td><p>SRV</p></td>
<td><p>_sipinternaltls. _tcp. contoso. com</p></td>
<td><p>pool01.contoso.com</p></td>
<td><p>5061</p></td>
<td><p>Necesario para que la configuración automática de los clientes de Lync 2013 funcione internamente.</p></td>
</tr>
<tr class="even">
<td><p>DNS interno</p></td>
<td><p>SRV</p></td>
<td><p>_sipinternaltls. _tcp. fabrikam. com</p></td>
<td><p>pool01.fabrikam.com</p></td>
<td><p>5061</p></td>
<td><p>Necesario para que la configuración automática de los clientes de Lync 2013 funcione internamente.</p></td>
</tr>
<tr class="odd">
<td><p>DNS interno</p></td>
<td><p>SRV</p></td>
<td><p>_ntp. _udp. contoso. com</p></td>
<td><p>dc01.contoso.com</p></td>
<td><p>123</p></td>
<td><p>El origen de protocolo de tiempo de red (NTP) es necesario para los dispositivos que ejecutan Lync Phone Edition. Internamente, debe apuntar al controlador de dominio. Si el controlador de dominio no está definido, intentará usar el servidor NTP time.windows.com.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

