---
title: Planeación de autenticación moderna (ADAL) con Skype para la empresa
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: Este artículo explica qué es autenticación moderno (que se basa en la biblioteca de autenticación de Active Directory (ADAL) y OAuth 2.0).
ms.openlocfilehash: 666808134e2ed178a85058a6e3cd3019bf982a35
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33907195"
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a>Cómo usar la autenticación moderna (ADAL) con Skype Empresarial
 
En este artículo se presenta autenticación moderno (que se basa en la biblioteca de autenticación de Active Directory (ADAL) y OAuth 2.0) que puede encontrarse en la actualización de marzo de 2016 actualización acumulativa de Skype para la empresa de Skype para Business Server 2015, o de inicial versión de Skype para Business Server 2019.
  
## <a name="what-is-adal"></a>¿Qué es ADAL?

ADAL es el acrónimo de "Biblioteca de autenticación de Active Directory" y, junto con OAuth 2.0, es fundamental en la autenticación moderna. Esta biblioteca de código está diseñada para disponer de recursos protegidos en el directorio de aplicaciones de cliente (como Skype para la empresa) a través de los tokens de seguridad. ADAL funciona con OAuth 2.0 para permitir más escenarios de autorización y autenticación, como la autenticación multifactor (MFA) y más formas de autenticación SAML.
  
Varias aplicaciones que actúan como clientes pueden aprovecharse de la autenticación moderna para obtener recursos protegidos. En Skype para Business Server, esta tecnología se usa entre clientes locales y los servidores locales con el fin de proporcionar a los usuarios un nivel adecuado de autorización de recursos.
  
Las conversaciones de autenticación moderna (que se basan en ADAL y OAuth 2.0) tienen algunos elementos en común.
  
- Hay un cliente que realiza una solicitud para un recurso, en este caso, el cliente es Skype para la empresa.
    
- No hay un recurso al que el cliente necesita un nivel específico de acceso, y este recurso está protegida mediante un servicio de directorio, en este caso, el recurso es Skype para Business Server.
    
- No hay una conexión de OAuth, en otras palabras, una conexión que está dedicado a la *autorización de* un usuario para obtener acceso a un recurso. (OAuth también se conoce por el nombre descriptivo, autenticación "de servidor a servidor" y, a menudo, aparece abreviado como S2S).
    
En Skype para las conversaciones de Business Server moderno autenticación (ADAL), Skype para Business Server se comunica a través de ADFS (ADFS 3.0 en Windows Server 2012 R2). La autenticación puede ocurrir con otro proveedor de identidades (IdP), pero el servidor de Skype Empresarial necesita configurarse para poder comunicarse directamente con ADFS. Si no ha configurado ADFS para que funcione con Skype para Business Server complete la [instalación de AD FS](https://technet.microsoft.com/en-us/library/adfs2-step-by-step-guides%28v=ws.10%29.aspx).
  
ADAL se incluye en la actualización de marzo de 2016 actualización acumulativa de Skype para Business Server 2015 y el de 2016 marzo actualización acumulativa de Skype para empresarial **debe** estar instalado y es necesario para la configuración correcta. Para Skype para Business Server 2019, está disponible desde la versión inicial del producto.
  
> [!NOTE]
> Con la versión inicial, la autenticación moderna en un entorno local solo se admite si no existe una topología combinada de Skype. Por ejemplo, si el entorno es totalmente Skype para Business Server. Esta instrucción puede estar vinculada a cambios. 
  
Debe descargarse un paquete de PowerShell que incluye archivos .ps1 con los comandos que usa ADAL para obtener una configuración correcta.

Para obtener información acerca de cómo implementar la autenticación moderno en Skype para la empresa, consulte: [cómo usar autenticación moderno (ADAL) con Skype para la empresa](../../manage/authentication/use-adal.md)
