---
title: 'Lync Server 2013: Requisitos de la infraestructura de certificados'
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
ms.openlocfilehash: 61205cf4ecdac8eac78820442264286f414095ac
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736830"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-infrastructure-requirements-for-lync-server-2013"></a><span data-ttu-id="ff11b-102">Requisitos de la infraestructura de certificados para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ff11b-102">Certificate infrastructure requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ff11b-103">_**Última modificación del tema:** 2016-06-23_</span><span class="sxs-lookup"><span data-stu-id="ff11b-103">_**Topic Last Modified:** 2016-06-23_</span></span>

<span data-ttu-id="ff11b-104">Lync Server 2013 requiere una infraestructura de clave pública (PKI) para que sea compatible con las conexiones TLS y Mutual TLS (MTLS).</span><span class="sxs-lookup"><span data-stu-id="ff11b-104">Lync Server 2013 requires a public key infrastructure (PKI) to support TLS and mutual TLS (MTLS) connections.</span></span>

<span data-ttu-id="ff11b-105">Lync Server usa certificados para los siguientes fines:</span><span class="sxs-lookup"><span data-stu-id="ff11b-105">Lync Server uses certificates for the following purposes:</span></span>

  - <span data-ttu-id="ff11b-106">Conexiones TLS entre el cliente y el servidor</span><span class="sxs-lookup"><span data-stu-id="ff11b-106">TLS connections between client and server</span></span>

  - <span data-ttu-id="ff11b-107">Conexiones MTLS entre servidores</span><span class="sxs-lookup"><span data-stu-id="ff11b-107">MTLS connections between servers</span></span>

  - <span data-ttu-id="ff11b-108">Federación mediante la detección automática de asociados de DNS</span><span class="sxs-lookup"><span data-stu-id="ff11b-108">Federation using automatic DNS discovery of partners</span></span>

  - <span data-ttu-id="ff11b-109">Acceso de usuarios remotos a la mensajería instantánea (MI)</span><span class="sxs-lookup"><span data-stu-id="ff11b-109">Remote user access for instant messaging (IM)</span></span>

  - <span data-ttu-id="ff11b-110">Acceso de usuarios externos a sesiones de audio/vídeo (A/V), uso compartido de aplicaciones y conferencias</span><span class="sxs-lookup"><span data-stu-id="ff11b-110">External user access to audio/video (A/V) sessions, application sharing, and conferencing</span></span>

  - <span data-ttu-id="ff11b-111">Solicitudes de teléfono móvil con el descubrimiento automático de servicios Web</span><span class="sxs-lookup"><span data-stu-id="ff11b-111">Mobile requests using automatic discovery of Web Services</span></span>

