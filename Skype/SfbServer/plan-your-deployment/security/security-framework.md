---
title: Marco de seguridad de Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 01131e28-b38e-40d9-8524-06725b9c6608
description: Esta sección proporciona una descripción general de los elementos fundamentales que forman el marco de seguridad de Skype empresarial Server. Comprender el funcionamiento conjunto de estos elementos es esencial para tomar decisiones fundamentadas sobre la seguridad de su implementación particular de Skype empresarial Server.
ms.openlocfilehash: 8b82b09a8220139abe62ac4503ad8a7eddc28e99
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296878"
---
# <a name="security-framework-for-skype-for-business-server"></a>Marco de seguridad de Skype empresarial Server
 
Esta sección proporciona una descripción general de los elementos fundamentales que forman el marco de seguridad de Skype empresarial Server. Comprender el funcionamiento conjunto de estos elementos es esencial para tomar decisiones fundamentadas sobre la seguridad de su implementación particular de Skype empresarial Server.
  
Dichos elementos son los siguientes:
  
- Los servicios de dominio de Active Directory (AD DS) proporcionan un único repositorio de back-end de confianza para cuentas de usuario y recursos de red.
    
- El control de acceso basado en roles (RBAC) le permite delegar tareas administrativas y mantener, al mismo tiempo, altos estándares de seguridad.
    
- La infraestructura de clave pública (PKI) utiliza certificados emitidos por entidades de certificación (CA) de confianza para autenticar los servidores y garantizar la integridad de los datos.
    
- La Seguridad de la capa de transporte (TLS), HTTPS sobre SSL (HTTPS) y Mutual TLS (MTLS) permiten la autenticación de los extremos y el cifrado de la mensajería instantánea. Las secuencias de audio, vídeo y uso compartido de aplicaciones punto a punto se cifran con el protocolo de transporte seguro en tiempo real (SRTP).
    
- Para la autenticación del usuario se usan los protocolos estándar de la industria, siempre que sea posible.
    
- Windows PowerShell ofrece características de seguridad que están habilitadas de forma predeterminada para que los usuarios no puedan ejecutar scripts con facilidad o sin problemas.
    
Estos elementos de seguridad fundamentales trabajan juntos para definir usuarios, servidores, conexiones y operaciones de confianza para ayudar a garantizar una base segura para Skype empresarial Server.
  
## <a name="in-this-section"></a>En esta sección

Los temas de esta sección describen cómo funciona cada uno de estos elementos fundamentales para mejorar la seguridad de su infraestructura de servidor de Skype empresarial.
  
- [Servicios de dominio de Active Directory para Skype empresarial Server](active-directory-domain-services.md)
    
- [Control de acceso basado en roles (RBAC) para Skype empresarial Server](role-based-access-control-rbac.md)
    
- [Infraestructura de clave pública para Skype empresarial Server](public-key-infrastructure-for-skype.md)
    
- [TLS y MTLS para Skype empresarial Server](tls-and-mtls.md)
    
- [Cifrado para Skype empresarial Server](encryption.md)
    
- [Autenticación de usuarios y clientes para Skype empresarial Server](user-and-client-authentication.md)
    
- [Herramientas de administración de Windows PowerShell y Skype empresarial](management-tools.md)
    

