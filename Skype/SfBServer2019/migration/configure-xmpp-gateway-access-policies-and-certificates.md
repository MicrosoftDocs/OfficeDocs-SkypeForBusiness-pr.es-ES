---
title: Configurar certificados y directivas de acceso por puerta de enlace XMPP
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'La Federación XMPP define una implementación externa basada en el protocolo de presencia y mensajería extensible (XMPP). Una configuración XMPP permite a los usuarios acceder a los usuarios del dominio XMPP de la siguiente manera:'
ms.openlocfilehash: 8182153bf3633b2392969f5870a7d5b96471d4fb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813768"
---
# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a>Configurar certificados y directivas de acceso por puerta de enlace XMPP

La Federación XMPP define una implementación externa basada en el protocolo de presencia y mensajería extensible (XMPP). Una configuración XMPP permite a los usuarios acceder a los usuarios del dominio XMPP de la siguiente manera:
  
- Mensajería instantánea y presencia-persona a persona solamente
    
- Creación de los contactos de XMPP federado en el cliente de Skype empresarial
    
Al configurar directivas para la compatibilidad de los socios de XMPP federados, las directivas se aplican a los usuarios de XMPP Federated Domains, pero no a los usuarios de los proveedores de servicios de mensajería instantánea (mi) protocolo de inicio de sesión (mi) ni a los dominios federados de SIP. Configure un socio de XMPP federado para cada dominio de XMPP federado que desee permitir a los usuarios que añadan contactos y se comuniquen con ellos. Una vez que las directivas estén en vigor, tendrá que configurar los certificados de la puerta de enlace XMPP. 
  
> [!NOTE]
> La funcionalidad de XMPP es obsoleta en Skype empresarial Server 2019, pero puede continuarse en un servidor heredado en coexistencia con Skype empresarial Server 2019. Asegúrese de que ya ha implementado el servidor heredado (Skype empresarial Server 2015/Lync Server 2013) puerta de enlace XMPP y ha configurado las directivas de acceso para habilitar a los usuarios para la puerta de enlace XMPP heredada. Para obtener más información, consulte [migrar la Federación XMPP](migrating-xmpp-federation.md). 
  
### <a name="configure-an-external-access-policy-to-enable-users-for-legacy-xmpp-gateway"></a>Configurar una directiva de acceso externo para habilitar a los usuarios para la puerta de enlace XMPP heredada

1. Abra el panel de control heredado de Skype empresarial Server.
    
2. En la barra de navegación izquierda, haga clic en **Federación y acceso externo**y, después, haga clic en **Directiva de acceso externo**.
    
3. Haga clic en **Nuevo** y, luego, en **Directiva de usuario**.
    
4. Escriba un nombre para la Directiva de usuario de acceso externo.
    
5. Proporcione una descripción para la Directiva de usuario de acceso externo.
    
6. Seleccione **Habilitar comunicaciones con usuarios federados**.
    
7. Seleccione **Habilitar comunicaciones con usuarios federados de XMPP**.
    
8. Haga clic en **confirmar** para guardar los cambios en el sitio o en la Directiva de usuario. 
    

