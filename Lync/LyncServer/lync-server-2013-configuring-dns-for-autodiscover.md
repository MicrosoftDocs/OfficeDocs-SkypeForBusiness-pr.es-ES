---
title: 'Lync Server 2013: configuración de DNS para la detección automática'
description: 'Lync Server 2013: configuración de DNS para la detección automática.'
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
ms.openlocfilehash: 98a56cf3aa260bcbec9099e65958a9b17c3eaf26
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548466"
---
# <a name="configuring-dns-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="6c331-103">Configuración de DNS para la detección automática en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c331-103">Configuring DNS for Autodiscover in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6c331-104">_**Última modificación del tema:** 2012-12-12_</span><span class="sxs-lookup"><span data-stu-id="6c331-104">_**Topic Last Modified:** 2012-12-12_</span></span>

<span data-ttu-id="6c331-105">Para admitir la detección automática de clientes de Lync, debe crear los siguientes registros del sistema de nombres de dominio (DNS):</span><span class="sxs-lookup"><span data-stu-id="6c331-105">To support autodiscovery for Lync clients, you need to create the following Domain Name System (DNS) records:</span></span>

  - <span data-ttu-id="6c331-106">Un registro DNS interno para admitir clientes de Lync que se conectan desde dentro de la red de la organización</span><span class="sxs-lookup"><span data-stu-id="6c331-106">An internal DNS record to support Lync clients who connect from within your organization's network</span></span>

  - <span data-ttu-id="6c331-107">Un registro DNS externo, o público, para admitir clientes de Lync que se conectan desde Internet</span><span class="sxs-lookup"><span data-stu-id="6c331-107">An external, or public, DNS record to support Lync clients who connect from the Internet</span></span>

<span data-ttu-id="6c331-108">Debe crear un registro DNS interno y un registro DNS externo para cada dominio SIP.</span><span class="sxs-lookup"><span data-stu-id="6c331-108">You must create an internal DNS record and an external DNS record for each SIP domain.</span></span>

<span data-ttu-id="6c331-109">Los registros DNS pueden ser registros CNAME o registros A (host), en función de la capacidad de crear nuevos certificados con el nombre alternativo de sujeto adicional (SAN).</span><span class="sxs-lookup"><span data-stu-id="6c331-109">The DNS records can be either A (host) records or CNAME records, based on your ability to create new certificates with the additional subject alternate name (SAN).</span></span> <span data-ttu-id="6c331-110">Si no puede solicitar e implementar un nuevo certificado externo (público) con el lyncdiscover.\<domain name\></span><span class="sxs-lookup"><span data-stu-id="6c331-110">If you are not able to request and deploy a new external (public) certificate with the lyncdiscover.\<domain name\></span></span> <span data-ttu-id="6c331-111">SAN, use el procedimiento para usar el puerto HTTP/TCP 80.</span><span class="sxs-lookup"><span data-stu-id="6c331-111">SAN, use the procedure for using HTTP/TCP port 80.</span></span> <span data-ttu-id="6c331-112">Los siguientes procedimientos describen cómo crear registros DNS internos y externos.</span><span class="sxs-lookup"><span data-stu-id="6c331-112">The following procedures describe how to create internal and external DNS records.</span></span>

<div>

## <a name="to-create-dns-cname-records"></a><span data-ttu-id="6c331-113">Para crear registros CNAME de DNS</span><span class="sxs-lookup"><span data-stu-id="6c331-113">To create DNS CNAME records</span></span>

1.  <span data-ttu-id="6c331-114">Inicie sesión en un servidor DNS de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="6c331-114">Log on to a DNS server as follows:</span></span>
    
      - <span data-ttu-id="6c331-115">Para crear un registro DNS interno, inicie sesión en un servidor DNS de su red como miembro del grupo Domain Admins o miembro del grupo DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="6c331-115">To create an internal DNS record, log on to a DNS server in your network as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
    
      - <span data-ttu-id="6c331-116">Para crear un registro DNS externo, conéctese a su proveedor de DNS público.</span><span class="sxs-lookup"><span data-stu-id="6c331-116">To create an external DNS record, connect to your public DNS provider.</span></span>

