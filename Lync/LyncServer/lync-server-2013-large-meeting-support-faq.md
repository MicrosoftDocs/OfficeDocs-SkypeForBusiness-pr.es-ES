---
title: 'Lync Server 2013: preguntas más frecuentes sobre la compatibilidad con reuniones grandes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server large meeting support FAQ
ms:assetid: 34b4fb6a-e35c-47e8-8ab1-f8331741fed2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204804(v=OCS.15)
ms:contentKeyID: 48183837
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8b00c7d2713bed543dd42812d0d7c31bf75cd1d8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146343"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="large-meeting-support-faq-for-lync-server-2013"></a><span data-ttu-id="c0a67-102">Preguntas más frecuentes de soporte de reuniones grandes para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c0a67-102">Large meeting support FAQ for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c0a67-103">_**Última modificación del tema:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="c0a67-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="c0a67-104">Las siguientes secciones ofrecen respuestas a preguntas habituales para crear y ejecutar reuniones grandes.</span><span class="sxs-lookup"><span data-stu-id="c0a67-104">The following sections provide answers to common questions for creating and running large meetings.</span></span>

<div>

## <a name="q-how-many-users-can-participate-in-a-large-meeting"></a><span data-ttu-id="c0a67-105">P: ¿Cuántos usuarios pueden participar en una reunión grande?</span><span class="sxs-lookup"><span data-stu-id="c0a67-105">Q: How many users can participate in a large meeting?</span></span>

<span data-ttu-id="c0a67-106">El modelo de usuario de Lync Server especifica los límites de 250 usuarios en un grupo compartido o 1000 usuarios en un grupo dedicado a reuniones grandes, pero estos números solo representan el número de usuarios que se probaron y solo para el conjunto específico de hardware que usamos en nuestras pruebas.</span><span class="sxs-lookup"><span data-stu-id="c0a67-106">The Lync Server user model specifies limits of 250 users in a shared pool or 1000 users in a pool dedicated to large meetings, but these numbers only represent the number of users we tested and only for the specific set of hardware that we used in our testing.</span></span> <span data-ttu-id="c0a67-107">En función de nuestra prueba, se recomiendan dichos límites para tamaños máximos.</span><span class="sxs-lookup"><span data-stu-id="c0a67-107">Based on our testing, we recommend those limits for maximum sizes.</span></span> <span data-ttu-id="c0a67-108">Sin embargo, se controla el número real de participantes permitidos en las reuniones de la organización mediante la configuración de una o varias directivas de conferencia (que se configuran mediante cmdlets de Windows PowerShell en el shell de administración de Lync Server o mediante el uso de Lync Server Panel de control).</span><span class="sxs-lookup"><span data-stu-id="c0a67-108">However, you control the actual number of participants allowed in meetings in your organization by configuring one or more conferencing policies (which you configure using Windows PowerShell cmdlets in the Lync Server Management Shell or using the Lync Server Control Panel).</span></span> <span data-ttu-id="c0a67-109">El número que especifica en una directiva de conferencia puede ser cualquier número entero de 32 bits comprendido entre 1 y 4.294.967.295, pero el tamaño recomendado se encuentra entre 2 y 250 participantes, inclusive; y el valor predeterminado es 250.</span><span class="sxs-lookup"><span data-stu-id="c0a67-109">The number that you specify in a conferencing policy can be any 32-bit whole number between 1 and 4,294,967,295, but the recommended size is between 2 and 250 participants, inclusive; and the default value is 250.</span></span>

</div>

<div>

## <a name="q-how-many-meetings-or-other-workloads-can-i-have-in-a-pool-that-is-dedicated-to-large-meetings"></a><span data-ttu-id="c0a67-110">P: ¿Cuántas reuniones u otras cargas de trabajo puedo tener en un grupo de servidores que está dedicado a reuniones grandes?</span><span class="sxs-lookup"><span data-stu-id="c0a67-110">Q: How many meetings or other workloads can I have in a pool that is dedicated to large meetings?</span></span>

<span data-ttu-id="c0a67-p102">Para garantizar la mejor experiencia de usuario en reuniones grandes de hasta 1000 participantes, se recomienda hospedar únicamente una única reunión grande cada vez en un grupo de servidores dedicado a reuniones grandes. También se recomienda no permitir que se ejecute cualquier otra carga de trabajo en dicho grupo de servidores cuando la reunión grande se encuentre en curso.</span><span class="sxs-lookup"><span data-stu-id="c0a67-p102">To ensure the best user experience in large meetings of up to 1000 participants, we recommend hosting only a single large meeting at a time on a pool that is dedicated to large meetings. We also recommend not allowing any other workloads to run on that pool when the large meeting is in progress.</span></span>

</div>

<div>

## <a name="q-should-the-organizers-of-large-meeting-be-homed-on-the-dedicated-pool"></a><span data-ttu-id="c0a67-113">P: ¿Deberían los organizadores de reuniones grandes hospedarse en el grupo de servidores dedicado?</span><span class="sxs-lookup"><span data-stu-id="c0a67-113">Q: Should the organizers of large meeting be homed on the dedicated pool?</span></span>

