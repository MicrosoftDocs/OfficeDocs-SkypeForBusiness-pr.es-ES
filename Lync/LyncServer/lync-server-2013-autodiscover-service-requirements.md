---
title: 'Lync Server 2013: requisitos del servicio Detección automática'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Autodiscover service requirements
ms:assetid: 0ac5dbf7-9acd-4d25-b21a-932022b8b983
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690012(v=OCS.15)
ms:contentKeyID: 48183368
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ec6c3ada06312f816a75f5539593336addc8d2b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196983"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="autodiscover-service-requirements-for-lync-server-2013"></a><span data-ttu-id="3c303-102">Requisitos del servicio Detección automática para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3c303-102">Autodiscover service requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3c303-103">_**Última modificación del tema:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="3c303-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="3c303-104">El servicio Detección automática de Microsoft Lync Server 2013 se ejecuta en los servidores de director y de grupo de servidores front-end y, cuando se publican en DNS, los dispositivos móviles que ejecutan Lync Mobile pueden usar para encontrar los servicios de movilidad.</span><span class="sxs-lookup"><span data-stu-id="3c303-104">The Microsoft Lync Server 2013 Autodiscover Service runs on the Director and Front End pool servers, and when published in DNS, can be used by mobile devices running Lync Mobile to locate mobility services.</span></span> <span data-ttu-id="3c303-105">Antes de que los dispositivos móviles que ejecutan Lync Mobile puedan aprovechar la detección automática, debe modificar las listas de nombres alternativos de sujeto de certificado en cualquier Director y servidor front-end que ejecute el servicio Detección automática.</span><span class="sxs-lookup"><span data-stu-id="3c303-105">Before mobile devices running Lync Mobile can take advantage of automatic discovery, you need to modify certificate subject alternative name lists on any Director and Front End Server running the Autodiscover Service.</span></span> <span data-ttu-id="3c303-106">Además, es posible que haya que modificar las listas de nombres alternativos de sujeto en certificados usados para las reglas de publicación de servicios web en proxies inversos.</span><span class="sxs-lookup"><span data-stu-id="3c303-106">In addition, it may be necessary to modify the subject alternative name lists on certificates used for external web service publishing rules on reverse proxies.</span></span>

<span data-ttu-id="3c303-107">Para obtener información detallada sobre las entradas de nombre alternativo de sujeto que son necesarias para los directores, los servidores front-end y los servidores proxy inversos, consulte [Technical Requirements for Mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md) en Planning for Mobility.</span><span class="sxs-lookup"><span data-stu-id="3c303-107">For details about the subject alternative name entries that are required for Directors, Front End Servers, and reverse proxies, see [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md) in Planning for Mobility.</span></span>

<span data-ttu-id="3c303-108">La decisión de usar listas de nombres alternativos de sujeto en proxies inversos se basa en si se publica el servicio Detección automática en el puerto 80 o en el puerto 443:</span><span class="sxs-lookup"><span data-stu-id="3c303-108">The decision about using subject alternative name lists on reverse proxies is based on whether you publish the Autodiscover Service on port 80 or on port 443:</span></span>

  - <span data-ttu-id="3c303-109">**Publicado en el puerto 80**   no es necesario realizar cambios en los certificados si la consulta inicial al servicio Detección automática se produce a través del puerto 80.</span><span class="sxs-lookup"><span data-stu-id="3c303-109">**Published on port 80**   No certificate changes are required if the initial query to the Autodiscover Service occurs over port 80.</span></span> <span data-ttu-id="3c303-110">Esto se debe a que los dispositivos móviles que ejecutan Lync tendrán acceso al proxy inverso en el puerto 80 externamente y, a continuación, se redirigirán a un director o a un servidor front-end en el puerto 8080 de forma interna.</span><span class="sxs-lookup"><span data-stu-id="3c303-110">This is because mobile devices running Lync will access the reverse proxy on port 80 externally and then be redirected to a Director or Front End Server on port 8080 internally.</span></span> <span data-ttu-id="3c303-111">Para obtener más información, vea la sección “Proceso de detección automática inicial usando el puerto 80” más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="3c303-111">For details, see the “Initial Autodiscover Process Using Port 80” section later in this topic.</span></span>

  - <span data-ttu-id="3c303-112">**Publicado en el puerto 443**   la lista de nombres alternativos de sujeto en los certificados usados por la regla de publicación de servicios web externos debe contener un *lyncdiscover.\< entrada\> sipdomain* para cada dominio SIP dentro de la organización.</span><span class="sxs-lookup"><span data-stu-id="3c303-112">**Published on port 443**   The subject alternative name list on certificates used by the external web services publishing rule must contain a *lyncdiscover.\<sipdomain\>* entry for each SIP domain within your organization.</span></span>

