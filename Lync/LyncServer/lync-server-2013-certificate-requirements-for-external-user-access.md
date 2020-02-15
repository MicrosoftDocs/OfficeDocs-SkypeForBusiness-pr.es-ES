---
title: 'Lync Server 2013: requisitos de certificado para el acceso de usuarios externos'
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
ms.openlocfilehash: 7000456629a91742350b9866dc9e1441c18eee57
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030874"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="c5350-102">Requisitos de certificado para el acceso de usuarios externos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5350-102">Certificate requirements for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c5350-103">_**Última modificación del tema:** 2016-03-29_</span><span class="sxs-lookup"><span data-stu-id="c5350-103">_**Topic Last Modified:** 2016-03-29_</span></span>

<span data-ttu-id="c5350-104">El software de comunicaciones Microsoft Lync Server 2013 admite el uso de un único certificado público para las interfaces externas perimetrales de acceso y conferencia Web, además del servicio de autenticación A/V.</span><span class="sxs-lookup"><span data-stu-id="c5350-104">Microsoft Lync Server 2013 communications software supports the use of a single public certificate for access and web conferencing Edge external interfaces, plus the A/V Authentication service.</span></span> <span data-ttu-id="c5350-105">La interfaz interna perimetral utiliza generalmente un certificado privado que emite una autoridad de certificación (CA) interna, pero también puede utilizar un certificado público siempre y cuando sea de una CA pública de confianza.</span><span class="sxs-lookup"><span data-stu-id="c5350-105">The Edge internal interface typically uses a private certificate issued by an internal certification authority (CA), but can also use a public certificate, provided that it is from a trusted public CA.</span></span> <span data-ttu-id="c5350-106">El servidor proxy inverso de la implementación utiliza un certificado público y cifra la comunicación desde el proxy inverso hacia los clientes y del proxy inverso hacia los servidores internos utilizando HTTP (es decir, seguridad de la capa de transporte por HTTP).</span><span class="sxs-lookup"><span data-stu-id="c5350-106">The reverse proxy in your deployment uses a public certificate and encrypts the communication from the reverse proxy to clients and the reverse proxy to internal servers by using HTTP (that is, Transport Layer Security over HTTP).</span></span>

