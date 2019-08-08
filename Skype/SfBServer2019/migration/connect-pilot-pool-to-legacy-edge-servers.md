---
title: Conecte el grupo de servidores piloto a los servidores perimetrales heredados
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Después de implementar Skype empresarial Server 2019, debe configurar una ruta de Federación para el sitio. Para poder usar la ruta federada que usa la instalación heredada, Skype empresarial Server 2019 debe estar configurado para usar esta ruta.
ms.openlocfilehash: 7a5a65e1488d5a119e3d11affbbaa9995a06626e
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239227"
---
# <a name="connect-pilot-pool-to-legacy-edge-servers"></a>Conecte el grupo de servidores piloto a los servidores perimetrales heredados

Después de implementar Skype empresarial Server 2019, debe configurar una ruta de Federación para el sitio. Para poder usar la ruta federada que usa la instalación heredada, Skype empresarial Server 2019 debe estar configurado para usar esta ruta. 
  
Para permitir que el sitio de Skype empresarial Server 2019 use el director y el servidor perimetral de la implementación heredada, use el generador de topología para asociar el grupo perimetral heredado.
  
### <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a>Para asociar el grupo perimetral heredado mediante el generador de topología

1. Abra el generador de topologías. 
    
2. Seleccione su sitio, que se encuentra directamente debajo del nodo **de Skype empresarial Server** . 
    
3. En el menú **acciones** , haga clic en **Editar propiedades**.
    
4. En el panel de la izquierda, seleccione **ruta de Federación**.
    
5. En **asignación**de la ruta de Federación de sitios, seleccione **Habilitar Federación SIP**y, a continuación, seleccione el director heredado o el servidor perimetral heredado si no se muestra ningún director.
  
6. Haga clic en **Aceptar** para cerrar la página **Editar propiedades** . 
    
7. En el generador de topologías, en el nodo de Skype empresarial Server 2019, vaya a los grupos de servidores **Standard Edition** o **Enterprise Edition**, haga clic con el botón secundario en el grupo y, a continuación, haga clic en **Editar propiedades**.
    
8. En **asociaciones**, active la casilla situada junto a **asociar grupo perimetral (para componentes multimedia)**. 
    
9. En la lista, seleccione el servidor perimetral heredado. 
  
10. Haga clic en **Aceptar** para cerrar la página **Editar propiedades** . 
    
11. En el **generador**de topologías, seleccione el nodo de nivel superior, **Skype empresarial Server**.
    
12. En el menú **acción** , haga clic en **publicar topología**y, a continuación, haga clic en **siguiente**.
    
13. Cuando finalice el **Asistente para la publicación** , haga clic en **Finalizar**.
    

