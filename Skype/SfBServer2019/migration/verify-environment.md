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
description: Antes de implementar Skype empresarial Server 2019 en un estado de coexistencia, debe comprobar que los servicios heredados se han configurado e iniciado. Es importante identificar los servicios y características clave que existen en el entorno heredado antes de implementar un grupo piloto de Skype empresarial Server 2019. Antes de implementar Microsoft Skype empresarial Server 2019 XMPP en un estado de coexistencia con una implementación de XMPP heredada, debe comprobar que los servicios de XMPP heredado se hayan configurado e iniciado y que identifiquen qué socio federado admite la configuración de XMPP heredado.
ms.openlocfilehash: 2600cc2e6f4fac258431bcf505af10d1f8c212fe
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751682"
---
# <a name="verify-the-legacy-environment"></a>Comprobar el entorno heredado

Antes de implementar Skype empresarial Server 2019 en un estado de coexistencia, debe comprobar que los servicios heredados se han configurado e iniciado. Es importante identificar los servicios y características clave que existen en el entorno heredado antes de implementar un grupo piloto de Skype empresarial Server 2019. Antes de implementar Microsoft Skype empresarial Server 2019 XMPP en un estado de coexistencia con una implementación de XMPP heredada, debe comprobar que los servicios de XMPP heredado se han configurado e iniciado, e identificar qué socio federado es compatible con la configuración de XMPP heredado. La comprobación de la implementación heredada supone lo siguiente:
  
- Comprobar que se han iniciado los servicios heredados
    
- Revisión de la topología y los usuarios
    
- Comprobación de la configuración de la Federación y el servidor perimetral
    
- Comprobación de los servicios XMPP y socios federados
    
## <a name="verify-that-legacy-services-are-started"></a>Comprobar que se han iniciado los servicios heredados

1. Desde el servidor front-end heredado, navegue hasta el applet herramientas administrativo.
    
2. Compruebe que los servicios siguientes se están ejecutando en el servidor front-end:
    
     ![Lista de servicios que se ejecutan en el servidor front-end](../media/migration_lyncserver_config_w14_services.jpg)
  
## <a name="review-the-legacy-topology-in-skype-for-business-server-control-panel"></a>Revisión de la topología heredada en el panel de control de Skype empresarial Server

1. Inicie sesión en el servidor front-end con una cuenta que sea miembro del grupo RTCUniversalServerAdmins, o del rol administrativo CsAdministrator o CsUserAdministrator.
    
2. Abra el panel de control de Skype empresarial Server.
    
3. Seleccione **Topología**. Compruebe que se muestran los diversos servidores de la implementación heredada.
    
     ![Página de topología del panel de control](../media/migration_lyncserver_2010_topology.JPG)
  
## <a name="review-legacy-users-in-skype-for-business-server-control-panel"></a>Revisar usuarios heredados en el panel de control de Skype empresarial Server

1. Abra el panel de control de Skype empresarial Server.
    
2. Seleccione **usuarios**y, a continuación, haga clic en **Buscar**.
    
3. Compruebe que la columna **grupo de registrador** apunta al grupo heredado para cada usuario enumerado. 
    
     ![Panel de control, enumerar usuarios](../media/migration_lyncserver_2010_allusers.JPG)
  
## <a name="verify-legacy-edge-and-federation-settings"></a>Comprobar la configuración de la Federación y el servidor perimetral heredados

1. Inicie el Generador de topologías.
    
2. Seleccione **Descargar una topología desde una implementación existente**.
    
3. Elija un nombre de archivo y guarde la topología con el tipo de archivo default. tbxml.
    
4. Expanda el nodo instalaciones heredadas para mostrar los distintos roles de servidor en la implementación.
    
5. Seleccione el nodo de sitio y compruebe que se haya establecido un valor de **asignación de ruta de Federación de sitio** . 
    
     ![Generador de topologías, ruta de Federación del sitio](../media/migration_lyncserver_w14_federation.jpg)
  
6. Seleccione el servidor Standard Edition o el grupo de servidores front-end Enterprise Edition. Determinar si un grupo de servidores perimetrales se ha configurado para los medios por debajo de las **asociaciones**. 
    
     ![Generador de topologías que muestra servidores y grupos de servidores](../media/migration_lyncserver_w14_edgepool_media.jpg)
  
7. Seleccione el grupo de servidores perimetrales e identifique si un grupo de servidores de próximo salto se configura por debajo de la selección de próximo **salto**.
    
     ![Generador de topologías, selección de próximo salto](../media/migration_lyncserver_w14_nexthop.jpg)
  
## <a name="verify-legacy-xmpp-federated-partner-configuration"></a>Comprobar la configuración del socio federado de XMPP heredado

1. Desde el servidor XMPP heredado, desplácese al appletAdministrative Tools\Services.
    
2. Compruebe que se haya iniciado el servicio de puerta de enlace XMPP de Office Communications Server. 
    
     ![Servicio de puerta de enlace XMPP de Office Communications Server](../media/migration_lyncserver_15_xmpp_legacyservicesstarted.JPG)
  

