---
title: 'Lync Server 2013: Requisitos del servicio Detección automática'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Autodiscover service requirements
ms:assetid: 0ac5dbf7-9acd-4d25-b21a-932022b8b983
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690012(v=OCS.15)
ms:contentKeyID: 48183368
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ea9d9be05561d200696a5ad0256c0d5424cf9b8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842898"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="autodiscover-service-requirements-for-lync-server-2013"></a><span data-ttu-id="908a7-102">Requisitos del servicio Detección automática para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="908a7-102">Autodiscover service requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="908a7-103">_**Última modificación del tema:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="908a7-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="908a7-104">El servicio Detección automática de Microsoft Lync Server 2013 se ejecuta en el director y los servidores del grupo de servidores front-end, y cuando se publican en DNS, pueden ser usados por dispositivos móviles que ejecutan Lync Mobile para ubicar servicios de movilidad.</span><span class="sxs-lookup"><span data-stu-id="908a7-104">The Microsoft Lync Server 2013 Autodiscover Service runs on the Director and Front End pool servers, and when published in DNS, can be used by mobile devices running Lync Mobile to locate mobility services.</span></span> <span data-ttu-id="908a7-105">Antes de que los dispositivos móviles que ejecutan Lync Mobile puedan aprovechar el descubrimiento automático, debe modificar las listas de nombres alternativos del sujeto de certificado en cualquier Director y servidor front-end que ejecute el servicio Detección automática.</span><span class="sxs-lookup"><span data-stu-id="908a7-105">Before mobile devices running Lync Mobile can take advantage of automatic discovery, you need to modify certificate subject alternative name lists on any Director and Front End Server running the Autodiscover Service.</span></span> <span data-ttu-id="908a7-106">Además, puede que sea necesario modificar las listas de nombres alternativos del asunto en los certificados que se usan para las reglas de publicación de servicios web externos en los proxies inversos.</span><span class="sxs-lookup"><span data-stu-id="908a7-106">In addition, it may be necessary to modify the subject alternative name lists on certificates used for external web service publishing rules on reverse proxies.</span></span>

<span data-ttu-id="908a7-107">Para obtener información sobre las entradas de nombre alternativo de asunto necesarias para directores, servidores front-end y proxy inversos, consulte [requisitos técnicos para la movilidad en Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md) en planeamiento de movilidad.</span><span class="sxs-lookup"><span data-stu-id="908a7-107">For details about the subject alternative name entries that are required for Directors, Front End Servers, and reverse proxies, see [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md) in Planning for Mobility.</span></span>

<span data-ttu-id="908a7-108">La decisión sobre el uso de listas de nombres alternativos de asunto en proxies inversos se basa en si publica el servicio de detección automática en el puerto 80 o en el puerto 443:</span><span class="sxs-lookup"><span data-stu-id="908a7-108">The decision about using subject alternative name lists on reverse proxies is based on whether you publish the Autodiscover Service on port 80 or on port 443:</span></span>

  - <span data-ttu-id="908a7-109">**Publicado en el puerto 80**   no es necesario realizar cambios en los certificados si la consulta inicial para el servicio de detección automática se realiza a través del puerto 80.</span><span class="sxs-lookup"><span data-stu-id="908a7-109">**Published on port 80**   No certificate changes are required if the initial query to the Autodiscover Service occurs over port 80.</span></span> <span data-ttu-id="908a7-110">Esto se debe a que los dispositivos móviles que ejecutan Lync tendrán acceso al proxy inverso en el puerto 80 externamente y se redirigirá a un director o servidor front-end en el puerto 8080 de forma interna.</span><span class="sxs-lookup"><span data-stu-id="908a7-110">This is because mobile devices running Lync will access the reverse proxy on port 80 externally and then be redirected to a Director or Front End Server on port 8080 internally.</span></span> <span data-ttu-id="908a7-111">Para obtener más información, consulte la sección "proceso inicial de detección automática con el puerto 80" más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="908a7-111">For details, see the “Initial Autodiscover Process Using Port 80” section later in this topic.</span></span>

  - <span data-ttu-id="908a7-112">**Publicado en el puerto 443**   la lista de nombres alternativos de asunto en certificados usados por la regla de publicación de servicios web externos debe contener un \*lyncdiscover.\< sipdomain\> \* entrada para cada dominio SIP de su organización.</span><span class="sxs-lookup"><span data-stu-id="908a7-112">**Published on port 443**   The subject alternative name list on certificates used by the external web services publishing rule must contain a *lyncdiscover.\<sipdomain\>* entry for each SIP domain within your organization.</span></span>

