---
title: Compatibilidad con infraestructura de certificados 2013 de Lync Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate infrastructure support
ms:assetid: 47aa5c95-eb60-4d4b-81d5-7fdaef1a1145
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425950(v=OCS.15)
ms:contentKeyID: 48184047
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b17c6f53130d5f0cca96ce3b719001029398d91c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508007"
---
# <a name="certificate-infrastructure-support-in-lync-server-2013"></a><span data-ttu-id="acb59-102">Compatibilidad con la infraestructura de certificados en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="acb59-102">Certificate infrastructure support in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="acb59-103">_**Última modificación del tema:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="acb59-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="acb59-104">Lync Server 2013 requiere una infraestructura de clave pública (PKI) para admitir conexiones de seguridad de la capa de transporte (TLS) y TLS mutua (MTLS).</span><span class="sxs-lookup"><span data-stu-id="acb59-104">Lync Server 2013 requires a public key infrastructure (PKI) to support Transport Layer Security (TLS) and mutual TLS (MTLS) connections.</span></span> <span data-ttu-id="acb59-105">De forma predeterminada, Lync Server 2013 está configurado para usar TLS para las conexiones de cliente a servidor.</span><span class="sxs-lookup"><span data-stu-id="acb59-105">By default, Lync Server 2013 is configured to use TLS for client-to-server connections.</span></span> <span data-ttu-id="acb59-106">MTLS se usa para las conexiones entre servidores.</span><span class="sxs-lookup"><span data-stu-id="acb59-106">MTLS is used for connections between servers.</span></span>

<span data-ttu-id="acb59-107">Los certificados MTLS deben ser emitidos por entidades de certificación (CA) de confianza para Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="acb59-107">MTLS certificates must be issued by trusted certification authorities (CAs) for Lync Server 2013.</span></span> <span data-ttu-id="acb59-108">Lync Server admite certificados que se emiten desde las siguientes entidades de certificación:</span><span class="sxs-lookup"><span data-stu-id="acb59-108">Lync Server supports certificates that are issued from the following CAs:</span></span>

  - <span data-ttu-id="acb59-109">Certificados emitidos por una entidad de certificación interna:</span><span class="sxs-lookup"><span data-stu-id="acb59-109">Certificates issued from an internal CA:</span></span>
    
      - <span data-ttu-id="acb59-110">La entidad de certificación del sistema operativo Windows Server 2003</span><span class="sxs-lookup"><span data-stu-id="acb59-110">The Windows Server 2003 operating system CA</span></span>
    
      - <span data-ttu-id="acb59-111">La entidad de certificación del sistema operativo Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="acb59-111">The Windows Server 2008 operating system CA</span></span>
    
      - <span data-ttu-id="acb59-112">La entidad de certificación del sistema operativo Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="acb59-112">The Windows Server 2008 R2 operating system CA</span></span>
    
      - <span data-ttu-id="acb59-113">La entidad de certificación del sistema operativo Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="acb59-113">The Windows Server 2012 operating system CA</span></span>
    
      - <span data-ttu-id="acb59-114">La entidad de certificación del sistema operativo Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="acb59-114">The Windows Server 2012 R2 operating system CA</span></span>

  - <span data-ttu-id="acb59-115">Certificados emitidos por una entidad de certificación pública</span><span class="sxs-lookup"><span data-stu-id="acb59-115">Certificates issued from a public CA</span></span>

<span data-ttu-id="acb59-116">La comunicación con otras aplicaciones y servidores, como Exchange 2013, requiere un certificado que sea compatible con las demás aplicaciones y productos.</span><span class="sxs-lookup"><span data-stu-id="acb59-116">Communication with other applications and servers, such as Exchange 2013, requires a certificate that is supported by the other applications and products.</span></span> <span data-ttu-id="acb59-117">Para la versión 2013, Lync Server 2013 y otros productos de servidor de Microsoft, incluidos Exchange 2013 y SharePoint Server, admiten el protocolo Open Authorization (OAuth) para la autenticación y autorización de servidor a servidor.</span><span class="sxs-lookup"><span data-stu-id="acb59-117">For the 2013 release, Lync Server 2013 and other Microsoft server products, including Exchange 2013 and SharePoint Server, support the Open Authorization (OAuth) protocol for server-to-server authentication and authorization.</span></span> <span data-ttu-id="acb59-118">Para obtener más información, consulte [Managing Server-to-Server Authentication (OAuth) and Partner Applications in Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) en la documentación sobre implementación o sobre operaciones.</span><span class="sxs-lookup"><span data-stu-id="acb59-118">For details, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) in the Deployment documentation or the Operations documentation.</span></span>

<span data-ttu-id="acb59-119">Para las conexiones de clientes que ejecutan el sistema operativo Windows 7, el sistema operativo Windows Server 2008 R2 y Microsoft Office Communicator 2007 Phone Edition, Lync Server 2013 incluye soporte para certificados (pero no obligatorios) firmados con la función de hash criptográfica SHA-256.</span><span class="sxs-lookup"><span data-stu-id="acb59-119">For connections from clients running Windows 7 operating system, Windows Server 2008 R2 operating system, and Microsoft Office Communicator 2007 Phone Edition, Lync Server 2013 includes support for (but does not require) certificates signed using the SHA-256 cryptographic hash function.</span></span> <span data-ttu-id="acb59-120">Para permitir el acceso externo mediante SHA-256, el certificado externo lo emite una CA pública que usa SHA-256.</span><span class="sxs-lookup"><span data-stu-id="acb59-120">To support external access using SHA-256, the external certificate is issued by a public CA using SHA-256.</span></span>

<span data-ttu-id="acb59-121">Para obtener más información sobre los requisitos de certificado, consulte [Certificate Infrastructure Requirements for Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md) en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="acb59-121">For details about certificate requirements, see [Certificate infrastructure requirements for Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md) in the Planning documentation.</span></span> <span data-ttu-id="acb59-122">Para obtener más información sobre el uso de caracteres comodín con certificados, consulte [compatibilidad con certificados comodín en Lync Server 2013](lync-server-2013-wildcard-certificate-support.md) en la documentación sobre compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="acb59-122">For details about use of wildcards with certificates, see [Wildcard certificate support in Lync Server 2013](lync-server-2013-wildcard-certificate-support.md) in the Supportability documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

