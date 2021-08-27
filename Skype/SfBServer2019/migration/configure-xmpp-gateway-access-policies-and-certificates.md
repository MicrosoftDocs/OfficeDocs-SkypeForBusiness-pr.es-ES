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
ms.localizationpriority: medium
description: 'La federación XMPP define una implementación externa basada en el Protocolo extensible de mensajería y presencia (XMPP). Una configuración XMPP permite a los usuarios acceder a usuarios de dominio XMPP mediante:'
ms.openlocfilehash: c442d0c4f5b5443e378be5afc031f7489860e42a
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58594310"
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
    

