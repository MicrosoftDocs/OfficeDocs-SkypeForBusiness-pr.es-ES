---
title: 'Lync Server 2013: escenarios de proxy inverso'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scenarios for reverse proxy
ms:assetid: 13108f59-a660-4ff1-8404-079d1cb646f2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204691(v=OCS.15)
ms:contentKeyID: 48183468
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be05e3b63b73daeecbd4c0b34d9a893a8e27fa83
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42047953"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scenarios-for-reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="f67fe-102">Escenarios de proxy inverso en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f67fe-102">Scenarios for reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f67fe-103">_**Última modificación del tema:** 2013-01-21_</span><span class="sxs-lookup"><span data-stu-id="f67fe-103">_**Topic Last Modified:** 2013-01-21_</span></span>

<span data-ttu-id="f67fe-104">Los proxies inversos son necesarios en Lync Server 2013 para permitir el acceso a servicios y recursos como la reunión y las direcciones URL sencillas de acceso telefónico, la libreta de direcciones, el contenido de la reunión, la expansión de la lista de distribución, los servicios de movilidad y otros.</span><span class="sxs-lookup"><span data-stu-id="f67fe-104">Reverse proxies are required in Lync Server 2013 for providing access to services and resources such as the meeting and dial-in Simple URLs, address book, meeting content, distribution list expansion, mobility services, and others.</span></span> <span data-ttu-id="f67fe-105">El escenario típico de proxy inverso en Lync Server 2013 es permitir que los clientes externos (por ejemplo, el cliente de escritorio o el cliente de Lync Web App) tengan acceso al director o a los servicios web externos del servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="f67fe-105">The typical reverse proxy scenario in Lync Server 2013 is to allow external clients (for example, the desktop client or Lync Web App client) access to the Director or Front End Server external Web Services.</span></span>

<span data-ttu-id="f67fe-106">**Proxy inverso y servicios web externos**</span><span class="sxs-lookup"><span data-stu-id="f67fe-106">**Reverse proxy and external web services**</span></span>

<span data-ttu-id="f67fe-107">![13142405-d5c9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")</span><span class="sxs-lookup"><span data-stu-id="f67fe-107">![13142405-d5c9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")</span></span>

<span data-ttu-id="f67fe-108">Durante la fase de planeación, defina los requisitos para el proxy inverso en una implementación de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f67fe-108">During the planning phase, you define the requirements for the reverse proxy in a Lync Server 2013 deployment.</span></span> <span data-ttu-id="f67fe-109">El proxy inverso permite el acceso a características para los siguientes clientes externos:</span><span class="sxs-lookup"><span data-stu-id="f67fe-109">The reverse proxy enables access to features for the following external clients:</span></span>

  - <span data-ttu-id="f67fe-110">Cliente de escritorio de Microsoft Lync 2013</span><span class="sxs-lookup"><span data-stu-id="f67fe-110">Microsoft Lync 2013 desktop client</span></span>

  - <span data-ttu-id="f67fe-111">Microsoft Lync Web App</span><span class="sxs-lookup"><span data-stu-id="f67fe-111">Microsoft Lync Web App</span></span>

  - <span data-ttu-id="f67fe-112">Microsoft Lync Mobile</span><span class="sxs-lookup"><span data-stu-id="f67fe-112">Microsoft Lync Mobile</span></span>

  - <span data-ttu-id="f67fe-113">Aplicación Lync de la tienda Windows</span><span class="sxs-lookup"><span data-stu-id="f67fe-113">Lync Windows Store app</span></span>

<span data-ttu-id="f67fe-114">Al planear la implementación de Lync Server 2013, debe asignar los requisitos reales para Lync Server 2013 a las características de proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="f67fe-114">When planning your Lync Server 2013 deployment, you map the actual requirements for Lync Server 2013 to the reverse proxy features.</span></span>

1.  <span data-ttu-id="f67fe-115">Los clientes externos se conectarán al proxy inverso en el puerto TCP 443 y usarán la capa de sockets seguros (SSL) o la seguridad de la capa de transporte (TLS).</span><span class="sxs-lookup"><span data-stu-id="f67fe-115">External clients will connect to the reverse proxy on port TCP 443 and will use secure socket layer (SSL) or transport layer security (TLS).</span></span> <span data-ttu-id="f67fe-116">Los clientes móviles de Microsoft Lync pueden conectarse en el puerto TCP 80, pero solo cuando se realiza la conexión inicial a los servicios de detección de Lync, el administrador ha configurado los registros CNAME (o alias) del sistema de nombres de dominio (DNS) adecuados y acepta que este no se cifrará la comunicación.</span><span class="sxs-lookup"><span data-stu-id="f67fe-116">Microsoft Lync Mobile clients can connect on port TCP 80, but only when performing the initial connection to the Lync discover services and the administrator has configured the proper domain name system (DNS) CNAME (or alias) records, and accepts that this communication will not be encrypted.</span></span>

