---
title: Resumen de certificado-SIP, Federación XMPP y mensajería instantánea pública
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - SIP, XMPP federation, and public instant messaging
ms:assetid: 933d6351-cfa6-4432-b3ed-1aff3ac92065
ms:mtpsurl: https://technet.microsoft.com/library/JJ618372(v=OCS.15)
ms:contentKeyID: 49105659
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 284a633a2c5ce820009c6672058837bbecb7ecd6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517877"
---
# <a name="certificate-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="0317f-102">Resumen de certificado: SIP, Federación XMPP y mensajería instantánea pública en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0317f-102">Certificate summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0317f-103">_**Última modificación del tema:** 2013-03-15_</span><span class="sxs-lookup"><span data-stu-id="0317f-103">_**Topic Last Modified:** 2013-03-15_</span></span>

<span data-ttu-id="0317f-104">Los certificados que se necesitan para federar con Microsoft Lync Server 2013, Lync Server 2010 y Office Communications Server se suelen cumplir con los certificados que configure, solicite y asigne a su servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="0317f-104">The certificates that you need for federating with Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server will typically be met by the certificates that you configure, request and assign to your Edge Server.</span></span>

<span data-ttu-id="0317f-105">Los requisitos de certificado para habilitar y establecer comunicaciones con los asociados del protocolo extensible de mensajería y presencia (XMPP) requieren la adición de entradas para los dominios XMPP.</span><span class="sxs-lookup"><span data-stu-id="0317f-105">Certificate requirements for enabling and establishing communications with extensible messaging and presence protocol (XMPP) partners require addition of entries for your XMPP domains.</span></span> <span data-ttu-id="0317f-106">El registro incluido en el certificado como nombre alternativo del firmante (SAN) será el dominio que puede participar en las comunicaciones XMPP.</span><span class="sxs-lookup"><span data-stu-id="0317f-106">The record that is included on the certificate as a subject alternative name (SAN) will be the domain that can participate in XMPP communications.</span></span> <span data-ttu-id="0317f-107">El dominio puede ser el dominio de nivel de raíz (por ejemplo, contoso.com) si desea habilitar XMPP para todo el dominio, o bien dominios secundarios seleccionados (por ejemplo, corp.contoso.com, finance.contoso.com) si desea habilitar XMPP para un subconjunto de usuarios.</span><span class="sxs-lookup"><span data-stu-id="0317f-107">The domain can be the root-level domain (for example, contoso.com) if you want to enable XMPP for your entire domain, or can be selected child domains (for example, corp.contoso.com, finance.contoso.com) if you are enabling XMPP for a subset of users.</span></span>

<span data-ttu-id="0317f-108">Para configurar certificados para la conectividad de mensajería instantánea pública, tenga en cuenta que no hay nada diferente de otros tipos de Federación SIP o de certificados de servidor perimetral estándar, excepto que America Online (AOL) requiere el certificado o los certificados (en el caso de un grupo de servidores perimetrales) que también contengan el EKU de cliente.</span><span class="sxs-lookup"><span data-stu-id="0317f-108">To configure certificates for public Instant Messaging connectivity, note that there is nothing different from other SIP federation types or even standard Edge Server certificates, except that America Online (AOL) requires a the certificate or certificates (in the case of an Edge pool) to also contain the client EKU.</span></span> <span data-ttu-id="0317f-109">El EKU de cliente es una adición al certificado y forma parte del certificado público externo que se asigna a su servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="0317f-109">The client EKU is an addition to the certificate, and is part of the external public certificate that is assigned to your Edge Server.</span></span>

<span data-ttu-id="0317f-110">Para confirmar que ha cumplido los requisitos de certificado correctos para la implementación del servidor perimetral, revise los temas que se enumeran en la sección **vea también**.</span><span class="sxs-lookup"><span data-stu-id="0317f-110">To confirm that you have met the correct certificate requirements for your Edge Server deployment, review the topics listed in the section titled **See Also**.</span></span>

<div>



<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0317f-111">Componente</span><span class="sxs-lookup"><span data-stu-id="0317f-111">Component</span></span></th>
<th><span data-ttu-id="0317f-112">Nombre de sujeto</span><span class="sxs-lookup"><span data-stu-id="0317f-112">Subject name</span></span></th>
<th><span data-ttu-id="0317f-113">Nombres alternativos del sujeto (SAN)</span><span class="sxs-lookup"><span data-stu-id="0317f-113">Subject alternative names (SAN)</span></span></th>
<th><span data-ttu-id="0317f-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0317f-114">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0317f-115">Servidor perimetral de acceso/externo</span><span class="sxs-lookup"><span data-stu-id="0317f-115">External/Access Edge</span></span></p></td>
<td><p><span data-ttu-id="0317f-116">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0317f-116">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0317f-117">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0317f-117">sip.contoso.com</span></span></p>
<p><span data-ttu-id="0317f-118">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0317f-118">webcon.contoso.com</span></span></p>
<p><span data-ttu-id="0317f-119">contoso.com</span><span class="sxs-lookup"><span data-stu-id="0317f-119">contoso.com</span></span></p>



