---
title: Fases de migración
TOCTitle: Fases de migración
ms:assetid: cb7747ba-b872-42ca-ab41-76e3c4e77d06
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205336(v=OCS.15)
ms:contentKeyID: 48276693
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Fases de migración

 

_**Última modificación del tema:** 2012-09-17_

En Lync Server 2013 se definen los sitios de su red que contienen componentes Lync Server 2013. Un sitio es un conjunto de equipos que están bien conectados por una red de alta velocidad y baja latencia, como una red de área local (LAN) o dos redes conectadas por una red de fibra óptica de alta velocidad.

Un *grupo de servidores front-end* es un conjunto de servidores front-end configurados de manera idéntica que funcionan para ofrecer servicios para un grupo común de usuarios. Un grupo de servidores proporciona escalabilidad y funciones de conmutación por error a los usuarios. Cada servidor en un grupo debe ejecutar un rol o roles de servidores idénticos. Un Servidor Standard Edition, diseñado para organizaciones pequeñas, también define un grupo y se ejecuta en un solo servidor. Esto le permitirá disponer de la funcionalidad de Lync Server 2013 a un menor precio, pese a que no constituye una verdadera solución de alta disponibilidad.

La siguiente fase describe el proceso de migración de un grupo de servidores desde Lync Server 2010 a Lync Server 2013. En el caso de varios sitios que contengan varios grupos, se debe seguir este enfoque por fases para cada grupo individual.

1.  [Fase 1: Planear su migración desde Lync Server 2010](phase-1-plan-your-migration-from-lync-server-2010.md)

2.  [Fase 2: Preparar la migración](phase-2-prepare-for-migration.md)

3.  [Fase 3: Implementar un grupo piloto de Lync Server 2013](phase-3-deploy-lync-server-2013-pilot-pool.md)

4.  [Fase 4: Mover usuarios de prueba al grupo piloto](phase-4-move-test-users-to-the-pilot-pool.md)

5.  [Fase 5: Agregar servidor perimetral de Lync Server 2013 al grupo piloto](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

6.  [Fase 6: Pasar de la implementación piloto a la producción](phase-6-move-from-pilot-deployment-into-production.md)

7.  [Fase 7: Completar tareas posteriores a la migración](phase-7-complete-post-migration-tasks.md)

8.  [Fase 8: Retirar grupos heredados](phase-8-decommission-legacy-pools.md)

