---
title: 'Lync Server 2013: preguntas más frecuentes sobre la ayuda de reuniones grandes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync Server large meeting support FAQ
ms:assetid: 34b4fb6a-e35c-47e8-8ab1-f8331741fed2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204804(v=OCS.15)
ms:contentKeyID: 48183837
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c8355374a773afe3d6da22c886a2b103b13abd3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834948"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="large-meeting-support-faq-for-lync-server-2013"></a><span data-ttu-id="015f7-102">Preguntas más frecuentes sobre la compatibilidad con reuniones grandes para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="015f7-102">Large meeting support FAQ for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="015f7-103">_**Última modificación del tema:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="015f7-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="015f7-104">En las siguientes secciones se proporcionan respuestas a las preguntas más frecuentes sobre la creación y la ejecución de reuniones grandes.</span><span class="sxs-lookup"><span data-stu-id="015f7-104">The following sections provide answers to common questions for creating and running large meetings.</span></span>

<div>

## <a name="q-how-many-users-can-participate-in-a-large-meeting"></a><span data-ttu-id="015f7-105">P: ¿Cuántos usuarios pueden participar en una reunión de gran tamaño?</span><span class="sxs-lookup"><span data-stu-id="015f7-105">Q: How many users can participate in a large meeting?</span></span>

<span data-ttu-id="015f7-106">El modelo de usuario de Lync Server especifica los límites de usuarios de 250 en un grupo compartido o los usuarios de 1000 de un grupo dedicado a reuniones grandes, pero estos números solo representan el número de usuarios que probamos y solo para el conjunto específico de hardware que usamos en nuestras pruebas.</span><span class="sxs-lookup"><span data-stu-id="015f7-106">The Lync Server user model specifies limits of 250 users in a shared pool or 1000 users in a pool dedicated to large meetings, but these numbers only represent the number of users we tested and only for the specific set of hardware that we used in our testing.</span></span> <span data-ttu-id="015f7-107">Según nuestras pruebas, recomendamos esos límites para el tamaño máximo.</span><span class="sxs-lookup"><span data-stu-id="015f7-107">Based on our testing, we recommend those limits for maximum sizes.</span></span> <span data-ttu-id="015f7-108">Sin embargo, puede controlar la cantidad real de participantes permitidos en las reuniones de su organización mediante la configuración de una o más directivas de conferencia (que puede configurar con los cmdlets de Windows PowerShell en el shell de administración de Lync Server o con el servidor de Lync). Panel de control).</span><span class="sxs-lookup"><span data-stu-id="015f7-108">However, you control the actual number of participants allowed in meetings in your organization by configuring one or more conferencing policies (which you configure using Windows PowerShell cmdlets in the Lync Server Management Shell or using the Lync Server Control Panel).</span></span> <span data-ttu-id="015f7-109">El número que especifique en una directiva de conferencia puede ser cualquier número entero de 32 entre 1 y 4.294.967.295, pero el tamaño recomendado es de entre 2 y 250 participantes, ambos inclusive; y el valor predeterminado es 250.</span><span class="sxs-lookup"><span data-stu-id="015f7-109">The number that you specify in a conferencing policy can be any 32-bit whole number between 1 and 4,294,967,295, but the recommended size is between 2 and 250 participants, inclusive; and the default value is 250.</span></span>

</div>

<div>

## <a name="q-how-many-meetings-or-other-workloads-can-i-have-in-a-pool-that-is-dedicated-to-large-meetings"></a><span data-ttu-id="015f7-110">P: ¿cuántas reuniones u otras cargas de trabajo puedo tener en un grupo dedicado a reuniones grandes?</span><span class="sxs-lookup"><span data-stu-id="015f7-110">Q: How many meetings or other workloads can I have in a pool that is dedicated to large meetings?</span></span>

<span data-ttu-id="015f7-111">Para garantizar la mejor experiencia del usuario en reuniones de gran tamaño de hasta 1000 participantes, le recomendamos que aloje una sola reunión de gran tamaño a la vez en un grupo dedicado a reuniones grandes.</span><span class="sxs-lookup"><span data-stu-id="015f7-111">To ensure the best user experience in large meetings of up to 1000 participants, we recommend hosting only a single large meeting at a time on a pool that is dedicated to large meetings.</span></span> <span data-ttu-id="015f7-112">También recomendamos no permitir que se ejecuten otras cargas de trabajo en ese grupo cuando la reunión de gran tamaño está en curso.</span><span class="sxs-lookup"><span data-stu-id="015f7-112">We also recommend not allowing any other workloads to run on that pool when the large meeting is in progress.</span></span>

</div>

<div>

## <a name="q-should-the-organizers-of-large-meeting-be-homed-on-the-dedicated-pool"></a><span data-ttu-id="015f7-113">P: ¿deberían los organizadores de una reunión grande estar alojados en el grupo dedicado?</span><span class="sxs-lookup"><span data-stu-id="015f7-113">Q: Should the organizers of large meeting be homed on the dedicated pool?</span></span>

