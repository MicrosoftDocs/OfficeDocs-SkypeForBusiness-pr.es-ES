---
title: 'Lync Server 2013: Resumen de Puerto-detección automática'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Autodiscover
ms:assetid: 8bd16363-5e18-4e4b-be99-b3e6457b4c99
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945642(v=OCS.15)
ms:contentKeyID: 51541497
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 605aee0d4054c482140ae66ba460931d4658274d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049302"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---autodiscover-in-lync-server-2013"></a>Resumen de Puerto-detección automática en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-03-05_

El servicio Detección automática de Lync Server 2013 se ejecuta en los servidores de director y de grupo de servidores front-end y `lyncdiscover.<domain>` , `lyncdiscoverinternal.<domain>` cuando se publican en DNS con los registros de host y, pueden ser usados por los clientes para localizar las características de Lync Server. Para que los dispositivos móviles que ejecutan Lync Mobile usen la detección automática, es posible que primero necesite modificar las listas de nombres alternativos de sujeto de certificado en cualquier Director y servidor front-end que ejecute el servicio Detección automática. Además, es posible que haya que modificar las listas de nombres alternativos de sujeto en certificados usados para las reglas de publicación de servicios web en proxies inversos.

La decisión sobre si usar listas de nombres alternativos de sujetos en servidores proxy inversos se basa en si publica el servicio Detección automática en el puerto 80 o en el puerto 443:

  - **Publicado en el puerto 80**   para dispositivos móviles, no es necesario realizar cambios en los certificados si la consulta inicial al servicio Detección automática se produce a través del puerto 80. Esto se debe a que los dispositivos móviles que ejecutan Lync tendrán acceso al proxy inverso en el puerto 80 externamente y, a continuación, se redirigirán a un director o a un servidor front-end en el puerto 8080 de forma interna.

  - **Publicado en el puerto 443**   la lista de nombres alternativos de sujeto en los certificados usados por la regla de publicación de `lyncdiscover.<sipdomain>` servicios web externos debe contener una entrada para cada dominio SIP dentro de la organización.
    
    <div>
    

    > [!IMPORTANT]  
    > Para instalaciones nuevas o actualizaciones de Lync Server 2010 donde se implementó la movilidad, se usó el puerto 80 para la detección automática del servicio de movilidad o se volveron a emitir certificados con el nombre de sujeto y los nombres alternativos de sujeto correctos en su lugar. Revise los certificados en el director y el servidor front-end para confirmar la ruta de acceso que eligió.

    
    </div>

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
<td><p>Opcional Redirección a HTTPS si el usuario escribe&lt;http://&gt;publishedSiteFQDN. También es necesario si usa Office Web Apps para conferencias y el servicio Detección automática para dispositivos móviles que ejecutan Lync en situaciones en las que la organización no desea modificar el certificado de la regla de publicación de servicios web externos.</p></td>
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
<td><p>Servidor front-end, grupo de servidores front-end, Director, grupo de directores, Office Web Apps para conferencias</p></td>
<td><p>Es necesario si se usa el servicio Detección automática para dispositivos móviles que ejecutan Lync en situaciones en las que la organización no desea modificar el certificado de la regla de publicación de servicios web externos. El tráfico que se envía a 80 en la interfaz externa del proxy inverso se redirige a un grupo de servidores del puerto 8080 desde la interfaz interna del proxy inverso, para que los servicios web del grupo de servidores puedan distinguirlo del tráfico web interno.</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>Interfaz de proxy inverso interno</p></td>
<td><p>Servidor front-end, grupo de servidores front-end, Director, grupo de directores, Office Web Apps para conferencias</p></td>
<td><p>El tráfico enviado al puerto 443 de la interfaz externa del proxy inverso se redirige a un grupo de servidores del puerto 4443 desde la interfaz interna del proxy inverso para que los servicios web del grupo de servidores puedan distinguirlo del tráfico web interno.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

