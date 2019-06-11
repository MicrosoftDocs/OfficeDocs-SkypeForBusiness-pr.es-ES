---
title: Control de admisión de llamadas con un PBX o una puerta de enlace RTC de terceros
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call admission control with a third-party PSTN gateway or PBX
ms:assetid: 95dc4ceb-bcad-48ee-86ec-af911727f853
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398762(v=OCS.15)
ms:contentKeyID: 48184850
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c1996b56a50dbe616c8dc6e9b9b1c779c564b185
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842711"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-in-lync-server-2013-with-a-third-party-pstn-gateway-or-pbx"></a>Control de admisión de llamadas con un PBX o una puerta de enlace RTC de terceros en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-20_

En este tema se describen ejemplos de cómo el servicio de control de admisión de llamadas (CAC) puede implementarse en el vínculo entre la interfaz de la puerta de enlace del servidor de mediación y una puerta de enlace de la red telefónica conmutada (RTC) o de la central de conmutación (PBX) de terceros.

<div>

## <a name="case-1-cac-between-the-mediation-server-and-a-pstn-gateway"></a>Caso 1: servicio de control de admisión de llamadas entre el servidor de mediación y una puerta de enlace RTC

El CAC puede implementarse en el vínculo WAN de la interfaz de la puerta de enlace del servidor de mediación con una puerta de enlace RTC o PBX de terceros.

**Caso 1: servicio de control de admisión de llamadas entre el servidor de mediación y una puerta de enlace RTC**

![Caso 1: CAC entre la puerta de enlace RTC del servidor] de mediación (images/Gg398762.4bebf9ee-2732-4ea6-bbe5-0269b2903d8c(OCS.15).jpg "Caso 1: CAC entre la puerta de enlace RTC del servidor") de mediación

En este ejemplo, se aplica CAC entre el servidor de mediación y una puerta de enlace RTC. Si un usuario del cliente de Lync en el sitio de red 1 coloca una llamada RTC a través de la puerta de enlace RTC en el sitio de red 2, los medios fluyen por el vínculo WAN. Por tanto, se llevan a cabo dos comprobaciones de CAC para cada sesión de RTC:

  - Entre la aplicación cliente de Lync y el servidor de mediación

  - Entre el servidor de mediación y la puerta de enlace RTC

Esto funciona tanto para las llamadas RTC entrantes a un cliente en el sitio de red 1 como para las llamadas RTC salientes desde una aplicación cliente en el sitio de red 1.

<div>


> [!NOTE]
> Asegúrate de que la subred IP a la que pertenece la puerta de enlace RTC esté configurada y asociada con el sitio de red 2.<BR>Asegúrese de que la subred IP a la que pertenecen ambas interfaces del servidor de mediación está configurada y asociada con el sitio de red 1.<BR>Para obtener más información, consulte <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">asociar una subred con un sitio de red en Lync Server 2013</A>.



</div>

</div>

<div>

## <a name="case-2-cac-between-the-mediation-server-and-a-third-party-pbx-with-media-termination-point"></a>Caso 2: CAC entre el servidor de mediación y un PBX de terceros con punto de terminación de los medios

Esta configuración es similar a la del caso 1. En ambos casos, el servidor de mediación sabe qué dispositivo finaliza los medios en el extremo opuesto al vínculo WAN y la dirección IP de la puerta de enlace o PBX con punto de terminación de medios (MTP) está configurada en el servidor de mediación como el próximo salto.

**Caso 2: servicio de control de admisión de llamadas entre el servidor de mediación y una PBX de terceros con MTP**

![Caso 2: CAC entre el servidor de mediación PBX con MTP] (images/Gg398762.1c0b5263-c053-4cca-842f-85dd670760c8(OCS.15).jpg "Caso 2: CAC entre el servidor de mediación PBX con MTP")

En este ejemplo, se aplica CAC entre el servidor de mediación y PBX/MTP. Si un usuario del cliente de Lync en el sitio de red 1 coloca una llamada RTC a través de la PBX/MTP que se encuentra en el sitio de red 2, los medios se transmiten a través del vínculo WAN. Por tanto, se llevan a cabo dos comprobaciones de CAC para cada sesión de RTC:

  - Entre la aplicación cliente de Lync y el servidor de mediación

  - Entre el servidor de mediación y la PBX/MTP

Esto funciona tanto para las llamadas RTC entrantes a un cliente en el sitio de red 1 como para las llamadas RTC salientes desde un cliente en el sitio de red 1.

<div>


> [!NOTE]
> Asegúrate de que la subred IP a la que pertenece el MTP esté configurada y asociada con el sitio de red 2.<BR>Asegúrese de que la subred IP a la que pertenecen ambas interfaces del servidor de mediación está configurada y asociada con el sitio de red 1.<BR>Para obtener más información, consulte <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">asociar una subred con un sitio de red en Lync Server 2013</A>.



</div>

</div>

<div>

## <a name="case-3-cac-between-the-mediation-server-and-a-third-party-pbx-without-a-media-termination-point"></a>Caso 3: CAC entre el servidor de mediación y un sistema PBX de terceros sin un punto de terminación de medios

El caso 3 es ligeramente diferente a los dos primeros casos. Si no hay ningún MTP en la PBX de terceros, para una solicitud de sesión saliente al PBX de terceros, el servidor de mediación no sabrá dónde se cerrarán los medios en el límite de PBX. En este caso, los medios fluyen directamente entre el servidor de mediación y el dispositivo de extremo de terceros.

**Caso 3: servicio de control de admisión de llamadas entre el servidor de mediación y una PBX de terceros sin MTP**

![Caso 3: CAC entre el servidor de mediación PBX no MTP] (images/Gg398762.f4bcf800-3a68-4037-bb3f-adb2fdf50d32(OCS.15).jpg "Caso 3: CAC entre el servidor de mediación PBX no MTP")

En este ejemplo, si un usuario del cliente de Lync en el sitio de red 1 realiza una llamada a un usuario a través de la PBX, el servidor de mediación puede realizar comprobaciones CAC solo en el segmento proxy (entre la aplicación cliente de Lync y el servidor de mediación). Dado que el servidor de mediación no tiene información sobre el dispositivo de extremo durante la solicitud de la sesión, las comprobaciones de CAC no se pueden realizar en el vínculo WAN (entre el servidor de mediación y el extremo de terceros) antes del establecimiento. Sin embargo, una vez establecida la sesión, el servidor de mediación facilita la contabilidad del ancho de banda que se usa en el tronco.

Para las llamadas que se originan desde el extremo de terceros, la información sobre el dispositivo de punto final está disponible en el momento de la solicitud de sesión y la comprobación CAC se puede realizar en ambos lados del servidor de mediación.

<div>


> [!NOTE]
> Asegúrate de que la subred IP a la que pertenecen los dispositivos de extremo esté configurada y asociada con el sitio de red 2.<BR>Asegúrese de que la subred IP a la que pertenecen ambas interfaces del servidor de mediación está configurada y asociada con el sitio de red 1.<BR>Para obtener más información, consulte <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">asociar una subred con un sitio de red en Lync Server 2013</A>.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

