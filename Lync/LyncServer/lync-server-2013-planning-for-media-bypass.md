---
title: 'Lync Server 2013: Planeación de la omisión de medios'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for media bypass
ms:assetid: 8ac732b6-8538-4d7b-b1a9-2035e419dac2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398703(v=OCS.15)
ms:contentKeyID: 48184768
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b5d9687069e82cde803f7a01873db482ea2afa2f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521997"
---
# <a name="planning-for-media-bypass-in-lync-server-2013"></a>Planeación de la omisión de medios en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-21_

El desvío de medios consiste en quitar el servidor de mediación de la ruta de acceso a medios siempre que sea posible, en las llamadas cuya señalización atraviese el servidor de mediación.

El desvío de medios puede mejorar la calidad de la voz al reducir la latencia, la traducción innecesaria, la posibilidad de pérdida de paquetes y el número de puntos de errores potenciales. Se puede mejorar la escalabilidad, ya que, al eliminar el procesamiento de medios de las llamadas desviadas, se reduce la carga del servidor de mediación. Esta reducción de carga complementa la capacidad del servidor de mediación para controlar varias puertas de enlace.

Cuando un sitio de sucursal sin un servidor de mediación está conectado a un sitio central por uno o más vínculos WAN con ancho de banda restringido, la omisión de medios reduce el requisito de ancho de banda permitiendo que los medios de un cliente de un sitio de sucursal fluyan directamente a su puerta de enlace local sin tener que fluir primero a través del vínculo WAN a un servidor de mediación en el

Al aliviar el servidor de mediación del procesamiento de medios, la omisión de medios también puede reducir el número de servidores de mediación que requiere una infraestructura de telefonía IP empresarial.

La siguiente ilustración muestra las rutas de señalización y los medios básicos en las topologías con desvío de medios y sin él.

**Rutas de señalización y medios con desvío de medios y sin él**

![Aplicación de omisión de conexión de medios de voz CAC](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Aplicación de omisión de conexión de medios de voz CAC")

Por regla general, se recomienda habilitar el desvío de medios siempre que sea posible.

<div>

## <a name="in-this-section"></a>En esta sección

  - [Información general sobre la omisión de medios en Lync Server 2013](lync-server-2013-overview-of-media-bypass.md)

  - [Modos de omisión de medios en Lync Server 2013](lync-server-2013-media-bypass-modes.md)

  - [Omisión de medios y control de admisión de llamadas en Lync Server 2013](lync-server-2013-media-bypass-and-call-admission-control.md)

  - [Requisitos técnicos para la omisión de medios en Lync Server 2013](lync-server-2013-technical-requirements-for-media-bypass.md)

</div>

<div>

## <a name="related-sections"></a>Secciones relacionadas

[Implementación de características avanzadas de telefonía IP empresarial en Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

</div>

<div>

## <a name="see-also"></a>Consulte también


[Configurar un tronco con la omisión de medios en Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  


[Opciones de omisión de medios globales en Lync Server 2013](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

