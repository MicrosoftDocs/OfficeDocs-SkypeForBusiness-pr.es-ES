---
title: 'Lync Server 2013: Planear acceso de usuarios externos'
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
ms.openlocfilehash: 17d38abe775a915fc3357610ad2b741eb0e77628
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41752340"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="4112e-102">Planear acceso de usuarios externos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4112e-102">Planning for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4112e-103">_**Última modificación del tema:** 2013-01-19_</span><span class="sxs-lookup"><span data-stu-id="4112e-103">_**Topic Last Modified:** 2013-01-19_</span></span>

<span data-ttu-id="4112e-104">Las comunicaciones en la mayoría de las organizaciones implican a servicios y usuarios que no se encuentran dentro de la red interna.</span><span class="sxs-lookup"><span data-stu-id="4112e-104">Communications in most organizations involve services and users that are not inside your internal network.</span></span> <span data-ttu-id="4112e-105">Estos servicios y usuarios incluyen empleados que están fuera del sitio temporal o permanentemente, empleados de organizaciones de clientes o socios, personas que usan servicios de mensajería instantánea pública (mi) y clientes potenciales, socios y usuarios anónimos a los que invite a reuniones y presentaciones.</span><span class="sxs-lookup"><span data-stu-id="4112e-105">These services and users include employees who are temporarily or permanently offsite, employees of customer or partner organizations, people who use public instant messaging (IM) services, and potential customers, partners and anonymous users whom you invite to meetings and presentations.</span></span> <span data-ttu-id="4112e-106">En esta documentación, estas personas se conocen colectivamente como *usuarios externos*.</span><span class="sxs-lookup"><span data-stu-id="4112e-106">In this documentation, these people are collectively referred to as *external users*.</span></span>

<span data-ttu-id="4112e-107">Con Microsoft Lync Server 2013, los usuarios de su organización pueden usar la mensajería instantánea y la presencia para comunicarse con los usuarios externos y pueden participar en conferencias de audio y vídeo (A/V) y en conferencias web con sus empleados fuera del sitio y otros tipos de usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="4112e-107">With Microsoft Lync Server 2013, users in your organization can use IM and presence to communicate with external users, and they can participate in audio/video (A/V) conferencing and web conferencing with your offsite employees and other types of external users.</span></span> <span data-ttu-id="4112e-108">También puedes admitir el acceso externo desde dispositivos móviles y con la telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="4112e-108">You can also support external access from mobile devices and over Enterprise Voice.</span></span> <span data-ttu-id="4112e-109">Los usuarios externos que no son miembros de su organización pueden participar en reuniones de Lync Server 2013, lo que permite a los asistentes anónimos.</span><span class="sxs-lookup"><span data-stu-id="4112e-109">External users who are not members of your organization can participate in Lync Server 2013 meetings, allowing anonymous attendees.</span></span>

<span data-ttu-id="4112e-110">Para admitir las comunicaciones en el Firewall de la organización, debe implementar el servidor perimetral 2013 de Lync Server en la red perimetral (también conocida como DMZ, zona desmilitarizada y subred filtrada).</span><span class="sxs-lookup"><span data-stu-id="4112e-110">To support communications across your organization’s firewall, you deploy Lync Server 2013 Edge Server in your perimeter network (also known as DMZ, demilitarized zone, and screened subnet).</span></span> <span data-ttu-id="4112e-111">El servidor perimetral controla cómo los usuarios externos al firewall se pueden conectar a la implementación interna de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4112e-111">The Edge Server controls how users outside the firewall can connect to your internal Lync Server 2013 deployment.</span></span> <span data-ttu-id="4112e-112">También controla las comunicaciones con usuarios externos que se originan dentro del firewall.</span><span class="sxs-lookup"><span data-stu-id="4112e-112">It also controls communications with external users that originate within the firewall.</span></span>

<span data-ttu-id="4112e-113">En función de sus necesidades, puede implementar uno o varios servidores perimetrales en una o más ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="4112e-113">Depending on your requirements, you can deploy one or more Edge Servers in one or more locations.</span></span> <span data-ttu-id="4112e-114">En esta sección se describen escenarios para el acceso de usuarios externos en Lync Server 2013, y se explica cómo planear la topología perimetral y de proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="4112e-114">This section describes scenarios for external user access in Lync Server 2013, and it explains how to plan your edge and reverse proxy topology.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4112e-115">Aunque necesita un servidor perimetral para admitir la telefonía IP empresarial y el acceso de usuarios externos, esta sección se centra en la compatibilidad con la mensajería instantánea, la presencia, las conferencias A/V, la Federación, la conferencia web y Lync Mobile.</span><span class="sxs-lookup"><span data-stu-id="4112e-115">Although you need an Edge Server to support Enterprise Voice and external user access, this section focuses on support for IM, presence, A/V conferencing, federation, web conferencing, and Lync Mobile.</span></span> <span data-ttu-id="4112e-116">Para obtener más información sobre la compatibilidad de telefonía IP empresarial, consulte <A href="lync-server-2013-planning-for-enterprise-voice.md">planificación de telefonía empresarial en Lync Server 2013</A> en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="4112e-116">For details about support for Enterprise Voice, see <A href="lync-server-2013-planning-for-enterprise-voice.md">Planning for Enterprise Voice in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="4112e-117">En esta sección</span><span class="sxs-lookup"><span data-stu-id="4112e-117">In This Section</span></span>

  - [<span data-ttu-id="4112e-118">Cambios en Lync Server 2013 que afectan a la planificación del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="4112e-118">Changes in Lync Server 2013 that affect Edge Server planning</span></span>](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)

  - [<span data-ttu-id="4112e-119">Requisitos del sistema para componentes perimetrales para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4112e-119">System requirements for external user access components for Lync Server 2013</span></span>](lync-server-2013-system-requirements-for-external-user-access-components.md)

  - [<span data-ttu-id="4112e-120">Información general sobre el acceso de usuarios externos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4112e-120">Overview of external user access in Lync Server 2013</span></span>](lync-server-2013-overview-of-external-user-access.md)

  - [<span data-ttu-id="4112e-121">Descripción de la detección automática en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4112e-121">Understanding Autodiscover in Lync Server 2013</span></span>](lync-server-2013-understanding-autodiscover.md)

  - [<span data-ttu-id="4112e-122">Elección de una topología en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4112e-122">Choosing a topology in Lync Server 2013</span></span>](lync-server-2013-choosing-a-topology.md)

  - [<span data-ttu-id="4112e-123">Recopilación de datos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4112e-123">Data collection in Lync Server 2013</span></span>](lync-server-2013-data-collection.md)

  - [<span data-ttu-id="4112e-124">Determinar los requisitos DNS para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4112e-124">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)

  - [<span data-ttu-id="4112e-125">Determinar los requisitos de los puertos y el firewall de A/V externos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4112e-125">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

  - [<span data-ttu-id="4112e-126">Plan para certificados de servidores perimetrales en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4112e-126">Plan for Edge Server certificates in Lync Server 2013</span></span>](lync-server-2013-plan-for-edge-server-certificates.md)

  - [<span data-ttu-id="4112e-127">Escenarios para el acceso de usuarios externos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4112e-127">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

