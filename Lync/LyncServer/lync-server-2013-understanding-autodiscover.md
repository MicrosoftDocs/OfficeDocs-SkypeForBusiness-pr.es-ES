---
title: 'Lync Server 2013: Descripción de la detección automática'
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
ms.openlocfilehash: d9d885654f9222ce3d3e9fb7b03e9b388f0ca0a8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744830"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="understanding-autodiscover-in-lync-server-2013"></a><span data-ttu-id="d5b14-102">Descripción de la detección automática en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5b14-102">Understanding Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d5b14-103">_**Última modificación del tema:** 2013-06-03_</span><span class="sxs-lookup"><span data-stu-id="d5b14-103">_**Topic Last Modified:** 2013-06-03_</span></span>

<span data-ttu-id="d5b14-104">El servicio de detección automática de Lync Server 2013 es una característica introducida originalmente en Microsoft Lync Server 2010 como parte de la actualización acumulativa para Lync Server 2010: diciembre de 2011.</span><span class="sxs-lookup"><span data-stu-id="d5b14-104">The Lync Server 2013 Autodiscover Service is a feature that was originally introduced in Microsoft Lync Server 2010 as part of the Cumulative Update for Lync Server 2010: November 2011.</span></span> <span data-ttu-id="d5b14-105">Además de las correcciones, esta actualización acumulativa ofrece compatibilidad con clientes de Lync Mobile y Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="d5b14-105">In addition to fixes, this cumulative update delivered support for Lync Mobile and Lync 2013 clients.</span></span>

<span data-ttu-id="d5b14-106">En Lync Server 2013, el servicio Detección automática es una parte integral del funcionamiento de clientes móviles externos e internos, y la detección automática también se extiende a los nuevos clientes, como la aplicación de la tienda Windows de Lync recientemente presentada para Windows 8.</span><span class="sxs-lookup"><span data-stu-id="d5b14-106">In Lync Server 2013, the Autodiscover Service is an integral part of the operation of external and internal mobile clients, and Autodiscover is also extended to new clients, such as the recently introduced Lync Windows Store app for Windows 8.</span></span> <span data-ttu-id="d5b14-107">La detección automática también la usan los clientes de escritorio de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="d5b14-107">Autodiscover is also used by the Lync 2013 desktop clients.</span></span> <span data-ttu-id="d5b14-108">La detección automática se reconoce en Lync Server mediante el lyncdiscover de registros del sistema de nombres de dominio (DNS) requerido \*\*.\< dominio\> \*\* y **lyncdiscoverinternal.\< dominio\>**.</span><span class="sxs-lookup"><span data-stu-id="d5b14-108">Autodiscover is recognized in Lync Server by the required domain name system (DNS) records **lyncdiscover.\<domain\>** and **lyncdiscoverinternal.\<domain\>**.</span></span> <span data-ttu-id="d5b14-109">Además, las versiones más recientes de los clientes de escritorio de Lync 2010 y Lync 2013 prefieren la detección automática en los registros SRV del sistema de nombres de dominio (DNS), usando los registros SRV de DNS solo si lyncdiscover. \<dominio\> o lyncdiscoverinternal. \<el\> dominio no responde o no se resuelve.</span><span class="sxs-lookup"><span data-stu-id="d5b14-109">Additionally, newer versions of the Lync 2010 and Lync 2013 desktop client prefer Autodiscover over the domain name system (DNS) SRV records, using DNS SRV records only if lyncdiscover.\<domain\> or lyncdiscoverinternal.\<domain\> does not respond or does not resolve.</span></span> <span data-ttu-id="d5b14-110">La aplicación de la tienda Windows de Lync para Windows 8 y Lync Mobile usa exclusivamente la detección automática y no hará referencia a los registros SRV de DNS tradicionales.</span><span class="sxs-lookup"><span data-stu-id="d5b14-110">The Lync Windows Store app for Windows 8 and Lync Mobile uses Autodiscover exclusively and will not refer to the traditional DNS SRV records.</span></span>

<span data-ttu-id="d5b14-111">En Lync Server 2013, la detección automática se ha expandido para comunicar al cliente qué elementos, características y métodos de comunicación están disponibles para el cliente.</span><span class="sxs-lookup"><span data-stu-id="d5b14-111">In Lync Server 2013, Autodiscover is expanded to communicate to the client which elements, features, and communication methods are available to the client.</span></span> <span data-ttu-id="d5b14-112">La información se comunica mediante una solicitud que se envía desde el cliente, y los servicios Web de Lync Server responden con una respuesta claramente definida que denomina lo que está disponible para el cliente y cómo ponerse en contacto con esas características en el formato de la detección automática. Documento de respuesta.</span><span class="sxs-lookup"><span data-stu-id="d5b14-112">The information is communicated through a request that is sent from the client, and the Lync Server web services responds with a clearly defined response that names what is available to the client, and how to contact those features in the format of the Autodiscover Response document.</span></span>

