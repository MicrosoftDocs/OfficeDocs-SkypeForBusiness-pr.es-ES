---
title: 'Lync Server 2013: establecer un plan de copia de seguridad y restauración'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Establishing a backup and restoration plan
ms:assetid: 9f562ef1-3804-41e2-b3e4-d45b2e8c63c9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202183(v=OCS.15)
ms:contentKeyID: 51541499
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bbe142d697fc3d95772fb2d4ca758b8550054a8e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042527"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="establishing-a-backup-and-restoration-plan-for-lync-server-2013"></a>Establecimiento de un plan de copia de seguridad y restauración para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-17_

Para crear un plan de copia de seguridad y restauración deberá seguir estos pasos:

  - Desarrollar el plan.

  - Implementar el plan.

  - Mantenimiento del plan.

<div>

## <a name="developing-a-backup-and-restoration-plan"></a>Desarrollar un plan de copia de seguridad y restauración

Después de desarrollar su estrategia de copia de seguridad y restauración para Lync Server, Úsela para documentar un plan de copia de seguridad y restauración detallado. Su plan debe explicar en detalle las prioridades y requisitos para hacer copias de seguridad de datos y configuraciones. Puede usar la información contenida en [establecer una estrategia de copia de seguridad y restauración para Lync server 2013](lync-server-2013-establishing-a-backup-and-restoration-strategy.md) y las hojas de [cálculo de copia de seguridad y restauración de Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md) para facilitar la documentación de su estrategia. Su plan deberá incluir también criterios para decidir cuándo y cómo restaurar el servicio.

A medida que desarrolla el plan, debe tener en cuenta lo siguiente:

  - Cómo se recuperarán los servidores en nuevo hardware.

  - Cómo se recuperarán los servicios que requieran acciones por parte de varios departamentos o áreas de negocio.

  - Cómo adquirir servidores de repuesto rápidamente.

  - El tiempo que se tarda en completar la recuperación utilizando su estrategia. Considere los requisitos de la organización para el objetivo de tiempo de recuperación (RTO).

Modifique los procedimientos de copia de seguridad y restauración en este tema, agregando y eliminando procedimientos según corresponda, para reflejar los servidores y los componentes de la implementación. También puede Agregar los detalles apropiados, como la programación de copia de seguridad, a los procedimientos apropiados para asegurarse de que la información no se ha desactivado.

<div>


> [!NOTE]  
> Se recomienda crear scripts para tantos pasos como sea posible, para ayudar a garantizar la calidad y la reproducibilidad de los procedimientos.



</div>

En su plan, especifique quién es responsable de revisar el plan, quién es responsable de probar y validar los nuevos procedimientos o herramientas, y quién debe aprobar los cambios en el plan y los procedimientos relacionados.

Para asegurarse de que el plan de copia de seguridad y restauración cumple completamente todos los objetivos y las prioridades establecidos, obtenga la aprobación de los responsables de la toma de decisiones empresariales y los responsables de las decisiones técnicas de su organización antes de implementar el plan.

</div>

<div>

## <a name="implementing-the-backup-and-restoration-plan"></a>Implementar el plan de copia de seguridad y restauración

Para implementar un plan de copia de seguridad y restauración es necesario seguir estos pasos:

  - Probar y validar el plan.

  - Comunicar el plan.

  - Validar las operaciones de copia de seguridad y restauración.

<div>

## <a name="testing-and-validating-the-plan"></a>Probar y validar el plan

Los procedimientos descritos aquí se han probado y validado en un entorno de laboratorio. Para asegurarse de que estos u otros procedimientos funcionan en su entorno, debe probar y validar cada procedimiento que pretenda implementar. Complete las pruebas y la validación antes de enviar el plan para la aprobación final.

</div>

<div>

## <a name="communicating-the-plan"></a>Comunicar el plan