<span data-ttu-id="908a7-113">La reemisión de certificados mediante una entidad emisora de certificados interna suele ser un proceso simple, pero para los certificados públicos que se usan en la regla de publicación de servicio Web, agregar varias entradas de nombre alternativo de asunto puede resultar costoso.</span><span class="sxs-lookup"><span data-stu-id="908a7-113">Reissuing certificates using an internal certificate authority is typically a simple process but for public certificates used on the web service publishing rule, adding multiple subject alternative name entries can become expensive.</span></span> <span data-ttu-id="908a7-114">Para evitar este problema, admitimos la conexión de detección automática inicial en el puerto 80, que luego se le redirige al puerto 8080 en el servidor de director o de front-end.</span><span class="sxs-lookup"><span data-stu-id="908a7-114">To work around this issue, we support the initial automatic discovery connection over port 80, which is then redirected to port 8080 on the Director or Front End Server.</span></span>

<span data-ttu-id="908a7-115">Por ejemplo, supongamos que un cliente móvil que ejecuta Lync Mobile está configurado para iniciar sesión en Lync Server 2013 con la característica de detección automática mediante HTTP para la solicitud inicial.</span><span class="sxs-lookup"><span data-stu-id="908a7-115">For example, assume that a mobile client running Lync Mobile is configured to sign in to Lync Server 2013 using the automatic discovery feature using HTTP for the initial request.</span></span>

<div>

## <a name="initial-autodiscover-process-for-mobile-devices-using-port-80"></a><span data-ttu-id="908a7-116">Proceso de detección automática inicial para dispositivos móviles que usan el puerto 80</span><span class="sxs-lookup"><span data-stu-id="908a7-116">Initial Autodiscover Process for Mobile Devices Using Port 80</span></span>

1.  <span data-ttu-id="908a7-117">Dispositivo móvil que ejecuta Lync Mobile busca lyncdiscover.contoso.com con DNS, donde existe un registro A.</span><span class="sxs-lookup"><span data-stu-id="908a7-117">Mobile device running Lync Mobile looks up lyncdiscover.contoso.com using DNS, where an A record exists.</span></span>

2.  <span data-ttu-id="908a7-118">DNS externo devuelve la dirección IP de los servicios web externos al cliente.</span><span class="sxs-lookup"><span data-stu-id="908a7-118">External DNS returns the IP address for the external web services to the client.</span></span>

3.  <span data-ttu-id="908a7-119">Un dispositivo móvil que ejecuta Lync Mobile http://lyncdiscover.contoso.com?sipuri=lyncUser1@contoso.com envía una solicitud al proxy inverso</span><span class="sxs-lookup"><span data-stu-id="908a7-119">Mobile device running Lync Mobile sends request http://lyncdiscover.contoso.com?sipuri=lyncUser1@contoso.com to the reverse proxy</span></span>