<span data-ttu-id="d5b14-113">La mejor manera de comprender el documento de respuesta de detección automática, incluido el modo en que los servicios web comunican las características a los clientes a través de este documento, es dissect y definir cada línea en una respuesta típica del documento de respuesta de detección automática del servicio Web de Lync.</span><span class="sxs-lookup"><span data-stu-id="d5b14-113">The best way to understand the Autodiscover response document, including how the web services communicate features to clients through this document, is to dissect and define each line in a typical response from the Lync web service Autodiscover response document.</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="d5b14-114">En los detalles siguientes, el usuario ya se ha autenticado en el servidor principal respondiendo a una solicitud de autenticación.</span><span class="sxs-lookup"><span data-stu-id="d5b14-114">In the details that follow, the user has already authenticated to the home server by responding to an authentication request.</span></span>



</div>

<div class="">


> [!NOTE]  
> <span data-ttu-id="d5b14-115">El servicio Web de detección automática de Lync se define en los <STRONG>protocolos de Microsoft Office</STRONG> , en la sección <STRONG>Especificaciones abiertas</STRONG> de la biblioteca de <STRONG>Microsoft Developer Network</STRONG> (MSDN).</span><span class="sxs-lookup"><span data-stu-id="d5b14-115">The Lync Autodiscover Web Service is defined in the <STRONG>Microsoft Office Protocols</STRONG> in the <STRONG>Open Specifications</STRONG> section of the <STRONG>Microsoft Developer Network</STRONG> (MSDN) library.</span></span> <span data-ttu-id="d5b14-116">Para obtener más información, consulte el documento de especificación completa, "Protocolo de servicio Web de Lync Autodiscover" en: <A href="http://go.microsoft.com/fwlink/?linkid=273839">http://go.microsoft.com/fwlink/?LinkId=273839</A>.</span><span class="sxs-lookup"><span data-stu-id="d5b14-116">For details, see the full specification document, "Lync Autodiscover Web Service Protocol," at: <A href="http://go.microsoft.com/fwlink/?linkid=273839">http://go.microsoft.com/fwlink/?LinkId=273839</A>.</span></span> <span data-ttu-id="d5b14-117">Para obtener más información sobre la autenticación, consulte "Protocolo de servicio Web <A href="http://go.microsoft.com/fwlink/?linkid=279015">http://go.microsoft.com/fwlink/?LinkId=279015</A>de autenticación de OC" en.</span><span class="sxs-lookup"><span data-stu-id="d5b14-117">For details about authentication, see "OC Authentication Web Service Protocol" at <A href="http://go.microsoft.com/fwlink/?linkid=279015">http://go.microsoft.com/fwlink/?LinkId=279015</A>.</span></span>



</div>

<div>

## <a name="the-lync-server-web-service-autodiscover-response"></a><span data-ttu-id="d5b14-118">Respuesta de detección automática del servicio Web de Lync Server</span><span class="sxs-lookup"><span data-stu-id="d5b14-118">The Lync Server Web Service Autodiscover Response</span></span>

<span data-ttu-id="d5b14-119">La respuesta devuelta cuando se envía la solicitud de detección automática es la misma para un cliente interno o externo.</span><span class="sxs-lookup"><span data-stu-id="d5b14-119">The response returned when the Autodiscover request is sent is the same for an internal or an external client.</span></span> <span data-ttu-id="d5b14-120">Algunos parámetros que tienen en cuenta la ubicación pueden cambiar.</span><span class="sxs-lookup"><span data-stu-id="d5b14-120">Some parameters that are location–aware may change.</span></span> <span data-ttu-id="d5b14-121">Si se recibe una solicitud de cliente pero la agrupación real es distinta de la que se ha contactado, el grupo de inicio del usuario se establecerá para ese usuario.</span><span class="sxs-lookup"><span data-stu-id="d5b14-121">If a client request is received, but the actual pool is other than the one that has been contacted, the user’s home pool will be set for that user.</span></span> <span data-ttu-id="d5b14-122">Un colega cuya cuenta de usuario se encuentra en un grupo diferente, pero que inicia sesión desde la misma oficina, obtendría una respuesta algo diferente.</span><span class="sxs-lookup"><span data-stu-id="d5b14-122">A colleague whose user account is on a different pool, but logging in from the same office, would get a slightly different response.</span></span> <span data-ttu-id="d5b14-123">La respuesta indica el servidor frontal o el grupo de servidores front-end correcto para ese usuario.</span><span class="sxs-lookup"><span data-stu-id="d5b14-123">The response indicates the correct Front End Server or Front End pool for that user.</span></span>

