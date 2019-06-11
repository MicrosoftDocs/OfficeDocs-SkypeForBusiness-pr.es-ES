---
title: 'Lync Server 2013: Ubicación de la puerta de enlace RTC'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: PSTN gateway's location
ms:assetid: 49693a35-fad3-49ee-a71e-c7e4537b79aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994031(v=OCS.15)
ms:contentKeyID: 51803940
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b897d9ce438844cde7617bb7c3e1dae086605f09
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823549"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-gateways-location-in-lync-server-2013"></a>Ubicación de la puerta de enlace RTC en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-03-09_

Las llamadas enrutadas a través de puertas de enlace y PBX RTC pueden requerir restricciones de enrutamiento basadas en la ubicación, en función de la ubicación de dichos sistemas. El enrutamiento basado en la ubicación se puede habilitar en la granularidad según el enlace.

El enrutamiento basado en la ubicación presenta el siguiente conjunto de reglas cuando se habilita en un tronco:

  - Cuando el enrutamiento basado en la ubicación está habilitado para cada troncal, las reglas definidas en ese tronco se aplicarán únicamente a las llamadas dirigidas a través de ese tronco.

  - Para evitar que los peajes de RTC omitan donde las llamadas se originan desde un sitio de red diferente que el sitio de red en el que se encuentra la puerta de enlace RTC, el enrutamiento basado en la ubicación introduce la Asociación de un sitio de red a un tronco determinado. Esto define el sitio de red que permite que las llamadas se redirijan hacia determinado tronco.

Los troncos se pueden habilitar para el enrutamiento basado en la ubicación de dos maneras:

  - El tronco se define para una puerta de enlace RTC que realiza llamadas a la RTC. Las llamadas entrantes redirigidas por un tronco de este tipo se redirigen solo a los extremos ubicados dentro del mismo sitio de red que el tronco.

  - El tronco se define para un servidor de mediación del mismo nivel que no de salida las llamadas a los usuarios de RTC y servicios con teléfonos heredados en ubicaciones estáticas (es decir, teléfonos PBX). Para esta configuración en particular, todas las llamadas entrantes dirigidas por un tronco de este tipo se considerarán originadas desde el mismo sitio de red que el tronco. Las llamadas de usuarios de PBX tendrán la misma aplicación de enrutamiento basada en la ubicación que los usuarios de Lync que se encuentren en el mismo sitio de red que el tronco. Si dos sistemas PBX que se encuentran en sitios de red independientes se conectan a través de Lync Server, el enrutamiento basado en la ubicación permitirá el enrutamiento desde un extremo de PBX de un sitio de red a otro extremo de PBX en el otro sitio de red. Este escenario no quedará bloqueado por el enrutamiento basado en la ubicación. Además de este escenario y de forma similar a como usuario de Lync en la misma ubicación, los puntos de conexión conectados a un servidor de mediación del mismo nivel con esta configuración podrán realizar o recibir llamadas a y desde otros servidores de mediación del mismo nivel que no enrutan llamadas a la RTC (i. e. un extremo conectado a un PBX diferente, independientemente del sitio de red al que esté asociado el elemento del mismo nivel del servidor de mediación. Todas las llamadas entrantes, las llamadas salientes, las transferencias de llamadas y los reenvíos que impliquen puntos de conexión RTC estarán sujetos a enrutamiento basado en la ubicación para usar solo puertas de enlace RTC definidas como locales para este servidor del mismo nivel de media.

<div>

## <a name="see-also"></a>Vea también


[Instrucciones para el enrutamiento basado en ubicación en Lync Server 2013](lync-server-2013-guidance-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

