---
title: 'Lync Server 2013: proceso de programación de reuniones grandes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Large-meeting scheduling process
ms:assetid: de267458-885f-4176-a8d7-1a218e67640e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205334(v=OCS.15)
ms:contentKeyID: 48185639
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4fb2de8387abb48ad67b8a39bc1ac3ffc353a9b7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514017"
---
# <a name="large-meeting-scheduling-process-in-lync-server-2013"></a><span data-ttu-id="716ae-102">Proceso de programación de reuniones grandes en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="716ae-102">Large-meeting scheduling process in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="716ae-103">_**Última modificación del tema:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="716ae-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="716ae-104">Como solo se admite una única reunión grande en el grupo de servidores exclusivo de la reunión grande, recomendamos que implemente un proceso de programación de reunión grande para que le sea más fácil evitar conflictos en dicha reunión.</span><span class="sxs-lookup"><span data-stu-id="716ae-104">Because only one large meeting at a time is supported on the dedicated large meeting pool, we recommend implementing a large meeting scheduling process to help prevent large meeting conflicts.</span></span> <span data-ttu-id="716ae-105">El objetivo de la programación es facilitar la configuración de las reuniones grandes.</span><span class="sxs-lookup"><span data-stu-id="716ae-105">The purpose of such the scheduling process is to facilitate setting up large meetings.</span></span> <span data-ttu-id="716ae-106">Esta capacidad no la proporcionan directamente los clientes de Lync Server o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="716ae-106">Such capability is not provided directly by Lync Server or Lync Server clients.</span></span> <span data-ttu-id="716ae-107">Para implementar este proceso tiene la posibilidad de usar el sistema de vales del equipo de soporte técnico de la organización, si está disponible.</span><span class="sxs-lookup"><span data-stu-id="716ae-107">One way to implement such a process is to use your organization’s support team’s ticketing system, if available.</span></span>

<span data-ttu-id="716ae-108">Los organizadores de reuniones grandes que deseen programar una de estas reuniones deben ejecutar los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="716ae-108">For organizers of large meetings, scheduling a large meeting involves completing the following steps:</span></span>

1.  <span data-ttu-id="716ae-p102">El organizador de la reunión o el delegado determina la hora, la duración y el tamaño de la próxima reunión, además de presentar una lista de moderadores. Si se anticipa que el tamaño de la reunión va a superar los 250 usuarios o se desea garantizar la mejor experiencia de usuario para una reunión que no supere los 250 usuarios, el organizador o el delegado presentará una solicitud de convocatoria de reunión grande.</span><span class="sxs-lookup"><span data-stu-id="716ae-p102">The meeting organizer or delegate determines the time, duration, and size of an upcoming meeting, in addition to the list of presenters. If the anticipated meeting size exceeds 250 users or to ensure the best user experience for a meeting of fewer than 250 users, the organizer or the delegate submits a request for a large meeting.</span></span>

2.  <span data-ttu-id="716ae-p103">El personal de programación comprobará si la fecha y la hora están disponibles. Como solo admitimos una única reunión grande en el grupo de servidores dedicado a la vez, el personal de programación comprobará el calendario de reuniones grandes para determinar si hay otra reunión programada para la fecha y la hora solicitadas. Si la hora solicitada está disponible, el personal aprobará la solicitud de reunión.</span><span class="sxs-lookup"><span data-stu-id="716ae-p103">The scheduling staff checks to see whether the requested date and time is available. Since we support only a single large meeting on the dedicated pool at a time, the scheduling staff needs to check the large-meeting calendar to determine whether there is another meeting scheduled for the requested date and time. If the requested time is available, the staff approves the meeting request.</span></span>

3.  <span data-ttu-id="716ae-114">Si se aprueba la solicitud, el personal de programación (con credenciales en el grupo dedicado) usa el complemento de reunión en línea para Lync 2013 con Outlook para configurar una reunión en el grupo de reuniones de gran tamaño dedicado.</span><span class="sxs-lookup"><span data-stu-id="716ae-114">If the request is approved, the scheduling staff (using credentials on the dedicated pool) uses Online Meeting Add-in for Lync 2013 with Outlook to set up a meeting on the dedicated large-meeting pool.</span></span> <span data-ttu-id="716ae-115">Como parte del aviso de aprobación, se proporcionará al solicitante la dirección URL que se usará para unirse a la reunión.</span><span class="sxs-lookup"><span data-stu-id="716ae-115">The URL to be used to join the meeting is provided to the requester as part of the approval notice.</span></span>

4.  <span data-ttu-id="716ae-116">El organizador de la reunión o el delegado usa Outlook para programar la próxima reunión, agregando la dirección URL para unirse a la reunión a la invitación a la reunión.</span><span class="sxs-lookup"><span data-stu-id="716ae-116">The meeting organizer or delegate uses Outlook to schedule the upcoming meeting, adding the URL for joining the meeting to the meeting invitation.</span></span> <span data-ttu-id="716ae-117">Después, el organizador de la reunión o el delegado especificará los usuarios que desea invitar y les enviará la invitación.</span><span class="sxs-lookup"><span data-stu-id="716ae-117">The meeting organizer or delegate then specifies the users to be invited and sends out the meeting invitation.</span></span>
    
    <span data-ttu-id="716ae-118">En la figura siguiente se muestra una solicitud y un flujo de trabajo de aprobación típicos para programar grandes reuniones.</span><span class="sxs-lookup"><span data-stu-id="716ae-118">The following figure illustrates a typical request and approval workflow for scheduling large meetings.</span></span>
    
    <span data-ttu-id="716ae-119">![5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d](images/JJ205334.5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d(OCS.15).jpg "5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d")</span><span class="sxs-lookup"><span data-stu-id="716ae-119">![5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d](images/JJ205334.5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d(OCS.15).jpg "5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d")</span></span>  

</div>

<span> </span>

</div>

</div>

</div>

