---
title: Marco de seguridad para Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 01131e28-b38e-40d9-8524-06725b9c6608
description: En esta sección se proporciona información general sobre los elementos fundamentales que forman el marco de seguridad para Skype Empresarial Server. Comprender el modo en que estos elementos funcionan juntos es esencial para tomar decisiones fundamentadas sobre cómo proteger su implementación Skype Empresarial Server implementación.
ms.openlocfilehash: a0f6513f86d7416f546c6a744fc1b40df7c7137a18dae5d76fcf18166a4f2eb1
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54337718"
---
# <a name="security-framework-for-skype-for-business-server"></a>Marco de seguridad para Skype Empresarial Server
 
En esta sección se proporciona información general sobre los elementos fundamentales que forman el marco de seguridad para Skype Empresarial Server. Comprender el modo en que estos elementos funcionan juntos es esencial para tomar decisiones fundamentadas sobre cómo proteger su implementación Skype Empresarial Server implementación.
  
Estos elementos son los siguientes:
  
- Los Servicios de dominio de Active Directory (AD DS) proporcionan un único repositorio back-end de confianza para las cuentas de usuario y los recursos de red.
    
- Role-Based control de acceso (RBAC) permite delegar tareas administrativas al mismo tiempo que se mantienen altos estándares de seguridad.
    
- Public Key Infrastructure (PKI) usa certificados emitidos por entidades de certificación de confianza (CA) para autenticar servidores y garantizar la integridad de los datos.
    
- TLS (Seguridad de la capa de transporte), HTTPS sobre SSL (HTTPS) y MTLS (Mutual TLS) permiten la autenticación de los extremos y el cifrado de la mensajería instantánea. Las secuencias de audio, vídeo y aplicaciones compartidas punto a punto se cifran usando el protocolo de transporte seguro en tiempo real (SRTP).
    
- Para la autenticación se usan los protocolos estándar de la industria, siempre que sea posible.
    
- Windows PowerShell proporciona funciones de seguridad habilitadas de forma predeterminada para que los usuarios no puedan ejecutar scripts fácilmente o sin darse cuenta.
    
Estos elementos de seguridad fundamentales funcionan juntos para definir usuarios, servidores, conexiones y operaciones de confianza para ayudar a garantizar una base segura para Skype Empresarial Server.
  
## <a name="in-this-section"></a>En esta sección

En los temas de esta sección se describe cómo funciona cada uno de estos elementos fundamentales para mejorar la seguridad de la Skype Empresarial Server infraestructura.
  
- [Servicios de dominio de Active Directory para Skype Empresarial Server](active-directory-domain-services.md)
    
- [Control de acceso basado en roles (RBAC) para Skype Empresarial Server](role-based-access-control-rbac.md)
    
- [Infraestructura de clave pública para Skype Empresarial Server](public-key-infrastructure-for-skype.md)
    
- [TLS y MTLS para Skype Empresarial Server](tls-and-mtls.md)
    
- [Cifrado para Skype Empresarial Server](encryption.md)
    
- [Autenticación de usuario y cliente para Skype Empresarial Server](user-and-client-authentication.md)
    
- [Windows PowerShell y Skype Empresarial Server de administración](management-tools.md)
    