<span data-ttu-id="3c303-113">La reemisión de certificados usando una entidad de certificación interna suele ser un proceso sencillo, pero para certificados públicos usados en la regla de publicación de servicios web, puede resultar caro agregar varias entradas de nombres alternativos de sujeto.</span><span class="sxs-lookup"><span data-stu-id="3c303-113">Reissuing certificates using an internal certificate authority is typically a simple process but for public certificates used on the web service publishing rule, adding multiple subject alternative name entries can become expensive.</span></span> <span data-ttu-id="3c303-114">Para solucionar este problema, admitimos la conexión de detección automática inicial a través del puerto 80, que luego se redirige al puerto 8080 en el director o el servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="3c303-114">To work around this issue, we support the initial automatic discovery connection over port 80, which is then redirected to port 8080 on the Director or Front End Server.</span></span>

<span data-ttu-id="3c303-115">Por ejemplo, supongamos que un cliente móvil que ejecuta Lync Mobile está configurado para iniciar sesión en Lync Server 2013 mediante la característica de detección automática usando HTTP para la solicitud inicial.</span><span class="sxs-lookup"><span data-stu-id="3c303-115">For example, assume that a mobile client running Lync Mobile is configured to sign in to Lync Server 2013 using the automatic discovery feature using HTTP for the initial request.</span></span>

<div>

## <a name="initial-autodiscover-process-for-mobile-devices-using-port-80"></a><span data-ttu-id="3c303-116">Proceso de detección automática inicial para dispositivos móviles que usan el puerto 80</span><span class="sxs-lookup"><span data-stu-id="3c303-116">Initial Autodiscover Process for Mobile Devices Using Port 80</span></span>

1.  <span data-ttu-id="3c303-117">Dispositivo móvil que ejecuta Lync Mobile busca lyncdiscover.contoso.com mediante DNS, donde existe un registro A.</span><span class="sxs-lookup"><span data-stu-id="3c303-117">Mobile device running Lync Mobile looks up lyncdiscover.contoso.com using DNS, where an A record exists.</span></span>

2.  <span data-ttu-id="3c303-118">El DNS externo devuelve la dirección IP de los servicios web externos al cliente.</span><span class="sxs-lookup"><span data-stu-id="3c303-118">External DNS returns the IP address for the external web services to the client.</span></span>

3.  <span data-ttu-id="3c303-119">Un dispositivo móvil que ejecuta Lync Mobile http://lyncdiscover.contoso.com?sipuri=lyncUser1@contoso.com envía una solicitud al proxy inverso</span><span class="sxs-lookup"><span data-stu-id="3c303-119">Mobile device running Lync Mobile sends request http://lyncdiscover.contoso.com?sipuri=lyncUser1@contoso.com to the reverse proxy</span></span>

4.  <span data-ttu-id="3c303-120">La regla de publicación de web enlazará la solicitud del puerto 80 externamente al puerto 8080 de forma interna, que la enrutará a un director o a un servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="3c303-120">The web publishing rule will bridge the request from port 80 externally to port 8080 internally, which will then route it to either a Director or Front End Server.</span></span>
    
    <span data-ttu-id="3c303-121">Puesto que la solicitud es HTTP y no HTTPS, no es necesaria ninguna modificación en el certificado de la regla de publicación de los servicios web externos para admitir el servicio Detección automática.</span><span class="sxs-lookup"><span data-stu-id="3c303-121">Since the request is HTTP and not HTTPS, no modifications are needed to the certificate on the external web service publishing rule to support the Autodiscover Service.</span></span>

5.  <span data-ttu-id="3c303-122">El servicio Detección automática devuelve las direcciones URL del servicio web externo (en formato HTTPS).</span><span class="sxs-lookup"><span data-stu-id="3c303-122">The Autodiscover Service returns the external web service URLs (in HTTPS format).</span></span>

