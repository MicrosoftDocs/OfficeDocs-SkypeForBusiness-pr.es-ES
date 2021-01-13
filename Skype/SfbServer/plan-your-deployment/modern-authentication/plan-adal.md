---
title: Planificación de la autenticación moderna (ADAL) con Skype Empresarial
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: En este artículo se explica qué es la autenticación moderna (que se basa en la Biblioteca de autenticación de Active Directory (ADAL) y OAuth 2.0).
ms.openlocfilehash: bd5d172fe4589cbd28c5b22507ad8603695ed62f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816230"
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a>Cómo usar la autenticación moderna (ADAL) con Skype Empresarial
 
En este artículo se presenta la autenticación moderna (que se basa en la Biblioteca de autenticación de Active Directory (ADAL) y OAuth 2.0) que se puede encontrar en la actualización acumulativa de marzo de 2016 para Skype Empresarial para Skype Empresarial Server 2015, o desde la versión inicial de Skype Empresarial Server 2019.
  
## <a name="what-is-adal"></a>¿Qué es ADAL?

ADAL es el acrónimo de la "Biblioteca de autenticación de Active Directory" y, junto con OAuth 2.0, es una base de la autenticación moderna. Esta biblioteca de código está diseñada para que los recursos protegidos del directorio estén disponibles para las aplicaciones cliente (como Skype Empresarial) a través de tokens de seguridad. ADAL funciona con OAuth 2.0 para habilitar más escenarios de autenticación y autorización, como la autenticación multifactor (MFA) y más formas de autenticación SAML.
  
Una variedad de aplicaciones que actúan como clientes pueden aprovechar la autenticación moderna para obtener ayuda para obtener recursos protegidos. En Skype Empresarial Server, esta tecnología se usa entre los clientes locales y los servidores locales para proporcionar a los usuarios un nivel adecuado de autorización para los recursos.
  
Las conversaciones de autenticación moderna (basadas en ADAL y OAuth 2.0) tienen algunos elementos en común.
  
- Hay un cliente que realiza una solicitud para un recurso, en este caso, el cliente es Skype Empresarial.
    
- Hay un recurso al que el cliente necesita un nivel específico de acceso y este recurso está protegido por un servicio de directorio, en este caso el recurso es Skype Empresarial Server.
    
- Hay una conexión OAuth, es decir, una conexión dedicada a autorizar  *a*  un usuario a tener acceso a un recurso. (OAuth también se conoce por el nombre más descriptivo, autenticación de servidor a servidor, y a menudo se abrevia como S2S).
    
En las conversaciones de autenticación moderna (ADAL) de Skype Empresarial Server, Skype Empresarial Server se comunica a través de ADFS (ADFS 3.0 en Windows Server 2012 R2). La autenticación puede producirse con otro proveedor de identidades (IdP), pero Skype Empresarial Server debe configurarse para comunicarse directamente con ADFS. Si no ha configurado ADFS para trabajar con Skype Empresarial Server, complete la instalación [de ADFS.](https://technet.microsoft.com/library/adfs2-step-by-step-guides%28v=ws.10%29.aspx)
  
ADAL se incluye en la actualización acumulativa de marzo de 2016 para Skype Empresarial Server 2015, y la actualización acumulativa de marzo de 2016 para Skype Empresarial debe estar instalada y es necesaria para una configuración correcta.  Para Skype Empresarial Server 2019, está disponible desde la versión inicial del producto.
  
> [!NOTE]
> Durante la versión inicial, la autenticación moderna en un entorno local solo se admite si no hay ninguna topología mixta de Skype implicada. Por ejemplo, si el entorno es simplemente Skype Empresarial Server. Esta instrucción puede estar sujeta a cambios. 
  
Se debe descargar un paquete de PowerShell que incluya archivos .ps1 con los comandos usados por ADAL para una configuración correcta.

Para obtener información sobre cómo implementar la autenticación moderna en Skype Empresarial, consulte: Cómo usar la autenticación moderna [(ADAL) con Skype Empresarial](../../manage/authentication/use-adal.md)
