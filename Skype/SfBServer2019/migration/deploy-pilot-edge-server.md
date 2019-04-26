---
title: Implementar el servidor perimetral piloto
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: En este tema resalta las opciones de configuración que deben tener en cuenta antes de implementar su Skype para servidor perimetral de Business Server 2019. Los procesos de implementación y configuración de Skype para Business Server 2019 son muy similares a Skype para Business Server 2015. Esta sección resalta sólo puntos clave que debe tener en cuenta como parte de la implementación del grupo piloto. Para obtener instrucciones detalladas, vea implementar el acceso de usuarios externos en Skype para Business Server 2019 en la documentación de implementación, que se describe el proceso de implementación y también se proporciona información de configuración para el acceso de usuarios externos.
ms.openlocfilehash: 5b755d0ba8802c47a176cb3375a87b6523f35fad
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32239858"
---
# <a name="deploy-pilot-edge-server"></a>Implementar el servidor perimetral piloto

En este tema resalta las opciones de configuración que deben tener en cuenta antes de implementar su Skype para servidor perimetral de Business Server 2019. Los procesos de implementación y configuración de Skype para Business Server 2019 son muy similares a Skype para Business Server 2015. Esta sección resalta sólo puntos clave que debe tener en cuenta como parte de la implementación del grupo piloto. <!-- For detailed steps, see 
 [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.  -->
  
Al desplazarse por el Asistente para **Definir nuevo grupo perimetral** , revise las opciones de configuración de clave que se muestra en los siguientes pasos. Tenga en cuenta que se muestran sólo algunas páginas del Asistente para **Definir nuevo grupo de servidores de borde** . 
  
### <a name="to-define-an-edge-pool"></a>Para definir un grupo de servidores perimetrales

1. Inicie sesión en el equipo donde se encuentre instalado el Generador de topologías como miembro del grupo Administradores del dominio y el grupo RTCUniversalServerAdmins.
    
2. Navegue hasta el Skype para Business Server 2019 nodo. Haga clic en **grupos de servidores perimetrales**y haga clic en **grupo de servidores perimetrales de nuevo**.
    
     ![Definir el cuadro de diálogo nuevo grupo de servidores perimetrales](../media/migration_ocs_topo_edgepool_page1.JPG)
  
3. Un grupo de servidores perimetrales puede ser un **grupo de varios equipos** o **grupo de servidores de un solo equipo**.
    
     ![Definir el cuadro de diálogo de FQDN del grupo de servidores perimetrales](../media/migration_ocs_topo_edgepool_page2.JPG)
  
4. En la página **Seleccionar características** , no habilitar la federación o la federación XMPP. Federación y la federación XMPP se ambos actualmente enrutan a través del servidor perimetral heredado. Estas características se configurarán en una fase posterior de la migración. 

  
5. Siga completando las siguientes páginas del asistente: **FQDN externos**, **definir la dirección IP interna**y **definir la dirección IP externa**.
    
6. En la página **definir el servidor del próximo salto** , seleccione el Director para el próximo salto del grupo de servidores perimetrales heredado. 
    
     ![Definir el cuadro de diálogo próximo salto](../media/migration_ocs_topo_edgepool_page7.JPG)
  
7. En la página **asociar Front-End o grupos de servidores de mediación** , no se asocia un grupo de servidores con este grupo de servidores perimetrales en este momento. Actualmente se enruta el tráfico de medios externos a través del servidor perimetral heredado. Esta configuración se configurarán en una fase posterior de la migración. 
    
     ![Asociar el cuadro de diálogo de grupos de servidores Front-End](../media/migration_ocs_topo_edgepool_page8.JPG)
  
8. Haga clic en **Finalizar**y, a continuación, en **Publicar** la topología. 
    
9. Siga los pasos descritos en la documentación de implementación para instalar los archivos en el nuevo servidor perimetral, configurar los certificados e iniciar los servicios. 
<!-- [Install Edge Servers for Skype for Business Server 2019](../deployment/deploying-external-user-access/install-edge-servers.md) in -->
    
Es muy importante que siga las instrucciones que aparecen en los temas de la documentación de implementación. En esta sección se proporciona simplemente algunas instrucciones en Opciones de configuración al instalar estas funciones de servidor. 
<!-- [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) -->
  
Ahora debería tener un servidor perimetral heredado implementado en paralelo con un Skype para la implementación del servidor perimetral de Business Server 2019. Compruebe que tanto las implementaciones se ejecutan correctamente, se inician los servicios, y puede administrar cada implementación antes de pasar a la siguiente fase. 
  