<span data-ttu-id="ff11b-112">Para Lync Server, se aplican los siguientes requisitos comunes:</span><span class="sxs-lookup"><span data-stu-id="ff11b-112">For Lync Server, the following common requirements apply:</span></span>

  - <span data-ttu-id="ff11b-113">Todos los certificados de servidor deben admitir la autorización de servidor (EKU de servidor).</span><span class="sxs-lookup"><span data-stu-id="ff11b-113">All server certificates must support server authorization (Server EKU).</span></span>

  - <span data-ttu-id="ff11b-114">Todos los certificados de servidor deben contener un punto de distribución CRL (CDP).</span><span class="sxs-lookup"><span data-stu-id="ff11b-114">All server certificates must contain a CRL Distribution Point (CDP).</span></span>

  - <span data-ttu-id="ff11b-115">Todos los certificados deben estar firmados mediante un algoritmo de firma compatible con el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="ff11b-115">All certificates must be signed using a signing algorithm supported by the operating system.</span></span> <span data-ttu-id="ff11b-116">Lync Server 2013 admite el conjunto de tamaños de compendio SHA-1 y SHA-2 (224, 256, 384 y 512 bits), y cumple o supera los requisitos del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="ff11b-116">Lync Server 2013 supports the SHA-1 and SHA-2 suite of digest sizes (224, 256, 384 and 512-bit), and meets or exceeds the operating system requirements.</span></span> <span data-ttu-id="ff11b-117">Para obtener asistencia sobre el sistema [http://go.microsoft.com/fwlink/?LinkId=287002](http://go.microsoft.com/fwlink/?linkid=287002)operativo, consulte.</span><span class="sxs-lookup"><span data-stu-id="ff11b-117">For operating system support, see [http://go.microsoft.com/fwlink/?LinkId=287002](http://go.microsoft.com/fwlink/?linkid=287002).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ff11b-118">No está permitido usar el algoritmo de firma RSASSA-PSS, ya que podría dar lugar a errores en problemas relacionados con el inicio de sesión y el desvío de llamadas, entre otros. </span><span class="sxs-lookup"><span data-stu-id="ff11b-118">Using the RSASSA-PSS signature algorithm is unsupported, and may lead to errors on login and call forwarding issues, among other problems.</span></span>

    
    </div>

  - <span data-ttu-id="ff11b-119">La inscripción automática es compatible con los servidores internos que ejecutan Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ff11b-119">Auto-enrollment is supported for internal servers running Lync Server.</span></span>

  - <span data-ttu-id="ff11b-120">La inscripción automática no es compatible con los servidores perimetrales de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ff11b-120">Auto-enrollment is not supported for Lync Server Edge Servers.</span></span>

  - <span data-ttu-id="ff11b-121">Al enviar una solicitud de certificado basada en Web a una CA de Windows Server 2003, debe enviarla desde un equipo con Windows Server 2003 con SP2 o Windows XP.</span><span class="sxs-lookup"><span data-stu-id="ff11b-121">When you submit a web-based certificate request to a Windows Server 2003 CA, you must submit it from a computer running either Windows Server 2003 with SP2 or Windows XP.</span></span>
    
    <span data-ttu-id="ff11b-122">Tenga en cuenta que, aunque KB922706 ofrece compatibilidad para resolver problemas con la inscripción de certificados Web en una inscripción Web de servicios de Certificate Server de Windows Server 2003, no permite usar Windows Server 2008, Windows Vista o Windows 7 para solicitar una certificado de una CA de Windows Server 2003.</span><span class="sxs-lookup"><span data-stu-id="ff11b-122">Note that although KB922706 provides support for resolving issues with enrolling web certificates against a Windows Server 2003 Certificate Services web enrollment, it does not make it possible to use Windows Server 2008, Windows Vista, or Windows 7 to request a certificate from a Windows Server 2003 CA.</span></span>

  - <span data-ttu-id="ff11b-123">Se admiten longitudes de clave de cifrado de 1024, 2048 y 4096.</span><span class="sxs-lookup"><span data-stu-id="ff11b-123">Encryption key lengths of 1024, 2048, and 4096 are supported.</span></span> <span data-ttu-id="ff11b-124">Se recomienda usar longitudes de clave de 2048 y superiores.</span><span class="sxs-lookup"><span data-stu-id="ff11b-124">Key lengths of 2048 and greater are recommended.</span></span>

  - <span data-ttu-id="ff11b-125">El algoritmo de firma hash o implícito predeterminado es RSA.</span><span class="sxs-lookup"><span data-stu-id="ff11b-125">The default digest, or hash signing, algorithm is RSA.</span></span> <span data-ttu-id="ff11b-126">También se\_admiten los\_algoritmos P256,\_ECDH P384 y P521 ECDH.</span><span class="sxs-lookup"><span data-stu-id="ff11b-126">The ECDH\_P256, ECDH\_P384, and ECDH\_P521 algorithms are also supported.</span></span> 

<div>

## <a name="in-this-section"></a><span data-ttu-id="ff11b-127">En esta sección</span><span class="sxs-lookup"><span data-stu-id="ff11b-127">In This Section</span></span>

  - [<span data-ttu-id="ff11b-128">Requisitos de certificado para Servidores internos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ff11b-128">Certificate requirements for internal servers in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [<span data-ttu-id="ff11b-129">Requisitos de certificado para el acceso de usuarios externos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ff11b-129">Certificate requirements for external user access in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [<span data-ttu-id="ff11b-130">Requisitos de certificados para el servidor de chat persistente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ff11b-130">Certificate requirements for Persistent Chat server in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-persistent-chat-server.md)

  - [<span data-ttu-id="ff11b-131">Requisitos de certificado para movilidad en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ff11b-131">Certificate requirements for mobility in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-mobility.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