4.  <span data-ttu-id="908a7-120">La regla de publicación web enviará un puente de la solicitud desde el puerto 80 externamente al puerto 8080 de forma interna, que lo redirigirá a un director o a un servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="908a7-120">The web publishing rule will bridge the request from port 80 externally to port 8080 internally, which will then route it to either a Director or Front End Server.</span></span>
    
    <span data-ttu-id="908a7-121">Puesto que la solicitud es HTTP y no HTTPS, no es necesario realizar modificaciones en el certificado de la regla de publicación de servicio Web externo para admitir el servicio Detección automática.</span><span class="sxs-lookup"><span data-stu-id="908a7-121">Since the request is HTTP and not HTTPS, no modifications are needed to the certificate on the external web service publishing rule to support the Autodiscover Service.</span></span>

5.  <span data-ttu-id="908a7-122">El servicio Detección automática devuelve las direcciones URL del servicio Web externo (en formato HTTPS).</span><span class="sxs-lookup"><span data-stu-id="908a7-122">The Autodiscover Service returns the external web service URLs (in HTTPS format).</span></span>

6.  <span data-ttu-id="908a7-123">El dispositivo móvil que ejecuta Lync Mobile se puede volver a conectar al proxy inverso en el puerto 443 y se redirige a través de 4443 al servicio de movilidad que se ejecuta en el grupo de usuarios domésticos.</span><span class="sxs-lookup"><span data-stu-id="908a7-123">The mobile device running Lync Mobile can then reconnect to the reverse proxy on port 443 and is redirected over 4443 to the mobility service running on the user’s home pool.</span></span>
    
    <span data-ttu-id="908a7-124">Dado que la consulta HTTPS es a la dirección URL de los servicios web externos frente a la dirección URL del servicio de detección automática, se realiza correctamente porque el certificado ya contiene entradas de nombre alternativo del sujeto para los nombres de dominio completos (FQDN) de los servicios web externos.</span><span class="sxs-lookup"><span data-stu-id="908a7-124">Since the HTTPS query is to the external web services URL vs. the Autodiscover Service URL, it succeeds because the certificate will already contain subject alternative name entries for the external web services fully qualified domain names (FQDNs).</span></span>
    
    <span data-ttu-id="908a7-125">En este escenario, no es necesario realizar cambios en los certificados para admitir la movilidad.</span><span class="sxs-lookup"><span data-stu-id="908a7-125">In this scenario, there are no certificate changes required to support mobility.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="908a7-126">Si el servidor Web de destino tiene un certificado que no tiene un valor coincidente para lyncdiscover.contoso.com como un valor de lista de nombres alternativos de asunto:</span><span class="sxs-lookup"><span data-stu-id="908a7-126">If the target web server has a certificate that does not have a matching value for lyncdiscover.contoso.com as a subject alternative name list value:</span></span><BR><span data-ttu-id="908a7-127">a.&nbsp;&nbsp;&nbsp;el servidor web responde con un "servidor Hola" y no tiene certificado.</span><span class="sxs-lookup"><span data-stu-id="908a7-127">a.&nbsp;&nbsp;&nbsp;Web server responds with a “Server Hello” and no certificate.</span></span><BR><span data-ttu-id="908a7-128">b.&nbsp;&nbsp;&nbsp;dispositivo móvil que ejecuta Lync Mobile de inmediato finaliza la sesión.</span><span class="sxs-lookup"><span data-stu-id="908a7-128">b.&nbsp;&nbsp;&nbsp;Mobile device running Lync Mobile immediately terminates the session.</span></span><BR><span data-ttu-id="908a7-129">Si el servidor Web de destino tiene un certificado que incluye lyncdiscover.contoso.com como un valor de lista de nombres alternativos de asunto:</span><span class="sxs-lookup"><span data-stu-id="908a7-129">If the target web server has a certificate that includes lyncdiscover.contoso.com as a subject alternative name list value:</span></span><BR><span data-ttu-id="908a7-130">a.&nbsp;&nbsp;&nbsp;el servidor web responde con un certificado "servidor Hola".</span><span class="sxs-lookup"><span data-stu-id="908a7-130">a.&nbsp;&nbsp;&nbsp;Web server responds with a “Server hello” and a certificate.</span></span><BR><span data-ttu-id="908a7-131">b.&nbsp;&nbsp;&nbsp;dispositivo móvil que ejecuta Lync Mobile valida el certificado y completa el protocolo de enlace.</span><span class="sxs-lookup"><span data-stu-id="908a7-131">b.&nbsp;&nbsp;&nbsp;Mobile device running Lync Mobile validates the certificate and completes the handshake.</span></span>

    
    </div>

