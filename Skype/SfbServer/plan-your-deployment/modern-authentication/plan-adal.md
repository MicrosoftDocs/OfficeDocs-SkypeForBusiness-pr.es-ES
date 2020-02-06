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
ms.openlocfilehash: 239dd6a49ecbec043a661e622a66eb5cb4665e96
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815838"
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a>Cómo usar la autenticación moderna (ADAL) con Skype Empresarial
 
En este artículo se presenta la autenticación moderna (que se basa en la biblioteca de autenticación de Active Directory (ADAL) y OAuth 2,0) que puede encontrarse en la actualización acumulativa de marzo de 2016 para Skype empresarial para Skype empresarial 2015, o desde el inicio versión para Skype empresarial Server 2019.
  
## <a name="what-is-adal"></a>¿Qué es ADAL?

ADAL es el acrónimo de "Biblioteca de autenticación de Active Directory" y, junto con OAuth 2.0, es fundamental en la autenticación moderna. Esta biblioteca de códigos está diseñada para que los recursos protegidos de su directorio estén disponibles para las aplicaciones cliente (como Skype empresarial) mediante tokens de seguridad. ADAL funciona con OAuth 2.0 para permitir más escenarios de autorización y autenticación, como la autenticación multifactor (MFA) y más formas de autenticación SAML.
  
Varias aplicaciones que actúan como clientes pueden aprovecharse de la autenticación moderna para obtener recursos protegidos. En Skype empresarial Server, esta tecnología se usa entre los clientes locales y los servidores locales para ofrecer a los usuarios un nivel adecuado de autorización de los recursos.
  
Las conversaciones de autenticación moderna (que se basan en ADAL y OAuth 2.0) tienen algunos elementos en común.
  
- Un cliente hace una solicitud de un recurso, en este caso, el cliente es Skype empresarial.
    
- Hay un recurso al que el cliente necesita un nivel de acceso específico, y este recurso está asegurado por un servicio de directorio, en este caso el recurso es Skype empresarial Server.
    
- Hay una conexión OAuth, en otras palabras, una conexión que se dedica a *autorizar* a un usuario a obtener acceso a un recurso. (OAuth también se conoce por el nombre descriptivo, autenticación "de servidor a servidor" y, a menudo, aparece abreviado como S2S).
    
En las conversaciones de autenticación moderna de Skype empresarial Server (ADAL), Skype empresarial Server se comunica a través de ADFS (ADFS 3,0 en Windows Server 2012 R2). La autenticación puede ocurrir con otro proveedor de identidades (IdP), pero el servidor de Skype Empresarial necesita configurarse para poder comunicarse directamente con ADFS. Si no ha configurado ADFS para funcionar con Skype empresarial Server, complete la [instalación de ADFS](https://technet.microsoft.com/en-us/library/adfs2-step-by-step-guides%28v=ws.10%29.aspx).
  
ADAL se incluye en la actualización acumulativa de marzo de 2016 para Skype empresarial 2015 y la actualización acumulativa de marzo de 2016 para Skype empresarial **debe** instalarse y es necesaria para una configuración correcta. Para Skype empresarial Server 2019, está disponible en la versión inicial del producto.
  
> [!NOTE]
> Con la versión inicial, la autenticación moderna en un entorno local solo se admite si no existe una topología combinada de Skype. Por ejemplo, si el entorno es puramente de Skype empresarial Server. Esta instrucción puede estar vinculada a cambios. 
  
Debe descargarse un paquete de PowerShell que incluye archivos .ps1 con los comandos que usa ADAL para obtener una configuración correcta.

Para obtener información sobre cómo implementar la autenticación moderna en Skype empresarial, consulte: [Cómo usar la autenticación moderna (Adal) con Skype empresarial](../../manage/authentication/use-adal.md)
