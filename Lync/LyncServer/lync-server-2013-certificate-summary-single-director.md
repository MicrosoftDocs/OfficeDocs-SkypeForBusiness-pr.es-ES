---
title: 'Lync Server 2013: Resumen del certificado-Director único'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Single Director
ms:assetid: 1b769a76-cbf3-46e9-a955-f6cde5faff93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204720(v=OCS.15)
ms:contentKeyID: 48183546
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ceb2543cece60a32c733d2efad6023fc30bb2bf6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517937"
---
# <a name="certificate-summary---single-director-in-lync-server-2013"></a><span data-ttu-id="6a7d0-102">Resumen del certificado-Director único en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6a7d0-102">Certificate summary - Single Director in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6a7d0-103">_**Última modificación del tema:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="6a7d0-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="6a7d0-104">Los requisitos de certificado para un solo Director constan de un certificado predeterminado que tiene un nombre de sujeto y nombres alternativos de sujeto para los servicios que el director puede recibir.</span><span class="sxs-lookup"><span data-stu-id="6a7d0-104">Certificate requirements for a single Director consist of a default certificate that has a subject name and subject alternative names for services that the Director can receive.</span></span> <span data-ttu-id="6a7d0-105">Asimismo, existe un certificado OAuth Token para fines de autenticación de servidor a servidor.</span><span class="sxs-lookup"><span data-stu-id="6a7d0-105">Additionally, there is an OAuth Token certificate for server to server authentication purposes.</span></span>

### <a name="certificates-for-director"></a><span data-ttu-id="6a7d0-106">Certificados para el director</span><span class="sxs-lookup"><span data-stu-id="6a7d0-106">Certificates for Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6a7d0-107">Componente</span><span class="sxs-lookup"><span data-stu-id="6a7d0-107">Component</span></span></th>
<th><span data-ttu-id="6a7d0-108">Nombre de sujeto (SN)</span><span class="sxs-lookup"><span data-stu-id="6a7d0-108">Subject name (SN)</span></span></th>
<th><span data-ttu-id="6a7d0-109">Nombres alternativos del sujeto (SAN)</span><span class="sxs-lookup"><span data-stu-id="6a7d0-109">Subject alternative names (SAN)</span></span></th>
<th><span data-ttu-id="6a7d0-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6a7d0-110">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6a7d0-111">Predeterminado</span><span class="sxs-lookup"><span data-stu-id="6a7d0-111">Default</span></span></p></td>
<td><p><span data-ttu-id="6a7d0-112">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="6a7d0-112">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="6a7d0-113">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="6a7d0-113">dir01.contoso.net</span></span></p>
<p><span data-ttu-id="6a7d0-114">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="6a7d0-114">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="6a7d0-115">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="6a7d0-115">meet.contoso.com</span></span></p>
<p><span data-ttu-id="6a7d0-116">lyncdiscoverinternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="6a7d0-116">lyncdiscoverinternal.contoso.com</span></span></p>
<p><span data-ttu-id="6a7d0-117">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="6a7d0-117">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="6a7d0-118">(Opcional) \*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="6a7d0-118">(Optionally) \*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="6a7d0-119">Los certificados de director se pueden solicitar desde una entidad de certificación (CA) administrada internamente o desde una CA pública.</span><span class="sxs-lookup"><span data-stu-id="6a7d0-119">Director certificates can be requested from either an internally managed certification authority (CA) or from a public CA.</span></span></p>
<p><span data-ttu-id="6a7d0-120">El Director responde a las solicitudes del proxy inverso en el perímetro o desde el servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="6a7d0-120">The Director responds to requests from the reverse proxy in the perimeter or from the Edge Server.</span></span> <span data-ttu-id="6a7d0-121">Los clientes internos no usarán el director.</span><span class="sxs-lookup"><span data-stu-id="6a7d0-121">Internal clients will not use the Director.</span></span></p>
<p><span data-ttu-id="6a7d0-122">O una entrada con comodín para las direcciones URL simples</span><span class="sxs-lookup"><span data-stu-id="6a7d0-122">Or, a wildcard entry for the simple URLs</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6a7d0-123">OAuthTokenIssuer</span><span class="sxs-lookup"><span data-stu-id="6a7d0-123">OAuthTokenIssuer</span></span></p></td>
<td><p><span data-ttu-id="6a7d0-124">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="6a7d0-124">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="6a7d0-125">Sin entradas</span><span class="sxs-lookup"><span data-stu-id="6a7d0-125">No Entry</span></span></p></td>
<td><div>

> [!IMPORTANT]  
> <span data-ttu-id="6a7d0-126">Tenga en cuenta que la longitud mínima de clave es 1024, pero puede recibir una advertencia de que la clave mínima recomendada es de 2048 bits.</span><span class="sxs-lookup"><span data-stu-id="6a7d0-126">Note that the minimum key length is 1024, but you may receive a warning that the minimum recommended key length is 2048 bits.</span></span>


</div>
<p><span data-ttu-id="6a7d0-p103">El certificado OAuthTokenIssuer es un certificado de un solo propósito para los fines de los servidores de autenticación en un entorno de gran escala, y pueden solicitarse a una CA interna o a una CA pública. Este certificado es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="6a7d0-p103">The OAuthTokenIssuer certificate is a single-purpose certificate for the purpose of authenticating servers in a large-scale environment, and can be requested from an internal CA or from a public CA. The certificate is required.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

