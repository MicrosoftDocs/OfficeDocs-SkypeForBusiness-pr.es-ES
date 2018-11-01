---
title: 'Lync Server 2013: Resumen de puerto - Proxy inverso'
TOCTitle: Resumen de puerto - Proxy inverso
ms:assetid: 59b9ac3c-3e6f-4776-b366-174f0dd1f2eb
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204932(v=OCS.15)
ms:contentKeyID: 48275368
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Resumen de puerto - Proxy inverso en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

El proxy inverso cuenta con requisitos mínimos para firewall y puerto/protocolo.

  - Los requisitos del firewall externo son el puerto HTTPS/TCP/443 y el puerto HTTP/TCP/80 opcional. HTTPS se usa para comunicaciones seguras SSL y TLS a través del proxy inverso. HTTP se usa si el usuario opta por permitir el acceso al servicio Detección automática cuando la modificación de certificados resulta complicada o no se justifica debido a su costo.

  - Se espera que los clientes se conecten con el Servidor Office Web Apps en HTTPS. El Servidor Office Web Apps espera que los clientes internos se comuniquen en HTTPS/TCP/443. La configuración recomendada es permitir HTTPS/TCP/443 del proxy inverso al Servidor Office Web Apps.

  - El puerto 8080 se usa para enrutar el tráfico de la interfaz interna del proxy inverso a la IP virtual (VIP) de Servidor front-end, Grupo de servidores front-end o a la VIP opcional de Director o Grupo de directores. Los dispositivos móviles que ejecutan Lync necesitan el puerto TCP 8080 para localizar el servicio Detección automática en situaciones en que no es deseable modificar el certificado de la regla de publicación web externa (por ejemplo, si tiene un gran número de dominios SIP). Si decide adquirir nuevos certificados con las entradas SAN necesarias, el puerto TCP 8080 no se necesita y es opcional.

  - El puerto 4443 se usa para el tráfico de la interfaz interna del proxy inverso a la IP virtual (VIP) de Servidor front-end, Grupo de servidores front-end o a la VIP opcional de Director o Grupo de directores
    
    ![Proxy inverso y servicios web externos](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "Proxy inverso y servicios web externos")  
    
    > [!CAUTION]  
    > No se debe confundir el 4443 sobre TCP del proxy inverso con la implementación interna para el puerto 4443 sobre tráfico TCP del servidor Standard Edition o el Grupo de servidores front-end que administra el rol de Almacén de administración central.
    


## Detalles de protocolo y puerto

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
<td><p>(Opcional) Redirección a HTTPS si el usuario escribe http://<em>&lt;publishedSiteFQDN&gt;</em>.</p>
<p>Requerido también si usa Office Web Apps para conferencias y el servicio Detección automática para dispositivos móviles que ejecutan Lync en situaciones en que la organización no desea modificar el certificado en la regla de publicación de servicios web externos.</p></td>
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
<td><p>Servidor front-end, Grupo de servidores front-end, Director, Grupo de directores</p></td>
<td><p>Requerido si usa el servicio Detección automática para dispositivos móviles que ejecutan Lync en situaciones en que la organización no desea modificar el certificado de la regla de publicación de servicios web externos.</p>
<p>El tráfico enviado al puerto 80 de la interfaz externa del proxy inverso se redirige a un grupo de servidores del puerto 8080 desde la interfaz interna del proxy inverso para que los servicios web del grupo de servidores puedan distinguirlo del tráfico web interno.</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>Interfaz interna de proxy inverso</p></td>
<td><p>Servidor front-end, Grupo de servidores front-end, Director, Grupo de directores</p></td>
<td><p>El tráfico enviado al puerto 443 de la interfaz externa del proxy inverso se redirige a un grupo de servidores del puerto 4443 desde la interfaz interna del proxy inverso para que los servicios web del grupo de servidores puedan distinguirlo del tráfico web interno.</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP/443</p></td>
<td><p>Interfaz interna de proxy inverso</p></td>
<td><p>Office Web Apps para conferencias</p></td>
<td><p></p></td>
</tr>
</tbody>
</table>