<span data-ttu-id="d5b14-124">Un ejemplo de un documento de respuesta de detección automática:</span><span class="sxs-lookup"><span data-stu-id="d5b14-124">An example of an Autodiscover Response document:</span></span>

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

## <a name="autodiscover-response-document-details"></a><span data-ttu-id="d5b14-125">Detalles del documento de respuesta de detección automática</span><span class="sxs-lookup"><span data-stu-id="d5b14-125">Autodiscover Response Document Details</span></span>

<span data-ttu-id="d5b14-126">El documento de respuesta de detección automática puede tener uno de los dos formatos siguientes:</span><span class="sxs-lookup"><span data-stu-id="d5b14-126">The Autodiscover Response document can be in one of two formats.</span></span> <span data-ttu-id="d5b14-127">El formato predeterminado es una notación de objetos de JavaScript (JSON).</span><span class="sxs-lookup"><span data-stu-id="d5b14-127">The default format is a JavaScript Object Notation (JSON).</span></span> <span data-ttu-id="d5b14-128">El otro formato es un documento de lenguaje de marcado extensible (XML).</span><span class="sxs-lookup"><span data-stu-id="d5b14-128">The other format is extensible markup language (XML) document.</span></span> <span data-ttu-id="d5b14-129">En este ejemplo se usa el código XML.</span><span class="sxs-lookup"><span data-stu-id="d5b14-129">The XML is used for this example.</span></span> <span data-ttu-id="d5b14-130">La solicitud y la respuesta son predecibles porque el documento tiene un esquema definido que determina el formato.</span><span class="sxs-lookup"><span data-stu-id="d5b14-130">The request and response are predictable because the document has a defined schema that determines the format.</span></span> <span data-ttu-id="d5b14-131">La línea del documento que describe el esquema utilizado es la primera línea de la solicitud o respuesta:</span><span class="sxs-lookup"><span data-stu-id="d5b14-131">The line in the document that describes the schema used is the first line in the request or response:</span></span>

    <AutodiscoverResponse xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" AccessLocation="External">

<span data-ttu-id="d5b14-132">La definición de **AccessLocation = "external"** indica que la solicitud se realizó desde un usuario externo.</span><span class="sxs-lookup"><span data-stu-id="d5b14-132">The definition of **AccessLocation=”External”** indicates that the request was made from an external user.</span></span>

    <SipServerInternalAccess fqdn="pool01.contoso.com" port="5061"/>

&nbsp;

    <SipServerExternalAccess fqdn="sip.contoso.com" port="5061"/>

<span data-ttu-id="d5b14-133">Actualmente, SipServerInternalAccess y SipServerExternalAccess no se usan.</span><span class="sxs-lookup"><span data-stu-id="d5b14-133">SipServerInternalAccess and SipServerExternalAccess are currently not used.</span></span> <span data-ttu-id="d5b14-134">Estas entradas se reservan para usarlas en el futuro.</span><span class="sxs-lookup"><span data-stu-id="d5b14-134">These entries are reserved for future use.</span></span>

    <SipClientInternalAccess fqdn=" pool01.contoso.com" port="443"/>

&nbsp;

    <SipClientExternalAccess fqdn="sip.contoso.com " port="443"/>

<span data-ttu-id="d5b14-135">SipClientInternalAccess y SipClientExternalAccess describen el nombre de dominio completo y el puerto que usará un cliente interno o externo para acceder al servidor SIP definido.</span><span class="sxs-lookup"><span data-stu-id="d5b14-135">SipClientInternalAccess and SipClientExternalAccess describe the fully qualified domain name and port that an internal or external client will use to access the defined SIP Server.</span></span> <span data-ttu-id="d5b14-136">El cliente de escritorio de Lync y la aplicación de la tienda Windows de Lync usan estas entradas, en función de su ubicación (interna o externa) para buscar el director o el servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="d5b14-136">The Lync desktop client and the Lync Windows Store app use these entries, based on their location (internal or external) to find the Director or Front End Server.</span></span>

    <Link token="Internal/Autodiscover" href="https://webinternal.contoso.net/Autodiscover/AutodiscoverService.svc/root"/>

&nbsp;

    <Link token ="External/Autodiscover" href="https://webexternal.contoso.com/Autodiscover/AutodiscoverService.svc/root"/>

