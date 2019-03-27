---
title: Comprobación del entorno heredado
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Antes de implementar Skype para Business Server 2019 en un estado de coexistencia, debe comprobar que se han configurado e iniciado servicios heredados. Es importante identificar servicios clave y características que existen en el entorno heredado, antes de implementar un Skype para el grupo piloto Business Server 2019. Antes de implementar Microsoft Skype para Business Server 2019 XMPP en un estado de coexistencia con una implementación de XMPP heredado, debe comprobar los servicios XMPP heredados se han configurado y se ha iniciado e identificar qué es la configuración de XMPP heredada de socio federado compatibilidad con.
ms.openlocfilehash: 0f9812efe966d72eba1eeead9d74780f2ba16661
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30887353"
---
# <a name="verify-the-legacy-environment"></a>Comprobación del entorno heredado

Antes de implementar Skype para Business Server 2019 en un estado de coexistencia, debe comprobar que se han configurado e iniciado servicios heredados. Es importante identificar servicios clave y características que existen en el entorno heredado antes de implementar un Skype para el grupo piloto Business Server 2019. Antes de implementar Microsoft Skype para Business Server 2019 XMPP en un estado de coexistencia con una implementación de XMPP heredado, debe comprobar que se han configurado e iniciado los servicios XMPP heredados e identificar el socio XMPP heredado federado es compatible con la configuración. Comprobar la implementación heredada implica lo siguiente:
  
- Comprobar que se han iniciado los servicios heredados
    
- Revisar la topología y los usuarios
    
- Comprobar la federación y la configuración del servidor perimetral
    
- Comprobar los servicios de XMPP y los socios federados
    
## <a name="verify-that-legacy-services-are-started"></a>Compruebe que se han iniciado los servicios heredados

1. En el servidor front-heredado de End, navegue hasta el applet herramientas Administrativas\servicios.
    
2. Compruebe que los siguientes servicios se están ejecutando en el servidor Front-End:
    
     ![Lista de servicios que se ejecutan en el servidor Front-End](../media/migration_lyncserver_config_w14_services.jpg)
  
## <a name="review-the-legacy-topology-in-skype-for-business-server-control-panel"></a>Revise la topología heredada en Skype para el Panel de Control de servidor empresarial

1. Inicie sesión en el servidor front-end con una cuenta que sea miembro del grupo RTCUniversalServerAdmins o miembro del rol administrativo CsAdministrator o CsUserAdministrator.
    
2. Abra el Skype para el Panel de Control de servidor empresarial.
    
3. Seleccione la **topología**. Compruebe que se enumeran los diversos servidores en su implementación heredada.
    
     ![Página de topología del Panel de control](../media/migration_lyncserver_2010_topology.JPG)
  
## <a name="review-legacy-users-in-skype-for-business-server-control-panel"></a>Revise los usuarios heredados en Skype para el Panel de Control de servidor empresarial

1. Abra el Skype para el Panel de Control de servidor empresarial.
    
2. Seleccione **los usuarios**y, a continuación, haga clic en **Buscar**.
    
3. Compruebe que la columna **Grupo de registradores** apunta al grupo de servidores heredado para cada usuario de la lista. 
    
     ![Panel de control de lista de usuarios](../media/migration_lyncserver_2010_allusers.JPG)
  
## <a name="verify-legacy-edge-and-federation-settings"></a>Comprobar la configuración heredada de borde y federación

1. Iniciar el generador de topología.
    
2. Seleccione **Descargar topología de la implementación existente**.
    
3. Elija un nombre de archivo y guarde la topología con el tipo de archivo .tbxml predeterminado.
    
4. Expanda el nodo de instalaciones heredadas para revelar los diversos roles de servidor de la implementación.
    
5. Seleccione el nodo del sitio y compruebe que se establece un valor de **asignación de ruta de federación de sitio** . 
    
     ![Generador de topologías, ruta de federación del sitio](../media/migration_lyncserver_w14_federation.jpg)
  
6. Seleccione el grupo de servidores de front-end de un servidor Standard Edition o Enterprise Edition. Determinar si se ha configurado un grupo de servidores perimetrales para los medios por debajo de **las asociaciones**. 
    
     ![Generador de topología que muestra los servidores y grupos de servidores](../media/migration_lyncserver_w14_edgepool_media.jpg)
  
7. Seleccione el grupo de servidores perimetrales e identifique si un grupo del próximo salto se ha configurado bajo **selección de próximo salto**.
    
     ![Generador de topologías, selección de próximo salto](../media/migration_lyncserver_w14_nexthop.jpg)
  
## <a name="verify-legacy-xmpp-federated-partner-configuration"></a>Compruebe el socio federado de XMPP heredado configuración

1. Desde el servidor XMPP heredado, navegue hasta el applet herramientas Administrativas\servicios.
    
2. Compruebe que se ha iniciado el servicio de puerta de enlace de XMPP de Office Communications Server. 
    
     ![Servicio de puerta de enlace XMPP de Office Communications Server](../media/migration_lyncserver_15_xmpp_legacyservicesstarted.JPG)
  

