---
title: 'Resumen del puerto: detección automática en Lync Server 2013'
TOCTitle: 'Resumen del puerto: detección automática en Lync Server 2013'
ms:assetid: 8bd16363-5e18-4e4b-be99-b3e6457b4c99
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ945642(v=OCS.15)
ms:contentKeyID: 52061668
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Resumen del puerto: detección automática en Lync Server 2013

 

_**Última modificación del tema:** 2016-04-06_

El servicio Detección automática de Lync Server 2013 se ejecuta en los servidores director y grupo de servidores front-end, y cuando se publica en in DNS con los registros de host de `lyncdiscover.<domain>` y `lyncdiscoverinternal.<domain>`, los clientes pueden usarlo para localizar características de Lync Server. Antes de que los dispositivos móviles que ejecutan Lync Mobile puedan usar la detección automática, primero hay que modificar las listas de nombres alternativos de sujeto de certificados en cualquier Director y Servidor front-end que ejecute el servicio Detección automática. Además, es posible que haya que modificar las listas de nombres alternativos de sujeto en certificados usados para las reglas de publicación de servicios web en proxies inversos.

La decisión de usar listas de nombres alternativos de sujeto en proxies inversos se basa en si se publica el servicio Detección automática en el puerto 80 o en el puerto 443:

  - **Publicado en el puerto 80**   Para dispositivos móviles, no son necesarios cambios de certificado si la consulta inicial al servicio Detección automática se produce en el puerto 80. Esto se debe a que los dispositivos móviles que ejecutan Lync tendrán acceso al proxy inverso en el puerto 80 de forma externa y después se redirigirán a un Director o Servidor front-end en el puerto 8080 de forma interna.

  - **Publicado en el puerto 443**   La lista de nombres alternativos de sujeto en certificados usada por la regla de publicación de servicios web externos debe contener una entrada `lyncdiscover.<sipdomain>` para cada dominio SIP de su organización.
    
    > [!IMPORTANT]  
    > Para nuevas instalaciones o actualizaciones de Lync Server 2010 en las que se ha implementado Movilidad, bien usó el puerto 80 para la detección automática del servicio Movilidad, bien emitió de nuevo los certificados con los correspondientes nombre de sujeto y nombres alternativos de sujeto implementados. Revise los certificados de su Director y Servidor front-end para confirmar la ruta a elegir.
    


### Detalles de firewalls para servidor proxy inverso: Interfaz externa

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
<td><p>Agente de escucha de proxy inverso</p></td>
<td><p>(Opcional) Redirección a HTTPS si el usuario introduce http://<em>&lt;FQDNdelsitiopublicado&gt;</em>. También es necesario si usa Office Web Apps para conferencia y el servicio Detección automática para dispositivos móviles que ejecutan Lync en situaciones en las que la organización no desea cambiar el certificado de la regla de publicación de servicios web externos.</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/443</p></td>
<td><p>Cualquiera</p></td>
<td><p>Agente de escucha de proxy inverso</p></td>
<td><p>Descargas de libreta de direcciones, servicio de consulta web de libreta de direcciones, detección automática, actualizaciones de cliente, contenido de reuniones, actualizaciones de dispositivo, expansión de grupos, Office Web Apps para conferencias, conferencia de acceso telefónico y reuniones.</p></td>
</tr>
</tbody>
</table>


### Detalles de firewalls para servidor proxy inverso: Interfaz interna

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
<td><p>Interfaz interna de proxy inverso</p></td>
<td><p>Servidor front-end, Grupo de servidores front-end, Director, Grupo de directores, Office Web Apps para conferencia</p></td>
<td><p>Requerido si usa el servicio Detección automática para dispositivos móviles que ejecutan Lync en situaciones en que la organización no desea modificar el certificado de la regla de publicación de servicios web externos. El tráfico enviado al puerto 80 de la interfaz externa del proxy inverso se redirige a un grupo de servidores del puerto 8080 desde la interfaz interna del proxy inverso para que los servicios web del grupo de servidores puedan distinguirlo del tráfico web interno.</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>Interfaz interna de proxy inverso</p></td>
<td><p>Servidor front-end, Grupo de servidores front-end, Director, Grupo de directores, Office Web Apps para conferencia</p></td>
<td><p>El tráfico enviado al puerto 443 de la interfaz externa del proxy inverso se redirige a un grupo de servidores del puerto 4443 desde la interfaz interna del proxy inverso para que los servicios web del grupo de servidores puedan distinguirlo del tráfico web interno.</p></td>
</tr>
</tbody>
</table>

