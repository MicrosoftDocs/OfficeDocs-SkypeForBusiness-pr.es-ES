---
title: Resumen de puertos - Conectividad de mensajería instantánea pública
TOCTitle: Resumen de puertos - Conectividad de mensajería instantánea pública
ms:assetid: f46756ec-1401-4ca2-a4a4-5cd28bcfdc7f
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ618376(v=OCS.15)
ms:contentKeyID: 49129324
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Resumen de puertos - Conectividad de mensajería instantánea pública

 

_**Última modificación del tema:** 2015-03-09_

Para configurar un firewall para puertos y protocolos necesarios para la conectividad de mensajería instantánea (MI) pública, antes debe tener en cuenta que SIP/MTLS/TCP 5061 es bidireccional; es decir, permite a los contactos de la MI pública conectar con clientes de Lync y a Lync conectar con los contactos de la MI pública.

Windows Live Messenger puede participar en comunicaciones de audio y vídeo con clientes Lync, lo cual permite una configuración de puertos y protocolos de firewall muy similar a la que tendría normalmente en el firewall para dar soporte a clientes Lync como usuarios externos.

> [!IMPORTANT]  
> Lync es ahora más que nunca una poderosa herramienta de conexión entre empresas y con individuos de todo el mundo. La federación con Windows Live Messenger no precisa de ninguna licencia de usuario/dispositivo extra, aparte de la licencia de acceso de cliente (CAL) de Lync Standard. Esta lista incluirá también la federación con Skype, lo que permitirá a los usuarios de Lync llegar a cientos de millones de personas mediante voz y mensajería instantánea.<br />
> La federación con los contactos del cliente de Messenger finalizará oficialmente el 15 de marzo de 2013, excepto en Chino continental. Skype pasará a ser el cliente de federación de los usuarios federados que usaban Messenger.


## Resumen de firewall: Conectividad de mensajería instantánea pública


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
<td><p>Acceso/SIP(MTLS)/TCP/5061</p></td>
<td><p>Socios de conectividad de MI pública</p></td>
<td><p>Interfaz de acceso de Servidor perimetral</p></td>
<td><p>Para la conectividad de MI pública y federada mediante SIP.</p></td>
</tr>
<tr class="even">
<td><p>Acceso/SIP(MTLS)/TCP/5061</p></td>
<td><p>Interfaz de acceso de Servidor perimetral</p></td>
<td><p>Socios de conectividad de MI pública</p></td>
<td><p>Para la conectividad de MI pública y federada mediante SIP.</p></td>
</tr>
<tr class="odd">
<td><p>Acceso/SIP(TLS)/TCP/443</p></td>
<td><p>Clientes</p></td>
<td><p>Interfaz de acceso de Servidor perimetral</p></td>
<td><p>Tráfico SIP de cliente a servidor para acceso de usuarios externos.</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50.000-59.999</p></td>
<td><p>Interfaz de acceso de Servidor perimetral</p></td>
<td><p>Clientes de Live Messenger</p></td>
<td><p>Usado para sesiones de A/V con Windows Live Messenger si se ha configurado la conectividad de MI.</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN,MSTURN/UDP/3478</p></td>
<td><p>Interfaz de acceso de Servidor perimetral</p></td>
<td><p>Clientes de Live Messenger</p></td>
<td><p>Obligatorio para la conectividad de MI pública con Windows Live Messenger.</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN,MSTURN/UDP/3478</p></td>
<td><p>Clientes de Live Messenger</p></td>
<td><p>Interfaz de acceso de Servidor perimetral</p></td>
<td><p>Obligatorio para la conectividad de MI pública con Windows Live Messenger.</p></td>
</tr>
</tbody>
</table>


## Vea también

#### Conceptos

[Escenarios para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)  
[Determinar los requisitos de los puertos y el firewall de A/V externos en Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

