---
title: Marco de seguridad de Skype para Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 01131e28-b38e-40d9-8524-06725b9c6608
description: En esta sección se proporciona una visión general de los elementos fundamentales que constituyen el marco de seguridad de Skype para Business Server. Descripción de cómo funcionan conjuntamente estos elementos es fundamental para tomar decisiones fundamentadas sobre cómo asegurar su Skype determinado para la implementación de Business Server.
ms.openlocfilehash: 7c678e1f005178b569f8e4136d40fd911483a3d5
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30879885"
---
# <a name="security-framework-for-skype-for-business-server"></a>Marco de seguridad de Skype para Business Server
 
En esta sección se proporciona una visión general de los elementos fundamentales que constituyen el marco de seguridad de Skype para Business Server. Descripción de cómo funcionan conjuntamente estos elementos es fundamental para tomar decisiones fundamentadas sobre cómo asegurar su Skype determinado para la implementación de Business Server.
  
Dichos elementos son los siguientes:
  
- Los servicios de dominio de Active Directory (AD DS) proporciona un único repositorio back-end de confianza para las cuentas de usuario y recursos de red.
    
- El control de acceso basado en roles (RBAC) le permite delegar tareas administrativas y mantener, al mismo tiempo, altos estándares de seguridad.
    
- La infraestructura de clave pública (PKI) utiliza certificados emitidos por entidades de certificación (CA) de confianza para autenticar los servidores y garantizar la integridad de los datos.
    
- La Seguridad de la capa de transporte (TLS), HTTPS sobre SSL (HTTPS) y Mutual TLS (MTLS) permiten la autenticación de los extremos y el cifrado de la mensajería instantánea. Las secuencias de audio, vídeo y uso compartido de aplicaciones punto a punto se cifran con el protocolo de transporte seguro en tiempo real (SRTP).
    
- Para la autenticación del usuario se usan los protocolos estándar de la industria, siempre que sea posible.
    
- Windows PowerShell proporciona características de seguridad que están habilitadas de forma predeterminada para que los usuarios no pueden ejecutar fácilmente o sin darse cuenta secuencias de comandos.
    
Estos elementos de seguridad fundamentales funcionan conjuntamente para definir los usuarios de confianza, los servidores, las conexiones y operaciones para ayudar a garantizar una base segura para Skype para Business Server.
  
## <a name="in-this-section"></a>En esta sección

En los temas de esta sección se describen cómo funciona cada uno de estos elementos fundamentales para mejorar la seguridad de su Skype para infraestructura de Business Server.
  
- [Servicios de dominio de Active Directory para Skype para Business Server](active-directory-domain-services.md)
    
- [Control de acceso basado en roles (RBAC) para Skype para Business Server](role-based-access-control-rbac.md)
    
- [Infraestructura de clave pública de Skype para Business Server](public-key-infrastructure-for-skype.md)
    
- [TLS y MTLS para Skype para Business Server](tls-and-mtls.md)
    
- [Cifrado de Skype para Business Server](encryption.md)
    
- [Autenticación de usuario y el cliente para Skype para Business Server](user-and-client-authentication.md)
    
- [Windows PowerShell y Skype para herramientas de administración de Business Server](management-tools.md)
    

