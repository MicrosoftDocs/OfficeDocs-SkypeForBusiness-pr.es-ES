---
title: 'Lync Server 2013: Lista de comprobaciones para la implementación del enlace troncal SIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: SIP trunk deployment checklist
ms:assetid: 94f4f03e-19d5-4198-92be-e4076dbb959a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398755(v=OCS.15)
ms:contentKeyID: 48184891
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7854693702f1583ccaeb2ae6d54a1c7cb9bbcbcd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850626"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sip-trunk-deployment-checklist-for-lync-server-2013"></a>Lista de comprobaciones para la implementación del enlace troncal SIP para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-21_

Antes de que puedas implementar un tronco de SIP, tú y tu proveedor de servicios deben intercambiar información básica sobre los puntos de conexión de tu troncal de SIP.

Obtenga la siguiente información para cada puerta de enlace de ITSP a la que se conectará:

  - Dirección IP

  - Nombre de dominio completo (FQDN)

<div>


> [!NOTE]  
> Es posible que el proveedor de servicios le pida que se conecte a más de una puerta de enlace de ITSP. En ese caso, debe configurar una conexión entre cada una de las puertas de enlace de ITSP y cada servidor de mediación de su grupo.



</div>

La información que asignes a tu proveedor de servicios depende de tu tipo de conexión troncal de SIP:

  - En el caso de las conexiones de red privada o de cambio multiprotocolo (MPLS), asigne a la ITSP la dirección IP de enrutamiento pública del enrutador en la red perimetral (también conocida como DMZ, zona desmilitarizada y subred filtrada). Compruebe que la puerta de enlace o el controlador de borde de sesión (SBC) en el ITSP puede comunicarse con esta dirección. Además, da al ITSP el FQDN de tu servidor de mediación.

  - En el caso de las conexiones de red privada virtual (VPN), asigne a la ITSP la dirección IP de su servidor VPN.

<div>

## <a name="certificate-considerations"></a>Consideraciones de certificados

Para determinar si necesita un certificado para la Troncalización SIP, consulte a su ITSP acerca de la compatibilidad con el protocolo:

1.  Si su ITSP es compatible con el protocolo de control de transmisión (TCP), no necesita un certificado.

2.  Si su ITSP es compatible con la seguridad de la capa de transporte (TLS), ITSP debe proporcionarle un certificado.

<div>


> [!NOTE]  
> SIP funciona junto con el protocolo de transporte en tiempo real (RTP) o el protocolo de transporte seguro en tiempo real (SRTP), los protocolos que administran los datos de voz reales en las llamadas de voz a través del Protocolo de Internet (VoIP).



</div>

</div>

<div>

## <a name="deployment-process"></a>Proceso de implementación

Para implementar el lado servidor de Lync de la conexión de troncal de SIP, siga estos pasos:

1.  Con el generador de topologías de Lync Server, cree y configure la topología de dominio SIP. Para obtener más información, vea [definir y configurar una topología en el generador de topología para Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md) en la documentación de implementación.

2.  Use el panel de control de Lync Server para configurar el enrutamiento de voz para el nuevo dominio SIP. Para obtener más información, vea [configuración de troncos en Lync Server 2013](lync-server-2013-configuring-trunks.md) en la documentación de implementación.

3.  Pruebe la conectividad mediante el cmdlet **Test-CsPstnOutboundCall** . Para obtener más información, vea la documentación del shell de administración de Lync Server o la ayuda del shell de administración de Lync Server.

</div>

</div>

<span> </span>

</div>

</div>

</div>