<span data-ttu-id="908a7-132">Para admitir una conexión inicial con el servicio de detección automática con el puerto 80 en el servidor proxy inverso, puede crear una regla de publicación http similar a este ejemplo para una regla de publicación Web de proxy invertida de Forefront Threat Management Gateway 2010:</span><span class="sxs-lookup"><span data-stu-id="908a7-132">To support an initial connection to the Autodiscover Service using port 80 on your reverse proxy server, you can create an http publishing rule similar to this example for a Forefront Threat Management Gateway 2010 reverse proxy web publishing rule:</span></span>

1.  <span data-ttu-id="908a7-133">Cree una nueva regla de publicación de Web (por ejemplo, **detección automática de Lync Server (http)**).</span><span class="sxs-lookup"><span data-stu-id="908a7-133">Create a new web publishing rule (for example, **Lync Server Autodiscover (HTTP)**).</span></span>

2.  <span data-ttu-id="908a7-134">En **nombre público**, escriba lyncdiscover.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="908a7-134">In **Public Name**, enter lyncdiscover.contoso.com.</span></span>

3.  <span data-ttu-id="908a7-135">En la pestaña **puente** , seleccione solo la opción para enlazar solicitudes desde el puerto 80 al puerto 8080.</span><span class="sxs-lookup"><span data-stu-id="908a7-135">On the **Bridging** tab, select only the option to bridge requests from Port 80 to Port 8080.</span></span>

4.  <span data-ttu-id="908a7-136">En la pestaña **autenticación** , seleccione **sin autenticación**y el **cliente no puede autenticar directamente**.</span><span class="sxs-lookup"><span data-stu-id="908a7-136">On the **Authentication** tab, select **No authentication**, and **Client cannot authenticate directly**.</span></span>

5.  <span data-ttu-id="908a7-137">Confirme los cambios y mueva la regla a la parte superior de la lista de reglas de Lync (en primer lugar en el orden de procesamiento).</span><span class="sxs-lookup"><span data-stu-id="908a7-137">Commit changes, and move the rule to the top of the list of Lync rules (first in processing order).</span></span>

</div>

<div>

## <a name="mobility-for-the-split-domain-deployment"></a><span data-ttu-id="908a7-138">Movilidad para la implementación de dominios divididos</span><span class="sxs-lookup"><span data-stu-id="908a7-138">Mobility for the Split Domain Deployment</span></span>

<span data-ttu-id="908a7-139">Un espacio de direcciones SIP compartido, también conocido como un *dominio dividido*, o una *implementación híbrida* es una configuración en la que los usuarios se implementan en una implementación local y en un entorno en línea.</span><span class="sxs-lookup"><span data-stu-id="908a7-139">A shared SIP address space, also known as a *split-domain*, or a *hybrid deployment* is a configuration where users are deployed across an on-premise deployment and an online environment.</span></span> <span data-ttu-id="908a7-140">El resultado deseado es tener un usuario, independientemente de dónde se encuentre ubicado su servidor principal (local o en línea), iniciar sesión en la implementación y ser redirigido a la ubicación del servidor local.</span><span class="sxs-lookup"><span data-stu-id="908a7-140">The desired outcome is to have a user, regardless of where their home server is located (on-premise or online), to log into the deployment and be redirected to their home server location.</span></span> <span data-ttu-id="908a7-141">Para ello, se usa la característica de detección automática de Microsoft Lync Server 2013 para redirigir el usuario en línea a la topología en línea.</span><span class="sxs-lookup"><span data-stu-id="908a7-141">To accomplish this, the Autodiscover feature of Microsoft Lync Server 2013 is used to redirect the online user to the online topology.</span></span> <span data-ttu-id="908a7-142">Esto se realiza mediante la configuración del localizador de recursos uniforme (URL) de detección automática mediante el shell de administración de Lync Server y los cmdlets **Get-CsHostingProvider** y **set-CsHostingProvider**.</span><span class="sxs-lookup"><span data-stu-id="908a7-142">This is done by configuring the Autodiscover uniform resource locator (URL) by using the Lync Server Management Shell and the cmdlets **Get-CsHostingProvider** and **Set-CsHostingProvider**.</span></span>

