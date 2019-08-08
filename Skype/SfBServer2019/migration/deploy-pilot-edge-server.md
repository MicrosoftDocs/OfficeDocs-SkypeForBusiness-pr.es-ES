---
title: Implementar el servidor perimetral piloto
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: En este tema se destacan las opciones de configuración que debería conocer antes de implementar el servidor perimetral de Skype empresarial Server 2019. Los procesos de implementación y configuración de Skype empresarial Server 2019 son muy similares a los de Skype empresarial Server 2015. Esta sección solo resalta los puntos clave que debe considerar como parte de la implementación de un grupo piloto. Para conocer los pasos detallados, vea implementar el acceso de usuarios externos en Skype empresarial Server 2019 en la documentación de implementación, que describe el proceso de implementación y también proporciona información de configuración para el acceso de usuarios externos.
ms.openlocfilehash: b416ba38646d05f3d10a7d2643c01924fe57020a
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36238391"
---
# <a name="deploy-pilot-edge-server"></a>Implementar el servidor perimetral piloto

En este tema se destacan las opciones de configuración que debe tener en cuenta antes de implementar el servidor perimetral de Skype empresarial Server 2019. Los procesos de implementación y configuración de Skype empresarial Server 2019 son muy similares a los de Skype empresarial Server 2015. Esta sección solo resalta los puntos clave que debe considerar como parte de la implementación de un grupo piloto. <!-- For detailed steps, see 
 [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.  -->
  
Mientras navega por el asistente **definir nuevo grupo de bordes** , revise la configuración de clave que se muestra en los siguientes pasos. Observe que solo se muestran algunas páginas del asistente **definir nuevo grupo de bordes** . 
  
### <a name="to-define-an-edge-pool"></a>Para definir un grupo de límites

1. Inicie sesión en el equipo donde se encuentre instalado el Generador de topologías como miembro del grupo Administradores del dominio y el grupo RTCUniversalServerAdmins.
    
2. Vaya al nodo de Skype empresarial Server 2019. Haga clic con **** el botón secundario en agrupaciones perimetrales y haga clic en **nuevo borde**.
    
     ![Definir el cuadro de diálogo nuevo grupo perimetral](../media/migration_ocs_topo_edgepool_page1.JPG)
  
3. Un grupo de servidores perimetrales puede ser un **grupo de varios equipos** o un **único grupo de equipos**.
    
     ![Definir el cuadro de diálogo FQDN del grupo de bordes](../media/migration_ocs_topo_edgepool_page2.JPG)
  
4. En la página **seleccionar características** , no habilite la Federación ni la Federación XMPP. La Federación y la Federación de XMPP actualmente se enrutan a través del servidor perimetral heredado. Estas características se configurarán en una fase posterior de la migración. 

  
5. Siga completando las siguientes páginas del asistente: **FQDN externos**, **defina la dirección IP interna**y **defina la dirección IP externa**.
    
6. En la página **definir el servidor del próximo salto** , seleccione el director para el próximo salto del grupo de servidores perimetrales heredados. 
    
     ![Definir el cuadro de diálogo siguiente del salto](../media/migration_ocs_topo_edgepool_page7.JPG)
  
7. En la página **asociar grupos de servicios de media o front-end** , no asocie un grupo con este grupo de límites en este momento. El tráfico multimedia externo está enrutado a través del servidor perimetral heredado. Esta configuración se configurará en una fase posterior de la migración. 
    
     ![Cuadro de diálogo asociar grupos front-end](../media/migration_ocs_topo_edgepool_page8.JPG)
  
8. Haga clic en **Finalizar**y, a continuación, **publique** la topología. 
    
9. Siga los pasos que se indican en la documentación de implementación para instalar los archivos en el nuevo servidor perimetral, configurar certificados e iniciar los servicios. 
<!-- [Install Edge Servers for Skype for Business Server 2019](../deployment/deploying-external-user-access/install-edge-servers.md) in -->
    
Es muy importante seguir las directrices de los temas de la documentación de implementación. En esta sección se proporciona una mera información sobre las opciones de configuración al instalar estos roles de servidor. 
<!-- [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) -->
  
Ahora debe tener un servidor perimetral heredado implementado en paralelo con una implementación de servidor perimetral de Skype empresarial Server 2019. Compruebe que las implementaciones se ejecutan correctamente y que se inician los servicios, y puede administrar cada implementación antes de pasar a la siguiente fase. 
  

