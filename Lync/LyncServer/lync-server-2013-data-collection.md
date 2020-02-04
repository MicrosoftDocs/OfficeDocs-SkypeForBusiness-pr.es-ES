---
title: 'Lync Server 2013: Recopilación de datos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Data collection
ms:assetid: e40b03e5-455d-4bbc-831a-c61b1380db53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399008(v=OCS.15)
ms:contentKeyID: 48185722
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7c3d066aff26e06c003a31a58b4771d67f54f34
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728650"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="data-collection-in-lync-server-2013"></a><span data-ttu-id="b9a3e-102">Recopilación de datos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b9a3e-102">Data collection in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b9a3e-103">_**Última modificación del tema:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="b9a3e-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="b9a3e-104">En el software de comunicaciones Microsoft Lync Server 2013, puede ejecutar Microsoft Lync Server 2013, la herramienta de planeación sin documentar las direcciones IP existentes y propuestas y los nombres de dominio completos (FQDN) del servidor perimetral, pero es mucho más difícil de hacer por lo tanto, sin causar errores de configuración.</span><span class="sxs-lookup"><span data-stu-id="b9a3e-104">In Microsoft Lync Server 2013 communications software, you can run the Microsoft Lync Server 2013, Planning Tool without documenting your existing and proposed IP addresses and Edge Server fully qualified domain names (FQDNs), but it is significantly harder to do so without causing configuration errors.</span></span> <span data-ttu-id="b9a3e-105">Por ejemplo, si se necesita la coexistencia durante un período de tiempo, un error común es reutilizar FQDN de una implementación de perimetral existente para la implementación perimetral de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b9a3e-105">For example, if coexistence is required for a period of time, a common mistake is to reuse FQDNs from an existing Edge deployment for your Lync Server 2013 Edge deployment.</span></span> <span data-ttu-id="b9a3e-106">Al anotar las direcciones IP y los FQDN propuestos y existentes en una hoja de cálculo, tabla u otro formulario visual, ayuda a evitar problemas de configuración durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="b9a3e-106">By having the existing and proposed IP addresses and FQDNs written down in a spreadsheet, table, or other visual form, you help prevent setup problems during installation.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="b9a3e-107">Si ha usado versiones anteriores de la herramienta de planeación, es posible que haya usado la herramienta para crear su topología y el documento de topología exportado para usar en el generador de topología para publicar su topología.</span><span class="sxs-lookup"><span data-stu-id="b9a3e-107">If you have used previous versions of the Planning Tool, you may have used the tool to create your topology and the exported the topology document for use in Topology Builder to publish your topology.</span></span> <span data-ttu-id="b9a3e-108">La capacidad para exportar la topología se ha eliminado de la herramienta de planificación.</span><span class="sxs-lookup"><span data-stu-id="b9a3e-108">The ability to export the topology was removed from Planning Tool.</span></span> <span data-ttu-id="b9a3e-109">No se recomienda usar una versión anterior de la herramienta de planeación para crear un documento de topología para Lync Server 2013 y se producirán resultados inesperados.</span><span class="sxs-lookup"><span data-stu-id="b9a3e-109">Using a previous version of the Planning Tool to create a topology document for Lync Server 2013 is strongly discouraged, and will produce unexpected results.</span></span>



</div>

<span data-ttu-id="b9a3e-110">Por lo tanto, el enfoque recomendado es usar la siguiente plantilla de recopilación de datos, que corresponde a la topología perimetral, para recopilar las diversas direcciones IP y FQDN que necesitará para especificar en la herramienta de planeación.</span><span class="sxs-lookup"><span data-stu-id="b9a3e-110">Therefore, the recommended approach is to use the following data collection template, which corresponds to your Edge topology, to gather the various FQDN and IP addresses that you will need to enter into the Planning Tool.</span></span> <span data-ttu-id="b9a3e-111">Al documentar la configuración actual y propuesta, puede poner los valores en el contexto adecuado para su entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="b9a3e-111">By documenting the current and proposed configuration, you can put the values in the proper context for your production environment.</span></span> <span data-ttu-id="b9a3e-112">Y tiene que pensar en cómo se configurará la coexistencia y características, como las direcciones URL simples, los recursos compartidos de archivos y el equilibrio de carga.</span><span class="sxs-lookup"><span data-stu-id="b9a3e-112">And, you are forced to think about how you will configure coexistence and features such as simple URLs, file shares, and load balancing.</span></span>

<span data-ttu-id="b9a3e-113">Para implementar correctamente Microsoft Lync Server 2013, debe comprender la interacción y la dependencia de los componentes individuales.</span><span class="sxs-lookup"><span data-stu-id="b9a3e-113">To successfully deploy Microsoft Lync Server 2013, you need to understand the interaction of and reliance on the individual components.</span></span> <span data-ttu-id="b9a3e-114">Al recopilar datos de la infraestructura de servidor y de la red existente, y aplicar las instrucciones de planeación de estas secciones, puede integrar los componentes de Lync Server 2013 Edge Server en su infraestructura.</span><span class="sxs-lookup"><span data-stu-id="b9a3e-114">By collecting data from your existing network and server infrastructure, and applying the planning guidance in these sections, you can integrate Lync Server 2013 Edge Server components into your infrastructure.</span></span>

