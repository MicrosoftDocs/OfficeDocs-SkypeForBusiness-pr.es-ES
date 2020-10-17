---
title: 'Lync Server 2013: componente de servidor de mediación'
description: 'Lync Server 2013: componente de servidor de mediación.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mediation Server component
ms:assetid: 5b19edef-4a54-43c9-aa12-5643b8108355
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398399(v=OCS.15)
ms:contentKeyID: 48184239
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 08c11bff3ee7077d991204cda5a9885787c50ec2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568646"
---
# <a name="mediation-server-component-in-lync-server-2013"></a>Componente de servidor de mediación en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-21_

Debe implementar Lync Server 2013, servidor de mediación si implementa la carga de trabajo de Enterprise Voice. En esta sección se describe la funcionalidad básica, dependencias, topologías básicas y directrices de planeación.

El servidor de mediación traduce la señalización y, en algunas configuraciones, los medios entre la infraestructura de Lync Server 2013 interna, la infraestructura de telefonía IP empresarial y una puerta de enlace de red telefónica conmutada (RTC) o un tronco de protocolo de inicio de sesión (SIP). En el lado de Lync Server 2013, el servidor de mediación escucha en una sola dirección de transporte TLS mutua (MTLS). En el lado de la puerta de enlace, el servidor de mediación escucha en todos los puertos de escucha asociados con los troncos definidos en el documento de topología. Todas las puertas de enlace cualificadas deben admitir TLS, pero pueden estar habilitadas también para TCP. El protocolo TCP es compatible con puertas de enlace que no admiten TLS.

Si también tiene una central de conmutación (PBX) existente en su entorno, el servidor de mediación controla las llamadas entre los usuarios de Enterprise Voice y la PBX. Si la PBX es una IP-PBX, puede crear una conexión SIP directa entre la PBX y el servidor de mediación. Si su PBX es una PBX de división del tiempo (TDM), también debe implementar una puerta de enlace RTC entre el servidor de mediación y la PBX.

De forma predeterminada, el servidor de mediación se combina con el servidor front-end. El servidor de mediación también se puede implementar en un grupo de servidores independiente por motivos de rendimiento o si se implementa el enlace troncal SIP, en cuyo caso se recomienda encarecidamente el grupo de servidores independiente.

Si implementa conexiones SIP directas a una puerta de enlace RTC calificada que admita la omisión de medios y el equilibrio de carga de DNS, no es necesario disponer de un grupo de servidores de mediación independiente. No se necesita un servidor de mediación independiente, ya que las puertas de enlace cualificadas pueden realizar el equilibrio de carga de DNS para un grupo de servidores de mediación y pueden recibir tráfico de cualquier servidor de mediación de un grupo.

También recomendamos que instale el servidor de mediación en un grupo de servidores front-end cuando haya implementado sistemas PBX IP o que se conecte a un Controlador de borde de sesión (SBC) de servidor de telefonía por Internet, siempre y cuando se cumplan algunas de las siguientes condiciones:

  - El sistema IP-PBX o SBC esté configurado para recibir tráfico de cualquier servicio de mediación del grupo de servidores y pueda enrutar el tráfico uniformemente a todos los servidores de mediación del grupo.

  - La IP-PBX no admite el desvío de medios, pero el grupo de servidores front-end que hospeda el servidor de mediación puede controlar la transcodificación de voz para las llamadas en las que no se aplique el desvío de medios.

Puede usar la herramienta de planeación 2013 de Microsoft Lync Server para evaluar si el grupo de servidores front-end en el que desea combinar el servidor de mediación puede controlar la carga. Si el entorno no cumple estos requisitos, deberá implementar un grupo de servidores de mediación independiente.

Las funciones principales del servidor de mediación son las siguientes:

  - Cifrar y descifrar SRTP en el lado servidor de Lync

  - Convertir SIP sobre TCP (para puertas de enlace que no admiten TLS) en SIP sobre Mutual TLS

  - Conversión de transmisiones multimedia entre Lync Server y la puerta de enlace del mismo nivel del servidor de mediación

  - Conectar clientes que están fuera de la red con componentes ICE internos, que habilitan el paso de los medios a través de NAT y firewalls

  - Actuar como intermediario de los flujos de llamada que una puerta de enlace no admite, como las llamadas de los trabajadores remotos en un cliente de telefonía IP empresarial

  - En implementaciones que incluyen enlaces troncales SIP, trabajar con el proveedor de servicios de enlaces troncales SIP para proporcionar compatibilidad con la RTC, con lo que se elimina la necesidad de una puerta de enlace de RTC

En la siguiente figura se muestran los protocolos de señalización y medios que usa el servidor de mediación al comunicarse con una puerta de enlace RTC básica y la infraestructura de Enterprise Voice.

**Señalización y protocolos multimedia que usa el servidor de mediación**

![Diagrama de protocolos del servidor de mediación](images/Gg398399.c3d39ba0-e323-4a58-8f07-4e80d3278af2(OCS.15).jpg "Diagrama de protocolos del servidor de mediación")

<div>


> [!NOTE]  
> Si usa TCP o RTP/RTCP (en lugar de SRTP o SRTCP) en la red entre la puerta de enlace RTC y el servidor de mediación, le recomendamos que adopte las medidas necesarias para garantizar la seguridad y privacidad de la red.



</div>

<div>

## <a name="in-this-section"></a>En esta sección

  - [M:N troncal en Lync Server 2013](lync-server-2013-m-n-trunk.md)

  - [Control de admisión de llamadas y servidor de mediación en Lync Server 2013](lync-server-2013-call-admission-control-and-mediation-server.md)

  - [Enhanced 9-1-1 (E9-1-1) y servidor de mediación en Lync Server 2013](lync-server-2013-enhanced-9-1-1-e9-1-1-and-mediation-server.md)

  - [Omisión de medios y servidor de mediación en Lync Server 2013](lync-server-2013-media-bypass-and-mediation-server.md)

  - [Componentes y topologías para el servidor de mediación en Lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md)

  - [Instrucciones de implementación para el servidor de mediación en Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

