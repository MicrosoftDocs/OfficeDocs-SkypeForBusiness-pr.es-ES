---
title: 'Lync Server 2013: establecimiento de un plan de copia de seguridad y restauración'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Establishing a backup and restoration plan
ms:assetid: 9f562ef1-3804-41e2-b3e4-d45b2e8c63c9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202183(v=OCS.15)
ms:contentKeyID: 51541499
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b3516e63a7cbada4a89fad3540406e38b299fef
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835193"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="establishing-a-backup-and-restoration-plan-for-lync-server-2013"></a>Establecer un plan de copia de seguridad y restauración para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-17_

Para crear un plan de copia de seguridad y restauración, siga estos pasos:

  - Desarrollar el plan.

  - Implementar el plan.

  - Mantenimiento del plan.

<div>

## <a name="developing-a-backup-and-restoration-plan"></a>Desarrollar un plan de copia de seguridad y restauración

Después de desarrollar la estrategia de copia de seguridad y restauración de Lync Server, Úsela para documentar un plan detallado de copia de seguridad y restauración. Su plan debe transmitir claramente las prioridades y los requisitos para realizar copias de seguridad de los datos y la configuración. Puede usar la información contenida en [establecer una estrategia de copia de seguridad y restauración para Lync server 2013](lync-server-2013-establishing-a-backup-and-restoration-strategy.md) y las hojas de cálculo de [copia de seguridad y restauración de Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md) para facilitar la documentación de su estrategia. Su plan debe contener también criterios para decidir cuándo y cómo restaurar el servicio.

A medida que desarrolla su plan, debe tener en cuenta lo siguiente:

  - Cómo se recuperan los servidores en el nuevo hardware.

  - Cómo se recuperan los servicios que requieren una acción en la parte de varias áreas o departamentos empresariales.

  - Cómo puede adquirir servidores de repuesto rápidamente.

  - El tiempo que se tarda en recuperarse con su estrategia. Considere los requisitos de la organización para el objetivo de tiempo de recuperación (RTO).

Modifique los procedimientos de copia de seguridad y restauración de este tema, agregando y eliminando procedimientos según corresponda, para reflejar los servidores y componentes de su implementación. También puede agregar detalles apropiados, como la programación de la copia de seguridad, a los procedimientos apropiados para asegurarse de que la información no se ha descargado.

<div>


> [!NOTE]  
> Es recomendable crear scripts para tantos pasos como sea posible para garantizar la calidad y la reproducibilidad de los procedimientos.



</div>

En su plan, especifique quién es el responsable de revisar el plan, quién es el responsable de probar y validar los nuevos procedimientos o herramientas, y quién debe aprobar los cambios en el plan y los procedimientos relacionados.

Para asegurarse de que el plan de copia de seguridad y restauración cumple todos los objetivos y las prioridades establecidos, obtenga la aprobación de los responsables de la toma de decisiones empresariales y los responsables de las decisiones técnicas correspondientes de la organización antes de implementar el plan.

</div>

<div>

## <a name="implementing-the-backup-and-restoration-plan"></a>Implementación del plan de copia de seguridad y restauración

Para implementar un plan de copia de seguridad y restauración, debe seguir estos pasos:

  - Probar y validar el plan.

  - Comunicar el plan.

  - Validación de las operaciones de copia de seguridad y restauración.

<div>

## <a name="testing-and-validating-the-plan"></a>Probar y validar el plan

Los procedimientos descritos aquí se han probado y validado en un entorno de laboratorio. Para asegurarse de que estos u otros procedimientos funcionan en su entorno, debe probar y validar cada procedimiento que desee implementar. Complete las pruebas y la validación antes de enviar su plan para la aprobación final.

</div>

<div>

## <a name="communicating-the-plan"></a>Comunicar el plan