2.  <span data-ttu-id="6c331-117">Abra el complemento administrativo de DNS: haga clic en **Iniciar**, en **Herramientas administrativas** y en **DNS**.</span><span class="sxs-lookup"><span data-stu-id="6c331-117">Open the DNS administrative snap-in: Click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

3.  <span data-ttu-id="6c331-118">Siga uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="6c331-118">Do one of the following:</span></span>
    
      - <span data-ttu-id="6c331-119">Para un registro DNS interno, en el árbol de la consola del servidor DNS, expanda **Zonas de búsqueda directa** para su domino de Active Directory (por ejemplo, contoso.local).</span><span class="sxs-lookup"><span data-stu-id="6c331-119">For an internal DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your Active Directory domain (for example, contoso.local).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="6c331-120">Este dominio es el dominio de Active Directory en el que &nbsp; se instalan el grupo de directores de Lync Server 2013 y el grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="6c331-120">This domain is the Active Directory domain where your Lync Server 2013&nbsp;Director pool and Front End pool are installed.</span></span>

        
        </div>
    
      - <span data-ttu-id="6c331-121">Para un registro DNS externo, en el árbol de la consola del servidor DNS, expanda  **Zonas de búsqueda directa**para su dominio SIP (por ejemplo, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="6c331-121">For an external DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>

4.  <span data-ttu-id="6c331-122">Compruebe que existe un registro de host A para su grupo de directores de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="6c331-122">Verify that a host A record exists for your Director pool as follows:</span></span>
    
      - <span data-ttu-id="6c331-123">Para un registro DNS interno, debe haber un registro de host A para el nombre de dominio completo (FQDN) de servicios Web internos del grupo de directores (por ejemplo, lyncwebdir01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="6c331-123">For an internal DNS record, a host A record should exist for the internal Web Services fully qualified domain name (FQDN) for your Director pool (for example, lyncwebdir01.contoso.local).</span></span>
    
      - <span data-ttu-id="6c331-124">Para un registro DNS externo, debe haber un registro de host A para el FQDN de servicios web externos para el grupo de directores (por ejemplo, lyncwebextdir.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="6c331-124">For an external DNS record, a host A record should exist for the external web services FQDN for your Director pool (for example, lyncwebextdir.contoso.com).</span></span>

5.  <span data-ttu-id="6c331-125">Compruebe que existe un registro de host A para el grupo de servidores front-end de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="6c331-125">Verify that a host A record exists for your Front End pool as follows:</span></span>
    
      - <span data-ttu-id="6c331-126">Para un registro DNS interno, debe haber un registro de host A para el FQDN de servicios Web internos del grupo de servidores front-end (por ejemplo, lyncwebpool01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="6c331-126">For an internal DNS record, a host A record should exist for the internal Web Services FQDN for your Front End pool (for example, lyncwebpool01.contoso.local).</span></span>
    
      - <span data-ttu-id="6c331-127">Para un registro DNS externo, debe haber un registro de host A para el FQDN de servicios web externos del grupo de servidores front-end (por ejemplo, lyncwebextpool01.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="6c331-127">For an external DNS record, a host A record should exist for the external Web Services FQDN for your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>

6.  <span data-ttu-id="6c331-128">Para un registro DNS interno, en el árbol de la consola del servidor DNS, expanda **Zonas de búsqueda directa** para su domino SIP (por ejemplo, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="6c331-128">For an internal DNS record, in the console tree of your DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6c331-129">Si crea un registro DNS externo, <STRONG>Zonas de búsqueda directa</STRONG> ya está expandido en su domino SIP desde el paso 3.</span><span class="sxs-lookup"><span data-stu-id="6c331-129">If you are creating an external DNS record, <STRONG>Forward Lookup Zones</STRONG> is already expanded for your SIP domain from step 3.</span></span>

    
    </div>

7.  <span data-ttu-id="6c331-130">Haga clic con el botón secundario del mouse en el nombre de dominio SIP y, a continuación, haga clic en **Nuevo alias (CNAME)**.</span><span class="sxs-lookup"><span data-stu-id="6c331-130">Right-click the SIP domain name, and then click **New Alias (CNAME)**.</span></span>

8.  <span data-ttu-id="6c331-131">En **Nombre de alias**, escriba una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="6c331-131">In **Alias name**, type one of the following:</span></span>
    
      - <span data-ttu-id="6c331-132">Para un registro DNS interno, escriba lyncdiscoverinternal como nombre de host para la dirección URL del servicio Detección automática interna.</span><span class="sxs-lookup"><span data-stu-id="6c331-132">For an internal DNS record, type lyncdiscoverinternal as the host name for the internal Autodiscover Service URL.</span></span>
    
      - <span data-ttu-id="6c331-133">Para un registro DNS externo, escriba lyncdiscover como nombre de host para la dirección URL del servicio Detección automática externa.</span><span class="sxs-lookup"><span data-stu-id="6c331-133">For an external DNS record, type lyncdiscover as the host name for the external Autodiscover Service URL.</span></span>

9.  <span data-ttu-id="6c331-134">En **Nombre de dominio completo (FQDN) para el host de destino**, realice una de las operaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="6c331-134">In **Fully qualified domain name (FQDN) for target host**, do one of the following:</span></span>
    
      - <span data-ttu-id="6c331-135">Para un registro DNS interno, escriba o busque el FQDN de servicios Web interno de su grupo de directores (por ejemplo, lyncwebdir01. contoso. local) y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6c331-135">For an internal DNS record, type or browse to the internal Web Services FQDN for your Director pool (for example, lyncwebdir01.contoso.local), and then click **OK**.</span></span>
    
      - <span data-ttu-id="6c331-136">Para un registro DNS externo, escriba o busque el FQDN de servicios web externos para el grupo de directores (por ejemplo, lyncwebextdir.contoso.com) y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6c331-136">For an external DNS record, type or browse to the external Web Services FQDN for your Director pool (for example, lyncwebextdir.contoso.com), and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6c331-137">Si no usa un director, use el FQDN de servicios Web internos y externos para el grupo de servidores front-end, o bien, para un solo servidor, el FQDN para el servidor front-end o el servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="6c331-137">If you do not use a Director, use the internal and external Web Services FQDN for the Front End pool, or, for a single server, the FQDN for the Front End Server or Standard Edition server.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="6c331-138">Debe crear un nuevo registro CNAME de detección automática en la zona de búsqueda directa de cada dominio SIP que admita en su entorno de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6c331-138">You must create a new Autodiscover CNAME record in the forward lookup zone of each SIP domain that you support in your Lync Server 2013 environment.</span></span>

    
    </div>

</div>

<div>

## <a name="to-create-dns-a-records"></a><span data-ttu-id="6c331-139">Para crear registros DNS A</span><span class="sxs-lookup"><span data-stu-id="6c331-139">To create DNS A records</span></span>

1.  <span data-ttu-id="6c331-140">Inicie sesión en un servidor DNS de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="6c331-140">Log on to a DNS server as follows:</span></span>
    
      - <span data-ttu-id="6c331-141">Para crear un registro DNS interno, inicie sesión en un servidor DNS de su red como miembro del grupo Domain Admins o miembro del grupo DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="6c331-141">To create an internal DNS record, log on to a DNS server in your network as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
    
      - <span data-ttu-id="6c331-142">Para crear un registro DNS externo, conéctese a su proveedor de DNS público o al servidor DNS externo.</span><span class="sxs-lookup"><span data-stu-id="6c331-142">To create an external DNS record, connect to your public DNS provider or external DNS server.</span></span>

2.  <span data-ttu-id="6c331-143">Abra el complemento administrativo de DNS: haga clic en **Iniciar**, en **Herramientas administrativas** y en **DNS**.</span><span class="sxs-lookup"><span data-stu-id="6c331-143">Open the DNS administrative snap-in: Click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

3.  <span data-ttu-id="6c331-144">Siga uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="6c331-144">Do one of the following:</span></span>
    
      - <span data-ttu-id="6c331-145">Para un registro DNS interno, en el árbol de la consola del servidor DNS, expanda **Zonas de búsqueda directa** para su domino de Active Directory (por ejemplo, contoso.local).</span><span class="sxs-lookup"><span data-stu-id="6c331-145">For an internal DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your Active Directory domain (for example, contoso.local).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="6c331-146">Este dominio es el dominio de Active Directory en el que &nbsp; se instalan el grupo de directores de Lync Server 2013 y el grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="6c331-146">This domain is the Active Directory domain where your Lync Server 2013&nbsp;Director pool and Front End pool are installed.</span></span>

        
        </div>
    
      - <span data-ttu-id="6c331-147">Para un registro DNS externo, en el árbol de la consola del servidor DNS, expanda  **Zonas de búsqueda directa**para su dominio SIP (por ejemplo, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="6c331-147">For an external DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>

4.  <span data-ttu-id="6c331-148">Compruebe que exista un registro de host A (para IPv6, AAAA) para el grupo de directores de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="6c331-148">Verify that a host A (for IPv6, AAAA) record exists for your Director pool as follows:</span></span>
    
      - <span data-ttu-id="6c331-149">Para un registro DNS interno, debe haber un registro de host A (para IPv6, AAAA) para el FQDN de servicios Web internos del grupo de directores (por ejemplo, lyncwebdir01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="6c331-149">For an internal DNS record, a host A (for IPv6, AAAA) record should exist for the internal Web Services FQDN for your Director pool (for example, lyncwebdir01.contoso.local).</span></span>
    
      - <span data-ttu-id="6c331-150">Para un registro DNS externo, debe haber un registro de host A (para IPv6, AAAA) para el FQDN de servicios web externos del grupo de directores (por ejemplo, lyncwebextdir.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="6c331-150">For an external DNS record, a host A (for IPv6, AAAA) record should exist for the external Web Services FQDN for your Director pool (for example, lyncwebextdir.contoso.com).</span></span>

5.  <span data-ttu-id="6c331-151">Compruebe que existe un registro de host A (para IPv6, AAAA) para el grupo de servidores front-end de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="6c331-151">Verify that a host A (for IPv6, AAAA) record exists for your Front End pool as follows:</span></span>
    
      - <span data-ttu-id="6c331-152">Para un registro DNS interno, debe haber un registro de host A (para IPv6, AAAA) para el FQDN de servicios Web internos del grupo de servidores front-end (por ejemplo, lyncwebpool01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="6c331-152">For an internal DNS record, a host A (for IPv6, AAAA) record should exist for the internal Web Services FQDN for your Front End pool (for example, lyncwebpool01.contoso.local).</span></span>
    
      - <span data-ttu-id="6c331-153">Para un registro DNS externo, debe haber un registro de host A (para IPv6, AAAA) para el FQDN de servicios web externos del grupo de servidores front-end (por ejemplo, lyncwebextpool01.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="6c331-153">For an external DNS record, a host A (for IPv6, AAAA) record should exist for the external Web Services FQDN for your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>

6.  <span data-ttu-id="6c331-154">Para un registro DNS interno, en el árbol de la consola del servidor DNS, expanda **Zonas de búsqueda directa** para su domino SIP (por ejemplo, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="6c331-154">For an internal DNS record, in the console tree of your DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6c331-155">Si crea un registro DNS externo, <STRONG>Zonas de búsqueda directa</STRONG>ya está expandido en su domino SIP desde el paso 3.</span><span class="sxs-lookup"><span data-stu-id="6c331-155">If you are creating an external DNS record, <STRONG>Forward Lookup Zones</STRONG> is already expanded for your SIP domain from step 3.</span></span>

    
    </div>

7.  <span data-ttu-id="6c331-156">Haga clic con el botón secundario del mouse en el nombre de dominio SIP y, a continuación, haga clic en **Nuevo host (A o AAAA)**.</span><span class="sxs-lookup"><span data-stu-id="6c331-156">Right-click the SIP domain name, and then click **New Host (A or AAAA)**.</span></span>

8.  <span data-ttu-id="6c331-157">En **Nombre**, escriba el nombre de host de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="6c331-157">In **Name**, type the host name as follows:</span></span>
    
      - <span data-ttu-id="6c331-158">Para un registro DNS interno, escriba lyncdiscoverinternal como nombre de host para la dirección URL del servicio Detección automática interna.</span><span class="sxs-lookup"><span data-stu-id="6c331-158">For an internal DNS record, type lyncdiscoverinternal as the host name for the internal Autodiscover Service URL.</span></span>
    
      - <span data-ttu-id="6c331-159">Para un registro DNS externo, escriba lyncdiscover como nombre de host para la dirección URL del servicio Detección automática externa.</span><span class="sxs-lookup"><span data-stu-id="6c331-159">For an external DNS record, type lyncdiscover as the host name for the external Autodiscover Service URL.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6c331-160">El nombre de dominio se deduce de la zona en la que se define el registro y, por lo tanto, no es necesario introducirlo como parte del registro A.</span><span class="sxs-lookup"><span data-stu-id="6c331-160">The domain name is assumed from the zone in which the record is defined and, therefore, does not need to be entered as part of the A record.</span></span>

    
    </div>

9.  <span data-ttu-id="6c331-161">En **Dirección IP**, escriba la dirección IP de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="6c331-161">In **IP Address**, type the IP address as follows:</span></span>
    
      - <span data-ttu-id="6c331-162">Para un registro DNS interno, escriba la dirección IP de los servicios Web internos del Director (o bien, si usa un equilibrador de carga, escriba la IP virtual (VIP) del equilibrador de carga del Director).</span><span class="sxs-lookup"><span data-stu-id="6c331-162">For an internal DNS record, type the internal Web Services IP address of the Director (or, if you use a load balancer, type the virtual IP (VIP) of the Director load balancer).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="6c331-163">Si no usa un director, escriba la dirección IP del servidor front-end o del servidor Standard Edition, o bien, si usa un equilibrador de carga, escriba la VIP del equilibrador de carga del grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="6c331-163">If you do not use a Director, type the IP address of the Front End Server or Standard Edition server, or, if you use a load balancer, type the VIP of the Front End pool load balancer.</span></span>

        
        </div>
    
      - <span data-ttu-id="6c331-164">Para un registro DNS externo, escriba la dirección IP externa o pública del proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="6c331-164">For an external DNS record, type the external or public IP address of the reverse proxy.</span></span>

10. <span data-ttu-id="6c331-165">Haga clic en **Agregar host** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6c331-165">Click **Add Host**, and then click **OK**.</span></span>

11. <span data-ttu-id="6c331-166">Para crear un registro A adicional, repita los pasos del 8 al 10.</span><span class="sxs-lookup"><span data-stu-id="6c331-166">To create an additional A record, repeat steps 8 through 10.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="6c331-167">Debe crear un nuevo lyncdiscover y lyncdiscoverinternal A registros A en la zona de búsqueda directa de cada dominio SIP que admita en su entorno de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6c331-167">You must create a new lyncdiscover and lyncdiscoverinternal A records in the forward lookup zone of each SIP domain that you support in your Lync Server 2013 environment.</span></span>

    
    </div>

12. <span data-ttu-id="6c331-168">Cuando acabe de crear registros A (para IPv6, AAAA), haga clic en **Listo**.</span><span class="sxs-lookup"><span data-stu-id="6c331-168">When you are finished creating A (for IPv6, AAAA) records, click **Done**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

