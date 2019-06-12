---
title: 'Lync Server 2013: Configuración de los servidores proxy inversos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up reverse proxy servers
ms:assetid: 00bc138a-243f-4389-bfa5-9c62fcc95132
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398069(v=OCS.15)
ms:contentKeyID: 48183225
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef13f2351ab74c0e3b2ba558a9dbf0aef43d71b5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850640"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-reverse-proxy-servers-for-lync-server-2013"></a><span data-ttu-id="6e099-102">Configuración de los servidores proxy inversos para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e099-102">Setting up reverse proxy servers for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6e099-103">_**Última modificación del tema:** 2014-05-08_</span><span class="sxs-lookup"><span data-stu-id="6e099-103">_**Topic Last Modified:** 2014-05-08_</span></span>

<span data-ttu-id="6e099-104">Para implementaciones de servidor perimetral de Microsoft Lync Server 2013, es necesario un proxy inverso HTTPS en la red perimetral para que los clientes externos tengan acceso a los servicios Web de Lync Server 2013 (denominados *componentes Web* en Office Communications Server) en el director y el grupo de usuarios domésticos.</span><span class="sxs-lookup"><span data-stu-id="6e099-104">For Microsoft Lync Server 2013 Edge Server deployments, an HTTPS reverse proxy in the perimeter network is required for external clients to access the Lync Server 2013 Web Services (called *Web Components* in Office Communications Server) on the Director and the user’s home pool.</span></span> <span data-ttu-id="6e099-105">Algunas de las características que requieren acceso externo a través de un proxy inverso son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="6e099-105">Some of the features that require external access through a reverse proxy include the following:</span></span>

  - <span data-ttu-id="6e099-106">Permitir a los usuarios externos descargar el contenido de la reunión para sus reuniones.</span><span class="sxs-lookup"><span data-stu-id="6e099-106">Enabling external users to download meeting content for your meetings.</span></span>

  - <span data-ttu-id="6e099-107">Habilitar usuarios externos para expandir grupos de distribución.</span><span class="sxs-lookup"><span data-stu-id="6e099-107">Enabling external users to expand distribution groups.</span></span>

  - <span data-ttu-id="6e099-108">Permitir a los usuarios remotos descargar archivos desde el servicio de libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="6e099-108">Enabling remote users to download files from the Address Book service.</span></span>

  - <span data-ttu-id="6e099-109">Obtener acceso al cliente de Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="6e099-109">Accessing the Lync Web App client.</span></span>

  - <span data-ttu-id="6e099-110">Acceso a la Página Web de configuración de conferencias de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="6e099-110">Accessing the Dial-in Conferencing Settings webpage.</span></span>

  - <span data-ttu-id="6e099-111">Habilitar dispositivos externos para conectar con el servicio Web de actualización de dispositivos y obtener actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="6e099-111">Enabling external devices to connect to Device Update web service and obtain updates.</span></span>

  - <span data-ttu-id="6e099-112">Permitir que las aplicaciones móviles descubran y usen automáticamente las direcciones URL de movilidad (MCX) desde Internet.</span><span class="sxs-lookup"><span data-stu-id="6e099-112">Enabling mobile applications to automatically discover and use the mobility (Mcx) URLs from the Internet.</span></span>

  - <span data-ttu-id="6e099-113">Habilitar el cliente de Lync 2013, la aplicación de la tienda Windows de Lync y el cliente móvil Lync 2013 para ubicar las direcciones URL de detección de Lync (detección automática) y usar la API Web de comunicaciones unificadas (UCWA).</span><span class="sxs-lookup"><span data-stu-id="6e099-113">Enabling the Lync 2013 client, Lync Windows Store app and Lync 2013 Mobile client to locate the Lync Discover (autodiscover) URLs and use Unified Communications Web API (UCWA).</span></span>

<span data-ttu-id="6e099-114">Le recomendamos que configure su proxy HTTP inverso para publicar todos los servicios web en todos los grupos.</span><span class="sxs-lookup"><span data-stu-id="6e099-114">We recommend that you configure your HTTP reverse proxy to publish all Web Services in all pools.</span></span> <span data-ttu-id="6e099-115">Publicación de https://ExternalFQDN\* /publica todos los directorios virtuales de IIS para un grupo.</span><span class="sxs-lookup"><span data-stu-id="6e099-115">Publishing https:// ExternalFQDN/\* publishes all IIS virtual directories for a pool.</span></span> <span data-ttu-id="6e099-116">Necesita una regla de publicación para cada servidor Standard Edition, grupo de servidores front-end o grupo de directores o directores de su organización.</span><span class="sxs-lookup"><span data-stu-id="6e099-116">You need one publishing rule for each Standard Edition server, Front End pool, or Director or Director pool in your organization.</span></span>

