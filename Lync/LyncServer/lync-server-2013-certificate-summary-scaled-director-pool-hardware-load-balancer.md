---
title: Resumen de certificado-grupo de Director escalado, equilibrador de carga de hardware
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Scaled Director pool, hardware load balancer
ms:assetid: 45940add-8027-418d-b79a-9033b494762f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204846(v=OCS.15)
ms:contentKeyID: 48183992
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 33fed49b1174260e29f6badc4a3f994f888c1a4b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207006"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="cf6a7-102">Resumen de certificado-grupo de Director escalado, equilibrador de carga de hardware en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cf6a7-102">Certificate summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cf6a7-103">_**Última modificación del tema:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="cf6a7-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="cf6a7-104">Los requisitos de certificado para un director con un equilibrador de carga de hardware usarán un certificado predeterminado que tenga un nombre de sujeto y nombres alternativos de sujeto para los servicios que el grupo de directores pueda recibir.</span><span class="sxs-lookup"><span data-stu-id="cf6a7-104">Certificate requirements for a Director with a hardware load balancer will use a default certificate that has a subject name and subject alternative names for services that the Director pool can receive.</span></span> <span data-ttu-id="cf6a7-105">Se solicita un certificado para cada director del grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="cf6a7-105">A certificate is requested for each Director in the pool.</span></span> <span data-ttu-id="cf6a7-106">Además, hay un certificado OAuth Token para propósitos de servicio de autenticación de servidor que se instala en cada servidor.</span><span class="sxs-lookup"><span data-stu-id="cf6a7-106">Additionally there is an OAuth Token certificate for server to server authentication purposes that is installed on each server.</span></span>

### <a name="certificates-for-a-scaled-director-using-a-hardware-load-balancer"></a><span data-ttu-id="cf6a7-107">Certificados para un director escalado que usa un equilibrador de carga de hardware</span><span class="sxs-lookup"><span data-stu-id="cf6a7-107">Certificates for a Scaled Director Using a Hardware Load Balancer</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cf6a7-108">Componente</span><span class="sxs-lookup"><span data-stu-id="cf6a7-108">Component</span></span></th>
<th><span data-ttu-id="cf6a7-109">Nombre de sujeto (SN)</span><span class="sxs-lookup"><span data-stu-id="cf6a7-109">Subject name (SN)</span></span></th>
<th><span data-ttu-id="cf6a7-110">Nombres alternativos del sujeto (SAN)</span><span class="sxs-lookup"><span data-stu-id="cf6a7-110">Subject alternative names (SAN)</span></span></th>
<th><span data-ttu-id="cf6a7-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cf6a7-111">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cf6a7-112">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="cf6a7-112">Default</span></span></p></td>
<td><p><span data-ttu-id="cf6a7-113">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="cf6a7-113">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="cf6a7-114">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="cf6a7-114">dirpool01.contoso.net</span></span></p>
<p><span data-ttu-id="cf6a7-115">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="cf6a7-115">dir01.contoso.net</span></span></p>
<p><span data-ttu-id="cf6a7-116">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="cf6a7-116">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="cf6a7-117">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="cf6a7-117">meet.contoso.com</span></span></p>
<p><span data-ttu-id="cf6a7-118">lyncdiscoverinternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="cf6a7-118">lyncdiscoverinternal.contoso.com</span></span></p>
<p><span data-ttu-id="cf6a7-119">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="cf6a7-119">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="cf6a7-120">(Opcional) \*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="cf6a7-120">(Optionally) \*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="cf6a7-121">Los certificados de director se pueden solicitar desde una entidad de certificación (CA) administrada internamente o desde una CA pública.</span><span class="sxs-lookup"><span data-stu-id="cf6a7-121">Director certificates can be requested from either an internally managed certification authority (CA) or from a public CA.</span></span></p>
<p><span data-ttu-id="cf6a7-122">El Director responde a las solicitudes del proxy inverso en el perímetro o desde el servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="cf6a7-122">The Director responds to requests from the reverse proxy in the perimeter or from the Edge Server.</span></span></p>
<p><span data-ttu-id="cf6a7-123">O una entrada con comodín para las direcciones URL simples</span><span class="sxs-lookup"><span data-stu-id="cf6a7-123">Or, a wildcard entry for the simple URLs</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf6a7-124">OAuthTokenIssuer</span><span class="sxs-lookup"><span data-stu-id="cf6a7-124">OAuthTokenIssuer</span></span></p></td>
<td><p><span data-ttu-id="cf6a7-125">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="cf6a7-125">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="cf6a7-126">Sin entradas</span><span class="sxs-lookup"><span data-stu-id="cf6a7-126">No Entry</span></span></p></td>
<td>


> [!IMPORTANT]
> <span data-ttu-id="cf6a7-127">Tenga en cuenta que la longitud mínima de clave es 1024, pero puede recibir una advertencia de que la clave mínima recomendada es de 2048 bits.</span><span class="sxs-lookup"><span data-stu-id="cf6a7-127">Note that the minimum key length is 1024, but you may receive a warning that the minimum recommended key length is 2048 bits.</span></span>


<p><span data-ttu-id="cf6a7-p102">El certificado OAuthTokenIssuer es un certificado de un solo propósito para los fines de los servidores de autenticación en un entorno de gran escala, y pueden solicitarse a una CA interna o a una CA pública. Este certificado es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="cf6a7-p102">The OAuthTokenIssuer certificate is a single-purpose certificate for the purpose of authenticating servers in a large-scale environment, and can be requested from an internal CA or from a public CA. The certificate is required.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

