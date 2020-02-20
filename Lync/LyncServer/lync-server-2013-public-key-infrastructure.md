---
title: 'Lync Server 2013: infraestructura de clave pública'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Public Key Infrastructure for Lync Server 2013
ms:assetid: 737c8a25-23e9-4494-ab76-5a7b729b44ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481131(v=OCS.15)
ms:contentKeyID: 59893870
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 63ba5224d6663050295c5fddf9ea08e230f78506
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152294"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="public-key-infrastructure-for-lync-server-2013"></a><span data-ttu-id="557ec-102">Infraestructura de clave pública para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="557ec-102">Public Key Infrastructure for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="557ec-103">_**Última modificación del tema:** 2013-11-13_</span><span class="sxs-lookup"><span data-stu-id="557ec-103">_**Topic Last Modified:** 2013-11-13_</span></span>

<span data-ttu-id="557ec-104">Microsoft Lync Server 2013 se basa en certificados para la autenticación de servidores y para establecer una cadena de confianza entre clientes y servidores, así como entre los diferentes roles de servidor.</span><span class="sxs-lookup"><span data-stu-id="557ec-104">Microsoft Lync Server 2013 relies on certificates for server authentication and to establish a chain of trust between clients and servers and among the different server roles.</span></span> <span data-ttu-id="557ec-105">Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 y la infraestructura de clave pública (PKI) de Windows Server 2003 proporcionan la infraestructura para establecer y validar esta cadena de confianza.</span><span class="sxs-lookup"><span data-stu-id="557ec-105">The Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008, and Windows Server 2003 Public Key Infrastructure (PKI) provides the infrastructure for establishing and validating this chain of trust.</span></span>

<span data-ttu-id="557ec-106">Los certificados son identificadores digitales.</span><span class="sxs-lookup"><span data-stu-id="557ec-106">Certificates are digital IDs.</span></span> <span data-ttu-id="557ec-107">Identifican un servidor por su nombre y especifican sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="557ec-107">They identify a server by name and specify its properties.</span></span> <span data-ttu-id="557ec-108">Para asegurarse de que la información de un certificado es válida, el certificado debe ser emitido por una entidad de certificación en la que confían los clientes u otros servidores que se conectan al servidor.</span><span class="sxs-lookup"><span data-stu-id="557ec-108">To ensure that the information on a certificate is valid, the certificate must be issued by a CA that is trusted by clients or other servers that connect to the server.</span></span> <span data-ttu-id="557ec-109">Si el servidor se conecta sólo con otros clientes y servidores de una red privada, la entidad de certificación puede ser una entidad de certificación empresarial.</span><span class="sxs-lookup"><span data-stu-id="557ec-109">If the server connects only with other clients and servers on a private network, the CA can be an enterprise CA.</span></span> <span data-ttu-id="557ec-110">Si el servidor interactúa con entidades fuera de la red privada, es posible que se requiera una entidad de certificación pública.</span><span class="sxs-lookup"><span data-stu-id="557ec-110">If the server interacts with entities outside the private network, a public CA might be required.</span></span>

<span data-ttu-id="557ec-p103">Incluso si la información incluida en el certificado es válida, es preciso comprobar de alguna manera que el servidor que presenta el certificado es realmente el servidor representado por el certificado. Ahí es donde entra en juego la PKI de Windows.</span><span class="sxs-lookup"><span data-stu-id="557ec-p103">Even if the information on the certificate is valid, there must be some way to verify that the server presenting the certificate is actually the one represented by the certificate. This is where the Windows PKI comes in.</span></span>

