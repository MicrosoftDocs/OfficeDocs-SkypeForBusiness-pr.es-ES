---
title: Configurar certificados y directivas de acceso por puerta de enlace XMPP
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
description: 'La federación XMPP define una implementación externa basada en el Protocolo extensible de mensajería y presencia (XMPP). Una configuración XMPP permite a los usuarios acceder a los usuarios del dominio XMPP de la siguiente manera:'
ms.openlocfilehash: f94cd3bc0a769165f6ffe8ecabea8b7f48a1ff07
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753940"
---
# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a>Configurar certificados y directivas de acceso por puerta de enlace XMPP

La federación XMPP define una implementación externa basada en el Protocolo extensible de mensajería y presencia (XMPP). Una configuración XMPP permite a los usuarios acceder a los usuarios del dominio XMPP de la siguiente manera:
  
- MI y presencia-persona solo para la persona
    
- Creación de contactos federados XMPP en el cliente de Skype empresarial
    
Al configurar directivas para la compatibilidad con socios federados de XMPP, las directivas se aplican a los usuarios de dominios federados XMPP, pero no a los usuarios de los proveedores de servicios de mensajería instantánea (mi) del Protocolo de inicio de sesión (mi) ni a los dominios federados SIP. Configure un socio federado XMPP para cada dominio federado de XMPP en el que desee permitir que los usuarios agreguen contactos y se comuniquen con ellos. Una vez aplicadas las directivas, debe configurar los certificados de puerta de enlace XMPP. 
  
> [!NOTE]
> La funcionalidad XMPP está en desuso en Skype empresarial Server 2019, pero puede continuarse en un servidor heredado en coexistencia con Skype empresarial Server 2019. Asegúrese de que ya ha implementado la puerta de enlace XMPP del servidor heredado (Skype empresarial Server 2015/Lync Server 2013) y de que ha configurado las directivas de acceso para habilitar a los usuarios para la puerta de enlace XMPP heredada. Para obtener más información, consulte [migrar la Federación XMPP](migrating-xmpp-federation.md). 
  
### <a name="configure-an-external-access-policy-to-enable-users-for-legacy-xmpp-gateway"></a>Configurar una directiva de acceso externo para habilitar a los usuarios para la puerta de enlace XMPP heredada

1. Abra el panel de control de Skype empresarial Server heredado.
    
2. En el barra de navegación izquierda, haga clic en **Federación y acceso externo** y en **Directiva de acceso externo**.
    
3. Haga clic en **Nuevo** y después en **Directiva de usuario**.
    
4. Indique un nombre para la directiva de usuario de acceso externo.
    
5. Indique una descripción para la directiva de usuario de acceso externo.
    
6. Seleccione **Habilitar comunicaciones con usuarios federados**.
    
7. Seleccione **Habilitar comunicaciones con usuarios federados de XMPP**.
    
8. Haga clic en **Confirmar** para guardar los cambios en la directiva de sitio o de usuario. 
    

