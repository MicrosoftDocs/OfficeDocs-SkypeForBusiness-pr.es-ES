---
title: Migración a Skype empresarial Server 2019
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Los temas de esta sección le guían a través del proceso de migración a Skype empresarial Server 2019.
ms.openlocfilehash: bd1513e5ca2a33449f982394e4abc15b9616393b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34298151"
---
# <a name="migration-to-skype-for-business-server-2019"></a>Migración a Skype empresarial Server 2019

Los temas de esta sección le guían a través del proceso de migración a Skype empresarial Server 2019. En este artículo se describe la migración de Lync Server 2013 o Skype empresarial 2015 a Skype empresarial Server 2019.

> [!IMPORTANT]
> En todo el contenido, usamos el término *heredado* para referirse a los sistemas de Lync Server 2013 o Skype empresarial Server 2015 que está migrando a Skype empresarial Server 2019.
  
> [!IMPORTANT]
> En esta guía, se describen los pasos necesarios para llevar a cabo cada fase de la migración. No se trata de todas las topologías de implementación heredadas o de todos los escenarios posibles de migración. Por lo tanto, es posible que no tenga que realizar cada paso descrito, o puede que tenga que realizar algunos pasos adicionales, en función de su implementación. Esta guía también proporciona ejemplos de pasos de verificación. Estos pasos de verificación se proporcionan para ayudarle a comprender lo que debe buscar para asegurarse de que cada fase se complete correctamente a medida que avanza en la migración. Adapte estos pasos de verificación a su proceso de migración específico. 
  
Esta guía proporciona información específica para actualizar la implementación existente. No se explica cómo cambiar la topología existente. Esta guía no cubre la implementación de nuevas características. Cuando se documenta un procedimiento detallado en otra parte, esta guía le dirige a la sección de artículo o artículo. 
  
En este artículo se definen los términos según se especifica en la siguiente lista.
  
**migración:** Mover la implementación de producción de Lync Server 2013 o Skype empresarial 2015 a Skype empresarial Server 2019.
    
**coexistencia:** El entorno temporal que existe durante la migración cuando se ha migrado cierta funcionalidad a Skype empresarial Server 2019 y otras funciones siguen en una versión anterior.
    
**interoperabilidad:** La capacidad de la implementación para funcionar correctamente durante el período de coexistencia.

**heredado:** El sistema desde el que se está migrando, que es Lync Server 2013 o Skype empresarial Server 2015.
    
## <a name="in-this-section"></a>En esta sección

- [Antes de comenzar la migración](before-you-begin-the-migration.md)
    
- [Fase 1: Planear la migración](phase-1-plan-your-migration.md)
    
- [Fase 2: Preparación de la migración](phase-2-prepare-for-migration.md)
    
- [Fase 3: Implementar un grupo de servidores piloto](phase-3-deploy-pilot-pool.md)
    
- [Fase 4: mover los usuarios de prueba al grupo piloto](phase-4-move-test-users-to-the-pilot-pool.md)
    
- [Fase 5: Agregar un servidor perimetral al grupo de servidores piloto](phase-5-add-edge-server-to-pilot-pool.md)
    
- [Fase 6: Pasar de la implementación piloto a la producción](phase-6-move-from-pilot-deployment-into-production.md)
    
- [Fase 7: Finalización de las tareas posteriores a la migración](phase-7-complete-post-migration-tasks.md)
    
- [Fase 8: Retirar los grupos de servidores heredados](phase-8-decommission-legacy-pools.md)
    

