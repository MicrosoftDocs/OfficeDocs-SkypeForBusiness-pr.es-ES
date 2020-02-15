---
title: Resumen de Puerto-SIP, Federación XMPP y mensajería instantánea pública
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - SIP, XMPP federation, and public instant messaging
ms:assetid: ab05bdd6-e9b0-4b1b-9dd9-29ab88e8befe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618373(v=OCS.15)
ms:contentKeyID: 49105660
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2512b49f9e0bcdc092354a5f43cb234c7e4d5445
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043052"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>Resumen de Puerto-SIP, Federación XMPP y mensajería instantánea pública en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-03-15_

Los requisitos de puerto, protocolo y firewall para la Federación con Microsoft Lync Server 2013, Lync Server 2010 y Office Communications Server son similares a los del servidor perimetral implementado. Los clientes inician la comunicación con el servicio perimetral de acceso a través de TLS/SIP/TCP 443. No obstante, los socios federados iniciarán comunicaciones con el servicio perimetral de acceso a través de MTLS/SIP/TCP 5061.

Para configurar el firewall para los puertos y protocolos necesarios para la conectividad de mensajería instantánea pública, en primer lugar, tenga en cuenta que SIP/MTLS/TCP 5061 es bidireccional para tener en cuenta la capacidad de los contactos en el proveedor de mi pública para ponerse en contacto con clientes de Lync o Lync para ponerse en contacto con los contactos de mi pública.

Windows Live Messenger puede participar en las comunicaciones de audio y vídeo con los clientes de Lync. Esto cuenta con una configuración de protocolos y puertos de Firewall muy similares que normalmente tendría en el firewall para admitir clientes de Lync como usuarios externos.

<div>


> [!IMPORTANT]
> Más que nunca, Lync es una herramienta eficaz para la conexión entre organizaciones y con personas de todo el mundo. La Federación con Windows Live Messenger no requiere licencias de usuario o de dispositivo adicionales aparte de la licencia de acceso de cliente (CAL) de Lync Standard. La Federación de Skype se agregará a esta lista, lo que permite a los usuarios de Lync llegar a cientos de millones de personas con mi y voz.<BR>La Federación con los contactos del cliente de Messenger finalizará oficialmente el 15 de marzo de 2013, excepto para China continental. Skype se convertirá en cliente de Federación para los usuarios federados que usaron Messenger anteriormente.



</div>

Los puertos y protocolos definidos para el proxy de protocolo extensible de mensajería y presencia (XMPP) implementado en el servidor perimetral permiten las comunicaciones desde el socio federado de XMPP hacia el servidor perimetral y también permiten la comunicación desde el servidor perimetral al XMPP socio federado. Una regla también se define en el Firewall orientado internamente desde el servidor front-end o el grupo de servidores front-end hasta el servidor perimetral o el grupo de servidores perimetrales.

<div>

## <a name="firewall-summary---sip-federation"></a>Resumen del servidor de seguridad-Federación SIP


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
<td><p>Acceso/SIP (MTLS)/TCP/5061</p></td>
<td><p>Dirección IP pública del servicio perimetral de acceso</p></td>
<td><p>Cualquiera</p></td>
<td><p>Para la conectividad de MI pública y federada mediante SIP</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a>Resumen de firewall: Conectividad de mensajería instantánea pública


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
<td><p>Acceso/SIP (MTLS)/TCP/5061</p></td>
<td><p>Socios de conectividad de MI pública</p></td>
<td><p>Interfaz de acceso del servidor perimetral</p></td>
<td><p>Para la conectividad de mensajería instantánea pública y federada que usan SIP.</p></td>
</tr>
<tr class="even">
<td><p>Acceso/SIP (MTLS)/TCP/5061</p></td>
<td><p>Interfaz de acceso del servidor perimetral</p></td>
<td><p>Socios de conectividad de MI pública</p></td>
<td><p>Para la conectividad de mensajería instantánea pública y federada que usan SIP.</p></td>
</tr>
<tr class="odd">
<td><p>Acceso/SIP (TLS)/TCP/443</p></td>
<td><p>Clientes</p></td>
<td><p>Interfaz de acceso del servidor perimetral</p></td>
<td><p>Tráfico SIP de cliente a servidor para el acceso de usuarios externos.</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50000-59.999</p></td>
<td><p>Interfaz de acceso del servidor perimetral</p></td>
<td><p>Clientes de Live Messenger</p></td>
<td><p>Usado para sesiones de A/V con Windows Live Messenger si se ha configurado la conectividad de MI.</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>Interfaz de acceso del servidor perimetral</p></td>
<td><p>Clientes de Live Messenger</p></td>
<td><p>Necesario para la conectividad de mensajería instantánea pública con Windows Live Messenger.</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>Clientes de Live Messenger</p></td>
<td><p>Interfaz de acceso del servidor perimetral</p></td>
<td><p>Necesario para la conectividad de mensajería instantánea pública con Windows Live Messenger.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary---extensible-messaging-and-presence-protocol-xmpp"></a>Resumen de firewall, protocolo extensible de mensajería y presencia (XMPP)


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
<th>Origen (Dirección IP)</th>
<th>Destino (Dirección IP)</th>
<th>Comentarios</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XMPP/TCP/5269</p></td>
<td><p>Cualquiera</p></td>
<td><p>Dirección IP de la interfaz del servicio perimetral de acceso</p></td>
<td><p>Puerto de comunicación estándar de servidor a servidor para XMPP. Permite la comunicación con el proxy XMPP del servidor perimetral desde socios XMPP federados.</p></td>
</tr>
<tr class="even">
<td><p>XMPP/TCP/5269</p></td>
<td><p>Dirección IP de la interfaz del servicio perimetral de acceso</p></td>
<td><p>Cualquiera</p></td>
<td><p>Puerto de comunicación estándar de servidor a servidor para XMPP. Permite la comunicación desde el proxy XMPP del servidor perimetral a asociados de XMPP federados.</p></td>
</tr>
<tr class="odd">
<td><p>XMPP/MTLS/23456</p></td>
<td><p>Cualquiera</p></td>
<td><p>IP de la interfaz del servidor perimetral interno</p></td>
<td><p>Tráfico XMPP interno de la puerta de enlace XMPP del servidor front-end o del grupo de servidores front-end al servidor perimetral</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>Vea también


[Escenarios para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)  
[Determinación de los requisitos de los puertos y el Firewall de A/V externos para Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  


[Administrar socios federados XMPP en Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

