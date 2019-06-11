---
title: 'Lync Server 2013: Resumen de puertos-detección automática'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - Autodiscover
ms:assetid: 8bd16363-5e18-4e4b-be99-b3e6457b4c99
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945642(v=OCS.15)
ms:contentKeyID: 51541497
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7a40d86799b4922a819642aedf2461f038330593
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824081"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---autodiscover-in-lync-server-2013"></a>Resumen de puertos-detección automática en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-03-05_

El servicio de detección automática de Lync Server 2013 se ejecuta en los servidores de director y de grupo de servidores front-end `lyncdiscover.<domain>` y `lyncdiscoverinternal.<domain>` , cuando se publican en DNS con los registros de host y de hospedaje, los clientes pueden usarlos para localizar las características de Lync Server. Para que los dispositivos móviles que ejecutan Lync Mobile puedan usar la detección automática, es posible que primero tenga que modificar las listas de nombres alternativos del sujeto de certificado en cualquier Director y servidor front-end que ejecute el servicio Detección automática. Además, puede que sea necesario modificar las listas de nombres alternativos del asunto en los certificados que se usan para las reglas de publicación de servicios web externos en los proxies inversos.

La decisión sobre si usar o no las listas de nombres alternativos del sujeto en proxies inversos se basa en si publica el servicio de detección automática en el puerto 80 o en el puerto 443:

  - **Publicado en el puerto 80**   para dispositivos móviles, no es necesario realizar cambios en los certificados si la consulta inicial para el servicio de detección automática se realiza a través del puerto 80. Esto se debe a que los dispositivos móviles que ejecutan Lync tendrán acceso al proxy inverso en el puerto 80 externamente y se redirigirá a un director o servidor front-end en el puerto 8080 de forma interna.

  - **Publicado en el puerto 443**   la lista de nombres alternativos de asunto en certificados usados por la regla de publicación de servicios `lyncdiscover.<sipdomain>` web externos debe contener una entrada para cada dominio SIP de su organización.
    
    <div>
    

    > [!IMPORTANT]  
    > En el caso de instalaciones nuevas o actualizaciones de Lync Server 2010 donde ha implementado la movilidad, ya ha usado el puerto 80 para la detección automática del servicio de movilidad o ha reemitido certificados con el nombre de asunto y los nombres alternativos de asunto correctos. Revise los certificados de su director y del servidor front-end para confirmar qué ruta de acceso elegida.

    
    </div>

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
<td><p>Faculta Redireccionamiento a HTTPS si el usuario&lt;escribe&gt;http://publishedSiteFQDN. También se requiere si se usa Office Web Apps para conferencias y el servicio Detección automática para dispositivos móviles que ejecutan Lync en situaciones en las que la organización no desea modificar el certificado de regla de publicación de servicio Web externo.</p></td>
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
<td><p>Servidor front-end, grupo front-end, Director, grupo de directores, Office Web Apps para conferencias</p></td>
<td><p>Necesario si se usa el servicio de detección automática para dispositivos móviles que ejecutan Lync, en situaciones en las que la organización no desea modificar el certificado de la regla de publicación de servicio Web externo. El tráfico enviado al puerto 80 en la interfaz externa de proxy inverso se redirige a un grupo en el puerto 8080 desde la interfaz interna de proxy invertida para que los servicios web del grupo lo diferencien del tráfico web interno.</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>Interfaz interna de proxy invertida</p></td>
<td><p>Servidor front-end, grupo front-end, Director, grupo de directores, Office Web Apps para conferencias</p></td>
<td><p>El tráfico enviado al puerto 443 en la interfaz externa de proxy inverso se redirige a un grupo en el puerto 4443 desde la interfaz interna de proxy invertida para que los servicios web del grupo lo diferencien del tráfico web interno.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

