---
title: Migrar de Office Communications Server 2007 R2 a Lync Server 2013
TOCTitle: Migrar de Office Communications Server 2007 R2 a Lync Server 2013
ms:assetid: f3fa4f5f-e9a2-4fb7-a12d-20f04173e697
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205375(v=OCS.15)
ms:contentKeyID: 48277172
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Migrar de Office Communications Server 2007 R2 a Lync Server 2013

 

_**Última modificación del tema:** 2012-10-19_

En los temas de esta sección se le indica cómo realizar el proceso de migración de Office Communications Server 2007 R2 a Lync Server 2013.

> [!IMPORTANT]  
> En este documento se describen los pasos generalmente necesarios para llevar a cabo cada fase de migración. No se aborda cada posible topología de implementación heredada ni cada posible escenario de migración. Por lo tanto, dependiendo de su implementación, es posible que no necesite realizar cada paso descrito o bien es posible que necesite realizar pasos adicionales. En este documento también se ofrecen ejemplos de pasos de verificación. Estos pasos de verificación se ofrecen para ayudarle a entender lo que necesita buscar para garantizar que cada fase se finaliza correctamente mientras progresa a lo largo de su migración. Individualice estos pasos de verificación para su proceso de migración particular.



En esta guía se le ofrece información específica para actualizar su implementación existente. No se explica cómo cambiar su topología existente. En esta guía no se aborda la implementación de nuevas características. Cuando se documenta en otro lugar un procedimiento detallado, en esta guía se le dirige al documento o sección del documento pertinente.

En este documento se definen los términos siguiendo las especificaciones de la lista siguiente.

  - *migración*  
    Mover la implementación de su producción de una versión previa de Office Communications Server 2007 R2 a Lync Server 2013.

<!-- end list -->

  - *actualizar*  
    Instalar una versión más reciente de software en un servidor o equipo de cliente.

<!-- end list -->

  - *coexistencia*  
    Entorno temporal que se produce durante la migración cuando alguna funcionalidad se ha migrado a Lync Server 2013 y otra sigue aún en una versión anterior de Office Communications Server 2007 R2.

<!-- end list -->

  - *interoperabilidad*  
    La capacidad de su implementación para funcionar correctamente durante el período de coexistencia.

## En esta sección

  - [Antes de comenzar la migración](before-you-begin-the-migration_1.md)

  - [Fases de migración](migration-phases_1.md)

  - [Fase 1: Planear la migración de Office Communications Server 2007 R2](phase-1-plan-your-migration-from-office-communications-server-2007-r2.md)

  - [Fase 2: Preparar la migración](phase-2-prepare-for-migration_1.md)

  - [Fase 3: Implementar un grupo piloto de Lync Server 2013](phase-3-deploy-lync-server-2013-pilot-pool_1.md)

  - [Fase 4: Combinar topologías](phase-4-merge-topologies.md)

  - [Fase 5: Configurar el grupo piloto](phase-5-configure-the-pilot-pool.md)

  - [Fase 6: Mover usuarios al grupo piloto](phase-6-move-users-to-the-pilot-pool.md)

  - [Fase 7: Agregar un servidor perimetral de Lync Server 2013 al grupo piloto](phase-7-add-lync-server-2013-edge-server-to-pilot-pool.md)

  - [Fase 8: Mover de implementación piloto a producción](phase-8-move-from-pilot-deployment-into-production.md)

  - [Fase 9: Completar tareas posteriores a la migración](phase-9-complete-post-migration-tasks.md)

  - [Fase 10: Retirar sitios heredados](phase-10-decommission-legacy-site.md)

