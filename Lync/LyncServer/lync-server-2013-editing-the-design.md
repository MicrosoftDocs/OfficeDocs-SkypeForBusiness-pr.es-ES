---
title: 'Lync Server 2013: Edición del diseño'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Editing the design
ms:assetid: 08f639ba-0e5f-4ae7-9191-c3d96c25b169
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558608(v=OCS.15)
ms:contentKeyID: 51541445
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfce3bc4242140364005a9a981282ecb90a42d3b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739460"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="editing-the-design-in-lync-server-2013"></a><span data-ttu-id="15a67-102">Edición del diseño en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15a67-102">Editing the design in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="15a67-103">_**Última modificación del tema:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="15a67-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="15a67-p101">Una vez completadas las preguntas iniciales de la entrevista, podrá editar las direcciones IP y el nombre de dominio completo (FQDN) del sitio. Para ello, en la página **Topología global**, haga doble clic en el sitio que desea editar.</span><span class="sxs-lookup"><span data-stu-id="15a67-p101">After completing the initial interview questions, you can edit the fully qualified domain name (FQDN) and IP addresses for the site. To do this, on the **Global Topology** page, double-click the site that you want to edit.</span></span>

<span data-ttu-id="15a67-106">La herramienta de planeación muestra la topología del sitio seleccionado.</span><span class="sxs-lookup"><span data-stu-id="15a67-106">The Planning Tool displays the site topology for the selected site.</span></span> <span data-ttu-id="15a67-107">En la parte inferior de la página del sitio hay cuatro pestañas:</span><span class="sxs-lookup"><span data-stu-id="15a67-107">At the bottom of the site page are four tabs:</span></span>

<span data-ttu-id="15a67-108">![Herramienta de planeación - Topología del sitio](images/Gg558608.e6189c20-360a-42bd-ba90-11bdb5b7551b(OCS.15).jpg "Herramienta de planeación - Topología del sitio")</span><span class="sxs-lookup"><span data-stu-id="15a67-108">![Planning Tool Site Topology](images/Gg558608.e6189c20-360a-42bd-ba90-11bdb5b7551b(OCS.15).jpg "Planning Tool Site Topology")</span></span>

  - <span data-ttu-id="15a67-109">Topología del sitio: la página que se muestra actualmente con información general visual de la topología recomendada.</span><span class="sxs-lookup"><span data-stu-id="15a67-109">Site Topology – The currently displayed page with a visual overview of the topology as recommended.</span></span>

  - <span data-ttu-id="15a67-110">Diagrama de red perimetral: la página de diagrama de red perimetral es el lugar donde el diseñador realiza la mayor parte del trabajo en la herramienta de planeación.</span><span class="sxs-lookup"><span data-stu-id="15a67-110">Edge Network Diagram – The Edge Network Diagram page is where the designer does most of the work in the Planning Tool.</span></span> <span data-ttu-id="15a67-111">El diagrama muestra la configuración de red para una topología recomendada de Lync Server 2013, con entradas editables para direcciones IP y FQDN para servidores, grupos y equilibradores de carga de hardware y de sistema de nombres de dominio (DNS).</span><span class="sxs-lookup"><span data-stu-id="15a67-111">The diagram displays the network configuration for a recommended Lync Server 2013 topology, with editable entries for IP addresses and FQDNs for servers, pool, and both hardware and Domain Name System (DNS) load balancers.</span></span>

  - <span data-ttu-id="15a67-112">Informe de administración de la red perimetral: el informe de administración perimetral contiene un total de cuatro informes:</span><span class="sxs-lookup"><span data-stu-id="15a67-112">Edge Admin Report – The Edge Admin Report contains a total of four reports:</span></span>
    
    <span data-ttu-id="15a67-113">![Página Informe de administración de servidores perimetrales](images/Gg558608.0019cc5e-af39-4cb9-82ce-58f6388242ff(OCS.15).jpg "Página Informe de administración de servidores perimetrales")</span><span class="sxs-lookup"><span data-stu-id="15a67-113">![Edge Admin Report page](images/Gg558608.0019cc5e-af39-4cb9-82ce-58f6388242ff(OCS.15).jpg "Edge Admin Report page")</span></span>  
    
      - <span data-ttu-id="15a67-p104">Informe de resumen: un informe general de los valores de configuración de la red perimetral. Si modifica los valores de la página **Diagrama de red perimetral** por los valores de TCP/IP y FQDN de la topología que se usarán en la implementación real, esas direcciones y nombres se representarán aquí. De lo contrario, se mostrará el texto predeterminado.</span><span class="sxs-lookup"><span data-stu-id="15a67-p104">Summary Report – A general report of settings for the Edge network configuration. If you edit the values on the **Edge Network Diagram** page to the topology TCP/IP and FQDN values of that will be used in the actual deployment, those addresses and names will be represented here. Otherwise, the default text will appear.</span></span>
    
      - <span data-ttu-id="15a67-117">Informe de certificados: en el informe de certificado se enumerará el nombre de sujeto y los nombres alternativos de sujeto para los certificados que la topología requiere.</span><span class="sxs-lookup"><span data-stu-id="15a67-117">Certificate Report – The certificate report will list the subject name and subject alternative names for the certificates that are required for the topology.</span></span>
    
      - <span data-ttu-id="15a67-p105">Informe de firewall: en el informe de firewall se indicará la información necesaria para configurar firewalls perimetrales en la infraestructura. Esto incluye las direcciones IP (ya sea los valores predeterminados o los modificados), el rol de servidor, el puerto y la IP de origen, el puerto y la IP de destino, el protocolo de transporte, el protocolo de aplicación y las notas relevantes.</span><span class="sxs-lookup"><span data-stu-id="15a67-p105">Firewall Report – The firewall report lists information necessary to configure perimeter firewalls in the infrastructure. This includes the IP addresses (either the default or edited values), server role, source IP and port, destination IP and port, transport protocol, application protocol, and relevant notes.</span></span>
    
      - <span data-ttu-id="15a67-p106">Informe de DNS: en el informe de DNS se proporciona información relevante para las entradas DNS que deberá crear. También se incluye el tipo de registro, el FQDN, la dirección IP y los comentarios necesarios para obtener un funcionamiento correcto.</span><span class="sxs-lookup"><span data-stu-id="15a67-p106">DNS Report – The DNS Report lists relevant information for the DNS entries that you must create. The record type, FQDN, IP address, and comments necessary for the proper operation are included.</span></span>

  - <span data-ttu-id="15a67-p107">Resumen del sitio: el resumen del sitio presenta información general sobre las selecciones que ha realizado, ya sea respondiendo a las preguntas de la entrevista inicial o rellenando los valores en **Diseñar sitios**. También se muestra información sobre la capacidad.</span><span class="sxs-lookup"><span data-stu-id="15a67-p107">Site Summary – The site summary presents an overview of the selections that you made by either answering the initial interview questions or filling in the values in **Design Sites**. Capacity information is also presented.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="15a67-124">La información de la página Resumen del sitio está personalizada para cada diseño y puede que no contenga todas las secciones o toda la información que se indica aquí.</span><span class="sxs-lookup"><span data-stu-id="15a67-124">The information on the Site Summary page is customized for each design and may not contain all sections or information detailed here.</span></span>

    
    </div>

<div>

## <a name="see-also"></a><span data-ttu-id="15a67-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="15a67-125">See Also</span></span>


[<span data-ttu-id="15a67-126">Editar el diagrama de configuración de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15a67-126">Editing the network configuration diagram in Lync Server 2013</span></span>](lync-server-2013-editing-the-network-configuration-diagram.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

