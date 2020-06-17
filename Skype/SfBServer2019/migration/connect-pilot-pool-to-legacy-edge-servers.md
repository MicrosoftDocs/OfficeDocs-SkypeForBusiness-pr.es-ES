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
description: Después de implementar Skype empresarial Server 2019, debe configurar una ruta de Federación para el sitio. Para poder usar la ruta federada que usa la instalación heredada, Skype empresarial Server 2019 debe estar configurado para usar esta ruta.
ms.openlocfilehash: 8243ebbf9540587dedd8e4ae3a51e22f9a315728
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753930"
---
# <a name="connect-pilot-pool-to-legacy-edge-servers"></a>Conecte el grupo de servidores piloto a los servidores perimetrales heredados

Después de implementar Skype empresarial Server 2019, debe configurar una ruta de Federación para el sitio. Para poder usar la ruta federada que usa la instalación heredada, Skype empresarial Server 2019 debe estar configurado para usar esta ruta. 
  
Para permitir que el sitio de Skype empresarial Server 2019 use el director y el servidor perimetral de la implementación heredada, use el generador de topologías para asociar el grupo de servidores perimetrales heredados.
  
### <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a>Para asociar el grupo de servidores perimetrales heredados usando el Generador de topologías

1. Abra el Generador de topologías. 
    
2. Seleccione su sitio, que se encuentra justo debajo del nodo **Skype empresarial Server** . 
    
3. En el menú **Acciones**, haga clic en **Editar propiedades**.
    
4. En el panel izquierdo, seleccione **Ruta de federación**.
    
5. En **asignación de ruta de Federación del sitio**, seleccione **Habilitar Federación SIP**y, a continuación, seleccione el director heredado o el servidor perimetral heredado si no aparece ningún director.
  
6. Haga clic en **Aceptar** para cerrar la página **Editar propiedades**. 
    
7. En el generador de topologías, en el nodo Skype empresarial Server 2019, vaya a los grupos de servidores **front-end** **Standard Edition** o Enterprise Edition, haga clic con el botón secundario en el grupo y, a continuación, haga clic en **Editar propiedades**.
    
8. En **Asociaciones**, active la casilla situada junto a **Grupo de servidores perimetrales asociados (para componentes multimedia)**. 
    
9. En la lista, seleccione el servidor perimetral heredado. 
  
10. Haga clic en **Aceptar** para cerrar la página **Editar propiedades**. 
    
11. En el **generador de topologías**, seleccione el nodo de nivel superior, **Skype empresarial Server**.
    
12. En el menú **Acción**, haga clic en **Publicar topología** y en **Siguiente**.
    
13. Cuando el **Asistente para publicación** haya finalizado, haga clic en **Finalizar**.
    

