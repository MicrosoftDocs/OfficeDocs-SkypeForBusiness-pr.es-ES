---
title: 'Lync Server 2013: Planificar conferencias'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for conferencing
ms:assetid: 983a272a-e1b3-4d70-8f84-836b092fe526
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398781(v=OCS.15)
ms:contentKeyID: 48184937
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2aff3eef21ca150f4ad6fc9bb2358c2ac81680fd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824823"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="c6905-102">Planificar conferencias en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6905-102">Planning for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c6905-103">_**Última modificación del tema:** 2013-01-29_</span><span class="sxs-lookup"><span data-stu-id="c6905-103">_**Topic Last Modified:** 2013-01-29_</span></span>

<span data-ttu-id="c6905-104">Lync Server 2013 ofrece un amplio conjunto de capacidades de Conferencia:</span><span class="sxs-lookup"><span data-stu-id="c6905-104">Lync Server 2013 offers a rich set of conferencing capabilities:</span></span>

  - <span data-ttu-id="c6905-105">Conferencias web, que incluye colaboración de documentos, uso compartido de aplicaciones y uso compartido de escritorio.</span><span class="sxs-lookup"><span data-stu-id="c6905-105">Web conferencing, which includes document collaboration, application sharing, and desktop sharing.</span></span> <span data-ttu-id="c6905-106">Lync Server 2013 usa Office Web Apps y Office Web Apps Server para controlar el uso compartido y el procesamiento de presentaciones de PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="c6905-106">Lync Server 2013 uses Office Web Apps and the Office Web Apps Server to handle sharing and rendering of PowerPoint presentations.</span></span> <span data-ttu-id="c6905-107">Para obtener más información sobre cómo instalar y configurar el servidor de Office Web Apps, vea [configurar la integración con Office Web Apps Server y Lync server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="c6905-107">For details about installing and configuring the Office Web Apps Server, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

  - <span data-ttu-id="c6905-108">Conferencias de audio y vídeo (A/V), que permite a los usuarios tener conferencias de audio o vídeo en tiempo real sin necesidad de servicios externos, como el servicio Microsoft Live Meeting o un puente de audio de terceros.</span><span class="sxs-lookup"><span data-stu-id="c6905-108">Audio/video (A/V) conferencing, which enables users to have real-time audio or video conferences without the need for external services such as the Microsoft Live Meeting service or a third-party audio bridge.</span></span>

  - <span data-ttu-id="c6905-109">Conferencias de acceso telefónico local, que permite a los usuarios unirse a la parte de audio de una conferencia de 2013 de Lync Server mediante un teléfono con red telefónica conmutada (RTC) sin requerir un proveedor de servicios de audioconferencia de terceros.</span><span class="sxs-lookup"><span data-stu-id="c6905-109">Dial-in conferencing, which allows users to join the audio portion of a Lync Server 2013 conference by using a public switched telephone network (PSTN) phone without requiring a third-party audio conferencing provider.</span></span>

  - <span data-ttu-id="c6905-110">Conferencias de mensajería instantánea (mi), en las que más de dos partes se comunican en una sola sesión de mensajería instantánea.</span><span class="sxs-lookup"><span data-stu-id="c6905-110">Instant messaging (IM) conferencing, in which more than two parties communicate in a single IM session.</span></span> <span data-ttu-id="c6905-111">Para obtener más información sobre las conferencias de mensajería instantánea, consulte [planificación de servidores de aplicaciones para el usuario, mensajería instantánea y presencia en Lync Server 2013](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md).</span><span class="sxs-lookup"><span data-stu-id="c6905-111">For details about IM conferencing, see [Planning for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md).</span></span>

<span data-ttu-id="c6905-112">Lync Server 2013 admite tanto conferencias programadas como conferencias espontáneas.</span><span class="sxs-lookup"><span data-stu-id="c6905-112">Lync Server 2013 supports both scheduled conferences and impromptu conferences.</span></span>

<span data-ttu-id="c6905-113">Al implementar Lync Server 2013, el servidor front-end, puede elegir si implementar también las conferencias web, las conferencias A/V y las capacidades de conferencia de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="c6905-113">When you deploy Lync Server 2013, Front End Server, you can choose whether to also deploy the web conferencing, A/V conferencing, and dial-in conferencing capabilities.</span></span> <span data-ttu-id="c6905-114">Las capacidades de conferencia de mi siempre se implementan automáticamente junto con las funciones de conversación de mensajería instantánea en servidores front-end de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c6905-114">IM conferencing capabilities are always automatically deployed along with IM conversation capabilities on Lync Server 2013 Front End Servers.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c6905-115">Si su implementación incluye reuniones organizadas con clientes de Office Communicator 2007 R2 (incluida la consola de Live Meeting o el complemento de conferencias para Microsoft Office Outlook), las reuniones tendrán las siguientes limitaciones después de migrar a Lync. Server 2013:</span><span class="sxs-lookup"><span data-stu-id="c6905-115">If your deployment includes meetings organized using Office Communicator 2007 R2 clients (including the Live Meeting console or Conferencing Add-in for Microsoft Office Outlook), the meetings will have the following limitations after they are migrated to Lync Server 2013:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="c6905-116">Los usuarios de la reunión no podrán usar características de colaboración de datos, como la colaboración de documentos, uso compartido de aplicaciones y uso compartido de escritorio.</span><span class="sxs-lookup"><span data-stu-id="c6905-116">Users in the meeting will not be able to use data collaboration features, including document collaboration, application sharing, and desktop sharing.</span></span></P>
> <LI>
> <P><span data-ttu-id="c6905-117">Pueden surgir problemas de estabilidad, ya que los clientes de Office Communicator 2007 R2 no son compatibles con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c6905-117">Stability issues may arise since Office Communicator 2007 R2 clients are not supported with Lync Server 2013.</span></span></P></LI></UL><span data-ttu-id="c6905-118">Para evitar estos problemas, reprograme cualquier reunión organizada con clientes de Office Communicator 2007 R2 con Outlook 2010 o Outlook 2013 con el complemento de reunión en línea para Lync 2010 o el complemento de reunión en línea para Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="c6905-118">To avoid these issues, reschedule any meeting organized using Office Communicator 2007 R2 clients with Outlook 2010 or Outlook 2013 using either the Online Meeting Add-in for Lync 2010 or Online Meeting Add-in for Lync 2013.</span></span>



</div>

<span data-ttu-id="c6905-119">En las siguientes secciones, se describen los pasos necesarios para implementar los distintos tipos de capacidades de conferencia, incluidos el proceso de planeamiento, los componentes, los requisitos de hardware y software, y el proceso de implementación.</span><span class="sxs-lookup"><span data-stu-id="c6905-119">The following sections describe what is required to deploy the various types of conferencing capabilities, including the planning process, components, hardware and software requirements, and the deployment process.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c6905-120">En esta sección</span><span class="sxs-lookup"><span data-stu-id="c6905-120">In This Section</span></span>

  - [<span data-ttu-id="c6905-121">Información general sobre conferencias en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6905-121">Overview of conferencing in Lync Server 2013</span></span>](lync-server-2013-overview-of-conferencing.md)

  - [<span data-ttu-id="c6905-122">Definición de requisitos para conferencias en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6905-122">Defining your requirements for conferencing in Lync Server 2013</span></span>](lync-server-2013-defining-your-requirements-for-conferencing.md)

  - [<span data-ttu-id="c6905-123">Componentes y topologías para conferencias en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6905-123">Components and topologies for conferencing in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-conferencing.md)

  - [<span data-ttu-id="c6905-124">Requisitos técnicos para conferencias en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6905-124">Technical requirements for conferencing in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-conferencing.md)

  - [<span data-ttu-id="c6905-125">Lista de comprobación para la implementación de conferencias en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6905-125">Deployment checklist for conferencing in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-conferencing.md)

  - [<span data-ttu-id="c6905-126">Compatibilidad con reuniones grandes en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6905-126">Support for large meetings in Lync Server 2013</span></span>](lync-server-2013-support-for-large-meetings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

