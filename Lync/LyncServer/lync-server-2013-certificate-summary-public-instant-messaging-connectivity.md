---
title: 'Lync Server 2013: Resumen de certificado-conectividad de mensajería instantánea pública'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Public instant messaging connectivity
ms:assetid: 2b3687ee-50c2-4c1c-880e-8dcf8bd4f309
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618370(v=OCS.15)
ms:contentKeyID: 49105657
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bdc4bba8064332d7fa3f90d0d6a3d4b9f6cef9e6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512787"
---
# <a name="certificate-summary---public-instant-messaging-connectivity-in-lync-server-2013"></a><span data-ttu-id="64ed0-102">Resumen de certificado-conectividad de mensajería instantánea pública en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="64ed0-102">Certificate summary - Public instant messaging connectivity in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="64ed0-103">_**Última modificación del tema:** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="64ed0-103">_**Topic Last Modified:** 2013-02-19_</span></span>

<span data-ttu-id="64ed0-104">Para configurar certificados para la conectividad de mensajería instantánea pública, debe tener en cuenta en primer lugar que no hay nada diferente de otros tipos de Federación SIP o incluso los certificados de servidor perimetral estándar, excepto en que America Online (AOL) requiere una configuración de certificado única.</span><span class="sxs-lookup"><span data-stu-id="64ed0-104">To configure certificates for public Instant Messaging connectivity, you should first notice that there is nothing different from other SIP federation types or even standard Edge Server certificates, except that America Online (AOL) requires a unique certificate configuration.</span></span> <span data-ttu-id="64ed0-105">Además del uso mejorado de claves (EKU) del servidor, America Online requiere que el certificado o los certificados (en el caso de un grupo de servidores perimetrales) también contengan el EKU del cliente.</span><span class="sxs-lookup"><span data-stu-id="64ed0-105">In addition to the usual server enhanced key usage (EKU), America Online requires the certificate or certificates (in the case of an Edge pool) to also contain the client EKU.</span></span> <span data-ttu-id="64ed0-106">El EKU de cliente es una adición al certificado y forma parte del certificado público externo que se asigna a su servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="64ed0-106">The client EKU is an addition to the certificate, and is part of the external public certificate that is assigned to your Edge Server.</span></span>

<div>

## <a name="certificate-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="64ed0-107">Resumen del certificado: conectividad de mensajería instantánea pública</span><span class="sxs-lookup"><span data-stu-id="64ed0-107">Certificate Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="64ed0-108">Componente</span><span class="sxs-lookup"><span data-stu-id="64ed0-108">Component</span></span></th>
<th><span data-ttu-id="64ed0-109">Nombre de sujeto</span><span class="sxs-lookup"><span data-stu-id="64ed0-109">Subject name</span></span></th>
<th><span data-ttu-id="64ed0-110">Nombres alternativos del sujeto (SAN)/orden</span><span class="sxs-lookup"><span data-stu-id="64ed0-110">Subject alternative names (SAN)/Order</span></span></th>
<th><span data-ttu-id="64ed0-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="64ed0-111">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="64ed0-112">Servidor perimetral de acceso/externo</span><span class="sxs-lookup"><span data-stu-id="64ed0-112">External/Access Edge</span></span></p></td>
<td><p><span data-ttu-id="64ed0-113">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="64ed0-113">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="64ed0-114">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="64ed0-114">sip.contoso.com</span></span></p>
<p><span data-ttu-id="64ed0-115">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="64ed0-115">webcon.contoso.com</span></span></p>
<p><span data-ttu-id="64ed0-116">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="64ed0-116">sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="64ed0-117">El certificado debe ser de una entidad de certificación pública y debe tener el EKU de servidor y el EKU de cliente si se va a implementar la conectividad de mensajería instantánea pública con AOL.</span><span class="sxs-lookup"><span data-stu-id="64ed0-117">The certificate must be from a Public CA, and must have the server EKU and client EKU if public IM connectivity with AOL is to be deployed.</span></span> <span data-ttu-id="64ed0-118">El certificado se asigna a las interfaces del servidor perimetral externo para:</span><span class="sxs-lookup"><span data-stu-id="64ed0-118">The certificate is assigned to the external Edge Server interfaces for:</span></span></p>
<ul>
<li><p><span data-ttu-id="64ed0-119">Servicio perimetral de acceso</span><span class="sxs-lookup"><span data-stu-id="64ed0-119">Access Edge service</span></span></p></li>
<li><p><span data-ttu-id="64ed0-120">Servicio perimetral de conferencias web</span><span class="sxs-lookup"><span data-stu-id="64ed0-120">Web Conferencing Edge service</span></span></p></li>
<li><p><span data-ttu-id="64ed0-121">Servicio perimetral A/V</span><span class="sxs-lookup"><span data-stu-id="64ed0-121">A/V Edge service</span></span></p></li>
</ul>
<p><span data-ttu-id="64ed0-p103">Tenga en cuenta que las SAN se agregan automáticamente al certificado basado en las definiciones del Generador de topologías. Agregue entradas SAN según sea necesario para dominios adicionales de SIP y otras entradas que necesite admitir. El nombre del sujeto se replica en la SAN y debe estar presente para el correcto funcionamiento.</span><span class="sxs-lookup"><span data-stu-id="64ed0-p103">Note that SANs are automatically added to the certificate based on your definitions in Topology Builder. You add SAN entries as needed for additional SIP domains and other entries that you need to support. The subject name is replicated in the SAN and must be present for correct operation.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="64ed0-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="64ed0-125">See Also</span></span>


[<span data-ttu-id="64ed0-126">Escenarios para el acceso de usuarios externos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="64ed0-126">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

