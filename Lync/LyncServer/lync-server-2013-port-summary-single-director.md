---
title: 'Lync Server 2013: Resumen del puerto - Director único'
TOCTitle: Resumen del puerto - Director único
ms:assetid: 079c1414-723f-4499-b7d4-a0d7121c1626
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204648(v=OCS.15)
ms:contentKeyID: 48274334
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Resumen del puerto - Director único en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

Los requisitos de puerto de firewall para un Director único constan de los puertos que se usan para establecer comunicación con el Director desde la interfaz interna o la red orientada internamente del proxy inverso. Microsoft Lync Server 2013 espera de manera predeterminada que los puertos HTTP/TCP 8080 y HTTPS/TCP 4443 se abran desde el proxy inverso al Director, así como el Grupo de servidores front-end y Servidor front-end. Además, debe haber comunicación de protocolo de inicio de sesión (SIP) desde la interfaz interna de Servidor perimetral hasta el Director y el Grupo de servidores front-end y Servidor front-end. El protocolo SIP usa SIP/MTLS/TCP 5061 desde el Servidor perimetral hasta el Grupo de servidores front-end y Servidor front-end. Se debe crear también una regla que permite la comunicación SIP/MTLS/TCP 5061 desde el Director, Grupo de servidores front-end y Servidor front-end hasta la interfaz interna de Servidor perimetral.

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
<td><p>Director</p></td>
<td><p>Recibida inicialmente por el lado externo del proxy inverso, la comunicación se envía a los servicios web del Director y Servidor front-end</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP 4443</p></td>
<td><p>Interfaz interna de proxy inverso</p></td>
<td><p>Director</p></td>
<td><p>Recibida inicialmente por el lado externo del proxy inverso, la comunicación se envía a los servicios web del Director y Servidor front-end</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 444</p></td>
<td><p>Director</p></td>
<td><p>Servidor front-end o grupo de servidores front-end</p></td>
<td><p>Comunicación entre servidores entre el Director y el Servidor front-end</p></td>
</tr>
<tr class="even">
<td><p>HTTP/TCP 80</p></td>
<td><p>Clientes internos</p></td>
<td><p>Servicios web del Director</p></td>
<td><p>El Director ofrece servicios web a clientes internos y externos.</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 443</p></td>
<td><p>Clientes internos</p></td>
<td><p>Servicios web del Director</p></td>
<td><p>El Director ofrece servicios web a clientes internos y externos.</p></td>
</tr>
<tr class="even">
<td><p>SIP/MTLS/TCP 5061</p></td>
<td><p>Interfaz interna del Servidor perimetral</p></td>
<td><p>Director</p></td>
<td><p>Comunicación SIP desde el servidor perimetral hasta el Director y el Servidor front-end.</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50001</p></td>
<td><p>Cualquiera</p></td>
<td><p>Interfaz interna del Servidor perimetral</p></td>
<td><p>Controlador del Servicio de registro centralizado (ClsController.exe) o comandos (ClasAgent.exe) de agente y colección de registros</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50002</p></td>
<td><p>Cualquiera</p></td>
<td><p>Interfaz interna del Servidor perimetral</p></td>
<td><p>Controlador del Servicio de registro centralizado (ClsController.exe) o comandos (ClasAgent.exe) de agente y colección de registros</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50003</p></td>
<td><p>Cualquiera</p></td>
<td><p>Interfaz interna del Servidor perimetral</p></td>
<td><p>Controlador del Servicio de registro centralizado (ClsController.exe) o comandos (ClasAgent.exe) de agente y colección de registros</p></td>
</tr>
</tbody>
</table>

