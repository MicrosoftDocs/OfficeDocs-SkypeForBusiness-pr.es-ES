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
# <a name="security-framework-for-skype-for-business-server-2015"></a><span data-ttu-id="efd89-104">Marco de seguridad para Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="efd89-104">Security framework for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="efd89-105">Esta sección proporciona una visión general de los elementos fundamentales que forman el marco de seguridad de Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="efd89-105">This section provides an overview of the fundamental elements that form the security framework for Skype for Business Server 2015.</span></span> <span data-ttu-id="efd89-106">Comprender cómo funcionan juntos estos elementos es esencial para tomar decisiones acerca de cómo proteger su particular Skype para la implementación de Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="efd89-106">Understanding how these elements work together is essential to making informed decisions about securing your particular Skype for Business Server 2015 deployment.</span></span>
  
<span data-ttu-id="efd89-107">Dichos elementos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="efd89-107">These elements are as follows:</span></span>
  
- <span data-ttu-id="efd89-108">Los servicios de dominio de Active Directory (AD DS) proporciona un único repositorio de back-end de confianza para las cuentas de usuario y recursos de la red.</span><span class="sxs-lookup"><span data-stu-id="efd89-108">Active Directory Domain Services (AD DS) provides a single trusted back-end repository for user accounts and network resources.</span></span>
    
- <span data-ttu-id="efd89-109">El control de acceso basado en roles (RBAC) le permite delegar tareas administrativas y mantener, al mismo tiempo, altos estándares de seguridad.</span><span class="sxs-lookup"><span data-stu-id="efd89-109">Role-Based Access Control (RBAC) enables you to delegate administrative tasks while maintaining high standards for security.</span></span>
    
- <span data-ttu-id="efd89-110">La infraestructura de clave pública (PKI) utiliza certificados emitidos por entidades de certificación (CA) de confianza para autenticar los servidores y garantizar la integridad de los datos.</span><span class="sxs-lookup"><span data-stu-id="efd89-110">Public Key Infrastructure (PKI) uses certificates issued by trusted certification authorities (CAs) to authenticate servers and ensure data integrity.</span></span>
    
- <span data-ttu-id="efd89-p103">La Seguridad de la capa de transporte (TLS), HTTPS sobre SSL (HTTPS) y Mutual TLS (MTLS) permiten la autenticación de los extremos y el cifrado de la mensajería instantánea. Las secuencias de audio, vídeo y uso compartido de aplicaciones punto a punto se cifran con el protocolo de transporte seguro en tiempo real (SRTP).</span><span class="sxs-lookup"><span data-stu-id="efd89-p103">Transport Layer Security (TLS), HTTPS over SSL (HTTPS), and mutual TLS (MTLS) enable endpoint authentication and IM encryption. Point-to-point audio, video, and application sharing streams are encrypted using Secure Real-Time Transport Protocol (SRTP).</span></span>
    
- <span data-ttu-id="efd89-113">Para la autenticación del usuario se usan los protocolos estándar de la industria, siempre que sea posible.</span><span class="sxs-lookup"><span data-stu-id="efd89-113">Industry-standard protocols for user authentication, where possible.</span></span>
    
- <span data-ttu-id="efd89-114">Windows PowerShell proporciona características de seguridad que están habilitadas de forma predeterminada para que los usuarios no pueden ejecutar fácilmente o sin darse cuenta las secuencias de comandos.</span><span class="sxs-lookup"><span data-stu-id="efd89-114">Windows PowerShell provides security features that are enabled by default so that users cannot easily or unknowingly run scripts.</span></span>
    
<span data-ttu-id="efd89-115">Estos elementos fundamentales de seguridad trabajan juntos para definir la confianza de los usuarios, servidores, conexiones y operaciones para ayudar a garantizar una base segura de Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="efd89-115">These fundamental security elements work together to define trusted users, servers, connections, and operations to help ensure a secure foundation for Skype for Business Server 2015.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="efd89-116">En esta sección</span><span class="sxs-lookup"><span data-stu-id="efd89-116">In this section</span></span>

<span data-ttu-id="efd89-117">En los temas de esta sección describen cómo funciona cada uno de estos elementos fundamentales para mejorar la seguridad de su Skype para infraestructura de servidores empresariales.</span><span class="sxs-lookup"><span data-stu-id="efd89-117">The topics in this section describe how each of these fundamental elements works to enhance the security of your Skype for Business Server infrastructure.</span></span>
  
- [<span data-ttu-id="efd89-118">Servicios de dominio de Active Directory para Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="efd89-118">Active Directory Domain Services for Skype for Business Server 2015</span></span>](active-directory-domain-services.md)
    
- [<span data-ttu-id="efd89-119">Control de acceso basado en roles (RBAC) de Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="efd89-119">Role-based access control (RBAC) for Skype for Business Server 2015</span></span>](role-based-access-control-rbac.md)
    
- [<span data-ttu-id="efd89-120">Infraestructura de claves públicas para Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="efd89-120">Public Key Infrastructure for Skype for Business Server 2015</span></span>](public-key-infrastructure-for-skype.md)
    
- [<span data-ttu-id="efd89-121">TLS y MTLS para Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="efd89-121">TLS and MTLS for Skype for Business Server 2015</span></span>](tls-and-mtls.md)
    
- [<span data-ttu-id="efd89-122">Cifrado de Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="efd89-122">Encryption for Skype for Business Server 2015</span></span>](encryption.md)
    
- [<span data-ttu-id="efd89-123">Autenticación de cliente y usuario de Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="efd89-123">User and client authentication for Skype for Business Server 2015</span></span>](user-and-client-authentication.md)
    
- [<span data-ttu-id="efd89-124">Windows PowerShell y Skype para herramientas de administración de servidor de negocios 2015</span><span class="sxs-lookup"><span data-stu-id="efd89-124">Windows PowerShell and Skype for Business Server 2015 management tools</span></span>](management-tools.md)
    

