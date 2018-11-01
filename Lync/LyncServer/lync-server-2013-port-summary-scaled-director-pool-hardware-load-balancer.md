---
title: "Lync Server 2013: Resumen puerto: Grupo director escalado, equilibr. carga hardware"
TOCTitle: Resumen de puerto - Grupo de director escalado, equilibrador de carga de hardware
ms:assetid: 6ae2f4ac-5b64-4e45-8253-133308f5812d
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204983(v=OCS.15)
ms:contentKeyID: 48275596
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Resumen de puerto - Grupo de director escalado, equilibrador de carga de hardware en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

Los requisitos de puerto del firewall de un Grupo de directores consisten en los puertos que se usan para comunicarse con el Director desde la interfaz interna del Servidor perimetral o desde la interfaz de conexión interna del proxy inverso. Microsoft Lync Server 2013 espera de forma predeterminada que los puertos HTTP/TCP 8080 y HTTPS/TCP 4443 estén abiertos desde el proxy inverso al Director, así como el Grupo de servidores front-end y el Servidor front-end. Además, debe haber comunicación de protocolo de inicio de sesión (SIP) entre la interfaz interna del Servidor perimetral y el Director y entre el Grupo de servidores front-end y el Servidor front-end. El protocolo SIP emplea SIP/MTLS/TCP 5061 desde el Servidor perimetral al Grupo de servidores front-end y al Servidor front-end. De igual modo, se debe crear una regla que permita la comunicación a través de SIP/MTLS/TCP 5061 desde el Director, el Grupo de servidores front-end y el Servidor front-end a la interfaz interna del Servidor perimetral.

### Protocolos y puertos del Director para la definición de puertos

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Rol/Protocolo/TCP o UDP/Puerto</th>
<th>Dirección IP de origen</th>
<th>Dirección IP de destino</th>
<th>Notas</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HTTP/TCP 8080</p></td>
<td><p>Interfaz interna de proxy inverso</p></td>
<td><p>VIP del equilibrador de carga de hardware del Director</p></td>
<td><p>La comunicación, que el lado externo del proxy inverso recibe en principio, se envía al VIP del equilibrador de carga de hardware del Director y los servicios web de los Servidores front-end</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP 4443</p></td>
<td><p>Interfaz interna de proxy inverso</p></td>
<td><p>VIP del equilibrador de carga de hardware del Director</p></td>
<td><p>La comunicación, que el lado externo del proxy inverso recibe en principio, se envía al VIP del equilibrador de carga de hardware del Director y los servicios web de los Servidores front-end</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 444</p></td>
<td><p>Director</p></td>
<td><p>Servidor front-end o Grupo de servidores front-end</p></td>
<td><p>Comunicación entre servidores entre el VIP del equilibrador de carga de hardware del Director y el Servidores front-end</p></td>
</tr>
<tr class="even">
<td><p>HTTP/TCP 80</p></td>
<td><p>Clientes internos</p></td>
<td><p>VIP del equilibrador de carga de hardware del Director</p></td>
<td><p>El Director ofrece servicios web tanto a clientes internos como externos.</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 443</p></td>
<td><p>Clientes internos</p></td>
<td><p>VIP del equilibrador de carga de hardware del Director</p></td>
<td><p>El Director ofrece servicios web tanto a clientes internos como externos.</p></td>
</tr>
<tr class="even">
<td><p>SIP/MTLS/TCP 5061</p></td>
<td><p>Interfaz interna del Servidor perimetral</p></td>
<td><p>VIP del equilibrador de carga de hardware del Director</p></td>
<td><p>Comunicación SIP desde el Servidor perimetral al Director y el Servidores front-end.</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50001</p></td>
<td><p>Cualquiera</p></td>
<td><p>Director</p></td>
<td><p>Colección de registros y comandos del controlador del Servicio de registro centralizado (ClsController.exe) o del agente (ClsAgent.exe).</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50002</p></td>
<td><p>Cualquiera</p></td>
<td><p>Director</p></td>
<td><p>Colección de registros y comandos del controlador del Servicio de registro centralizado (ClsController.exe) o del agente (ClsAgent.exe).</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50003</p></td>
<td><p>Cualquiera</p></td>
<td><p>Director</p></td>
<td><p>Colección de registros y comandos del controlador del Servicio de registro centralizado (ClsController.exe) o del agente (ClsAgent.exe).</p></td>
</tr>
</tbody>
</table>

