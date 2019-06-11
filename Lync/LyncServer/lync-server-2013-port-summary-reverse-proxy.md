---
title: 'Lync Server 2013: Resumen de puerto - Proxy inverso'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - Reverse proxy
ms:assetid: 59b9ac3c-3e6f-4776-b366-174f0dd1f2eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204932(v=OCS.15)
ms:contentKeyID: 48184251
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a86b993a35210934f5ebef61464c11a153bf297
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824179"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---reverse-proxy-in-lync-server-2013"></a>Resumen de puerto - Proxy inverso en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-15_

El proxy inverso tiene requisitos mínimos para el firewall y el puerto/protocolo.

  - Los requisitos del firewall externo son HTTPS/TCP/443 y el HTTP/TCP/80 opcional. HTTPS se usa para comunicaciones seguras SSL y TLS a través del proxy inverso. HTTP se usa si elige permitir el acceso al servicio de detección automática al modificar certificados que puede resultar difícil o no estar justificado.

  - Los clientes esperan ponerse en contacto con el servidor de Office Web Apps en HTTPS. El servidor de Office Web Apps Server espera la comunicación de los clientes internos en HTTPS/TCP/443. La configuración recomendada es permitir HTTPS/TCP/443 desde el proxy inverso hasta el servidor de Office Web Apps.

  - El puerto 8080 se usa para enrutar el tráfico de la interfaz interna de proxy invertida al servidor front-end, la IP virtual de la agrupación de front-end (VIP) o el director opcional o VIP del grupo de directores. El puerto TCP 8080 es necesario para que los dispositivos móviles que ejecutan Lync encuentren el servicio de detección automática en situaciones en las que no es deseable modificar el certificado de la regla de publicación de servicio Web externo (por ejemplo, si tiene un gran número de dominios SIP). Si elige adquirir certificados nuevos con las entradas de SAN necesarias, el puerto TCP 8080 no es necesario y es opcional.

  - El puerto 4443 se usa para el tráfico de la interfaz interna de proxy invertida al servidor front-end, la IP virtual de grupo de servidores front-end (VIP) o el director opcional o VIP del grupo de directores
    
    ![13142405-d5c9-45b7-a8b7-a8c89f09c97c] (images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")  
    
    <div>
    

    > [!WARNING]  
    > No confunda el 4443 sobre TCP del proxy inverso en la implementación interna para el puerto 4443 sobre el tráfico TCP desde el servidor Standard Edition o el grupo de servidores front-end que administra la función de almacén de administración central.

    
    </div>

<div>

## <a name="port-and-protocol-details"></a>Detalles de protocolo y puerto

### <a name="firewall-details-for-reverse-proxy-server-external-interface"></a>Detalles del firewall para el servidor proxy inverso: interfaz externa

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
<th>Notas</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HTTP/TCP/80</p></td>
<td><p>Cualquiera</p></td>
<td><p>Escucha de proxy inverso</p></td>
<td><p>Faculta Redireccionamiento a HTTPS si el usuario&lt;escribe&gt;http://publishedSiteFQDN.</p>
<p>También se requiere si se usa Office Web Apps para conferencias y el servicio Detección automática para dispositivos móviles que ejecutan Lync en situaciones en las que la organización no desea modificar el certificado de regla de publicación de servicio Web externo.</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/443</p></td>
<td><p>Cualquiera</p></td>
<td><p>Escucha de proxy inverso</p></td>
<td><p>Descargas de la libreta de direcciones, servicio de consultas Web de la libreta de direcciones, detección automática, actualizaciones de cliente, contenido de la reunión, actualizaciones de dispositivos, expansión de grupos, Office Web Apps para conferencias, conferencias de acceso telefónico local y reuniones.</p></td>
</tr>
</tbody>
</table>


### <a name="firewall-details-for-reverse-proxy-server-internal-interface"></a>Detalles del firewall para el servidor proxy inverso: interfaz interna

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
<th>Notas</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HTTP/TCP/8080</p></td>
<td><p>Interfaz interna de proxy invertida</p></td>
<td><p>Servidor front-end, grupo front-end, Director, grupo de directores</p></td>
<td><p>Necesario si se usa el servicio de detección automática para dispositivos móviles que ejecutan Lync, en situaciones en las que la organización no desea modificar el certificado de la regla de publicación de servicio Web externo.</p>
<p>El tráfico enviado al puerto 80 en la interfaz externa de proxy inverso se redirige a un grupo en el puerto 8080 desde la interfaz interna de proxy invertida para que los servicios web del grupo lo diferencien del tráfico web interno.</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>Interfaz interna de proxy invertida</p></td>
<td><p>Servidor front-end, grupo front-end, Director, grupo de directores</p></td>
<td><p>El tráfico enviado al puerto 443 en la interfaz externa de proxy inverso se redirige a un grupo en el puerto 4443 desde la interfaz interna de proxy invertida para que los servicios web del grupo lo diferencien del tráfico web interno.</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP/443</p></td>
<td><p>Interfaz interna de proxy invertida</p></td>
<td><p>Office Web Apps para conferencias</p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

