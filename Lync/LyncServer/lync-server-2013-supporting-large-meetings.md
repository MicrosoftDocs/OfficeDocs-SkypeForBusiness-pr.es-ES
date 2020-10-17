---
title: 'Lync Server 2013: compatibilidad con reuniones grandes'
description: 'Lync Server 2013: admite reuniones grandes.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supporting large meetings using Lync Server
ms:assetid: 509a424f-a33d-4e72-8f87-a3ec7bb1ddeb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204894(v=OCS.15)
ms:contentKeyID: 48184136
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e116f4668c37fd26eea5cec322a8c6483385e7d3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554786"
---
# <a name="supporting-large-meetings-using-lync-server-2013"></a><span data-ttu-id="c3e06-103">Compatibilidad con reuniones grandes con Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c3e06-103">Supporting large meetings using Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c3e06-104">_**Última modificación del tema:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="c3e06-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="c3e06-105">Las reuniones grandes no siguen el modelo de prueba descrito en la sección anterior porque tienen las siguientes características:
</span><span class="sxs-lookup"><span data-stu-id="c3e06-105">Large meetings do not follow the test model described in the previous section because they have the following characteristics:</span></span>

  - <span data-ttu-id="c3e06-106">El formato de la reunión es una presentación de uno a varios.</span><span class="sxs-lookup"><span data-stu-id="c3e06-106">The meeting format is a one-to-many presentation.</span></span>

  - <span data-ttu-id="c3e06-107">Uno o unos pocos usuarios son presentadores y todo el mundo participa solo como asistentes.</span><span class="sxs-lookup"><span data-stu-id="c3e06-107">One or a few users are presenters, and everyone else participates only as attendees.</span></span>

  - <span data-ttu-id="c3e06-108">El uso compartido de una presentación de PowerPoint es la actividad principal de colaboración de datos.</span><span class="sxs-lookup"><span data-stu-id="c3e06-108">PowerPoint presentation sharing is the main data collaboration activity.</span></span>

  - <span data-ttu-id="c3e06-109">Se necesita audio y también se puede usar vídeo.</span><span class="sxs-lookup"><span data-stu-id="c3e06-109">Audio is required and video may also be used.</span></span>

  - <span data-ttu-id="c3e06-110">Una persona dedicada, generalmente el organizador de la reunión o un asistente del organizador, configura la reunión con suficiente antelación.</span><span class="sxs-lookup"><span data-stu-id="c3e06-110">A dedicated person, generally either the meeting organizer or an assistant to the organizer sets up the meeting well in advance.</span></span>

  - <span data-ttu-id="c3e06-111">El personal dedicado (no los presentadores) ejecuta la reunión, incluida la conexión a una reunión en línea, la comprobación de que el uso compartido de audio, vídeo y diapositivas funciona, la administración de roles de usuario y el salón de espera, la activación y desactivación del silencio de los participantes, la realización de preguntas y la administración de grabaciones, según sea lo adecuado.</span><span class="sxs-lookup"><span data-stu-id="c3e06-111">Dedicated staff (not the presenters) runs the meeting, including connecting to an online meeting, verifying that audio, video, and slide sharing work, managing lobby and user roles, muting and unmuting participants, taking questions, and managing recordings, as appropriate.</span></span>

<span data-ttu-id="c3e06-112">La compatibilidad con grandes reuniones de hasta 1.000 usuarios requiere abordar problemas relacionados con el modelo de hardware compartidos y el modelo sin reserva.</span><span class="sxs-lookup"><span data-stu-id="c3e06-112">Supporting large meetings of up to 1000 users requires addressing the issues related to both the shared hardware model and the no-reservation model.</span></span>

<span data-ttu-id="c3e06-113">Para disponer de suficientes recursos de CPU y memoria para reuniones de hasta 1000 usuarios, los servidores front-end de hospedaje no deben hospedar otras cargas de trabajo de mensajería instantánea (mi) y presencia o de telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="c3e06-113">To have sufficient CPU and memory resources for meetings of up to 1000 users, the hosting Front End Servers should not host any other instant messaging (IM) and presence or Enterprise Voice workloads.</span></span> <span data-ttu-id="c3e06-114">Tampoco debe alojar otras reuniones, independientemente de su tamaño.</span><span class="sxs-lookup"><span data-stu-id="c3e06-114">It should also not host any other meetings, regardless of the size of the other meetings.</span></span> <span data-ttu-id="c3e06-115">Esto significa que para hospedar reuniones de hasta 1000 usuarios es necesario configurar un grupo de Lync Server independiente dedicado a hospedar grandes reuniones de hasta 1000 usuarios.</span><span class="sxs-lookup"><span data-stu-id="c3e06-115">This means that hosting meetings of up to 1000 users requires setting up a separate Lync Server pool that is dedicated to hosting large meetings of up to 1000 users.</span></span>

<span data-ttu-id="c3e06-116">Un grupo de servidores de Lync Server dedicado a hospedar reuniones grandes debe hospedar una sola reunión de hasta 1000 usuarios al mismo tiempo, por lo que las horas de reunión deben reservarse por adelantado a través de un proceso de programación fuera de banda para garantizar un soporte dedicado desde los servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="c3e06-116">A Lync Server pool that is dedicated to hosting large meetings should host one and only one meeting of up to 1000 users at the same time, so meeting times need to be reserved in advance via an out of band scheduling process to ensure dedicated support from the Front End Servers.</span></span> <span data-ttu-id="c3e06-117">Para admitir más de una gran reunión al mismo tiempo, recomendamos configurar varios grupos de grandes reuniones dedicados.</span><span class="sxs-lookup"><span data-stu-id="c3e06-117">To support more than one large meeting at the same time, we recommend setting up multiple dedicated large-meeting pools.</span></span>

<span data-ttu-id="c3e06-p103">Recomendamos que una persona dedicada ejecute y supervise la parte en línea de una gran reunión. Esta persona podría ser el organizador, el delegado del organizador o presentador, o un miembro del equipo de soporte técnico de la gran reunión, dependiendo de las preferencias de la organización.</span><span class="sxs-lookup"><span data-stu-id="c3e06-p103">We recommend that a dedicated person run and monitor the online portion of a large meeting. This person might be the organizer, delegate of the organizer or presenter, or a member of the dedicated large meeting support team, depending on the organization’s preferences.</span></span>

<span data-ttu-id="c3e06-120">En las secciones siguientes, se describe cómo implementar un grupo dedicado para reuniones grandes, incluidos los procedimientos recomendados para usar Lync Server 2013 para admitir escenarios de reuniones grandes.</span><span class="sxs-lookup"><span data-stu-id="c3e06-120">In the following sections, we describe how to implement a dedicated pool for large meetings, including best practices for using Lync Server 2013 to support large meeting scenarios.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c3e06-121">En esta sección</span><span class="sxs-lookup"><span data-stu-id="c3e06-121">In This Section</span></span>

  - [<span data-ttu-id="c3e06-122">Configuración de la compatibilidad para reuniones grandes en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c3e06-122">Setting up support for large meetings in Lync Server 2013</span></span>](lync-server-2013-setting-up-support-for-large-meetings.md)

  - [<span data-ttu-id="c3e06-123">Administración de reuniones grandes en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c3e06-123">Managing large meetings in Lync Server 2013</span></span>](lync-server-2013-managing-large-meetings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

