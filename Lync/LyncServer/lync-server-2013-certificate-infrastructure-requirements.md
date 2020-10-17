---
title: Requisitos de infraestructura de certificados 2013 de Lync Server
description: Requisitos de infraestructura de certificados 2013 de Lync Server.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate infrastructure requirements
ms:assetid: 0051aa23-0bbe-4e72-9f29-e01c6bcc6190
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398066(v=OCS.15)
ms:contentKeyID: 48183219
ms.date: 06/23/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 02c7e69f272c29f0ba9386f403db326b4d39bbff
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544296"
---
# <a name="certificate-infrastructure-requirements-for-lync-server-2013"></a><span data-ttu-id="e90d6-103">Requisitos de infraestructura de certificados para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e90d6-103">Certificate infrastructure requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e90d6-104">_**Última modificación del tema:** 2016-06-23_</span><span class="sxs-lookup"><span data-stu-id="e90d6-104">_**Topic Last Modified:** 2016-06-23_</span></span>

<span data-ttu-id="e90d6-105">Lync Server 2013 requiere una infraestructura de clave pública (PKI) para admitir conexiones TLS y TLS mutua (MTLS).</span><span class="sxs-lookup"><span data-stu-id="e90d6-105">Lync Server 2013 requires a public key infrastructure (PKI) to support TLS and mutual TLS (MTLS) connections.</span></span>

<span data-ttu-id="e90d6-106">Lync Server usa certificados para los propósitos siguientes:</span><span class="sxs-lookup"><span data-stu-id="e90d6-106">Lync Server uses certificates for the following purposes:</span></span>

  - <span data-ttu-id="e90d6-107">Conexiones TLS entre clientes y servidores</span><span class="sxs-lookup"><span data-stu-id="e90d6-107">TLS connections between client and server</span></span>

  - <span data-ttu-id="e90d6-108">Conexiones MTLS entre servidores</span><span class="sxs-lookup"><span data-stu-id="e90d6-108">MTLS connections between servers</span></span>

  - <span data-ttu-id="e90d6-109">Federación mediante la detección automática basada en DNS de los socios</span><span class="sxs-lookup"><span data-stu-id="e90d6-109">Federation using automatic DNS discovery of partners</span></span>

  - <span data-ttu-id="e90d6-110">Acceso de usuarios remotos a la mensajería instantánea (IM)</span><span class="sxs-lookup"><span data-stu-id="e90d6-110">Remote user access for instant messaging (IM)</span></span>

  - <span data-ttu-id="e90d6-111">Acceso de usuarios externos a sesiones de audio/vídeo (A/V), a uso compartido de aplicaciones y a conferencias</span><span class="sxs-lookup"><span data-stu-id="e90d6-111">External user access to audio/video (A/V) sessions, application sharing, and conferencing</span></span>

  - <span data-ttu-id="e90d6-112">Solicitudes móviles mediante detección automática de servicios web</span><span class="sxs-lookup"><span data-stu-id="e90d6-112">Mobile requests using automatic discovery of Web Services</span></span>

