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
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
description: 'Summary: Learn how to configure a trunk between a Mediation Server and peers for Telefonía IP empresarial in Skype Empresarial Server.'
ms.openlocfilehash: 0b3846a79d05d6b3eaea664f919dfbca61b036b7
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58617046"
---
# <a name="configure-trunks-in-skype-for-business-server"></a>Configurar troncos en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre cómo configurar un tronco entre un servidor de mediación y los pares para Telefonía IP empresarial en Skype Empresarial Server.
  
Como parte de la implementación Telefonía IP empresarial, puede configurar un tronco entre un servidor de mediación y uno o varios de los siguientes sistemas del mismo nivel para proporcionar conectividad de red telefónica conmutada (RTC) para clientes y dispositivos de Telefonía IP empresarial de su organización:
  
- Conexión basada en troncos SIP para un proveedor de servicio s de telefonía
    
- Puerta de enlace RTC
    
- Central de conmutación (PBX)
    
Para obtener más información, vea [Plan for PSTN connectivity in Skype Empresarial Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).
  
Skype Empresarial Server admite varias asociaciones entre puertas de enlace y servidores de mediación. Estas asociaciones se realizan definiendo un tronco, que es una asociación lógica entre un grupo de servidores de mediación y una puerta de enlace de red telefónica conmutada (RTC), controlador de borde de sesión (SBC) o IP-PBX. Use el Generador de topologías para asociar puertas de enlace con servidores de mediación (es decir, troncos).
  
- Para asignar o quitar un tronco en Skype Empresarial Server, primero debe definir un tronco en el Generador de topologías. Un tronco consta de la siguiente asociación: Nombre de dominio completo (FQDN) del servidor de mediación, puerto de escucha del servidor de mediación, FQDN de puerta de enlace y puerto de escucha de puerta de enlace.
    
- Para configurar varios troncos, puede crear varias asociaciones entre la misma puerta de enlace y el servidor de mediación. Esto proporciona resistencia adicional a la infraestructura Telefonía IP empresarial, que es especialmente útil en escenarios interoperacionales de central de conmutación (PBX). 
    
Cuando se define un tronco, debe estar asociado con una ruta. Para asociar un tronco a una ruta, defina un nombre simple para el tronco en el Generador de topologías. Este nombre simple se usa como nombre de tronco en el Panel de control de Skype Empresarial Server, donde los troncos se pueden asociar con rutas. El nombre de tronco simple se usa como el nombre de puerta de enlace del Shell Skype Empresarial Server administración. 
  
```powershell
New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}
```

El administrador debe seleccionar un tronco predeterminado asociado a un servidor de mediación. En el Generador de topologías, haga clic con el botón secundario en el servidor de mediación asociado y, a continuación, haga clic en **Propiedades**. Especifique la puerta de enlace predeterminada para el servidor de mediación. 
  

