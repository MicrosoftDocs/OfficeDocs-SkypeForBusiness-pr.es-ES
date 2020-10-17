---
title: 'Lync Server 2013: Descripción de detección automática'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Understanding Autodiscover
ms:assetid: d70a15b7-750b-4e0f-9a7f-0254d6d486c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945654(v=OCS.15)
ms:contentKeyID: 51541522
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b63e29608dd8c3a0187b17c03e6ba9373b31f08f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527767"
---
# <a name="understanding-autodiscover-in-lync-server-2013"></a><span data-ttu-id="f1b98-102">Descripción de la detección automática en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1b98-102">Understanding Autodiscover in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f1b98-103">_**Última modificación del tema:** 2013-06-03_</span><span class="sxs-lookup"><span data-stu-id="f1b98-103">_**Topic Last Modified:** 2013-06-03_</span></span>

<span data-ttu-id="f1b98-104">El servicio Detección automática de Lync Server 2013 es una característica que se introdujo originalmente en Microsoft Lync Server 2010 como parte de la actualización acumulativa de Lync Server 2010: noviembre de 2011.</span><span class="sxs-lookup"><span data-stu-id="f1b98-104">The Lync Server 2013 Autodiscover Service is a feature that was originally introduced in Microsoft Lync Server 2010 as part of the Cumulative Update for Lync Server 2010: November 2011.</span></span> <span data-ttu-id="f1b98-105">Además de las correcciones, esta actualización acumulativa proporciona compatibilidad con clientes de Lync Mobile y Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="f1b98-105">In addition to fixes, this cumulative update delivered support for Lync Mobile and Lync 2013 clients.</span></span>

<span data-ttu-id="f1b98-106">En Lync Server 2013, el servicio de detección automática es una parte integral del funcionamiento de los clientes móviles internos y externos, y la detección automática también se extiende a los nuevos clientes, como la reciente introducción de la tienda Windows para Lync para Windows 8.</span><span class="sxs-lookup"><span data-stu-id="f1b98-106">In Lync Server 2013, the Autodiscover Service is an integral part of the operation of external and internal mobile clients, and Autodiscover is also extended to new clients, such as the recently introduced Lync Windows Store app for Windows 8.</span></span> <span data-ttu-id="f1b98-107">Detección automática también se usa en los clientes de escritorio de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="f1b98-107">Autodiscover is also used by the Lync 2013 desktop clients.</span></span> <span data-ttu-id="f1b98-108">La detección automática se reconoce en Lync Server mediante el lyncdiscover de registros del sistema de nombres de dominio (DNS) requerido \*\*. \<domain\> \*\*</span><span class="sxs-lookup"><span data-stu-id="f1b98-108">Autodiscover is recognized in Lync Server by the required domain name system (DNS) records **lyncdiscover.\<domain\>**</span></span> <span data-ttu-id="f1b98-109">y \*\*lyncdiscoverinternal. \<domain\> \*\*.</span><span class="sxs-lookup"><span data-stu-id="f1b98-109">and **lyncdiscoverinternal.\<domain\>**.</span></span> <span data-ttu-id="f1b98-110">Además, las versiones más recientes de los clientes de escritorio de Lync 2010 y Lync 2013 prefieren la detección automática en los registros SRV del sistema de nombres de dominio (DNS), usando los registros DNS SRV solo si lyncdiscover.\<domain\></span><span class="sxs-lookup"><span data-stu-id="f1b98-110">Additionally, newer versions of the Lync 2010 and Lync 2013 desktop client prefer Autodiscover over the domain name system (DNS) SRV records, using DNS SRV records only if lyncdiscover.\<domain\></span></span> <span data-ttu-id="f1b98-111">o lyncdiscoverinternal.\<domain\></span><span class="sxs-lookup"><span data-stu-id="f1b98-111">or lyncdiscoverinternal.\<domain\></span></span> <span data-ttu-id="f1b98-112">no responde o no se resuelve.</span><span class="sxs-lookup"><span data-stu-id="f1b98-112">does not respond or does not resolve.</span></span> <span data-ttu-id="f1b98-113">La aplicación Lync para la tienda Windows para Windows 8 y Lync Mobile usa exclusivamente detección automática y no hará referencia a los registros DNS SRV tradicionales.</span><span class="sxs-lookup"><span data-stu-id="f1b98-113">The Lync Windows Store app for Windows 8 and Lync Mobile uses Autodiscover exclusively and will not refer to the traditional DNS SRV records.</span></span>

