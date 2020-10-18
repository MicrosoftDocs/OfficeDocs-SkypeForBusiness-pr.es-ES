---
title: 'Lync Server 2013: requisitos de DNS para el grupo de servidores front-end'
description: 'Lync Server 2013: requisitos de DNS para el grupo de servidores front-end.'
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
ms.openlocfilehash: bfce90eccb8c8dff94d4122c96c4ca68ea9150f1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574336"
---
# <a name="dns-requirements-for-front-end-pool-in-lync-server-2013"></a>Requisitos de DNS para el grupo de servidores front-end en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-07_

Para completar con éxito este procedimiento, debe iniciar sesión en el servidor o dominio, al menos, como miembro del grupo administradores del dominio o como miembro del grupo DnsAdmins.

Debe configurar los registros del sistema de nombres de dominio (DNS) necesarios antes de publicar la topología en el generador de topologías. Además, algunos de los nombres de dominio completos (FQDN) que se usan en la configuración de una implementación de Lync Server 2013 son los FQDN lógicos y no físicos del servidor, por lo que se necesita una configuración DNS adicional antes de la publicación.

<div>


> [!WARNING]  
> Lync Server 2013 no admite dominios con una sola etiqueta. Por ejemplo, se admitiría un bosque con un dominio raíz denominado <STRONG>contoso.local</STRONG>, pero no un dominio raíz denominado <STRONG>local</STRONG>. Para obtener más información, consulte el artículo 300684 de Microsoft Knowledge base, "información sobre la configuración de Windows para dominios con nombres DNS de etiqueta única", at <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=300684"> https://go.microsoft.com/fwlink/p/?linkid=3052&amp ; kbid = 300684</A>.



</div>

<div>


> [!IMPORTANT]  
> El nombre que especifique debe ser idéntico al nombre del equipo configurado en el servidor. De manera predeterminada, el nombre de un equipo que no está unido a un dominio es un nombre corto, en lugar de un nombre de dominio completo (FQDN). Topology Builder usa nombres de dominio completos, no nombres cortos. <STRONG>Use solo caracteres estándar</STRONG> (incluidos A – z, a – z, 0 – 9 y guiones) al asignar FQDN de los servidores que ejecutan Lync Server, servidores perimetrales y grupos de servidores. No utilice caracteres Unicode ni de subrayado. Los DNS externos y las entidades de certificación (CA) públicas no admiten caracteres que no sean estándar en un nombre de dominio completo (cuando dicho nombre debe asignarse al nombre del sujeto en el certificado).



</div>

Antes de trabajar con la topología una vez implementada, asegúrese de que se crean los siguientes registros de DNS y Active Directory (según las necesidades específicas que indiquen):

  - Cada rol de servidor que existirá en la topología se publica como un objeto de Active Directory (una vez que se une el equipo al dominio).

  - Existe un registro DNS A para cada uno de los servidores.

  - Existe un registro SRV de DNS para cada dominio SIP si va a usar el inicio de sesión automático para clientes con el formato \_ sipinternaltls \_ TCP. \<SIP domain\> . Si va a usar la configuración manual para clientes, este registro no es necesario.

  - Un registro DNS A para cada URL sencilla configurada, de las que suelen haber cuatro: reunión, marcado, lwa y programador. Además, existe una dirección URL sencilla de administración que es una dirección URL especial para acceder al panel de control de Lync Server 2013.

  - El servidor que ejecuta SQL Server debe unirse al dominio y ser accesible por el equipo desde el que se publica el generador de topologías.

