---
title: Fases de la migración
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migration phases
ms:assetid: cb7747ba-b872-42ca-ab41-76e3c4e77d06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205336(v=OCS.15)
ms:contentKeyID: 48185642
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 63f789abee1949f7fae5a7a3d7dcdc03c86dc352
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527227"
---
# <a name="migration-phases"></a>Fases de la migración

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-17_

En Lync Server 2013, defina sitios en la red que contengan componentes de Lync Server 2013. Un sitio es un conjunto de equipos que están bien conectados por una red de alta velocidad y baja latencia, como una red de área local (LAN) o dos redes conectadas por una red de fibra óptica de alta velocidad.

Un *grupo de servidores front-end* es un conjunto de servidores front-end configurados de manera idéntica que funcionan para ofrecer servicios para un grupo común de usuarios. Un grupo de servidores proporciona escalabilidad y funciones de conmutación por error a los usuarios. Cada servidor en un grupo debe ejecutar un rol o roles de servidores idénticos. Un servidor Standard Edition, diseñado para pequeñas organizaciones, también define un grupo y se ejecuta en un único servidor. Esto le permite tener funcionalidad de Lync Server 2013 para un costo menor, pero no proporciona una solución de alta disponibilidad real.

En las siguientes fases, se describe el proceso de una migración de grupo de Lync Server 2010 a Lync Server 2013. En el caso de varios sitios que contengan varios grupos, se debe seguir este enfoque por fases para cada grupo individual.

1.  [Fase 1: planear la migración desde Lync Server 2010](phase-1-plan-your-migration-from-lync-server-2010.md)

2.  [Fase 2: Preparación de la migración](phase-2-prepare-for-migration.md)

3.  [Fase 3: implementar el grupo piloto de Lync Server 2013](phase-3-deploy-lync-server-2013-pilot-pool.md)

4.  [Fase 4: mover usuarios de prueba al grupo piloto](phase-4-move-test-users-to-the-pilot-pool.md)

5.  [Fase 5: agregar un servidor perimetral de Lync Server 2013 a un grupo piloto](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

6.  [Fase 6: Pasar de la implementación piloto a la producción](phase-6-move-from-pilot-deployment-into-production.md)

7.  [Fase 7: Finalización de las tareas posteriores a la migración](phase-7-complete-post-migration-tasks.md)

8.  [Fase 8: Retirar los grupos de servidores heredados](phase-8-decommission-legacy-pools.md)

</div>

<span> </span>

</div>

</div>

</div>

