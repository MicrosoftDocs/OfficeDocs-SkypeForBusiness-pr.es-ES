---
title: Fases de la migración
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: En Skype para Business Server 2019, es posible definir sitios en la red que contienen Skype para los componentes de Business Server 2019. Un sitio es un conjunto de equipos que están bien conectados mediante una red de alta velocidad, baja latencia, como una única red de área local (LAN) o dos redes conectadas mediante una red óptica de fibra de alta velocidad.
ms.openlocfilehash: d34351b551262450dee852efd7679f17cbe1e161
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231626"
---
# <a name="migration-phases"></a>Fases de la migración

En Skype para Business Server 2019, es posible definir sitios en la red que contienen Skype para los componentes de Business Server 2019. Un sitio es un conjunto de equipos que están bien conectados mediante una red de alta velocidad, baja latencia, como una única red de área local (LAN) o dos redes conectadas mediante una red óptica de fibra de alta velocidad. 
  
Un grupo de servidores Front-End es un conjunto de servidores Front-End que están configurados de manera idéntica y trabajo de conjuntamente para proporcionar servicios para un grupo de usuarios comunes. Un grupo de servidores proporciona escalabilidad y capacidad de conmutación por error a los usuarios. Todos los servidores de un grupo de servidores necesitan ejecutar uno o varios roles del servidor idénticos. Un servidor Standard Edition, diseñado para las organizaciones pequeñas, también define un grupo de servidores y se ejecuta en un único servidor. Esto permite disponer de Skype para la funcionalidad de Business Server 2019 para un costo menor, pero no proporciona una solución de alta disponibilidad es true. 
  
Las siguientes fases describen el proceso de una migración de grupo de servidores a Skype para Business Server 2019. Para varios sitios que contiene varios grupos de servidores, cada grupo de servidores individual debe seguir este enfoque por fases.
  
1. [Fase 1: Planear la migración](phase-1-plan-your-migration.md)
    
2. [Fase 2: Preparación de la migración](phase-2-prepare-for-migration.md)
    
3. [Fase 3: Implementar Skype para Business Server 2019 el grupo piloto](phase-3-deploy-pilot-pool.md)
    
4. [Fase 4: Mover usuarios de prueba al grupo piloto](phase-4-move-test-users-to-the-pilot-pool.md)
    
5. [Fase 5: Agregar Skype para servidor perimetral de Business Server 2019 al grupo piloto](phase-5-add-edge-server-to-pilot-pool.md)
    
6. [Fase 6: Pasar de la implementación piloto a la producción](phase-6-move-from-pilot-deployment-into-production.md)
    
7. [Fase 7: Finalización de las tareas posteriores a la migración](phase-7-complete-post-migration-tasks.md)
    
8. [Fase 8: Retirar los grupos de servidores heredados](phase-8-decommission-legacy-pools.md)
    