Su plan de copia de seguridad y restauración debe describir claramente quién implementa los procedimientos e incluir instrucciones paso por paso para llevar a cabo dichos procedimientos. Debe asegurarse de que todos los responsables de cualquier aspecto de la copia de seguridad y restauración comprenden el plan, cómo se va a implementar y cuál es su rol. Tenga en cuenta todos los requisitos de implementación para los siguientes aspectos:

  - Copia de seguridad del grupo y del servidor.

  - Restauración del servicio.

**Copias de seguridad de servidores y grupos de servidores**

El plan de copia de seguridad y restauración debe incluir toda la información necesaria para completar los procedimientos de copia de seguridad de forma continuada. Deberá comunicar a los miembros del equipo responsable una serie de informaciones básicas, entre ellas las siguientes:

  - Equipo o persona (especificado como una persona o rol) responsable de realizar la copia de seguridad de cada servidor.

  - Programaciones específicas para hacer copias de seguridad de cada servidor.

  - Ubicaciones de copia de seguridad para cada tipo de datos (configuración, base de datos y recursos compartidos de archivos).

  - Procedimientos de copia de seguridad que se van a usar, incluidas las herramientas necesarias para completar cada procedimiento.

  - Información necesaria para completar las copias de seguridad, tal como se describe en las [hojas de cálculo de copia de seguridad y restauración de Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).

  - Métodos de validación que se usan para ayudar a garantizar que se realicen copias de seguridad de los datos y la configuración correctamente y que estén disponibles para la restauración, lo que puede incluir auditorías periódicas y restauraciones de prueba.

**Restauración de servicio**

El plan de copia de seguridad y restauración debe incluir toda la información necesaria para restaurar el servicio, en caso de que uno o varios servidores experimenten una pérdida que permita que el servicio no esté disponible. Deberá comunicar a los miembros del equipo responsable una serie de informaciones básicas, entre ellas las siguientes:

  - Equipo o persona (especificados como persona individual o rol) responsable de determinar cuándo se necesita restaurar el servicio, así como los procedimientos que se utilizarán para restaurarlo y el equipo o persona responsable de implementar los procedimientos para cada escenario de restauración.

  - Criterios para determinar qué procedimientos de restauración son los más apropiados para una situación concreta.

  - Tiempo estimado para la restauración del servicio y el objetivo de tiempo de recuperación (RTO) en cada escenario de restauración.

  - Procedimientos de restauración que se utilizarán, incluyendo las herramientas necesarias para completar cada procedimiento

  - Información necesaria para restaurar los datos y la configuración. Las hojas de cálculo se proporcionan en las [hojas de cálculo de copia de seguridad y restauración de Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).

</div>

<div>

## <a name="validating-backup-and-restoration-operations"></a>Validar operaciones de copia de seguridad y restauración

Tras completar las tareas iniciales de copia de seguridad en su entorno de producción y a intervalos especificados (conforme a su plan de copia de seguridad y restauración), deberá verificar lo siguiente:

  - Las copias de seguridad se están haciendo según lo requerido.

  - Se puede tener acceso a los datos y la configuración de la copia de seguridad.

  - Los procedimientos de restauración pueden realizarse dentro de las horas de objetivo de tiempo de recuperación (RTO) especificadas en el plan de copia de seguridad y restauración, y los resultados cumplen todos los requisitos empresariales.

  - Las copias de seguridad de las hojas se han completado, verificado y almacenado en una ubicación segura. Estas hojas de cálculo se proporcionan en las [hojas de cálculo de copia de seguridad y restauración de Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).

  - Los procedimientos de restauración se han probado y se ha verificado que funciona según lo esperado y conforme al plan de copia de seguridad y restauración.

</div>

</div>

<div>

## <a name="maintaining-the-backup-and-restoration-plan"></a>Mantener el plan de copia de seguridad y restauración

Una topología de Lync Server es un entorno dinámico que cambia con la organización. Reevalúe el plan de copia de seguridad y restauración a medida que su organización cambie y revise periódicamente para asegurarse de que sigue cumpliendo las necesidades de su empresa.

</div>

</div>

<span> </span>

</div>

</div>

</div>