> [!NOTE]
> <span data-ttu-id="0317f-120">Para admitir el espacio de nombres XMPP de contoso.com</span><span class="sxs-lookup"><span data-stu-id="0317f-120">To support the contoso.com XMPP namespace</span></span>


<p><span data-ttu-id="0317f-121">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="0317f-121">sip.fabrikam.com</span></span></p>



> [!NOTE]
> <span data-ttu-id="0317f-122">Para admitir el espacio de nombres SIP fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="0317f-122">To support the fabrikam.com SIP namespace</span></span>


<p><span data-ttu-id="0317f-123">fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="0317f-123">fabrikam.com</span></span></p>



> [!NOTE]
> <span data-ttu-id="0317f-124">Para admitir el espacio de nombres XMPP de fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="0317f-124">To support the fabrikam.com XMPP namespace</span></span>

</td>
<td><p><span data-ttu-id="0317f-125">El certificado debe ser de una entidad de certificación pública y debe tener el EKU de servidor y el EKU de cliente si se va a implementar la conectividad de mensajería instantánea pública con AOL.</span><span class="sxs-lookup"><span data-stu-id="0317f-125">The certificate must be from a Public CA, and must have the server EKU and client EKU if public IM connectivity with AOL is to be deployed.</span></span> <span data-ttu-id="0317f-126">El certificado se asigna a las interfaces del servidor perimetral externo para:</span><span class="sxs-lookup"><span data-stu-id="0317f-126">The certificate is assigned to the external Edge Server interfaces for:</span></span></p>
<ul>
<li><p><span data-ttu-id="0317f-127">Servicio perimetral de acceso</span><span class="sxs-lookup"><span data-stu-id="0317f-127">Access Edge service</span></span></p></li>
<li><p><span data-ttu-id="0317f-128">Servicio perimetral de conferencias web</span><span class="sxs-lookup"><span data-stu-id="0317f-128">Web Conferencing Edge service</span></span></p></li>
<li><p><span data-ttu-id="0317f-129">Servicio perimetral A/V</span><span class="sxs-lookup"><span data-stu-id="0317f-129">A/V Edge service</span></span></p></li>
</ul>



> [!NOTE]
> <span data-ttu-id="0317f-130">Técnicamente, no se asigna un certificado al servidor perimetral a/V.</span><span class="sxs-lookup"><span data-stu-id="0317f-130">Technically, a certificate is not assigned to the A/V Edge.</span></span> <span data-ttu-id="0317f-131">La comunicación y la autenticación seguras se administran mediante el servicio de autenticación relé multimedia (MRAS).</span><span class="sxs-lookup"><span data-stu-id="0317f-131">Secure communication and authentication is managed by way of the Media Relay Authentication Service (MRAS).</span></span> <span data-ttu-id="0317f-132">MRAS usa el certificado asignado a la interfaz interna del servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="0317f-132">MRAS uses the certificate assigned to the Edge Server internal interface.</span></span>


<p><span data-ttu-id="0317f-p105">Tenga en cuenta que las SAN se agregan automáticamente al certificado basado en las definiciones del Generador de topologías. Agregue entradas SAN según sea necesario para dominios adicionales de SIP y otras entradas que necesite admitir. El nombre del sujeto se replica en la SAN y debe estar presente para el correcto funcionamiento.</span><span class="sxs-lookup"><span data-stu-id="0317f-p105">Note that SANs are automatically added to the certificate based on your definitions in Topology Builder. You add SAN entries as needed for additional SIP domains and other entries that you need to support. The subject name is replicated in the SAN and must be present for correct operation.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0317f-136">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0317f-136">See Also</span></span>


[<span data-ttu-id="0317f-137">Configuración XMPP de ejemplo en Lync Server 2013: Federación XMPP con Google Talk</span><span class="sxs-lookup"><span data-stu-id="0317f-137">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</span></span>](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[<span data-ttu-id="0317f-138">Planeación de certificados de servidor perimetral en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0317f-138">Plan for Edge Server certificates in Lync Server 2013</span></span>](lync-server-2013-plan-for-edge-server-certificates.md)  
[<span data-ttu-id="0317f-139">Resumen de certificado-perímetro consolidado de un solo consolidado con direcciones IP privadas mediante NAT en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0317f-139">Certificate summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)  
[<span data-ttu-id="0317f-140">Resumen de certificado-perímetro consolidado de un solo consolidado con direcciones IP públicas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0317f-140">Certificate summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-single-consolidated-edge-with-public-ip-addresses.md)  
[<span data-ttu-id="0317f-141">Resumen de certificado-servidor perimetral consolidado ampliado, equilibrio de carga DNS con direcciones IP privadas mediante NAT en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0317f-141">Certificate summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-private-ip.md)  
[<span data-ttu-id="0317f-142">Resumen de certificado-servidor perimetral consolidado ampliado, equilibrio de carga DNS con direcciones IP públicas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0317f-142">Certificate summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)  
[<span data-ttu-id="0317f-143">Resumen de certificado-servidor perimetral consolidado ampliado con equilibradores de carga de hardware en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0317f-143">Certificate summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

