---
title: 'Lync Server 2013: Iniciar el proceso de planeación'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Beginning the planning process
ms:assetid: df3722b3-f859-49e1-b3ff-ee6863483731
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398986(v=OCS.15)
ms:contentKeyID: 48185618
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 582769109a3792ddc2efdbef5d4a557b781c39b8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842743"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="beginning-the-planning-process-for-lync-server-2013"></a>Iniciar el proceso de planeación para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-24_

Aunque la planeación de una implementación de comunicaciones unificadas locales puede intimidar, Lync Server ofrece dos valiosas herramientas para ayudarle:

  - **La herramienta de planeación** es un asistente que presenta una serie de preguntas sobre su organización, las características de Lync Server que desea habilitar y sus necesidades de planeación de capacidad. A continuación, crea una topología de implementación recomendada en función de sus respuestas y genera un diagrama de Microsoft Visio de esta implementación.

  - El **generador de topología** es un componente de instalación de Lync Server. El generador de topología se usa para crear, ajustar y publicar la topología planeada. También valida su topología antes de empezar con las instalaciones del servidor. Al instalar Lync Server en servidores individuales, los servidores leen la topología publicada como parte del proceso de instalación y el programa de instalación implementa el servidor tal como se indica en la topología.

<div>

## <a name="lync-server-planning-tool"></a>Herramienta de planeación de Lync Server

La herramienta de planeación toma sus respuestas a las preguntas de la herramienta y genera una topología basada en las directrices y procedimientos recomendados de Lync Server. También proporciona varias vistas de una implementación en función de las respuestas. Muestra una vista global de todos los sitios (es decir, tanto los sitios centrales como las sucursales) y las vistas detalladas que muestran los servidores y otros componentes de cada sitio.

La ejecución de la herramienta de planeación no le compromete a ninguna implementación específica ni inicia ningún proceso. De hecho, ejecutar la herramienta de planeación incluso antes de tener un plan para empresas puede ser una forma muy instructiva de comprender los tipos de preguntas que debe considerar en su proceso de planeación.

Puede ejecutar la herramienta de planeación varias veces, responder a las preguntas de manera diferente y comparar los resultados. Si tiene un diseño que está más satisfecho pero que necesita realizar cambios, puede volver a la herramienta de planificación, cargar el diseño y realizar los cambios. La herramienta de planificación tarda aproximadamente 15 minutos en completarse.

Una vez que esté satisfecho, puede usar la herramienta de planeación para crear un diagrama de la implementación planeada. Puede usar este diagrama mientras crea la implementación en el generador de topología.

<div>


> [!NOTE]  
> La herramienta de planeación que se incluye en esta versión de Lync Server 2013 es una versión preliminar. Tenga en cuenta que las cifras de la planificación de capacidad de la Herramienta de planeación son preliminares y no son compatibles con la versión final.



</div>

</div>

<div>

## <a name="lync-server-topology-builder"></a>Generador de topología de Lync Server

Una vez que haya decidido su plan de implementación, use el generador de topología para empezar a implementarlo. Cuando termine, use el generador de topología para validar la topología y, a continuación, si se supera, puede publicar la topología. Al publicar la topología, Lync Server coloca la topología en el almacén de administración central, que se crea en este momento si aún no existe. Al instalar Lync Server en cada servidor de la implementación, el servidor lee la topología del almacén central de administración y se instala para adaptarse a su rol en la implementación.

Como alternativa, si está familiarizado con Lync Server y necesita menos instrucciones preceptivas, puede omitir la herramienta de planeación y usar los asistentes en el generador de topología para el diseño inicial de la implementación y también para los pasos de validación y publicación.

El uso del generador de topología para planear y publicar una topología es un paso obligatorio. No se puede omitir el generador de topología e instalar Lync Server individualmente en los servidores de la implementación. Cada servidor debe leer la topología desde una topología validada Publicada en el almacén de administración central.

</div>

<div>

## <a name="high-level-planning-process"></a>Proceso de planificación de alto nivel

Recomendamos el siguiente proceso general para usar la documentación y la herramienta de planeación para planear la implementación de Lync Server.

1.  Si está familiarizado con las versiones anteriores de Lync Server, lea [nuevas características de Lync server 2013](lync-server-2013-new-features.md) para familiarizarse con las nuevas características y requisitos de lync Server 2013.

2.  Lea el resto de temas de esta sección de la documentación: [aspectos básicos de topología que debe conocer antes de planear Lync server 2013](lync-server-2013-topology-basics-you-must-know-before-planning.md), [topologías de referencia en Lync Server 2013](lync-server-2013-reference-topologies.md), [decisiones iniciales de planeación para Lync Server 2013](lync-server-2013-initial-planning-decisions.md)y [ Clientes para Lync Server 2013](lync-server-2013-clients.md). Observe las decisiones de planeación representadas en las [topologías de referencia en Lync Server 2013](lync-server-2013-reference-topologies.md).

3.  Ahora que está más familiarizado con las características de Lync Server y los tipos de preguntas que deben responderse, ejecute la herramienta de planeación y vea la topología resultante y sus detalles. Asegúrese de que la topología cumpla con los requisitos únicos de su organización.

4.  Si hay cargas de trabajo o características específicas en las que está interesado o necesita conocer, lea las secciones correspondientes de la [planificación de Lync Server 2013](lync-server-2013-planning.md).

5.  Vuelva a ejecutar la herramienta de planeación. Puede comenzar con la implementación que creó en el paso 3 y modificar los resultados o comenzar de nuevo desde el principio.
    
    Si es necesario, ejecute la herramienta de planeación una tercera vez y repita hasta que esté satisfecho con la salida.

6.  Cuando haya finalizado el plan de topología, use la herramienta de planeación para crear e imprimir un diagrama de Visio de su topología. Puede usar esta copia impresa mientras trabaja con Topology Builder para introducir su topología.

7.  Antes de comenzar la implementación, lea la determinación de los [requisitos del sistema para Lync server 2013](lync-server-2013-determining-your-system-requirements.md) y la determinación de los [requisitos de infraestructura de Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) para familiarizarse con los requisitos previos y la infraestructura necesaria para Lync Server. Además, asegúrese de que ha leído todas las secciones de [planeación de Lync Server 2013](lync-server-2013-planning.md) que se aplican a las cargas de trabajo y las características que planea implementar.

</div>

<div>

## <a name="migrating-from-previous-versions"></a>Migrar desde versiones anteriores

Si va a migrar a Lync Server desde una versión anterior, consulte la documentación de la [migración](migration.md) para obtener instrucciones específicas para la migración y la implementación.

</div>

</div>

<span> </span>

</div>

</div>

</div>

