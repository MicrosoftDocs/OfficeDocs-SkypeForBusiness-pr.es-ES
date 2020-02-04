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
ms.openlocfilehash: 9b205699e9efd896a157654f5c1fb200e34087fc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724630"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="public-key-infrastructure-for-lync-server-2013"></a><span data-ttu-id="4c017-102">Infraestructura de clave pública para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4c017-102">Public Key Infrastructure for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4c017-103">_**Última modificación del tema:** 2013-11-13_</span><span class="sxs-lookup"><span data-stu-id="4c017-103">_**Topic Last Modified:** 2013-11-13_</span></span>

<span data-ttu-id="4c017-104">Microsoft Lync Server 2013 se basa en certificados para la autenticación de servidores y para establecer una cadena de confianza entre clientes y servidores, así como entre los diferentes roles de servidor.</span><span class="sxs-lookup"><span data-stu-id="4c017-104">Microsoft Lync Server 2013 relies on certificates for server authentication and to establish a chain of trust between clients and servers and among the different server roles.</span></span> <span data-ttu-id="4c017-105">Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 y Windows Server 2003 infraestructura de clave pública (PKI) proporciona la infraestructura para establecer y validar esta cadena de confianza.</span><span class="sxs-lookup"><span data-stu-id="4c017-105">The Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008, and Windows Server 2003 Public Key Infrastructure (PKI) provides the infrastructure for establishing and validating this chain of trust.</span></span>

<span data-ttu-id="4c017-p102">Los certificados son identificadores digitales. Identifican un servidor por nombre y especifican sus propiedades. Para garantizar la validez de la información incluida en un certificado, este debe proceder de una entidad de certificación (CA) que sea de confianza para los clientes u otros servidores que se conectan al servidor. Si el servidor se conecta únicamente a otros clientes y servidores de una red privada, la CA puede ser una CA de empresa. Si el servidor interactúa con entidades ubicadas fuera de la red privada, es posible que se requiera una CA pública.</span><span class="sxs-lookup"><span data-stu-id="4c017-p102">Certificates are digital IDs. They identify a server by name and specify its properties. To ensure that the information on a certificate is valid, the certificate must be issued by a CA that is trusted by clients or other servers that connect to the server. If the server connects only with other clients and servers on a private network, the CA can be an enterprise CA. If the server interacts with entities outside the private network, a public CA might be required.</span></span>

<span data-ttu-id="4c017-p103">Incluso si la información incluida en el certificado es válida, es preciso comprobar de alguna manera que el servidor que presenta el certificado es realmente el servidor representado por el certificado. Ahí es donde entra en juego la PKI de Windows.</span><span class="sxs-lookup"><span data-stu-id="4c017-p103">Even if the information on the certificate is valid, there must be some way to verify that the server presenting the certificate is actually the one represented by the certificate. This is where the Windows PKI comes in.</span></span>

<span data-ttu-id="4c017-p104">Cada certificado está asociado a una clave pública. El servidor indicado en el certificado tiene una clave privada correspondiente que solo él conoce. El cliente o servidor que se conecta usa la clave pública para cifrar un fragmento de información aleatorio y enviarlo al servidor. Si el servidor descifra la información y la devuelve como texto sin formato, la entidad que se conecta puede estar segura de que el servidor tiene la clave privada asociada al certificado y, por consiguiente, es el servidor indicado en el certificado.</span><span class="sxs-lookup"><span data-stu-id="4c017-p104">Each certificate is linked to a public key. The server named on the certificate holds a corresponding private key that only it knows. A connecting client or server uses the public key to encrypt a random piece of information and sends it to the server. If the server decrypts the information and returns it as plain text, the connecting entity can be sure that the server holds the private key to the certificate and therefore is the server named on the certificate.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4c017-117">No todas las entidades emisoras públicas cumplen con los requisitos de los certificados de 2013 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4c017-117">Not all public CAs comply with the requirements of Lync Server 2013 certificates.</span></span> <span data-ttu-id="4c017-118">Para los certificados públicos, se recomienda consultar la lista de proveedores autorizados de CA públicas.</span><span class="sxs-lookup"><span data-stu-id="4c017-118">We recommend that you refer to the listing of certified Public CA vendors for your public certificate needs.</span></span> <span data-ttu-id="4c017-119">Para obtener más información, vea socios de certificados <A href="http://go.microsoft.com/fwlink/p/?linkid=140898">http://go.microsoft.com/fwlink/p/?LinkId=140898</A>de comunicaciones unificadas en.</span><span class="sxs-lookup"><span data-stu-id="4c017-119">For details, see Unified Communications Certificate Partners at <A href="http://go.microsoft.com/fwlink/p/?linkid=140898">http://go.microsoft.com/fwlink/p/?LinkId=140898</A>.</span></span>