<span data-ttu-id="f1b98-114">En Lync Server 2013, la detección automática se expande para comunicar al cliente qué elementos, características y métodos de comunicación están disponibles para el cliente.</span><span class="sxs-lookup"><span data-stu-id="f1b98-114">In Lync Server 2013, Autodiscover is expanded to communicate to the client which elements, features, and communication methods are available to the client.</span></span> <span data-ttu-id="f1b98-115">La información se comunica a través de una solicitud enviada desde el cliente y los servicios Web de Lync Server responden con una respuesta definida claramente que indica lo que está disponible para el cliente y cómo ponerse en contacto con dichas características en el formato del documento de respuesta de detección automática.</span><span class="sxs-lookup"><span data-stu-id="f1b98-115">The information is communicated through a request that is sent from the client, and the Lync Server web services responds with a clearly defined response that names what is available to the client, and how to contact those features in the format of the Autodiscover Response document.</span></span>

<span data-ttu-id="f1b98-116">La mejor manera de comprender el documento de respuesta de detección automática, incluido cómo los servicios web comunican las características a los clientes a través de este documento, es dissect y definen cada línea en una respuesta típica del documento de respuesta de detección automática del servicio Web de Lync.</span><span class="sxs-lookup"><span data-stu-id="f1b98-116">The best way to understand the Autodiscover response document, including how the web services communicate features to clients through this document, is to dissect and define each line in a typical response from the Lync web service Autodiscover response document.</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="f1b98-117">En los detalles que se indican a continuación, el usuario ya se ha autenticado en el servidor principal respondiendo a una solicitud de autenticación.</span><span class="sxs-lookup"><span data-stu-id="f1b98-117">In the details that follow, the user has already authenticated to the home server by responding to an authentication request.</span></span>



</div>

<div class="">


> [!NOTE]  
> <span data-ttu-id="f1b98-118">El servicio Web de detección automática de Lync se define en los <STRONG>protocolos de Microsoft Office</STRONG> en la sección de <STRONG>Especificaciones abiertas</STRONG> de la biblioteca de <STRONG>Microsoft Developer Network</STRONG> (MSDN).</span><span class="sxs-lookup"><span data-stu-id="f1b98-118">The Lync Autodiscover Web Service is defined in the <STRONG>Microsoft Office Protocols</STRONG> in the <STRONG>Open Specifications</STRONG> section of the <STRONG>Microsoft Developer Network</STRONG> (MSDN) library.</span></span> <span data-ttu-id="f1b98-119">Para obtener más información, consulte el documento de especificación completa, "Protocolo del servicio Web de detección automática de Lync" en: <A href="https://go.microsoft.com/fwlink/?linkid=273839">https://go.microsoft.com/fwlink/?LinkId=273839</A> .</span><span class="sxs-lookup"><span data-stu-id="f1b98-119">For details, see the full specification document, "Lync Autodiscover Web Service Protocol," at: <A href="https://go.microsoft.com/fwlink/?linkid=273839">https://go.microsoft.com/fwlink/?LinkId=273839</A>.</span></span> <span data-ttu-id="f1b98-120">Para obtener más información acerca de la autenticación, consulte "Protocolo de servicio Web de autenticación de OC" en <A href="https://go.microsoft.com/fwlink/?linkid=279015">https://go.microsoft.com/fwlink/?LinkId=279015</A> .</span><span class="sxs-lookup"><span data-stu-id="f1b98-120">For details about authentication, see "OC Authentication Web Service Protocol" at <A href="https://go.microsoft.com/fwlink/?linkid=279015">https://go.microsoft.com/fwlink/?LinkId=279015</A>.</span></span>



</div>

<div>

## <a name="the-lync-server-web-service-autodiscover-response"></a><span data-ttu-id="f1b98-121">Respuesta de detección automática del servicio Web de Lync Server</span><span class="sxs-lookup"><span data-stu-id="f1b98-121">The Lync Server Web Service Autodiscover Response</span></span>