2.  <span data-ttu-id="f67fe-117">Lync Server 2013 servicios web externos (implementados en el servidor front-end o el director) esperan una conexión de un proxy inverso en el puerto TCP 4443 y espera que la conexión sea SSL/TLS.</span><span class="sxs-lookup"><span data-stu-id="f67fe-117">Lync Server 2013 external web services (deployed on the Front End Server and/or the Director) expect a connection from a reverse proxy on port TCP 4443, and it expects that the connection will be SSL/TLS.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="f67fe-118">Los puertos de escucha predeterminados sugeridos para los servicios web externos son TCP 8080 para tráfico HTTP y TCP 4443 para el tráfico HTTPS.</span><span class="sxs-lookup"><span data-stu-id="f67fe-118">The suggested default listening ports for the external web services are TCP 8080 for HTTP traffic, and TCP 4443 for HTTPS traffic.</span></span> <span data-ttu-id="f67fe-119">El generador de topologías proporciona una oportunidad para reemplazar los valores predeterminados y definir sus propios puertos de escucha para los servicios web externos.</span><span class="sxs-lookup"><span data-stu-id="f67fe-119">Topology Builder provides an opportunity to override the defaults and define your own listening ports for the external web services.</span></span> <span data-ttu-id="f67fe-120">Es importante tener en cuenta que el proxy inverso se comunica con los servicios web externos y que los clientes externos se comunican con el proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="f67fe-120">It’s important to note that the reverse proxy communicates with the external web services, and the external clients communicate with the reverse proxy.</span></span> <span data-ttu-id="f67fe-121">El cliente externo se comunica con el proxy inverso en el puerto TCP 443, pero puede redefinir el puerto en el que se comunica el proxy inverso con los servicios web externos.</span><span class="sxs-lookup"><span data-stu-id="f67fe-121">The external client communicates with the reverse proxy on port TCP 443, but you can redefine what port the reverse proxy communicates with the external web services on.</span></span> <span data-ttu-id="f67fe-122">Las opciones del generador de topologías para invalidar los puertos de escucha predeterminados para los servicios web le permiten resolver los conflictos de puertos de escucha que pueden surgir en la infraestructura.</span><span class="sxs-lookup"><span data-stu-id="f67fe-122">The options in Topology Builder to override the default listening ports for the web services allows you to resolve listening port conflicts that may arise in your infrastructure.</span></span>

    
    </div>

3.  <span data-ttu-id="f67fe-123">Lync Server 2013 servicios web externos esperan un encabezado host sin modificar del cliente para identificar qué servicio y el directorio del servidor web está intentando usar el cliente.</span><span class="sxs-lookup"><span data-stu-id="f67fe-123">Lync Server 2013 external web services expect an unmodified Host Header from the client to identify what service and web server directory the client is attempting to use.</span></span> <span data-ttu-id="f67fe-124">Las solicitudes deben aparecer como si proceden del proxy inverso</span><span class="sxs-lookup"><span data-stu-id="f67fe-124">Requests should appear as if they came from the reverse proxy</span></span>

