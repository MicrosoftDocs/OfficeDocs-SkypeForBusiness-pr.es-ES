---
title: 'Lync Server 2013: Planificar la omisión de medios'
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
ms.openlocfilehash: 97b28559ea58439d370042d54ab7ef58943bc594
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41751160"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-media-bypass-in-lync-server-2013"></a>Planificar la omisión de medios en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-21_

La omisión de elementos multimedia hace referencia a quitar el servidor de mediación de la ruta multimedia siempre que sea posible para las llamadas cuya señalización atraviese el servidor de mediación.

La omisión de medios puede mejorar la calidad de la voz al reducir la latencia, la conversión innecesaria, la posibilidad de la pérdida de paquetes y la cantidad de puntos de errores potenciales. La escalabilidad puede mejorarse, ya que la eliminación del procesamiento de medios para llamadas omitidas reduce la carga en el servidor de mediación. Esta reducción de carga complementa la capacidad del servidor de mediación para controlar varias puertas de enlace.

Cuando un sitio de sucursal sin un servidor de mediación se conecta a un sitio central mediante uno o varios vínculos WAN con ancho de banda restringido, la omisión de medios disminuye el requisito de ancho de banda permitiendo que los medios de un cliente de un sitio de sucursal fluyan directamente a su puerta de enlace local sin en primer lugar, debe transmitirse a través del vínculo WAN a un servidor de mediación del sitio central y viceversa.

Al aliviar el servidor de mediación del procesamiento multimedia, la omisión de medios también puede reducir el número de servidores de mediación que requiere una infraestructura de telefonía IP empresarial.

La siguiente figura muestra las rutas de señalización y los medios básicos en las topologías con omisión de medios y sin ella.

**Rutas de señalización y medios con omisión de medios y sin ella**

![Aplicación de la conexión de desvío de medios del control de admisión de llamadas de voz](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Aplicación de la conexión de desvío de medios del control de admisión de llamadas de voz")

Como regla general, habilita la omisión de medios siempre que sea posible.

<div>

## <a name="in-this-section"></a>En esta sección

  - [Información general sobre la omisión de elementos multimedia en Lync Server 2013](lync-server-2013-overview-of-media-bypass.md)

  - [Modos de omisión de medios en Lync Server 2013](lync-server-2013-media-bypass-modes.md)

  - [Omisión de medios y control de admisión de llamadas en Lync Server 2013](lync-server-2013-media-bypass-and-call-admission-control.md)

  - [Requisitos técnicos para la omisión de medios en Lync Server 2013](lync-server-2013-technical-requirements-for-media-bypass.md)

</div>

<div>

## <a name="related-sections"></a>Secciones relacionadas

[Implementación de características avanzadas de telefonía empresarial en Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

</div>

<div>

## <a name="see-also"></a>Vea también


[Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  


[Opciones de omisión de multimedia global en Lync Server 2013](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

