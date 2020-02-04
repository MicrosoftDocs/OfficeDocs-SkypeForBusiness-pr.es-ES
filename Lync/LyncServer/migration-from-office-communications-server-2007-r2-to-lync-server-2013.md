---
title: Migrar de Office Communications Server 2007 R2 a Lync Server 2013
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
ms.openlocfilehash: e32d43e8052de454647cd9f69b4572d178a0cecb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730970"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-from-office-communications-server-2007-r2-to-lync-server-2013"></a>Migrar de Office Communications Server 2007 R2 a Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-19_

Los temas de esta sección le guían a través del proceso de migración de Office Communications Server 2007 R2 a Lync Server 2013

<div>


> [!IMPORTANT]  
> Este documento describe los pasos que generalmente se necesitan para realizar cada fase de la migración. No se trata de todas las topologías de implementación heredadas o de todos los escenarios posibles de migración. Por lo tanto, es posible que no tenga que realizar cada paso descrito, o puede que tenga que realizar algunos pasos adicionales, en función de su implementación. Este documento también proporciona ejemplos de pasos de verificación. Estos pasos de verificación se proporcionan para ayudarle a comprender lo que debe buscar para asegurarse de que cada fase se complete correctamente a medida que avanza en la migración. Adapte estos pasos de verificación a su proceso de migración específico.



</div>

Esta guía proporciona información específica para actualizar la implementación existente. No se explica cómo cambiar la topología existente. Esta guía no cubre la implementación de nuevas características. Cuando un procedimiento detallado está documentado en otra parte, esta guía le dirige a la sección documento o documento adecuada.

Este documento define los términos según se especifican en la siguiente lista.

  - *realizar*  
    Mover la implementación de producción de una versión anterior de Office Communications Server 2007 R2 a Lync Server 2013.

<!-- end list -->

  - *actualiza*  
    Instalar una versión más reciente del software en un servidor o en un equipo cliente.

<!-- end list -->

  - *coexistencia*  
    El entorno temporal que existe durante la migración cuando se ha migrado cierta funcionalidad a Lync Server 2013 y otras funciones siguen en una versión anterior de Office Communications Server 2007 R2.

<!-- end list -->

  - *interoperabilidad*  
    La capacidad de la implementación para funcionar correctamente durante el período de coexistencia.

<div>

## <a name="in-this-section"></a>En esta sección

  - [Antes de comenzar la migración](before-you-begin-the-migration_1.md)

  - [Fases de la migración](migration-phases_1.md)

  - [Fase 1: planear la migración de Office Communications Server 2007 R2](phase-1-plan-your-migration-from-office-communications-server-2007-r2.md)

  - [Fase 2: Preparación de la migración](phase-2-prepare-for-migration_1.md)

  - [Fase 3: implementar el grupo de pruebas piloto de Lync Server 2013](phase-3-deploy-lync-server-2013-pilot-pool_1.md)

  - [Fase 4: combinar topologías](phase-4-merge-topologies.md)

  - [Fase 5: configurar el grupo piloto](phase-5-configure-the-pilot-pool.md)

  - [Fase 6: mover usuarios a la agrupación piloto](phase-6-move-users-to-the-pilot-pool.md)

  - [Fase 7: agregar el servidor perimetral 2013 de Lync Server a un grupo piloto](phase-7-add-lync-server-2013-edge-server-to-pilot-pool.md)

  - [Fase 8: pasar de la implementación piloto a la producción](phase-8-move-from-pilot-deployment-into-production.md)

  - [Fase 9: completar las tareas posteriores a la migración](phase-9-complete-post-migration-tasks.md)

  - [Fase 10: retirar el sitio heredado](phase-10-decommission-legacy-site.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

