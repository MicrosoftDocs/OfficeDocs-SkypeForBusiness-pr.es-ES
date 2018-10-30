---
title: 'Lync Server 2013: Iniciar el proceso de planeación'
TOCTitle: Iniciar el proceso de planeación
ms:assetid: df3722b3-f859-49e1-b3ff-ee6863483731
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398986(v=OCS.15)
ms:contentKeyID: 48276931
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Iniciar el proceso de planeación para Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

A pesar de que la planeación de una implementación local de comunicaciones unificadas puede resultar intimidante, Lync Server proporciona dos valiosas herramientas para ayudarle:

  - **Herramienta de planeación** es un asistente que formula una serie de preguntas sobre la organización, las características de Lync Server que desea habilitar y sus necesidades de planeación de la capacidad. Después crea una topología de implementación recomendada basada en las respuestas y genera un diagrama de Microsoft Visio de esta implementación.

  - **Generador de topologías** es un componente de instalación de Lync Server. Generador de topologías se usa para crear, ajustar y publicar la topología planeada. Asimismo, valida la topología antes de comenzar a realizar las instalaciones del servidor. Al instalar Lync Server en servidores individuales, estos leen la topología publicada como parte del proceso de instalación, y el programa de instalación implementa el servidor tal y como se haya indicado en la topología.

## Herramienta de planeación de Lync Server

La Herramienta de planeación incorpora en la herramienta sus respuestas a las preguntas y genera una topología basada en las instrucciones generales y los procedimientos recomendados de Lync Server. Asimismo, proporciona varias vistas de una implementación basadas en sus respuestas. Muestra una vista global de todos los sitios (es decir, una vista que incluye tanto los sitios centrales como los sitios de sucursal) y vistas detalladas que muestran los servidores y otros componentes de cada sitio.

Ejecutar la Herramienta de planeación no le obliga a realizar ninguna implementación específica ni iniciar ningún proceso. De hecho, ejecutar la Herramienta de planeación incluso antes de que tenga un plan firme en mente puede ser una forma muy instructiva de comprender los tipos de preguntas en los que debe pensar durante el proceso de planeación.

Puede ejecutar la Herramienta de planeación varias veces, respondiendo a las preguntas de forma distinta cada vez para luego comparar los resultados. Si ya tiene un diseño con el que está bastante satisfecho, pero necesita realizar cambios, puede volver a la Herramienta de planeación, cargar el diseño y realizar los cambios. Completar la Herramienta de planeación lleva aproximadamente 15 minutos.

Una vez satisfecho, use la Herramienta de planeación para crear un diagrama de la implementación planeada. Use este diagrama durante la creación de la implementación en Generador de topologías.


> [!NOTE]
> La herramienta de planeación incluida con esta versión de Lync Server 2013 es una versión preliminar. Observe que los números de planeamiento de capacidad de la herramienta de planeamiento son preliminares y no se admiten en la versión final.



## Generador de topologías de Lync Server

Una vez decidido el plan de implementación, se usa Generador de topologías para iniciar la implementación. Una vez haya finalizado, se usa Generador de topologías para realizar la validación de la topología y, si la supera, podrá publicar la topología. Al publicar la topología, Lync Server coloca la topología en el Almacén de administración central que, si no existe, se crea en este momento. Al instalar Lync Server en cada uno de los servidores de la implementación, el servidor lee la topología del Almacén de administración central y se instala para coincidir con el rol correspondiente de su implementación.

Si está muy familiarizado con Lync Server y necesita menos pautas, omita la Herramienta de planeación y use los asistentes de Generador de topologías para realizar el diseño inicial de su implementación, así como para los pasos de validación y publicación.

Usar Generador de topologías para planear y publicar una topología es un paso obligatorio. No omita Generador de topologías e instale Lync Server de forma individual en los servidores de su implementación. Cada servidor debe leer la topología de una topología validada y publicada en el Almacén de administración central.

## Proceso de planeación de alto nivel

Recomendamos seguir el proceso general siguiente para usar tanto la documentación como la Herramienta de planeación para planear su implementación de Lync Server.

1.  Si está familiarizado con las versiones anteriores de Lync Server, lea [Nuevas funciones en Lync Server 2013](lync-server-2013-new-features.md) para familiarizarse con las nuevas características y los nuevos requisitos de Lync Server 2013.

2.  Lea los demás temas de esta sección de la documentación: [Aspectos básicos de la topología a tener en cuenta antes de la planificación para Lync Server 2013](lync-server-2013-topology-basics-you-must-know-before-planning.md), [Topologías de referencia en Lync Server 2013](lync-server-2013-reference-topologies.md), [Decisiones de planeación iniciales para Lync Server 2013](lync-server-2013-initial-planning-decisions.md) y [Clientes para Lync Server 2013](lync-server-2013-clients.md). Anote las decisiones de planeación representadas en [Topologías de referencia en Lync Server 2013](lync-server-2013-reference-topologies.md).

3.  Ahora que está más familiarizado con las características de Lync Server y los tipos de preguntas que debe responder, vuelva a ejecutar la Herramienta de planeación y vea la topología resultante y sus detalles. Compruebe que la topología se adapta a los requisitos únicos de la organización

4.  Si existen cargas de trabajo o características concretas en las que está interesado o sobre las que desea obtener más información, lea las secciones correspondientes de [Planeación de Lync Server 2013](lync-server-2013-planning.md).

5.  Vuelva a ejecutar la Herramienta de planeación. Empiece con la implementación creada en el paso 3 y modifique los resultados, o bien empiece desde el principio.
    
    Si es preciso, ejecute la Herramienta de planeación una tercera vez hasta que esté satisfecho con el resultado.

6.  Una vez finalizado el plan de topología, use Herramienta de planeación para crear e imprimir un diagrama de Visio de la topología. Use esta copia impresa mientras trabaje con Generador de topologías para introducir la topología.

7.  Antes de iniciar la implementación, lea las secciones [Determinar los requisitos del sistema para Lync Server 2013](lync-server-2013-determining-your-system-requirements.md) y [Determinar los requisitos de infraestructura para Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) para familiarizarse con los requisitos previos y la infraestructura necesarios para Lync Server. Asimismo, no olvide leer todas las secciones de [Planeación de Lync Server 2013](lync-server-2013-planning.md) que hablen sobre las cargas de trabajo y las características que tiene previsto implementar.

## Migración desde versiones anteriores

Si va a realizar una migración a Lync Server desde una versión anterior, consulte la documentación de [Migración](migration.md) para obtener instrucciones específicas para su migración e implementación.

