---
title: 'Lync Server 2013: Requisitos de certificado para el acceso de usuarios externos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate requirements for external user access
ms:assetid: d45b6b10-556f-4b10-b1a7-fb0d0a64a498
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398920(v=OCS.15)
ms:contentKeyID: 48185503
ms.date: 03/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1b6495dbad5350f94873099985922f1adc198f2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736840"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="c1598-102">Requisitos de certificado para el acceso de usuarios externos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c1598-102">Certificate requirements for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c1598-103">_**Última modificación del tema:** 2016-03-29_</span><span class="sxs-lookup"><span data-stu-id="c1598-103">_**Topic Last Modified:** 2016-03-29_</span></span>

<span data-ttu-id="c1598-104">El software de comunicaciones Microsoft Lync Server 2013 admite el uso de un único certificado público para las interfaces externas de acceso y de conferencia Web, además del servicio de autenticación A/V.</span><span class="sxs-lookup"><span data-stu-id="c1598-104">Microsoft Lync Server 2013 communications software supports the use of a single public certificate for access and web conferencing Edge external interfaces, plus the A/V Authentication service.</span></span> <span data-ttu-id="c1598-105">La interfaz interna de Edge generalmente usa un certificado privado emitido por una entidad de certificación (CA) interna, pero también puede usar un certificado público, siempre que proviene de una CA pública de confianza.</span><span class="sxs-lookup"><span data-stu-id="c1598-105">The Edge internal interface typically uses a private certificate issued by an internal certification authority (CA), but can also use a public certificate, provided that it is from a trusted public CA.</span></span> <span data-ttu-id="c1598-106">El proxy inverso de la implementación usa un certificado público y cifra la comunicación desde el proxy inverso a los clientes y el proxy inverso a los servidores internos mediante HTTP (es decir, la seguridad de la capa de transporte a través de HTTP).</span><span class="sxs-lookup"><span data-stu-id="c1598-106">The reverse proxy in your deployment uses a public certificate and encrypts the communication from the reverse proxy to clients and the reverse proxy to internal servers by using HTTP (that is, Transport Layer Security over HTTP).</span></span>

