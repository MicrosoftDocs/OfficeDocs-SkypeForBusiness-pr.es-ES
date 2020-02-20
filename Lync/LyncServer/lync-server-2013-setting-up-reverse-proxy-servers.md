---
title: 'Lync Server 2013: configuración de servidores proxy inversos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up reverse proxy servers
ms:assetid: 00bc138a-243f-4389-bfa5-9c62fcc95132
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398069(v=OCS.15)
ms:contentKeyID: 48183225
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f0d00b30100b9203c82df0a2fc8ed8c4c593dfb0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143004"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-reverse-proxy-servers-for-lync-server-2013"></a><span data-ttu-id="abe57-102">Configuración de servidores proxy inversos para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="abe57-102">Setting up reverse proxy servers for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="abe57-103">_**Última modificación del tema:** 2014-05-08_</span><span class="sxs-lookup"><span data-stu-id="abe57-103">_**Topic Last Modified:** 2014-05-08_</span></span>

<span data-ttu-id="abe57-104">Para las implementaciones del servidor perimetral 2013 de Microsoft Lync Server, se requiere un proxy inverso HTTPS en la red perimetral para que los clientes externos tengan acceso a los servicios Web de Lync Server 2013 (denominados *componentes Web* en Office Communications Server) en el director y en el grupo de servidores principales del usuario.</span><span class="sxs-lookup"><span data-stu-id="abe57-104">For Microsoft Lync Server 2013 Edge Server deployments, an HTTPS reverse proxy in the perimeter network is required for external clients to access the Lync Server 2013 Web Services (called *Web Components* in Office Communications Server) on the Director and the user’s home pool.</span></span> <span data-ttu-id="abe57-105">Algunas de las características que requieren un acceso externo a través de un proxy inverso incluyen lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="abe57-105">Some of the features that require external access through a reverse proxy include the following:</span></span>

  - <span data-ttu-id="abe57-106">Habilitación de los usuarios externos para descargar el contenido de la reunión para sus reuniones.</span><span class="sxs-lookup"><span data-stu-id="abe57-106">Enabling external users to download meeting content for your meetings.</span></span>

  - <span data-ttu-id="abe57-107">Habilitación de los usuarios externos para expandir grupos de distribución.</span><span class="sxs-lookup"><span data-stu-id="abe57-107">Enabling external users to expand distribution groups.</span></span>

  - <span data-ttu-id="abe57-108">Habilitación de los usuarios remotos para descargar archivos desde el servicio de libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="abe57-108">Enabling remote users to download files from the Address Book service.</span></span>

  - <span data-ttu-id="abe57-109">Obtener acceso al cliente de Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="abe57-109">Accessing the Lync Web App client.</span></span>

  - <span data-ttu-id="abe57-110">Acceso a la página web de configuración de conferencia de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="abe57-110">Accessing the Dial-in Conferencing Settings webpage.</span></span>

  - <span data-ttu-id="abe57-111">Habilitación de los dispositivos externos para conectarse al servicio web de actualización de dispositivos y obtener actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="abe57-111">Enabling external devices to connect to Device Update web service and obtain updates.</span></span>

  - <span data-ttu-id="abe57-112">Habilitación de aplicaciones móviles para que detecten y usen las direcciones URL de movilidad (MCX) automáticamente desde Internet.</span><span class="sxs-lookup"><span data-stu-id="abe57-112">Enabling mobile applications to automatically discover and use the mobility (Mcx) URLs from the Internet.</span></span>

  - <span data-ttu-id="abe57-113">Habilitar el cliente de Lync 2013, la aplicación de la tienda Windows de Lync y el cliente móvil de Lync 2013 para localizar las direcciones URL de detección de Lync (detección automática) y usar la API Web de comunicaciones unificadas (UCWA).</span><span class="sxs-lookup"><span data-stu-id="abe57-113">Enabling the Lync 2013 client, Lync Windows Store app and Lync 2013 Mobile client to locate the Lync Discover (autodiscover) URLs and use Unified Communications Web API (UCWA).</span></span>

<span data-ttu-id="abe57-114">Se recomienda configurar el proxy inverso HTTP para publicar todos los servicios web en todos los grupos.</span><span class="sxs-lookup"><span data-stu-id="abe57-114">We recommend that you configure your HTTP reverse proxy to publish all Web Services in all pools.</span></span> <span data-ttu-id="abe57-115">Publishing https://ExternalFQDN\* /publica todos los directorios virtuales de IIS para un grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="abe57-115">Publishing https:// ExternalFQDN/\* publishes all IIS virtual directories for a pool.</span></span> <span data-ttu-id="abe57-116">Se necesita una regla de publicación para cada servidor Standard Edition, cada grupo de servidores front-end o cada director o grupo de directores de la organización.</span><span class="sxs-lookup"><span data-stu-id="abe57-116">You need one publishing rule for each Standard Edition server, Front End pool, or Director or Director pool in your organization.</span></span>

