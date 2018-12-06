---
title: "Resumen de puerto: federación SIP, federación XMPP y mensajería instantánea pública"
TOCTitle: "Résumé des ports - Féd. SIP, XMPP et messagerie instantanée publique"
ms:assetid: ab05bdd6-e9b0-4b1b-9dd9-29ab88e8befe
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ618373(v=OCS.15)
ms:contentKeyID: 49115308
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Resumen de puerto: federación SIP, federación XMPP y mensajería instantánea pública

 

_**Última modificación del tema:** 2015-03-09_

Los requisitos de puerto, protocolo y firewall para la federación con Microsoft Lync Server 2013, Lync Server 2010 y Office Communications Server son similares a los requisitos del Servidor perimetral implementado. Los clientes inician la comunicación con el Servidor perimetral de acceso a través de TLS/SIP/TCP 443. Sin embargo, los socios federados iniciarán las comunicaciones con el Servidor perimetral de acceso a través de MTLS/SIP/TCP 5061.

Para configurar en el firewall los puertos y protocolos necesarios para admitir la conectividad de mensajería instantánea pública, antes debe tener en cuenta que SIP/MTLS/TCP 5061 es bidireccional: es decir, permite a los contactos de la MI pública contactar con los clientes de Lync y a Lync contactar con los contactos de la MI pública.

Windows Live Messenger puede participar en comunicaciones de audio y vídeo con los clientes de Lync, por lo que la configuración de puertos y protocolos del firewall es muy similar a la que tendría normalmente en el firewall para admitir a los clientes de Lync como usuarios externos.

> [!IMPORTANT]  
> Lync es, ahora más que nunca, una eficaz herramienta para conectar organizaciones e individuos de todo el mundo. La federación con Windows Live Messenger no precisa de ninguna licencia de usuario o dispositivo adicional, aparte de la licencia de acceso de cliente (CAL) estándar de Lync. Esta lista incluirá también la federación con Skype, lo que permitirá a los usuarios de Lync llegar a cientos de millones de personas con voz y mensajería instantánea.<br />
> La federación con los contactos de clientes Messenger finalizará oficialmente el 15 de marzo de 2013, excepto en China continental. Skype pasará a ser el cliente de federación de los usuarios federados que usaban Messenger.


Los puertos y protocolos definidos para el proxy de protocolo extensible de mensajería y presencia (XMPP) implementado en el Servidor perimetral posibilitan las comunicaciones desde el socio federado de XMPP hasta el Servidor perimetral, y también posibilitan la comunicación desde su Servidor perimetral hasta el socio federado de XMPP. Además, hay una regla definida en el firewall de conexión interna para las comunicaciones entre el Servidor front-end o el Grupo de servidores front-end y el Servidor perimetral o el Grupo de servidores perimetrales.

## Resumen del firewall: federación SIP


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
<td><p>Dirección IP pública de Servidor perimetral de acceso</p></td>
<td><p>Cualquiera</p></td>
<td><p>Para la conectividad de MI pública y federada mediante SIP</p></td>
</tr>
</tbody>
</table>


## Resumen del firewall: Conectividad de mensajería instantánea pública


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
<td><p>Interfaz de acceso del Servidor perimetral</p></td>
<td><p>Para la conectividad de MI pública y federada mediante SIP.</p></td>
</tr>
<tr class="even">
<td><p>Acceso/SIP(MTLS)/TCP/5061</p></td>
<td><p>Interfaz de acceso del Servidor perimetral</p></td>
<td><p>Socios de conectividad de MI pública</p></td>
<td><p>Para la conectividad de MI pública y federada mediante SIP.</p></td>
</tr>
<tr class="odd">
<td><p>Acceso/SIP(TLS)/TCP/443</p></td>
<td><p>Clientes</p></td>
<td><p>Interfaz de acceso del Servidor perimetral</p></td>
<td><p>Tráfico SIP de cliente a servidor para el acceso de usuarios externos.</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50.000–59.999</p></td>
<td><p>Interfaz de acceso del Servidor perimetral</p></td>
<td><p>Clientes de Live Messenger</p></td>
<td><p>Se usa para las sesiones de A/V con Windows Live Messenger si se ha configurado la conectividad de MI pública.</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN,MSTURN/UDP/3478</p></td>
<td><p>Interfaz de acceso del Servidor perimetral</p></td>
<td><p>Clientes de Live Messenger</p></td>
<td><p>Obligatorio para la conectividad de MI pública con Windows Live Messenger.</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN,MSTURN/UDP/3478</p></td>
<td><p>Clientes de Live Messenger</p></td>
<td><p>Interfaz de acceso del Servidor perimetral</p></td>
<td><p>Obligatorio para la conectividad de MI pública con Windows Live Messenger.</p></td>
</tr>
</tbody>
</table>


## Resumen del firewall: Protocolo extensible de mensajería y presencia (XMPP)


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
<th>Origen (dirección IP)</th>
<th>Destino (dirección IP)</th>
<th>Comentarios</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XMPP/TCP/5269</p></td>
<td><p>Cualquiera</p></td>
<td><p>Dirección IP de la interfaz del Servidor perimetral de acceso</p></td>
<td><p>Puerto de comunicación estándar de servidor a servidor para XMPP. Permite la comunicación con el servidor proxy XMPP del Servidor perimetral desde socios XMPP federados</p></td>
</tr>
<tr class="even">
<td><p>XMPP/TCP/5269</p></td>
<td><p>Dirección IP de la interfaz del Servidor perimetral de acceso</p></td>
<td><p>Cualquiera</p></td>
<td><p>Puerto de comunicación estándar de servidor a servidor para XMPP. Permite la comunicación desde el servidor proxy XMPP del Servidor perimetral hasta los socios XMPP federados</p></td>
</tr>
<tr class="odd">
<td><p>XMPP/MTLS/23456</p></td>
<td><p>Cualquiera</p></td>
<td><p>IP interna de la interfaz del Servidor perimetral</p></td>
<td><p>Tráfico XMPP interno desde la puerta de enlace XMPP del Servidor front-end o del Grupo de servidores front-end hasta el Servidor perimetral</p></td>
</tr>
</tbody>
</table>


## Vea también

#### Conceptos

[Escenarios para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)  
[Determinar los requisitos de los puertos y el firewall de A/V externos en Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  

#### Otros recursos

[Administrar socios federados XMPP para su organización en Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)