<span data-ttu-id="6e099-117">Además, debe publicar las direcciones URL simples.</span><span class="sxs-lookup"><span data-stu-id="6e099-117">In addition, you need to publish the simple URLs.</span></span> <span data-ttu-id="6e099-118">Si la organización tiene un grupo de directores o directores, el proxy inverso HTTP escucha las solicitudes HTTP/HTTPS a las direcciones URL simples y envíales un proxy al directorio virtual de servicios Web externo del director o grupo de directores.</span><span class="sxs-lookup"><span data-stu-id="6e099-118">If the organization has a Director or Director pool, the HTTP reverse proxy listens for HTTP/HTTPS requests to the simple URLs and proxies them to the external Web Services virtual directory on the Director or Director pool.</span></span> <span data-ttu-id="6e099-119">Si no ha implementado un director, debe designar uno para administrar solicitudes a las direcciones URL simples.</span><span class="sxs-lookup"><span data-stu-id="6e099-119">If you have not deployed a Director, you need to designate one pool to handle requests to the simple URLs.</span></span> <span data-ttu-id="6e099-120">(Si este no es el grupo de hogar del usuario, lo redirigirá a los servicios web en el grupo de hogar del usuario).</span><span class="sxs-lookup"><span data-stu-id="6e099-120">(If this is not the user’s home pool, it will redirect them onward to the Web Services on the user’s home pool).</span></span> <span data-ttu-id="6e099-121">Las direcciones URL simples se pueden controlar mediante una regla de publicación de web dedicada o se puede Agregar a los nombres públicos de la regla de publicación web para el director.</span><span class="sxs-lookup"><span data-stu-id="6e099-121">The simple URLs can be handled by a dedicated web publishing rule, or you can add it to the public names of the web publishing rule for the Director.</span></span> <span data-ttu-id="6e099-122">También necesita publicar la dirección URL del servicio de detección automática externa.</span><span class="sxs-lookup"><span data-stu-id="6e099-122">You also need to publish the external Autodiscover Service URL.</span></span>

<span data-ttu-id="6e099-123">Puede usar Microsoft Forefront Threat Management Gateway 2010, Microsoft Internet Security and Acceleration (ISA) Server 2006 SP1 o Internet Information Server 7,0, 7,5 o 8,0 con enrutamiento de solicitud de aplicación (IIS ARR) como proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="6e099-123">You can use Microsoft Forefront Threat Management Gateway 2010, Microsoft Internet Security and Acceleration (ISA) Server 2006 SP1, or Internet Information Server 7.0, 7.5 or 8.0 with Application Request Routing (IIS ARR) as a reverse proxy.</span></span> <span data-ttu-id="6e099-124">Los pasos detallados en esta sección describen cómo configurar Forefront Threat Management Gateway 2010, y los pasos para configurar ISA Server 2006 son casi idénticos.</span><span class="sxs-lookup"><span data-stu-id="6e099-124">The detailed steps in this section describe how to configure Forefront Threat Management Gateway 2010, and the steps for configuring ISA Server 2006 are almost identical.</span></span> <span data-ttu-id="6e099-125">También se proporciona una guía para IIS ARR.</span><span class="sxs-lookup"><span data-stu-id="6e099-125">Guidance is also provided for IIS ARR.</span></span> <span data-ttu-id="6e099-126">Si está usando un proxy inverso diferente, consulte la documentación de ese producto y asigne los requisitos definidos aquí a las características asociadas de otros servidores proxy inversos.</span><span class="sxs-lookup"><span data-stu-id="6e099-126">If you are using a different reverse proxy, consult the documentation for that product and map the requirements defined here to the associated features in other reverse proxies.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6e099-127">El enrutamiento de solicitudes de aplicaciones de Internet Information Server (IIS ARR) es una opción completamente probada y admitida para implementar un proxy inverso para Lync Server 2010 y Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6e099-127">Internet Information Server Application Request Routing (IIS ARR) is a fully tested and supported option for implementing a reverse proxy for Lync Server 2010 and Lync Server 2013.</span></span> <span data-ttu-id="6e099-128">En noviembre de 2012, Microsoft ha cesado las ventas de licencias de ForeFront Threat Management Gateway 2010 o TMG.</span><span class="sxs-lookup"><span data-stu-id="6e099-128">In November, 2012, Microsoft ceased license sales of ForeFront Threat Management Gateway 2010, or TMG.</span></span> <span data-ttu-id="6e099-129">TMG sigue siendo un producto totalmente compatible y aún está disponible para su venta en dispositivos vendidos por terceros.</span><span class="sxs-lookup"><span data-stu-id="6e099-129">TMG is still a fully supported product, and is still available for sale on appliances sold by third parties.</span></span> <span data-ttu-id="6e099-130">Además, muchos servidores de seguridad y equilibradores de carga de hardware de terceros proporcionan soporte de proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="6e099-130">Also, many third party hardware load balancers and firewalls provide reverse proxy support.</span></span> <span data-ttu-id="6e099-131">Para los equilibradores de carga de hardware y los firewalls que proporcionan características de proxy invertida, consulte a su proveedor para obtener instrucciones específicas sobre cómo configurar su producto para proporcionar soporte inverso de proxy para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6e099-131">For hardware load balancers and firewalls that provide reverse proxy features, check with your vendor for specific instructions on how to configure their product to provide reverse proxy support for Lync Server.</span></span> <span data-ttu-id="6e099-132">También puede ver los terceros que han enviado documentación de su producto a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6e099-132">You can also view third parties that have submitted documentation for their product to Microsoft.</span></span> <span data-ttu-id="6e099-133">El soporte técnico es proporcionado por el tercero para su solución.</span><span class="sxs-lookup"><span data-stu-id="6e099-133">Support is provided by the third party for their solution.</span></span> <span data-ttu-id="6e099-134">Para ver los terceros que están activos en la oferta de soluciones, consulte <A href="http://go.microsoft.com/fwlink/?linkid=268730">infraestructura cualificada para Microsoft Lync</A>.</span><span class="sxs-lookup"><span data-stu-id="6e099-134">To see third parties that are active in providing solutions, see <A href="http://go.microsoft.com/fwlink/?linkid=268730">Infrastructure qualified for Microsoft Lync</A>.</span></span>



