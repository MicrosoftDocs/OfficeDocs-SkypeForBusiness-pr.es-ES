---
title: 'Lync Server 2013: Resumen de Puerto-proxy inverso'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Reverse proxy
ms:assetid: 59b9ac3c-3e6f-4776-b366-174f0dd1f2eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204932(v=OCS.15)
ms:contentKeyID: 48184251
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aedd0552377861c686667eadd88d190a03799cce
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152648"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---reverse-proxy-in-lync-server-2013"></a>Resumen de Puerto-proxy inverso en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-15_

El proxy inverso tiene requisitos mínimos para el firewall y el puerto/protocolo.

  - Los requisitos del firewall externo son HTTPS/TCP/443 y el HTTP/TCP/80 opcional. HTTPS se usa para las comunicaciones seguras SSL y TLS a través del proxy inverso. HTTP se usa si elige permitir el acceso al servicio de detección automática al modificar certificados que puede resultar difícil o no estar justificado por el costo.

  - Los clientes esperan ponerse en contacto con el servidor de Office Web Apps en HTTPS. El servidor de Office Web Apps espera la comunicación de clientes internos en HTTPS/TCP/443. La configuración recomendada es permitir HTTPS/TCP/443 desde el proxy inverso hasta el servidor de Office Web Apps.

  - El puerto 8080 se usa para enrutar el tráfico de la interfaz interna del proxy inverso al servidor front-end, la dirección IP virtual (VIP) del grupo de servidores front-end o el director opcional o VIP del grupo de directores. El puerto TCP 8080 es necesario para que los dispositivos móviles que ejecutan Lync encuentren el servicio Detección automática en situaciones en las que no es deseable modificar el certificado de la regla de publicación de servicios web externos (por ejemplo, si tiene un gran número de dominios SIP). Si elige adquirir nuevos certificados con las entradas de SAN necesarias, el puerto TCP 8080 no es necesario y es opcional.

  - El puerto 4443 se usa para el tráfico desde la interfaz interna del proxy inverso hasta el servidor front-end, la IP virtual del grupo de servidores front-end (VIP) o el director opcional o VIP del grupo de directores
    
    ![13142405-d5c9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")  
    
    <div>
    

    > [!WARNING]  
    > No confunda el 4443 sobre TCP del proxy inverso con la implementación interna para el puerto 4443 a través de tráfico TCP desde el servidor Standard Edition o el grupo de servidores front-end que administra la función de almacén de administración central.

    
    </div>

<div>

## <a name="port-and-protocol-details"></a>Detalles de puerto y protocolo

### <a name="firewall-details-for-reverse-proxy-server-external-interface"></a>Detalles de firewalls para servidor proxy inverso: Interfaz externa

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
<th>Notas</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HTTP/TCP/80</p></td>
<td><p>Cualquiera</p></td>
<td><p>Escucha de proxy inverso</p></td>
<td><p>Opcional Redirección a HTTPS si el usuario escribe&lt;http://&gt;publishedSiteFQDN.</p>
<p>También es necesario si usa Office Web Apps para conferencias y el servicio Detección automática para dispositivos móviles que ejecutan Lync en situaciones en las que la organización no desea modificar el certificado de la regla de publicación de servicios web externos.</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/443</p></td>
<td><p>Cualquiera</p></td>
<td><p>Escucha de proxy inverso</p></td>
<td><p>Descargas de la libreta de direcciones, servicio de consulta Web de libreta de direcciones, detección automática, actualizaciones de cliente, contenido de reuniones, actualizaciones de dispositivos, expansión de grupos, Office Web Apps para conferencias, conferencias de acceso telefónico local y reuniones.</p></td>
</tr>
</tbody>
</table>


### <a name="firewall-details-for-reverse-proxy-server-internal-interface"></a>Detalles de firewalls para servidor proxy inverso: Interfaz interna

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
<th>Notas</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HTTP/TCP/8080</p></td>
<td><p>Interfaz de proxy inverso interno</p></td>
<td><p>Servidor front-end, grupo de servidores front-end, Director, grupo de directores</p></td>
<td><p>Es necesario si se usa el servicio Detección automática para dispositivos móviles que ejecutan Lync en situaciones en las que la organización no desea modificar el certificado de la regla de publicación de servicios web externos.</p>
<p>El tráfico que se envía a 80 en la interfaz externa del proxy inverso se redirige a un grupo de servidores del puerto 8080 desde la interfaz interna del proxy inverso, para que los servicios web del grupo de servidores puedan distinguirlo del tráfico web interno.</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>Interfaz de proxy inverso interno</p></td>
<td><p>Servidor front-end, grupo de servidores front-end, Director, grupo de directores</p></td>
<td><p>El tráfico enviado al puerto 443 de la interfaz externa del proxy inverso se redirige a un grupo de servidores del puerto 4443 desde la interfaz interna del proxy inverso para que los servicios web del grupo de servidores puedan distinguirlo del tráfico web interno.</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP/443</p></td>
<td><p>Interfaz de proxy inverso interno</p></td>
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