<span data-ttu-id="abe57-117">Además, deberá publicar las direcciones URL sencillas.</span><span class="sxs-lookup"><span data-stu-id="abe57-117">In addition, you need to publish the simple URLs.</span></span> <span data-ttu-id="abe57-118">Si la organización tiene un director o un grupo de directores, el proxy inverso HTTP escucha las solicitudes de HTTP/HTTPS para direcciones URL sencillas y las envía al directorio virtual de servicios web externos del director o grupo de directores.</span><span class="sxs-lookup"><span data-stu-id="abe57-118">If the organization has a Director or Director pool, the HTTP reverse proxy listens for HTTP/HTTPS requests to the simple URLs and proxies them to the external Web Services virtual directory on the Director or Director pool.</span></span> <span data-ttu-id="abe57-119">Si no se ha implementado ningún director, deberá designar un grupo para administrar las solicitudes para las URL sencillas.</span><span class="sxs-lookup"><span data-stu-id="abe57-119">If you have not deployed a Director, you need to designate one pool to handle requests to the simple URLs.</span></span> <span data-ttu-id="abe57-120">(Si este no es el grupo principal del usuario, las redireccionará a los servicios web del grupo principal del usuario).</span><span class="sxs-lookup"><span data-stu-id="abe57-120">(If this is not the user’s home pool, it will redirect them onward to the Web Services on the user’s home pool).</span></span> <span data-ttu-id="abe57-121">Las URL sencillas pueden administrarse mediante una regla de publicación web dedicada, o bien puede agregarlas a los nombres públicos de la regla de publicación web para el director.</span><span class="sxs-lookup"><span data-stu-id="abe57-121">The simple URLs can be handled by a dedicated web publishing rule, or you can add it to the public names of the web publishing rule for the Director.</span></span> <span data-ttu-id="abe57-122">También tiene que publicar la dirección URL externa del servicio Detección automática.</span><span class="sxs-lookup"><span data-stu-id="abe57-122">You also need to publish the external Autodiscover Service URL.</span></span>

<span data-ttu-id="abe57-123">Puede usar Microsoft Forefront Threat Management Gateway 2010, Microsoft Internet Security and Acceleration (ISA) Server 2006 SP1, o Internet Information Server 7,0, 7,5 o 8,0 con enrutamiento de solicitud de aplicación (IIS ARR) como proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="abe57-123">You can use Microsoft Forefront Threat Management Gateway 2010, Microsoft Internet Security and Acceleration (ISA) Server 2006 SP1, or Internet Information Server 7.0, 7.5 or 8.0 with Application Request Routing (IIS ARR) as a reverse proxy.</span></span> <span data-ttu-id="abe57-124">Los pasos detallados de esta sección describen cómo configurar Forefront Threat Management Gateway 2010 y los pasos para configurar ISA Server 2006 son casi idénticos.</span><span class="sxs-lookup"><span data-stu-id="abe57-124">The detailed steps in this section describe how to configure Forefront Threat Management Gateway 2010, and the steps for configuring ISA Server 2006 are almost identical.</span></span> <span data-ttu-id="abe57-125">También se proporciona una guía para IIS ARR.</span><span class="sxs-lookup"><span data-stu-id="abe57-125">Guidance is also provided for IIS ARR.</span></span> <span data-ttu-id="abe57-126">Si usa un proxy inverso diferente, consulte la documentación de ese producto y asigne los requisitos definidos aquí a las características asociadas de otros proxy inversos.</span><span class="sxs-lookup"><span data-stu-id="abe57-126">If you are using a different reverse proxy, consult the documentation for that product and map the requirements defined here to the associated features in other reverse proxies.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="abe57-127">El enrutamiento de solicitudes de aplicaciones de Internet Information Server (IIS ARR) es una opción completamente probada y admitida para implementar un proxy inverso para Lync Server 2010 y Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="abe57-127">Internet Information Server Application Request Routing (IIS ARR) is a fully tested and supported option for implementing a reverse proxy for Lync Server 2010 and Lync Server 2013.</span></span> <span data-ttu-id="abe57-128">En noviembre de 2012, Microsoft ha cesado las ventas de licencias de ForeFront Threat Management Gateway 2010 o TMG.</span><span class="sxs-lookup"><span data-stu-id="abe57-128">In November, 2012, Microsoft ceased license sales of ForeFront Threat Management Gateway 2010, or TMG.</span></span> <span data-ttu-id="abe57-129">TMG sigue siendo un producto totalmente compatible y sigue disponible para la venta en los dispositivos que venden otros fabricantes.</span><span class="sxs-lookup"><span data-stu-id="abe57-129">TMG is still a fully supported product, and is still available for sale on appliances sold by third parties.</span></span> <span data-ttu-id="abe57-130">Además, muchos equilibradores de carga de hardware y firewalls de terceros proporcionan compatibilidad con proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="abe57-130">Also, many third party hardware load balancers and firewalls provide reverse proxy support.</span></span> <span data-ttu-id="abe57-131">Para los equilibradores de carga de hardware y los firewalls que proporcionan características de proxy inverso, consulte al proveedor para obtener instrucciones específicas sobre cómo configurar su producto para proporcionar compatibilidad con un proxy inverso para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="abe57-131">For hardware load balancers and firewalls that provide reverse proxy features, check with your vendor for specific instructions on how to configure their product to provide reverse proxy support for Lync Server.</span></span> <span data-ttu-id="abe57-132">También puede ver a Microsoft otros fabricantes que han enviado documentación sobre su producto.</span><span class="sxs-lookup"><span data-stu-id="abe57-132">You can also view third parties that have submitted documentation for their product to Microsoft.</span></span> <span data-ttu-id="abe57-133">El soporte técnico es proporcionado por el tercero para su soluci? a.</span><span class="sxs-lookup"><span data-stu-id="abe57-133">Support is provided by the third party for their solution.</span></span> <span data-ttu-id="abe57-134">Para ver los terceros que están activos en la oferta de soluciones, consulte <A href="https://go.microsoft.com/fwlink/?linkid=268730">infraestructura apta para Microsoft Lync</A>.</span><span class="sxs-lookup"><span data-stu-id="abe57-134">To see third parties that are active in providing solutions, see <A href="https://go.microsoft.com/fwlink/?linkid=268730">Infrastructure qualified for Microsoft Lync</A>.</span></span>



