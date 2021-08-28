---
title: Planeación de la autenticación moderna (ADAL) con Skype Empresarial
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
description: En este artículo se explica qué es la autenticación moderna (que se basa en la Biblioteca de autenticación de Active Directory (ADAL) y OAuth 2.0).
ms.openlocfilehash: 29bbe33754b2363e84f449115bd51396ad9af932
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58614020"
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a>Cómo usar la autenticación moderna (ADAL) con Skype Empresarial
 
En este artículo se presenta la autenticación moderna (basada en la Biblioteca de autenticación de Active Directory (ADAL) y OAuth 2.0) que se puede encontrar en la actualización acumulativa de marzo de 2016 para Skype Empresarial para Skype Empresarial Server 2015 o desde la versión inicial de Skype Empresarial Server 2019.
  
## <a name="what-is-adal"></a>¿Qué es ADAL?

ADAL es el acrónimo de la "Biblioteca de autenticación de Active Directory" y, junto con OAuth 2.0, es una base de la autenticación moderna. Esta biblioteca de código está diseñada para que los recursos protegidos del directorio estén disponibles para las aplicaciones cliente (como Skype Empresarial) mediante tokens de seguridad. ADAL funciona con OAuth 2.0 para habilitar más escenarios de autenticación y autorización, como la autenticación multifactor (MFA) y más formas de autenticación SAML.
  
Una variedad de aplicaciones que actúan como clientes pueden aprovechar la autenticación moderna para obtener ayuda para obtener recursos protegidos. En Skype Empresarial Server, esta tecnología se usa entre clientes locales y servidores locales con el fin de proporcionar a los usuarios un nivel adecuado de autorización a los recursos.
  
Las conversaciones de autenticación moderna (basadas en ADAL y OAuth 2.0) tienen algunos elementos en común.
  
- Hay un cliente que realiza una solicitud para un recurso, en este caso, el cliente está Skype Empresarial.
    
- Hay un recurso al que el cliente necesita un nivel de acceso específico y este recurso está protegido por un servicio de directorio, en este caso el recurso Skype Empresarial Server.
    
- Hay una conexión OAuth, es decir, una conexión dedicada a autorizar  *a*  un usuario a tener acceso a un recurso. (OAuth también se conoce por el nombre más descriptivo, autenticación de servidor a servidor, y a menudo se abrevia como S2S).
    
En Skype Empresarial Server conversaciones de autenticación moderna (ADAL), Skype Empresarial Server se comunica a través de ADFS (ADFS 3.0 en Windows Server 2012 R2). La autenticación puede ocurrir con otro proveedor de identidades (IdP), pero Skype Empresarial servidor debe configurarse para comunicarse directamente con ADFS. Si no ha configurado ADFS para que funcione con Skype Empresarial Server por favor complete la instalación [de ADFS](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd727938(v=ws.10)).
  
ADAL se incluye en la actualización acumulativa de marzo de 2016 para Skype Empresarial Server 2015 y la  actualización acumulativa de marzo de 2016 para Skype Empresarial debe instalarse y es necesaria para una configuración correcta. Para Skype Empresarial Server 2019, está disponible desde la versión inicial del producto.
  
> [!NOTE]
> Durante la versión inicial, la autenticación moderna en un entorno local solo se admite si no hay ninguna topología Skype mixta. Por ejemplo, si el entorno es puramente Skype Empresarial Server. Esta instrucción puede estar sujeta a cambios. 
  
Un paquete de PowerShell que .ps1 archivos con los comandos usados por ADAL debe descargarse para una configuración correcta.

Para obtener información sobre cómo implementar la autenticación moderna en Skype Empresarial, consulte: Cómo usar la autenticación moderna [(ADAL) con Skype Empresarial](/microsoft-365/enterprise/hybrid-modern-auth-overview)