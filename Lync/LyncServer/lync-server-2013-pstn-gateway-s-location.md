---
title: 'Lync Server 2013: ubicación de la puerta de enlace RTC'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN gateway's location
ms:assetid: 49693a35-fad3-49ee-a71e-c7e4537b79aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994031(v=OCS.15)
ms:contentKeyID: 51803940
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef9c58115349e8fedaf25d6f8bc4e1991b65a963
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152314"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="pstn-gateways-location-in-lync-server-2013"></a>Ubicación de la puerta de enlace RTC en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-03-09_

Las llamadas enrutadas a través de puertas de enlace RTC y PBX pueden requerir restricciones de enrutamiento basadas en la ubicación en función de la ubicación de dichos sistemas. El enrutamiento basado en ubicación se puede habilitar en la granularidad en función de cada tronco.

El enrutamiento basado en ubicación presenta el siguiente conjunto de reglas cuando se habilita en un tronco:

  - Cuando se habilita el enrutamiento basado en ubicación por tronco, las reglas definidas en ese tronco se aplicarán solo a las llamadas enrutadas a través de ese tronco.

  - Para evitar que se omitan los peajes de RTC en los que las llamadas se originan desde un sitio de red diferente que el sitio de red en el que se encuentra la puerta de enlace RTC, el enrutamiento basado en ubicación presenta la Asociación de un sitio de red a un tronco determinado. Define el sitio de red que permite que las llamadas se enruten a un tronco determinado.

Los troncos pueden estar habilitados para el enrutamiento basado en la ubicación de dos maneras:

  - El tronco se define para una puerta de enlace RTC que salida las llamadas a la RTC. Las llamadas entrantes redirigidas por un tronco de este tipo se redirigirán solo a los extremos ubicados dentro del mismo sitio de red que el tronco.

  - El tronco se define para un servidor de mediación del mismo nivel que no salida las llamadas a los usuarios de RTC y servicios con teléfonos heredados en ubicaciones estáticas (es decir, los teléfonos PBX). Para esta configuración específica, se considerará que todas las llamadas entrantes redirigidas por un tronco de este tipo se originan desde el mismo sitio de red que el tronco. Las llamadas de los usuarios de PBX tendrán la misma aplicación de enrutamiento basada en ubicación que los usuarios de Lync que se encuentran en el mismo sitio de red que el tronco. Si dos sistemas PBX ubicados en sitios de red independientes están conectados a través de Lync Server, el enrutamiento basado en ubicación permitirá el enrutamiento desde un extremo de PBX en un sitio de red a otro extremo de PBX en el otro sitio de red. Este escenario no se bloqueará por el enrutamiento basado en ubicación. Además de este escenario y de una manera similar a un usuario de Lync en la misma ubicación, los extremos conectados a un puesto del servidor de mediación con esta configuración podrán realizar o recibir llamadas a y desde otros servidores de mediación del mismo nivel que no enruten llamadas a la RTC (i. e. un extremo conectado a un PBX diferente, independientemente del sitio de red al que esté asociado el elemento del mismo nivel del servidor de mediación. Todas las llamadas entrantes, las llamadas salientes, las transferencias de llamadas y las llamadas reenvíos en las que participen los extremos RTC estarán sujetas a un enrutamiento basado en ubicación para usar solo puertas de enlace RTC definidas como locales para este servidor de mediación del mismo nivel.

<div>

## <a name="see-also"></a>Vea también


[Guía para el enrutamiento basado en ubicación en Lync Server 2013](lync-server-2013-guidance-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

