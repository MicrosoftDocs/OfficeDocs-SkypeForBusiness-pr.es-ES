---
title: Configurar certificados y directivas de acceso por puerta de enlace XMPP
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'La federación XMPP define una implementación externa en función de la mensajería eXtensible y el protocolo de presencia (XMPP). Una configuración de XMPP permite a los usuarios acceso a los usuarios de dominio XMPP por:'
ms.openlocfilehash: 2ec2440365907632523728238c51cc90e894c84e
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "25027861"
---
# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a>Configurar certificados y directivas de acceso por puerta de enlace XMPP

La federación XMPP define una implementación externa en función de la mensajería eXtensible y el protocolo de presencia (XMPP). Una configuración de XMPP permite a los usuarios acceso a los usuarios de dominio XMPP por:
  
- Mensajería instantánea y presencia - solo persona a persona
    
- Creación de contactos federados XMPP en el Skype para clientes empresariales
    
Al configurar las directivas de soporte técnico de XMPP socios federados, las directivas se aplican a los usuarios de dominios XMPP federado, pero no a los usuarios del protocolo de inicio de sesión (SIP) de mensajería instantánea servicio (IM) de SIP o proveedores de dominios federados. Configurar a un socio federado de XMPP para cada dominio federado XMPP que se desea permitir a los usuarios agregar contactos y comunicarse con. Una vez que las directivas están en su lugar, debe configurar los certificados de puerta de enlace XMPP. 
  
> [!NOTE]
> Funcionalidad XMPP está en desuso en Skype para Business Server 2019, pero se puede continuar en un servidor heredado en coexistencia con Skype para Business Server 2019. Asegúrese de que ya ha implementado el servidor heredado (Skype para Business Server 2015 / Lync Server 2013) puerta de enlace de XMPP y configurado las directivas de acceso para permitir a los usuarios para la puerta de enlace de XMPP heredado. Para obtener información detallada, vea [Migrar la federación XMPP](migrating-xmpp-federation.md). 
  
### <a name="configure-an-external-access-policy-to-enable-users-for-legacy-xmpp-gateway"></a>Configurar una directiva de acceso externo para habilitar usuarios para la puerta de enlace de XMPP heredado

1. Abra el Skype heredado para el Panel de Control de servidor empresarial.
    
2. En la barra de navegación izquierda, haga clic en **federación y acceso externo**y, a continuación, haga clic en **Directiva de acceso externo**.
    
3. Haga clic en **Nuevo** y, luego, en **Directiva de usuario**.
    
4. Escriba un nombre para la directiva de usuario de acceso externo.
    
5. Proporcione una descripción para la directiva de usuario de acceso externo.
    
6. Seleccione **Habilitar las comunicaciones con los usuarios federados**.
    
7. Seleccione **habilitar comunicaciones con XMPP usuarios federados**.
    
8. Haga clic en **Confirmar** para guardar los cambios en la directiva de sitio o usuario. 
    