<span data-ttu-id="f1b98-122">La respuesta devuelta cuando la solicitud de detección automática se envía es la misma para un cliente interno o externo.</span><span class="sxs-lookup"><span data-stu-id="f1b98-122">The response returned when the Autodiscover request is sent is the same for an internal or an external client.</span></span> <span data-ttu-id="f1b98-123">Algunos parámetros que tienen en cuenta la ubicación pueden cambiar.</span><span class="sxs-lookup"><span data-stu-id="f1b98-123">Some parameters that are location–aware may change.</span></span> <span data-ttu-id="f1b98-124">Si se recibe una solicitud de cliente, pero el grupo real es distinto del que se ha contactado, el grupo de servidores principal del usuario se establecerá para ese usuario.</span><span class="sxs-lookup"><span data-stu-id="f1b98-124">If a client request is received, but the actual pool is other than the one that has been contacted, the user’s home pool will be set for that user.</span></span> <span data-ttu-id="f1b98-125">Un compañero cuya cuenta de usuario se encuentra en un grupo diferente, pero que inicia sesión desde la misma oficina, obtendría una respuesta ligeramente distinta.</span><span class="sxs-lookup"><span data-stu-id="f1b98-125">A colleague whose user account is on a different pool, but logging in from the same office, would get a slightly different response.</span></span> <span data-ttu-id="f1b98-126">La respuesta indica el servidor front-end o el grupo de servidores front-end correctos para ese usuario.</span><span class="sxs-lookup"><span data-stu-id="f1b98-126">The response indicates the correct Front End Server or Front End pool for that user.</span></span>

<span data-ttu-id="f1b98-127">Un ejemplo de un documento de respuesta de detección automática:</span><span class="sxs-lookup"><span data-stu-id="f1b98-127">An example of an Autodiscover Response document:</span></span>

    <AutodiscoverResponse xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" AccessLocation="External">
       <User>
          <SipServerInternalAccess fqdn="pool01.contoso.com" port="5061"/>
          <SipClientInternalAccess fqdn=" pool01.contoso.com" port="443"/>
          <SipServerExternalAccess fqdn="sip.contoso.com" port="5061"/>
          <SipClientExternalAccess fqdn="sip.contoso.com " port="443"/>
          <Link token ="External/Autodiscover" href="https://webexternal.contoso.com/Autodiscover/AutodiscoverService.svc/root"/>
          <Link token="Internal/Autodiscover" href="https://webinternal.contoso.net/Autodiscover/AutodiscoverService.svc/root"/>
          <Link token="External/AuthBroker" href="https://webexternal.contoso.com/Reach/sip.svc"/>
          <Link token="Internal/AuthBroker" href="https://webinternal.contoso.net/Reach/sip.svc"/>
          <Link token="External/WebScheduler" href="https://webexternal.contoso.com/Scheduler"/>
          <Link token="Internal/WebScheduler" href="https://webinternal.contoso.net/Scheduler"/>
          <Link token="External/Mcx" href="https://webexternal.contoso.com/Mcx/McxService.svc"/>
          <Link token="Internal/Mcx" href="https://webexternal.contoso.net/Mcx/McxService.svc"/>
          <Link token="External/Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>
          <Link token="Internal/Ucwa" href="https://webinternal.contoso.net/ucwa/v1/applications"/>
          <Link token="Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>
          <Link token="External/XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>
          <Link token="Internal/XFrame" href="https://webinternal.contoso.net/Autodiscover/XFrame/XFrame.html"/>
          <Link token="XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>
          <Link token="Self" href="https://webexternal.contoso.net/Autodiscover/AutodiscoverService.svc/root/user"/>
       </User>
    </AutodiscoverResponse>

<div>

## <a name="autodiscover-response-document-details"></a><span data-ttu-id="f1b98-128">Detalles del documento de respuesta de detección automática</span><span class="sxs-lookup"><span data-stu-id="f1b98-128">Autodiscover Response Document Details</span></span>

