---
title: Configuración de troncos en Skype para Business Server
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
ms.assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
description: 'Resumen: Obtenga información sobre cómo configurar un tronco entre un servidor de mediación y a los compañeros para Enterprise Voice en Skype para Business Server.'
ms.openlocfilehash: 02ace749e62b7e6edd3f514fa81b55eb30c87094
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23887979"
---
# <a name="configure-trunks-in-skype-for-business-server"></a>Configuración de troncos en Skype para Business Server
 
**Resumen:** Obtenga información sobre cómo configurar un tronco entre un servidor de mediación y a los compañeros para Enterprise Voice en Skype para Business Server.
  
Como parte de la implementación de Enterprise Voice, puede configurar un tronco entre un servidor de mediación y uno o varios de los siguientes elementos del mismo nivel para proporcionar conectividad de telefónica conmutada (RTC) de la red de clientes de Enterprise Voice y dispositivos en su organización:
  
- Conexión basada en troncos SIP para un proveedor de servicio s de telefonía
    
- Puerta de enlace RTC
    
- Central de conmutación (PBX)
    
Para obtener más información, consulte [Plan para la conectividad de RTC en Skype para Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).
  
Skype para la funcionalidad de Business Server admite varias asociaciones entre los servidores de mediación y puertas de enlace. Estas asociaciones se realizan mediante la definición de un tronco, que es una asociación lógica entre un grupo de servidores de mediación y una telefónica conmutada (RTC) de red puerta de enlace, controlador de borde de sesión (SBC) o IP-PBX. Use el generador de topología para asociar las puertas de enlace con los servidores de mediación (es decir, troncos).
  
- Para asignar o quitar un tronco en Skype para Business Server, primero debe definir un tronco en el generador de topología. Un tronco consta de la asociación siguiente: el servidor de mediación completo (FQDN) del nombre de dominio, el puerto de escucha del servidor de mediación, el FQDN de puerta de enlace y el puerto de escucha de puerta de enlace.
    
- Para configurar varios troncos, puede crear varias asociaciones entre la misma puerta de enlace y el servidor de mediación. Esto proporciona resistencia adicional a la infraestructura de telefonía IP empresarial, que es especialmente útil en escenarios de interoperational de central de conmutación (PBX) de exchange. 
    
Cuando se define un tronco, debe estar asociado con una ruta. Para asociar un tronco a una ruta, defina un nombre sencillo para el tronco en el generador de topología. Este nombre simple se utiliza como el nombre del tronco en el Skype para el Panel de Control de servidor empresarial, donde se pueden asociadas con rutas de troncos. El nombre del tronco simple se utiliza como el nombre de la puerta de enlace de la Skype para Shell de administración de servidor empresarial. 
  
```
New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}
```

El administrador debe seleccionar un tronco predeterminado asociado con un servidor de mediación. En el generador de topología, haga clic en el servidor de mediación asociado y, a continuación, haga clic en **Propiedades**. Especifique la puerta de enlace predeterminada para el servidor de mediación. 
  