<span data-ttu-id="908a7-143">Tendrá que recopilar y registrar los siguientes atributos implementados:</span><span class="sxs-lookup"><span data-stu-id="908a7-143">You will need to collect and record the following deployed attributes:</span></span>

  - <span data-ttu-id="908a7-144">Desde el shell de administración de Lync Server, escriba</span><span class="sxs-lookup"><span data-stu-id="908a7-144">From the Lync Server Management Shell, type</span></span>
    
        Get-CsHostingProvider

  - <span data-ttu-id="908a7-145">En los resultados, busque el proveedor en línea con el atributo **ProxyFQDN**.</span><span class="sxs-lookup"><span data-stu-id="908a7-145">In the results, find the online provider with the attribute **ProxyFQDN**.</span></span> <span data-ttu-id="908a7-146">Por ejemplo, sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="908a7-146">For example, sipfed.online.lync.com</span></span>

  - <span data-ttu-id="908a7-147">Registrar el valor de la ProxyFQDN</span><span class="sxs-lookup"><span data-stu-id="908a7-147">Record the value of the ProxyFQDN</span></span>

  - <span data-ttu-id="908a7-148">Habilitar la Federación en el panel de control de Lync Server local, lo que permite la Federación con el proveedor en línea</span><span class="sxs-lookup"><span data-stu-id="908a7-148">Enable federation in the on-premise Lync Server Control Panel, allowing federation with the online provider</span></span>

  - <span data-ttu-id="908a7-149">Habilitar la Federación para el proveedor en línea.</span><span class="sxs-lookup"><span data-stu-id="908a7-149">Enable federation for the online provider.</span></span> <span data-ttu-id="908a7-150">De forma predeterminada, todos los usuarios conectados están habilitados para la Federación de dominios y pueden comunicarse con todos los dominios.</span><span class="sxs-lookup"><span data-stu-id="908a7-150">By default, all online users are enabled for domain federation and can communicate with all domains</span></span>

  - <span data-ttu-id="908a7-151">Si va a definir dominios bloqueados y permitidos, determine los dominios que va a permitir o bloquear de forma explícita</span><span class="sxs-lookup"><span data-stu-id="908a7-151">If you will define blocked and allowed domains, determine the domains that you will explicitly allow or explicitly block</span></span>

  - <span data-ttu-id="908a7-152">Para la Federación en línea, debe planear las excepciones del firewall, los certificados y los registros de host DNS (A o AAAA, si usa IPv6).</span><span class="sxs-lookup"><span data-stu-id="908a7-152">For online federation, you must plan for firewall exceptions, certificates and DNS host (A or AAAA, if using IPv6) records.</span></span> <span data-ttu-id="908a7-153">Además, debe configurar directivas de Federación.</span><span class="sxs-lookup"><span data-stu-id="908a7-153">Additionally, you must configure federation policies.</span></span> <span data-ttu-id="908a7-154">Para obtener más información, consulte [planificación de Lync server 2013 y Federación de Office Communications Server](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md)</span><span class="sxs-lookup"><span data-stu-id="908a7-154">For details, see [Planning for Lync Server 2013 and Office Communications Server federation](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

