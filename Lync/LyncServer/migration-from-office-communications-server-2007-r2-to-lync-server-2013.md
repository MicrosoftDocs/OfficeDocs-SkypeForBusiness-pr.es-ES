---
title: Migración de Office Communications Server 2007 R2 a Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migration from Office Communications Server 2007 R2 to Lync Server 2013
ms:assetid: f3fa4f5f-e9a2-4fb7-a12d-20f04173e697
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205375(v=OCS.15)
ms:contentKeyID: 48185802
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 624891658fb925fbc2522e98f8b216e535d2bf0c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035896"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-from-office-communications-server-2007-r2-to-lync-server-2013"></a>Migración de Office Communications Server 2007 R2 a Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-19_

Los temas de esta sección le guiarán por el proceso de migración de Office Communications Server 2007 R2 a Lync Server 2013

<div>


> [!IMPORTANT]  
> Este documento describe los pasos necesarios generalmente para llevar a cabo cada fase de migración. No aborda toda la topología de implementación heredada posible o cada posible escenario de migración. Por lo tanto, dependiendo de su implementación, es posible que no necesite realizar cada paso descrito o también es posible que necesite realizar pasos adicionales. Este documento también proporciona ejemplos de pasos de verificación. Estos pasos de verificación se ofrecen para ayudarle a entender lo que necesita buscar para garantizar que cada fase finalice correctamente mientras progresa a lo largo de la migración. Individualice estos pasos de verificación para su proceso de migración particular.



</div>

Esta guía le ofrece información específica para actualizar su implementación existente. No explica cómo cambiar su topología existente. Tampoco aborda la implementación de nuevas características. Cuando se documenta en otro lugar un procedimiento detallado, esta guía le dirige al documento o sección del documento pertinente.

Este documento define términos siguiendo las especificaciones de la lista siguiente.

  - *Migraciones*  
    Mover la implementación de producción de una versión anterior de Office Communications Server 2007 R2 a Lync Server 2013.

<!-- end list -->

  - *actualización*  
    Instalar una versión de software más reciente en un equipo cliente o servidor.

<!-- end list -->

  - *coexistencia*  
    El entorno temporal que existe durante la migración cuando alguna funcionalidad se ha migrado a Lync Server 2013 y la funcionalidad sigue siendo una versión anterior de Office Communications Server 2007 R2.

<!-- end list -->

  - *interoperabilidad*  
    La capacidad de su implementación para funcionar correctamente durante el período e coexistencia.

<div>

## <a name="in-this-section"></a>En esta sección

  - [Antes de comenzar la migración](before-you-begin-the-migration_1.md)

  - [Fases de la migración](migration-phases_1.md)

  - [Fase 1: planear la migración desde Office Communications Server 2007 R2](phase-1-plan-your-migration-from-office-communications-server-2007-r2.md)

  - [Fase 2: preparar la migración](phase-2-prepare-for-migration_1.md)

  - [Fase 3: implementar el grupo piloto de Lync Server 2013](phase-3-deploy-lync-server-2013-pilot-pool_1.md)

  - [Fase 4: combinar topologías](phase-4-merge-topologies.md)

  - [Fase 5: configurar el grupo piloto](phase-5-configure-the-pilot-pool.md)

  - [Fase 6: mover usuarios al grupo piloto](phase-6-move-users-to-the-pilot-pool.md)

  - [Fase 7: agregar un servidor perimetral de Lync Server 2013 a un grupo piloto](phase-7-add-lync-server-2013-edge-server-to-pilot-pool.md)

  - [Fase 8: pasar de la implementación piloto a la producción](phase-8-move-from-pilot-deployment-into-production.md)

  - [Fase 9: completar las tareas posteriores a la migración](phase-9-complete-post-migration-tasks.md)

  - [Fase 10: retirar el sitio heredado](phase-10-decommission-legacy-site.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

