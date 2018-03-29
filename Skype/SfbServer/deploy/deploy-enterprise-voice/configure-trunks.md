---
title: Configurar troncos en Skype Empresarial Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
description: 'Resumen: Conozca cómo configurar un enlace entre un servidor de mediación y compañeros para Telefonía IP empresarial en Skype para Business Server 2015.'
ms.openlocfilehash: a2630d3e37e6ab15a0e88593549e9365ac69a3e7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="configure-trunks-in-skype-for-business-server-2015"></a>Configurar troncos en Skype Empresarial Server 2015
 
**Resumen:** Obtenga información sobre cómo configurar un enlace entre un servidor de mediación y compañeros para Telefonía IP empresarial en Skype para Business Server 2015.
  
Como parte de la implementación de Telefonía IP empresarial, puede configurar un enlace entre un servidor de mediación y uno o más de los siguientes pares para proporcionar conectividad de telefónica pública conmutada (PSTN) de red para clientes de Telefonía IP empresarial y dispositivos de su organización:
  
- Conexión basada en troncos SIP para un proveedor de servicio s de telefonía
    
- Puerta de enlace RTC
    
- Central de conmutación (PBX)
    
Para obtener más detalles, consulte [Plan de conectividad PSTN en Skype para Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).
  
Skype para la funcionalidad de Business Server admite varias asociaciones entre los servidores de mediación y puertas de enlace. Estas asociaciones se realizan mediante la definición de un tronco, que es una asociación lógica entre un grupo de servidores de mediación y telefónica pública conmutada (PSTN) de red puerta de enlace, controlador de borde de sesión (SBC) o IP-PBX. Utilice el generador de topología para asociar las puertas de enlace con los servidores de mediación (es decir, troncos).
  
- Para asignar o quitar un tronco en Skype para Business Server, primero debe definir un tronco en el generador de topología. Un tronco consiste en la asociación siguiente: servidor de mediación completo nombre de dominio (completo FQDN), el puerto de escucha del servidor de mediación, el FQDN de la puerta de enlace y el puerto de escucha de puerta de enlace.
    
- Para configurar varios troncos, puede crear varias asociaciones entre la misma puerta de enlace y el servidor de mediación. Esto proporciona resistencia adicional a la infraestructura de Telefonía IP empresarial, que es especialmente útil en escenarios interoperables de private branch exchange (PBX). 
    
Cuando se define un tronco, debe estar asociado con una ruta. Para asociar un tronco a una ruta, define un nombre sencillo para el tronco en el generador de topología. Este nombre simple se utiliza como el nombre de tronco en el Skype Business Server Panel de Control, donde los troncos pueden asociarse con rutas. El nombre simple del tronco se utiliza como el nombre de puerta de enlace desde el Skype para el Shell de administración de servidor de empresa. 
  
```
New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}
```

El administrador debe seleccionar un tronco predeterminado asociado con un servidor de mediación. En el generador de topología (ratón) en el servidor de mediación asociado y, a continuación, haga clic en **Propiedades**. Especifique la puerta de enlace predeterminada para el servidor de mediación. 
  

