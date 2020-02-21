---
title: 'Lync Server 2013: Inicio del proceso de planeación'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Beginning the planning process
ms:assetid: df3722b3-f859-49e1-b3ff-ee6863483731
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398986(v=OCS.15)
ms:contentKeyID: 48185618
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 04bc27b965da5d4761e3283ea3106a8a3b90ebf8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181353"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="beginning-the-planning-process-for-lync-server-2013"></a>Inicio del proceso de planeación de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-24_

Aunque parece intimidar a la planeación de una implementación local de comunicaciones unificadas, Lync Server ofrece dos herramientas valiosas que le ayudarán a:

  - **La herramienta de planeación** es un asistente que presenta una serie de preguntas sobre la organización, las características de Lync Server que desea habilitar y las necesidades de planeación de la capacidad. A continuación, se crea una topología de implementación recomendada en función de las respuestas y se genera un diagrama de Microsoft Visio de esta implementación.

  - El **generador de topologías** es un componente de instalación de Lync Server. Puede usar el generador de topologías para crear, ajustar y publicar la topología planeada. Asimismo, valida la topología antes de comenzar a realizar las instalaciones del servidor. Al instalar Lync Server en servidores individuales, los servidores leen la topología publicada como parte del proceso de instalación, y el programa de instalación implementa el servidor tal como se indicó en la topología.

<div>

## <a name="lync-server-planning-tool"></a>Herramienta de planeación de Lync Server

La herramienta de planeación toma sus respuestas a las preguntas de la herramienta y genera una topología en función de las instrucciones y los procedimientos recomendados de Lync Server. También proporciona varias vistas de una implementación en función de las respuestas. Muestra una vista global de todos los sitios (es decir, tanto sitios centrales como sucursales) y vistas detalladas que muestran los servidores y otros componentes en cada sitio.

La ejecución de la herramienta de planeación no le compromete a ninguna implementación específica ni inicia ningún proceso. De hecho, ejecutar la herramienta de planeación incluso antes de tener en cuenta un plan de empresa puede ser una forma muy instructiva de comprender los tipos de preguntas que debe considerar en el proceso de planeación.

Puede ejecutar la herramienta de planeación varias veces, responder a las preguntas de manera diferente y comparar los resultados. Si tiene un diseño con el que está satisfecho principalmente pero que necesita realizar cambios en, puede volver a la herramienta de planeación, cargar el diseño y realizar los cambios. La herramienta de planeación tarda unos 15 minutos en completarse.

Cuando esté satisfecho, puede usar la herramienta de planeación para crear un diagrama de la implementación planeada. Puede usar este diagrama mientras crea la implementación en el generador de topologías.

<div>


> [!NOTE]  
> La herramienta de planeación que se incluye con esta versión de Lync Server 2013 es una versión preliminar. Tenga en cuenta que los números de planeación de la capacidad de la herramienta de planeación son preliminares y no se admiten en la versión final.



</div>

</div>

<div>

## <a name="lync-server-topology-builder"></a>Generador de topologías de Lync Server

Una vez que haya decidido el plan de implementación, use el generador de topologías para empezar a implementar. Cuando termine, use el generador de topologías para validar la topología y, si es así, puede publicar la topología. Al publicar la topología, Lync Server coloca la topología en el almacén de administración central, que se crea en este momento si aún no existe. Al instalar Lync Server en cada servidor de la implementación, el servidor lee la topología del almacén de administración central y se instala para ajustarse a su rol en la implementación.

Como alternativa, si está familiarizado con Lync Server y necesita menos instrucciones preceptivas, puede omitir la herramienta de planeación y usar los asistentes en el generador de topologías para el diseño inicial de la implementación y también para los pasos de validación y publicación.

Es un paso necesario usar el generador de topologías para planear y publicar una topología. No se puede omitir el generador de topología e instalar Lync Server individualmente en los servidores de la implementación. Cada servidor debe leer la topología desde una topología validada y publicada en el almacén de administración central.

</div>

<div>

## <a name="high-level-planning-process"></a>Proceso de planeación de alto nivel

Se recomienda el siguiente proceso general para usar la documentación y la herramienta de planeación para planear la implementación de Lync Server.

1.  Si está familiarizado con las versiones anteriores de Lync Server, lea [nuevas características en Lync server 2013](lync-server-2013-new-features.md) para familiarizarse con las nuevas características y requisitos en lync Server 2013.

2.  Lea los otros temas de esta sección de la documentación: [aspectos básicos de las topologías que debe conocer antes de planear Lync server 2013](lync-server-2013-topology-basics-you-must-know-before-planning.md), [topologías de referencia en Lync Server 2013](lync-server-2013-reference-topologies.md), [decisiones iniciales de planeación para](lync-server-2013-initial-planning-decisions.md)Lync Server 2013 y [clientes para Lync Server 2013](lync-server-2013-clients.md). Tenga en cuenta las decisiones de planeación representadas en las [topologías de referencia en Lync Server 2013](lync-server-2013-reference-topologies.md).

3.  Ahora que está más familiarizado con las características de Lync Server y los tipos de preguntas que deben responderse, ejecute la herramienta de planeación y vea la topología resultante y sus detalles. Asegúrese de que la topología cumple los requisitos únicos para su organización.

4.  Si hay cargas de trabajo o características específicas en las que está interesado o necesita aprender sobre, lea las secciones correspondientes de [Planning para Lync Server 2013](lync-server-2013-planning.md).

5.  Vuelva a ejecutar la herramienta de planeación. Puede comenzar con la implementación que ha creado en el paso 3 y modificar los resultados o comenzar de nuevo desde el principio.
    
    Si es necesario, ejecute la herramienta de planeación una tercera vez y repita hasta que quede satisfecho con el resultado.

6.  Cuando haya finalizado el plan de topología, use la herramienta de planeación para crear e imprimir un diagrama de Visio de la topología. Puede usar esta copia impresa mientras trabaja con Topology Builder para introducir su topología.

7.  Antes de comenzar con la implementación, lea la determinación de los [requisitos del sistema para Lync server 2013](lync-server-2013-determining-your-system-requirements.md) y la determinación de los [requisitos de infraestructura para Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) para familiarizarse con los requisitos previos y la infraestructura necesaria para Lync Server. Además, asegúrese de que ha leído todas las secciones de [planeación de Lync Server 2013](lync-server-2013-planning.md) que se aplican a las cargas de trabajo y las características que tiene previsto implementar.

</div>

<div>

## <a name="migrating-from-previous-versions"></a>Migración desde versiones anteriores

Si va a migrar a Lync Server desde una versión anterior, consulte la documentación de la [migración](migration.md) para obtener instrucciones específicas para la migración y la implementación.

</div>

</div>

<span> </span>

</div>

</div>

</div>

