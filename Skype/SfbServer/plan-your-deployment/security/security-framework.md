---
title: Marco de seguridad para Skype Empresarial Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 7/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 01131e28-b38e-40d9-8524-06725b9c6608
description: Esta sección proporciona una visión general de los elementos fundamentales que forman el marco de seguridad de Skype para Business Server 2015. Comprender cómo funcionan juntos estos elementos es esencial para tomar decisiones acerca de cómo proteger su particular Skype para la implementación de Business Server 2015.
ms.openlocfilehash: c29941a3e903b6318db2de0453589b5017e6f51b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="security-framework-for-skype-for-business-server-2015"></a>Marco de seguridad para Skype Empresarial Server 2015
 
Esta sección proporciona una visión general de los elementos fundamentales que forman el marco de seguridad de Skype para Business Server 2015. Comprender cómo funcionan juntos estos elementos es esencial para tomar decisiones acerca de cómo proteger su particular Skype para la implementación de Business Server 2015.
  
Dichos elementos son los siguientes:
  
- Los servicios de dominio de Active Directory (AD DS) proporciona un único repositorio de back-end de confianza para las cuentas de usuario y recursos de la red.
    
- El control de acceso basado en roles (RBAC) le permite delegar tareas administrativas y mantener, al mismo tiempo, altos estándares de seguridad.
    
- La infraestructura de clave pública (PKI) utiliza certificados emitidos por entidades de certificación (CA) de confianza para autenticar los servidores y garantizar la integridad de los datos.
    
- La Seguridad de la capa de transporte (TLS), HTTPS sobre SSL (HTTPS) y Mutual TLS (MTLS) permiten la autenticación de los extremos y el cifrado de la mensajería instantánea. Las secuencias de audio, vídeo y uso compartido de aplicaciones punto a punto se cifran con el protocolo de transporte seguro en tiempo real (SRTP).
    
- Para la autenticación del usuario se usan los protocolos estándar de la industria, siempre que sea posible.
    
- Windows PowerShell proporciona características de seguridad que están habilitadas de forma predeterminada para que los usuarios no pueden ejecutar fácilmente o sin darse cuenta las secuencias de comandos.
    
Estos elementos fundamentales de seguridad trabajan juntos para definir la confianza de los usuarios, servidores, conexiones y operaciones para ayudar a garantizar una base segura de Skype para Business Server 2015.
  
## <a name="in-this-section"></a>En esta sección

En los temas de esta sección describen cómo funciona cada uno de estos elementos fundamentales para mejorar la seguridad de su Skype para infraestructura de servidores empresariales.
  
- [Servicios de dominio de Active Directory para Skype para Business Server 2015](active-directory-domain-services.md)
    
- [Control de acceso basado en roles (RBAC) de Skype para Business Server 2015](role-based-access-control-rbac.md)
    
- [Infraestructura de claves públicas para Skype para Business Server 2015](public-key-infrastructure-for-skype.md)
    
- [TLS y MTLS para Skype para Business Server 2015](tls-and-mtls.md)
    
- [Cifrado de Skype para Business Server 2015](encryption.md)
    
- [Autenticación de cliente y usuario de Skype para Business Server 2015](user-and-client-authentication.md)
    
- [Windows PowerShell y Skype para herramientas de administración de servidor de negocios 2015](management-tools.md)
    

