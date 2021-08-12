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
description: 'La federación XMPP define una implementación externa basada en el Protocolo extensible de mensajería y presencia (XMPP). Una configuración XMPP permite a los usuarios acceder a usuarios de dominio XMPP mediante:'
ms.openlocfilehash: 31d3c2a4b4d16407a30eb755e8b18b3ddf1a1b31c342ed6ff3384bbcef3afbc6
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54296027"
---
# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a>Configurar certificados y directivas de acceso por puerta de enlace XMPP

La federación XMPP define una implementación externa basada en el Protocolo extensible de mensajería y presencia (XMPP). Una configuración XMPP permite a los usuarios acceder a usuarios de dominio XMPP mediante:
  
- Mensajería instantánea y presencia: solo de persona a persona
    
- Creación de contactos federados XMPP en el Skype Empresarial cliente
    
Al configurar directivas para admitir socios federados XMPP, las directivas se aplican a los usuarios de dominios federados XMPP, pero no a los usuarios de proveedores de servicios de mensajería instantánea (MI) del Protocolo de inicio de sesión (SIP) o dominios federados SIP. Configure un partner federado XMPP para cada dominio federado XMPP con el que desee permitir a los usuarios agregar contactos y comunicarse con ellos. Una vez aplicadas las directivas, debe configurar los certificados de puerta de enlace XMPP. 
  
> [!NOTE]
> La funcionalidad XMPP está en desuso en Skype Empresarial Server 2019, pero se puede continuar en un servidor heredado en coexistencia con Skype Empresarial Server 2019. Asegúrese de que ya ha implementado la puerta de enlace XMPP del servidor heredado (Skype Empresarial Server 2015 / Lync Server 2013) y de configurar las directivas de acceso para habilitar a los usuarios para la puerta de enlace XMPP heredada. Para obtener más información, [vea Migración de la federación XMPP](migrating-xmpp-federation.md). 
  
### <a name="configure-an-external-access-policy-to-enable-users-for-legacy-xmpp-gateway"></a>Configurar una directiva de acceso externo para habilitar usuarios para la puerta de enlace XMPP heredada

1. Abra el panel de control Skype Empresarial Server heredado.
    
2. En el barra de navegación izquierda, haga clic en **Federación y acceso externo** y en **Directiva de acceso externo**.
    
3. Haga clic en **Nuevo** y después en **Directiva de usuario**.
    
4. Indique un nombre para la directiva de usuario de acceso externo.
    
5. Indique una descripción para la directiva de usuario de acceso externo.
    
6. Seleccione **Habilitar comunicaciones con usuarios federados**.
    
7. Seleccione **Habilitar comunicaciones con usuarios federados de XMPP**.
    
8. Haga clic en **Confirmar** para guardar los cambios en la directiva de sitio o de usuario. 
    

