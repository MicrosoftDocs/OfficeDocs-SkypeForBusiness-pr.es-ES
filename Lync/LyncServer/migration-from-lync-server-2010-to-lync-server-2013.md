---
title: Migración de Lync Server 2010 a Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migration from Lync Server 2010 to Lync Server 2013
ms:assetid: ef99d4a9-a666-4a92-9994-4d7930f70d55
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205369(v=OCS.15)
ms:contentKeyID: 48185779
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 89bc70635ac941398a71515e77dd1a792973fc35
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527307"
---
# <a name="migration-from-lync-server-2010-to-lync-server-2013"></a>Migración de Lync Server 2010 a Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-17_

Los temas de esta sección le guiarán por el proceso de migración de Lync Server 2010 a Lync Server 2013.

<div>


> [!IMPORTANT]  
> Este documento describe los pasos necesarios generalmente para llevar a cabo cada fase de migración. No aborda toda la topología de implementación heredada posible o cada posible escenario de migración. Por lo tanto, dependiendo de su implementación, es posible que no necesite realizar cada paso descrito o también es posible que necesite realizar pasos adicionales. Este documento también proporciona ejemplos de pasos de verificación. Estos pasos de verificación se ofrecen para ayudarle a entender lo que necesita buscar para garantizar que cada fase finalice correctamente mientras progresa a lo largo de la migración. Individualice estos pasos de verificación para su proceso de migración particular.



</div>

Esta guía le ofrece información específica para actualizar su implementación existente. No explica cómo cambiar su topología existente. Tampoco aborda la implementación de nuevas características. Cuando se documenta en otro lugar un procedimiento detallado, esta guía le dirige al documento o sección del documento pertinente.

Este documento define términos siguiendo las especificaciones de la lista siguiente.

  - *Migraciones*  
    Mover la implementación de producción de una versión anterior de Lync Server 2010 a Lync Server 2013.

<!-- end list -->

  - *actualización*  
    Instalar una versión de software más reciente en un equipo cliente o servidor.

<!-- end list -->

  - *coexistencia*  
    El entorno temporal que existe durante la migración cuando alguna funcionalidad se ha migrado a Lync Server 2013 y la funcionalidad sigue siendo una versión anterior de Lync Server 2010.

<!-- end list -->

  - *interoperabilidad*  
    La capacidad de su implementación para funcionar correctamente durante el período e coexistencia.

<div>

## <a name="in-this-section"></a>En esta sección

  - [Antes de comenzar la migración](before-you-begin-the-migration.md)

  - [Fase 1: planear la migración desde Lync Server 2010](phase-1-plan-your-migration-from-lync-server-2010.md)

  - [Fase 2: Preparación de la migración](phase-2-prepare-for-migration.md)

  - [Fase 3: implementar el grupo piloto de Lync Server 2013](phase-3-deploy-lync-server-2013-pilot-pool.md)

  - [Fase 4: mover usuarios de prueba al grupo piloto](phase-4-move-test-users-to-the-pilot-pool.md)

  - [Fase 5: agregar un servidor perimetral de Lync Server 2013 a un grupo piloto](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

  - [Fase 6: Pasar de la implementación piloto a la producción](phase-6-move-from-pilot-deployment-into-production.md)

  - [Fase 7: Finalización de las tareas posteriores a la migración](phase-7-complete-post-migration-tasks.md)

  - [Fase 8: Retirar los grupos de servidores heredados](phase-8-decommission-legacy-pools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