<span data-ttu-id="b9a3e-115">En la [elección de una topología en Lync Server 2013](lync-server-2013-choosing-a-topology.md), hay tres arquitecturas principales con dos variantes, para un total de cinco escenarios de implementación posibles.</span><span class="sxs-lookup"><span data-stu-id="b9a3e-115">Introduced in [Choosing a topology in Lync Server 2013](lync-server-2013-choosing-a-topology.md), there are three main architectures with two variations, for a total of five possible deployment scenarios.</span></span> <span data-ttu-id="b9a3e-116">Uno de estos escenarios será el punto de partida para la recopilación de datos.</span><span class="sxs-lookup"><span data-stu-id="b9a3e-116">One of these scenarios will be the starting point for your data collection.</span></span> <span data-ttu-id="b9a3e-117">Las direcciones IP, los nombres de los servidores y los nombres de dominio son ejemplos que coinciden con los diagramas de certificado, Firewall y DNS correspondientes que detallan la información necesaria para una solución de planeación completa.</span><span class="sxs-lookup"><span data-stu-id="b9a3e-117">The IP addresses, server names, and domain names are examples that coincide with the matching certificate, firewall, and DNS diagrams that detail the information required for a complete planning solution.</span></span> <span data-ttu-id="b9a3e-118">Los diagramas y el rellenado de los valores de certificado, DNS y firewall requeridos son especialmente importantes en las comunicaciones entre equipos donde la administración de la entidad de certificación, la configuración de firewall y DNS está administrada por equipos que no son el equipo en el que planifica la implementación.</span><span class="sxs-lookup"><span data-stu-id="b9a3e-118">The diagrams and filling in your required certificate, DNS and firewall values is especially important in cross-team communications where the management of the certification authority, firewall configuration and DNS is managed by teams other than the team that plans the deployment.</span></span> <span data-ttu-id="b9a3e-119">Los diagramas proporcionan información sobre los componentes necesarios que se pueden usar para comunicar estos requisitos para la colaboración entre equipos.</span><span class="sxs-lookup"><span data-stu-id="b9a3e-119">The diagrams provide information on required components that can be used to communicate these requirements for cross-team collaboration.</span></span>

<span data-ttu-id="b9a3e-120">Los diagramas proporcionados son intencionalmente genéricos, pero permiten la recopilación de toda la información pertinente que sería necesaria para la comunicación de los requisitos en un escenario de equipo cruzado en el que la creación y administración de certificados, servidores la implementación y la administración de servidores son gestionadas por distintos grupos.</span><span class="sxs-lookup"><span data-stu-id="b9a3e-120">The provided diagrams are intentionally generic, but allow for the collection of all pertinent data that would be necessary for communication of requirements in a cross team scenario where networking, firewall, certificate creation and management, server deployment, and server management are handled by different groups.</span></span> <span data-ttu-id="b9a3e-121">Disponer de la información necesaria para la configuración de redes, firewalls, puertos y protocolos, certificados y servidores es incalculable cuando la implementación de Lync Server está en curso.</span><span class="sxs-lookup"><span data-stu-id="b9a3e-121">Having the required details for configuration of networking, firewalls, ports and protocols, certificates, and servers is invaluable when the deployment of Lync Server is underway.</span></span>

<span data-ttu-id="b9a3e-122">**Servidor perimetral y grupo Edge**</span><span class="sxs-lookup"><span data-stu-id="b9a3e-122">**Edge Server and Edge pool**</span></span>

<span data-ttu-id="b9a3e-123">![7624717a-ce99-4ae8-a929-2c4d74a2e47d](images/Gg399008.7624717a-ce99-4ae8-a929-2c4d74a2e47d(OCS.15).jpg "7624717a-ce99-4ae8-a929-2c4d74a2e47d")</span><span class="sxs-lookup"><span data-stu-id="b9a3e-123">![7624717a-ce99-4ae8-a929-2c4d74a2e47d](images/Gg399008.7624717a-ce99-4ae8-a929-2c4d74a2e47d(OCS.15).jpg "7624717a-ce99-4ae8-a929-2c4d74a2e47d")</span></span>

<span data-ttu-id="b9a3e-124">**Proxy inverso**</span><span class="sxs-lookup"><span data-stu-id="b9a3e-124">**Reverse Proxy**</span></span>

<span data-ttu-id="b9a3e-125">![cf63fc50-2d11-4334-afc8-2d664ba1b6bb](images/Gg399008.cf63fc50-2d11-4334-afc8-2d664ba1b6bb(OCS.15).jpg "cf63fc50-2d11-4334-afc8-2d664ba1b6bb")</span><span class="sxs-lookup"><span data-stu-id="b9a3e-125">![cf63fc50-2d11-4334-afc8-2d664ba1b6bb](images/Gg399008.cf63fc50-2d11-4334-afc8-2d664ba1b6bb(OCS.15).jpg "cf63fc50-2d11-4334-afc8-2d664ba1b6bb")</span></span>

<span data-ttu-id="b9a3e-126">**Grupo de directores o directores**</span><span class="sxs-lookup"><span data-stu-id="b9a3e-126">**Director or Director pool**</span></span>

<span data-ttu-id="b9a3e-127">![56ba29ff-1309-4d5d-bf5c-35372169e947](images/Gg399008.56ba29ff-1309-4d5d-bf5c-35372169e947(OCS.15).jpg "56ba29ff-1309-4d5d-bf5c-35372169e947")</span><span class="sxs-lookup"><span data-stu-id="b9a3e-127">![56ba29ff-1309-4d5d-bf5c-35372169e947](images/Gg399008.56ba29ff-1309-4d5d-bf5c-35372169e947(OCS.15).jpg "56ba29ff-1309-4d5d-bf5c-35372169e947")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

