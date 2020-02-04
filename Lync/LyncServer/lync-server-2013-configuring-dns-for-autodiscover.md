---
title: 'Lync Server 2013: configuración de DNS para la detección automática'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring DNS for Autodiscover
ms:assetid: f07a634c-3cf3-4958-8556-84596319ef54
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945656(v=OCS.15)
ms:contentKeyID: 51541528
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77cf81cd82655a37ad089d915e9e3799671025bb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736460"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-dns-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="8fa4d-102">Configuración de DNS para la detección automática en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8fa4d-102">Configuring DNS for Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8fa4d-103">_**Última modificación del tema:** 2012-12-12_</span><span class="sxs-lookup"><span data-stu-id="8fa4d-103">_**Topic Last Modified:** 2012-12-12_</span></span>

<span data-ttu-id="8fa4d-104">Para admitir la detección automática de los clientes de Lync, debe crear los siguientes registros del sistema de nombres de dominio (DNS):</span><span class="sxs-lookup"><span data-stu-id="8fa4d-104">To support autodiscovery for Lync clients, you need to create the following Domain Name System (DNS) records:</span></span>

  - <span data-ttu-id="8fa4d-105">Un registro DNS interno para admitir clientes de Lync que se conecten desde la red de la organización</span><span class="sxs-lookup"><span data-stu-id="8fa4d-105">An internal DNS record to support Lync clients who connect from within your organization's network</span></span>

  - <span data-ttu-id="8fa4d-106">Un registro DNS público o externo para admitir clientes de Lync que se conectan desde Internet</span><span class="sxs-lookup"><span data-stu-id="8fa4d-106">An external, or public, DNS record to support Lync clients who connect from the Internet</span></span>

<span data-ttu-id="8fa4d-107">Debe crear un registro DNS interno y un registro DNS externo para cada dominio SIP.</span><span class="sxs-lookup"><span data-stu-id="8fa4d-107">You must create an internal DNS record and an external DNS record for each SIP domain.</span></span>

<span data-ttu-id="8fa4d-108">Los registros DNS pueden ser A (host) o registros CNAME, en función de su capacidad para crear certificados nuevos con el nombre alternativo de asunto adicional (SAN).</span><span class="sxs-lookup"><span data-stu-id="8fa4d-108">The DNS records can be either A (host) records or CNAME records, based on your ability to create new certificates with the additional subject alternate name (SAN).</span></span> <span data-ttu-id="8fa4d-109">Si no puede solicitar e implementar un nuevo certificado externo (público) con el lyncdiscover. \<nombre\> de dominio San, use el procedimiento para usar el puerto http/TCP 80.</span><span class="sxs-lookup"><span data-stu-id="8fa4d-109">If you are not able to request and deploy a new external (public) certificate with the lyncdiscover.\<domain name\> SAN, use the procedure for using HTTP/TCP port 80.</span></span> <span data-ttu-id="8fa4d-110">Los procedimientos siguientes describen cómo crear registros DNS internos y externos.</span><span class="sxs-lookup"><span data-stu-id="8fa4d-110">The following procedures describe how to create internal and external DNS records.</span></span>

<div>

## <a name="to-create-dns-cname-records"></a><span data-ttu-id="8fa4d-111">Para crear registros CNAME de DNS</span><span class="sxs-lookup"><span data-stu-id="8fa4d-111">To create DNS CNAME records</span></span>

1.  <span data-ttu-id="8fa4d-112">Inicie sesión en un servidor DNS de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="8fa4d-112">Log on to a DNS server as follows:</span></span>
    
      - <span data-ttu-id="8fa4d-113">Para crear un registro DNS interno, inicie sesión en un servidor DNS de la red como miembro del grupo administradores de dominio o miembro del grupo DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="8fa4d-113">To create an internal DNS record, log on to a DNS server in your network as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
    
      - <span data-ttu-id="8fa4d-114">Para crear un registro DNS externo, conéctese a su proveedor de DNS público.</span><span class="sxs-lookup"><span data-stu-id="8fa4d-114">To create an external DNS record, connect to your public DNS provider.</span></span>

