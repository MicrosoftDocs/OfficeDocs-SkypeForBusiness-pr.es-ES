---
title: 'Lync Server 2013: edición del diseño'
description: 'Lync Server 2013: edición del diseño.'
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
ms.openlocfilehash: 20462c1c1813551159e8eeb3b255bd9069e3cce1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570626"
---
# <a name="editing-the-design-in-lync-server-2013"></a><span data-ttu-id="f770a-103">Edición del diseño en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f770a-103">Editing the design in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f770a-104">_**Última modificación del tema:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="f770a-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="f770a-105">Después de completar las preguntas de la entrevista inicial, puede editar el nombre de dominio completo (FQDN) y las direcciones IP del sitio.</span><span class="sxs-lookup"><span data-stu-id="f770a-105">After completing the initial interview questions, you can edit the fully qualified domain name (FQDN) and IP addresses for the site.</span></span> <span data-ttu-id="f770a-106">Para ello, en la página **Topología global**, haga clic con el botón secundario en el sitio que desea editar.</span><span class="sxs-lookup"><span data-stu-id="f770a-106">To do this, on the **Global Topology** page, double-click the site that you want to edit.</span></span>

<span data-ttu-id="f770a-107">La herramienta de planeación muestra la topología del sitio seleccionado.</span><span class="sxs-lookup"><span data-stu-id="f770a-107">The Planning Tool displays the site topology for the selected site.</span></span> <span data-ttu-id="f770a-108">En la parte inferior de la página del sitio hay cuatro pestañas:</span><span class="sxs-lookup"><span data-stu-id="f770a-108">At the bottom of the site page are four tabs:</span></span>