<span data-ttu-id="557ec-p104">Cada certificado está asociado a una clave pública. El servidor indicado en el certificado tiene una clave privada correspondiente que solo él conoce. El cliente o servidor que se conecta usa la clave pública para cifrar un fragmento de información aleatorio y enviarlo al servidor. Si el servidor descifra la información y la devuelve como texto sin formato, la entidad que se conecta puede estar segura de que el servidor tiene la clave privada asociada al certificado y, por consiguiente, es el servidor indicado en el certificado.</span><span class="sxs-lookup"><span data-stu-id="557ec-p104">Each certificate is linked to a public key. The server named on the certificate holds a corresponding private key that only it knows. A connecting client or server uses the public key to encrypt a random piece of information and sends it to the server. If the server decrypts the information and returns it as plain text, the connecting entity can be sure that the server holds the private key to the certificate and therefore is the server named on the certificate.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="557ec-117">No todas las entidades de certificación públicas cumplen con los requisitos de los certificados 2013 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="557ec-117">Not all public CAs comply with the requirements of Lync Server 2013 certificates.</span></span> <span data-ttu-id="557ec-118">Para los certificados públicos, se recomienda consultar la lista de proveedores autorizados de CA públicas.</span><span class="sxs-lookup"><span data-stu-id="557ec-118">We recommend that you refer to the listing of certified Public CA vendors for your public certificate needs.</span></span> <span data-ttu-id="557ec-119">Para obtener más información, vea asociados de certificados <A href="https://go.microsoft.com/fwlink/p/?linkid=140898">https://go.microsoft.com/fwlink/p/?LinkId=140898</A>de comunicaciones unificadas en.</span><span class="sxs-lookup"><span data-stu-id="557ec-119">For details, see Unified Communications Certificate Partners at <A href="https://go.microsoft.com/fwlink/p/?linkid=140898">https://go.microsoft.com/fwlink/p/?LinkId=140898</A>.</span></span>



</div>

<div>

## <a name="crl-distribution-points"></a><span data-ttu-id="557ec-120">Puntos de distribución CRL</span><span class="sxs-lookup"><span data-stu-id="557ec-120">CRL Distribution Points</span></span>

<span data-ttu-id="557ec-121">Lync Server 2013 requiere que todos los certificados de servidor contengan uno o más puntos de distribución de listas de revocación de certificados (CRL).</span><span class="sxs-lookup"><span data-stu-id="557ec-121">Lync Server 2013 requires all server certificates to contain one or more Certificate Revocation List (CRL) distribution points.</span></span> <span data-ttu-id="557ec-122">Los puntos de distribución CRL son ubicaciones desde las que se pueden descargar listas de revocación de certificados para comprobar si un certificado no ha sido revocado después de su emisión.</span><span class="sxs-lookup"><span data-stu-id="557ec-122">CRL distribution points (CDPs) are locations from which CRLs can be downloaded for purposes of verifying that the certificate has not been revoked since the time it was issued and the certificate is still within the validity period.</span></span> <span data-ttu-id="557ec-123">Un punto de distribución CRL se anota en las propiedades del certificado como una dirección URL y suele ser HTTPS.</span><span class="sxs-lookup"><span data-stu-id="557ec-123">A CRL distribution point is noted in the properties of the certificate as a URL, and is typically secure HTTP.</span></span>

</div>

<div>

## <a name="enhanced-key-usage"></a><span data-ttu-id="557ec-124">Uso mejorado de clave</span><span class="sxs-lookup"><span data-stu-id="557ec-124">Enhanced Key Usage</span></span>

<span data-ttu-id="557ec-125">Lync Server 2013 requiere que todos los certificados de servidor sean compatibles con el uso mejorado de clave (EKU) para fines de autenticación de servidor.</span><span class="sxs-lookup"><span data-stu-id="557ec-125">Lync Server 2013 requires all server certificates to support Enhanced Key Usage (EKU) for the purpose of server authentication.</span></span> <span data-ttu-id="557ec-126">La configuración del campo EKU para la autenticación de los servidores significa que el certificado es válido para la autenticación de los servidores.</span><span class="sxs-lookup"><span data-stu-id="557ec-126">Configuring the EKU field for server authentication means that the certificate is valid for the purpose of authenticating servers.</span></span> <span data-ttu-id="557ec-127">Este EKU es esencial para MTLS.</span><span class="sxs-lookup"><span data-stu-id="557ec-127">This EKU is essential for MTLS.</span></span> <span data-ttu-id="557ec-128">Puede haber varias entradas en el EKU; de este modo, se habilita el certificado para varios propósitos.</span><span class="sxs-lookup"><span data-stu-id="557ec-128">It is possible to have more than one entry in the EKU, enabling the certificate for more than one purpose.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="557ec-p108">El EKU para la autenticación de clientes se requería para las conexiones MTLS salientes de Live Communications Server 2003 y Live Communications Server 2005, pero ya no se requiere. Sin embargo, este EKU debe estar presente en los servidores perimetrales que se conectan a AOL a través de la conectividad de mensajería instantánea pública.</span><span class="sxs-lookup"><span data-stu-id="557ec-p108">The Client Authentication EKU is required for outbound MTLS connections from Live Communications Server 2003 and Live Communications Server 2005, but it is no longer required. However, this EKU must be present on Edge Servers that connect to AOL by means of public IM connectivity.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

