---
title: Definición de troncos adicionales en el generador de Skype para Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e68b8377-50a2-452a-bf5c-910929e34236
description: 'Resumen: Obtenga información sobre cómo definir un tronco adicional entre un servidor de mediación y una puerta de enlace, del mismo nivel en el generador de Skype para Business Server.'
ms.openlocfilehash: 6099f0542634b19bcee989e985f5a8829749daef
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23883942"
---
# <a name="define-additional-trunks-in-topology-builder-in-skype-for-business-server"></a>Definición de troncos adicionales en el generador de Skype para Business Server
 
**Resumen:** Obtenga información sobre cómo definir un tronco adicional entre un servidor de mediación y una puerta de enlace, del mismo nivel en el generador de Skype para Business Server.
  
Siga estos pasos para definir un tronco adicional a la que se puede asociar a un par con un servidor de mediación. Un par proporciona a los usuarios habilitados para Enterprise Voice con conectividad a la red telefónica pública conmutada (RTC). Un par puede ser una puerta de enlace RTC, un IP-PBX o un controlador de borde de sesión (SBC) para un proveedor de servicios de telefonía por Internet (ITSP).
  
Un tronco es una conexión lógica entre un servidor de mediación y una puerta de enlace.
  
> [!NOTE]
> En este tema se da por supuesto que tienen el programa de instalación de una puerta de enlace RTC y tronco raíz con al menos un independientes o combinados servidor de mediación o grupo de servidores tal como se describe en [definir una puerta de enlace en el generador de Skype para Business Server](define-a-gateway.md) en la documentación de implementación.
  
### <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a>Para definir un tronco adicional entre un servidor de mediación y un par de puerta de enlace

1. Inicie el generador: Haga clic en **Inicio**, haga clic en **Todos los programas**, haga clic en **Skype para Business Server 2015**y, a continuación, haga clic en **Skype para Business Server 2015Topology Builder**.
    
2. En Skype para Business Server, el nombre del sitio, **Componentes compartidos**, haga clic en el nodo **troncos** y, a continuación, haga clic en **Nuevo tronco**.
    3. En **Definir nuevo tronco**, escriba un nombre descriptivo para identificar con exclusividad el tronco. Dos troncos no pueden tener el mismo nombre.
    
    > [!NOTE]
    > Si especifica seguridad de capa de transporte (TLS) como el tipo de transporte, debe especificar el FQDN en lugar de la dirección IP del par del servidor de mediación. 
  
4. En **Puerta de enlace PSTN asociada**, seleccione la puerta de enlace de mismo nivel PSTN para asociarla a este tronco.
    5. En **Puerto de escucha para puerta de enlace RTC**, escriba el puerto de escucha que el par (puerta de enlace RTC, IP-PBX o SBC) recibirá mensajes SIP desde el servidor de mediación es que se asociará con este tronco. Los puertos de mismo nivel habituales son 5066 para el protocolo de control de transmisiones (TCP) y 5067 para la seguridad de la capa de transporte (TLS). Los puertos de la aplicación de sucursal con funciones de supervivencia predeterminados son 5081 para TCP y 5082 para TLS.
    
6. En **Protocolo de transporte SIP**, haga clic en el tipo de transporte que usa el punto.
    
    > [!NOTE]
    > Por motivos de seguridad, recomendamos encarecidamente que implemente a un punto para el servidor de mediación que pueda usar TLS. 
  
7. En el **Servidor de mediación asociado**, seleccione el grupo de servidores de mediación para asociar con el tronco raíz de este punto
    
8. En **puerto de servidor de mediación asociado**, escriba el puerto de escucha que el servidor de mediación recibirá mensajes SIP desde el mismo nivel.
    
    > [!NOTE]
    > Compatible con varios tronco en Skype para Business Server, no se puede configurar dos troncos con nombres de tronco diferentes con el mismo **puerto del servidor de mediación asociado** y el **Puerto de escucha para puerta de enlace IP/RTC**
  
    > [!NOTE]
    > Compatible con varios tronco en Skype para Business Server, se puede definir varios SIP señalización puertos en el servidor de mediación para la comunicación con varios elementos del mismo nivel. Al definir un tronco, debe ser el número de **puerto del servidor de mediación asociado** dentro del intervalo de puertos de escucha para el protocolo respectivo permitida por el servidor de mediación. Este intervalo de puertos se define en Skype para grupos de Business Server y el servidor de mediación. Haga clic en el grupo de servidores de mediación correspondiente y seleccione **Editar propiedades**. Especifique el intervalo de puertos en el campo **Puertos de escucha**.
  
9. Haga clic en **Aceptar**. 
    

