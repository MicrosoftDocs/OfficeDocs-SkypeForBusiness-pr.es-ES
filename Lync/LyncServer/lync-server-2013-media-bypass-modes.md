---
title: 'Lync Server 2013: modos de omisión de medios'
description: 'Lync Server 2013: modos de omisión de medios.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media bypass modes
ms:assetid: 38c06c81-7e45-4423-9e00-7fbfa4befe46
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425862(v=OCS.15)
ms:contentKeyID: 48183898
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a7f1a71930df7ef92a29087f42bdb9382b3904c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577906"
---
# <a name="media-bypass-modes-in-lync-server-2013"></a>Modos de omisión de medios en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-05_

Debe configurar el desvío de medios de forma global y para cada tronco RTC individual. Al habilitar el desvío de medios globalmente, tiene dos opciones: **Desviar siempre** y **Usar información de sitio y región**.

Como el propio nombre sugiere, **Desviar siempre** significa que se intentará realizar el desvío de todas las llamadas de RTC. **Desviar siempre** se usa en implementaciones en las que no hay necesidad de habilitar el control de admisión de llamadas ni de especificar información detallada de configuración con respecto a cuándo intentar el desvío de medios. Además, **Desviar siempre** se usa cuando existe plena conectividad entre clientes y puertas de enlace de RTC. En esta configuración, todas las subredes se asignan únicamente a un solo identificador de desvío, que el sistema calcula.

Con **Usar información de sitio y región**, se usa el identificador de desvío asociado a la configuración del sitio y la región para tomar la decisión de desvío. Esta configuración proporciona la flexibilidad de configurar el desvío para las topologías más comunes, ya que proporciona un control más preciso cuando se produce el desvío, además de admitir interacciones con el control de admisión de llamadas (CAC). El sistema intenta facilitarle la tarea asignando automáticamente identificadores de desvío de la manera siguiente.

  - El sistema asigna automáticamente un único identificador de desvío a cada región.

  - Cualquier sitio conectado a una región por un vínculo WAN sin restricciones de ancho de banda hereda el mismo identificador de desvío de la región.

  - A un sitio asociado a la región por un vínculo WAN con un ancho de banda restringido se le asigna un identificador de desvío distinto al de la región.

  - Las subredes asociadas a cada sitio heredan el identificador de desvío del sitio.

<div>

## <a name="see-also"></a>Consulte también


[Información general sobre la omisión de medios en Lync Server 2013](lync-server-2013-overview-of-media-bypass.md)  
[Omisión de medios y control de admisión de llamadas en Lync Server 2013](lync-server-2013-media-bypass-and-call-admission-control.md)  
[Requisitos técnicos para la omisión de medios en Lync Server 2013](lync-server-2013-technical-requirements-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