</div>

<span data-ttu-id="abe57-135">Los siguientes temas y procedimientos usan Forefront Threat Management Gateway 2010 e IIS ARR como base para los procedimientos de implementación y configuración.</span><span class="sxs-lookup"><span data-stu-id="abe57-135">The following topics and procedures use Forefront Threat Management Gateway 2010 and IIS ARR as the basis for the deployment and configuration procedures.</span></span>

  - [<span data-ttu-id="abe57-136">Configurar FQDN de granja de servidores web para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="abe57-136">Configure web farm FQDNs for Lync Server 2013</span></span>](lync-server-2013-configure-web-farm-fqdns.md)

  - [<span data-ttu-id="abe57-137">Configurar adaptadores de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="abe57-137">Configure network adapters in Lync Server 2013</span></span>](lync-server-2013-configure-network-adapters.md)

  - [<span data-ttu-id="abe57-138">Solicitar y configurar un certificado para el proxy HTTP inverso en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="abe57-138">Request and configure a certificate for your reverse HTTP proxy in Lync Server 2013</span></span>](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md)

  - [<span data-ttu-id="abe57-139">Configurar las reglas de publicación web para un solo grupo de servidores interno en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="abe57-139">Configure web publishing rules for a single internal pool in Lync Server 2013</span></span>](lync-server-2013-configure-web-publishing-rules-for-a-single-internal-pool.md)

  - [<span data-ttu-id="abe57-140">Comprobar o configurar la autenticación y la certificación en directorios virtuales de IIS en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="abe57-140">Verify or configure authentication and certification on IIS virtual directories in Lync Server 2013</span></span>](lync-server-2013-verify-or-configure-authentication-and-certification-on-iis-virtual-directories.md)

  - [<span data-ttu-id="abe57-141">Crear registros DNS para servidores de proxy inverso en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="abe57-141">Create DNS records for reverse proxy servers in Lync Server 2013</span></span>](lync-server-2013-create-dns-records-for-reverse-proxy-servers.md)

  - [<span data-ttu-id="abe57-142">Comprobar el acceso a través del proxy inverso en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="abe57-142">Verify access through your reverse proxy in Lync Server 2013</span></span>](lync-server-2013-verify-access-through-your-reverse-proxy.md)

<div>

## <a name="before-you-begin"></a><span data-ttu-id="abe57-143">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="abe57-143">Before You Begin</span></span>

