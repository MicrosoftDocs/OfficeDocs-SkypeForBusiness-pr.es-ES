---
title: Migración a Skype Empresarial Server 2019
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Los temas de esta sección le guían a través del proceso de migración a Skype Empresarial Server 2019.
ms.openlocfilehash: 6eb192c11ec8d1f44539e3bd5180249d85180d2b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58587982"
---
# <a name="migration-to-skype-for-business-server-2019"></a>Migración a Skype Empresarial Server 2019

Los temas de esta sección le guían a través del proceso de migración a Skype Empresarial Server 2019. En este artículo se trata la migración de Lync Server 2013 o Skype Empresarial Server 2015 a Skype Empresarial Server 2019.

> [!IMPORTANT]
> En todo el contenido,  usamos el término heredado para hacer referencia al Lync Server 2013 o Skype Empresarial Server 2015 heredado que está migrando a Skype Empresarial Server 2019.
  
> [!IMPORTANT]
> En esta guía se describen los pasos generalmente necesarios para realizar cada fase de migración. No aborda toda la topología de implementación heredada posible o cada posible escenario de migración. Por lo tanto, dependiendo de su implementación, es posible que no necesite realizar cada paso descrito o también es posible que necesite realizar pasos adicionales. Esta guía también proporciona ejemplos de pasos de comprobación. Estos pasos de verificación se ofrecen para ayudarle a entender lo que necesita buscar para garantizar que cada fase finalice correctamente mientras progresa a lo largo de la migración. Individualice estos pasos de verificación para su proceso de migración particular. 
  
Esta guía le ofrece información específica para actualizar su implementación existente. No explica cómo cambiar su topología existente. Tampoco aborda la implementación de nuevas características. Cuando se documenta un procedimiento detallado en otro lugar, esta guía le dirige a la sección de artículos o artículos. 
  
En este artículo se definen los términos especificados en la siguiente lista.
  
**migración:** Mover la implementación de producción de Lync Server 2013 o Skype Empresarial Server 2015 a Skype Empresarial Server 2019.
    
**coexistencia:** El entorno temporal que existe durante la migración cuando algunas funciones se han migrado a Skype Empresarial Server 2019 y otras funciones permanecen en una versión anterior.
    
**interoperabilidad:** La capacidad de la implementación para funcionar correctamente durante el período de coexistencia.

**heredado:** El sistema desde el que está migrando, que es Lync Server 2013 o Skype Empresarial Server 2015.
    
## <a name="in-this-section"></a>En esta sección

- [Antes de comenzar la migración](before-you-begin-the-migration.md)
    
- [Fase 1: Planear la migración](phase-1-plan-your-migration.md)
    
- [Fase 2: Preparación de la migración](phase-2-prepare-for-migration.md)
    
- [Fase 3: Implementar un grupo de servidores piloto](phase-3-deploy-pilot-pool.md)
    
- [Fase 4: Mover usuarios de prueba al grupo piloto](phase-4-move-test-users-to-the-pilot-pool.md)
    
- [Fase 5: Agregar un servidor perimetral al grupo de servidores piloto](phase-5-add-edge-server-to-pilot-pool.md)
    
- [Fase 6: Pasar de la implementación piloto a la producción](phase-6-move-from-pilot-deployment-into-production.md)
    
- [Fase 7: Finalización de las tareas posteriores a la migración](phase-7-complete-post-migration-tasks.md)
    
- [Fase 8: Retirar los grupos de servidores heredados](phase-8-decommission-legacy-pools.md)
    

