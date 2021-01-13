---
title: Configurar troncos en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
description: 'Resumen: obtenga información sobre cómo configurar un tronco entre un servidor de mediación y los sistemas del mismo nivel Telefonía IP empresarial en Skype Empresarial Server.'
ms.openlocfilehash: f2e9f3a5e9fa9d89ef9db63aa82b6a3ce3a86c6e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824960"
---
# <a name="configure-trunks-in-skype-for-business-server"></a>Configurar troncos en Skype Empresarial Server
 
**Resumen:** Learn how to configure a trunk between a Mediation Server and peers for Telefonía IP empresarial in Skype for Business Server.
  
Como parte de la implementación de Telefonía IP empresarial, puede configurar un tronco entre un servidor de mediación y uno o varios de los siguientes sistemas del mismo nivel para proporcionar conectividad de red telefónica conmutada (RTC) para los clientes y dispositivos de Telefonía IP empresarial de su organización:
  
- Conexión basada en troncos SIP para un proveedor de servicio s de telefonía
    
- Puerta de enlace RTC
    
- Central de conmutación (PBX)
    
Para obtener más información, consulte [Plan for PSTN connectivity in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).
  
La funcionalidad de Skype Empresarial Server admite varias asociaciones entre puertas de enlace y servidores de mediación. Estas asociaciones se realizan definiendo un tronco, que es una asociación lógica entre un grupo de servidores de mediación y una puerta de enlace de red telefónica conmutada (RTC), un controlador de borde de sesión (SBC) o una IP-PBX. Use el Generador de topologías para asociar puertas de enlace con servidores de mediación (es decir, troncos).
  
- Para asignar o quitar un tronco en Skype Empresarial Server, primero debe definir un tronco en topology Builder. Un tronco consta de la siguiente asociación: nombre de dominio completo (FQDN) del servidor de mediación, puerto de escucha del servidor de mediación, FQDN de puerta de enlace y puerto de escucha de puerta de enlace.
    
- Para configurar varios troncos, puede crear varias asociaciones entre la misma puerta de enlace y el servidor de mediación. Esto proporciona resistencia adicional a la infraestructura Telefonía IP empresarial, que es especialmente útil en escenarios interoperacionales de central de conmutación (PBX). 
    
Cuando se define un tronco, debe estar asociado con una ruta. Para asociar un tronco a una ruta, debe definir un nombre simple para el tronco en topology Builder. Este nombre simple se usa como nombre de tronco en el Panel de control de Skype Empresarial Server, donde los troncos se pueden asociar con rutas. El nombre de tronco simple se usa como el nombre de puerta de enlace del Shell de administración de Skype Empresarial Server. 
  
```powershell
New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}
```

El administrador debe seleccionar un tronco predeterminado asociado a un servidor de mediación. En el Generador de topologías, haga clic con el botón secundario en el servidor de mediación asociado y, a continuación, haga clic en **Propiedades.** Especifique la puerta de enlace predeterminada para el servidor de mediación. 
  

