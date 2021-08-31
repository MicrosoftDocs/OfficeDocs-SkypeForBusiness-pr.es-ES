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
ms.localizationpriority: medium
description: En este tema se resaltan las opciones de configuración que debe tener en cuenta antes de implementar Skype Empresarial Server servidor perimetral de 2019. Los procesos de implementación y configuración de Skype Empresarial Server 2019 son muy similares a Skype Empresarial Server 2015. En esta sección solo se detallan los aspectos clave que hay que considerar al implementar el grupo piloto. Para obtener pasos detallados, vea Deploying external user access in Skype Empresarial Server 2019 en la documentación sobre implementación, que describe el proceso de implementación y también proporciona información de configuración para el acceso de usuarios externos.
ms.openlocfilehash: 39ec659c5099a7be9587c630aa487ddeda1df500
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2021
ms.locfileid: "58728049"
---
# <a name="deploy-pilot-edge-server"></a>Implementar el servidor perimetral piloto

En este tema se resaltan las opciones de configuración que debe tener en cuenta antes de implementar Skype Empresarial Server servidor perimetral de 2019. Los procesos de implementación y configuración de Skype Empresarial Server 2019 son muy similares a Skype Empresarial Server 2015. En esta sección solo se detallan los aspectos clave que hay que considerar al implementar el grupo piloto. <!-- For detailed steps, see 
 [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.  -->
  
Al navegar por el asistente **Definir nuevo grupo de servidores perimetrales**, repase las principales opciones de configuración recogidas en cada paso. Observe que solo se muestran unas cuantas páginas deeste asistente. 
  
### <a name="to-define-an-edge-pool"></a>Para definir un grupo de servidores perimetrales

1. Inicie sesión en el equipo en el que Topology Builder esté instalado como miembro del grupo Admins. del dominio y el grupo RTCUniversalServerAdmins.
    
2. Vaya al nodo Skype Empresarial Server 2019. haga clic con el botón secundario en **Grupos de servidores perimetrales** y en **Nuevo grupo de servidores perimetrales**.
    
     ![Defina el cuadro de diálogo Nuevo grupo de servidores perimetrales.](../media/migration_ocs_topo_edgepool_page1.JPG)
  
3. Un grupo de servidores perimetrales puede ser un **Grupo de varios equipos** o un **Grupo de un solo equipo**.
    
     ![Defina el cuadro de diálogo FQDN del grupo de servidores perimetrales.](../media/migration_ocs_topo_edgepool_page2.JPG)
  
4. En la página **Seleccionar características**, no habilite la federación ni la federación XMPP. La federación y la federación XMPP se enrutan actualmente a través del servidor perimetral heredado. Estas características se configurarán en una fase posterior de la migración. 

  
5. Siga completando las siguientes páginas del asistente: **FQDN externos**, Definir la **dirección IP** interna y Definir la dirección **IP externa**.
    
6. En la **página Definir el servidor del** próximo salto, seleccione director para el próximo salto del grupo perimetral heredado. 
    
     ![Defina el cuadro de diálogo Siguiente salto.](../media/migration_ocs_topo_edgepool_page7.JPG)
  
7. En la página Asociar grupos de servidores **front-end** o de mediación, no asocie un grupo con este grupo de servidores perimetrales en este momento. El tráfico de medios externos se enruta actualmente a través del servidor perimetral heredado. Definiremos esta configuración en una fase posterior de la migración. 
    
     ![Cuadro de diálogo Asociar grupos de servidores front-end.](../media/migration_ocs_topo_edgepool_page8.JPG)
  
8. Haga clic en **Finalizar** y después en **Publicar** para publicar la topología. 
    
9. Siga los pasos de la documentación de implementación para instalar los archivos en el nuevo servidor perimetral, configurar certificados e iniciar los servicios. 
<!-- [Install Edge Servers for Skype for Business Server 2019](../deployment/deploying-external-user-access/install-edge-servers.md) in -->
    
Es muy importante que siga las directrices de los temas de la documentación de implementación. En esta sección solo se ha proporcionado cierta orientación sobre las opciones de configuración al instalar estos roles de servidor. 
<!-- [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) -->
  
Ahora debe tener un servidor perimetral heredado implementado en paralelo con una Skype Empresarial Server de servidor perimetral de 2019. Antes de pasar a la siguiente fase, confirme que ambas implementaciones funcionan correctamente, que los servicios se han iniciado y que puede administrar cada una de las implementaciones. 
  

