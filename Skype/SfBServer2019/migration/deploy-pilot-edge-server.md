---
title: Implementar el servidor perimetral piloto
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
description: En este tema se destacan las opciones de configuración que debe tener en cuenta antes de implementar el servidor perimetral de Skype empresarial Server 2019. Los procesos de implementación y configuración de Skype empresarial Server 2019 son muy similares a los de Skype empresarial Server 2015. En esta sección solo se detallan los aspectos clave que hay que considerar al implementar el grupo piloto. Para obtener los pasos detallados, consulte Deploying external User Access in Skype for Business Server 2019 en la documentación sobre implementación, que describe el proceso de implementación y también proporciona información de configuración para el acceso de usuarios externos.
ms.openlocfilehash: 00c371b917f2649dba9011fbbce6162b153822d1
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752872"
---
# <a name="deploy-pilot-edge-server"></a>Implementar el servidor perimetral piloto

En este tema se destacan las opciones de configuración que debe tener en cuenta antes de implementar el servidor perimetral de Skype empresarial Server 2019. Los procesos de implementación y configuración de Skype empresarial Server 2019 son muy similares a los de Skype empresarial Server 2015. En esta sección solo se detallan los aspectos clave que hay que considerar al implementar el grupo piloto. <!-- For detailed steps, see 
 [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.  -->
  
Al navegar por el asistente **Definir nuevo grupo de servidores perimetrales**, repase las principales opciones de configuración recogidas en cada paso. Observe que solo se muestran unas cuantas páginas de**** este asistente. 
  
### <a name="to-define-an-edge-pool"></a>Para definir un grupo de servidores perimetrales

1. Inicie sesión en el equipo en el que Topology Builder esté instalado como miembro del grupo Admins. del dominio y el grupo RTCUniversalServerAdmins.
    
2. Navegue hasta el nodo Skype empresarial Server 2019. haga clic con el botón secundario en **Grupos de servidores perimetrales** y en **Nuevo grupo de servidores perimetrales**.
    
     ![Definir el cuadro de diálogo nuevo grupo de servidores perimetrales](../media/migration_ocs_topo_edgepool_page1.JPG)
  
3. Un grupo de servidores perimetrales puede ser un **Grupo de varios equipos** o un **Grupo de un solo equipo**.
    
     ![Cuadro de diálogo definir el FQDN del grupo de servidores perimetrales](../media/migration_ocs_topo_edgepool_page2.JPG)
  
4. En la página **Seleccionar características**, no habilite la federación ni la federación XMPP. La Federación y la Federación de XMPP se enrutan actualmente a través del servidor perimetral heredado. Estas características se configurarán en una fase posterior de la migración. 

  
5. Siga completando las siguientes páginas del asistente: **FQDN externos**, **definir la dirección IP interna**y **definir la dirección IP externa**.
    
6. En la página **definir el servidor del próximo salto** , seleccione el director para el próximo salto del grupo de servidores perimetrales heredados. 
    
     ![Cuadro de diálogo definir el próximo salto](../media/migration_ocs_topo_edgepool_page7.JPG)
  
7. En la página **asociar grupos de servidores front-end o de mediación** , no asocie un grupo de servidores con este grupo de servidores perimetrales en este momento. El tráfico multimedia externo se enruta actualmente a través del servidor perimetral heredado. Definiremos esta configuración en una fase posterior de la migración. 
    
     ![Cuadro de diálogo asociar grupos de servidores front-end](../media/migration_ocs_topo_edgepool_page8.JPG)
  
8. Haga clic en **Finalizar** y después en **Publicar** para publicar la topología. 
    
9. Siga los pasos de la documentación de implementación para instalar los archivos en el nuevo servidor perimetral, configurar los certificados e iniciar los servicios. 
<!-- [Install Edge Servers for Skype for Business Server 2019](../deployment/deploying-external-user-access/install-edge-servers.md) in -->
    
Es muy importante que siga las instrucciones de los temas de la documentación de implementación. En esta sección solo se ha proporcionado cierta orientación sobre las opciones de configuración al instalar estos roles de servidor. 
<!-- [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) -->
  
Ahora debe tener un servidor perimetral heredado implementado en paralelo con una implementación de servidor perimetral de Skype empresarial Server 2019. Antes de pasar a la siguiente fase, confirme que ambas implementaciones funcionan correctamente, que los servicios se han iniciado y que puede administrar cada una de las implementaciones. 
  