<span data-ttu-id="f770a-109">![Topología de sitio de la herramienta de planeación](images/Gg558608.e6189c20-360a-42bd-ba90-11bdb5b7551b(OCS.15).jpg "Topología de sitio de la herramienta de planeación")</span><span class="sxs-lookup"><span data-stu-id="f770a-109">![Planning Tool Site Topology](images/Gg558608.e6189c20-360a-42bd-ba90-11bdb5b7551b(OCS.15).jpg "Planning Tool Site Topology")</span></span>

  - <span data-ttu-id="f770a-110">Topología del sitio: La página que se muestra actualmente con información general visual de la topología recomendada.</span><span class="sxs-lookup"><span data-stu-id="f770a-110">Site Topology – The currently displayed page with a visual overview of the topology as recommended.</span></span>

  - <span data-ttu-id="f770a-111">Diagrama de red perimetral: la página de diagrama de red perimetral es donde el diseñador realiza la mayor parte del trabajo en la herramienta de planeación.</span><span class="sxs-lookup"><span data-stu-id="f770a-111">Edge Network Diagram – The Edge Network Diagram page is where the designer does most of the work in the Planning Tool.</span></span> <span data-ttu-id="f770a-112">El diagrama muestra la configuración de red para una topología de Lync Server 2013 recomendada, con entradas editables para direcciones IP y FQDN para servidores, grupo y equilibradores de carga de hardware y de sistema de nombres de dominio (DNS).</span><span class="sxs-lookup"><span data-stu-id="f770a-112">The diagram displays the network configuration for a recommended Lync Server 2013 topology, with editable entries for IP addresses and FQDNs for servers, pool, and both hardware and Domain Name System (DNS) load balancers.</span></span>

  - <span data-ttu-id="f770a-113">Informe de administración perimetral: El informe de administración perimetral contiene un total de cuatro informes:</span><span class="sxs-lookup"><span data-stu-id="f770a-113">Edge Admin Report – The Edge Admin Report contains a total of four reports:</span></span>
    
    <span data-ttu-id="f770a-114">![Página Informe de administración perimetral](images/Gg558608.0019cc5e-af39-4cb9-82ce-58f6388242ff(OCS.15).jpg "Página Informe de administración perimetral")</span><span class="sxs-lookup"><span data-stu-id="f770a-114">![Edge Admin Report page](images/Gg558608.0019cc5e-af39-4cb9-82ce-58f6388242ff(OCS.15).jpg "Edge Admin Report page")</span></span>  
    
      - <span data-ttu-id="f770a-115">Informe de resumen: Un informe general de las opciones de configuración de la red perimetral.</span><span class="sxs-lookup"><span data-stu-id="f770a-115">Summary Report – A general report of settings for the Edge network configuration.</span></span> <span data-ttu-id="f770a-116">Si edita los valores de la página de **Diagrama de red perimetral** con los valores de la topología TCP/IP y FQDN de que se usarán en la implementación real, esas direcciones y nombres se representarán aquí.</span><span class="sxs-lookup"><span data-stu-id="f770a-116">If you edit the values on the **Edge Network Diagram** page to the topology TCP/IP and FQDN values of that will be used in the actual deployment, those addresses and names will be represented here.</span></span> <span data-ttu-id="f770a-117">De lo contrario, aparecerá el texto predeterminado.</span><span class="sxs-lookup"><span data-stu-id="f770a-117">Otherwise, the default text will appear.</span></span>
    
      - <span data-ttu-id="f770a-118">Informe de certificado: En el informe de certificado se enumerará el nombre de sujeto y los nombres alternativos de sujeto para los certificados que la topología requiere.</span><span class="sxs-lookup"><span data-stu-id="f770a-118">Certificate Report – The certificate report will list the subject name and subject alternative names for the certificates that are required for the topology.</span></span>
    
      - <span data-ttu-id="f770a-119">Informe de firewall: En el informe de firewall se indicará la información necesaria para configurar firewalls perimetrales en la infraestructura.</span><span class="sxs-lookup"><span data-stu-id="f770a-119">Firewall Report – The firewall report lists information necessary to configure perimeter firewalls in the infrastructure.</span></span> <span data-ttu-id="f770a-120">Esto incluye las direcciones IP (los valores predeterminados o modificados), el rol del servidor, el puerto y la IP de origen, el puerto y la IP de destino, el protocolo de transporte, el protocolo de la aplicación y las notas relevantes.</span><span class="sxs-lookup"><span data-stu-id="f770a-120">This includes the IP addresses (either the default or edited values), server role, source IP and port, destination IP and port, transport protocol, application protocol, and relevant notes.</span></span>
    
      - <span data-ttu-id="f770a-121">Informe de DNS: el informe de DNS muestra la información relevante para las entradas de DNS que debe crear.</span><span class="sxs-lookup"><span data-stu-id="f770a-121">DNS Report – The DNS Report lists relevant information for the DNS entries that you must create.</span></span> <span data-ttu-id="f770a-122">También se incluye el tipo de registro, el FQDN, la dirección IP y los comentarios necesarios para que obtener un funcionamiento correcto.</span><span class="sxs-lookup"><span data-stu-id="f770a-122">The record type, FQDN, IP address, and comments necessary for the proper operation are included.</span></span>

  - <span data-ttu-id="f770a-123">Resumen del sitio: el resumen del sitio presenta una descripción general de las selecciones realizadas al responder a las preguntas de la entrevista inicial o al rellenar los valores en **diseñar sitios**.</span><span class="sxs-lookup"><span data-stu-id="f770a-123">Site Summary – The site summary presents an overview of the selections that you made by either answering the initial interview questions or filling in the values in **Design Sites**.</span></span> <span data-ttu-id="f770a-124">También se presenta información sobre la capacidad.</span><span class="sxs-lookup"><span data-stu-id="f770a-124">Capacity information is also presented.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f770a-125">La información de la página Resumen del sitio está personalizada para cada diseño y puede que no contenga todas las secciones o toda la información que se indica aquí.</span><span class="sxs-lookup"><span data-stu-id="f770a-125">The information on the Site Summary page is customized for each design and may not contain all sections or information detailed here.</span></span>

    
    </div>

<div>

## <a name="see-also"></a><span data-ttu-id="f770a-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f770a-126">See Also</span></span>


[<span data-ttu-id="f770a-127">Editar el diagrama de configuración de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f770a-127">Editing the network configuration diagram in Lync Server 2013</span></span>](lync-server-2013-editing-the-network-configuration-diagram.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

