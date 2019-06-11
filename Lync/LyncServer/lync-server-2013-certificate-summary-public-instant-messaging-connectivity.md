---
title: 'Lync Server 2013: Resumen del certificado-conectividad de mensajería instantánea pública'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate summary - Public instant messaging connectivity
ms:assetid: 2b3687ee-50c2-4c1c-880e-8dcf8bd4f309
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618370(v=OCS.15)
ms:contentKeyID: 49105657
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31988207403ef1ccb5ea366da6e1ec6b3d448b4e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842639"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---public-instant-messaging-connectivity-in-lync-server-2013"></a><span data-ttu-id="72cc4-102">Resumen del certificado: conectividad de mensajería instantánea pública en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72cc4-102">Certificate summary - Public instant messaging connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="72cc4-103">_**Última modificación del tema:** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="72cc4-103">_**Topic Last Modified:** 2013-02-19_</span></span>

<span data-ttu-id="72cc4-104">Para configurar certificados para la conectividad de mensajería instantánea pública, primero debe tener en cuenta que no hay nada diferente de otros tipos de Federación SIP o incluso los certificados de servidor perimetral estándar, excepto que America Online (AOL) requiere un único configuración de certificado.</span><span class="sxs-lookup"><span data-stu-id="72cc4-104">To configure certificates for public Instant Messaging connectivity, you should first notice that there is nothing different from other SIP federation types or even standard Edge Server certificates, except that America Online (AOL) requires a unique certificate configuration.</span></span> <span data-ttu-id="72cc4-105">Además del uso mejorado de claves (EKU) del servidor, America Online requiere que el certificado o los certificados (en el caso de un grupo de límites) contengan también el EKU de cliente.</span><span class="sxs-lookup"><span data-stu-id="72cc4-105">In addition to the usual server enhanced key usage (EKU), America Online requires the certificate or certificates (in the case of an Edge pool) to also contain the client EKU.</span></span> <span data-ttu-id="72cc4-106">El EKU de cliente es una adición al certificado y forma parte del certificado público externo que se asigna al servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="72cc4-106">The client EKU is an addition to the certificate, and is part of the external public certificate that is assigned to your Edge Server.</span></span>

<div>

## <a name="certificate-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="72cc4-107">Resumen del certificado: conectividad de mensajería instantánea pública</span><span class="sxs-lookup"><span data-stu-id="72cc4-107">Certificate Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="72cc4-108">Componente</span><span class="sxs-lookup"><span data-stu-id="72cc4-108">Component</span></span></th>
<th><span data-ttu-id="72cc4-109">Nombre del asunto</span><span class="sxs-lookup"><span data-stu-id="72cc4-109">Subject name</span></span></th>
<th><span data-ttu-id="72cc4-110">Nombres alternativos de asunto (SAN)/Order</span><span class="sxs-lookup"><span data-stu-id="72cc4-110">Subject alternative names (SAN)/Order</span></span></th>
<th><span data-ttu-id="72cc4-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="72cc4-111">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="72cc4-112">Perimetral de acceso externo</span><span class="sxs-lookup"><span data-stu-id="72cc4-112">External/Access Edge</span></span></p></td>
<td><p><span data-ttu-id="72cc4-113">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="72cc4-113">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="72cc4-114">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="72cc4-114">sip.contoso.com</span></span></p>
<p><span data-ttu-id="72cc4-115">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="72cc4-115">webcon.contoso.com</span></span></p>
<p><span data-ttu-id="72cc4-116">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="72cc4-116">sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="72cc4-117">El certificado debe ser de una entidad de certificación pública y debe tener el EKU de servidor y el EKU de cliente si se va a implementar la conectividad de mensajería instantánea pública con AOL.</span><span class="sxs-lookup"><span data-stu-id="72cc4-117">The certificate must be from a Public CA, and must have the server EKU and client EKU if public IM connectivity with AOL is to be deployed.</span></span> <span data-ttu-id="72cc4-118">El certificado se asigna a las interfaces del servidor perimetral externo para:</span><span class="sxs-lookup"><span data-stu-id="72cc4-118">The certificate is assigned to the external Edge Server interfaces for:</span></span></p>
<ul>
<li><p><span data-ttu-id="72cc4-119">Servicio perimetral de acceso</span><span class="sxs-lookup"><span data-stu-id="72cc4-119">Access Edge service</span></span></p></li>
<li><p><span data-ttu-id="72cc4-120">Servicio perimetral de conferencia web</span><span class="sxs-lookup"><span data-stu-id="72cc4-120">Web Conferencing Edge service</span></span></p></li>
<li><p><span data-ttu-id="72cc4-121">Servicio perimetral A/V</span><span class="sxs-lookup"><span data-stu-id="72cc4-121">A/V Edge service</span></span></p></li>
</ul>
<p><span data-ttu-id="72cc4-122">Tenga en cuenta que las redes San se agregan automáticamente al certificado según sus definiciones en el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="72cc4-122">Note that SANs are automatically added to the certificate based on your definitions in Topology Builder.</span></span> <span data-ttu-id="72cc4-123">Agregue las entradas de SAN según sea necesario para dominios SIP adicionales y otras entradas que necesite admitir.</span><span class="sxs-lookup"><span data-stu-id="72cc4-123">You add SAN entries as needed for additional SIP domains and other entries that you need to support.</span></span> <span data-ttu-id="72cc4-124">El nombre del asunto se replica en el SAN y debe estar presente para que funcione correctamente.</span><span class="sxs-lookup"><span data-stu-id="72cc4-124">The subject name is replicated in the SAN and must be present for correct operation.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="72cc4-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="72cc4-125">See Also</span></span>


[<span data-ttu-id="72cc4-126">Escenarios para el acceso de usuarios externos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72cc4-126">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