<span data-ttu-id="c1598-107">A continuación se indican los requisitos para el certificado público que se usa para las interfaces externas de acceso y de la conferencia Web, y el servicio de autenticación A/V:</span><span class="sxs-lookup"><span data-stu-id="c1598-107">Following are the requirements for the public certificate used for access and web conferencing Edge external interfaces, and the A/V authentication service:</span></span>

  - <span data-ttu-id="c1598-108">El certificado debe ser emitido por una entidad de certificación pública aprobada que admita el nombre alternativo del sujeto.</span><span class="sxs-lookup"><span data-stu-id="c1598-108">The certificate must be issued by an approved public CA that supports subject alternative name.</span></span> <span data-ttu-id="c1598-109">Para obtener más información, consulte el artículo 929395 de Microsoft Knowledge base, "asociados de certificados de comunicaciones unificadas para Exchange Server [http://go.microsoft.com/fwlink/p/?linkId=202834](http://go.microsoft.com/fwlink/p/?linkid=202834)y Communications Server", en.</span><span class="sxs-lookup"><span data-stu-id="c1598-109">For details, see Microsoft Knowledge Base article 929395, "Unified Communications Certificate Partners for Exchange Server and for Communications Server," at [http://go.microsoft.com/fwlink/p/?linkId=202834](http://go.microsoft.com/fwlink/p/?linkid=202834).</span></span>

  - <span data-ttu-id="c1598-110">Si el certificado se va a usar en un grupo perimetral, debe crearse como exportable, con el mismo certificado que se usa en cada servidor perimetral del grupo Edge.</span><span class="sxs-lookup"><span data-stu-id="c1598-110">If the certificate will be used on an Edge pool, it must be created as exportable, with the same certificate used on each Edge Server in the Edge pool.</span></span> <span data-ttu-id="c1598-111">El requisito de clave privada exportable es para los fines del servicio de autenticación A/V, que debe usar la misma clave privada en todos los servidores perimetrales del grupo.</span><span class="sxs-lookup"><span data-stu-id="c1598-111">The exportable private key requirement is for the purposes of the A/V Authentication service, which must use the same private key across all Edge Servers in the pool.</span></span>

  - <span data-ttu-id="c1598-112">Si desea maximizar el tiempo de actividad de sus servicios de audio/vídeo, revise los requisitos del certificado para implementar un certificado de servicio perimetral A/V desvinculado (es decir, un certificado de servicio perimetral A/V independiente de los otros objetivos de certificado de borde externo).</span><span class="sxs-lookup"><span data-stu-id="c1598-112">If you want to maximize the uptime for your Audio/Video services, review the certificate requirements for implementing a decoupled A/V Edge service certificate (that is, a separate A/V Edge service certificate from the other External Edge certificate purposes).</span></span> <span data-ttu-id="c1598-113">Para obtener más información, vea [cambios en Lync server 2013 que afectan a la planeación de los servidores perimetrales](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md), [plan para certificados de servidor perimetral en Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md) y [certificados AV y OAuth en Lync Server 2013 mediante-Roll en Set-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate).</span><span class="sxs-lookup"><span data-stu-id="c1598-113">For details, see [Changes in Lync Server 2013 that affect Edge Server planning](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md), [Plan for Edge Server certificates in Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md) and [Staging AV and OAuth certificates in Lync Server 2013 using -Roll in Set-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate).</span></span>

  - <span data-ttu-id="c1598-114">El nombre de firmante del certificado es el nombre de dominio completo de la interfaz externa de servicio perimetral de Access (FQDN) o el equilibrio de carga de hardware VIP (por ejemplo, access.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="c1598-114">The subject name of the certificate is the Access Edge service external interface fully qualified domain name (FQDN) or hardware load balancer VIP (for example, access.contoso.com).</span></span> <span data-ttu-id="c1598-115">).</span><span class="sxs-lookup"><span data-stu-id="c1598-115">).</span></span> <span data-ttu-id="c1598-116">El nombre del asunto no puede tener un carácter comodín, debe ser un nombre explícito.</span><span class="sxs-lookup"><span data-stu-id="c1598-116">The subject name can’t have a wildcard character, it must be an explicit name.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c1598-117">Para Lync Server 2013, esto ya no es necesario, pero se le sigue recomendando para la compatibilidad con Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="c1598-117">For Lync Server 2013, this is no longer a requirement, but it is still recommended for compatibility with Office Communications Server.</span></span>

    
    </div>

  - <span data-ttu-id="c1598-118">La lista de nombres alternativos de asunto contiene los FQDN de los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="c1598-118">The subject alternative name list contains the FQDNs of the following:</span></span>
    
      - <span data-ttu-id="c1598-119">La VIP de la interfaz externa del servicio perimetral de acceso o del equilibrador de carga del hardware (por ejemplo, sip.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="c1598-119">The Access Edge service external interface or hardware load balancer VIP (for example, sip.contoso.com).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="c1598-120">Aunque el nombre del sujeto del certificado es igual al FQDN del perímetro de acceso, el nombre alternativo del sujeto también debe contener el FQDN del perímetro de acceso porque la seguridad de la capa de transporte (TLS) omite el nombre del sujeto y usa las entradas de nombre alternativo de asunto para validación.</span><span class="sxs-lookup"><span data-stu-id="c1598-120">Even though the certificate subject name is equal to the access Edge FQDN, the subject alternative name must also contain the access Edge FQDN because Transport Layer Security (TLS) ignores the subject name and uses the subject alternative name entries for validation.</span></span>

        
        </div>
    
      - <span data-ttu-id="c1598-121">La interfaz externa perimetral de la conferencia web o el equilibrador de carga del hardware VIP (por ejemplo, webcon.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="c1598-121">The web conferencing Edge external interface or hardware load balancer VIP (for example, webcon.contoso.com).</span></span>
    
      - <span data-ttu-id="c1598-122">Si está usando la configuración automática o la Federación de clientes, incluya también cualquier FQDN de dominio SIP usado dentro de su empresa (por ejemplo, sip.contoso.com, sip.fabrikam.com).</span><span class="sxs-lookup"><span data-stu-id="c1598-122">If you are using client auto-configuration or federation, also include any SIP domain FQDNs used within your company (for example, sip.contoso.com, sip.fabrikam.com).</span></span>
    
      - <span data-ttu-id="c1598-123">El servicio de borde A/V no usa las entradas de nombre de sujeto o de nombre alternativo de asunto.</span><span class="sxs-lookup"><span data-stu-id="c1598-123">The A/V Edge service does not use the subject name or the subject alternative names entries.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c1598-124">El orden de los FQDN en la lista de nombres alternativos de asunto no es relevante.</span><span class="sxs-lookup"><span data-stu-id="c1598-124">The order of the FQDNs in the subject alternative names list does not matter.</span></span>

    
    </div>

<span data-ttu-id="c1598-125">Si implementa varios servidores perimetrales con equilibrio de carga en un sitio, el certificado del servicio de autenticación A/V instalado en cada servidor perimetral debe ser de la misma CA y debe usar la misma clave privada.</span><span class="sxs-lookup"><span data-stu-id="c1598-125">If you are deploying multiple, load-balanced Edge Servers at a site, the A/V authentication service certificate that is installed on each Edge Server must be from the same CA and must use the same private key.</span></span> <span data-ttu-id="c1598-126">Tenga en cuenta que la clave privada del certificado debe ser exportable, independientemente de si se usa en un servidor perimetral o en muchos servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="c1598-126">Note that the certificate's private key must be exportable, regardless of whether it is used on one Edge Server or many Edge Servers.</span></span> <span data-ttu-id="c1598-127">También debe ser exportable si solicita el certificado desde cualquier equipo que no sea el servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="c1598-127">It must also be exportable if you request the certificate from any computer other than the Edge Server.</span></span> <span data-ttu-id="c1598-128">Puesto que el servicio de autenticación A/V no usa el nombre de asunto o el nombre alternativo de asunto, puede reutilizar el certificado perimetral de acceso siempre que se cumplan los requisitos de nombre de asunto y nombre alternativo del asunto para el límite de acceso y la clave privada del certificado, y la clave privada del certificado se puede exportar.</span><span class="sxs-lookup"><span data-stu-id="c1598-128">Because the A/V authentication service does not use the subject name or subject alternative name, you can reuse the access Edge certificate as long as the subject name and subject alternative name requirements are met for the access Edge and the web conferencing Edge and the certificate’s private key is exportable.</span></span>

<span data-ttu-id="c1598-129">Los requisitos para el certificado privado (o público) que se usa para la interfaz interna de Edge son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="c1598-129">Requirements for the private (or public) certificate used for the Edge internal interface are as follows:</span></span>

  - <span data-ttu-id="c1598-130">El certificado puede ser emitido por una entidad de certificación interna o por una entidad emisora de certificados pública aprobada.</span><span class="sxs-lookup"><span data-stu-id="c1598-130">The certificate can be issued by an internal CA or an approved public certificate CA.</span></span>

  - <span data-ttu-id="c1598-131">El nombre de firmante del certificado suele ser el FQDN de la interfaz interna del perímetro o el VIP del equilibrador de carga de hardware (por ejemplo, lsedge.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="c1598-131">The subject name of the certificate is typically the Edge internal interface FQDN or hardware load balancer VIP (for example, lsedge.contoso.com).</span></span> <span data-ttu-id="c1598-132">Sin embargo, puede usar un certificado comodín en el perímetro interno.</span><span class="sxs-lookup"><span data-stu-id="c1598-132">However, you can use a wildcard certificate on the Edge internal.</span></span>

  - <span data-ttu-id="c1598-133">No se requiere ninguna lista de nombres alternativos de asunto.</span><span class="sxs-lookup"><span data-stu-id="c1598-133">No subject alternative name list is required.</span></span>

<span data-ttu-id="c1598-134">El proxy inverso en las solicitudes de servicios de implementación para:</span><span class="sxs-lookup"><span data-stu-id="c1598-134">The reverse proxy in your deployment services requests for:</span></span>

  - <span data-ttu-id="c1598-135">Acceso de usuarios externos a contenido de reuniones para reuniones</span><span class="sxs-lookup"><span data-stu-id="c1598-135">External user access to meeting content for meetings</span></span>

  - <span data-ttu-id="c1598-136">Acceso de usuarios externos para expandir y mostrar miembros de grupos de distribución</span><span class="sxs-lookup"><span data-stu-id="c1598-136">External user access to expand and display members of distribution groups</span></span>

  - <span data-ttu-id="c1598-137">Acceso de usuarios externos a archivos descargables desde el servicio de libreta de direcciones</span><span class="sxs-lookup"><span data-stu-id="c1598-137">External user access to downloadable files from the Address Book Service</span></span>

  - <span data-ttu-id="c1598-138">Acceso de usuarios externos al cliente de Lync Web App</span><span class="sxs-lookup"><span data-stu-id="c1598-138">External user access to the Lync Web App client</span></span>

  - <span data-ttu-id="c1598-139">Acceso de usuarios externos a la Página Web de la configuración de conferencias de acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="c1598-139">External user access to the Dial-in Conferencing Settings web page</span></span>

  - <span data-ttu-id="c1598-140">Acceso de usuarios externos al servicio de información de ubicación</span><span class="sxs-lookup"><span data-stu-id="c1598-140">External user access to the Location Information Service</span></span>

  - <span data-ttu-id="c1598-141">Acceso de dispositivo externo al servicio de actualización de dispositivos y obtener actualizaciones</span><span class="sxs-lookup"><span data-stu-id="c1598-141">External device access to the Device Update Service and obtain updates</span></span>

<span data-ttu-id="c1598-142">El proxy inverso publica las direcciones URL de los componentes Web internos del servidor.</span><span class="sxs-lookup"><span data-stu-id="c1598-142">The reverse proxy publishes the internal server Web Components URLs.</span></span> <span data-ttu-id="c1598-143">Las direcciones URL de los componentes Web se definen en el director, el servidor front-end o el grupo front-end como **servicios web externos** en el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="c1598-143">The Web Components URLs are defined on the Director, Front End Server or Front End pool as the **External web services** in Topology Builder.</span></span>

<span data-ttu-id="c1598-144">Las entradas con comodín son compatibles con el campo Nombre alternativo del sujeto del certificado asignado al proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="c1598-144">Wildcard entries are supported in the subject alternative name field of the certificate assigned to the reverse proxy.</span></span> <span data-ttu-id="c1598-145">Para obtener más información sobre cómo configurar la solicitud de certificado para el proxy inverso, consulte [solicitar y configurar un certificado para su proxy http inverso en Lync Server 2013](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="c1598-145">For details about how to configure the certificate request for the reverse proxy, see [Request and configure a certificate for your reverse HTTP proxy in Lync Server 2013](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="c1598-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="c1598-146">See Also</span></span>


[<span data-ttu-id="c1598-147">Compatibilidad de certificado de comodín en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c1598-147">Wildcard certificate support in Lync Server 2013</span></span>](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

