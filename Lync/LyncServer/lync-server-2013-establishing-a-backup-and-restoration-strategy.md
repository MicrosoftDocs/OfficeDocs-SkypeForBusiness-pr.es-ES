---
title: Trazar una estrategia de copia de seguridad y restauración
TOCTitle: Trazar una estrategia de copia de seguridad y restauración
ms:assetid: f545a75f-bbc4-4968-b510-8f6f3920112b
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Hh202195(v=OCS.15)
ms:contentKeyID: 52061979
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Trazar una estrategia de copia de seguridad y restauración

 

_**Última modificación del tema:** 2013-03-26_

Para desarrollar un plan de copia de seguridad y restauración para Lync Server, desarrolle una estrategia acorde con los objetivos de la organización. El desarrollo de una estrategia de copia de seguridad y restauración eficaz incluye lo siguiente:

  - Establecer las prioridades profesionales

  - Identificar los requisitos de copia de seguridad y restauración

## Establecer las prioridades profesionales

Evaluar las prioridades profesionales de la organización. Normalmente, las principales prioridades profesionales que afectan a la estrategia de copia de seguridad y restauración son las siguientes:

  - Requisitos de continuidad profesionales

  - Precisión de los datos

  - Importancia de los datos

  - Requisitos de portabilidad

  - Restricciones de costos

Con las necesidades profesionales de este tipo es más fácil determinar los contratos de nivel de servicio que puede desarrollar con sus clientes. Los contratos de nivel de servicio tienen una gran influencia en la estrategia de copia de seguridad y restauración.

## Identificar los requisitos de copia de seguridad y restauración

Las prioridades profesionales y los contratos de nivel de servicio determinan los requisitos de la organización para realizar copias de seguridad de Lync Server y restaurarlo. Identifique y documente los requisitos para lo siguiente:

  - **Frecuencia de copias de seguridad**   Recuerde que, salvo en el caso de los grupos de servidores front end en las relaciones emparejadas, tal como se describe en [Planeación de alta disponibilidad y recuperación ante desastres en Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md), Lync Server admite únicamente el modelo de recuperación simple, lo que significa que se restaura hasta la última copia de seguridad completa. Planee exhaustivamente la frecuencia con la que necesita realizar una copia de seguridad completa. Para más información sobre los procesos recomendados con relación a la frecuencia de las copias de seguridad, vea [Procedimientos recomendados de copia de seguridad y restauración](lync-server-2013-best-practices-for-backup-and-restoration.md).

  - **Herramientas de copia de seguridad y restauración**   Indique quién utilizará las herramientas y en qué equipos. Para más información sobre las herramientas que se describen en este tema y los permisos necesarios, vea [Requisitos de copia de seguridad y restauracion: herramientas y permisos](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md).

  - **Ubicación de copia de seguridad**   Identifique si las copias de seguridad se conservan de forma local o remota, teniendo en cuenta la seguridad y la accesibilidad. Especifique los medios que se utilizarán para las copias de seguridad.

  - **Requisitos de hardware y software**   Identifique y documente sus requisitos específicos de hardware y software, incluido el hardware para el almacenamiento de copias de seguridad, la restauración de componentes específicos y cualquier software y conectividad de red necesarios para la realización de copias de seguridad y la restauración. A medida que desarrolle sus requisitos de hardware y software, tenga en cuenta los distintos escenarios de restauración que se exponen a continuación.

  - **Escenarios de restauración**   Se describen los procesos de restauración para los escenarios siguientes:
    
      - Error en un grupo de Lync Server. Este escenario requiere volver a generar cada servidor del grupo.
    
      - Error en un Servidor Standard Edition. Este escenario requiere volver a generar el servidor en un equipo nuevo o limpio y restaurar las bases de datos.
    
      - Pérdida de Almacén de administración central. Como mínimo, este escenario requiere la restauración y publicación de Almacén de administración central.
    
      - Pérdida de un servidor back-end cuando Almacén de administración central aún funciona normalmente. Este escenario requiere volver a generar el servidor en un equipo nuevo o limpio y restaurar las bases de datos.
    
      - Error en un servidor miembro de un grupo de Lync Server. Este escenario requiere volver a generar el servidor en un equipo nuevo o limpio.
    
      - Error en un Almacén de archivos. Este escenario requiere restaurar el servidor de archivos o el clúster de archivos.
    
      - Una base de datos de archivado, supervisión o chat persistente da un error. En este escenario deben volver a crearse las bases de datos y, si los datos son de importancia crítica para la organización, deben restaurarse. Los datos de archivado, supervisión o chat persistente no son necesarios para obtener y ejecutar una copia de seguridad de Lync Server.

