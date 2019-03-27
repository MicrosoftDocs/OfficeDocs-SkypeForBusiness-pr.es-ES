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
# <a name="security-framework-for-skype-for-business-server"></a><span data-ttu-id="828e9-104">Marco de seguridad de Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="828e9-104">Security framework for Skype for Business Server</span></span>
 
<span data-ttu-id="828e9-105">En esta sección se proporciona una visión general de los elementos fundamentales que constituyen el marco de seguridad de Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="828e9-105">This section provides an overview of the fundamental elements that form the security framework for Skype for Business Server.</span></span> <span data-ttu-id="828e9-106">Descripción de cómo funcionan conjuntamente estos elementos es fundamental para tomar decisiones fundamentadas sobre cómo asegurar su Skype determinado para la implementación de Business Server.</span><span class="sxs-lookup"><span data-stu-id="828e9-106">Understanding how these elements work together is essential to making informed decisions about securing your particular Skype for Business Server deployment.</span></span>
  
<span data-ttu-id="828e9-107">Dichos elementos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="828e9-107">These elements are as follows:</span></span>
  
- <span data-ttu-id="828e9-108">Los servicios de dominio de Active Directory (AD DS) proporciona un único repositorio back-end de confianza para las cuentas de usuario y recursos de red.</span><span class="sxs-lookup"><span data-stu-id="828e9-108">Active Directory Domain Services (AD DS) provides a single trusted back-end repository for user accounts and network resources.</span></span>
    
- <span data-ttu-id="828e9-109">El control de acceso basado en roles (RBAC) le permite delegar tareas administrativas y mantener, al mismo tiempo, altos estándares de seguridad.</span><span class="sxs-lookup"><span data-stu-id="828e9-109">Role-Based Access Control (RBAC) enables you to delegate administrative tasks while maintaining high standards for security.</span></span>
    
- <span data-ttu-id="828e9-110">La infraestructura de clave pública (PKI) utiliza certificados emitidos por entidades de certificación (CA) de confianza para autenticar los servidores y garantizar la integridad de los datos.</span><span class="sxs-lookup"><span data-stu-id="828e9-110">Public Key Infrastructure (PKI) uses certificates issued by trusted certification authorities (CAs) to authenticate servers and ensure data integrity.</span></span>
    
- <span data-ttu-id="828e9-p103">La Seguridad de la capa de transporte (TLS), HTTPS sobre SSL (HTTPS) y Mutual TLS (MTLS) permiten la autenticación de los extremos y el cifrado de la mensajería instantánea. Las secuencias de audio, vídeo y uso compartido de aplicaciones punto a punto se cifran con el protocolo de transporte seguro en tiempo real (SRTP).</span><span class="sxs-lookup"><span data-stu-id="828e9-p103">Transport Layer Security (TLS), HTTPS over SSL (HTTPS), and mutual TLS (MTLS) enable endpoint authentication and IM encryption. Point-to-point audio, video, and application sharing streams are encrypted using Secure Real-Time Transport Protocol (SRTP).</span></span>
    
- <span data-ttu-id="828e9-113">Para la autenticación del usuario se usan los protocolos estándar de la industria, siempre que sea posible.</span><span class="sxs-lookup"><span data-stu-id="828e9-113">Industry-standard protocols for user authentication, where possible.</span></span>
    
- <span data-ttu-id="828e9-114">Windows PowerShell proporciona características de seguridad que están habilitadas de forma predeterminada para que los usuarios no pueden ejecutar fácilmente o sin darse cuenta secuencias de comandos.</span><span class="sxs-lookup"><span data-stu-id="828e9-114">Windows PowerShell provides security features that are enabled by default so that users cannot easily or unknowingly run scripts.</span></span>
    
<span data-ttu-id="828e9-115">Estos elementos de seguridad fundamentales funcionan conjuntamente para definir los usuarios de confianza, los servidores, las conexiones y operaciones para ayudar a garantizar una base segura para Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="828e9-115">These fundamental security elements work together to define trusted users, servers, connections, and operations to help ensure a secure foundation for Skype for Business Server.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="828e9-116">En esta sección</span><span class="sxs-lookup"><span data-stu-id="828e9-116">In this section</span></span>

<span data-ttu-id="828e9-117">En los temas de esta sección se describen cómo funciona cada uno de estos elementos fundamentales para mejorar la seguridad de su Skype para infraestructura de Business Server.</span><span class="sxs-lookup"><span data-stu-id="828e9-117">The topics in this section describe how each of these fundamental elements works to enhance the security of your Skype for Business Server infrastructure.</span></span>
  
- [<span data-ttu-id="828e9-118">Servicios de dominio de Active Directory para Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="828e9-118">Active Directory Domain Services for Skype for Business Server</span></span>](active-directory-domain-services.md)
    
- [<span data-ttu-id="828e9-119">Control de acceso basado en roles (RBAC) para Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="828e9-119">Role-based access control (RBAC) for Skype for Business Server</span></span>](role-based-access-control-rbac.md)
    
- [<span data-ttu-id="828e9-120">Infraestructura de clave pública de Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="828e9-120">Public Key Infrastructure for Skype for Business Server</span></span>](public-key-infrastructure-for-skype.md)
    
- [<span data-ttu-id="828e9-121">TLS y MTLS para Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="828e9-121">TLS and MTLS for Skype for Business Server</span></span>](tls-and-mtls.md)
    
- [<span data-ttu-id="828e9-122">Cifrado de Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="828e9-122">Encryption for Skype for Business Server</span></span>](encryption.md)
    
- [<span data-ttu-id="828e9-123">Autenticación de usuario y el cliente para Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="828e9-123">User and client authentication for Skype for Business Server</span></span>](user-and-client-authentication.md)
    
- [<span data-ttu-id="828e9-124">Windows PowerShell y Skype para herramientas de administración de Business Server</span><span class="sxs-lookup"><span data-stu-id="828e9-124">Windows PowerShell and Skype for Business Server management tools</span></span>](management-tools.md)
    

