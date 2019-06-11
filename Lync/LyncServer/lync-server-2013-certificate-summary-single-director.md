---
title: 'Lync Server 2013: Resumen de certificado - Director único'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate summary - Single Director
ms:assetid: 1b769a76-cbf3-46e9-a955-f6cde5faff93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204720(v=OCS.15)
ms:contentKeyID: 48183546
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e44be0ca76a1926a1515657a9d7d5646a49390c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842622"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---single-director-in-lync-server-2013"></a><span data-ttu-id="9f144-102">Resumen de certificado - Director único en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9f144-102">Certificate summary - Single Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9f144-103">_**Última modificación del tema:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="9f144-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="9f144-104">Los requisitos de certificado para un único Director consisten en un certificado predeterminado que tiene un nombre de sujeto y nombres alternativos de sujeto para los servicios que el director puede recibir.</span><span class="sxs-lookup"><span data-stu-id="9f144-104">Certificate requirements for a single Director consist of a default certificate that has a subject name and subject alternative names for services that the Director can receive.</span></span> <span data-ttu-id="9f144-105">Además, hay un certificado de token de OAuth para propósitos de autenticación de servidor a servidor.</span><span class="sxs-lookup"><span data-stu-id="9f144-105">Additionally, there is an OAuth Token certificate for server to server authentication purposes.</span></span>

### <a name="certificates-for-director"></a><span data-ttu-id="9f144-106">Certificados para Director</span><span class="sxs-lookup"><span data-stu-id="9f144-106">Certificates for Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9f144-107">Componente</span><span class="sxs-lookup"><span data-stu-id="9f144-107">Component</span></span></th>
<th><span data-ttu-id="9f144-108">Nombre de sujeto</span><span class="sxs-lookup"><span data-stu-id="9f144-108">Subject name (SN)</span></span></th>
<th><span data-ttu-id="9f144-109">Nombres alternativos de asunto (SAN)</span><span class="sxs-lookup"><span data-stu-id="9f144-109">Subject alternative names (SAN)</span></span></th>
<th><span data-ttu-id="9f144-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9f144-110">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9f144-111">Predeterminado</span><span class="sxs-lookup"><span data-stu-id="9f144-111">Default</span></span></p></td>
<td><p><span data-ttu-id="9f144-112">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="9f144-112">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="9f144-113">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="9f144-113">dir01.contoso.net</span></span></p>
<p><span data-ttu-id="9f144-114">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9f144-114">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="9f144-115">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9f144-115">meet.contoso.com</span></span></p>
<p><span data-ttu-id="9f144-116">lyncdiscoverinternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9f144-116">lyncdiscoverinternal.contoso.com</span></span></p>
<p><span data-ttu-id="9f144-117">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9f144-117">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="9f144-118">(Opcional) \*. contoso.com</span><span class="sxs-lookup"><span data-stu-id="9f144-118">(Optionally) \*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="9f144-119">Los certificados de director se pueden solicitar desde una entidad de certificación (CA) administrada internamente o desde una CA pública.</span><span class="sxs-lookup"><span data-stu-id="9f144-119">Director certificates can be requested from either an internally managed certification authority (CA) or from a public CA.</span></span></p>
<p><span data-ttu-id="9f144-120">El Director responde a las solicitudes del proxy inverso en el perímetro o del servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="9f144-120">The Director responds to requests from the reverse proxy in the perimeter or from the Edge Server.</span></span> <span data-ttu-id="9f144-121">Los clientes internos no usarán el director.</span><span class="sxs-lookup"><span data-stu-id="9f144-121">Internal clients will not use the Director.</span></span></p>
<p><span data-ttu-id="9f144-122">O bien, una entrada comodín para las direcciones URL simples</span><span class="sxs-lookup"><span data-stu-id="9f144-122">Or, a wildcard entry for the simple URLs</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f144-123">OAuthTokenIssuer</span><span class="sxs-lookup"><span data-stu-id="9f144-123">OAuthTokenIssuer</span></span></p></td>
<td><p><span data-ttu-id="9f144-124">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="9f144-124">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="9f144-125">Ninguna entrada</span><span class="sxs-lookup"><span data-stu-id="9f144-125">No Entry</span></span></p></td>
<td><div>

> [!IMPORTANT]  
> <span data-ttu-id="9f144-126">Tenga en cuenta que la longitud de clave mínima es 1024, pero es posible que reciba una advertencia que indica que la longitud de clave mínima recomendada es de 2048 bits.</span><span class="sxs-lookup"><span data-stu-id="9f144-126">Note that the minimum key length is 1024, but you may receive a warning that the minimum recommended key length is 2048 bits.</span></span>


</div>
<p><span data-ttu-id="9f144-127">El certificado OAuthTokenIssuer es un certificado de un único propósito para el propósito de autenticar servidores en un entorno de gran escala y se puede solicitar desde una entidad de certificación interna o desde una CA pública.</span><span class="sxs-lookup"><span data-stu-id="9f144-127">The OAuthTokenIssuer certificate is a single-purpose certificate for the purpose of authenticating servers in a large-scale environment, and can be requested from an internal CA or from a public CA.</span></span> <span data-ttu-id="9f144-128">El certificado es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="9f144-128">The certificate is required.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

