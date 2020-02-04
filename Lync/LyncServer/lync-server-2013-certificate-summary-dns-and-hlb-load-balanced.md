---
title: 'Lync Server 2013: Resumen de certificado - Carga equilibrada DNS y HLB'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - DNS and HLB load balanced
ms:assetid: 8318a1a4-b423-47b7-95e6-9541adfad391
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205047(v=OCS.15)
ms:contentKeyID: 48184676
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b8cd6d86844629544b54670eb07c3433d19f99f2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736660"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a><span data-ttu-id="c0b48-102">Resumen de certificado - Carga equilibrada DNS y HLB en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c0b48-102">Certificate summary - DNS and HLB load balanced in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c0b48-103">_**Última modificación del tema:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="c0b48-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="c0b48-104">Los requisitos de certificado para un director con el equilibrio de carga de DNS y un equilibrador de carga de hardware usarán un certificado predeterminado que tiene un nombre de sujeto y nombres alternativos de asunto para los servicios que el director puede recibir.</span><span class="sxs-lookup"><span data-stu-id="c0b48-104">Certificate requirements for a Director with DNS load balancing and a hardware load balancer will use a default certificate that has a subject name and subject alternative names for services that the Director can receive.</span></span> <span data-ttu-id="c0b48-105">Se solicita un certificado para cada director del grupo.</span><span class="sxs-lookup"><span data-stu-id="c0b48-105">A certificate is requested for each Director in the pool.</span></span> <span data-ttu-id="c0b48-106">Es importante recordar que el equilibrador de carga de hardware equilibra la carga del tráfico del proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="c0b48-106">It is important to remember that the hardware load balancer is load balancing only the traffic from the reverse proxy.</span></span> <span data-ttu-id="c0b48-107">Además, hay un certificado de token de OAuth para la autenticación de servidor a servidor que se instala en cada servidor.</span><span class="sxs-lookup"><span data-stu-id="c0b48-107">Additionally, there is an OAuth Token certificate for server to server authentication purposes that is installed on each server.</span></span>

### <a name="certificates-for-director"></a><span data-ttu-id="c0b48-108">Certificados para Director</span><span class="sxs-lookup"><span data-stu-id="c0b48-108">Certificates for Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c0b48-109">Componente</span><span class="sxs-lookup"><span data-stu-id="c0b48-109">Component</span></span></th>
<th><span data-ttu-id="c0b48-110">Nombre de sujeto</span><span class="sxs-lookup"><span data-stu-id="c0b48-110">Subject name (SN)</span></span></th>
<th><span data-ttu-id="c0b48-111">Nombres alternativos de asunto (SAN)</span><span class="sxs-lookup"><span data-stu-id="c0b48-111">Subject alternative names (SAN)</span></span></th>
<th><span data-ttu-id="c0b48-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c0b48-112">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c0b48-113">Predeterminado</span><span class="sxs-lookup"><span data-stu-id="c0b48-113">Default</span></span></p></td>
<td><p><span data-ttu-id="c0b48-114">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="c0b48-114">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="c0b48-115">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="c0b48-115">dirpool01.contoso.net</span></span></p>
<p><span data-ttu-id="c0b48-116">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="c0b48-116">dir01.contoso.net</span></span></p>
<p><span data-ttu-id="c0b48-117">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c0b48-117">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="c0b48-118">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c0b48-118">meet.contoso.com</span></span></p>
<p><span data-ttu-id="c0b48-119">lyncdiscoverinternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c0b48-119">lyncdiscoverinternal.contoso.com</span></span></p>
<p><span data-ttu-id="c0b48-120">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c0b48-120">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="c0b48-121">(Opcional) \*. contoso.com</span><span class="sxs-lookup"><span data-stu-id="c0b48-121">(Optionally) \*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="c0b48-122">Los certificados de director se pueden solicitar desde una entidad de certificación (CA) administrada internamente o desde una CA pública.</span><span class="sxs-lookup"><span data-stu-id="c0b48-122">Director certificates can be requested from either an internally managed certification authority (CA) or from a public CA.</span></span></p>
<p><span data-ttu-id="c0b48-123">El Director responde a las solicitudes del proxy inverso en el perímetro o del servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="c0b48-123">The Director responds to requests from the reverse proxy in the perimeter or from the Edge Server.</span></span> <span data-ttu-id="c0b48-124">Los clientes internos no usarán el director.</span><span class="sxs-lookup"><span data-stu-id="c0b48-124">Internal clients will not use the Director.</span></span></p>
<p><span data-ttu-id="c0b48-125">O bien, una entrada comodín para las direcciones URL simples</span><span class="sxs-lookup"><span data-stu-id="c0b48-125">Or, a wildcard entry for the simple URLs</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0b48-126">OAuthTokenIssuer</span><span class="sxs-lookup"><span data-stu-id="c0b48-126">OAuthTokenIssuer</span></span></p></td>
<td><p><span data-ttu-id="c0b48-127">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="c0b48-127">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="c0b48-128">Ninguna entrada</span><span class="sxs-lookup"><span data-stu-id="c0b48-128">No Entry</span></span></p></td>
<td><div>

> [!IMPORTANT]  
> <span data-ttu-id="c0b48-129">Tenga en cuenta que la longitud de clave mínima es 1024, pero es posible que reciba una advertencia que indica que la longitud de clave mínima recomendada es de 2048 bits.</span><span class="sxs-lookup"><span data-stu-id="c0b48-129">Note that the minimum key length is 1024, but you may receive a warning that the minimum recommended key length is 2048 bits.</span></span>


</div>
<p><span data-ttu-id="c0b48-130">El certificado OAuthTokenIssuer es un certificado de un único propósito para el propósito de autenticar servidores en un entorno de gran escala y se puede solicitar desde una entidad de certificación interna o desde una CA pública.</span><span class="sxs-lookup"><span data-stu-id="c0b48-130">The OAuthTokenIssuer certificate is a single-purpose certificate for the purpose of authenticating servers in a large-scale environment, and can be requested from an internal CA or from a public CA.</span></span> <span data-ttu-id="c0b48-131">El certificado es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="c0b48-131">The certificate is required.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