El plan de copia de seguridad y restauración debería describir claramente quién implementa procedimientos e instrucciones paso a paso para llevar a cabo los procedimientos. Debe asegurarse de que todos los responsables de cualquier aspecto de la copia de seguridad y restauración entienden el plan, cómo se va a implementar y cuál es su función. Esto incluye todos los requisitos de implementación para lo siguiente:

  - Copia de seguridad del servidor y del grupo.

  - Restauración de servicio.

**Copia de seguridad del servidor y del grupo**

El plan de copia de seguridad y restauración debe incluir toda la información necesaria para completar procedimientos de copia de seguridad de manera continua. La información principal que se debe transmitir a los miembros del equipo responsable incluye lo siguiente:

  - Equipo o persona (especificada como una persona o rol) responsable de realizar la copia de seguridad de cada servidor.

  - Programaciones específicas para realizar copias de seguridad de cada servidor.

  - Ubicaciones de copia de seguridad para cada tipo de datos (configuración, base de datos y recursos compartidos de archivos).

  - Procedimientos de copia de seguridad que se deben usar, incluidas las herramientas necesarias para completar cada procedimiento.

  - Información necesaria para completar las copias de seguridad, como se explica en las [hojas de cálculo de copia de seguridad y restauración de Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).

  - Métodos de validación que se van a usar para ayudar a garantizar que se realicen copias de seguridad de los datos y la configuración correctamente y que estén disponibles para la restauración, que pueden incluir auditorías periódicas y restauraciones de prueba.

**Restauración del servicio**

El plan de copia de seguridad y restauración debe incluir toda la información necesaria para restaurar el servicio, en caso de que uno o varios servidores experimenten una pérdida que hace que el servicio no esté disponible. La información principal que se debe transmitir a los miembros del equipo responsable incluye lo siguiente:

  - Equipo o persona (especificada como una persona o un rol) responsable de determinar cuándo se necesita la restauración del servicio y los procedimientos que se deben usar para restaurar el servicio, así como el equipo o la persona responsable de implementar procedimientos para cada uno de los escenario de restauración.

  - Criterios para determinar qué procedimientos de restauración son los más adecuados para una situación específica.

  - Tiempo estimado para la restauración del objetivo de servicio y tiempo de recuperación (RTO) en cada escenario de restauración.

  - Procedimientos de restauración que se deben usar, incluidas las herramientas necesarias para completar cada procedimiento.

  - Información necesaria para restaurar los datos y la configuración. Las hojas de cálculo se proporcionan en las [hojas de cálculo de copia de seguridad y restauración de Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).

</div>

<div>

## <a name="validating-backup-and-restoration-operations"></a>Validación de las operaciones de copia de seguridad y restauración

Después de completar los esfuerzos de copia de seguridad inicial en el entorno de producción y en intervalos especificados (según se cubre en el plan de copia de seguridad y restauración), debe comprobar lo siguiente:

  - Las copias de seguridad se producen según sea necesario.

  - Los datos y la configuración de la copia de seguridad son accesibles.

  - Los procedimientos de restauración se pueden realizar en las horas de objetivo de tiempo de recuperación (RTO) especificadas en el plan de copia de seguridad y restauración, y los resultados cumplen todos los requisitos empresariales.

  - Las hojas de cálculo de copia de seguridad se han completado y verificado, y se almacenan en un lugar seguro. Estas hojas de cálculo se proporcionan en las [hojas de cálculo de copia de seguridad y restauración de Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).

  - Los procedimientos de restauración han sido probados y verificados para funcionar según lo esperado, según lo especificado en el plan de copia de seguridad y restauración.

</div>

</div>

<div>

## <a name="maintaining-the-backup-and-restoration-plan"></a>Mantenimiento del plan de copia de seguridad y restauración

Una topología de Lync Server es un entorno dinámico que cambia con su organización. Reevalúe el plan de copia de seguridad y restauración a medida que su organización cambie y revise periódicamente para asegurarse de que continúa satisfaciendo las necesidades de su empresa.

</div>

</div>

<span> </span>

</div>

</div>

</div>

