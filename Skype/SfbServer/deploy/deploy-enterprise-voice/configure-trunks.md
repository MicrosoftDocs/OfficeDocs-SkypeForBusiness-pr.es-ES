---
title: Configurar troncos en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
description: 'Resumen: Aprenda a configurar un tronco entre un servidor de mediación y los homólogos de telefonía IP empresarial en Skype empresarial Server.'
ms.openlocfilehash: 9bd285f1364d54940afd827858248656a6bb9f00
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001240"
---
# <a name="configure-trunks-in-skype-for-business-server"></a>Configurar troncos en Skype empresarial Server
 
**Resumen:** Obtenga información sobre cómo configurar un tronco entre un servidor de mediación y los interlocutores de telefonía IP empresarial en Skype empresarial Server.
  
Como parte de la implementación de telefonía IP empresarial, puede configurar un tronco entre un servidor de mediación y uno o más de los siguientes elementos para proporcionar conectividad de red telefónica conmutada (RTC) pública para los clientes y dispositivos de voz de su organización:
  
- Conexión basada en troncos SIP para un proveedor de servicio s de telefonía
    
- Puerta de enlace RTC
    
- Central de conmutación (PBX)
    
Para obtener más información, consulte [planear la conectividad RTC en Skype empresarial Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).
  
La funcionalidad de Skype empresarial Server admite varias asociaciones entre puertas de enlace y servidores de mediación. Estas asociaciones se realizan mediante la definición de un tronco, que es una asociación lógica entre un grupo de servidores de mediación y una puerta de enlace de red de telefonía pública conmutada (RTC), controlador de borde de sesión (SBC) o IP-PBX. Use el generador de topología para asociar puertas de enlace con servidores de mediación (es decir, troncos).
  
- Para asignar o quitar un tronco en Skype empresarial Server, primero debe definir un tronco en el generador de topologías. Un tronco consiste en la siguiente Asociación: nombre de dominio completo (FQDN) de Media Server, el puerto de escucha del servidor de mediación, el FQDN de la puerta de enlace y el puerto de escucha de la puerta de enlace.
    
- Para configurar varios troncos, puede crear varias asociaciones entre la misma puerta de enlace y el servidor de mediación. Esto proporciona resistencia adicional a la infraestructura de telefonía IP empresarial, que es especialmente útil en escenarios de interoperabilidad de la intercambiación privada (PBX). 
    
Cuando se define un tronco, debe estar asociado con una ruta. Para asociar un tronco a una ruta, defina un nombre simple para el tronco en el generador de topología. Este nombre simple se usa como el nombre del tronco en el panel de control de Skype empresarial Server, donde se pueden asociar los troncos con las rutas. El nombre de tronco simple se usa como el nombre de la puerta de enlace desde el shell de administración de Skype empresarial Server. 
  
```powershell
New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}
```

El administrador debe seleccionar un tronco predeterminado asociado a un servidor de mediación. En el generador de topología, haga clic con el botón secundario en el servidor de mediación asociado y luego haga clic en **propiedades**. Especificar la puerta de enlace predeterminada para el servidor de mediación. 
  

