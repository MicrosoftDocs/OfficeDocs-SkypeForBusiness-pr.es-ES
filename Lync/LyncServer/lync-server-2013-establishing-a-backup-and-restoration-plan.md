---
title: Definir un plan de copia de seguridad y restauración
TOCTitle: Definir un plan de copia de seguridad y restauración
ms:assetid: 9f562ef1-3804-41e2-b3e4-d45b2e8c63c9
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Hh202183(v=OCS.15)
ms:contentKeyID: 52061691
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Definir un plan de copia de seguridad y restauración

 

_**Última modificación del tema:** 2013-02-17_

Para crear un plan de copia de seguridad y restauración deberá seguir estos pasos:

  - Desarrollar el plan.

  - Implementar el plan.

  - Mantener el plan.

## Desarrollar un plan de copia de seguridad y restauración

Tras desarrollar su estrategia de copia de seguridad y restauración para Lync Server, úsela para documentar un plan detallado de copia de seguridad y restauración. Su plan debe explicar en detalle las prioridades y requisitos para hacer copias de seguridad de datos y configuraciones. Puede usar la información de [Trazar una estrategia de copia de seguridad y restauración](lync-server-2013-establishing-a-backup-and-restoration-strategy.md) y las hojas de [Hojas de cálculo de copia de seguridad y restauración](lync-server-2013-backup-and-restoration-worksheets.md) para facilitar la documentación de su estrategia. Su plan deberá incluir también criterios para decidir cuándo y cómo restaurar el servicio.

A medida que desarrolle su plan, deberá considerar y tener en cuenta lo siguiente:

  - Cómo se recuperarán los servidores en nuevo hardware.

  - Cómo se recuperarán los servicios que requieran acciones por parte de varios departamentos o áreas de negocio.

  - Cómo adquirir servidores de repuesto rápidamente.

  - El tiempo que se tarda en completar la recuperación utilizando su estrategia. Tenga en cuenta los requisitos de su organización para el objetivo de tiempo de recuperación (RTO).

Cambie los procedimientos de copia de seguridad y restauración descritos en este tema. Para ello, agregue o elimine procedimientos según sea necesario a fin de reflejar la estructura de servidores y componentes de su implementación. También puede agregar detalles (como la programación de copia de seguridad) que se correspondan con los procedimientos apropiados para asegurarse de no omitir información.


> [!NOTE]
> Le recomendamos que cree scripts para tantos pasos como sea posible a fin de garantizar la calidad y reproducibilidad de los procedimientos.



Especifique en su plan quién es responsable de revisarlo, quién es responsable de probar y validar nuevos procedimientos o herramientas y quién debe aprobar los cambios en el plan y los procedimientos relacionados.

Para asegurarse de que su plan de copia de seguridad y restauración cumple con todos los objetivos y prioridades que haya establecido, obtenga la aprobación de los técnicos y responsables de negocio encargados de toma de decisiones en su organización antes de implementar el plan.

## Implementar el plan de copia de seguridad y restauración

Para implementar un plan de copia de seguridad y restauración debe hacerse lo siguiente:

  - Probar y validar el plan.

  - Comunicar el plan.

  - Validar operaciones de copia de seguridad y restauración.

## Probar y validar el plan

Los procedimientos descritos en este documento han sido probados y validados en un entorno de laboratorio. Para garantizar que estos y otros procedimientos funcionen en su entorno, pruebe y valide cada procedimiento que pretenda implementar. Complete los procesos de pruebas y validación antes de enviar el plan para su aprobación final.

## Comunicar el plan

Su plan de copia de seguridad y restauración tiene que describir claramente quién implementa los procedimientos e incluir instrucciones paso por paso para llevar a cabo dichos procedimientos. Asegúrese de que todas las personas responsables de cualquier aspecto del proceso de copia de seguridad y restauración comprende el plan, la forma de implementarlo y su rol dentro de él. Esto incluye todos los requisitos de implementación para los siguientes aspectos:

  - Copias de seguridad de servidores y grupos de servidores.

  - Restauración de servicio.

**Copias de seguridad de servidores y grupos de servidores**

El plan de copia de seguridad y restauración debe incluir toda la información necesaria para completar los procedimientos de copia de seguridad de forma continuada. Deberá comunicar a los miembros del equipo responsable una serie de informaciones básicas, entre ellas las siguientes:

  - Equipo o persona (especificados como persona individual o rol) responsable de hacer las copias de seguridad en cada servidor.

  - Programaciones específicas para copias de seguridad en cada servidor.

  - Las ubicaciones de copia de seguridad para cada tipo de datos (configuración, base de datos y recursos compartidos de archivos).

  - Procedimientos de copia de seguridad que se usarán, incluyendo las herramientas necesarias para completar cada procedimiento.

  - Información requerida para hacer copias de seguridad completas, según se explica en [Hojas de cálculo de copia de seguridad y restauración](lync-server-2013-backup-and-restoration-worksheets.md).

  - Métodos de validación que se usarán para asegurarse de que se han hecho copias de seguridad adecuadas de los datos y la configuración y que dichas copias están disponibles para su restauración. Estos métodos pueden incluir pruebas de restauración y auditorías periódicas.

**Restauración de servicio**

El plan de copia de seguridad y restauración incluirá toda la información necesaria para restaurar el servicio en el caso de que uno o más servidores experimenten una pérdida que haga que el servicio no esté disponible. Comunique a los miembros del equipo responsable la información básica, en la que se incluye:

  - Equipo o persona (especificados como persona individual o rol) responsable de determinar cuándo se necesita restaurar el servicio, así como los procedimientos que se utilizarán para restaurarlo y el equipo o persona responsable de implementar los procedimientos para cada escenario de restauración.

  - Criterios para determinar qué procedimientos de restauración son los más apropiados para una situación concreta.

  - Estimaciones de tiempo para la restauración del servicio y el objetivo de tiempo de recuperación (RTO) en cada escenario de restauración.

  - Procedimientos de restauración que se utilizarán, incluyendo las herramientas necesarias para completar cada procedimiento

  - Información necesaria para restaurar los datos y la configuración. Encontrará las hojas correspondientes en [Hojas de cálculo de copia de seguridad y restauración](lync-server-2013-backup-and-restoration-worksheets.md).

## Validar operaciones de copia de seguridad y restauración

Tras completar las tareas iniciales de copia de seguridad en su entorno de producción y a intervalos especificados (conforme a su plan de copia de seguridad y restauración), deberá verificar lo siguiente:

  - Las copias de seguridad se están haciendo según lo requerido.

  - Los datos y configuraciones de los que se han hecho copias de seguridad son accesibles.

  - Los procedimientos de restauración pueden llevarse a cabo dentro del objetivo de tiempo de recuperación (RTO) especificado en el plan de copia de seguridad y restauración, y los resultados satisfacen todos los requisitos de negocio.

  - Las copias de seguridad de las hojas se han completado, verificado y almacenado en una ubicación segura. Puede encontrar dichas hojas en [Hojas de cálculo de copia de seguridad y restauración](lync-server-2013-backup-and-restoration-worksheets.md).

  - Los procedimientos de restauración se han probado y se ha verificado que funciona según lo esperado y conforme al plan de copia de seguridad y restauración.

## Mantener el plan de copia de seguridad y restauración

Una topología de Lync Server es un entorno dinámico que cambia con su organización. Reevalúe el plan de copia de seguridad y restauración a medida que cambie la organización y revíselo periódicamente para asegurarse de que sigue satisfaciendo las necesidades del negocio.

