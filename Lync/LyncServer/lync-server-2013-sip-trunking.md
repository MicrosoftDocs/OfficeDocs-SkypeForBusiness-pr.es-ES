---
title: 'Lync Server 2013: enlace troncal SIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SIP trunking
ms:assetid: 7c586401-d0e5-4017-b3e1-fe5e7f8fc6db
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398619(v=OCS.15)
ms:contentKeyID: 48184615
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f3ee2efb7f1c392b20bdc6b16ff3c7063ebe4759
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200303"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="sip-trunking-in-lync-server-2013"></a>Enlace troncal SIP en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-08-13_

El Protocolo de inicio de sesión (SIP) se usa para iniciar y administrar sesiones de comunicaciones de voz sobre IP (VoIP) del servicio telefónico básico y para otros servicios de comunicación en tiempo real, como la mensajería instantánea, las conferencias, la detección de presencia y los elementos multimedia. Esta sección ofrece información sobre la planeación para implementar *troncos SIP*, un tipo de conexión SIP que se extiende más allá del límite de su red local.

<div>

## <a name="what-is-sip-trunking"></a>¿Qué es el enlace troncal SIP?

Un tronco SIP es una conexión IP que establece un vínculo de comunicaciones SIP entre su organización y un proveedor de servicios de telefonía de Internet (ITSP) más allá de su firewall. En general, los troncos SIP se usan para conectar el sitio central de una organización a un ITSP. En ciertos casos, se puede usar también el enlace troncal SIP para conectar una sucursal a un ITSP.

<div>

## <a name="sip-trunks-vs-direct-sip-connections"></a>Troncos SIP y conexiones SIP directas

El término *tronco* deriva de la tecnología de circuitos conmutados. Se refiere a una línea física dedicada que conecta el equipo de conmutación telefónica. Como sus antecesores, los troncos de multiplexación por división de tiempo (TDM), los troncos SIP son conexiones entre dos redes SIP independientes: la empresa Lync Server 2013 y la ITSP. A diferencia de los troncos de circuitos conmutados, los enlaces troncales SIP son conexiones virtuales que se pueden establecer sobre cualquiera de los tipos de conexión de enlaces troncales SIP compatibles. Para obtener más información sobre los tipos de conexión compatibles, vea [¿cómo se implementa el enlace troncal SIP en Lync Server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md).

Por otra parte, las conexiones SIP directas son conexiones SIP que no cruzan los límites de la red local (es decir, que se conectan a central de conmutación (PBX) o a una red telefónica conmutada (RTC) dentro de su red local). Para obtener información detallada sobre cómo usar las conexiones SIP directas con Lync Server 2013, consulte [Direct SIP Connections in Lync server 2013](lync-server-2013-direct-sip-connections.md).

</div>

</div>

<div>

## <a name="in-this-section"></a>En esta sección

  - [Información general sobre el enlace troncal SIP en Lync Server 2013](lync-server-2013-overview-of-sip-trunking.md)

  - [¿Cómo puedo implementar el enlace troncal SIP en Lync Server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md)

  - [Componentes y topologías para el enlace troncal SIP en Lync Server 2013](lync-server-2013-components-and-topologies-for-sip-trunking.md)

  - [Enlace troncal SIP de sitios de sucursal en Lync Server 2013](lync-server-2013-branch-site-sip-trunking.md)

  - [Lista de comprobación para la implementación del tronco SIP para Lync Server 2013](lync-server-2013-sip-trunk-deployment-checklist.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

