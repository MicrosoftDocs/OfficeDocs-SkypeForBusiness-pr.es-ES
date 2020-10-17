---
title: 'Lync Server 2013: lista de comprobación para la implementación del tronco SIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SIP trunk deployment checklist
ms:assetid: 94f4f03e-19d5-4198-92be-e4076dbb959a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398755(v=OCS.15)
ms:contentKeyID: 48184891
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 09c9916be9b32eb4a1fb0a5981cc6769bafc3420
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519707"
---
# <a name="sip-trunk-deployment-checklist-for-lync-server-2013"></a>Lista de comprobación para la implementación del tronco SIP para Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-21_

Para poder implementar un tronco SIP, primero debe intercambiar alguna información de conexión básica con su proveedor de servicios relacionada con sus respectivos extremos de tronco SIP.

Obtenga la información siguiente de cada una de las puertas de enlace del proveedor de servicios de telefonía por Internet a las que se vaya a conectar:

  - Dirección IP

  - Nombre de dominio completo (FQDN)

<div>


> [!NOTE]  
> Es posible que el proveedor de servicios le pida que se conecte a más de una puerta de enlace del proveedor de servicios de telefonía por Internet. En ese caso, debe configurar una conexión entre cada puerta de enlace de ITSP y cada uno de los servidores de mediación del grupo.



</div>

La información que facilita al proveedor de servicios depende del tipo de conexión del tronco SIP:

  - En el caso de conexiones de red privadas o de conmutación multiprotocolo mediante etiquetas (MPLS, Multiprotocol Label Switching) facilite al proveedor de servicios de telefonía por Internet la dirección IP enrutable públicamente del enrutador de su red perimetral (también conocida como extranet o subred filtrada). Compruebe que la puerta de enlace o el controlador de borde de sesión (SBC) del proveedor de servicios de telefonía por Internet pueda obtener acceso a esta dirección. Proporcione también al ITSP el FQDN del servidor de mediación.

  - Para conexiones de red privada virtual (VPN), facilítele también la dirección IP del servidor VPN.

<div>

## <a name="certificate-considerations"></a>Consideraciones de certificados

Para determinar si necesita un certificado para el enlace troncal SIP, infórmese con su proveedor de servicios de telefonía por Internet acerca de la compatibilidad con protocolos:

1.  Si solo admite el protocolo de control de transmisión (TCP), no necesita ningún certificado.

2.  Si admite el protocolo de seguridad de la capa de transporte (TLS), el proveedor de servicios de telefonía por Internet deberá proporcionarle un certificado.

<div>


> [!NOTE]  
> El protocolo SIP trabaja junto con el protocolo de transporte en tiempo real (RTP) o el protocolo de transporte seguro en tiempo real (SRTP), que son los encargados de administrar los datos de voz reales en las llamadas del protocolo de Voz sobre Protocolo de Internet (VoIP).



</div>

</div>

<div>

## <a name="deployment-process"></a>Proceso de implementación

Para implementar el lado de Lync Server de la conexión de tronco SIP, siga estos pasos:

1.  Mediante el generador de topologías de Lync Server, cree y configure la topología de dominio SIP. Para obtener información detallada, consulte [definir y configurar una topología en Topology Builder for Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md) en la documentación sobre implementación.

2.  Mediante el panel de control de Lync Server, configure el enrutamiento de voz para el nuevo dominio SIP. Para obtener más información, consulte [configuración de troncos en Lync Server 2013](lync-server-2013-configuring-trunks.md) en la documentación sobre implementación.

3.  Pruebe la conectividad con el cmdlet **Test-CsPstnOutboundCall**. Para obtener más información, consulte la documentación o la ayuda del shell de administración de Lync Server para el shell de administración de Lync Server.

</div>

</div>

<span> </span>

</div>

</div>

</div>

