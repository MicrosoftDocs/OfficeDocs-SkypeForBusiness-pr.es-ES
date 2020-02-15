---
title: 'Lync Server 2013: componentes y topologías para el enlace troncal SIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for SIP trunking
ms:assetid: 8ed9a9d0-517e-4f36-a131-22cdafa257fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398720(v=OCS.15)
ms:contentKeyID: 48184775
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a9e31b7cc0ea6e5acec0382ecd468a868152570d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007980"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-sip-trunking-in-lync-server-2013"></a>Componentes y topologías para el enlace troncal SIP en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-21_

En la siguiente figura se muestra la topología de enlace troncal SIP en Lync Server.

**Topología del enlace troncal SIP**

![Topología de enlace troncal SIP](images/Gg398720.669fb55d-7c81-4e21-9421-fabc43d6e064(OCS.15).jpg "Topología de enlace troncal SIP")

Como se muestra en el diagrama, se usa una red privada virtual (VPN) de IP para la conectividad entre la red empresarial y el proveedor de servicios de la red telefónica conmutada (RTC). El objetivo de esta red privada es proporcionar conectividad IP, mejorar la seguridad y obtener garantías (opcionales) de Calidad de servicio (QoS). Dada la naturaleza de una VPN, no necesita usar Seguridad de la capa de transporte (TLS) para el tráfico de señalización SIP ni el Protocolo de transporte en tiempo real seguro (SRTP) para el tráfico de medios. Las conexiones entre la empresa y el proveedor de servicios constan, por lo tanto, de conexiones TCP simples para SIP y el Protocolo de transporte en tiempo real (RTP) simple (sobre UDP) para los medios de túnel a través de una VPN de IP. Asegúrese de que todos los firewalls que hay entre los enrutadores de VPN tienen los puertos abiertos para permitir la comunicación de dichos enrutadores, y que las direcciones IP de los bordes externos de los enrutadores de VPN se pueden redirigir públicamente.

<div>


> [!IMPORTANT]  
> Consulte a su proveedor de servicios para saber si admite alta disponibilidad, incluida la conmutación por error. Si es así, tendrá que averiguar los procedimientos para instalarla. Por ejemplo, ¿necesita configurar solo una dirección IP y un tronco SIP en cada servidor de mediación, o debe configurar varios troncos SIP en cada servidor de mediación?<BR>Si tiene varios sitios centrales, pregunte también si el proveedor de servicios tiene la capacidad de habilitar conexiones hacia y desde otro sitio central.



</div>

<div>


> [!NOTE]  
> Para el enlace troncal SIP, se recomienda implementar servidores de mediación independientes. Para obtener más información, consulte <A href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">Deploying Mediation Servers and Defining Peers in Lync Server 2013</A> en la documentación sobre implementación.



</div>

<div>

## <a name="securing-the-mediation-server-for-sip-trunking"></a>Protección del servidor de mediación para el enlace troncal SIP

Por motivos de seguridad, debe instalar una LAN virtual (VLAN) por cada conexión que haya entre ambos enrutadores de VPN. El proceso concreto para instalar una VLAN varía según el fabricante del enrutador. Para obtener información detallada, contacte con el proveedor de su enrutador.

Se recomienda seguir estas instrucciones:

  - Configure una LAN virtual (VLAN) entre el servidor de mediación y el enrutador de VPN en la red perimetral (también denominada DMZ, zona desmilitarizada y subred filtrada).

  - No permita la difusión ni la transferencia de paquetes multidifusión desde el enrutador a la VLAN.

  - Bloquear todas las reglas de enrutamiento que enruten el tráfico del enrutador a cualquier lugar pero el servidor de mediación.

Si usa un servidor de VPN, se recomienda seguir estas instrucciones:

  - Configure una VLAN entre el servidor VPN y el servidor de mediación.

  - No permita la difusión ni la transmisión de paquetes multidifusión desde el servidor de VPN a la VLAN.

  - Bloquee todas las reglas de enrutamiento que enruten el tráfico del servidor VPN hacia cualquier lugar y el servidor de mediación.

  - Cifre los datos de la VPN mediante encapsulación de enrutamiento genérico (GRE).

</div>

</div>

<span> </span>

</div>

</div>

</div>

