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
# <a name="security-framework-for-skype-for-business-server"></a><span data-ttu-id="2f351-104">Marco de seguridad para Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="2f351-104">Security framework for Skype for Business Server</span></span>
 
<span data-ttu-id="2f351-105">En esta sección se proporciona información general sobre los elementos fundamentales que forman el marco de seguridad de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="2f351-105">This section provides an overview of the fundamental elements that form the security framework for Skype for Business Server.</span></span> <span data-ttu-id="2f351-106">Comprender cómo funcionan conjuntamente estos elementos es esencial para tomar decisiones fundamentadas sobre la protección de su implementación de Skype Empresarial Server en particular.</span><span class="sxs-lookup"><span data-stu-id="2f351-106">Understanding how these elements work together is essential to making informed decisions about securing your particular Skype for Business Server deployment.</span></span>
  
<span data-ttu-id="2f351-107">Estos elementos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="2f351-107">These elements are as follows:</span></span>
  
- <span data-ttu-id="2f351-108">Los Servicios de dominio de Active Directory (AD DS) proporcionan un único repositorio back-end de confianza para las cuentas de usuario y los recursos de red.</span><span class="sxs-lookup"><span data-stu-id="2f351-108">Active Directory Domain Services (AD DS) provides a single trusted back-end repository for user accounts and network resources.</span></span>
    
- <span data-ttu-id="2f351-109">Role-Based Control de acceso remoto (RBAC) permite delegar tareas administrativas a la vez que se mantienen altos estándares de seguridad.</span><span class="sxs-lookup"><span data-stu-id="2f351-109">Role-Based Access Control (RBAC) enables you to delegate administrative tasks while maintaining high standards for security.</span></span>
    
- <span data-ttu-id="2f351-110">La infraestructura de clave pública (PKI) usa certificados emitidos por entidades de certificación (CA) de confianza para autenticar servidores y garantizar la integridad de los datos.</span><span class="sxs-lookup"><span data-stu-id="2f351-110">Public Key Infrastructure (PKI) uses certificates issued by trusted certification authorities (CAs) to authenticate servers and ensure data integrity.</span></span>
    
- <span data-ttu-id="2f351-p103">TLS (Seguridad de la capa de transporte), HTTPS sobre SSL (HTTPS) y MTLS (Mutual TLS) permiten la autenticación de los extremos y el cifrado de la mensajería instantánea. Las secuencias de audio, vídeo y aplicaciones compartidas punto a punto se cifran usando el protocolo de transporte seguro en tiempo real (SRTP).</span><span class="sxs-lookup"><span data-stu-id="2f351-p103">Transport Layer Security (TLS), HTTPS over SSL (HTTPS), and mutual TLS (MTLS) enable endpoint authentication and IM encryption. Point-to-point audio, video, and application sharing streams are encrypted using Secure Real-Time Transport Protocol (SRTP).</span></span>
    
- <span data-ttu-id="2f351-113">Para la autenticación se usan los protocolos estándar de la industria, siempre que sea posible.</span><span class="sxs-lookup"><span data-stu-id="2f351-113">Industry-standard protocols for user authentication, where possible.</span></span>
    
- <span data-ttu-id="2f351-114">Windows PowerShell proporciona funciones de seguridad habilitadas de forma predeterminada para que los usuarios no puedan ejecutar scripts fácilmente o sin darse cuenta.</span><span class="sxs-lookup"><span data-stu-id="2f351-114">Windows PowerShell provides security features that are enabled by default so that users cannot easily or unknowingly run scripts.</span></span>
    
<span data-ttu-id="2f351-115">Estos elementos de seguridad fundamentales funcionan conjuntamente para definir usuarios, servidores, conexiones y operaciones de confianza para ayudar a garantizar una base segura para Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="2f351-115">These fundamental security elements work together to define trusted users, servers, connections, and operations to help ensure a secure foundation for Skype for Business Server.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="2f351-116">En esta sección</span><span class="sxs-lookup"><span data-stu-id="2f351-116">In this section</span></span>

<span data-ttu-id="2f351-117">En los temas de esta sección se describe cómo funciona cada uno de estos elementos fundamentales para mejorar la seguridad de la infraestructura de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="2f351-117">The topics in this section describe how each of these fundamental elements works to enhance the security of your Skype for Business Server infrastructure.</span></span>
  
- [<span data-ttu-id="2f351-118">Servicios de dominio de Active Directory para Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="2f351-118">Active Directory Domain Services for Skype for Business Server</span></span>](active-directory-domain-services.md)
    
- [<span data-ttu-id="2f351-119">Control de acceso basado en roles (RBAC) para Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="2f351-119">Role-based access control (RBAC) for Skype for Business Server</span></span>](role-based-access-control-rbac.md)
    
- [<span data-ttu-id="2f351-120">Infraestructura de clave pública para Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="2f351-120">Public Key Infrastructure for Skype for Business Server</span></span>](public-key-infrastructure-for-skype.md)
    
- [<span data-ttu-id="2f351-121">TLS y MTLS para Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="2f351-121">TLS and MTLS for Skype for Business Server</span></span>](tls-and-mtls.md)
    
- [<span data-ttu-id="2f351-122">Cifrado para Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="2f351-122">Encryption for Skype for Business Server</span></span>](encryption.md)
    
- [<span data-ttu-id="2f351-123">Autenticación de usuario y cliente para Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="2f351-123">User and client authentication for Skype for Business Server</span></span>](user-and-client-authentication.md)
    
- [<span data-ttu-id="2f351-124">Windows PowerShell de administración de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="2f351-124">Windows PowerShell and Skype for Business Server management tools</span></span>](management-tools.md)
    