6.  <span data-ttu-id="3c303-123">El dispositivo móvil que ejecuta Lync Mobile puede volver a conectarse al proxy inverso en el puerto 443 y se redirige a través de 4443 al servicio de movilidad que se ejecuta en el grupo de servidores principales del usuario.</span><span class="sxs-lookup"><span data-stu-id="3c303-123">The mobile device running Lync Mobile can then reconnect to the reverse proxy on port 443 and is redirected over 4443 to the mobility service running on the user’s home pool.</span></span>
    
    <span data-ttu-id="3c303-124">Puesto que la consulta HTTPS es a la dirección URL de servicios web externos frente a la dirección URL del servicio Detección automática, se realiza correctamente porque el certificado ya deberá contener entradas de nombres alternativos de sujeto para los FQDN de servicios web externos.</span><span class="sxs-lookup"><span data-stu-id="3c303-124">Since the HTTPS query is to the external web services URL vs. the Autodiscover Service URL, it succeeds because the certificate will already contain subject alternative name entries for the external web services fully qualified domain names (FQDNs).</span></span>
    
    <span data-ttu-id="3c303-125">En este escenario, no hay cambios de certificado necesarios para admitir la movilidad.</span><span class="sxs-lookup"><span data-stu-id="3c303-125">In this scenario, there are no certificate changes required to support mobility.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3c303-126">Si el servidor web de destino tiene un certificado que no tiene un valor coincidente para lyncdiscover.contoso.com como valor de lista de nombres alternativos de sujeto:</span><span class="sxs-lookup"><span data-stu-id="3c303-126">If the target web server has a certificate that does not have a matching value for lyncdiscover.contoso.com as a subject alternative name list value:</span></span><BR><span data-ttu-id="3c303-127">a.&nbsp;&nbsp;&nbsp;el servidor web responde con un "servidor Hello" y ningún certificado.</span><span class="sxs-lookup"><span data-stu-id="3c303-127">a.&nbsp;&nbsp;&nbsp;Web server responds with a “Server Hello” and no certificate.</span></span><BR><span data-ttu-id="3c303-128">b.&nbsp;&nbsp;&nbsp;el dispositivo móvil que ejecuta Lync Mobile finaliza inmediatamente la sesión.</span><span class="sxs-lookup"><span data-stu-id="3c303-128">b.&nbsp;&nbsp;&nbsp;Mobile device running Lync Mobile immediately terminates the session.</span></span><BR><span data-ttu-id="3c303-129">Si el servidor web de destino tiene un certificado que incluye lyncdiscover.contoso.com como valor de lista de nombres alternativos de sujeto:</span><span class="sxs-lookup"><span data-stu-id="3c303-129">If the target web server has a certificate that includes lyncdiscover.contoso.com as a subject alternative name list value:</span></span><BR><span data-ttu-id="3c303-130">a.&nbsp;&nbsp;&nbsp;el servidor web responde con un "servidor Hello" y un certificado.</span><span class="sxs-lookup"><span data-stu-id="3c303-130">a.&nbsp;&nbsp;&nbsp;Web server responds with a “Server hello” and a certificate.</span></span><BR><span data-ttu-id="3c303-131">b.&nbsp;&nbsp;&nbsp;el dispositivo móvil que ejecuta Lync Mobile valida el certificado y completa el protocolo de enlace.</span><span class="sxs-lookup"><span data-stu-id="3c303-131">b.&nbsp;&nbsp;&nbsp;Mobile device running Lync Mobile validates the certificate and completes the handshake.</span></span>

    
    </div>

<span data-ttu-id="3c303-132">Para admitir una conexión inicial al servicio Detección automática usando el puerto 80 en su servidor proxy inverso, puede crear una regla de publicación http similar a este ejemplo para una regla de publicación de web de proxy inverso de Forefront Threat Management Gateway 2010:</span><span class="sxs-lookup"><span data-stu-id="3c303-132">To support an initial connection to the Autodiscover Service using port 80 on your reverse proxy server, you can create an http publishing rule similar to this example for a Forefront Threat Management Gateway 2010 reverse proxy web publishing rule:</span></span>

1.  <span data-ttu-id="3c303-133">Crear una nueva regla de publicación de web (por ejemplo, **Detección automática de Lync Server (HTTP)**).</span><span class="sxs-lookup"><span data-stu-id="3c303-133">Create a new web publishing rule (for example, **Lync Server Autodiscover (HTTP)**).</span></span>

2.  <span data-ttu-id="3c303-134">En **Nombre público**, escriba lyncdiscover.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="3c303-134">In **Public Name**, enter lyncdiscover.contoso.com.</span></span>

3.  <span data-ttu-id="3c303-135">En la ficha **Protocolo de puente**, seleccione solo la opción para conectar solicitudes del puerto 80 al puerto 8080.</span><span class="sxs-lookup"><span data-stu-id="3c303-135">On the **Bridging** tab, select only the option to bridge requests from Port 80 to Port 8080.</span></span>

4.  <span data-ttu-id="3c303-136">En la ficha **Autenticación**, seleccione **Sin autenticación** y **El cliente no se puede autenticar directamente**.</span><span class="sxs-lookup"><span data-stu-id="3c303-136">On the **Authentication** tab, select **No authentication**, and **Client cannot authenticate directly**.</span></span>

5.  <span data-ttu-id="3c303-137">Confirme los cambios y mueva la regla a la parte superior de la lista de reglas de Lync (primero en el orden de procesamiento).</span><span class="sxs-lookup"><span data-stu-id="3c303-137">Commit changes, and move the rule to the top of the list of Lync rules (first in processing order).</span></span>

</div>

<div>

## <a name="mobility-for-the-split-domain-deployment"></a><span data-ttu-id="3c303-138">Movilidad para la implementación de dominio dividido</span><span class="sxs-lookup"><span data-stu-id="3c303-138">Mobility for the Split Domain Deployment</span></span>

