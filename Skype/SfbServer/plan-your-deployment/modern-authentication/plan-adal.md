---
title: Planeación de la autenticación moderna (ADAL) con Skype empresarial
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: En este artículo se explica qué es la autenticación moderna (que se basa en la biblioteca de autenticación de Active Directory (ADAL) y OAuth 2,0).
ms.openlocfilehash: 5a51b0712f33cbafc64f87f56b4d12649bfad97e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046293"
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a>Cómo usar la autenticación moderna (ADAL) con Skype empresarial
 
En este artículo se presenta la autenticación moderna (que se basa en la biblioteca de autenticación de Active Directory (ADAL) y OAuth 2,0) que puede encontrarse en la actualización acumulativa de marzo de 2016 para Skype empresarial para Skype empresarial Server 2015 o desde el inicial Release for Skype for Business Server 2019.
  
## <a name="what-is-adal"></a>¿Qué es ADAL?

ADAL es el acrónimo de "biblioteca de autenticación de Active Directory" y, junto con OAuth 2,0, es un respaldo de la autenticación moderna. Esta biblioteca de código está diseñada para que los recursos protegidos en su directorio estén disponibles para las aplicaciones cliente (como Skype empresarial) mediante tokens de seguridad. ADAL funciona con OAuth 2,0 para habilitar más escenarios de autenticación y autorización, como multi-factor Authentication (MFA) y más formas de autenticación SAML.
  
Una variedad de aplicaciones que actúan como clientes pueden aprovechar la autenticación moderna para ayudarle a obtener recursos protegidos. En Skype empresarial Server, esta tecnología se usa entre los clientes locales y los servidores locales para proporcionar a los usuarios un nivel adecuado de autorización para los recursos.
  
Las conversaciones de autenticación moderna (que se basan en ADAL y OAuth 2,0) tienen algunos elementos en común.
  
- Hay un cliente que realiza una solicitud para un recurso, en este caso, el cliente es Skype empresarial.
    
- Hay un recurso para el que el cliente necesita un nivel específico de acceso y este recurso está protegido por un servicio de directorio, en este caso el recurso es Skype empresarial Server.
    
- Hay una conexión de OAuth, es decir, una conexión dedicada a *autorizar* a un usuario para que tenga acceso a un recurso. (OAuth también se conoce por el nombre descriptivo, la autenticación de servidor a servidor y, a menudo, se suele abreviar como S2S).
    
En conversaciones de autenticación moderna (ADAL) de Skype empresarial Server, Skype empresarial Server se comunica a través de ADFS (ADFS 3,0 en Windows Server 2012 R2). La autenticación puede producirse mediante otro proveedor de identidades (IdP), pero es necesario configurar Skype empresarial Server para comunicarse con ADFS directamente. Si no ha configurado ADFS para que funcione con Skype empresarial Server, complete la [instalación de ADFS](https://technet.microsoft.com/library/adfs2-step-by-step-guides%28v=ws.10%29.aspx).
  
ADAL se incluye en la actualización acumulativa de marzo de 2016 para Skype empresarial Server 2015 y la actualización acumulativa de marzo de 2016 para Skype empresarial **debe** estar instalada y es necesaria para una configuración correcta. Para Skype empresarial Server 2019, está disponible en la versión inicial del producto.
  
> [!NOTE]
> Durante la versión inicial, la autenticación moderna en un entorno local solo se admite si no interviene una topología mixta de Skype. Por ejemplo, si el entorno es puramente de Skype empresarial Server. Esta instrucción puede estar sujeta a cambios. 
  
Debe descargarse un paquete de PowerShell que incluya archivos. PS1 con los comandos que usa ADAL para una configuración correcta.

Para obtener información sobre cómo implementar la autenticación moderna en Skype empresarial, consulte: [Cómo usar la autenticación moderna (Adal) con Skype empresarial](../../manage/authentication/use-adal.md) .