<span data-ttu-id="c0a67-p103">No. Se recomienda no hospedar ningún usuario distinto del personal dedicado que administra la programación de reuniones grandes en el grupo de servidores dedicado. Esto evita que tráfico de comunicaciones en tiempo real provoque problemas con reuniones grandes que se hospedan en el grupo de servidores. Debería programar reuniones grandes en el grupo de servidores dedicado con una cuenta de usuario del personal de programación de reuniones grandes. Debería agregar la cuenta de usuario del organizador de reuniones (el usuario que solicita una reunión grande) como moderador para las reuniones grandes.</span><span class="sxs-lookup"><span data-stu-id="c0a67-p103">No. We recommend not homing any users other than the dedicated staff that manages scheduling of large meetings on the dedicated pool. This prevents other real-time communications traffic from causing problems with large meetings that are hosted in the pool. You should schedule large meetings on the dedicated pool using a user account of the large meeting scheduling staff. You should add the user account of the meeting organizer (the user who requests a large meeting) as a presenter for the large meeting.</span></span>

</div>

<div>

## <a name="q-what-media-modalities-can-i-use-in-a-large-meeting"></a><span data-ttu-id="c0a67-119">P: ¿Qué modalidades de medios puedo usar en una reunión grande?</span><span class="sxs-lookup"><span data-stu-id="c0a67-119">Q: What media modalities can I use in a large meeting?</span></span>

<span data-ttu-id="c0a67-120">Las reuniones grandes con un máximo de 1000 usuarios pueden incluir audio, video, uso compartido de PowerPoint, pizarras y sondeo de presencia.</span><span class="sxs-lookup"><span data-stu-id="c0a67-120">Large meetings with up to 1000 users can include audio, video, PowerPoint sharing, whiteboards, and presence polling.</span></span>

</div>

<div>

## <a name="q-can-i-use-group-instant-messaging-im-in-large-meetings"></a><span data-ttu-id="c0a67-121">P: ¿Puedo usar la mensajería instantánea de grupo (MI) en reuniones grandes?</span><span class="sxs-lookup"><span data-stu-id="c0a67-121">Q: Can I use group instant messaging (IM) in large meetings?</span></span>

<span data-ttu-id="c0a67-122">Sí.</span><span class="sxs-lookup"><span data-stu-id="c0a67-122">Yes.</span></span> <span data-ttu-id="c0a67-123">Sin embargo, los números grandes de mensajes instantáneos, especialmente cuando se envían por un gran número de participantes de reunión, pueden afectar a la experiencia del usuario debido a problemas con el desplazamiento de texto rápido en la ventana de MI.</span><span class="sxs-lookup"><span data-stu-id="c0a67-123">However, large numbers of instant messages, especially when sent by a large number of meeting participants, can affect the user experience due to problems with fast text scrolling in the IM window.</span></span> <span data-ttu-id="c0a67-124">La entrega de una gran cantidad de mensajes instantáneos de un máximo de 1000 usuarios también puede introducir cargas de servidor importantes, que pueden afectar al rendimiento.</span><span class="sxs-lookup"><span data-stu-id="c0a67-124">Delivering a large amount of instant messages to up to 1000 users can also introduce significant server loads, which can affect performance.</span></span> <span data-ttu-id="c0a67-125">Por lo general, la mensajería instantánea solo es necesaria para las\&preguntas y respuestas (Q como).</span><span class="sxs-lookup"><span data-stu-id="c0a67-125">Generally, IM is only required for questions and answers (Q\&As).</span></span>

</div>

<div>

## <a name="can-users-join-large-meetings-by-dialing-in-from-a-phone"></a><span data-ttu-id="c0a67-126">¿Pueden los usuarios unirse a reuniones grandes marcando desde un teléfono?</span><span class="sxs-lookup"><span data-stu-id="c0a67-126">Can users join large meetings by dialing in from a phone?</span></span>

<span data-ttu-id="c0a67-127">Sí.</span><span class="sxs-lookup"><span data-stu-id="c0a67-127">Yes.</span></span> <span data-ttu-id="c0a67-128">Si el grupo de servidores de Lync Server 2013 se ha implementado correctamente y está habilitado para las conferencias de acceso telefónico local, los usuarios podrán unirse a las reuniones grandes marcando en.</span><span class="sxs-lookup"><span data-stu-id="c0a67-128">If the Lync Server 2013 pool is properly deployed and enabled for dial-in conferencing, users will be able to join the large meetings by dialing in.</span></span> <span data-ttu-id="c0a67-129">Nuestra prueba ha mostrado que hasta un máximo de un 15% de los 1000 usuarios pueden unirse a la reunión grande por un período de 10 minutos.</span><span class="sxs-lookup"><span data-stu-id="c0a67-129">Our testing has shown that up to 15% of the 1000 users can join the large meeting over a 10 minute period.</span></span>

</div>

<div>

## <a name="q-can-i-host-large-meetings-in-a-virtual-topology"></a><span data-ttu-id="c0a67-130">P: ¿Puedo hospedar reuniones grandes en una topología virtual?</span><span class="sxs-lookup"><span data-stu-id="c0a67-130">Q: Can I host large meetings in a virtual topology?</span></span>

<span data-ttu-id="c0a67-131">No hemos probado reuniones grandes en una topología virtual, por lo que no admitimos el uso de máquinas virtuales para hospedar un grupo de servidores dedicados para reuniones grandes.</span><span class="sxs-lookup"><span data-stu-id="c0a67-131">We have not tested large meetings in a virtual topology, so we do not support the use of virtual machines to host a dedicated pool for large meetings.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