La tabla sigue las arquitecturas de referencia presentadas en la sección Planeación. Para obtener más información, consulte [escenarios para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) en la documentación referente a la planeación.

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
<th>Asignado a/Comentarios</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS interno</p></td>
<td><p>A</p></td>
<td><p>pool01.contoso.net</p></td>
<td><p>Grupo01 (Equilibrio de carga de DNS). Requiere un registro a de DNS para la dirección IP de cada servidor front-end dentro del grupo de servidores, asignando al FQDN del grupo de servidores.</p></td>
</tr>
<tr class="even">
<td><p>DNS interno</p></td>
<td><p>A</p></td>
<td><p>pool01.contoso.net</p></td>
<td><p>Grupo01 (IP virtual (VIP) del equilibrador de carga de hardware)</p></td>
</tr>
<tr class="odd">
<td><p>DNS interno</p></td>
<td><p>A</p></td>
<td><p>fe01.contoso.net</p>
<p>fe02.contoso.net</p>
<p>fe03.contoso.net</p>
<p>…</p></td>
<td><p>Servidor front-end de grupo01 (nodo 1).</p>
<p>Servidor front-end de grupo01 (nodo 2).</p>
<p>Servidor front-end de grupo01 (nodo 3).</p>
<p>…</p></td>
</tr>
<tr class="even">
<td><p>DNS interno</p></td>
<td><p>A</p></td>
<td><p>fe02.contoso.net</p></td>
<td><p>Servidor front-end de grupo01 (nodo 2).</p></td>
</tr>
<tr class="odd">
<td><p>DNS interno</p></td>
<td><p>A</p></td>
<td><p>lsweb.contoso.net</p></td>
<td><p>Grupo01 (VIP) para el tráfico web cliente-servidor</p></td>
</tr>
<tr class="even">
<td><p>DNS interno</p></td>
<td><p>A</p></td>
<td><p>sqlbe.contoso.net</p></td>
<td><p>Servidor back-end de grupo01 que ejecuta SQL Server 2008 R2.</p></td>
</tr>
<tr class="odd">
<td><p>DNS interno</p></td>
<td><p>A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Es necesario para Lync Phone Edition o el inicio de sesión automático de los clientes sin los registros SRV de DNS y para la coincidencia estricta de dominios. No es necesario en todos los casos.</p></td>
</tr>
<tr class="even">
<td><p>DNS interno</p></td>
<td><p>A</p></td>
<td><p>sip.fabrikam.com</p></td>
<td><p>Asume un segundo dominio SIP. Necesario para Lync Phone Edition, el inicio de sesión automático de los clientes sin los registros SRV de DNS y para la coincidencia estricta de dominios. No es necesario en todos los casos.</p></td>
</tr>
<tr class="odd">
<td><p>DNS interno</p></td>
<td><p>A</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>Dirección URL sencilla para las conferencias de acceso telefónico local publicadas internamente: el servidor front-end (o director, si está instalado) responde a consultas de URL sencillas.</p></td>
</tr>
<tr class="even">
<td><p>DNS interno</p></td>
<td><p>A</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>Dirección URL sencilla para conferencias publicadas internamente: el servidor front-end (o director, si está instalado) responde a consultas de URL sencillas.</p></td>
</tr>
<tr class="odd">
<td><p>DNS interno</p></td>
<td><p>A</p></td>
<td><p>admin.contoso.com</p>
<p>administrar</p></td>
<td><p>Registro opcional, dirección URL sencilla para Lync Server 2013 panel de control publicado internamente: el servidor front-end (o director, si está instalado) responde a consultas de URL sencillas. Se recomienda usar solo el nombre de host (sin nombre de dominio).</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> VIP = dirección IP virtual para el equilibrador de carga de hardware



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
<th>Asignado a/Comentarios</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS interno</p></td>
<td><p>SRV</p></td>
<td><p>_sipinternaltls _sipinternaltls._tcp. contoso. com</p></td>
<td><p>pool01.contoso.com</p></td>
<td><p>5061</p></td>
<td><p>Necesario para la configuración automática de clientes de Lync 2013 para que funcionen internamente.</p></td>
</tr>
<tr class="even">
<td><p>DNS interno</p></td>
<td><p>SRV</p></td>
<td><p>_sipinternaltls _sipinternaltls._tcp. fabrikam. com</p></td>
<td><p>pool01.fabrikam.com</p></td>
<td><p>5061</p></td>
<td><p>Necesario para la configuración automática de clientes de Lync 2013 para que funcionen internamente.</p></td>
</tr>
<tr class="odd">
<td><p>DNS interno</p></td>
<td><p>SRV</p></td>
<td><p>_ntp _ntp._udp. contoso. com</p></td>
<td><p>dc01.contoso.com</p></td>
<td><p>123</p></td>
<td><p>El origen del Protocolo de tiempo de la red (NTP) es necesario para los dispositivos que ejecutan Lync Phone Edition. Internamente, esto deberá apuntar al controlador de dominio. Si el controlador de dominio no se ha definido, intentará usar el servidor NTP time.windows.com</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

