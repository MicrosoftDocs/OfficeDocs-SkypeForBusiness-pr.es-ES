---
title: Fases de la migración
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: En Skype Empresarial Server 2019, se definen sitios en la red que contienen Skype Empresarial Server componentes de 2019. Un sitio es un conjunto de equipos que están bien conectados por una red de alta velocidad y baja latencia, como una red de área local (LAN) o dos redes conectadas por una red de fibra óptica de alta velocidad.
ms.openlocfilehash: 0e79dca32a0e3c377eea8e60e0e19514dcb7f4dfb459922b68c9913f4bd3c363
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54303424"
---
# <a name="migration-phases"></a>Fases de la migración

En Skype Empresarial Server 2019, se definen sitios en la red que contienen Skype Empresarial Server componentes de 2019. Un sitio es un conjunto de equipos que están bien conectados por una red de alta velocidad y baja latencia, como una red de área local (LAN) o dos redes conectadas por una red de fibra óptica de alta velocidad. 
  
Un grupo de servidores front-end es un conjunto de servidores front-end configurados de manera idéntica que funcionan para ofrecer servicios para un grupo común de usuarios. Un grupo de servidores proporciona escalabilidad y funciones de conmutación por error a los usuarios. Cada servidor en un grupo debe ejecutar un rol o roles de servidores idénticos. Un servidor Standard Edition, diseñado para organizaciones pequeñas, también define un grupo de servidores y se ejecuta en un solo servidor. Esto le permite tener una Skype Empresarial Server 2019 con un costo menor, pero no proporciona una solución de alta disponibilidad real. 
  
En las siguientes fases se describe el proceso de migración de un grupo a Skype Empresarial Server 2019. En el caso de varios sitios que contengan varios grupos, se debe seguir este enfoque por fases para cada grupo individual.
  
1. [Fase 1: Planear la migración](phase-1-plan-your-migration.md)
    
2. [Fase 2: Preparación de la migración](phase-2-prepare-for-migration.md)
    
3. [Fase 3: Implementar Skype Empresarial Server grupo piloto de 2019](phase-3-deploy-pilot-pool.md)
    
4. [Fase 4: Mover usuarios de prueba al grupo piloto](phase-4-move-test-users-to-the-pilot-pool.md)
    
5. [Fase 5: Agregar Skype Empresarial Server servidor perimetral de 2019 al grupo piloto](phase-5-add-edge-server-to-pilot-pool.md)
    
6. [Fase 6: Pasar de la implementación piloto a la producción](phase-6-move-from-pilot-deployment-into-production.md)
    
7. [Fase 7: Finalización de las tareas posteriores a la migración](phase-7-complete-post-migration-tasks.md)
    
8. [Fase 8: Retirar los grupos de servidores heredados](phase-8-decommission-legacy-pools.md)
    

