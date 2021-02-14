---
title: Conecte el grupo de servidores piloto a los servidores perimetrales heredados
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
description: Después de implementar Skype Empresarial Server 2019, debe configurar una ruta de federación para su sitio. Para usar la ruta federada que está utilizando la instalación heredada, Skype Empresarial Server 2019 debe configurarse para usar esta ruta.
ms.openlocfilehash: 8243ebbf9540587dedd8e4ae3a51e22f9a315728
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753930"
---
# <a name="connect-pilot-pool-to-legacy-edge-servers"></a>Conecte el grupo de servidores piloto a los servidores perimetrales heredados

Después de implementar Skype Empresarial Server 2019, debe configurar una ruta de federación para su sitio. Para usar la ruta federada que está utilizando la instalación heredada, Skype Empresarial Server 2019 debe configurarse para usar esta ruta. 
  
Para habilitar el sitio de Skype Empresarial Server 2019 para que use el director y el servidor perimetral de la implementación heredada, use topology Builder para asociar el grupo de servidores perimetrales heredado.
  
### <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a>Para asociar el grupo de servidores perimetrales heredados usando el Generador de topologías

1. Abra el Generador de topologías. 
    
2. Seleccione su sitio, que está directamente debajo del **nodo de Skype Empresarial Server.** 
    
3. En el menú **Acciones**, haga clic en **Editar propiedades**.
    
4. En el panel izquierdo, seleccione **Ruta de federación**.
    
5. En **Asignación de ruta** de federación de sitio, seleccione Habilitar federación **SIP** y, a continuación, seleccione el director heredado o el servidor perimetral heredado si no aparece ningún director.
  
6. Haga clic en **Aceptar** para cerrar la página **Editar propiedades**. 
    
7. En el Generador de topologías, en el nodo de Skype Empresarial Server 2019, vaya al servidor **Standard Edition** o a los grupos de servidores **front-end de Enterprise Edition,** haga clic con el botón secundario en el grupo y, a continuación, haga clic en Editar **propiedades.**
    
8. En **Asociaciones**, active la casilla situada junto a **Grupo de servidores perimetrales asociados (para componentes multimedia)**. 
    
9. En la lista, seleccione el servidor perimetral heredado. 
  
10. Haga clic en **Aceptar** para cerrar la página **Editar propiedades**. 
    
11. En **el Generador de** topologías, seleccione el nodo superior, Skype Empresarial **Server**.
    
12. En el menú **Acción**, haga clic en **Publicar topología** y en **Siguiente**.
    
13. Cuando el **Asistente para publicación** haya finalizado, haga clic en **Finalizar**.
    