</div>

<div>

## <a name="crl-distribution-points"></a><span data-ttu-id="4c017-120">Puntos de distribución CRL</span><span class="sxs-lookup"><span data-stu-id="4c017-120">CRL Distribution Points</span></span>

<span data-ttu-id="4c017-121">Lync Server 2013 requiere que todos los certificados de servidor contengan uno o varios puntos de distribución de la lista de revocación de certificados (CRL).</span><span class="sxs-lookup"><span data-stu-id="4c017-121">Lync Server 2013 requires all server certificates to contain one or more Certificate Revocation List (CRL) distribution points.</span></span> <span data-ttu-id="4c017-122">Los puntos de distribución CRL (CDP) son ubicaciones desde las que se pueden descargar CRL para comprobar si un certificado no ha sido revocado después de su emisión y todavía se encuentra dentro del período de validez.</span><span class="sxs-lookup"><span data-stu-id="4c017-122">CRL distribution points (CDPs) are locations from which CRLs can be downloaded for purposes of verifying that the certificate has not been revoked since the time it was issued and the certificate is still within the validity period.</span></span> <span data-ttu-id="4c017-123">Un punto de distribución CRL se anota en las propiedades del certificado como una dirección URL y suele ser HTTPS.</span><span class="sxs-lookup"><span data-stu-id="4c017-123">A CRL distribution point is noted in the properties of the certificate as a URL, and is typically secure HTTP.</span></span>

</div>

<div>

## <a name="enhanced-key-usage"></a><span data-ttu-id="4c017-124">Uso mejorado de clave</span><span class="sxs-lookup"><span data-stu-id="4c017-124">Enhanced Key Usage</span></span>

<span data-ttu-id="4c017-125">Lync Server 2013 requiere que todos los certificados de servidor admitan el uso mejorado de claves (EKU) para la autenticación del servidor.</span><span class="sxs-lookup"><span data-stu-id="4c017-125">Lync Server 2013 requires all server certificates to support Enhanced Key Usage (EKU) for the purpose of server authentication.</span></span> <span data-ttu-id="4c017-126">La configuración del campo EKU para la autenticación de los servidores significa que el certificado es válido para la autenticación de los servidores.</span><span class="sxs-lookup"><span data-stu-id="4c017-126">Configuring the EKU field for server authentication means that the certificate is valid for the purpose of authenticating servers.</span></span> <span data-ttu-id="4c017-127">Este EKU es esencial para MTLS.</span><span class="sxs-lookup"><span data-stu-id="4c017-127">This EKU is essential for MTLS.</span></span> <span data-ttu-id="4c017-128">Puede haber varias entradas en el EKU; de este modo, se habilita el certificado para varios propósitos.</span><span class="sxs-lookup"><span data-stu-id="4c017-128">It is possible to have more than one entry in the EKU, enabling the certificate for more than one purpose.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4c017-129">El EKU de autenticación de cliente es necesario para las conexiones MTLS de salida de Live Communications Server 2003 y Live Communications Server 2005, pero ya no es necesario.</span><span class="sxs-lookup"><span data-stu-id="4c017-129">The Client Authentication EKU is required for outbound MTLS connections from Live Communications Server 2003 and Live Communications Server 2005, but it is no longer required.</span></span> <span data-ttu-id="4c017-130">Sin embargo, este EKU debe estar presente en los servidores perimetrales que se conectan a AOL por medio de la conectividad de mensajería instantánea pública.</span><span class="sxs-lookup"><span data-stu-id="4c017-130">However, this EKU must be present on Edge Servers that connect to AOL by means of public IM connectivity.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

