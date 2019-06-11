---
title: 'Lync Server 2013: componente de servidor de mediación'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Mediation Server component
ms:assetid: 5b19edef-4a54-43c9-aa12-5643b8108355
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398399(v=OCS.15)
ms:contentKeyID: 48184239
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1f3476f8b4e99b2abccb67f1d75446a126df03d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827231"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mediation-server-component-in-lync-server-2013"></a>Componente de servidor de mediación de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-21_

Debe implementar Lync Server 2013, servidor de mediación si implementa la carga de trabajo de telefonía IP empresarial. En esta sección se describen la funcionalidad básica, las dependencias, las topologías básicas y las directrices de planificación.

El servidor de mediación traduce la señalización y, en algunas configuraciones, multimedia entre su Lync Server 2013 interno, la infraestructura de telefonía IP empresarial y una puerta de enlace de red telefónica conmutada (RTC) o un tronco de protocolo de inicio de sesión (SIP). En el lado de Lync Server 2013, el servidor de mediación escucha en una única dirección de transporte TLS Mutual (MTLS). En la puerta de enlace, el servidor de mediación escucha en todos los puertos de escucha asociados a los troncos definidos en el documento de topología. Todas las puertas de enlace calificadas necesitan compatibilidad con TLS, pero también pueden habilitar TCP. TCP es compatible con las puertas de enlace que no son compatibles con TLS.

Si también tiene una central de conmutación (PBX) existente en su entorno, el servidor de mediación controla las llamadas entre los usuarios de voz de empresa y la PBX. Si su PBX es IP-PBX, puede crear una conexión SIP directa entre la PBX y el servidor de mediación. Si su PBX es un PBX de división de tiempo (TDM), también debe implementar una puerta de enlace RTC entre el servidor de mediación y la PBX.

El servidor de mediación se encuentra en el servidor front-end de forma predeterminada. El servidor de mediación también se puede implementar en un grupo independiente por razones de rendimiento o si implementa la Troncalización SIP, en cuyo caso se recomienda encarecidamente el grupo independiente.

Si implementa conexiones SIP directas en una puerta de enlace PSTN calificada que admite la omisión de medios y el equilibrio de carga de DNS, no es necesario disponer de un grupo de servidores de mediación independiente. No es necesario un grupo de servidores de mediación independiente porque las puertas de enlace válidas son capaces de equilibrar la carga de DNS en un grupo de servidores de mediación y pueden recibir tráfico de cualquier servidor de mediación de un grupo.

También le recomendamos que Collocate el servidor de mediación en un grupo de servidores front-end cuando haya implementado PBX IP o conecte con un controlador de borde de sesión (SBC) de un proveedor de servicios de telefonía por Internet, siempre que se cumpla cualquiera de las siguientes condiciones:

  - El IP-PBX o SBC está configurado para recibir tráfico de cualquier servidor de mediación del grupo y puede enrutar uniformemente el tráfico a todos los servidores de mediación del grupo.

  - El IP-PBX no admite la omisión de medios, pero el grupo de servidores front-end que hospeda el servidor de mediación puede controlar la transcodificación de voz para las llamadas a las que no se aplica la omisión de medios.

Puede usar la herramienta de planeación de Microsoft Lync Server 2013 para evaluar si el grupo de servidores front-end en el que desea Collocate el servidor de mediación puede controlar la carga. Si su entorno no puede cumplir estos requisitos, debe implementar un grupo de servidores de mediación independiente.

Las funciones principales del servidor de mediación son las siguientes:

  - Cifrar y descifrar SRTP en el servidor de Lync

  - Conversión de SIP a través de TCP (para puertas de enlace que no admiten TLS) a SIP a través de TLS Mutual

  - Traducción de transmisiones de medios entre Lync Server y Gateway peer of the Media Server

  - Conectar clientes que están fuera de la red a componentes de ICE internos, que permiten un recorrido multimedia de NAT y firewalls

  - Actuar como intermediario de los flujos de llamadas que no admite una puerta de enlace, como las llamadas de trabajadores remotos en un cliente de telefonía empresarial

  - En las implementaciones que incluyen el Troncalización SIP, al trabajar con el proveedor de servicios de Troncalización SIP para proporcionar compatibilidad con RTC, que elimina la necesidad de una puerta de enlace RTC

La siguiente ilustración muestra los protocolos de señalización y multimedia que usa el servidor de mediación al comunicarse con una puerta de enlace PSTN básica y la infraestructura de telefonía IP empresarial.

**Señalización y protocolos multimedia que usa el servidor de mediación**

![Diagrama protocolos de servidor] de mediación (images/Gg398399.c3d39ba0-e323-4a58-8f07-4e80d3278af2(OCS.15).jpg "Diagrama protocolos de servidor") de mediación

<div>


> [!NOTE]  
> Si está usando TCP o RTP/RTCP (en lugar de SRTP o SRTCP) en la red entre la puerta de enlace PSTN y el servidor de mediación, le recomendamos que tome medidas para garantizar la seguridad y la privacidad de la red.



</div>

<div>

## <a name="in-this-section"></a>En esta sección

  - [M:N troncal en Lync Server 2013](lync-server-2013-m-n-trunk.md)

  - [Control de admisión de llamadas y servidor de mediación en Lync Server 2013](lync-server-2013-call-admission-control-and-mediation-server.md)

  - [9-1-1 mejorado (E9-1-1) y servidor de mediación en Lync Server 2013](lync-server-2013-enhanced-9-1-1-e9-1-1-and-mediation-server.md)

  - [Omisión de medios y servidor de mediación en Lync Server 2013](lync-server-2013-media-bypass-and-mediation-server.md)

  - [Componentes y topologías para el servidor de mediación en Lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md)

  - [Instrucciones de implementación para el servidor de mediación en Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

