---
title: Conectar el grupo piloto a servidores perimetrales heredados
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Después de la implementación de Skype para 2019 de servidor empresarial, debe configurar una ruta de federación para su sitio. Para poder usar la ruta federada que está siendo utilizada por la instalación heredada, Skype para Business Server 2019 debe configurarse para utilizar esta ruta.
ms.openlocfilehash: 6766034cf54fd867c9b270324cb1db8ad2d644d5
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "25030570"
---
# <a name="connect-pilot-pool-to-legacy-edge-servers"></a>Conectar el grupo piloto a servidores perimetrales heredados

Después de la implementación de Skype para 2019 de servidor empresarial, debe configurar una ruta de federación para su sitio. Para poder usar la ruta federada que está siendo utilizada por la instalación heredada, Skype para Business Server 2019 debe configurarse para utilizar esta ruta. 
  
Para habilitar la Skype para Business Server 2019 sitios usar el Director y el servidor perimetral de la implementación heredada, use el generador de topología para asociar el grupo de servidores perimetrales heredado.
  
### <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a>Para asociar el grupo de servidores perimetrales heredado mediante el generador de topología

1. Abra el generador de topología. 
    
2. Seleccione su sitio, que se encuentra justo debajo del nodo de **Skype para Business Server** . 
    
3. En el menú **acciones** , haga clic en **Editar propiedades**.
    
4. En el panel izquierdo, seleccione **ruta de federación**.
    
5. En **asignación de ruta de federación de sitio**, seleccione **Habilitar federación SIP**y, a continuación, seleccione el Director heredado o el servidor perimetral heredado si se muestra ningún Director.
  
6. Haga clic en **Aceptar** para cerrar la página **Editar propiedades** . 
    
7. En el generador, bajo el Skype para Business Server 2019 nodo, desplácese hasta el **servidor Standard Edition** o **grupos de servidores Front-End de Enterprise Edition**, (ratón) en el grupo de servidores y, a continuación, haga clic en **Editar propiedades**.
    
8. En **asociaciones**, active la casilla de verificación situada junto a **grupo de servidores perimetrales asociados (para componentes multimedia)**. 
    
9. En la lista, seleccione el servidor perimetral heredado. 
  
10. Haga clic en **Aceptar** para cerrar la página **Editar propiedades** . 
    
11. En **El generador de topología**, seleccione el nodo de nivel superior, **Skype para Business Server**.
    
12. En el menú **acción** , haga clic en **Publicar topología**y, a continuación, haga clic en **siguiente**.
    
13. Cuando se complete el **Asistente para la publicación** , haga clic en **Finalizar**.
    

