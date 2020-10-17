---
title: 'Lync Server 2013: informes de uso del sistema'
description: 'Lync Server 2013: informes de uso del sistema.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: System usage reports
ms:assetid: 187d316d-2456-417e-b636-05527a18ef06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558618(v=OCS.15)
ms:contentKeyID: 48183529
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6fffaf22dacbc68958e64090fd4c7d44e32f8ade
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562596"
---
# <a name="system-usage-reports-in-lync-server-2013"></a><span data-ttu-id="44ff9-103">Informes de uso del sistema en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44ff9-103">System usage reports in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="44ff9-104">_**Última modificación del tema:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="44ff9-104">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="44ff9-105">Los informes de uso del sistema proporcionan información sobre el uso del sistema según los datos de registro de detalles de llamadas (CDR) recopilados por el servidor de Lync.</span><span class="sxs-lookup"><span data-stu-id="44ff9-105">The System Usage Reports provide system usage information based on call detail recording (CDR) data collected by the Lync Server.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="44ff9-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="44ff9-106">In This Section</span></span>

  - [<span data-ttu-id="44ff9-107">Informe de registro de usuario en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44ff9-107">User Registration Report in Lync Server 2013</span></span>](lync-server-2013-user-registration-report.md)
    
    <span data-ttu-id="44ff9-108">Proporciona un resumen de la conectividad de usuarios a la implementación de Lync Server 2013 basándose en eventos de registro como los inicios de sesión de usuario.</span><span class="sxs-lookup"><span data-stu-id="44ff9-108">Provides a summary of user connectivity to the Lync Server 2013 deployment based on registration events such as user logons.</span></span> <span data-ttu-id="44ff9-109">El informe proporciona una forma de ver los inicios de sesión internos y externos y comparar el número de usuarios que iniciaron sesión en Lync Server 2013 con el número de usuarios que usaron el servicio en realidad mientras iniciaban sesión.</span><span class="sxs-lookup"><span data-stu-id="44ff9-109">The report provides a way to view both internal and external logons, and to compare the number of users who logged on to Lync Server 2013 with the number of users who actually used the service while they were logged on.</span></span>

  - [<span data-ttu-id="44ff9-110">Informe de Resumen de actividad punto a punto en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44ff9-110">Peer-to-Peer Activity Summary Report in Lync Server 2013</span></span>](lync-server-2013-peer-to-peer-activity-summary-report.md)
    
    <span data-ttu-id="44ff9-p102">Proporciona un resumen de las sesiones punto a punto de mensajería instantánea (MI), audio, vídeo, transferencia de archivos y uso compartido de aplicaciones. Las sesiones punto a punto son sesiones en las que hay solamente dos usuarios.</span><span class="sxs-lookup"><span data-stu-id="44ff9-p102">Provides a summary of peer-to-peer instant messaging (IM), audio, video, file transfer, and application sharing sessions. Peer-to-peer sessions are sessions involving just two users.</span></span>

  - [<span data-ttu-id="44ff9-113">Informe de Resumen de conferencia en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44ff9-113">Conference Summary Report in Lync Server 2013</span></span>](lync-server-2013-conference-summary-report.md)
    
    <span data-ttu-id="44ff9-114">Proporciona un resumen de todas las actividades de conferencia.</span><span class="sxs-lookup"><span data-stu-id="44ff9-114">Provides a summary of all conference activities.</span></span> <span data-ttu-id="44ff9-115">Las conferencias son sesiones en las que hay tres o más usuarios.</span><span class="sxs-lookup"><span data-stu-id="44ff9-115">Conferences are sessions involving three or more people.</span></span>

  - [<span data-ttu-id="44ff9-116">Informe de Resumen de conferencia RTC en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44ff9-116">PSTN Conference Summary Report in Lync Server 2013</span></span>](lync-server-2013-pstn-conference-summary-report.md)
    
    <span data-ttu-id="44ff9-p104">Proporciona un resumen de todas las conferencias RTC. En estas conferencias, al menos un usuario llama mediante la red telefónica conmutada (RTC), lo que también se conoce como *conferencia de acceso telefónico local*.</span><span class="sxs-lookup"><span data-stu-id="44ff9-p104">Provides a summary of all PSTN conferences. These are conferences where at least one user dials in using the public switched telephone network (PSTN), which is also referred to as *dial-in conferencing*.</span></span>

  - [<span data-ttu-id="44ff9-119">Informe de uso del grupo de respuesta en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44ff9-119">Response Group Usage Report in Lync Server 2013</span></span>](lync-server-2013-response-group-usage-report.md)
    
    <span data-ttu-id="44ff9-120">Proporciona un resumen del uso del grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="44ff9-120">Provides a summary of Response Group usage.</span></span> <span data-ttu-id="44ff9-121">La aplicación de grupo de respuesta ofrece una forma de enrutar automáticamente las llamadas telefónicas a entidades, como una línea de asistencia técnica o atención al cliente.</span><span class="sxs-lookup"><span data-stu-id="44ff9-121">The Response Group application provides a way for you to automatically route phone calls to entities such as a help desk or customer support line.</span></span>

  - [<span data-ttu-id="44ff9-122">Informe de inventario de teléfono IP en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44ff9-122">IP Phone Inventory Report in Lync Server 2013</span></span>](lync-server-2013-ip-phone-inventory-report.md)
    
    <span data-ttu-id="44ff9-123">Proporciona información acerca de los teléfonos IP que actualmente se usan en la organización.</span><span class="sxs-lookup"><span data-stu-id="44ff9-123">Provides information about the IP phones currently in use in the organization.</span></span> <span data-ttu-id="44ff9-124">El informe se basa en los inicios de sesión y los registros del teléfono.</span><span class="sxs-lookup"><span data-stu-id="44ff9-124">The report is based on phone registrations and logons.</span></span> <span data-ttu-id="44ff9-125">No se debe tratar como un inventario completo.</span><span class="sxs-lookup"><span data-stu-id="44ff9-125">It should not be considered a complete inventory.</span></span> <span data-ttu-id="44ff9-126">Por ejemplo, es posible que ya no utilice teléfonos que aún se mencionan en el informe (porque iniciaron sesión al menos una vez).</span><span class="sxs-lookup"><span data-stu-id="44ff9-126">For example, you might have removed phones that are still listed in the report because they logged on at least once.</span></span> <span data-ttu-id="44ff9-127">Del mismo modo, es posible que también tenga teléfonos nuevos que no aparezcan en el informe simplemente porque los usuarios no han iniciado sesión en Lync Server con sus nuevos teléfonos todavía.</span><span class="sxs-lookup"><span data-stu-id="44ff9-127">Likewise, you might also have new phones that do not show up in the report simply because users have not logged on to Lync Server with their new phones yet.</span></span>

  - [<span data-ttu-id="44ff9-128">Informe de control de admisión de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44ff9-128">Call Admission Control Report in Lync Server 2013</span></span>](lync-server-2013-call-admission-control-report.md)
    
    <span data-ttu-id="44ff9-p107">Proporciona una lista de actividades punto a punto y de conferencia que utilizan el servicio de control de admisión de llamadas. El control de admisión de llamadas (CAC) es una forma de determinar, en función de las restricciones de ancho de banda, si está permitido establecer sesiones de comunicación en tiempo real, como las llamadas de voz o vídeo.</span><span class="sxs-lookup"><span data-stu-id="44ff9-p107">Provides a list of peer-to-peer and conference activities that use call admission control. Call admission control (CAC) is a way of determining whether you should allow real-time communications sessions, such as voice or video calls, based on bandwidth constraints.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