<span data-ttu-id="d5b14-137">Las `Autodiscover` referencias contienen los puntos de entrada de servicio del servicio Detección automática.</span><span class="sxs-lookup"><span data-stu-id="d5b14-137">The `Autodiscover` references contain the service entry points for the Autodiscover service.</span></span> <span data-ttu-id="d5b14-138">El atributo token contiene el nombre del servicio y el href es una dirección URL que define el cliente en el que se puede encontrar el servicio.</span><span class="sxs-lookup"><span data-stu-id="d5b14-138">The token attribute contains the name of the service, and the href is a URL that defines for the client where the service can be found.</span></span> <span data-ttu-id="d5b14-139">Los clientes de una red externa usan `External/Autodiscover`el.</span><span class="sxs-lookup"><span data-stu-id="d5b14-139">Clients on an external network use the `External/Autodiscover`.</span></span> <span data-ttu-id="d5b14-140">El servicio de detección automática se instala como parte del proceso de implementación.</span><span class="sxs-lookup"><span data-stu-id="d5b14-140">The Autodiscover service is installed as part of the deployment process.</span></span> <span data-ttu-id="d5b14-141">`Internal/Autodiscover`no se utiliza actualmente y se reserva para su uso futuro.</span><span class="sxs-lookup"><span data-stu-id="d5b14-141">`Internal/Autodiscover` is not currently used, and is reserved for future use.</span></span>

    <Link token="Internal/AuthBroker" href="https://webinternal.contoso.net/Reach/sip.svc"/>

&nbsp;

    <Link token="External/AuthBroker" href="https://webexternal.contoso.com/Reach/sip.svc"/>

<span data-ttu-id="d5b14-142">Las `AuthBroker` referencias contienen los puntos de entrada de servicio para el servicio agente de autenticación interno y externo, en este caso, SIP. SVC.</span><span class="sxs-lookup"><span data-stu-id="d5b14-142">The `AuthBroker` references contain the service entry points for the internal and the external authentication broker service, in this case, sip.svc.</span></span> <span data-ttu-id="d5b14-143">El atributo token contiene el nombre del servicio y el href es una dirección URL que define el cliente en el que se puede encontrar el servicio.</span><span class="sxs-lookup"><span data-stu-id="d5b14-143">The token attribute contains the name of the service, and the href is a URL that defines for the client where the service can be found.</span></span> <span data-ttu-id="d5b14-144">Clientes de la red interna que usan `Internal/AuthBroker`.</span><span class="sxs-lookup"><span data-stu-id="d5b14-144">Clients on the internal network with use `Internal/AuthBroker`.</span></span> <span data-ttu-id="d5b14-145">Los clientes de una red externa usan `External/AuthBroker`el.</span><span class="sxs-lookup"><span data-stu-id="d5b14-145">Clients on an external network use the `External/AuthBroker`.</span></span> <span data-ttu-id="d5b14-146">El servicio de AuthBroker se instala como parte del proceso de implementación de los servicios Web internos de la implementación de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d5b14-146">The AuthBroker service is installed as part of the deployment process of your internal Lync Server 2013 deployment web services.</span></span>

    <Link token="Internal/WebScheduler" href="https://webinternal.contoso.net/Scheduler"/>

&nbsp;

    <Link token="External/WebScheduler" href="https://webexternal.contoso.com/Scheduler"/>

<span data-ttu-id="d5b14-147">El `WebScheduler` token hace referencia a las direcciones URL para el acceso de cliente a la programación basada en web para conferencias de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d5b14-147">The `WebScheduler` token references the URLs for client access to the web-based scheduling for Lync Server conferences.</span></span> <span data-ttu-id="d5b14-148">En este momento, `External/WebScheduler` solo se usa el.</span><span class="sxs-lookup"><span data-stu-id="d5b14-148">Currently, only the `External/WebScheduler` is used.</span></span> <span data-ttu-id="d5b14-149">El programa web se instala como parte del proceso de implementación de los servicios Web internos de la implementación de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d5b14-149">The WebScheduler is installed as part of the deployment process of your internal Lync Server 2013 deployment web services.</span></span>

    <Link token="Internal/Mcx" href="https://webexternal.contoso.net/Mcx/McxService.svc"/>

&nbsp;

    <Link token="External/Mcx" href="https://webexternal.contoso.com/Mcx/McxService.svc"/>