<span data-ttu-id="e90d6-113">Para Lync Server, se aplican los siguientes requisitos comunes:</span><span class="sxs-lookup"><span data-stu-id="e90d6-113">For Lync Server, the following common requirements apply:</span></span>

  - <span data-ttu-id="e90d6-114">Todos los certificados de servidor deben admitir la autorización de servidor (EKU de servidor).</span><span class="sxs-lookup"><span data-stu-id="e90d6-114">All server certificates must support server authorization (Server EKU).</span></span>

  - <span data-ttu-id="e90d6-115">Todos los certificados de servidor deben contener un punto de distribución CRL (CDP).</span><span class="sxs-lookup"><span data-stu-id="e90d6-115">All server certificates must contain a CRL Distribution Point (CDP).</span></span>

  - <span data-ttu-id="e90d6-116">Todos los certificados deben estar firmados con un algoritmo de firma compatible con el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="e90d6-116">All certificates must be signed using a signing algorithm supported by the operating system.</span></span> <span data-ttu-id="e90d6-117">Lync Server 2013 admite el conjunto de tamaños de compendio SHA-1 y SHA-2 (224, 256, 384 y 512 bits) y cumple o supera los requisitos del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="e90d6-117">Lync Server 2013 supports the SHA-1 and SHA-2 suite of digest sizes (224, 256, 384 and 512-bit), and meets or exceeds the operating system requirements.</span></span> <span data-ttu-id="e90d6-118">Para compatibilidad con sistemas operativos, consulte [https://go.microsoft.com/fwlink/?LinkId=287002](https://go.microsoft.com/fwlink/?linkid=287002) .</span><span class="sxs-lookup"><span data-stu-id="e90d6-118">For operating system support, see [https://go.microsoft.com/fwlink/?LinkId=287002](https://go.microsoft.com/fwlink/?linkid=287002).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e90d6-119">No se admite el uso del algoritmo de firma RSASSA-PSS, lo que puede producir errores en los problemas de inicio de sesión y desvío de llamadas, entre otros.</span><span class="sxs-lookup"><span data-stu-id="e90d6-119">Using the RSASSA-PSS signature algorithm is unsupported, and may lead to errors on login and call forwarding issues, among other problems.</span></span>

    
    </div>

  - <span data-ttu-id="e90d6-120">La inscripción automática se admite para los servidores internos que ejecutan Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e90d6-120">Auto-enrollment is supported for internal servers running Lync Server.</span></span>

  - <span data-ttu-id="e90d6-121">La inscripción automática no es compatible con los servidores perimetrales de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e90d6-121">Auto-enrollment is not supported for Lync Server Edge Servers.</span></span>

  - <span data-ttu-id="e90d6-122">Cuando envíe una solicitud de certificado web a una entidad de certificación de Windows Server 2003, deberá hacerlo desde un equipo que ejecute Windows Server 2003 con SP2 o Windows XP.</span><span class="sxs-lookup"><span data-stu-id="e90d6-122">When you submit a web-based certificate request to a Windows Server 2003 CA, you must submit it from a computer running either Windows Server 2003 with SP2 or Windows XP.</span></span>
    
    <span data-ttu-id="e90d6-123">Tenga en cuenta que aunque KB922706 ofrece soporte técnico para resolver problemas relacionados con los certificados web de inscripción de una inscripción web de los servicios de certificados de Windows Server 2003, no permite el uso de Windows Server 2008, Windows Vista o Windows 7 para solicitar un certificado desde una entidad de certificación de Windows Server 2003.</span><span class="sxs-lookup"><span data-stu-id="e90d6-123">Note that although KB922706 provides support for resolving issues with enrolling web certificates against a Windows Server 2003 Certificate Services web enrollment, it does not make it possible to use Windows Server 2008, Windows Vista, or Windows 7 to request a certificate from a Windows Server 2003 CA.</span></span>

  - <span data-ttu-id="e90d6-124">Se admiten longitudes de clave de cifrado de 1024, 2048 y 4096.</span><span class="sxs-lookup"><span data-stu-id="e90d6-124">Encryption key lengths of 1024, 2048, and 4096 are supported.</span></span> <span data-ttu-id="e90d6-125">Se recomiendan longitudes de clave de 2048 y posteriores.</span><span class="sxs-lookup"><span data-stu-id="e90d6-125">Key lengths of 2048 and greater are recommended.</span></span>

  - <span data-ttu-id="e90d6-126">El algoritmo de síntesis predeterminada, o firma de hash, es RSA.</span><span class="sxs-lookup"><span data-stu-id="e90d6-126">The default digest, or hash signing, algorithm is RSA.</span></span> <span data-ttu-id="e90d6-127">\_También se admiten los algoritmos de P256 ECDH, ECDH \_ P384 y \_ P521 ECDH.</span><span class="sxs-lookup"><span data-stu-id="e90d6-127">The ECDH\_P256, ECDH\_P384, and ECDH\_P521 algorithms are also supported.</span></span> 

<div>

## <a name="in-this-section"></a><span data-ttu-id="e90d6-128">En esta sección</span><span class="sxs-lookup"><span data-stu-id="e90d6-128">In This Section</span></span>

  - [<span data-ttu-id="e90d6-129">Requisitos de certificado para servidores internos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e90d6-129">Certificate requirements for internal servers in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [<span data-ttu-id="e90d6-130">Requisitos de certificado para el acceso de usuarios externos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e90d6-130">Certificate requirements for external user access in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [<span data-ttu-id="e90d6-131">Requisitos de certificado para el servidor de chat persistente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e90d6-131">Certificate requirements for Persistent Chat server in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-persistent-chat-server.md)

  - [<span data-ttu-id="e90d6-132">Requisitos de certificados para movilidad en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e90d6-132">Certificate requirements for mobility in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-mobility.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

