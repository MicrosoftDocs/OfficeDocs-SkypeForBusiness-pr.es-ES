---
title: Requisitos de la infraestructura de red de Lync Server 2013
description: Requisitos de la infraestructura de red de Lync Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Network infrastructure requirements
ms:assetid: 35c7bb3f-8e0f-48b7-8a2c-857d4b42a4c4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425841(v=OCS.15)
ms:contentKeyID: 48183804
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6f7ff21c2f936ef8e048f6831d55408994055400
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561506"
---
# <a name="network-infrastructure-requirements-for-lync-server-2013"></a>Requisitos de la infraestructura de red para Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-18_

La tarjeta adaptadora de red de cada servidor de la topología de Lync Server 2013 debe admitir al menos 1 Gigabit por segundo (Gbps). En general, debe conectar todos los roles de servidor dentro de la topología de Lync Server usando una red de área local (LAN) de baja latencia y gran ancho de banda. El tamaño de la LAN depende del tamaño de la topología:

  - En las topologías de Standard Edition, los servidores deben estar en una red que admita Ethernet de 1 Gbps o equivalente.

  - En las topologías del grupo de servidores front-end, la mayoría de los servidores deben estar en una red que admita más de 1 Gbps, especialmente cuando se admiten conferencias de audio y vídeo (A/V) y uso compartido de aplicaciones.

Para la integración de la red telefónica conmutada (RTC), puede usar líneas T1/E1 o enlaces troncales SIP.

<div>

## <a name="audiovideo-network-requirements"></a>Requisitos de red para el audio y vídeo

Entre los requisitos de red para audio y vídeo (A/V) en una implementación de Lync Server se incluyen los siguientes:

  - Si va a implementar un solo servidor perimetral o un grupo de servidores perimetrales mediante el equilibrio de carga de DNS, puede configurar el firewall externo como NAT. No puede configurar el firewall interno como un NAT. Para obtener más información sobre estos requisitos, consulte [determine external a/V Firewall and Port Requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md) en la documentación referente a la planeación.
    
    <div>
    

    > [!IMPORTANT]  
    > Si tiene un grupo de servidores perimetrales y usa un equilibrador de carga de hardware, debe usar direcciones IP públicas en cada uno de los servidores perimetrales y no puede usar NAT para los servidores o el grupo de servidores en el dispositivo NAT (por ejemplo, el Firewall u otro dispositivo de infraestructura que NAT tráfico entrante o saliente). Para obtener más información, consulte <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">Port Summary-Scaled Consolidated Edge with hardware Load balances in Lync Server 2013</A> en la documentación de Planning for external User Access.

    
    </div>

  - Si la organización usa una infraestructura QoS (Calidad de servicio), el subsistema de medios estará diseñado de modo que funcione con esta infraestructura existente.

  - Si usa el protocolo de seguridad de Internet (IPsec), se recomienda deshabilitar IPsec en los intervalos de puertos usados para el tráfico de audio y vídeo. Para obtener más información, consulte [excepciones de IPSec en Lync Server 2013](lync-server-2013-ipsec-exceptions.md) en la documentación referente a la planeación.

Para asegurar una calidad óptima de los medios, siga este procedimiento:

  - Aprovisione los vínculos de red para que admitan una capacidad de proceso de 65 kilobits por segundo (Kbps) por secuencia de audio y 500 Kbps por secuencia de vídeo en los períodos de uso máximo. Una sesión bidireccional de audio o vídeo consta de dos secuencias.

  - Para hacer frente a picos inesperados en el tráfico por encima de este nivel y mayor uso a lo largo del tiempo, los extremos de medios de Lync Server se pueden adaptar a distintas condiciones de red y admitir cargas de tres veces el rendimiento (ver párrafo anterior) para audio y vídeo, al mismo tiempo que conservan la calidad aceptable. No obstante, no se puede dar por sentado que esta capacidad de adaptación admita una red mal aprovisionada. En una red aprovisionada inhabilitada, se reduce la capacidad de los extremos de medios de Lync Server para tratar dinámicamente las distintas condiciones de red (por ejemplo, una pérdida de paquetes alta temporal).

  - En el caso de los vínculos de red donde el aprovisionamiento resulta muy costoso y difícil, puede que se vea obligado a considerar un aprovisionamiento para un menor volumen de tráfico. En este escenario, permita que la elasticidad de los puntos de conexión multimedia de Lync Server absorba la diferencia entre el volumen de tráfico y el nivel de tráfico máximo, a costa de una reducción de la calidad de la voz. También hay una disminución en el margen que normalmente está disponible para absorber los picos de tráfico repentinos.

  - En el caso de los vínculos que no se pueden aprovisionar correctamente a corto plazo (por ejemplo, un sitio con vínculos WAN de muy poca calidad), considere la posibilidad de deshabilitar el vídeo para algunos usuarios.

  - Aprovisione la red para asegurar un retraso máximo de un extremo a otro (latencia) de 150 milisegundos (ms) con carga máxima. La latencia es la única discapacidad de red que los componentes multimedia de Lync Server no pueden reducir y es importante buscar y eliminar los puntos débiles.

  - En el caso de los servidores que ejecutan software antivirus, incluya todos los servidores que ejecutan Lync Server en la lista de excepciones para proporcionar un rendimiento y una calidad de audio óptimos.

</div>

<div>

## <a name="conferencing-network-requirements"></a>Requisitos de red de la conferencia

El ancho de banda que se usa para descargar contenido de conferencia del servidor de Internet Information Services (IIS) depende del tamaño del contenido que se carga.

</div>

</div>

<span> </span>

</div>

</div>

</div>

