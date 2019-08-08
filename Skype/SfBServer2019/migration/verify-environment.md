---
title: Comprobar el entorno heredado
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Antes de implementar Skype empresarial Server 2019 en un estado de coexistencia, debe comprobar que los servicios heredados se han configurado e iniciado. Es importante identificar los servicios clave y las características que existen en su entorno heredado antes de implementar un grupo de pruebas piloto de Skype empresarial Server 2019. Antes de implementar Microsoft Skype empresarial Server 2019 XMPP en un estado de coexistencia con una implementación de XMPP heredada, debe comprobar que los servicios de XMPP heredado se han configurado e iniciado, e identificar a qué socio federado se encuentra la configuración de XMPP heredada. dando.
ms.openlocfilehash: 4c648dbbadeca50c12eb6047958ef63066ed7a3a
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243778"
---
# <a name="verify-the-legacy-environment"></a>Comprobar el entorno heredado

Antes de implementar Skype empresarial Server 2019 en un estado de coexistencia, debe comprobar que los servicios heredados se han configurado e iniciado. Es importante identificar los servicios clave y las características que existen en el entorno heredado antes de implementar un grupo de pruebas piloto de Skype empresarial Server 2019. Antes de implementar Microsoft Skype empresarial Server 2019 XMPP en un estado de coexistencia con una implementación de XMPP heredada, debe comprobar que los servicios de XMPP heredado se han configurado e iniciado, e identificar a qué socio federado el XMPP heredado. es compatible con la configuración. La comprobación de la implementación heredada conlleva lo siguiente:
  
- Comprobar que los servicios heredados se han iniciado
    
- Revisar la topología y los usuarios
    
- Comprobar la configuración del servidor perimetral y la Federación
    
- Verificación de los servicios XMPP y los socios federados
    
## <a name="verify-that-legacy-services-are-started"></a>Comprobar que los servicios heredados se han iniciado

1. Desde el servidor front-end heredado, navegue hasta el applet Tools\Services administrativo.
    
2. Compruebe que se están ejecutando los siguientes servicios en el servidor front-end:
    
     ![Lista de servicios que se ejecutan en el servidor front-end](../media/migration_lyncserver_config_w14_services.jpg)
  
## <a name="review-the-legacy-topology-in-skype-for-business-server-control-panel"></a>Revisar la topología heredada en el panel de control de Skype empresarial Server

1. Inicie sesión en el servidor front-end con una cuenta que sea miembro del grupo RTCUniversalServerAdmins o miembro del rol administrativo CsAdministrator o CsUserAdministrator.
    
2. Abra el panel de control de Skype empresarial Server.
    
3. Seleccione **topología**. Compruebe que se muestran los diversos servidores de su implementación heredada.
    
     ![Página de topología del panel de control](../media/migration_lyncserver_2010_topology.JPG)
  
## <a name="review-legacy-users-in-skype-for-business-server-control-panel"></a>Revisar los usuarios heredados en el panel de control de Skype empresarial Server

1. Abra el panel de control de Skype empresarial Server.
    
2. Seleccione **usuarios**y, a continuación, haga clic en **Buscar**.
    
3. Compruebe que la columna **registrar grupo** apunta a la agrupación heredada para cada usuario de la lista. 
    
     ![Panel de control con una lista de usuarios](../media/migration_lyncserver_2010_allusers.JPG)
  
## <a name="verify-legacy-edge-and-federation-settings"></a>Comprobar la configuración de la Federación y los límites heredados

1. Iniciar el generador de topología.
    
2. Seleccione **Descargar topología de la implementación existente**.
    
3. Elija un nombre de archivo y guarde la topología con el tipo de archivo default. tbxml.
    
4. Expanda el nodo instalaciones heredadas para mostrar los distintos roles de servidor en la implementación.
    
5. Seleccione el nodo de sitio y compruebe que se ha establecido un valor de **asignación de enrutamiento de Federación de sitios** . 
    
     ![Generador de topologías, ruta de Federación de sitios](../media/migration_lyncserver_w14_federation.jpg)
  
6. Seleccione el servidor Standard Edition o el grupo de servidores front-end Enterprise Edition. Determine si un grupo de servidores perimetrales se ha configurado para los medios por debajo de las **asociaciones**. 
    
     ![Generador de topología que muestra servidores y pools](../media/migration_lyncserver_w14_edgepool_media.jpg)
  
7. Seleccione el grupo de bordes y identifique si un grupo de saltos siguiente está configurado por debajo de la **selección de próximos saltos**.
    
     ![Generador de topologías, selección del próximo salto](../media/migration_lyncserver_w14_nexthop.jpg)
  
## <a name="verify-legacy-xmpp-federated-partner-configuration"></a>Comprobar la configuración heredada del socio XMPP federado

1. Desde el servidor XMPP heredado, vaya al applet Tools\Services administrativo.
    
2. Compruebe que se ha iniciado el servicio de puerta de enlace XMPP de Office Communications Server. 
    
     ![Servicio de puerta de enlace XMPP de Office Communications Server](../media/migration_lyncserver_15_xmpp_legacyservicesstarted.JPG)
  

