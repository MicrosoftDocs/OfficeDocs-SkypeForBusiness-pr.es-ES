---
title: 'Lync Server 2013: Planeación del acceso de usuarios externos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for external user access
ms:assetid: ea098933-eff5-461e-aba3-e7f128784dc2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399048(v=OCS.15)
ms:contentKeyID: 48185903
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 15b4a64c729268efcbdf2bb572c47122d4b41510
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139699"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="d01a5-102">Planeación del acceso de usuarios externos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d01a5-102">Planning for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d01a5-103">_**Última modificación del tema:** 2013-01-19_</span><span class="sxs-lookup"><span data-stu-id="d01a5-103">_**Topic Last Modified:** 2013-01-19_</span></span>

<span data-ttu-id="d01a5-p101">Es probable que una gran parte de la comunicación en su organización implique a gente que se encuentra fuera del firewall: empleados que trabajan de forma temporal o permanente fuera del puesto de trabajo, empleados de organizaciones de socios o clientes, gente que usa los servicios de mensajería instantánea pública y posibles clientes o socios que usted invite a reuniones y presentaciones. En esta documentación, se hace referencia a estas personas como *usuarios externos*.</span><span class="sxs-lookup"><span data-stu-id="d01a5-p101">Communications in most organizations involve services and users that are not inside your internal network. These services and users include employees who are temporarily or permanently offsite, employees of customer or partner organizations, people who use public instant messaging (IM) services, and potential customers, partners and anonymous users whom you invite to meetings and presentations. In this documentation, these people are collectively referred to as *external users*.</span></span>

<span data-ttu-id="d01a5-107">Con Microsoft Lync Server 2013, los usuarios de su organización pueden usar la mensajería instantánea y la presencia para comunicarse con los usuarios externos y pueden participar en conferencias de audio y vídeo (A/V) y conferencias web con los empleados fuera del sitio y otros tipos de usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="d01a5-107">With Microsoft Lync Server 2013, users in your organization can use IM and presence to communicate with external users, and they can participate in audio/video (A/V) conferencing and web conferencing with your offsite employees and other types of external users.</span></span> <span data-ttu-id="d01a5-108">Asimismo, puede permitir el acceso externo desde dispositivos móviles y a través de la Telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="d01a5-108">You can also support external access from mobile devices and over Enterprise Voice.</span></span> <span data-ttu-id="d01a5-109">Los usuarios externos que no son miembros de su organización pueden participar en reuniones de Lync Server 2013, lo que permite a los asistentes anónimos.</span><span class="sxs-lookup"><span data-stu-id="d01a5-109">External users who are not members of your organization can participate in Lync Server 2013 meetings, allowing anonymous attendees.</span></span>

<span data-ttu-id="d01a5-110">Para admitir las comunicaciones en el Firewall de la organización, debe implementar el servidor perimetral de Lync Server 2013 en la red perimetral (también denominada DMZ, zona desmilitarizada y subred filtrada).</span><span class="sxs-lookup"><span data-stu-id="d01a5-110">To support communications across your organization’s firewall, you deploy Lync Server 2013 Edge Server in your perimeter network (also known as DMZ, demilitarized zone, and screened subnet).</span></span> <span data-ttu-id="d01a5-111">El servidor perimetral controla el modo en que los usuarios externos al firewall pueden conectarse a la implementación interna de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d01a5-111">The Edge Server controls how users outside the firewall can connect to your internal Lync Server 2013 deployment.</span></span> <span data-ttu-id="d01a5-112">Además, controla las comunicaciones con usuarios externos que se originan dentro del firewall.</span><span class="sxs-lookup"><span data-stu-id="d01a5-112">It also controls communications with external users that originate within the firewall.</span></span>

<span data-ttu-id="d01a5-113">Según sus requisitos, puede implementar uno o más servidores perimetrales en una o más ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="d01a5-113">Depending on your requirements, you can deploy one or more Edge Servers in one or more locations.</span></span> <span data-ttu-id="d01a5-114">En esta sección se describen los escenarios para el acceso de usuarios externos en Lync Server 2013 y se explica cómo planear la topología perimetral y de proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="d01a5-114">This section describes scenarios for external user access in Lync Server 2013, and it explains how to plan your edge and reverse proxy topology.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d01a5-115">Aunque es necesario disponer de un servidor perimetral que admita la telefonía IP empresarial y el acceso de usuarios externos, esta sección se centra en la compatibilidad con la mensajería instantánea, la presencia, las conferencias A/V, la Federación, la conferencia web y Lync Mobile.</span><span class="sxs-lookup"><span data-stu-id="d01a5-115">Although you need an Edge Server to support Enterprise Voice and external user access, this section focuses on support for IM, presence, A/V conferencing, federation, web conferencing, and Lync Mobile.</span></span> <span data-ttu-id="d01a5-116">Para obtener más información sobre la compatibilidad con Enterprise Voice, consulte <A href="lync-server-2013-planning-for-enterprise-voice.md">Planning for Enterprise Voice in Lync Server 2013</A> en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="d01a5-116">For details about support for Enterprise Voice, see <A href="lync-server-2013-planning-for-enterprise-voice.md">Planning for Enterprise Voice in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d01a5-117">En esta sección</span><span class="sxs-lookup"><span data-stu-id="d01a5-117">In This Section</span></span>

  - [<span data-ttu-id="d01a5-118">Cambios en Lync Server 2013 que afectan a la planeación del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="d01a5-118">Changes in Lync Server 2013 that affect Edge Server planning</span></span>](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)

  - [<span data-ttu-id="d01a5-119">Requisitos del sistema para componentes de acceso de usuarios externos para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d01a5-119">System requirements for external user access components for Lync Server 2013</span></span>](lync-server-2013-system-requirements-for-external-user-access-components.md)

  - [<span data-ttu-id="d01a5-120">Información general sobre el acceso de usuarios externos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d01a5-120">Overview of external user access in Lync Server 2013</span></span>](lync-server-2013-overview-of-external-user-access.md)

  - [<span data-ttu-id="d01a5-121">Descripción de la detección automática en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d01a5-121">Understanding Autodiscover in Lync Server 2013</span></span>](lync-server-2013-understanding-autodiscover.md)

  - [<span data-ttu-id="d01a5-122">Elección de una topología en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d01a5-122">Choosing a topology in Lync Server 2013</span></span>](lync-server-2013-choosing-a-topology.md)

  - [<span data-ttu-id="d01a5-123">Recopilación de datos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d01a5-123">Data collection in Lync Server 2013</span></span>](lync-server-2013-data-collection.md)

  - [<span data-ttu-id="d01a5-124">Determinación de los requisitos de DNS para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d01a5-124">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)

  - [<span data-ttu-id="d01a5-125">Determinación de los requisitos de los puertos y el Firewall de A/V externos para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d01a5-125">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

  - [<span data-ttu-id="d01a5-126">Planeación de certificados de servidor perimetral en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d01a5-126">Plan for Edge Server certificates in Lync Server 2013</span></span>](lync-server-2013-plan-for-edge-server-certificates.md)

  - [<span data-ttu-id="d01a5-127">Escenarios para el acceso de usuarios externos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d01a5-127">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

