---
title: 'Lync Server 2013: Resumen de puerto - Carga equilibrada DNS y HLB'
TOCTitle: Resumen de puerto - Carga equilibrada DNS y HLB
ms:assetid: b07c37e4-820e-46ee-a678-1da95d1b87af
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205179(v=OCS.15)
ms:contentKeyID: 48276369
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Resumen de puerto - Carga equilibrada DNS y HLB en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

Los requisitos de puertos de firewall para un Director único incluyen los puertos que se usan para establecer la comunicación con el Director desde la interfaz interna o la red interna del proxy inverso. De manera predeterminada, Microsoft Lync Server 2013 espera que los puertos HTTP/TCP 8080 y HTTPS/TCP 4443 estén abiertos del proxy inverso al Director, además del Grupo de servidores front-end y el Servidor front-end. Además, debe haber comunicación del protocolo de inicio de sesión (SIP) de la interfaz interna del Servidor perimetral al Director, y al Grupo de servidores front-end y el Servidor front-end. El protocolo SIP usa SIP/MTLS/TCP 5061 del Servidor perimetral al Grupo de servidores front-end y el Servidor front-end. También se debe crear una regla que permita la comunicación SIP/MTLS/TCP 5061 del Director, el Grupo de servidores front-end y el Servidor front-end a la interfaz interna del Servidor perimetral.

### Puertos y protocolos del Director único para definiciones de firewall

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
<td><p>Recibida inicialmente por el lado externo del proxy inverso, la comunicación se envía a la VIP del HLB del Director y los servicios web del Servidor front-end.</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP 4443</p></td>
<td><p>Interfaz interna de proxy inverso</p></td>
<td><p>VIP del equilibrador de carga de hardware del Director</p></td>
<td><p>Recibida inicialmente por el lado externo del proxy inverso, la comunicación se envía a la VIP del HLB del Director y los servicios web del Servidor front-end.</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 444</p></td>
<td><p>Director</p></td>
<td><p>Grupo de servidores front-end o Servidor front-end</p></td>
<td><p>Comunicación entre servidores, entre la VIP del HLB del Director y el Servidor front-end o Servidores front-end.</p></td>
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
<td><p>Director</p></td>
<td><p>Comunicación SIP del servidor perimetral al Director, además del Servidores front-end.</p></td>
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

