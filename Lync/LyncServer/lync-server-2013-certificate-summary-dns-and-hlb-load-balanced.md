---
title: 'Lync Server 2013: Resumen de certificado-carga equilibrada DNS y HLB'
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
ms.openlocfilehash: 743818f81f5083e9c5d3a7877d2518d05176a5e7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499297"
---
# <a name="certificate-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a><span data-ttu-id="adebd-102">Resumen de certificado-carga equilibrada DNS y HLB en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="adebd-102">Certificate summary - DNS and HLB load balanced in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="adebd-103">_**Última modificación del tema:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="adebd-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="adebd-104">Los requisitos de certificado para un director con equilibrio de carga de DNS y un equilibrador de carga de hardware usarán un certificado predeterminado que tenga un nombre de sujeto y nombres alternativos de sujeto para los servicios que el director pueda recibir.</span><span class="sxs-lookup"><span data-stu-id="adebd-104">Certificate requirements for a Director with DNS load balancing and a hardware load balancer will use a default certificate that has a subject name and subject alternative names for services that the Director can receive.</span></span> <span data-ttu-id="adebd-105">Se solicita un certificado para cada director del grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="adebd-105">A certificate is requested for each Director in the pool.</span></span> <span data-ttu-id="adebd-106">Es importante recordar que el equilibrador de carga de hardware está equilibrando la carga solamente del tráfico del proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="adebd-106">It is important to remember that the hardware load balancer is load balancing only the traffic from the reverse proxy.</span></span> <span data-ttu-id="adebd-107">Además, existe un certificado del token OAuth para fines de autenticación de servidor a servidor que se instalan en cada servidor.</span><span class="sxs-lookup"><span data-stu-id="adebd-107">Additionally, there is an OAuth Token certificate for server to server authentication purposes that is installed on each server.</span></span>

### <a name="certificates-for-director"></a><span data-ttu-id="adebd-108">Certificados para el director</span><span class="sxs-lookup"><span data-stu-id="adebd-108">Certificates for Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="adebd-109">Componente</span><span class="sxs-lookup"><span data-stu-id="adebd-109">Component</span></span></th>
<th><span data-ttu-id="adebd-110">Nombre de sujeto (SN)</span><span class="sxs-lookup"><span data-stu-id="adebd-110">Subject name (SN)</span></span></th>
<th><span data-ttu-id="adebd-111">Nombres alternativos del sujeto (SAN)</span><span class="sxs-lookup"><span data-stu-id="adebd-111">Subject alternative names (SAN)</span></span></th>
<th><span data-ttu-id="adebd-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="adebd-112">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="adebd-113">Predeterminado</span><span class="sxs-lookup"><span data-stu-id="adebd-113">Default</span></span></p></td>
<td><p><span data-ttu-id="adebd-114">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="adebd-114">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="adebd-115">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="adebd-115">dirpool01.contoso.net</span></span></p>
<p><span data-ttu-id="adebd-116">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="adebd-116">dir01.contoso.net</span></span></p>
<p><span data-ttu-id="adebd-117">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="adebd-117">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="adebd-118">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="adebd-118">meet.contoso.com</span></span></p>
<p><span data-ttu-id="adebd-119">lyncdiscoverinternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="adebd-119">lyncdiscoverinternal.contoso.com</span></span></p>
<p><span data-ttu-id="adebd-120">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="adebd-120">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="adebd-121">(Opcional) \*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="adebd-121">(Optionally) \*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="adebd-122">Los certificados de director se pueden solicitar desde una entidad de certificación (CA) administrada internamente o desde una CA pública.</span><span class="sxs-lookup"><span data-stu-id="adebd-122">Director certificates can be requested from either an internally managed certification authority (CA) or from a public CA.</span></span></p>
<p><span data-ttu-id="adebd-123">El Director responde a las solicitudes del proxy inverso en el perímetro o desde el servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="adebd-123">The Director responds to requests from the reverse proxy in the perimeter or from the Edge Server.</span></span> <span data-ttu-id="adebd-124">Los clientes internos no usarán el director.</span><span class="sxs-lookup"><span data-stu-id="adebd-124">Internal clients will not use the Director.</span></span></p>
<p><span data-ttu-id="adebd-125">O una entrada con comodín para las direcciones URL simples</span><span class="sxs-lookup"><span data-stu-id="adebd-125">Or, a wildcard entry for the simple URLs</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="adebd-126">OAuthTokenIssuer</span><span class="sxs-lookup"><span data-stu-id="adebd-126">OAuthTokenIssuer</span></span></p></td>
<td><p><span data-ttu-id="adebd-127">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="adebd-127">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="adebd-128">Sin entradas</span><span class="sxs-lookup"><span data-stu-id="adebd-128">No Entry</span></span></p></td>
<td><div>

> [!IMPORTANT]  
> <span data-ttu-id="adebd-129">Tenga en cuenta que la longitud mínima de clave es 1024, pero puede recibir una advertencia de que la clave mínima recomendada es de 2048 bits.</span><span class="sxs-lookup"><span data-stu-id="adebd-129">Note that the minimum key length is 1024, but you may receive a warning that the minimum recommended key length is 2048 bits.</span></span>


</div>
<p><span data-ttu-id="adebd-p103">El certificado OAuthTokenIssuer es un certificado de un solo propósito para los fines de los servidores de autenticación en un entorno de gran escala, y pueden solicitarse a una CA interna o a una CA pública. Este certificado es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="adebd-p103">The OAuthTokenIssuer certificate is a single-purpose certificate for the purpose of authenticating servers in a large-scale environment, and can be requested from an internal CA or from a public CA. The certificate is required.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