4.  <span data-ttu-id="f67fe-125">Los servicios web externos usan directorios virtuales de servidor Web (vDir) definidos que proporcionan los servicios ofrecidos a los clientes.</span><span class="sxs-lookup"><span data-stu-id="f67fe-125">The external web services use defined web server virtual directories (vDir) that provide the services offered to clients.</span></span> <span data-ttu-id="f67fe-126">Los servicios Web específicos que pueden identificarse externamente son:</span><span class="sxs-lookup"><span data-stu-id="f67fe-126">Specific externally identifiable web services are:</span></span>
    
      - <span data-ttu-id="f67fe-127">El vDir "reunirse" para las reuniones de conferencia Web</span><span class="sxs-lookup"><span data-stu-id="f67fe-127">The “Meet” vDir for web conference meetings</span></span>
    
      - <span data-ttu-id="f67fe-128">El vDir de "marcado" para el acceso telefónico y la conferencia telefónica</span><span class="sxs-lookup"><span data-stu-id="f67fe-128">The “Dialin” vDir for phone access and phone conferencing</span></span>
    
      - <span data-ttu-id="f67fe-129">El vDir "detección automática" de la aplicación de la tienda Windows de Lync, Lync Mobile y el cliente de escritorio Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="f67fe-129">The “Autodiscover” vDir for Lync Windows Store app, Lync Mobile, and the desktop client Lync 2013.</span></span> <span data-ttu-id="f67fe-130">La detección automática en Lync Server 2013 se conoce con el nombre DNS "lyncdiscover"</span><span class="sxs-lookup"><span data-stu-id="f67fe-130">Autodiscover in Lync Server 2013 is known by the DNS name “lyncdiscover”</span></span>
    
      - <span data-ttu-id="f67fe-131">El cliente externo tiene acceso a los servicios no definidos por llamadas directas a los servicios web externos.</span><span class="sxs-lookup"><span data-stu-id="f67fe-131">Services not defined are accessed by the external client by direct calls to the external web services.</span></span> <span data-ttu-id="f67fe-132">Por ejemplo, las llamadas directas a los servicios web externos y los vDirs asociados tienen acceso a la expansión del grupo de distribución (DLX) y al servicio de libreta de direcciones (ABS).</span><span class="sxs-lookup"><span data-stu-id="f67fe-132">For example, distribution group expansion (DLX) and the address book service (ABS) are accessed by direct calls to the external web services and associated vDirs.</span></span> <span data-ttu-id="f67fe-133">El cliente conoce la ruta de acceso real al vDir y crea un localizador uniforme de registros (URL) en función de esta información.</span><span class="sxs-lookup"><span data-stu-id="f67fe-133">The client knows the actual path to the vDir and constructs a uniform record locator (URL) based on this information.</span></span> <span data-ttu-id="f67fe-134">El cliente tendría acceso al servicio de libreta de direcciones mediante una dirección URL similar a`https://externalweb.contoso.com/abs/handler`</span><span class="sxs-lookup"><span data-stu-id="f67fe-134">The client would access the address book service using a URL similar to `https://externalweb.contoso.com/abs/handler`</span></span>
    
      - <span data-ttu-id="f67fe-135">Office Web Apps Server cuando se definen y configuran conferencias como parte de la topología de Lync Server</span><span class="sxs-lookup"><span data-stu-id="f67fe-135">The Office Web Apps Server when conferencing is defined and configured as part of the Lync Server topology</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="f67fe-136">El servidor de Office Web Apps es un servidor de roles independiente y no está configurado como parte de los servicios web externos.</span><span class="sxs-lookup"><span data-stu-id="f67fe-136">The Office Web Apps Server is a separate role server and is not configured as part of the external web services.</span></span> <span data-ttu-id="f67fe-137">Este servidor se publica por separado para el acceso de clientes.</span><span class="sxs-lookup"><span data-stu-id="f67fe-137">This server is separately published for client access.</span></span>

        
        </div>

5.  <span data-ttu-id="f67fe-138">Definir el puente SSL para cada servicio.</span><span class="sxs-lookup"><span data-stu-id="f67fe-138">Define SSL bridging for each service.</span></span> <span data-ttu-id="f67fe-139">El puerto externo TCP 443 está asignado al puerto de servicios Web externo TCP 4443.</span><span class="sxs-lookup"><span data-stu-id="f67fe-139">The external port TCP 443 is mapped to the external web services port of TCP 4443.</span></span> <span data-ttu-id="f67fe-140">Para HTTP sin cifrar, el puerto TCP 80 está asignado al puerto de servicios Web externo TCP 8080</span><span class="sxs-lookup"><span data-stu-id="f67fe-140">For unencrypted HTTP, port TCP 80 is mapped to the external web services port TCP 8080</span></span>

6.  <span data-ttu-id="f67fe-141">Planeación de escuchas de proxy inverso para publicar recursos de servidor Web</span><span class="sxs-lookup"><span data-stu-id="f67fe-141">Plan for reverse proxy listeners to publish web server resources</span></span>

7.  <span data-ttu-id="f67fe-142">Solicite y configure el certificado para el proxy inverso en función de los servicios que se ofrecerán.</span><span class="sxs-lookup"><span data-stu-id="f67fe-142">Request and configure the certificate for the reverse proxy based on the services that will be offered.</span></span> <span data-ttu-id="f67fe-143">Si se configura con los nombres alternativos de sujeto correctos, todos los agentes de escucha configurados en el servidor de proxy inverso pueden compartir este certificado.</span><span class="sxs-lookup"><span data-stu-id="f67fe-143">If configured with the correct subject alternative names, this certificate can be shared by all configured listeners on the reverse proxy server</span></span>

<span data-ttu-id="f67fe-144">Recursos disponibles para planear la implementación de su proxy inverso:</span><span class="sxs-lookup"><span data-stu-id="f67fe-144">Resources available for planning your reverse proxy deployment:</span></span>

  - [<span data-ttu-id="f67fe-145">Recopilación de datos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f67fe-145">Data collection in Lync Server 2013</span></span>](lync-server-2013-data-collection.md)

  - [<span data-ttu-id="f67fe-146">Resumen de certificado-proxy inverso en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f67fe-146">Certificate summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-reverse-proxy.md)

  - [<span data-ttu-id="f67fe-147">Resumen de Puerto-proxy inverso en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f67fe-147">Port summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-port-summary-reverse-proxy.md)

  - [<span data-ttu-id="f67fe-148">Resumen de DNS-proxy inverso en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f67fe-148">DNS summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-dns-summary-reverse-proxy.md)

</div>

<span> </span>

</div>

</div>

</div>

