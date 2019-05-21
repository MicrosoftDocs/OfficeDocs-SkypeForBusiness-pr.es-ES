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
# <a name="security-framework-for-skype-for-business-server"></a><span data-ttu-id="d712f-104">Marco de seguridad de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="d712f-104">Security framework for Skype for Business Server</span></span>
 
<span data-ttu-id="d712f-105">Esta sección proporciona una descripción general de los elementos fundamentales que forman el marco de seguridad de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="d712f-105">This section provides an overview of the fundamental elements that form the security framework for Skype for Business Server.</span></span> <span data-ttu-id="d712f-106">Comprender el funcionamiento conjunto de estos elementos es esencial para tomar decisiones fundamentadas sobre la seguridad de su implementación particular de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="d712f-106">Understanding how these elements work together is essential to making informed decisions about securing your particular Skype for Business Server deployment.</span></span>
  
<span data-ttu-id="d712f-107">Dichos elementos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="d712f-107">These elements are as follows:</span></span>
  
- <span data-ttu-id="d712f-108">Los servicios de dominio de Active Directory (AD DS) proporcionan un único repositorio de back-end de confianza para cuentas de usuario y recursos de red.</span><span class="sxs-lookup"><span data-stu-id="d712f-108">Active Directory Domain Services (AD DS) provides a single trusted back-end repository for user accounts and network resources.</span></span>
    
- <span data-ttu-id="d712f-109">El control de acceso basado en roles (RBAC) le permite delegar tareas administrativas y mantener, al mismo tiempo, altos estándares de seguridad.</span><span class="sxs-lookup"><span data-stu-id="d712f-109">Role-Based Access Control (RBAC) enables you to delegate administrative tasks while maintaining high standards for security.</span></span>
    
- <span data-ttu-id="d712f-110">La infraestructura de clave pública (PKI) utiliza certificados emitidos por entidades de certificación (CA) de confianza para autenticar los servidores y garantizar la integridad de los datos.</span><span class="sxs-lookup"><span data-stu-id="d712f-110">Public Key Infrastructure (PKI) uses certificates issued by trusted certification authorities (CAs) to authenticate servers and ensure data integrity.</span></span>
    
- <span data-ttu-id="d712f-p103">La Seguridad de la capa de transporte (TLS), HTTPS sobre SSL (HTTPS) y Mutual TLS (MTLS) permiten la autenticación de los extremos y el cifrado de la mensajería instantánea. Las secuencias de audio, vídeo y uso compartido de aplicaciones punto a punto se cifran con el protocolo de transporte seguro en tiempo real (SRTP).</span><span class="sxs-lookup"><span data-stu-id="d712f-p103">Transport Layer Security (TLS), HTTPS over SSL (HTTPS), and mutual TLS (MTLS) enable endpoint authentication and IM encryption. Point-to-point audio, video, and application sharing streams are encrypted using Secure Real-Time Transport Protocol (SRTP).</span></span>
    
- <span data-ttu-id="d712f-113">Para la autenticación del usuario se usan los protocolos estándar de la industria, siempre que sea posible.</span><span class="sxs-lookup"><span data-stu-id="d712f-113">Industry-standard protocols for user authentication, where possible.</span></span>
    
- <span data-ttu-id="d712f-114">Windows PowerShell ofrece características de seguridad que están habilitadas de forma predeterminada para que los usuarios no puedan ejecutar scripts con facilidad o sin problemas.</span><span class="sxs-lookup"><span data-stu-id="d712f-114">Windows PowerShell provides security features that are enabled by default so that users cannot easily or unknowingly run scripts.</span></span>
    
<span data-ttu-id="d712f-115">Estos elementos de seguridad fundamentales trabajan juntos para definir usuarios, servidores, conexiones y operaciones de confianza para ayudar a garantizar una base segura para Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="d712f-115">These fundamental security elements work together to define trusted users, servers, connections, and operations to help ensure a secure foundation for Skype for Business Server.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="d712f-116">En esta sección</span><span class="sxs-lookup"><span data-stu-id="d712f-116">In this section</span></span>

<span data-ttu-id="d712f-117">Los temas de esta sección describen cómo funciona cada uno de estos elementos fundamentales para mejorar la seguridad de su infraestructura de servidor de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="d712f-117">The topics in this section describe how each of these fundamental elements works to enhance the security of your Skype for Business Server infrastructure.</span></span>
  
- [<span data-ttu-id="d712f-118">Servicios de dominio de Active Directory para Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="d712f-118">Active Directory Domain Services for Skype for Business Server</span></span>](active-directory-domain-services.md)
    
- [<span data-ttu-id="d712f-119">Control de acceso basado en roles (RBAC) para Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="d712f-119">Role-based access control (RBAC) for Skype for Business Server</span></span>](role-based-access-control-rbac.md)
    
- [<span data-ttu-id="d712f-120">Infraestructura de clave pública para Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="d712f-120">Public Key Infrastructure for Skype for Business Server</span></span>](public-key-infrastructure-for-skype.md)
    
- [<span data-ttu-id="d712f-121">TLS y MTLS para Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="d712f-121">TLS and MTLS for Skype for Business Server</span></span>](tls-and-mtls.md)
    
- [<span data-ttu-id="d712f-122">Cifrado para Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="d712f-122">Encryption for Skype for Business Server</span></span>](encryption.md)
    
- [<span data-ttu-id="d712f-123">Autenticación de usuarios y clientes para Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="d712f-123">User and client authentication for Skype for Business Server</span></span>](user-and-client-authentication.md)
    
- [<span data-ttu-id="d712f-124">Herramientas de administración de Windows PowerShell y Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="d712f-124">Windows PowerShell and Skype for Business Server management tools</span></span>](management-tools.md)
    

