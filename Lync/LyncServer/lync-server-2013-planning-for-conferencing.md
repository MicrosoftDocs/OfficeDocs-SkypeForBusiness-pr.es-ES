---
title: 'Lync Server 2013: Planeación de conferencias'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for conferencing
ms:assetid: 983a272a-e1b3-4d70-8f84-836b092fe526
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398781(v=OCS.15)
ms:contentKeyID: 48184937
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e1197dd61ea6ed871b851061d86c8653de32ddc5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036992"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="cf1cd-102">Planeación de conferencias en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cf1cd-102">Planning for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cf1cd-103">_**Última modificación del tema:** 2013-01-29_</span><span class="sxs-lookup"><span data-stu-id="cf1cd-103">_**Topic Last Modified:** 2013-01-29_</span></span>

<span data-ttu-id="cf1cd-104">Lync Server 2013 ofrece un amplio conjunto de capacidades de Conferencia:</span><span class="sxs-lookup"><span data-stu-id="cf1cd-104">Lync Server 2013 offers a rich set of conferencing capabilities:</span></span>

  - <span data-ttu-id="cf1cd-105">Conferencia web, que incluye colaboración en documentos, uso compartido de aplicaciones y uso compartido de escritorio.</span><span class="sxs-lookup"><span data-stu-id="cf1cd-105">Web conferencing, which includes document collaboration, application sharing, and desktop sharing.</span></span> <span data-ttu-id="cf1cd-106">Lync Server 2013 usa Office Web Apps y Office Web Apps Server para controlar el uso compartido y la representación de presentaciones de PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="cf1cd-106">Lync Server 2013 uses Office Web Apps and the Office Web Apps Server to handle sharing and rendering of PowerPoint presentations.</span></span> <span data-ttu-id="cf1cd-107">Para más información sobre la instalación y la configuración del servidor de Office Web Apps, vea [Configuring Integration with Office Web Apps Server and Lync server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="cf1cd-107">For details about installing and configuring the Office Web Apps Server, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

  - <span data-ttu-id="cf1cd-108">Conferencia de audio/vídeo (A/V), que permite a los usuarios participar en conferencias de audio o vídeo en tiempo real sin necesidad de servicios externos, como el servicio Microsoft Live Meeting o un puente de audio de terceros.</span><span class="sxs-lookup"><span data-stu-id="cf1cd-108">Audio/video (A/V) conferencing, which enables users to have real-time audio or video conferences without the need for external services such as the Microsoft Live Meeting service or a third-party audio bridge.</span></span>

  - <span data-ttu-id="cf1cd-109">Conferencia de acceso telefónico local, que permite a los usuarios unirse a la parte de audio de una conferencia de Lync Server 2013 mediante un teléfono de red telefónica conmutada (RTC) sin necesidad de un proveedor de servicios de audioconferencia de terceros.</span><span class="sxs-lookup"><span data-stu-id="cf1cd-109">Dial-in conferencing, which allows users to join the audio portion of a Lync Server 2013 conference by using a public switched telephone network (PSTN) phone without requiring a third-party audio conferencing provider.</span></span>

  - <span data-ttu-id="cf1cd-110">Conferencia de mensajería instantánea, donde más de dos participantes se comunican en una única sesión de mensajería instantánea.</span><span class="sxs-lookup"><span data-stu-id="cf1cd-110">Instant messaging (IM) conferencing, in which more than two parties communicate in a single IM session.</span></span> <span data-ttu-id="cf1cd-111">Para obtener más información sobre las conferencias de mensajería instantánea, vea [planeación de los servidores front-end, la mensajería instantánea y la presencia en Lync Server 2013](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md).</span><span class="sxs-lookup"><span data-stu-id="cf1cd-111">For details about IM conferencing, see [Planning for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md).</span></span>

<span data-ttu-id="cf1cd-112">Lync Server 2013 admite conferencias programadas y conferencias improvisadas.</span><span class="sxs-lookup"><span data-stu-id="cf1cd-112">Lync Server 2013 supports both scheduled conferences and impromptu conferences.</span></span>

<span data-ttu-id="cf1cd-113">Al implementar Lync Server 2013, el servidor front-end, puede elegir si también desea implementar la conferencia Web, la conferencia A/V y las capacidades de conferencia de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="cf1cd-113">When you deploy Lync Server 2013, Front End Server, you can choose whether to also deploy the web conferencing, A/V conferencing, and dial-in conferencing capabilities.</span></span> <span data-ttu-id="cf1cd-114">Las capacidades de conferencia de mensajería instantánea se implementan siempre de forma automática junto con las funciones de conversación de mensajería instantánea en los servidores front-end de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cf1cd-114">IM conferencing capabilities are always automatically deployed along with IM conversation capabilities on Lync Server 2013 Front End Servers.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cf1cd-115">Si su implementación incluye reuniones organizadas mediante clientes de Office Communicator 2007 R2 (incluido el complemento de conferencia o consola de Live Meeting para Microsoft Office Outlook), las reuniones tendrán las siguientes limitaciones después de que se migren a Lync. Servidor 2013:</span><span class="sxs-lookup"><span data-stu-id="cf1cd-115">If your deployment includes meetings organized using Office Communicator 2007 R2 clients (including the Live Meeting console or Conferencing Add-in for Microsoft Office Outlook), the meetings will have the following limitations after they are migrated to Lync Server 2013:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="cf1cd-116">Los usuarios de la reunión no podrán usar las características de colaboración de datos, como la colaboración en documentos, el uso compartido de aplicaciones y el uso compartido de escritorio.</span><span class="sxs-lookup"><span data-stu-id="cf1cd-116">Users in the meeting will not be able to use data collaboration features, including document collaboration, application sharing, and desktop sharing.</span></span></P>
> <LI>
> <P><span data-ttu-id="cf1cd-117">Los problemas de estabilidad pueden surgir debido a que los clientes de Office Communicator 2007 R2 no son compatibles con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cf1cd-117">Stability issues may arise since Office Communicator 2007 R2 clients are not supported with Lync Server 2013.</span></span></P></LI></UL><span data-ttu-id="cf1cd-118">Para evitar estos problemas, reprograme cualquier reunión organizada mediante los clientes de Office Communicator 2007 R2 con Outlook 2010 o Outlook 2013 mediante el complemento de reunión en línea para Lync 2010 o el complemento de reunión en línea para Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="cf1cd-118">To avoid these issues, reschedule any meeting organized using Office Communicator 2007 R2 clients with Outlook 2010 or Outlook 2013 using either the Online Meeting Add-in for Lync 2010 or Online Meeting Add-in for Lync 2013.</span></span>



</div>

<span data-ttu-id="cf1cd-119">En las secciones siguientes se describe lo que es necesario para implementar los distintos tipos de capacidades de conferencia, incluido el proceso de planeación, los componentes, los requisitos de hardware y software y el proceso de implementación.</span><span class="sxs-lookup"><span data-stu-id="cf1cd-119">The following sections describe what is required to deploy the various types of conferencing capabilities, including the planning process, components, hardware and software requirements, and the deployment process.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="cf1cd-120">En esta sección</span><span class="sxs-lookup"><span data-stu-id="cf1cd-120">In This Section</span></span>

  - [<span data-ttu-id="cf1cd-121">Información general sobre las conferencias en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cf1cd-121">Overview of conferencing in Lync Server 2013</span></span>](lync-server-2013-overview-of-conferencing.md)

  - [<span data-ttu-id="cf1cd-122">Definición de los requisitos para las conferencias en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cf1cd-122">Defining your requirements for conferencing in Lync Server 2013</span></span>](lync-server-2013-defining-your-requirements-for-conferencing.md)

  - [<span data-ttu-id="cf1cd-123">Componentes y topologías para conferencias en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cf1cd-123">Components and topologies for conferencing in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-conferencing.md)

  - [<span data-ttu-id="cf1cd-124">Requisitos técnicos para conferencias en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cf1cd-124">Technical requirements for conferencing in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-conferencing.md)

  - [<span data-ttu-id="cf1cd-125">Lista de comprobación para la implementación de conferencias en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cf1cd-125">Deployment checklist for conferencing in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-conferencing.md)

  - [<span data-ttu-id="cf1cd-126">Compatibilidad con reuniones grandes en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cf1cd-126">Support for large meetings in Lync Server 2013</span></span>](lync-server-2013-support-for-large-meetings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

