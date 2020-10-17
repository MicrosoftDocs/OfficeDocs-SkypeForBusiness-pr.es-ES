---
title: 'Lync Server 2013: diseño de la topología mediante la herramienta de planeación'
description: 'Lync Server 2013: diseño de la topología mediante la herramienta de planeación.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Designing the topology by using the Planning Tool
ms:assetid: 2a352f62-c5cb-4ef1-9aa9-7f0c1ab47455
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558631(v=OCS.15)
ms:contentKeyID: 51541454
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fcc10d09d7b8b815e2b4924d06c10de23c14236b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542596"
---
# <a name="designing-the-topology-for-lync-server-2013-by-using-the-planning-tool"></a><span data-ttu-id="127c5-103">Diseño de la topología para Lync Server 2013 mediante la herramienta de planeación</span><span class="sxs-lookup"><span data-stu-id="127c5-103">Designing the topology for Lync Server 2013 by using the Planning Tool</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="127c5-104">_**Última modificación del tema:** 2013-03-04_</span><span class="sxs-lookup"><span data-stu-id="127c5-104">_**Topic Last Modified:** 2013-03-04_</span></span>

<span data-ttu-id="127c5-105">La herramienta de planeación de Microsoft Lync Server 2013 es una herramienta guiada por un asistente y como una entrevista que plantea preguntas sobre la topología de Lync Server 2013 que se está diseñando.</span><span class="sxs-lookup"><span data-stu-id="127c5-105">The Microsoft Lync Server 2013, Planning Tool is a wizard driven, interview-like tool that asks questions about the Lync Server 2013 topology that you are designing.</span></span> <span data-ttu-id="127c5-106">La herramienta de planeación usa la información suministrada, junto con las prácticas recomendadas para el diseño y la capacidad de la topología, para presentar una topología recomendada en función de las respuestas proporcionadas.</span><span class="sxs-lookup"><span data-stu-id="127c5-106">The Planning Tool uses the information supplied, coupled with preferred practices for topology design and capacity, to present a recommended topology based on the answers supplied.</span></span> <span data-ttu-id="127c5-107">Puede descargar la herramienta de planeación desde el centro de descargas de Microsoft ( [https://go.microsoft.com/fwlink/?LinkID=282725](https://go.microsoft.com/fwlink/?linkid=282725) ).</span><span class="sxs-lookup"><span data-stu-id="127c5-107">You can download the Planning Tool from the Microsoft Downloads Center ([https://go.microsoft.com/fwlink/?LinkID=282725](https://go.microsoft.com/fwlink/?linkid=282725)).</span></span>

<span data-ttu-id="127c5-108">En última instancia, el objetivo de la herramienta de planeación es facilitar la complejidad del diseño de una topología completa de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="127c5-108">Ultimately, the goal of the Planning Tool is to ease the potential complexity of designing a complete Lync Server 2013 topology.</span></span> <span data-ttu-id="127c5-109">De igual modo, esta herramienta proporciona referencias contextuales a la documentación de planeación e implementación de la propia herramienta, siempre y cuando haya una conexión a Internet disponible que permita conectarse al sitio web de Microsoft TechNet.</span><span class="sxs-lookup"><span data-stu-id="127c5-109">The tool also provides contextual references to planning and deployment documentation inside the tool, provided that an Internet connection is available to connect to the Microsoft TechNet website.</span></span>

<span data-ttu-id="127c5-110">Después de personalizar la topología con las direcciones TCP/IP de la infraestructura y los nombres de dominio completos (FQDN), la herramienta de planeación pone a disposición una serie de informes que cubren el nombre del sistema de nombres de dominio (DNS), las reglas de firewall, los certificados y mucho más.</span><span class="sxs-lookup"><span data-stu-id="127c5-110">After customizing the topology with the infrastructure’s TCP/IP addresses and fully qualified domain names (FQDNs), the Planning Tool makes available a series of reports that cover Domain Name System (DNS) naming, firewall rules, certificates, and more.</span></span>

<span data-ttu-id="127c5-111">La herramienta de planeación también ofrece la posibilidad de exportar información en dos formatos:</span><span class="sxs-lookup"><span data-stu-id="127c5-111">The Planning Tool also provides the ability to export information in two formats:</span></span>

  - <span data-ttu-id="127c5-112">Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="127c5-112">Microsoft Excel</span></span>

  - <span data-ttu-id="127c5-113">Microsoft Visio</span><span class="sxs-lookup"><span data-stu-id="127c5-113">Microsoft Visio</span></span>

<span data-ttu-id="127c5-114">Los temas siguientes presentan y detallan la herramienta de planeación.</span><span class="sxs-lookup"><span data-stu-id="127c5-114">The following topics introduce and detail the Planning Tool.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="127c5-115">En esta sección</span><span class="sxs-lookup"><span data-stu-id="127c5-115">In This Section</span></span>

  - [<span data-ttu-id="127c5-116">Instalar la herramienta de planeación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="127c5-116">Installing the Planning Tool in Lync Server 2013</span></span>](lync-server-2013-installing-the-planning-tool.md)

  - [<span data-ttu-id="127c5-117">Instalación de software opcional en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="127c5-117">Installing optional software in Lync Server 2013</span></span>](lync-server-2013-installing-optional-software.md)

  - [<span data-ttu-id="127c5-118">Navegación por la herramienta de planeación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="127c5-118">Navigating the Planning Tool in Lync Server 2013</span></span>](lync-server-2013-navigating-the-planning-tool.md)

  - [<span data-ttu-id="127c5-119">Crear el diseño de topología inicial para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="127c5-119">Create the initial topology design for Lync Server 2013</span></span>](lync-server-2013-create-the-initial-topology-design.md)

  - [<span data-ttu-id="127c5-120">Revisión de los informes del administrador en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="127c5-120">Reviewing the Administrator Reports in Lync Server 2013</span></span>](lync-server-2013-reviewing-the-administrator-reports.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="127c5-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="127c5-121">See Also</span></span>


[<span data-ttu-id="127c5-122">Implementar Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="127c5-122">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)  
[<span data-ttu-id="127c5-123">Planeación de los servidores front-end, la mensajería instantánea y la presencia en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="127c5-123">Planning for Front End Servers, instant messaging, and presence in Lync Server 2013</span></span>](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

