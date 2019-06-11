---
title: Resumen de certificado - Grupo de director escalado, equilibrador de carga de hardware
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate summary - Scaled Director pool, hardware load balancer
ms:assetid: 45940add-8027-418d-b79a-9033b494762f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204846(v=OCS.15)
ms:contentKeyID: 48183992
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 21b1688641d09e00c82ea952d57bd2a9547ac0dd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842626"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="6e060-102">Resumen de certificado - Grupo de director escalado, equilibrador de carga de hardware en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e060-102">Certificate summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6e060-103">_**Última modificación del tema:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="6e060-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="6e060-104">Los requisitos de certificado para un director con un equilibrador de carga de hardware usarán un certificado predeterminado que tiene un nombre de sujeto y nombres alternativos de asunto para los servicios que el grupo de directores puede recibir.</span><span class="sxs-lookup"><span data-stu-id="6e060-104">Certificate requirements for a Director with a hardware load balancer will use a default certificate that has a subject name and subject alternative names for services that the Director pool can receive.</span></span> <span data-ttu-id="6e060-105">Se solicita un certificado para cada director del grupo.</span><span class="sxs-lookup"><span data-stu-id="6e060-105">A certificate is requested for each Director in the pool.</span></span> <span data-ttu-id="6e060-106">Además, hay un certificado de token de OAuth para la autenticación de servidor a servidor que se instala en cada servidor.</span><span class="sxs-lookup"><span data-stu-id="6e060-106">Additionally there is an OAuth Token certificate for server to server authentication purposes that is installed on each server.</span></span>

### <a name="certificates-for-a-scaled-director-using-a-hardware-load-balancer"></a><span data-ttu-id="6e060-107">Certificados para un director con escala usando un equilibrador de carga de hardware</span><span class="sxs-lookup"><span data-stu-id="6e060-107">Certificates for a Scaled Director Using a Hardware Load Balancer</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6e060-108">Componente</span><span class="sxs-lookup"><span data-stu-id="6e060-108">Component</span></span></th>
<th><span data-ttu-id="6e060-109">Nombre de sujeto</span><span class="sxs-lookup"><span data-stu-id="6e060-109">Subject name (SN)</span></span></th>
<th><span data-ttu-id="6e060-110">Nombres alternativos de asunto (SAN)</span><span class="sxs-lookup"><span data-stu-id="6e060-110">Subject alternative names (SAN)</span></span></th>
<th><span data-ttu-id="6e060-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6e060-111">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6e060-112">Predeterminado</span><span class="sxs-lookup"><span data-stu-id="6e060-112">Default</span></span></p></td>
<td><p><span data-ttu-id="6e060-113">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="6e060-113">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="6e060-114">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="6e060-114">dirpool01.contoso.net</span></span></p>
<p><span data-ttu-id="6e060-115">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="6e060-115">dir01.contoso.net</span></span></p>
<p><span data-ttu-id="6e060-116">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="6e060-116">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="6e060-117">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="6e060-117">meet.contoso.com</span></span></p>
<p><span data-ttu-id="6e060-118">lyncdiscoverinternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="6e060-118">lyncdiscoverinternal.contoso.com</span></span></p>
<p><span data-ttu-id="6e060-119">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="6e060-119">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="6e060-120">(Opcional) \*. contoso.com</span><span class="sxs-lookup"><span data-stu-id="6e060-120">(Optionally) \*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="6e060-121">Los certificados de director se pueden solicitar desde una entidad de certificación (CA) administrada internamente o desde una CA pública.</span><span class="sxs-lookup"><span data-stu-id="6e060-121">Director certificates can be requested from either an internally managed certification authority (CA) or from a public CA.</span></span></p>
<p><span data-ttu-id="6e060-122">El Director responde a las solicitudes del proxy inverso en el perímetro o del servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="6e060-122">The Director responds to requests from the reverse proxy in the perimeter or from the Edge Server.</span></span></p>
<p><span data-ttu-id="6e060-123">O bien, una entrada comodín para las direcciones URL simples</span><span class="sxs-lookup"><span data-stu-id="6e060-123">Or, a wildcard entry for the simple URLs</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e060-124">OAuthTokenIssuer</span><span class="sxs-lookup"><span data-stu-id="6e060-124">OAuthTokenIssuer</span></span></p></td>
<td><p><span data-ttu-id="6e060-125">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="6e060-125">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="6e060-126">Ninguna entrada</span><span class="sxs-lookup"><span data-stu-id="6e060-126">No Entry</span></span></p></td>
<td>


> [!IMPORTANT]
> <span data-ttu-id="6e060-127">Tenga en cuenta que la longitud de clave mínima es 1024, pero es posible que reciba una advertencia que indica que la longitud de clave mínima recomendada es de 2048 bits.</span><span class="sxs-lookup"><span data-stu-id="6e060-127">Note that the minimum key length is 1024, but you may receive a warning that the minimum recommended key length is 2048 bits.</span></span>


<p><span data-ttu-id="6e060-128">El certificado OAuthTokenIssuer es un certificado de un único propósito para el propósito de autenticar servidores en un entorno de gran escala y se puede solicitar desde una entidad de certificación interna o desde una CA pública.</span><span class="sxs-lookup"><span data-stu-id="6e060-128">The OAuthTokenIssuer certificate is a single-purpose certificate for the purpose of authenticating servers in a large-scale environment, and can be requested from an internal CA or from a public CA.</span></span> <span data-ttu-id="6e060-129">El certificado es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="6e060-129">The certificate is required.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