<span data-ttu-id="f1b98-129">El documento de respuesta de detección automática puede tener uno de estos dos formatos.</span><span class="sxs-lookup"><span data-stu-id="f1b98-129">The Autodiscover Response document can be in one of two formats.</span></span> <span data-ttu-id="f1b98-130">El formato predeterminado es una notación de objetos JavaScript (JSON).</span><span class="sxs-lookup"><span data-stu-id="f1b98-130">The default format is a JavaScript Object Notation (JSON).</span></span> <span data-ttu-id="f1b98-131">El otro formato es documento de lenguaje de marcado extensible (XML).</span><span class="sxs-lookup"><span data-stu-id="f1b98-131">The other format is extensible markup language (XML) document.</span></span> <span data-ttu-id="f1b98-132">El código XML se usa para este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="f1b98-132">The XML is used for this example.</span></span> <span data-ttu-id="f1b98-133">La solicitud y la respuesta son predecibles porque el documento tiene un esquema definido que determina el formato.</span><span class="sxs-lookup"><span data-stu-id="f1b98-133">The request and response are predictable because the document has a defined schema that determines the format.</span></span> <span data-ttu-id="f1b98-134">La línea del documento que describe el esquema usado es la primera línea de la solicitud o respuesta:</span><span class="sxs-lookup"><span data-stu-id="f1b98-134">The line in the document that describes the schema used is the first line in the request or response:</span></span>

    <AutodiscoverResponse xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" AccessLocation="External">

<span data-ttu-id="f1b98-135">La definición de **AccessLocation = "external"** indica que la solicitud se ha realizado desde un usuario externo.</span><span class="sxs-lookup"><span data-stu-id="f1b98-135">The definition of **AccessLocation=”External”** indicates that the request was made from an external user.</span></span>

    <SipServerInternalAccess fqdn="pool01.contoso.com" port="5061"/>

&nbsp;

    <SipServerExternalAccess fqdn="sip.contoso.com" port="5061"/>

<span data-ttu-id="f1b98-136">Actualmente, SipServerInternalAccess y SipServerExternalAccess no se usan.</span><span class="sxs-lookup"><span data-stu-id="f1b98-136">SipServerInternalAccess and SipServerExternalAccess are currently not used.</span></span> <span data-ttu-id="f1b98-137">Estas entradas están reservadas para su uso en el futuro.</span><span class="sxs-lookup"><span data-stu-id="f1b98-137">These entries are reserved for future use.</span></span>

    <SipClientInternalAccess fqdn=" pool01.contoso.com" port="443"/>

&nbsp;

    <SipClientExternalAccess fqdn="sip.contoso.com " port="443"/>

<span data-ttu-id="f1b98-138">SipClientInternalAccess y SipClientExternalAccess describen el nombre de dominio completo y el puerto que un cliente interno o externo usará para tener acceso al servidor SIP definido.</span><span class="sxs-lookup"><span data-stu-id="f1b98-138">SipClientInternalAccess and SipClientExternalAccess describe the fully qualified domain name and port that an internal or external client will use to access the defined SIP Server.</span></span> <span data-ttu-id="f1b98-139">El cliente de escritorio de Lync y la aplicación Lync de la tienda Windows usan estas entradas, en función de su ubicación (interna o externa) para encontrar el director o el servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="f1b98-139">The Lync desktop client and the Lync Windows Store app use these entries, based on their location (internal or external) to find the Director or Front End Server.</span></span>

    <Link token="Internal/Autodiscover" href="https://webinternal.contoso.net/Autodiscover/AutodiscoverService.svc/root"/>

&nbsp;

    <Link token ="External/Autodiscover" href="https://webexternal.contoso.com/Autodiscover/AutodiscoverService.svc/root"/>

<span data-ttu-id="f1b98-140">Las `Autodiscover` referencias contienen los puntos de entrada de servicio para el servicio Detección automática.</span><span class="sxs-lookup"><span data-stu-id="f1b98-140">The `Autodiscover` references contain the service entry points for the Autodiscover service.</span></span> <span data-ttu-id="f1b98-141">El atributo token contiene el nombre del servicio y Href es una dirección URL que define el cliente en el que se puede encontrar el servicio.</span><span class="sxs-lookup"><span data-stu-id="f1b98-141">The token attribute contains the name of the service, and the href is a URL that defines for the client where the service can be found.</span></span> <span data-ttu-id="f1b98-142">Los clientes de una red externa usan el `External/Autodiscover` .</span><span class="sxs-lookup"><span data-stu-id="f1b98-142">Clients on an external network use the `External/Autodiscover`.</span></span> <span data-ttu-id="f1b98-143">El servicio de detección automática se instala como parte del proceso de implementación.</span><span class="sxs-lookup"><span data-stu-id="f1b98-143">The Autodiscover service is installed as part of the deployment process.</span></span> <span data-ttu-id="f1b98-144">`Internal/Autodiscover` no se usa actualmente y se reserva para su uso en el futuro.</span><span class="sxs-lookup"><span data-stu-id="f1b98-144">`Internal/Autodiscover` is not currently used, and is reserved for future use.</span></span>

    <Link token="Internal/AuthBroker" href="https://webinternal.contoso.net/Reach/sip.svc"/>

