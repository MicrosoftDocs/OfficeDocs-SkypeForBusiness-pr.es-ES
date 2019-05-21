---
title: Fases de la migración
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: En Skype empresarial Server 2019, define sitios en su red que contienen componentes de Skype empresarial Server 2019. Un sitio es un conjunto de equipos que están conectados correctamente mediante una red de alta velocidad y baja latencia, como una única red de área local (LAN) o dos redes conectadas por una red de fibra óptica de alta velocidad.
ms.openlocfilehash: 8f50f25536e330a03440702614f81c09ce74518a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34298165"
---
# <a name="migration-phases"></a>Fases de la migración

En Skype empresarial Server 2019, define sitios en su red que contienen componentes de Skype empresarial Server 2019. Un sitio es un conjunto de equipos que están conectados correctamente mediante una red de alta velocidad y baja latencia, como una única red de área local (LAN) o dos redes conectadas por una red de fibra óptica de alta velocidad. 
  
Un grupo de servidores front-end es un conjunto de servidores de aplicaciones para el usuario que están configurados de manera idéntica y trabajan juntos para proporcionar servicios a un grupo común de usuarios. Un grupo proporciona capacidad de escalabilidad y conmutación por error a los usuarios. Todos los servidores de un grupo de servidores necesitan ejecutar uno o varios roles del servidor idénticos. Un servidor Standard Edition, diseñado para pequeñas organizaciones, también define un pool y se ejecuta en un solo servidor. Esto le permite tener la funcionalidad de Skype empresarial Server 2019 por un menor costo, pero no proporciona una verdadera solución de alta disponibilidad. 
  
Las siguientes fases describen el proceso de migración de grupo a Skype empresarial Server 2019. Para varios sitios que contienen varios grupos, cada grupo debe seguir este enfoque por fases.
  
1. [Fase 1: Planear la migración](phase-1-plan-your-migration.md)
    
2. [Fase 2: Preparación de la migración](phase-2-prepare-for-migration.md)
    
3. [Fase 3: implementar el grupo de pruebas piloto de Skype empresarial Server 2019](phase-3-deploy-pilot-pool.md)
    
4. [Fase 4: mover los usuarios de prueba al grupo piloto](phase-4-move-test-users-to-the-pilot-pool.md)
    
5. [Fase 5: agregar el servidor perimetral de Skype empresarial Server 2019 a una agrupación piloto](phase-5-add-edge-server-to-pilot-pool.md)
    
6. [Fase 6: Pasar de la implementación piloto a la producción](phase-6-move-from-pilot-deployment-into-production.md)
    
7. [Fase 7: Finalización de las tareas posteriores a la migración](phase-7-complete-post-migration-tasks.md)
    
8. [Fase 8: Retirar los grupos de servidores heredados](phase-8-decommission-legacy-pools.md)
    

