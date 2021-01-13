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
description: En esta sección se proporciona información general sobre los elementos fundamentales que forman el marco de seguridad de Skype Empresarial Server. Comprender cómo funcionan conjuntamente estos elementos es esencial para tomar decisiones fundamentadas sobre la protección de su implementación de Skype Empresarial Server en particular.
ms.openlocfilehash: 94d2ffac30e029ab6631557a69d6da3ec108657f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832100"
---
# <a name="security-framework-for-skype-for-business-server"></a>Marco de seguridad para Skype Empresarial Server
 
En esta sección se proporciona información general sobre los elementos fundamentales que forman el marco de seguridad de Skype Empresarial Server. Comprender cómo funcionan conjuntamente estos elementos es esencial para tomar decisiones fundamentadas sobre la protección de su implementación de Skype Empresarial Server en particular.
  
Estos elementos son los siguientes:
  
- Los Servicios de dominio de Active Directory (AD DS) proporcionan un único repositorio back-end de confianza para las cuentas de usuario y los recursos de red.
    
- Role-Based Control de acceso remoto (RBAC) permite delegar tareas administrativas a la vez que se mantienen altos estándares de seguridad.
    
- La infraestructura de clave pública (PKI) usa certificados emitidos por entidades de certificación (CA) de confianza para autenticar servidores y garantizar la integridad de los datos.
    
- TLS (Seguridad de la capa de transporte), HTTPS sobre SSL (HTTPS) y MTLS (Mutual TLS) permiten la autenticación de los extremos y el cifrado de la mensajería instantánea. Las secuencias de audio, vídeo y aplicaciones compartidas punto a punto se cifran usando el protocolo de transporte seguro en tiempo real (SRTP).
    
- Para la autenticación se usan los protocolos estándar de la industria, siempre que sea posible.
    
- Windows PowerShell proporciona funciones de seguridad habilitadas de forma predeterminada para que los usuarios no puedan ejecutar scripts fácilmente o sin darse cuenta.
    
Estos elementos de seguridad fundamentales funcionan conjuntamente para definir usuarios, servidores, conexiones y operaciones de confianza para ayudar a garantizar una base segura para Skype Empresarial Server.
  
## <a name="in-this-section"></a>En esta sección

En los temas de esta sección se describe cómo funciona cada uno de estos elementos fundamentales para mejorar la seguridad de la infraestructura de Skype Empresarial Server.
  
- [Servicios de dominio de Active Directory para Skype Empresarial Server](active-directory-domain-services.md)
    
- [Control de acceso basado en roles (RBAC) para Skype Empresarial Server](role-based-access-control-rbac.md)
    
- [Infraestructura de clave pública para Skype Empresarial Server](public-key-infrastructure-for-skype.md)
    
- [TLS y MTLS para Skype Empresarial Server](tls-and-mtls.md)
    
- [Cifrado para Skype Empresarial Server](encryption.md)
    
- [Autenticación de usuario y cliente para Skype Empresarial Server](user-and-client-authentication.md)
    
- [Windows PowerShell de administración de Skype Empresarial Server](management-tools.md)
    

