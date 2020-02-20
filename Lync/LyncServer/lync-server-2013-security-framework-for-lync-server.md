---
title: 'Lync Server 2013: marco de seguridad para Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Security framework for Lync Server 2013
ms:assetid: 01131e28-b38e-40d9-8524-06725b9c6608
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481316(v=OCS.15)
ms:contentKeyID: 59893866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 472e15d2206e787abb571885f0155bb0169f7234
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144068"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="security-framework-for-lync-server-2013"></a><span data-ttu-id="fd5e2-102">Marco de seguridad para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd5e2-102">Security framework for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fd5e2-103">_**Última modificación del tema:** 2013-11-08_</span><span class="sxs-lookup"><span data-stu-id="fd5e2-103">_**Topic Last Modified:** 2013-11-08_</span></span>

<span data-ttu-id="fd5e2-104">En esta sección se proporciona información general sobre los elementos fundamentales que forman el marco de seguridad para Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-104">This section provides an overview of the fundamental elements that form the security framework for Microsoft Lync Server 2013.</span></span> <span data-ttu-id="fd5e2-105">Comprender cómo estos elementos funcionan juntos es esencial para tomar decisiones informadas sobre la seguridad de su implementación de Lync Server 2013 en particular.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-105">Understanding how these elements work together is essential to making informed decisions about securing your particular Lync Server 2013 deployment.</span></span>

<span data-ttu-id="fd5e2-106">Estos elementos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="fd5e2-106">These elements are as follows:</span></span>

  - <span data-ttu-id="fd5e2-107">Los Servicios de dominio de Active Directory (AD DS) proporcionan un único repositorio back-end de confianza para las cuentas de usuario y los recursos de red.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-107">Active Directory Domain Services (AD DS) provides a single trusted back-end repository for user accounts and network resources.</span></span>

  - <span data-ttu-id="fd5e2-108">El control de acceso basado en roles (RBAC) le permite delegar tareas administrativas a la vez que mantiene altos estándares de seguridad.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-108">Role-Based Access Control (RBAC) enables you to delegate administrative tasks while maintaining high standards for security.</span></span>

  - <span data-ttu-id="fd5e2-109">La infraestructura de clave pública (PKI) utiliza certificados emitidos por entidades de certificación (CA) de confianza para autenticar los servidores y garantizar la integridad de los datos.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-109">Public Key Infrastructure (PKI) uses certificates issued by trusted certification authorities (CAs) to authenticate servers and ensure data integrity.</span></span>

  - <span data-ttu-id="fd5e2-p102">TLS (Seguridad de la capa de transporte), HTTPS sobre SSL (HTTPS) y MTLS (Mutual TLS) permiten la autenticación de los extremos y el cifrado de la mensajería instantánea. Las secuencias de audio, vídeo y aplicaciones compartidas punto a punto se cifran usando el protocolo de transporte seguro en tiempo real (SRTP).</span><span class="sxs-lookup"><span data-stu-id="fd5e2-p102">Transport Layer Security (TLS), HTTPS over SSL (HTTPS), and mutual TLS (MTLS) enable endpoint authentication and IM encryption. Point-to-point audio, video, and application sharing streams are encrypted using Secure Real-Time Transport Protocol (SRTP).</span></span>

  - <span data-ttu-id="fd5e2-112">Para la autenticación se usan los protocolos estándar de la industria, siempre que sea posible.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-112">Industry-standard protocols for user authentication, where possible.</span></span>

  - <span data-ttu-id="fd5e2-113">Windows PowerShell proporciona funciones de seguridad habilitadas de forma predeterminada para que los usuarios no puedan ejecutar scripts fácilmente o sin darse cuenta.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-113">Windows PowerShell provides security features that are enabled by default so that users cannot easily or unknowingly run scripts.</span></span>

<span data-ttu-id="fd5e2-114">Estos elementos fundamentales de seguridad funcionan en conjunto para definir usuarios, servidores, conexiones y operaciones de confianza para ayudar a garantizar una base segura para Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-114">These fundamental security elements work together to define trusted users, servers, connections, and operations to help ensure a secure foundation for Lync Server 2013.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="fd5e2-115">En esta sección</span><span class="sxs-lookup"><span data-stu-id="fd5e2-115">In This Section</span></span>

<span data-ttu-id="fd5e2-116">En los temas de esta sección se describe cómo funciona cada uno de estos elementos fundamentales para mejorar la seguridad de la infraestructura de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-116">The topics in this section describe how each of these fundamental elements works to enhance the security of your Lync Server infrastructure.</span></span>

  - [<span data-ttu-id="fd5e2-117">Servicios de dominio de Active Directory para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd5e2-117">Active Directory Domain Services for Lync Server 2013</span></span>](lync-server-2013-active-directory-domain-services-for-lync-server.md)

  - [<span data-ttu-id="fd5e2-118">Control de acceso basado en roles (RBAC) para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd5e2-118">Role-based access control (RBAC) for Lync Server 2013</span></span>](lync-server-2013-role-based-access-control-rbac.md)

  - [<span data-ttu-id="fd5e2-119">Infraestructura de clave pública para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd5e2-119">Public Key Infrastructure for Lync Server 2013</span></span>](lync-server-2013-public-key-infrastructure.md)

  - [<span data-ttu-id="fd5e2-120">TLS y MTLS para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd5e2-120">TLS and MTLS for Lync Server 2013</span></span>](lync-server-2013-tls-and-mtls.md)

  - [<span data-ttu-id="fd5e2-121">Cifrado para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd5e2-121">Encryption for Lync Server 2013</span></span>](lync-server-2013-encryption.md)

  - [<span data-ttu-id="fd5e2-122">Autenticación de usuario y cliente para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd5e2-122">User and client authentication for Lync Server 2013</span></span>](lync-server-2013-user-and-client-authentication.md)

  - [<span data-ttu-id="fd5e2-123">Herramientas de administración de Windows PowerShell y Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd5e2-123">Windows PowerShell and Lync Server 2013 management tools</span></span>](lync-server-2013-windows-powershell-and-lync-server-management-tools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

