---
title: Fases de la migración
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migration phases
ms:assetid: cb7747ba-b872-42ca-ab41-76e3c4e77d06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205336(v=OCS.15)
ms:contentKeyID: 48185642
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fa7226a442d8e41d4ab0e6e3511a35e020decb65
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849953"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-phases"></a>Fases de la migración

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-17_

En Lync Server 2013, se definen sitios en la red que contienen componentes de Lync Server 2013. Un sitio es un conjunto de equipos que están conectados correctamente mediante una red de alta velocidad y baja latencia, como una única red de área local (LAN) o dos redes conectadas por una red de fibra óptica de alta velocidad.

Un *Grupo* de servidores front-end es un conjunto de servidores de aplicaciones para el usuario que están configurados de manera idéntica y trabajan juntos para proporcionar servicios a un grupo común de usuarios. Un grupo proporciona capacidad de escalabilidad y conmutación por error a los usuarios. Todos los servidores de un grupo de servidores necesitan ejecutar uno o varios roles del servidor idénticos. Un servidor Standard Edition, diseñado para pequeñas organizaciones, también define un pool y se ejecuta en un solo servidor. Esto le permite tener la funcionalidad de Lync Server 2013 para un menor costo, pero no proporciona una verdadera solución de alta disponibilidad.

Las siguientes fases describen el proceso de migración de grupo de Lync Server 2010 a Lync Server 2013. Para varios sitios que contienen varios grupos, cada grupo debe seguir este enfoque por fases.

1.  [Fase 1: planear la migración desde Lync Server 2010](phase-1-plan-your-migration-from-lync-server-2010.md)

2.  [Fase 2: Preparación de la migración](phase-2-prepare-for-migration.md)

3.  [Fase 3: implementar el grupo de pruebas piloto de Lync Server 2013](phase-3-deploy-lync-server-2013-pilot-pool.md)

4.  [Fase 4: mover los usuarios de prueba al grupo piloto](phase-4-move-test-users-to-the-pilot-pool.md)

5.  [Fase 5: agregar el servidor perimetral 2013 de Lync Server a un grupo piloto](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

6.  [Fase 6: Pasar de la implementación piloto a la producción](phase-6-move-from-pilot-deployment-into-production.md)

7.  [Fase 7: Finalización de las tareas posteriores a la migración](phase-7-complete-post-migration-tasks.md)

8.  [Fase 8: Retirar los grupos de servidores heredados](phase-8-decommission-legacy-pools.md)

</div>

<span> </span>

</div>

</div>

</div>

