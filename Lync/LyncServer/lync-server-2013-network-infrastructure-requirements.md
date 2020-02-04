---
title: Requisitos de la infraestructura de red de Lync Server 2013
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
ms.openlocfilehash: fcded907075b6587eb62ea8b6b76566c4f29ac87
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765921"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="network-infrastructure-requirements-for-lync-server-2013"></a>Requisitos de infraestructura de red para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-18_

La tarjeta adaptadora de red de cada servidor de la topología de Lync Server 2013 debe admitir al menos 1 Gigabit por segundo (Gbps). En general, debe conectar todos los roles de servidor dentro de la topología de Lync Server con una red de área local (LAN) de baja latencia y ancho de banda alto. El tamaño de la LAN depende del tamaño de la topología:

  - En las topologías de Standard Edition, los servidores deben estar en una red que admita 1 Gbps de Ethernet o equivalente.

  - En las topologías de grupos de servidores front-end, la mayoría de los servidores deberían estar en una red que admita más de 1 Gbps, especialmente cuando se admiten conferencias de audio/vídeo (A/V) y uso compartido de aplicaciones.

Para la integración de la red telefónica conmutada (RTC), puede usar líneas T1/E1 o enlaces troncales SIP.

<div>

## <a name="audiovideo-network-requirements"></a>Requisitos de red de audio o vídeo

Entre los requisitos de red para audio/vídeo (A/V) en una implementación de Lync Server se incluyen los siguientes:

  - Si implementa un único servidor perimetral o un grupo de límites mediante el equilibrio de carga de DNS, puede configurar el firewall externo como NAT. El firewall interno no se puede configurar como NAT. Para obtener más información sobre estos requisitos, consulte [determinar el firewall externo a/V y los requisitos de puerto para Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md) en la documentación de planeación.
    
    <div>
    

    > [!IMPORTANT]  
    > Si tiene un grupo perimetral y usa un equilibrador de carga de hardware, debe usar direcciones IP públicas en cada uno de los servidores perimetrales y no puede usar NAT para los servidores o el grupo en el dispositivo NAT (por ejemplo, el Firewall u otro dispositivo de infraestructura que pueda ser NAT Inbou tráfico ND o saliente). Para obtener más información, consulte <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">Resumen por puerto: borde consolidado escalado con equilibradores de carga de hardware en Lync Server 2013</A> en la documentación de planeación de usuarios externos.

    
    </div>

  - Si la organización usa una infraestructura QoS (Calidad de servicio), el subsistema de medios estará diseñado de modo que funcione con esta infraestructura existente.

  - Si usa el protocolo de seguridad de Internet (IPsec), recomendamos deshabilitar IPsec en los intervalos de puertos usados para el tráfico de audio y vídeo. Para obtener más información, consulte [excepciones de IPSec en Lync Server 2013](lync-server-2013-ipsec-exceptions.md) en la documentación de planeación.

Para garantizar una óptima calidad de medios, haga lo siguiente:

  - Aprovisione los vínculos de red para admitir el rendimiento de 65 kilobits por segundo (kbps) por secuencia de audio y 500 Kbps por secuencia de vídeo, si está habilitado, durante períodos de uso máximo. Una sesión de audio o video bidireccional consta de dos secuencias.

  - Para hacer frente a picos inesperados en el tráfico por encima de este nivel y mayor uso a lo largo del tiempo, los puntos de conexión de Lync Server media se pueden adaptar a condiciones de red variables y admitir cargas tres veces el rendimiento (vea el párrafo anterior) de audio y vídeo al mismo tiempo mantener la calidad aceptable. Sin embargo, no asumas que esta adaptabilidad será compatible con una red con el preaprovisionamiento. En una red con aprovisionamiento inhabilitado, la capacidad de los puntos de conexión multimedia de Lync Server para tratar dinámicamente con diversas condiciones de red (por ejemplo, pérdida de paquetes temporales altos) se reduce.

  - En el caso de los vínculos de red en los que el aprovisionamiento es muy económico y difícil, es posible que tenga que considerar el suministro para un menor volumen de tráfico. En este escenario, deje que la elasticidad de los puntos de conexión multimedia de Lync Server absorba la diferencia entre el volumen de tráfico y el nivel de tráfico máximo, a costa de reducir la calidad de la voz. Además, hay una disminución en el espacio que, de otro modo, está disponible para absorber picos repentinos del tráfico.

  - Para los vínculos que no se pueden aprovisionar correctamente a corto plazo (por ejemplo, un sitio con vínculos WAN muy deficientes), deshabilite el vídeo para determinados usuarios.

  - Aprovisione su red para garantizar un retardo (latencia) extremo a extremo máximo (latencia) de 150 milisegundos (MS) en carga máxima. Latencia es el posible deterioro de red que los componentes multimedia de Lync Server no pueden reducir y es importante buscar y eliminar los puntos débiles.

  - En el caso de los servidores que ejecutan software antivirus, incluya todos los servidores que ejecutan Lync Server en la lista de excepciones para proporcionar un rendimiento óptimo y una calidad de audio.

</div>

<div>

## <a name="conferencing-network-requirements"></a>Requisitos de la red de conferencias

El ancho de banda que se usa para descargar el contenido de la Conferencia del servidor de servicios de Internet Information Server (IIS) depende del tamaño del contenido que se carga.

</div>

</div>

<span> </span>

</div>

</div>

</div>