2.  <span data-ttu-id="8fa4d-115">Abra el complemento administrativo DNS: haga clic en **Inicio**, haga clic en **herramientas administrativas**y, a continuación, haga clic en **DNS**.</span><span class="sxs-lookup"><span data-stu-id="8fa4d-115">Open the DNS administrative snap-in: Click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

3.  <span data-ttu-id="8fa4d-116">Siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="8fa4d-116">Do one of the following:</span></span>
    
      - <span data-ttu-id="8fa4d-117">Para un registro DNS interno, en el árbol de consola del servidor DNS, expanda **zonas de búsqueda directa** para el dominio de Active Directory (por ejemplo, contoso. local).</span><span class="sxs-lookup"><span data-stu-id="8fa4d-117">For an internal DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your Active Directory domain (for example, contoso.local).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="8fa4d-118">Este dominio es el dominio de Active Directory donde se instalan&nbsp;el grupo de directores de Lync Server 2013 y el grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="8fa4d-118">This domain is the Active Directory domain where your Lync Server 2013&nbsp;Director pool and Front End pool are installed.</span></span>

        
        </div>
    
      - <span data-ttu-id="8fa4d-119">Para un registro DNS externo, en el árbol de consola del servidor DNS, expanda **zonas de búsqueda directa** para su dominio SIP (por ejemplo, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="8fa4d-119">For an external DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>

4.  <span data-ttu-id="8fa4d-120">Compruebe que existe un registro para el grupo de directores de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="8fa4d-120">Verify that a host A record exists for your Director pool as follows:</span></span>
    
      - <span data-ttu-id="8fa4d-121">Para un registro DNS interno, debe existir un registro A para el nombre de dominio completo (FQDN) de los servicios Web internos para el grupo de directores (por ejemplo, lyncwebdir01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="8fa4d-121">For an internal DNS record, a host A record should exist for the internal Web Services fully qualified domain name (FQDN) for your Director pool (for example, lyncwebdir01.contoso.local).</span></span>
    
      - <span data-ttu-id="8fa4d-122">Para un registro DNS externo, debe existir un registro A host para el FQDN de los servicios web externos para el grupo de directores (por ejemplo, lyncwebextdir.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="8fa4d-122">For an external DNS record, a host A record should exist for the external web services FQDN for your Director pool (for example, lyncwebextdir.contoso.com).</span></span>

5.  <span data-ttu-id="8fa4d-123">Compruebe que existe un registro de host para el grupo de servidores front-end de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="8fa4d-123">Verify that a host A record exists for your Front End pool as follows:</span></span>
    
      - <span data-ttu-id="8fa4d-124">Para un registro DNS interno, debe existir un registro A en el FQDN de los servicios Web internos para el grupo de servidores front-end (por ejemplo, lyncwebpool01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="8fa4d-124">For an internal DNS record, a host A record should exist for the internal Web Services FQDN for your Front End pool (for example, lyncwebpool01.contoso.local).</span></span>
    
      - <span data-ttu-id="8fa4d-125">Para un registro DNS externo, debe existir un registro A host para el FQDN de los servicios web externos para el grupo de front-end (por ejemplo, lyncwebextpool01.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="8fa4d-125">For an external DNS record, a host A record should exist for the external Web Services FQDN for your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>

6.  <span data-ttu-id="8fa4d-126">Para un registro DNS interno, en el árbol de consola del servidor DNS, expanda **zonas de búsqueda directa** para su dominio SIP (por ejemplo, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="8fa4d-126">For an internal DNS record, in the console tree of your DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8fa4d-127">Si va a crear un registro DNS externo, las <STRONG>zonas de búsqueda directa</STRONG> ya están expandidas para su dominio SIP del paso 3.</span><span class="sxs-lookup"><span data-stu-id="8fa4d-127">If you are creating an external DNS record, <STRONG>Forward Lookup Zones</STRONG> is already expanded for your SIP domain from step 3.</span></span>

    
    </div>

7.  <span data-ttu-id="8fa4d-128">Haga clic con el botón derecho en el nombre de dominio SIP y después haga clic en **nuevo alias (CNAME)**.</span><span class="sxs-lookup"><span data-stu-id="8fa4d-128">Right-click the SIP domain name, and then click **New Alias (CNAME)**.</span></span>

8.  <span data-ttu-id="8fa4d-129">En **nombre de alias**, escriba una de las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="8fa4d-129">In **Alias name**, type one of the following:</span></span>
    
      - <span data-ttu-id="8fa4d-130">Para un registro DNS interno, escriba lyncdiscoverinternal como nombre de host para la dirección URL interna del servicio de detección automática.</span><span class="sxs-lookup"><span data-stu-id="8fa4d-130">For an internal DNS record, type lyncdiscoverinternal as the host name for the internal Autodiscover Service URL.</span></span>
    
      - <span data-ttu-id="8fa4d-131">Para un registro DNS externo, escriba lyncdiscover como nombre de host para la dirección URL del servicio de detección automática externa.</span><span class="sxs-lookup"><span data-stu-id="8fa4d-131">For an external DNS record, type lyncdiscover as the host name for the external Autodiscover Service URL.</span></span>

9.  <span data-ttu-id="8fa4d-132">En el **nombre de dominio completo (FQDN) del host de destino**, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="8fa4d-132">In **Fully qualified domain name (FQDN) for target host**, do one of the following:</span></span>
    
      - <span data-ttu-id="8fa4d-133">Para un registro DNS interno, escriba o busque el FQDN de servicios Web internos de su grupo de directores (por ejemplo, lyncwebdir01. contoso. local) y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8fa4d-133">For an internal DNS record, type or browse to the internal Web Services FQDN for your Director pool (for example, lyncwebdir01.contoso.local), and then click **OK**.</span></span>
    
      - <span data-ttu-id="8fa4d-134">Para un registro DNS externo, escriba o busque el FQDN de servicios web externos para el grupo de directores (por ejemplo, lyncwebextdir.contoso.com) y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8fa4d-134">For an external DNS record, type or browse to the external Web Services FQDN for your Director pool (for example, lyncwebextdir.contoso.com), and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8fa4d-135">Si no usa un director, use el FQDN de los servicios Web internos y externos para el grupo de servidores front-end, o bien, para un único servidor, el FQDN del servidor front-end o el servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="8fa4d-135">If you do not use a Director, use the internal and external Web Services FQDN for the Front End pool, or, for a single server, the FQDN for the Front End Server or Standard Edition server.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="8fa4d-136">Debe crear un nuevo registro CNAME de detección automática en la zona de búsqueda directa de cada dominio SIP que admita en el entorno de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8fa4d-136">You must create a new Autodiscover CNAME record in the forward lookup zone of each SIP domain that you support in your Lync Server 2013 environment.</span></span>

    
    </div>

</div>

<div>

## <a name="to-create-dns-a-records"></a><span data-ttu-id="8fa4d-137">Para crear registros A de DNS</span><span class="sxs-lookup"><span data-stu-id="8fa4d-137">To create DNS A records</span></span>

1.  <span data-ttu-id="8fa4d-138">Inicie sesión en un servidor DNS de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="8fa4d-138">Log on to a DNS server as follows:</span></span>
    
      - <span data-ttu-id="8fa4d-139">Para crear un registro DNS interno, inicie sesión en un servidor DNS de la red como miembro del grupo administradores de dominio o miembro del grupo DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="8fa4d-139">To create an internal DNS record, log on to a DNS server in your network as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
    
      - <span data-ttu-id="8fa4d-140">Para crear un registro DNS externo, conéctese a su proveedor de DNS público o servidor DNS externo.</span><span class="sxs-lookup"><span data-stu-id="8fa4d-140">To create an external DNS record, connect to your public DNS provider or external DNS server.</span></span>

2.  <span data-ttu-id="8fa4d-141">Abra el complemento administrativo DNS: haga clic en **Inicio**, haga clic en **herramientas administrativas**y, a continuación, haga clic en **DNS**.</span><span class="sxs-lookup"><span data-stu-id="8fa4d-141">Open the DNS administrative snap-in: Click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

3.  <span data-ttu-id="8fa4d-142">Siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="8fa4d-142">Do one of the following:</span></span>
    
      - <span data-ttu-id="8fa4d-143">Para un registro DNS interno, en el árbol de consola del servidor DNS, expanda **zonas de búsqueda directa** para el dominio de Active Directory (por ejemplo, contoso. local).</span><span class="sxs-lookup"><span data-stu-id="8fa4d-143">For an internal DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your Active Directory domain (for example, contoso.local).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="8fa4d-144">Este dominio es el dominio de Active Directory donde se instalan&nbsp;el grupo de directores de Lync Server 2013 y el grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="8fa4d-144">This domain is the Active Directory domain where your Lync Server 2013&nbsp;Director pool and Front End pool are installed.</span></span>

        
        </div>
    
      - <span data-ttu-id="8fa4d-145">Para un registro DNS externo, en el árbol de consola del servidor DNS, expanda **zonas de búsqueda directa** para su dominio SIP (por ejemplo, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="8fa4d-145">For an external DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>

4.  <span data-ttu-id="8fa4d-146">Compruebe que existe un registro A (para IPv6, AAAA) para el grupo de directores de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="8fa4d-146">Verify that a host A (for IPv6, AAAA) record exists for your Director pool as follows:</span></span>
    
      - <span data-ttu-id="8fa4d-147">Para un registro DNS interno, debe existir un registro host A (para IPv6, AAAA) para el FQDN de los servicios Web internos para el grupo de directores (por ejemplo, lyncwebdir01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="8fa4d-147">For an internal DNS record, a host A (for IPv6, AAAA) record should exist for the internal Web Services FQDN for your Director pool (for example, lyncwebdir01.contoso.local).</span></span>
    
      - <span data-ttu-id="8fa4d-148">Para un registro DNS externo, debe existir un registro host A (para IPv6, AAAA) para el FQDN de los servicios web externos para el grupo de directores (por ejemplo, lyncwebextdir.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="8fa4d-148">For an external DNS record, a host A (for IPv6, AAAA) record should exist for the external Web Services FQDN for your Director pool (for example, lyncwebextdir.contoso.com).</span></span>

5.  <span data-ttu-id="8fa4d-149">Compruebe que existe un registro host (para IPv6, AAAA) para el grupo de servidores front-end de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="8fa4d-149">Verify that a host A (for IPv6, AAAA) record exists for your Front End pool as follows:</span></span>
    
      - <span data-ttu-id="8fa4d-150">Para un registro DNS interno, debe existir un registro host A (para IPv6, AAAA) para el FQDN de los servicios Web internos de su grupo de front-end (por ejemplo, lyncwebpool01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="8fa4d-150">For an internal DNS record, a host A (for IPv6, AAAA) record should exist for the internal Web Services FQDN for your Front End pool (for example, lyncwebpool01.contoso.local).</span></span>
    
      - <span data-ttu-id="8fa4d-151">Para un registro DNS externo, debe existir un registro host (para IPv6, AAAA) para el FQDN de los servicios web externos para el grupo de front-end (por ejemplo, lyncwebextpool01.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="8fa4d-151">For an external DNS record, a host A (for IPv6, AAAA) record should exist for the external Web Services FQDN for your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>

6.  <span data-ttu-id="8fa4d-152">Para un registro DNS interno, en el árbol de consola del servidor DNS, expanda **zonas de búsqueda directa** para su dominio SIP (por ejemplo, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="8fa4d-152">For an internal DNS record, in the console tree of your DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8fa4d-153">Si va a crear un registro DNS externo, las <STRONG>zonas de búsqueda directa</STRONG> ya están expandidas para su dominio SIP del paso 3.</span><span class="sxs-lookup"><span data-stu-id="8fa4d-153">If you are creating an external DNS record, <STRONG>Forward Lookup Zones</STRONG> is already expanded for your SIP domain from step 3.</span></span>

    
    </div>

7.  <span data-ttu-id="8fa4d-154">Haga clic con el botón secundario en el nombre de dominio SIP y, a continuación, haga clic en **nuevo host (A o aaaa)**.</span><span class="sxs-lookup"><span data-stu-id="8fa4d-154">Right-click the SIP domain name, and then click **New Host (A or AAAA)**.</span></span>

8.  <span data-ttu-id="8fa4d-155">En **nombre**, escriba el nombre de host como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="8fa4d-155">In **Name**, type the host name as follows:</span></span>
    
      - <span data-ttu-id="8fa4d-156">Para un registro DNS interno, escriba lyncdiscoverinternal como nombre de host para la dirección URL interna del servicio de detección automática.</span><span class="sxs-lookup"><span data-stu-id="8fa4d-156">For an internal DNS record, type lyncdiscoverinternal as the host name for the internal Autodiscover Service URL.</span></span>
    
      - <span data-ttu-id="8fa4d-157">Para un registro DNS externo, escriba lyncdiscover como nombre de host para la dirección URL del servicio de detección automática externa.</span><span class="sxs-lookup"><span data-stu-id="8fa4d-157">For an external DNS record, type lyncdiscover as the host name for the external Autodiscover Service URL.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8fa4d-158">El nombre de dominio se supone de la zona en la que se define el registro y, por lo tanto, no es necesario escribirlo como parte del registro A.</span><span class="sxs-lookup"><span data-stu-id="8fa4d-158">The domain name is assumed from the zone in which the record is defined and, therefore, does not need to be entered as part of the A record.</span></span>

    
    </div>

9.  <span data-ttu-id="8fa4d-159">En **dirección IP**, escriba la dirección IP de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="8fa4d-159">In **IP Address**, type the IP address as follows:</span></span>
    
      - <span data-ttu-id="8fa4d-160">Para un registro DNS interno, escriba la dirección IP de los servicios Web internos del Director (o bien, si usa un equilibrador de carga, escriba la dirección IP virtual (VIP) del equilibrador de carga del Director).</span><span class="sxs-lookup"><span data-stu-id="8fa4d-160">For an internal DNS record, type the internal Web Services IP address of the Director (or, if you use a load balancer, type the virtual IP (VIP) of the Director load balancer).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="8fa4d-161">Si no usa un director, escriba la dirección IP del servidor front-end o del servidor Standard Edition, o bien, si usa un equilibrador de carga, escriba la VIP del equilibrador de carga del grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="8fa4d-161">If you do not use a Director, type the IP address of the Front End Server or Standard Edition server, or, if you use a load balancer, type the VIP of the Front End pool load balancer.</span></span>

        
        </div>
    
      - <span data-ttu-id="8fa4d-162">Para un registro DNS externo, escriba la dirección IP externa o pública del proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="8fa4d-162">For an external DNS record, type the external or public IP address of the reverse proxy.</span></span>

10. <span data-ttu-id="8fa4d-163">Haga clic en **Agregar host**y, a continuación, en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8fa4d-163">Click **Add Host**, and then click **OK**.</span></span>

11. <span data-ttu-id="8fa4d-164">Para crear un registro A adicional, repita los pasos 8 a 10.</span><span class="sxs-lookup"><span data-stu-id="8fa4d-164">To create an additional A record, repeat steps 8 through 10.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="8fa4d-165">Debe crear una nueva lyncdiscover y lyncdiscoverinternal registros A en la zona de búsqueda directa de cada dominio SIP que admita en el entorno de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8fa4d-165">You must create a new lyncdiscover and lyncdiscoverinternal A records in the forward lookup zone of each SIP domain that you support in your Lync Server 2013 environment.</span></span>

    
    </div>

12. <span data-ttu-id="8fa4d-166">Cuando haya terminado de crear un registro (para IPv6, AAAA), haga clic en **listo**.</span><span class="sxs-lookup"><span data-stu-id="8fa4d-166">When you are finished creating A (for IPv6, AAAA) records, click **Done**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