<span data-ttu-id="3c303-139">Un espacio de direcciones SIP compartido, también conocido como un *dominio dividido* o una *implementación híbrida* es una configuración en la que los usuarios se implementan en toda una implementación local y en un entorno en línea.</span><span class="sxs-lookup"><span data-stu-id="3c303-139">A shared SIP address space, also known as a *split-domain*, or a *hybrid deployment* is a configuration where users are deployed across an on-premise deployment and an online environment.</span></span> <span data-ttu-id="3c303-140">El resultado deseado es tener un usuario, independientemente de dónde se encuentre su servidor principal (in situ o en línea), para iniciar sesión en la implementación y redirigirse a la ubicación de su servidor principal.</span><span class="sxs-lookup"><span data-stu-id="3c303-140">The desired outcome is to have a user, regardless of where their home server is located (on-premise or online), to log into the deployment and be redirected to their home server location.</span></span> <span data-ttu-id="3c303-141">Para ello, se usa la característica de detección automática de Microsoft Lync Server 2013 para redirigir el usuario en línea a la topología en línea.</span><span class="sxs-lookup"><span data-stu-id="3c303-141">To accomplish this, the Autodiscover feature of Microsoft Lync Server 2013 is used to redirect the online user to the online topology.</span></span> <span data-ttu-id="3c303-142">Esto se lleva a cabo mediante la configuración del localizador uniforme de recursos (URL) de detección automática mediante el shell de administración de Lync Server y los cmdlets **Get-CsHostingProvider** y **set-CsHostingProvider**.</span><span class="sxs-lookup"><span data-stu-id="3c303-142">This is done by configuring the Autodiscover uniform resource locator (URL) by using the Lync Server Management Shell and the cmdlets **Get-CsHostingProvider** and **Set-CsHostingProvider**.</span></span>

<span data-ttu-id="3c303-143">Necesitará recopilar y registrar los siguientes atributos implementados:</span><span class="sxs-lookup"><span data-stu-id="3c303-143">You will need to collect and record the following deployed attributes:</span></span>

  - <span data-ttu-id="3c303-144">Desde el shell de administración de Lync Server, escriba</span><span class="sxs-lookup"><span data-stu-id="3c303-144">From the Lync Server Management Shell, type</span></span>
    
        Get-CsHostingProvider

  - <span data-ttu-id="3c303-p105">En los resultados, encuentre el proveedor en línea que tenga el atributo **ProxyFQDN**. Por ejemplo, sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="3c303-p105">In the results, find the online provider with the attribute **ProxyFQDN**. For example, sipfed.online.lync.com</span></span>

  - <span data-ttu-id="3c303-147">Registre el valor del ProxyFQDN</span><span class="sxs-lookup"><span data-stu-id="3c303-147">Record the value of the ProxyFQDN</span></span>

  - <span data-ttu-id="3c303-148">Habilitación de la Federación en el panel de control de Lync Server local, lo que permite la Federación con el proveedor en línea</span><span class="sxs-lookup"><span data-stu-id="3c303-148">Enable federation in the on-premise Lync Server Control Panel, allowing federation with the online provider</span></span>

  - <span data-ttu-id="3c303-p106">Habilite la federación para el proveedor en línea. De manera predeterminada, todos los usuarios en línea están habilitados para la federación de dominios y pueden comunicarse con todos los dominios</span><span class="sxs-lookup"><span data-stu-id="3c303-p106">Enable federation for the online provider. By default, all online users are enabled for domain federation and can communicate with all domains</span></span>

  - <span data-ttu-id="3c303-151">Si desea definir dominios restringidos y permitidos, determine de manera explícita los dominios que permitirá y los que restringirá</span><span class="sxs-lookup"><span data-stu-id="3c303-151">If you will define blocked and allowed domains, determine the domains that you will explicitly allow or explicitly block</span></span>

  - <span data-ttu-id="3c303-152">Para la federación en línea, debe planificar registros host (A o AAAA, si utiliza IPv6) de DNS, certificados y excepciones de firewall.</span><span class="sxs-lookup"><span data-stu-id="3c303-152">For online federation, you must plan for firewall exceptions, certificates and DNS host (A or AAAA, if using IPv6) records.</span></span> <span data-ttu-id="3c303-153">Asimismo, debe configurar las directivas de federación.</span><span class="sxs-lookup"><span data-stu-id="3c303-153">Additionally, you must configure federation policies.</span></span> <span data-ttu-id="3c303-154">Para obtener más información, consulte [Planning for Lync Server 2013 y Office Communications Server Federation](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md)</span><span class="sxs-lookup"><span data-stu-id="3c303-154">For details, see [Planning for Lync Server 2013 and Office Communications Server federation](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

