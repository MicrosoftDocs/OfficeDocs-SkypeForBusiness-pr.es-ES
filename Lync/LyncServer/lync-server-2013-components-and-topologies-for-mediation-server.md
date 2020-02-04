---
title: 'Lync Server 2013: Componentes y topologías para el servidor de mediación'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for Mediation Server
ms:assetid: 71397168-36c3-4d21-b8ef-db6a751634ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398537(v=OCS.15)
ms:contentKeyID: 48184487
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 62516645266f67b7be61154b45afd00107ec3814
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742620"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-mediation-server-in-lync-server-2013"></a>Componentes y topologías para el servidor de mediación en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-21_

En este tema se describen los componentes de los que depende el servidor de mediación y las topologías en las que se puede implementar el servidor de mediación.

<div>

## <a name="dependencies"></a>Dependencias

El servidor de mediación tiene las siguientes dependencias:

  - **Registro.** Obligatorio. El registrador es el próximo salto para la señalización en las interacciones del servidor de mediación con la red de Lync Server 2013. Tenga en cuenta que el servidor de mediación se puede poner en un servidor front-end junto con el registrador, además de instalarse en un grupo independiente que solo contiene servidores de mediación. El registrador se colocará con un servidor de mediación y una puerta de enlace RTC en una aplicación de rama superviviente.

  - **Servidor de supervisión.** Opcional, pero muy recomendable. El servidor de supervisión permite que el servidor de mediación grabe métricas de calidad asociadas a sus sesiones de medios.

  - **Servidor perimetral.** Necesario para la compatibilidad con usuarios externos. El servidor perimetral permite que el servidor de mediación interactúe con los usuarios que se encuentran detrás de un NAT o firewall.

</div>

<div>

## <a name="topologies"></a>Topologías

Lync Server 2013, el servidor de mediación se encuentra de forma predeterminada con una instancia del registrador en un servidor Standard Edition, un grupo front-end o una aplicación de rama Reactivable. Todos los servidores de mediación de un grupo de servidores front-end se deben configurar de la misma manera.

Cuando el rendimiento es un problema, puede ser preferible implementar uno o varios servidores de mediación en un grupo independiente dedicado. O bien, si va a implementar una Troncalización SIP, le recomendamos que implemente un grupo de servidores de mediación independiente.

Si implementa conexiones SIP directas en una puerta de enlace PSTN calificada que admite la omisión de medios y el equilibrio de carga de DNS, no es necesario disponer de un grupo de servidores de mediación independiente. No es necesario un grupo de servidores de mediación independiente porque las puertas de enlace válidas son capaces de equilibrar la carga de DNS en un grupo de servidores de mediación y pueden recibir tráfico de cualquier servidor de mediación de un grupo.

También le recomendamos que Collocate el servidor de mediación en un grupo de servidores front-end cuando haya implementado PBX IP o conecte con un controlador de borde de sesión (SBC) de un proveedor de servicios de telefonía por Internet, siempre que se cumpla cualquiera de las siguientes condiciones:

  - El IP-PBX o SBC está configurado para recibir tráfico de cualquier servidor de mediación del grupo y puede enrutar uniformemente el tráfico a todos los servidores de mediación del grupo.

  - El IP-PBX no admite la omisión de medios, pero el grupo de servidores front-end que hospeda el servidor de mediación puede controlar la transcodificación de voz para las llamadas a las que no se aplica la omisión de medios.

Puede usar la herramienta de planeación de Microsoft Lync Server 2013 para evaluar si el grupo de servidores front-end en el que desea Collocate el servidor de mediación puede controlar la carga. Si su entorno no puede cumplir estos requisitos, debe implementar un grupo de servidores de mediación independiente.

Para más información sobre qué topología implementar, vea [directrices de implementación para servidor de mediación en Lync server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).

En la siguiente figura se muestra una topología sencilla que consta de dos sitios conectados a través de un vínculo WAN. El servidor de mediación se encuentra en el registrador de un grupo de servidores front-end en el sitio 1. Los servidores de mediación del sitio 1 controlan la puerta de enlace PSTN en el sitio 1 y la puerta de enlace en el sitio 2. En esta topología, la omisión de medios se habilita de forma global para usar la información del sitio y de la región, y los troncos a cada una de las puertas de enlace RTC (GW1 y GW2) tienen la omisión habilitada.

**Ejemplo de sitios conectados por medio de un vínculo WAN con un servidor de mediación en el Sitio 1 y una puerta de enlace RTC en el Sitio 2**

![Puerta de enlace de WAN de topología de voz con servidor de mediación](images/Gg398537.67872e61-1444-447b-918c-abe89abc3004(OCS.15).jpg "Puerta de enlace de WAN de topología de voz con servidor de mediación")

La siguiente figura muestra una topología simple en la que el servidor de mediación se encuentra con el registrador en el grupo front-end en el sitio 1 y tiene una conexión SIP directa con IP-PBX en el sitio 1. En esta ilustración, el servidor de mediación también controla una puerta de enlace RTC en el sitio 2. Supongamos que los usuarios de Lync existen en los dos sitios 1 y 2. También se supone que el IP-PBX tiene un procesador de medios asociado al que deben atravesarse todos los medios originarios de los puntos de conexión de Lync antes de enviarlos a los puntos de conexión multimedia controlados por el IP-PBX. En esta topología, la omisión de medios se habilita de forma global para usar la información del sitio y de la región, y los troncos a la puerta de enlace RTC y la PBX tienen la omisión de medios habilitada.

**Ejemplo de sitios conectados mediante un vínculo WAN con un servidor de mediación en el Sitio 1 y un sistema PBX en el Sitio 2**

![PBX de WAN del servidor de mediación de topología de voz](images/Gg398537.df6c8a5b-8431-4187-907d-ff5ca26eeeec(OCS.15).jpg "PBX de WAN del servidor de mediación de topología de voz")

Para más información sobre la planeación de topologías PBX, vea [directrices de implementación para servidor de mediación en Lync server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md) y [Opciones de implementación de SIP directo en Lync Server 2013](lync-server-2013-direct-sip-deployment-options.md).

En la última ilustración de este tema se muestra una topología en la que el servidor de mediación está conectado al SBC de un proveedor de servicios de telefonía por Internet. Para obtener más información sobre las topologías de tronco de SIP, consulte [SIP trunking in Lync Server 2013](lync-server-2013-sip-trunking.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