</div>

<span data-ttu-id="6e099-135">Los siguientes temas y procedimientos usan Forefront Threat Management Gateway 2010 e IIS ARR como la base de los procedimientos de implementación y configuración.</span><span class="sxs-lookup"><span data-stu-id="6e099-135">The following topics and procedures use Forefront Threat Management Gateway 2010 and IIS ARR as the basis for the deployment and configuration procedures.</span></span>

  - [<span data-ttu-id="6e099-136">Configurar los nombres de dominio completos (FQDN) de la granja de servidores web para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e099-136">Configure web farm FQDNs for Lync Server 2013</span></span>](lync-server-2013-configure-web-farm-fqdns.md)

  - [<span data-ttu-id="6e099-137">Configurar adaptadores de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e099-137">Configure network adapters in Lync Server 2013</span></span>](lync-server-2013-configure-network-adapters.md)

  - [<span data-ttu-id="6e099-138">Solicitar y configurar un certificado para el proxy HTTP inverso en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e099-138">Request and configure a certificate for your reverse HTTP proxy in Lync Server 2013</span></span>](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md)

  - [<span data-ttu-id="6e099-139">Configurar las reglas de publicación web para un solo grupo de servidores interno en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e099-139">Configure web publishing rules for a single internal pool in Lync Server 2013</span></span>](lync-server-2013-configure-web-publishing-rules-for-a-single-internal-pool.md)

  - [<span data-ttu-id="6e099-140">Comprobar o configurar la autenticación y la certificación en directorios virtuales IIS en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e099-140">Verify or configure authentication and certification on IIS virtual directories in Lync Server 2013</span></span>](lync-server-2013-verify-or-configure-authentication-and-certification-on-iis-virtual-directories.md)

  - [<span data-ttu-id="6e099-141">Crear registros DNS para servidores de proxy inverso en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e099-141">Create DNS records for reverse proxy servers in Lync Server 2013</span></span>](lync-server-2013-create-dns-records-for-reverse-proxy-servers.md)

  - [<span data-ttu-id="6e099-142">Comprobar el acceso a través del proxy inverso en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e099-142">Verify access through your reverse proxy in Lync Server 2013</span></span>](lync-server-2013-verify-access-through-your-reverse-proxy.md)

<div>

## <a name="before-you-begin"></a><span data-ttu-id="6e099-143">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="6e099-143">Before You Begin</span></span>

<span data-ttu-id="6e099-144">Para implementar correctamente Forefront Threat Management Gateway 2010 como su proxy inverso, necesita configurar y configurar un servidor, usando los requisitos previos y requisitos de hardware definidos en la documentación de la puerta de 2010 enlace de administración de Forefront Threat Management.</span><span class="sxs-lookup"><span data-stu-id="6e099-144">To successfully deploy Forefront Threat Management Gateway 2010 as your reverse proxy, you need to setup and configure a server, using the prerequisites and hardware requirements defined in the Forefront Threat Management Gateway 2010 documentation.</span></span> <span data-ttu-id="6e099-145">Vea el tema siguiente configurado para configurar correctamente el hardware e instalar Forefront Threat Management Gateway 2010 en el servidor antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="6e099-145">See the following topic set to properly configure the hardware and to install Forefront Threat Management Gateway 2010 on the server before proceeding.</span></span>

  - <span></span>  
    [<span data-ttu-id="6e099-146">Forefront Threat Management Gateway (TMG) 2010</span><span class="sxs-lookup"><span data-stu-id="6e099-146">Forefront Threat Management Gateway (TMG) 2010</span></span>](http://go.microsoft.com/fwlink/?linkid=291292)

  - <span></span>  
    [<span data-ttu-id="6e099-147">Recomendaciones de hardware de Forefront TMG 2010</span><span class="sxs-lookup"><span data-stu-id="6e099-147">Forefront TMG 2010 hardware recommendations</span></span>](http://go.microsoft.com/fwlink/?linkid=291293)

<span data-ttu-id="6e099-148">Para implementar correctamente IIS ARR como su proxy inverso, revise los temas siguientes para configurar el hardware y el software necesario.</span><span class="sxs-lookup"><span data-stu-id="6e099-148">To successfully deploy IIS ARR as your reverse proxy, review the following topics to configure the hardware and the prerequisite software.</span></span>

  - <span></span>  
    <span data-ttu-id="6e099-149">Para instalar IIS en Windows Server 2008 o Windows Server 2008 R2, consulte [instalar IIS 7 en Windows server 2008 o Windows server 2008 R2](http://go.microsoft.com/fwlink/?linkid=291296)</span><span class="sxs-lookup"><span data-stu-id="6e099-149">To install IIS on Windows Server 2008 or Windows Server 2008 R2, see [Installing IIS 7 on Windows Server 2008 or Windows Server 2008 R2](http://go.microsoft.com/fwlink/?linkid=291296)</span></span>

  - <span></span>  
    <span data-ttu-id="6e099-150">Para instalar IIS en Windows Server 2012, consulte [instalar IIS 8 en Windows server 2012](http://go.microsoft.com/fwlink/?linkid=291297)</span><span class="sxs-lookup"><span data-stu-id="6e099-150">To install IIS on Windows Server 2012, see [Installing IIS 8 on Windows Server 2012](http://go.microsoft.com/fwlink/?linkid=291297)</span></span>

  - <span></span>  
    <span data-ttu-id="6e099-151">Para instalar IIS en Windows Server 2012 R2, consulte [instalar iis 8,5 en Windows server 2012 R2](http://go.microsoft.com/fwlink/?linkid=330687)</span><span class="sxs-lookup"><span data-stu-id="6e099-151">To install IIS on Windows Server 2012 R2, see [Installing IIS 8.5 on Windows Server 2012 R2](http://go.microsoft.com/fwlink/?linkid=330687)</span></span>

  - <span></span>  
    <span data-ttu-id="6e099-152">Para descargar la extensión de enrutamiento de solicitud de la aplicación para IIS, siga las instrucciones de la [solicitud de enrutamiento v 2.5 de solicitud de aplicación](http://go.microsoft.com/fwlink/?linkid=291298)</span><span class="sxs-lookup"><span data-stu-id="6e099-152">To download the Application Request Routing extension for IIS, follow the instructions at [Application Request Routing v2.5 Download](http://go.microsoft.com/fwlink/?linkid=291298)</span></span>

  - <span></span>  
    <span data-ttu-id="6e099-153">Para instalar ARR, para las instrucciones en [instalar aplicación solicitud de enrutamiento versión 2](http://go.microsoft.com/fwlink/?linkid=291299)</span><span class="sxs-lookup"><span data-stu-id="6e099-153">To install ARR, for the instructions at [Install Application Request Routing Version 2](http://go.microsoft.com/fwlink/?linkid=291299)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6e099-154">Las instrucciones publicadas actualmente son para ARR 2,0.</span><span class="sxs-lookup"><span data-stu-id="6e099-154">The instructions currently posted are for ARR 2.0.</span></span> <span data-ttu-id="6e099-155">Para la instalación de la extensión, no hay ninguna diferencia entre las dos versiones.</span><span class="sxs-lookup"><span data-stu-id="6e099-155">For installation of the extension, there is no difference between the two versions.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

