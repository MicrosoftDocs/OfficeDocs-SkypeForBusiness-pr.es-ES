---
title: Comprobar el entorno heredado
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
description: Antes de implementar Skype Empresarial Server 2019 en un estado de coexistencia, debe comprobar que los servicios heredados se han configurado e iniciado. Es importante identificar los servicios y características clave que existen en su entorno heredado, antes de implementar un grupo piloto de Skype Empresarial Server 2019. Antes de implementar XMPP de Microsoft Skype Empresarial Server 2019 en un estado de coexistencia con una implementación XMPP heredada, debe comprobar que los servicios XMPP heredados se han configurado e iniciado, e identificar qué socio federado admite la configuración XMPP heredada.
ms.openlocfilehash: 2600cc2e6f4fac258431bcf505af10d1f8c212fe
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751682"
---
# <a name="verify-the-legacy-environment"></a>Comprobar el entorno heredado

Antes de implementar Skype Empresarial Server 2019 en un estado de coexistencia, debe comprobar que los servicios heredados se han configurado e iniciado. Es importante identificar los servicios y características clave que existen en su entorno heredado antes de implementar un grupo piloto de Skype Empresarial Server 2019. Antes de implementar XMPP de Microsoft Skype Empresarial Server 2019 en un estado de coexistencia con una implementación XMPP heredada, debe comprobar que los servicios XMPP heredados se han configurado e iniciado, e identificar qué socio federado admite la configuración XMPP heredada. La comprobación de la implementación heredada implica lo siguiente:
  
- Comprobación de que se han iniciado los servicios heredados
    
- Revisión de la topología y los usuarios
    
- Comprobación de la configuración de federación y servidor perimetral
    
- Comprobación de servicios XMPP y socios federados
    
## <a name="verify-that-legacy-services-are-started"></a>Comprobar que se han iniciado los servicios heredados

1. Desde el servidor front-end heredado, vaya al applet Herramientas administrativas\Servicios.
    
2. Compruebe que los servicios siguientes se están ejecutando en el servidor front-end:
    
     ![Lista de servicios que se ejecutan en el servidor front-end](../media/migration_lyncserver_config_w14_services.jpg)
  
## <a name="review-the-legacy-topology-in-skype-for-business-server-control-panel"></a>Revisar la topología heredada en el Panel de control de Skype Empresarial Server

1. Inicie sesión en el servidor front-end con una cuenta que sea miembro del grupo RTCUniversalServerAdmins, o del rol administrativo CsAdministrator o CsUserAdministrator.
    
2. Abra el Panel de control de Skype Empresarial Server.
    
3. Seleccione **Topología**. Compruebe que se muestran los distintos servidores de la implementación heredada.
    
     ![Página de topología del Panel de control](../media/migration_lyncserver_2010_topology.JPG)
  
## <a name="review-legacy-users-in-skype-for-business-server-control-panel"></a>Revisar los usuarios heredados en el Panel de control de Skype Empresarial Server

1. Abra el Panel de control de Skype Empresarial Server.
    
2. Seleccione **Usuarios y,** a continuación, haga clic **en Buscar**.
    
3. Compruebe que la columna **Grupo de registradores** apunta al grupo heredado para cada usuario enumerado. 
    
     ![Lista de usuarios del Panel de control](../media/migration_lyncserver_2010_allusers.JPG)
  
## <a name="verify-legacy-edge-and-federation-settings"></a>Comprobar la configuración de federación y perimetral heredada

1. Inicie el Generador de topologías.
    
2. Seleccione **Descargar una topología desde una implementación existente**.
    
3. Elija un nombre de archivo y guarde la topología con el tipo de archivo .tbxml predeterminado.
    
4. Expanda el nodo de instalación heredado para mostrar los distintos roles de servidor de la implementación.
    
5. Seleccione el nodo de sitio y compruebe que se ha establecido un valor de asignación de ruta **de federación** de sitio. 
    
     ![Generador de topologías, ruta de federación de sitios](../media/migration_lyncserver_w14_federation.jpg)
  
6. Seleccione el servidor Standard Edition o el grupo de servidores front-end Enterprise Edition. Determinar si se ha configurado un grupo de servidores perimetrales para los medios debajo de **Asociaciones.** 
    
     ![Generador de topologías que muestra servidores y grupos de servidores](../media/migration_lyncserver_w14_edgepool_media.jpg)
  
7. Seleccione el grupo de servidores perimetrales e identifique si un grupo de servidores del próximo salto está configurado debajo **de la selección del próximo salto.**
    
     ![Generador de topologías, selección del próximo salto](../media/migration_lyncserver_w14_nexthop.jpg)
  
## <a name="verify-legacy-xmpp-federated-partner-configuration"></a>Comprobar la configuración de socios federados XMPP heredados

1. Desde el servidor XMPP heredado, desplácese al appletAdministrative Tools\Services.
    
2. Compruebe que se haya iniciado el servicio de puerta de enlace XMPP de Office Communications Server. 
    
     ![Servicio de puerta de enlace XMPP de Office Communications Server](../media/migration_lyncserver_15_xmpp_legacyservicesstarted.JPG)
  

