---
title: 'Lync Server 2013: Compatibilidad con infraestructura de certificados'
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
ms.openlocfilehash: dc8cb5bdad02de4fcb407d7eb27960258a46dd3e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736814"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-infrastructure-support-in-lync-server-2013"></a><span data-ttu-id="f6d1f-102">Compatibilidad con infraestructura de certificados en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6d1f-102">Certificate infrastructure support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f6d1f-103">_**Última modificación del tema:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="f6d1f-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="f6d1f-104">Lync Server 2013 requiere una infraestructura de clave pública (PKI) para admitir conexiones de seguridad de nivel de transporte (TLS) y TLS Mutual (MTLS).</span><span class="sxs-lookup"><span data-stu-id="f6d1f-104">Lync Server 2013 requires a public key infrastructure (PKI) to support Transport Layer Security (TLS) and mutual TLS (MTLS) connections.</span></span> <span data-ttu-id="f6d1f-105">De forma predeterminada, Lync Server 2013 está configurado para usar TLS para las conexiones entre clientes y servidores.</span><span class="sxs-lookup"><span data-stu-id="f6d1f-105">By default, Lync Server 2013 is configured to use TLS for client-to-server connections.</span></span> <span data-ttu-id="f6d1f-106">MTLS se usa para las conexiones entre servidores.</span><span class="sxs-lookup"><span data-stu-id="f6d1f-106">MTLS is used for connections between servers.</span></span>

<span data-ttu-id="f6d1f-107">Los certificados MTLS deben ser emitidos por entidades de certificación (CA) de confianza para Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f6d1f-107">MTLS certificates must be issued by trusted certification authorities (CAs) for Lync Server 2013.</span></span> <span data-ttu-id="f6d1f-108">Lync Server admite certificados emitidos por las siguientes CA:</span><span class="sxs-lookup"><span data-stu-id="f6d1f-108">Lync Server supports certificates that are issued from the following CAs:</span></span>

  - <span data-ttu-id="f6d1f-109">Certificados emitidos por una entidad de certificación interna:</span><span class="sxs-lookup"><span data-stu-id="f6d1f-109">Certificates issued from an internal CA:</span></span>
    
      - <span data-ttu-id="f6d1f-110">La entidad de certificación del sistema operativo Windows Server 2003</span><span class="sxs-lookup"><span data-stu-id="f6d1f-110">The Windows Server 2003 operating system CA</span></span>
    
      - <span data-ttu-id="f6d1f-111">La entidad de certificación del sistema operativo Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="f6d1f-111">The Windows Server 2008 operating system CA</span></span>
    
      - <span data-ttu-id="f6d1f-112">La entidad de certificación del sistema operativo Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="f6d1f-112">The Windows Server 2008 R2 operating system CA</span></span>
    
      - <span data-ttu-id="f6d1f-113">La entidad de certificación del sistema operativo Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="f6d1f-113">The Windows Server 2012 operating system CA</span></span>
    
      - <span data-ttu-id="f6d1f-114">La entidad de certificación del sistema operativo Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="f6d1f-114">The Windows Server 2012 R2 operating system CA</span></span>

  - <span data-ttu-id="f6d1f-115">Certificados emitidos por una entidad de certificación pública</span><span class="sxs-lookup"><span data-stu-id="f6d1f-115">Certificates issued from a public CA</span></span>

<span data-ttu-id="f6d1f-116">La comunicación con otras aplicaciones y servidores, como Exchange 2013, requiere un certificado que sea compatible con otras aplicaciones y productos.</span><span class="sxs-lookup"><span data-stu-id="f6d1f-116">Communication with other applications and servers, such as Exchange 2013, requires a certificate that is supported by the other applications and products.</span></span> <span data-ttu-id="f6d1f-117">Para la versión 2013, Lync Server 2013 y otros productos de Microsoft Server, incluidos Exchange 2013 y SharePoint Server, admiten el protocolo de autorización abierta (OAuth) para la autenticación y la autorización de servidor a servidor.</span><span class="sxs-lookup"><span data-stu-id="f6d1f-117">For the 2013 release, Lync Server 2013 and other Microsoft server products, including Exchange 2013 and SharePoint Server, support the Open Authorization (OAuth) protocol for server-to-server authentication and authorization.</span></span> <span data-ttu-id="f6d1f-118">Para obtener más información, vea [administrar la autenticación de servidor a servidor (OAuth) y las aplicaciones de socios en Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) en la documentación de implementación o en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="f6d1f-118">For details, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) in the Deployment documentation or the Operations documentation.</span></span>

<span data-ttu-id="f6d1f-119">Para las conexiones de clientes que ejecutan el sistema operativo Windows 7, el sistema operativo Windows Server 2008 R2 y Microsoft Office Communicator 2007 Phone Edition, Lync Server 2013 incluye compatibilidad con certificados (pero no obligatorios) firmados con SHA-256 función hash criptográfica.</span><span class="sxs-lookup"><span data-stu-id="f6d1f-119">For connections from clients running Windows 7 operating system, Windows Server 2008 R2 operating system, and Microsoft Office Communicator 2007 Phone Edition, Lync Server 2013 includes support for (but does not require) certificates signed using the SHA-256 cryptographic hash function.</span></span> <span data-ttu-id="f6d1f-120">Para admitir el acceso externo mediante SHA-256, un certificado externo es emitido por una entidad de certificación pública con SHA-256.</span><span class="sxs-lookup"><span data-stu-id="f6d1f-120">To support external access using SHA-256, the external certificate is issued by a public CA using SHA-256.</span></span>

<span data-ttu-id="f6d1f-121">Para obtener más información sobre los requisitos de certificado, consulte [requisitos de infraestructura de certificados para Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="f6d1f-121">For details about certificate requirements, see [Certificate infrastructure requirements for Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md) in the Planning documentation.</span></span> <span data-ttu-id="f6d1f-122">Para obtener más información sobre el uso de caracteres comodín con certificados, consulte [compatibilidad de certificados comodín en Lync Server 2013](lync-server-2013-wildcard-certificate-support.md) en la documentación de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="f6d1f-122">For details about use of wildcards with certificates, see [Wildcard certificate support in Lync Server 2013](lync-server-2013-wildcard-certificate-support.md) in the Supportability documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