&nbsp;

    <Link token="External/AuthBroker" href="https://webexternal.contoso.com/Reach/sip.svc"/>

<span data-ttu-id="f1b98-145">Las `AuthBroker` referencias contienen los puntos de entrada de servicio para el servicio de agente de autenticación interno y externo, en este caso, SIP. SVC.</span><span class="sxs-lookup"><span data-stu-id="f1b98-145">The `AuthBroker` references contain the service entry points for the internal and the external authentication broker service, in this case, sip.svc.</span></span> <span data-ttu-id="f1b98-146">El atributo token contiene el nombre del servicio y Href es una dirección URL que define el cliente en el que se puede encontrar el servicio.</span><span class="sxs-lookup"><span data-stu-id="f1b98-146">The token attribute contains the name of the service, and the href is a URL that defines for the client where the service can be found.</span></span> <span data-ttu-id="f1b98-147">Clientes de la red interna que usan `Internal/AuthBroker` .</span><span class="sxs-lookup"><span data-stu-id="f1b98-147">Clients on the internal network with use `Internal/AuthBroker`.</span></span> <span data-ttu-id="f1b98-148">Los clientes de una red externa usan el `External/AuthBroker` .</span><span class="sxs-lookup"><span data-stu-id="f1b98-148">Clients on an external network use the `External/AuthBroker`.</span></span> <span data-ttu-id="f1b98-149">El servicio AuthBroker se instala como parte del proceso de implementación de los servicios Web internos de implementación de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f1b98-149">The AuthBroker service is installed as part of the deployment process of your internal Lync Server 2013 deployment web services.</span></span>

    <Link token="Internal/WebScheduler" href="https://webinternal.contoso.net/Scheduler"/>

&nbsp;

    <Link token="External/WebScheduler" href="https://webexternal.contoso.com/Scheduler"/>

<span data-ttu-id="f1b98-150">El `WebScheduler` token hace referencia a las direcciones URL para el acceso de cliente a la programación basada en web para conferencias de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f1b98-150">The `WebScheduler` token references the URLs for client access to the web-based scheduling for Lync Server conferences.</span></span> <span data-ttu-id="f1b98-151">Actualmente, solo `External/WebScheduler` se usa el.</span><span class="sxs-lookup"><span data-stu-id="f1b98-151">Currently, only the `External/WebScheduler` is used.</span></span> <span data-ttu-id="f1b98-152">Webprogramation se instala como parte del proceso de implementación de los servicios Web internos de implementación de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f1b98-152">The WebScheduler is installed as part of the deployment process of your internal Lync Server 2013 deployment web services.</span></span>

    <Link token="Internal/Mcx" href="https://webexternal.contoso.net/Mcx/McxService.svc"/>

&nbsp;

    <Link token="External/Mcx" href="https://webexternal.contoso.com/Mcx/McxService.svc"/>

<span data-ttu-id="f1b98-153">`Internal/Mcx` y `External/Mcx` son las ubicaciones de los servicios de movilidad que se incluyen en la actualización acumulativa para Lync Server 2010: noviembre de 2011.</span><span class="sxs-lookup"><span data-stu-id="f1b98-153">`Internal/Mcx` and `External/Mcx` are the locations of the Mobility services, introduced in Cumulative Update for Lync Server 2010: November 2011.</span></span> <span data-ttu-id="f1b98-154">Lync 2010 Mobile seguirá usando estas referencias en todos los dispositivos compatibles.</span><span class="sxs-lookup"><span data-stu-id="f1b98-154">These references will continue to be used by Lync 2010 Mobile on all supported devices.</span></span> <span data-ttu-id="f1b98-155">El servicio MCX se instala como parte del proceso de implementación de los servicios Web internos de implementación de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f1b98-155">The Mcx service is installed as part of the deployment process of your internal Lync Server 2013 deployment web services.</span></span>

    <Link token="Internal/Ucwa" href="https://webinternal.contoso.net/ucwa/v1/applications"/>