<span data-ttu-id="c5350-107">A continuación, se indican los requisitos para el certificado público usado para interfaces externas perimetrales, de conferencia web y de acceso, así como el servicio de autenticación A/V:</span><span class="sxs-lookup"><span data-stu-id="c5350-107">Following are the requirements for the public certificate used for access and web conferencing Edge external interfaces, and the A/V authentication service:</span></span>

  - <span data-ttu-id="c5350-108">El certificado debe ser emitido por una CA pública aprobada que admita el nombre alternativo de sujeto.</span><span class="sxs-lookup"><span data-stu-id="c5350-108">The certificate must be issued by an approved public CA that supports subject alternative name.</span></span> <span data-ttu-id="c5350-109">Para obtener más información, consulte el artículo 929395 de Microsoft Knowledge base, "asociados de certificados de comunicaciones unificadas para Exchange Server [http://go.microsoft.com/fwlink/p/?linkId=202834](http://go.microsoft.com/fwlink/p/?linkid=202834)y para Communications Server" en.</span><span class="sxs-lookup"><span data-stu-id="c5350-109">For details, see Microsoft Knowledge Base article 929395, "Unified Communications Certificate Partners for Exchange Server and for Communications Server," at [http://go.microsoft.com/fwlink/p/?linkId=202834](http://go.microsoft.com/fwlink/p/?linkid=202834).</span></span>

  - <span data-ttu-id="c5350-p103">Si el certificado se usará en un grupo de servidores perimetrales, debe crearse como exportable, con el mismo certificado usado en cada servidor perimetral en el grupo de servidores perimetrales. El requisito de clave privada exportable se debe al servicio de autenticación A/V, que debe usar la misma clave privada a través de todos los servidores perimetrales en el grupo.</span><span class="sxs-lookup"><span data-stu-id="c5350-p103">If the certificate will be used on an Edge pool, it must be created as exportable, with the same certificate used on each Edge Server in the Edge pool. The exportable private key requirement is for the purposes of the A/V Authentication service, which must use the same private key across all Edge Servers in the pool.</span></span>

  - <span data-ttu-id="c5350-112">Si desea maximizar el tiempo de actividad de los servicios de audio y vídeo, revise los requisitos de certificado para implementar un certificado de servicio perimetral A/V desacoplado (es decir, un certificado de servicio perimetral A/V independiente de los otros propósitos de certificado perimetral externo).</span><span class="sxs-lookup"><span data-stu-id="c5350-112">If you want to maximize the uptime for your Audio/Video services, review the certificate requirements for implementing a decoupled A/V Edge service certificate (that is, a separate A/V Edge service certificate from the other External Edge certificate purposes).</span></span> <span data-ttu-id="c5350-113">Para obtener más información, vea [cambios en Lync server 2013 que afectan a la planeación de los servidores perimetrales](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md), [Plan for Edge Server Certificates in Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md) y staging de los [certificados AV y OAuth en Lync Server 2013 usando-Roll en Set-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate).</span><span class="sxs-lookup"><span data-stu-id="c5350-113">For details, see [Changes in Lync Server 2013 that affect Edge Server planning](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md), [Plan for Edge Server certificates in Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md) and [Staging AV and OAuth certificates in Lync Server 2013 using -Roll in Set-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate).</span></span>

  - <span data-ttu-id="c5350-114">El nombre de sujeto del certificado es el nombre de dominio completo (FQDN) de la interfaz externa del servicio perimetral de acceso o el VIP del equilibrador de carga de hardware (por ejemplo, access.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="c5350-114">The subject name of the certificate is the Access Edge service external interface fully qualified domain name (FQDN) or hardware load balancer VIP (for example, access.contoso.com).</span></span> <span data-ttu-id="c5350-115">).</span><span class="sxs-lookup"><span data-stu-id="c5350-115">).</span></span> <span data-ttu-id="c5350-116">El nombre del sujeto no puede tener un carácter comodín, debe ser un nombre explícito.</span><span class="sxs-lookup"><span data-stu-id="c5350-116">The subject name can’t have a wildcard character, it must be an explicit name.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c5350-117">Para Lync Server 2013, ya no es un requisito, pero se sigue recomendando por compatibilidad con Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="c5350-117">For Lync Server 2013, this is no longer a requirement, but it is still recommended for compatibility with Office Communications Server.</span></span>

    
    </div>

  - <span data-ttu-id="c5350-118">La lista de nombres alternativos de sujeto contiene los FQDN de:</span><span class="sxs-lookup"><span data-stu-id="c5350-118">The subject alternative name list contains the FQDNs of the following:</span></span>
    
      - <span data-ttu-id="c5350-119">La interfaz externa del servicio perimetral de acceso o VIP del equilibrador de carga de hardware (por ejemplo, sip.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="c5350-119">The Access Edge service external interface or hardware load balancer VIP (for example, sip.contoso.com).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="c5350-120">A pesar de que el nombre de sujeto del certificado equivale al FQDN del servidor perimetral de acceso, el nombre alternativo del sujeto también debe contener el FQDN del servidor perimetral de acceso porque Seguridad de la capa de transporte (TLS, Transport Layer Security) ignora el nombre de sujeto y usa las entradas del nombre alternativo del sujeto para la validación.</span><span class="sxs-lookup"><span data-stu-id="c5350-120">Even though the certificate subject name is equal to the access Edge FQDN, the subject alternative name must also contain the access Edge FQDN because Transport Layer Security (TLS) ignores the subject name and uses the subject alternative name entries for validation.</span></span>

        
        </div>
    
      - <span data-ttu-id="c5350-121">La interfaz perimetral externa de conferencia web o la VIP del equilibrador de carga de hardware (por ejemplo, webcon.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="c5350-121">The web conferencing Edge external interface or hardware load balancer VIP (for example, webcon.contoso.com).</span></span>
    
      - <span data-ttu-id="c5350-122">Si usa una federación o configuración automática de clientes, incluya también todos los FQDN de dominios SIP usados en la compañía (por ejemplo, sip.contoso.com, sip.fabrikam.com).</span><span class="sxs-lookup"><span data-stu-id="c5350-122">If you are using client auto-configuration or federation, also include any SIP domain FQDNs used within your company (for example, sip.contoso.com, sip.fabrikam.com).</span></span>
    
      - <span data-ttu-id="c5350-123">El servicio perimetral A/V no usa las entradas de nombre de sujeto o de nombres alternativos de sujeto.</span><span class="sxs-lookup"><span data-stu-id="c5350-123">The A/V Edge service does not use the subject name or the subject alternative names entries.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c5350-124">El orden de los FQDN en la lista de nombres alternativos del sujeto no importa.</span><span class="sxs-lookup"><span data-stu-id="c5350-124">The order of the FQDNs in the subject alternative names list does not matter.</span></span>

    
    </div>

<span data-ttu-id="c5350-p106">Si va a implementar varios servidores perimetrales de carga equilibrada en un sitio, el certificado de servicio de autenticación A/V instalado en cada servidor perimetral debe ser de la misma CA y debe usar la misma clave privada. Tenga en cuenta que la clave privada del certificado debe poder exportarse, independientemente de si se usa en un servidor perimetral o en varios. También debe poder exportarse si solicita el certificado desde cualquier equipo que no sea el servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="c5350-p106">If you are deploying multiple, load-balanced Edge Servers at a site, the A/V authentication service certificate that is installed on each Edge Server must be from the same CA and must use the same private key. Note that the certificate's private key must be exportable, regardless of whether it is used on one Edge Server or many Edge Servers. It must also be exportable if you request the certificate from any computer other than the Edge Server. Because the A/V authentication service does not use the subject name or subject alternative name, you can reuse the access Edge certificate as long as the subject name and subject alternative name requirements are met for the access Edge and the web conferencing Edge and the certificate’s private key is exportable.</span></span>

<span data-ttu-id="c5350-129">Estos son los requisitos para el certificado privado (o público) usado para la interfaz perimetral interna:</span><span class="sxs-lookup"><span data-stu-id="c5350-129">Requirements for the private (or public) certificate used for the Edge internal interface are as follows:</span></span>

  - <span data-ttu-id="c5350-130">El certificado puede ser emitido por una CA interna o por una CA pública de certificados aprobada.</span><span class="sxs-lookup"><span data-stu-id="c5350-130">The certificate can be issued by an internal CA or an approved public certificate CA.</span></span>

  - <span data-ttu-id="c5350-p107">El nombre de sujeto del certificado suele ser el FQDN de la interfaz perimetral interna o la VIP del equilibrador de carga de hardware (por ejemplo, lsedge.contoso.com). No obstante, puede usar un certificado de comodín en la interfaz perimetral interna.</span><span class="sxs-lookup"><span data-stu-id="c5350-p107">The subject name of the certificate is typically the Edge internal interface FQDN or hardware load balancer VIP (for example, lsedge.contoso.com). However, you can use a wildcard certificate on the Edge internal.</span></span>

  - <span data-ttu-id="c5350-133">No se necesita ningún nombre alternativo de sujeto.</span><span class="sxs-lookup"><span data-stu-id="c5350-133">No subject alternative name list is required.</span></span>

<span data-ttu-id="c5350-134">El servidor proxy inverso de los servicios de implementación solicitan que los usuarios externos puedan obtener acceso a:</span><span class="sxs-lookup"><span data-stu-id="c5350-134">The reverse proxy in your deployment services requests for:</span></span>

  - <span data-ttu-id="c5350-135">El contenido de las reuniones</span><span class="sxs-lookup"><span data-stu-id="c5350-135">External user access to meeting content for meetings</span></span>

  - <span data-ttu-id="c5350-136">Expandir y mostrar los miembros de los grupos de distribución</span><span class="sxs-lookup"><span data-stu-id="c5350-136">External user access to expand and display members of distribution groups</span></span>

  - <span data-ttu-id="c5350-137">Archivos descargables del servicio de libreta de direcciones</span><span class="sxs-lookup"><span data-stu-id="c5350-137">External user access to downloadable files from the Address Book Service</span></span>

  - <span data-ttu-id="c5350-138">Acceso de usuarios externos al cliente de Lync Web App</span><span class="sxs-lookup"><span data-stu-id="c5350-138">External user access to the Lync Web App client</span></span>

  - <span data-ttu-id="c5350-139">La página web de configuración de las conferencias de acceso telefónico</span><span class="sxs-lookup"><span data-stu-id="c5350-139">External user access to the Dial-in Conferencing Settings web page</span></span>

  - <span data-ttu-id="c5350-140">El servicio de información de ubicación</span><span class="sxs-lookup"><span data-stu-id="c5350-140">External user access to the Location Information Service</span></span>

  - <span data-ttu-id="c5350-141">Que los dispositivos externos obtengan acceso al servicio de actualización de dispositivos y obtengan las actualizaciones</span><span class="sxs-lookup"><span data-stu-id="c5350-141">External device access to the Device Update Service and obtain updates</span></span>

<span data-ttu-id="c5350-142">El servidor proxy inverso publique las direcciones URL de los componentes web del servidor interno.</span><span class="sxs-lookup"><span data-stu-id="c5350-142">The reverse proxy publishes the internal server Web Components URLs.</span></span> <span data-ttu-id="c5350-143">Las direcciones URL de los componentes Web se definen en el director, el servidor front-end o el grupo de servidores front-end como los **servicios web externos** en el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="c5350-143">The Web Components URLs are defined on the Director, Front End Server or Front End pool as the **External web services** in Topology Builder.</span></span>

<span data-ttu-id="c5350-144">Se pueden utilizar entradas de caracteres comodín en el campo de nombre alternativo de sujeto del certificado asignado al proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="c5350-144">Wildcard entries are supported in the subject alternative name field of the certificate assigned to the reverse proxy.</span></span> <span data-ttu-id="c5350-145">Para obtener más información sobre cómo configurar la solicitud de certificado para el proxy inverso, vea [solicitar y configurar un certificado para el proxy http inverso en Lync Server 2013](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="c5350-145">For details about how to configure the certificate request for the reverse proxy, see [Request and configure a certificate for your reverse HTTP proxy in Lync Server 2013](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="c5350-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="c5350-146">See Also</span></span>


[<span data-ttu-id="c5350-147">Compatibilidad con certificados comodín en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5350-147">Wildcard certificate support in Lync Server 2013</span></span>](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

