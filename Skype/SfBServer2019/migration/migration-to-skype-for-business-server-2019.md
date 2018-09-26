---
title: Migración a Skype para Business Server 2019
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: En los temas de esta sección le guían por el proceso de migración a Skype para Business Server 2019.
ms.openlocfilehash: 544dd01cdea68971b54374ca6e0e94909e249c82
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "25027833"
---
# <a name="migration-to-skype-for-business-server-2019"></a>Migración a Skype para Business Server 2019

En los temas de esta sección le guían por el proceso de migración a Skype para Business Server 2019. Este artículo describen migración Lync Server 2013 o Skype para Business Server 2015 para Skype para Business Server 2019.

> [!IMPORTANT]
> En todo el contenido, usamos el término de *heredado* para hacer referencia a la heredados Lync Server 2013 o Skype para Business Server 2015 que va a migrar a Skype para Business Server 2019.
  
> [!IMPORTANT]
> Esta guía describe los pasos que se requieren normalmente para llevar a cabo cada fase de migración. No se trata cada topología de implementación heredada posibles o cada escenario de migración posibles. Por lo tanto, es posible que no necesite realizar cada paso del proceso que se describen, o es posible que necesite realizar pasos adicionales, dependiendo de la implementación. Esta guía también proporciona ejemplos de los pasos de verificación. Se proporcionan estos pasos de comprobación que le ayudarán a comprender lo que necesita buscar para asegurarse de que cada fase se realiza correctamente a medida que avance a través de la migración. Adaptar estos pasos de comprobación para el proceso de migración específicos. 
  
Esta guía proporciona información específica para actualizar la implementación existente. No se explica cómo cambiar la topología existente. Esta guía no aborda la implementación de nuevas características. Cuando un procedimiento detallado está documentado en otro lugar, esta guía le dirige a la sección de artículo o el artículo. 
  
En este artículo se define los términos tal como se especifica en la siguiente lista.
  
**migración:** Mover la implementación de producción de Lync Server 2013 o Skype para Business Server 2015 a Skype para Business Server 2019.
    
**coexistencia:** El entorno temporal que se produce durante la migración cuando alguna funcionalidad se ha migrado a Skype para Business Server 2019 y otra funcionalidad sigue aún en una versión anterior.
    
**interoperabilidad:** La capacidad de la implementación para funcionar correctamente durante el período de coexistencia.

**heredado:** El sistema va a migrar desde, lo que es Lync Server 2013 o Skype para Business Server 2015.
    
## <a name="in-this-section"></a>En esta sección

- [Antes de comenzar la migración](before-you-begin-the-migration.md)
    
- [Fase 1: Planear la migración](phase-1-plan-your-migration.md)
    
- [Fase 2: Preparación para la migración](phase-2-prepare-for-migration.md)
    
- [Fase 3: Implementar grupo piloto](phase-3-deploy-pilot-pool.md)
    
- [Fase 4: Mover usuarios de prueba al grupo piloto](phase-4-move-test-users-to-the-pilot-pool.md)
    
- [Fase 5: Agregar servidor perimetral al grupo piloto](phase-5-add-edge-server-to-pilot-pool.md)
    
- [Fase 6: Pasar de la implementación piloto a producción](phase-6-move-from-pilot-deployment-into-production.md)
    
- [Fase 7: Completar tareas posteriores a la migración](phase-7-complete-post-migration-tasks.md)
    
- [Fase 8: Retirar grupos de servidores heredados](phase-8-decommission-legacy-pools.md)
    