<span data-ttu-id="015f7-114">No.</span><span class="sxs-lookup"><span data-stu-id="015f7-114">No.</span></span> <span data-ttu-id="015f7-115">Le recomendamos que no se a ningún usuario que no sea el personal dedicado que administra la programación de reuniones grandes en el grupo dedicado.</span><span class="sxs-lookup"><span data-stu-id="015f7-115">We recommend not homing any users other than the dedicated staff that manages scheduling of large meetings on the dedicated pool.</span></span> <span data-ttu-id="015f7-116">Esto evita que otro tráfico de comunicaciones en tiempo real cause problemas con reuniones grandes hospedadas en el grupo.</span><span class="sxs-lookup"><span data-stu-id="015f7-116">This prevents other real-time communications traffic from causing problems with large meetings that are hosted in the pool.</span></span> <span data-ttu-id="015f7-117">Debe programar reuniones grandes en el grupo dedicado usando una cuenta de usuario del gran personal de programación de reuniones.</span><span class="sxs-lookup"><span data-stu-id="015f7-117">You should schedule large meetings on the dedicated pool using a user account of the large meeting scheduling staff.</span></span> <span data-ttu-id="015f7-118">Debe agregar la cuenta de usuario del organizador de la reunión (el usuario que solicita una reunión grande) como moderador de la reunión grande.</span><span class="sxs-lookup"><span data-stu-id="015f7-118">You should add the user account of the meeting organizer (the user who requests a large meeting) as a presenter for the large meeting.</span></span>

</div>

<div>

## <a name="q-what-media-modalities-can-i-use-in-a-large-meeting"></a><span data-ttu-id="015f7-119">P: ¿Qué es lo que las modalidades de medios puedo usar en una reunión grande?</span><span class="sxs-lookup"><span data-stu-id="015f7-119">Q: What media modalities can I use in a large meeting?</span></span>

<span data-ttu-id="015f7-120">Las reuniones grandes con hasta 1000 usuarios pueden incluir audio, vídeo, uso compartido de PowerPoint, pizarras y sondeo de presencia.</span><span class="sxs-lookup"><span data-stu-id="015f7-120">Large meetings with up to 1000 users can include audio, video, PowerPoint sharing, whiteboards, and presence polling.</span></span>

</div>

<div>

## <a name="q-can-i-use-group-instant-messaging-im-in-large-meetings"></a><span data-ttu-id="015f7-121">P: ¿Puedo usar la mensajería instantánea grupal (mi) en reuniones grandes?</span><span class="sxs-lookup"><span data-stu-id="015f7-121">Q: Can I use group instant messaging (IM) in large meetings?</span></span>

<span data-ttu-id="015f7-122">Sí.</span><span class="sxs-lookup"><span data-stu-id="015f7-122">Yes.</span></span> <span data-ttu-id="015f7-123">Sin embargo, un gran número de mensajes instantáneos, especialmente cuando los envía un gran número de participantes de la reunión, puede afectar la experiencia del usuario debido a problemas con el desplazamiento de texto rápido en la ventana de mensajes instantáneos.</span><span class="sxs-lookup"><span data-stu-id="015f7-123">However, large numbers of instant messages, especially when sent by a large number of meeting participants, can affect the user experience due to problems with fast text scrolling in the IM window.</span></span> <span data-ttu-id="015f7-124">Ofrecer una gran cantidad de mensajes instantáneos a un máximo de 1000 usuarios también puede presentar cargas de servidor significativas, lo cual puede afectar al rendimiento.</span><span class="sxs-lookup"><span data-stu-id="015f7-124">Delivering a large amount of instant messages to up to 1000 users can also introduce significant server loads, which can affect performance.</span></span> <span data-ttu-id="015f7-125">Por lo general, la mensajería instantánea solo es necesaria para preguntas\&y respuestas (Q como).</span><span class="sxs-lookup"><span data-stu-id="015f7-125">Generally, IM is only required for questions and answers (Q\&As).</span></span>

</div>

<div>

## <a name="can-users-join-large-meetings-by-dialing-in-from-a-phone"></a><span data-ttu-id="015f7-126">¿Los usuarios pueden unirse a reuniones grandes al marcar desde un teléfono?</span><span class="sxs-lookup"><span data-stu-id="015f7-126">Can users join large meetings by dialing in from a phone?</span></span>

<span data-ttu-id="015f7-127">Sí.</span><span class="sxs-lookup"><span data-stu-id="015f7-127">Yes.</span></span> <span data-ttu-id="015f7-128">Si el grupo de 2013 de Lync Server se ha implementado correctamente y está habilitado para las conferencias de acceso telefónico local, los usuarios podrán unirse a las reuniones grandes al marcar.</span><span class="sxs-lookup"><span data-stu-id="015f7-128">If the Lync Server 2013 pool is properly deployed and enabled for dial-in conferencing, users will be able to join the large meetings by dialing in.</span></span> <span data-ttu-id="015f7-129">Nuestras pruebas han demostrado que hasta el 15% de los usuarios de 1000 pueden unirse a la reunión de gran tamaño durante un período de 10 minutos.</span><span class="sxs-lookup"><span data-stu-id="015f7-129">Our testing has shown that up to 15% of the 1000 users can join the large meeting over a 10 minute period.</span></span>

</div>

<div>

## <a name="q-can-i-host-large-meetings-in-a-virtual-topology"></a><span data-ttu-id="015f7-130">P: ¿puedo hospedar reuniones grandes en una topología virtual?</span><span class="sxs-lookup"><span data-stu-id="015f7-130">Q: Can I host large meetings in a virtual topology?</span></span>

<span data-ttu-id="015f7-131">No hemos probado las reuniones grandes en una topología virtual, por lo que no admitimos el uso de máquinas virtuales para hospedar un grupo dedicado para reuniones grandes.</span><span class="sxs-lookup"><span data-stu-id="015f7-131">We have not tested large meetings in a virtual topology, so we do not support the use of virtual machines to host a dedicated pool for large meetings.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