<span data-ttu-id="d5b14-150">`Internal/Mcx`y `External/Mcx` son las ubicaciones de los servicios de movilidad que se introdujeron en la actualización acumulativa para Lync Server 2010:2011 de noviembre.</span><span class="sxs-lookup"><span data-stu-id="d5b14-150">`Internal/Mcx` and `External/Mcx` are the locations of the Mobility services, introduced in Cumulative Update for Lync Server 2010: November 2011.</span></span> <span data-ttu-id="d5b14-151">Estas referencias seguirán siendo usadas por Lync 2010 Mobile en todos los dispositivos compatibles.</span><span class="sxs-lookup"><span data-stu-id="d5b14-151">These references will continue to be used by Lync 2010 Mobile on all supported devices.</span></span> <span data-ttu-id="d5b14-152">El servicio de MCX se instala como parte del proceso de implementación de los servicios Web internos de la implementación de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d5b14-152">The Mcx service is installed as part of the deployment process of your internal Lync Server 2013 deployment web services.</span></span>

    <Link token="Internal/Ucwa" href="https://webinternal.contoso.net/ucwa/v1/applications"/>

&nbsp;

    <Link token="External/Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>

&nbsp;

    <Link token="Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>

<span data-ttu-id="d5b14-153">**Interno/ucwa**, **externo/ucwa** y **ucwa** proporcionan un medio para que los clientes tengan acceso a la interfaz de programación de aplicaciones Web de comunicaciones unificadas (API de ucwa o simplemente Ucwa).</span><span class="sxs-lookup"><span data-stu-id="d5b14-153">**Internal/Ucwa**, **External/Ucwa** and **Ucwa** provide a means for clients to access the Unified Communications Web Application Programming Interface (UCWA API, or simply UCWA).</span></span> <span data-ttu-id="d5b14-154">`Internal/Ucwa`y `External/Ucwa` los directorios virtuales son puntos de acceso reservados para futuras mejoras de características, y no se usan.</span><span class="sxs-lookup"><span data-stu-id="d5b14-154">`Internal/Ucwa` and `External/Ucwa` virtual directories are access points reserved for future feature enhancement, and are not used.</span></span> <span data-ttu-id="d5b14-155">El `Ucwa` directorio virtual se usa para Microsoft Lync Mobile (introducido con lync Server 2013) en todos los dispositivos compatibles.</span><span class="sxs-lookup"><span data-stu-id="d5b14-155">The `Ucwa` virtual directory is used for Microsoft Lync Mobile (introduced with Lync Server 2013) on all supported devices.</span></span> <span data-ttu-id="d5b14-156">El servicio UCWA se instala como parte del proceso de implementación de los servicios Web internos de la implementación de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d5b14-156">The UCWA service is installed as part of the deployment process of your internal Lync Server 2013 deployment web services.</span></span>

    <Link token="Internal/XFrame" href="https://webinternal.contoso.net/Autodiscover/XFrame/XFrame.html"/>

&nbsp;

    <Link token="External/XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>

&nbsp;

    <Link token="XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>

<span data-ttu-id="d5b14-157">`Internal/XFrame`, **Externo/XFrame** y **XFrame** proporcionan acceso a las aplicaciones de servidor basadas en UCWA.</span><span class="sxs-lookup"><span data-stu-id="d5b14-157">`Internal/XFrame`, **External/XFrame** and **XFrame** provide access for UCWA-based server applications.</span></span> <span data-ttu-id="d5b14-158">XFrame se instala como parte del proceso de implementación de los servicios Web internos de la implementación de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d5b14-158">XFrame is installed as part of the deployment process of your internal Lync Server 2013 deployment web services.</span></span>

    <Link token="Self" href="https://webexternal.contoso.net/Autodiscover/AutodiscoverService.svc/root/user"/>

<span data-ttu-id="d5b14-159">El `Self` token hace referencia a información específica del cliente (tipo de respuesta de usuario) que está realizando la solicitud.</span><span class="sxs-lookup"><span data-stu-id="d5b14-159">The `Self` token refers to information specific to the client (user response type) that is making the request.</span></span> <span data-ttu-id="d5b14-160">El cliente que hizo esta solicitud era externo, y esta referencia de la detección automática es a la parte de usuario del servicio de detección automática.</span><span class="sxs-lookup"><span data-stu-id="d5b14-160">The client that made this request was external, and this Autodiscover reference is to the user portion of the Autodiscover service.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d5b14-161">Vea también</span><span class="sxs-lookup"><span data-stu-id="d5b14-161">See Also</span></span>


[<span data-ttu-id="d5b14-162">Requisitos del sistema para componentes perimetrales para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5b14-162">System requirements for external user access components for Lync Server 2013</span></span>](lync-server-2013-system-requirements-for-external-user-access-components.md)  
[<span data-ttu-id="d5b14-163">Planificación de la detección automática en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5b14-163">Planning for Autodiscover in Lync Server 2013</span></span>](lync-server-2013-planning-for-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

