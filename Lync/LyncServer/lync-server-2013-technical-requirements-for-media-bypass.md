---
title: 'Lync Server 2013: requisitos técnicos para la omisión de medios'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for media bypass
ms:assetid: 6162a204-0e7c-460a-8eb2-e592c6590a8a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398435(v=OCS.15)
ms:contentKeyID: 48184321
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ad685e59616f7f2a90cc8a9d3feb5f4ea669587
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141816"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-media-bypass-in-lync-server-2013"></a>Requisitos técnicos para la omisión de medios en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-21_

Por cada llamada a la RTC, el servidor de mediación determina si los medios del punto de conexión de Lync de origen se pueden enviar directamente a un servidor de mediación del mismo nivel sin atravesar el servidor de mediación. El componente del mismo nivel puede ser una puerta de enlace RTC, un sistema IP-PBX o un controlador SBC en un proveedor de servicios de telefonía por Internet (ITSP) asociado con el tronco entre el servidor de mediación hacia el que se ha enrutado la llamada.

Puede emplearse el desvío de medios cuando se reúnen los siguientes requisitos:

  - Un elemento del mismo nivel del servidor de mediación debe admitir las capacidades necesarias para la omisión de medios, la más importante es la capacidad para controlar varias respuestas bifurcadas (conocidas como "cuadros de diálogo iniciales"). Póngase en contacto con el fabricante de su puerta de enlace, sistema PBX o ITSP para obtener el valor del número máximo de diálogos iniciales que la puerta de enlace, el sistema PBX o el SBC puede aceptar.

  - El servidor de mediación del mismo nivel debe aceptar el tráfico de medios directamente desde los puntos de conexión de Lync. Muchas ITSPs permiten que SBC reciba el tráfico solo del servidor de mediación. Póngase en contacto con el ITSP para determinar si el SBC acepta el tráfico de medios directamente desde los puntos de conexión de Lync.

  - Los clientes de Lync y un servidor de mediación deben estar bien conectados, lo que significa que ya se encuentran en la misma región de red o en sitios de red que se conectan a la región a través de vínculos WAN que no tienen restricciones de ancho de banda.

<div>

## <a name="see-also"></a>Vea también


[Modos de omisión de medios en Lync Server 2013](lync-server-2013-media-bypass-modes.md)  
[Omisión de medios y control de admisión de llamadas en Lync Server 2013](lync-server-2013-media-bypass-and-call-admission-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

