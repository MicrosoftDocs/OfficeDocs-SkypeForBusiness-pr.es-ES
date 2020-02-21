---
title: 'Lync Server 2013: componentes y topologías para el servidor de mediación'
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
ms.openlocfilehash: a1b6c824da8eccaec0cb48450b0d81dddcc60f99
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187993"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

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

  - **Dominios.** Necesario. El registrador es el próximo salto para la señalización en las interacciones del servidor de mediación con la red Lync Server 2013. Tenga en cuenta que el servidor de mediación se puede combinar en un servidor front-end junto con el registrador, además de estar instalado en un grupo independiente que solo consista en servidores de mediación. El registrador se combina con un servidor de mediación y una puerta de enlace RTC en una aplicación de sucursal con funciones de supervivencia.

  - **Servidor de supervisión.** Opcional pero muy recomendable. El servidor de supervisión permite que el servidor de mediación registre las métricas de calidad asociadas con sus sesiones de medios.

  - **Servidor perimetral.** Obligatorio para la compatibilidad con usuarios externos. El servidor perimetral permite que el servidor de mediación interactúe con los usuarios que se encuentren detrás de un firewall o NAT.

</div>

<div>

## <a name="topologies"></a>Topologías

El servidor de mediación de Lync Server 2013, que se combina de forma predeterminada con una instancia del registrador en un servidor Standard Edition, un grupo de servidores front-end o una aplicación de sucursal con funciones de supervivencia. Todos los servidores de mediación de un grupo de servidores front-end deben estar configurados de forma idéntica.

Cuando el rendimiento es un problema, es preferible implementar uno o varios servidores de mediación en un grupo independiente dedicado. O bien, si va a implementar un enlace troncal SIP, le recomendamos que implemente un grupo de servidores de mediación independiente.

Si implementa conexiones SIP directas a una puerta de enlace RTC calificada que admita la omisión de medios y el equilibrio de carga de DNS, no es necesario disponer de un grupo de servidores de mediación independiente. No se necesita un servidor de mediación independiente, ya que las puertas de enlace cualificadas pueden realizar el equilibrio de carga de DNS para un grupo de servidores de mediación y pueden recibir tráfico de cualquier servidor de mediación de un grupo.

También recomendamos que instale el servidor de mediación en un grupo de servidores front-end cuando haya implementado sistemas PBX IP o que se conecte a un Controlador de borde de sesión (SBC) de servidor de telefonía por Internet, siempre y cuando se cumplan algunas de las siguientes condiciones:

  - El sistema IP-PBX o SBC esté configurado para recibir tráfico de cualquier servicio de mediación del grupo de servidores y pueda enrutar el tráfico uniformemente a todos los servidores de mediación del grupo.

  - La IP-PBX no admite el desvío de medios, pero el grupo de servidores front-end que hospeda el servidor de mediación puede controlar la transcodificación de voz para las llamadas en las que no se aplique el desvío de medios.

Puede usar la herramienta de planeación 2013 de Microsoft Lync Server para evaluar si el grupo de servidores front-end en el que desea combinar el servidor de mediación puede controlar la carga. Si el entorno no cumple estos requisitos, deberá implementar un grupo de servidores de mediación independiente.

Para obtener información detallada sobre la topología que se va a implementar, consulte [directrices de implementación para servidor de mediación en Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).

En la siguiente figura se muestra una topología sencilla que consta de dos sitios conectados mediante un vínculo WAN. El servidor de mediación se combina con el registrador en un grupo de servidores front-end en el sitio 1. Los servidores de mediación en el sitio 1 controlan tanto la puerta de enlace RTC en el sitio 1 como la puerta de enlace en el sitio 2. En esta topología, el desvío de medios se habilita globalmente para usar la información de sitio y de región, y los troncos a cada una de las puertas de enlace RTC (GW1 y GW2) tienen el desvío habilitado.

**Ejemplo de sitios conectados mediante un vínculo WAN con un servidor de mediación en el Sitio 1 y una puerta de enlace RTC en el Sitio 2**

![Topología de voz con puerta de enlace WAN del servidor de mediación](images/Gg398537.67872e61-1444-447b-918c-abe89abc3004(OCS.15).jpg "Topología de voz con puerta de enlace WAN del servidor de mediación")

En la siguiente figura se muestra una topología sencilla en la que el servidor de mediación se combina con el registrador del grupo de servidores front-end en el sitio 1 y tiene una conexión SIP directa con el IP-PBX en el sitio 1. En esta figura, el servidor de mediación también controla una puerta de enlace RTC en el sitio 2. Supongamos que los usuarios de Lync existen en los sitios 1 y 2. Supongamos también que la IP-PBX tiene un procesador de medios asociado que debe atravesar todos los medios que provienen de los puntos de conexión de Lync antes de enviarlos a los extremos de medios controlados por la IP-PBX. En esta topología, el desvío de medios se habilita globalmente para usar la información de sitio y de región, y los troncos a la puerta de enlace RTC y al PBX tienen el desvío de medios habilitado.

**Ejemplo de sitios conectados mediante un vínculo WAN con un servidor de mediación en el Sitio 1 y un sistema PBX en el Sitio 2**

![Topología de voz servidor de mediación PBX para WAN](images/Gg398537.df6c8a5b-8431-4187-907d-ff5ca26eeeec(OCS.15).jpg "Topología de voz servidor de mediación PBX para WAN")

Para obtener información detallada sobre la planeación de topologías PBX, consulte [directrices de implementación para servidor de mediación en Lync server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md) y [Opciones de implementación SIP directa en Lync Server 2013](lync-server-2013-direct-sip-deployment-options.md).

La última figura de este tema muestra una topología en la que el servidor de mediación está conectado al SBC de un proveedor de servicios de telefonía por Internet. Para obtener más información sobre las topologías de tronco SIP, consulte [SIP trunking in Lync Server 2013](lync-server-2013-sip-trunking.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

