---
title: Migrar Lync Server 2010 a Lync Server 2013
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
ms.openlocfilehash: 0c32d2679d4f31863e389735efb6660ea670b959
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727730"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-from-lync-server-2010-to-lync-server-2013"></a>Migrar Lync Server 2010 a Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-17_

Los temas de esta sección le guiarán a través del proceso de migración de Lync Server 2010 a Lync Server 2013.

<div>


> [!IMPORTANT]  
> Este documento describe los pasos que generalmente se necesitan para realizar cada fase de la migración. No se trata de todas las topologías de implementación heredadas o de todos los escenarios posibles de migración. Por lo tanto, es posible que no tenga que realizar cada paso descrito, o puede que tenga que realizar algunos pasos adicionales, en función de su implementación. Este documento también proporciona ejemplos de pasos de verificación. Estos pasos de verificación se proporcionan para ayudarle a comprender lo que debe buscar para asegurarse de que cada fase se complete correctamente a medida que avanza en la migración. Adapte estos pasos de verificación a su proceso de migración específico.



</div>

Esta guía proporciona información específica para actualizar la implementación existente. No se explica cómo cambiar la topología existente. Esta guía no cubre la implementación de nuevas características. Cuando un procedimiento detallado está documentado en otra parte, esta guía le dirige a la sección documento o documento adecuada.

Este documento define los términos según se especifican en la siguiente lista.

  - *realizar*  
    Mover la implementación de producción de una versión anterior de Lync Server 2010 a Lync Server 2013.

<!-- end list -->

  - *actualiza*  
    Instalar una versión más reciente del software en un servidor o en un equipo cliente.

<!-- end list -->

  - *coexistencia*  
    El entorno temporal que existe durante la migración cuando se ha migrado cierta funcionalidad a Lync Server 2013 y otras funciones siguen en una versión anterior de Lync Server 2010.

<!-- end list -->

  - *interoperabilidad*  
    La capacidad de la implementación para funcionar correctamente durante el período de coexistencia.

<div>

## <a name="in-this-section"></a>En esta sección

  - [Antes de comenzar la migración](before-you-begin-the-migration.md)

  - [Fase 1: planear la migración desde Lync Server 2010](phase-1-plan-your-migration-from-lync-server-2010.md)

  - [Fase 2: Preparación de la migración](phase-2-prepare-for-migration.md)

  - [Fase 3: implementar el grupo de pruebas piloto de Lync Server 2013](phase-3-deploy-lync-server-2013-pilot-pool.md)

  - [Fase 4: mover los usuarios de prueba al grupo piloto](phase-4-move-test-users-to-the-pilot-pool.md)

  - [Fase 5: agregar el servidor perimetral 2013 de Lync Server a un grupo piloto](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

  - [Fase 6: Pasar de la implementación piloto a la producción](phase-6-move-from-pilot-deployment-into-production.md)

  - [Fase 7: Finalización de las tareas posteriores a la migración](phase-7-complete-post-migration-tasks.md)

  - [Fase 8: Retirar los grupos de servidores heredados](phase-8-decommission-legacy-pools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