&nbsp;

    <Link token="External/Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>

&nbsp;

    <Link token="Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>

<span data-ttu-id="f1b98-156">**Interno/ucwa**, **external/ucwa** y **Ucwa** proporcionan un medio para que los clientes tengan acceso a la interfaz de programación de aplicaciones Web de comunicaciones unificadas (API de Ucwa o simplemente a Ucwa).</span><span class="sxs-lookup"><span data-stu-id="f1b98-156">**Internal/Ucwa**, **External/Ucwa** and **Ucwa** provide a means for clients to access the Unified Communications Web Application Programming Interface (UCWA API, or simply UCWA).</span></span> <span data-ttu-id="f1b98-157">`Internal/Ucwa` los `External/Ucwa` directorios virtuales son puntos de acceso reservados para futuras mejoras de características, y no se usan.</span><span class="sxs-lookup"><span data-stu-id="f1b98-157">`Internal/Ucwa` and `External/Ucwa` virtual directories are access points reserved for future feature enhancement, and are not used.</span></span> <span data-ttu-id="f1b98-158">El `Ucwa` directorio virtual se usa para Microsoft Lync Mobile (incluido en Lync Server 2013) en todos los dispositivos compatibles.</span><span class="sxs-lookup"><span data-stu-id="f1b98-158">The `Ucwa` virtual directory is used for Microsoft Lync Mobile (introduced with Lync Server 2013) on all supported devices.</span></span> <span data-ttu-id="f1b98-159">El servicio UCWA se instala como parte del proceso de implementación de los servicios Web internos de implementación de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f1b98-159">The UCWA service is installed as part of the deployment process of your internal Lync Server 2013 deployment web services.</span></span>

    <Link token="Internal/XFrame" href="https://webinternal.contoso.net/Autodiscover/XFrame/XFrame.html"/>

&nbsp;

    <Link token="External/XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>

&nbsp;

    <Link token="XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>

<span data-ttu-id="f1b98-160">`Internal/XFrame`, **External/XFrame** y **XFrame** proporcionan acceso a las aplicaciones de servidor basadas en UCWA.</span><span class="sxs-lookup"><span data-stu-id="f1b98-160">`Internal/XFrame`, **External/XFrame** and **XFrame** provide access for UCWA-based server applications.</span></span> <span data-ttu-id="f1b98-161">XFrame se instala como parte del proceso de implementación de los servicios Web internos de implementación de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f1b98-161">XFrame is installed as part of the deployment process of your internal Lync Server 2013 deployment web services.</span></span>

    <Link token="Self" href="https://webexternal.contoso.net/Autodiscover/AutodiscoverService.svc/root/user"/>

<span data-ttu-id="f1b98-162">El `Self` token hace referencia a la información específica del cliente (tipo de respuesta de usuario) que realiza la solicitud.</span><span class="sxs-lookup"><span data-stu-id="f1b98-162">The `Self` token refers to information specific to the client (user response type) that is making the request.</span></span> <span data-ttu-id="f1b98-163">El cliente que realizó esta solicitud era externo y esta referencia de detección automática es a la parte de usuario del servicio Detección automática.</span><span class="sxs-lookup"><span data-stu-id="f1b98-163">The client that made this request was external, and this Autodiscover reference is to the user portion of the Autodiscover service.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f1b98-164">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f1b98-164">See Also</span></span>


[<span data-ttu-id="f1b98-165">Requisitos del sistema para componentes de acceso de usuarios externos para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1b98-165">System requirements for external user access components for Lync Server 2013</span></span>](lync-server-2013-system-requirements-for-external-user-access-components.md)  
[<span data-ttu-id="f1b98-166">Planeación de la detección automática en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1b98-166">Planning for Autodiscover in Lync Server 2013</span></span>](lync-server-2013-planning-for-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