<span data-ttu-id="abe57-144">Para implementar correctamente Forefront Threat Management Gateway 2010 como su proxy inverso, debe instalar y configurar un servidor, usando los requisitos previos y los requisitos de hardware definidos en la documentación de Forefront Threat Management Gateway 2010.</span><span class="sxs-lookup"><span data-stu-id="abe57-144">To successfully deploy Forefront Threat Management Gateway 2010 as your reverse proxy, you need to setup and configure a server, using the prerequisites and hardware requirements defined in the Forefront Threat Management Gateway 2010 documentation.</span></span> <span data-ttu-id="abe57-145">Consulte el siguiente tema establecido para configurar correctamente el hardware e instalar Forefront Threat Management Gateway 2010 en el servidor antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="abe57-145">See the following topic set to properly configure the hardware and to install Forefront Threat Management Gateway 2010 on the server before proceeding.</span></span>

  - <span></span>  
    [<span data-ttu-id="abe57-146">Forefront Threat Management Gateway (TMG) 2010</span><span class="sxs-lookup"><span data-stu-id="abe57-146">Forefront Threat Management Gateway (TMG) 2010</span></span>](https://go.microsoft.com/fwlink/?linkid=291292)

  - <span></span>  
    [<span data-ttu-id="abe57-147">Recomendaciones de hardware de Forefront TMG 2010</span><span class="sxs-lookup"><span data-stu-id="abe57-147">Forefront TMG 2010 hardware recommendations</span></span>](https://go.microsoft.com/fwlink/?linkid=291293)

<span data-ttu-id="abe57-148">Para implementar correctamente IIS ARR como su proxy inverso, revise los siguientes temas para configurar el hardware y el software necesario como requisito previo.</span><span class="sxs-lookup"><span data-stu-id="abe57-148">To successfully deploy IIS ARR as your reverse proxy, review the following topics to configure the hardware and the prerequisite software.</span></span>

  - <span></span>  
    <span data-ttu-id="abe57-149">Para instalar IIS en Windows Server 2008 o Windows Server 2008 R2, vea [instalación de IIS 7 en Windows server 2008 o Windows server 2008 R2](https://go.microsoft.com/fwlink/?linkid=291296)</span><span class="sxs-lookup"><span data-stu-id="abe57-149">To install IIS on Windows Server 2008 or Windows Server 2008 R2, see [Installing IIS 7 on Windows Server 2008 or Windows Server 2008 R2](https://go.microsoft.com/fwlink/?linkid=291296)</span></span>

  - <span></span>  
    <span data-ttu-id="abe57-150">Para instalar IIS en Windows Server 2012, vea [instalar IIS 8 en Windows server 2012](https://go.microsoft.com/fwlink/?linkid=291297)</span><span class="sxs-lookup"><span data-stu-id="abe57-150">To install IIS on Windows Server 2012, see [Installing IIS 8 on Windows Server 2012](https://go.microsoft.com/fwlink/?linkid=291297)</span></span>

  - <span></span>  
    <span data-ttu-id="abe57-151">Para instalar IIS en Windows Server 2012 R2, vea [Installing iis 8,5 on Windows server 2012 R2](https://go.microsoft.com/fwlink/?linkid=330687)</span><span class="sxs-lookup"><span data-stu-id="abe57-151">To install IIS on Windows Server 2012 R2, see [Installing IIS 8.5 on Windows Server 2012 R2](https://go.microsoft.com/fwlink/?linkid=330687)</span></span>

  - <span></span>  
    <span data-ttu-id="abe57-152">Para descargar la extensión de enrutamiento de solicitudes de aplicación para IIS, siga las instrucciones que se indican en [descarga de enrutamiento de solicitud de aplicación v 2.5](https://go.microsoft.com/fwlink/?linkid=291298)</span><span class="sxs-lookup"><span data-stu-id="abe57-152">To download the Application Request Routing extension for IIS, follow the instructions at [Application Request Routing v2.5 Download](https://go.microsoft.com/fwlink/?linkid=291298)</span></span>

  - <span></span>  
    <span data-ttu-id="abe57-153">Para instalar ARR, siga las instrucciones de [install Application request Routing Routing version 2](https://go.microsoft.com/fwlink/?linkid=291299) .</span><span class="sxs-lookup"><span data-stu-id="abe57-153">To install ARR, for the instructions at [Install Application Request Routing Version 2](https://go.microsoft.com/fwlink/?linkid=291299)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="abe57-154">Las instrucciones que se han publicado actualmente son para ARR 2,0.</span><span class="sxs-lookup"><span data-stu-id="abe57-154">The instructions currently posted are for ARR 2.0.</span></span> <span data-ttu-id="abe57-155">Para la instalación de la extensión, no hay ninguna diferencia entre las dos versiones.</span><span class="sxs-lookup"><span data-stu-id="abe57-155">For installation of the extension, there is no difference between the two versions.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

