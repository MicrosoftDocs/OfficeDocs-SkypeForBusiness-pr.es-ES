---
title: 'Lync Server 2013: Resumen de puertos: conectividad de mensajería instantánea pública'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Public instant messaging connectivity
ms:assetid: f46756ec-1401-4ca2-a4a4-5cd28bcfdc7f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618376(v=OCS.15)
ms:contentKeyID: 49105663
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16430849221631d9b540f5ee51b0a07758a38b05
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725060"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---public-instant-messaging-connectivity-in-lync-server-2013"></a>Resumen de puertos: conectividad de mensajería instantánea pública en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-16_

Para configurar el firewall para los puertos y protocolos necesarios para admitir la conectividad de mensajería instantánea pública, primero tenga en cuenta que los SIP/MTLS/TCP 5061 son bidireccionales para tener en cuenta la capacidad de los contactos en el proveedor de mi pública para ponerse en contacto con los clientes de Lync o para que Lync pueda comunicarse con los contactos públicos de mensajería instantánea.

Windows Live Messenger puede participar en comunicaciones de audio y vídeo con clientes de Lync. Esto cuenta con una configuración de protocolo y un puerto de Firewall muy similar que normalmente tendría en el firewall para admitir clientes de Lync como usuarios externos.

<div>


> [!IMPORTANT]  
> Más que nunca, Lync es una herramienta eficaz para la conexión entre organizaciones y con personas de todo el mundo. La Federación con Windows Live Messenger no requiere licencias de usuario o de dispositivo adicionales aparte de la licencia de acceso de cliente (CAL) de Lync. La Federación de Skype se agrega a esta lista, lo que permite a los usuarios de Lync llegar a cientos de millones de personas con la mensajería instantánea y la voz.<BR>La Federación con los contactos de los clientes de Messenger terminará oficialmente el 15 de marzo de 2013, excepto en el caso de China continental. Skype se convertirá en el cliente de Federación para los usuarios federados que antes usaban Messenger.



</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a>Resumen del firewall: conectividad de mensajería instantánea pública


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Función/protocolo/TCP o UDP/puerto</th>
<th>Dirección IP de origen</th>
<th>Dirección IP de destino</th>
<th>Notas</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Acceso/SIP (MTLS)/TCP/5061</p></td>
<td><p>Partners de conectividad de mensajería instantánea pública</p></td>
<td><p>Interfaz de acceso al servidor perimetral</p></td>
<td><p>Para la conectividad de mensajería instantánea pública y federada que usan SIP.</p></td>
</tr>
<tr class="even">
<td><p>Acceso/SIP (MTLS)/TCP/5061</p></td>
<td><p>Interfaz de acceso al servidor perimetral</p></td>
<td><p>Partners de conectividad de mensajería instantánea pública</p></td>
<td><p>Para la conectividad de mensajería instantánea pública y federada que usan SIP.</p></td>
</tr>
<tr class="odd">
<td><p>Acceso/SIP (TLS)/TCP/443</p></td>
<td><p>Clientes</p></td>
<td><p>Interfaz de acceso al servidor perimetral</p></td>
<td><p>Tráfico SIP de cliente a servidor para el acceso de usuarios externos.</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50000-59.999 SESIONES</p></td>
<td><p>Interfaz de acceso al servidor perimetral</p></td>
<td><p>Clientes de Live Messenger</p></td>
<td><p>Se usa para sesiones de A/V con Windows Live Messenger si está configurada la conectividad de mensajería instantánea pública.</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>Interfaz de acceso al servidor perimetral</p></td>
<td><p>Clientes de Live Messenger</p></td>
<td><p>Necesario para la conectividad de mensajería instantánea pública con Windows Live Messenger.</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>Clientes de Live Messenger</p></td>
<td><p>Interfaz de acceso al servidor perimetral</p></td>
<td><p>Necesario para la conectividad de mensajería instantánea pública con Windows Live Messenger.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>Vea también


[Escenarios para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)  
[Determinar los requisitos de los puertos y el firewall de A/V externos en Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

