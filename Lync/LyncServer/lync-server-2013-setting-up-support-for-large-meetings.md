---
title: 'Lync Server 2013: configuración de soporte técnico para reuniones grandes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up support for large meetings
ms:assetid: 8e22d34b-b395-408d-9d48-8f2a3abe9513
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205074(v=OCS.15)
ms:contentKeyID: 48184763
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e8331c28d5bd06e6a3f7d9dab2fba7db334cd00
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764566"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-support-for-large-meetings-in-lync-server-2013"></a><span data-ttu-id="da361-102">Configurar la compatibilidad para reuniones grandes en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="da361-102">Setting up support for large meetings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="da361-103">_**Última modificación del tema:** 2014-05-12_</span><span class="sxs-lookup"><span data-stu-id="da361-103">_**Topic Last Modified:** 2014-05-12_</span></span>

<span data-ttu-id="da361-104">La compatibilidad con las reuniones de gran tamaño de hasta 1000 usuarios requiere la creación de una topología adecuada, la satisfacción de los requisitos previos de hardware y software, y la configuración adecuada del entorno.</span><span class="sxs-lookup"><span data-stu-id="da361-104">Supporting large meetings of up to 1000 users requires creating an appropriate topology, meeting hardware and software prerequisites, and configuring the environment appropriately.</span></span>

<div>

## <a name="topology-requirements"></a><span data-ttu-id="da361-105">Requisitos de topología</span><span class="sxs-lookup"><span data-stu-id="da361-105">Topology Requirements</span></span>

<span data-ttu-id="da361-106">Una única reunión grande requiere al menos un servidor front-end y un servidor back-end.</span><span class="sxs-lookup"><span data-stu-id="da361-106">A single large meeting requires at least one Front End Server and one Back End Server.</span></span> <span data-ttu-id="da361-107">Sin embargo, para ofrecer una alta disponibilidad, recomendamos un grupo de servidores front-end con servidores de back-end duplicados.</span><span class="sxs-lookup"><span data-stu-id="da361-107">However, to provide high availability, we recommend a two Front End Server pool with mirrored Back End Servers.</span></span>

<span data-ttu-id="da361-108">El usuario que hospede las reuniones grandes debe tener su cuenta de usuario alojada en este grupo.</span><span class="sxs-lookup"><span data-stu-id="da361-108">The user who hosts the large meetings must have their user account homed in this pool.</span></span> <span data-ttu-id="da361-109">Pero, no se recomienda hospedar otras cuentas de usuario en este grupo.</span><span class="sxs-lookup"><span data-stu-id="da361-109">However, we do not recommend that you host other user accounts in this pool.</span></span> <span data-ttu-id="da361-110">Úselo solo para reuniones grandes.</span><span class="sxs-lookup"><span data-stu-id="da361-110">Instead, use it only for the large meetings.</span></span> <span data-ttu-id="da361-111">El procedimiento recomendado es crear una cuenta de usuario especial en este grupo y usarla solo para hospedar reuniones grandes.</span><span class="sxs-lookup"><span data-stu-id="da361-111">The best practice is to create a special user account in this pool to be used only to host large meetings.</span></span> <span data-ttu-id="da361-112">Como la configuración de las reuniones grandes se optimiza para el rendimiento, al utilizarla como un usuario normal podría tener problemas como la imposibilidad de promover una sesión P2P a una reunión cuando hay un extremo RTC involucrado.</span><span class="sxs-lookup"><span data-stu-id="da361-112">Since the large meeting setting is optimized for performance, using it as a normal user could have problems such as the inability to promote a P2P session to a meeting when a PSTN endpoint is involved.</span></span>

<span data-ttu-id="da361-113">Administrar un grupo con exactamente dos servidores front-end requiere algunas consideraciones especiales.</span><span class="sxs-lookup"><span data-stu-id="da361-113">Managing a pool with exactly two Front End Servers requires some special considerations.</span></span> <span data-ttu-id="da361-114">Para obtener más información, vea [topologías y componentes para servidores front-end, mensajería instantánea y presencia en Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span><span class="sxs-lookup"><span data-stu-id="da361-114">For more information, see [Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span></span>

<span data-ttu-id="da361-115">Además, si desea proporcionar la opción de recuperación ante desastres y conmutación por error para el grupo que se usa para las reuniones grandes, puede asociarlo a un grupo dedicado con una configuración similar y datos diferentes.</span><span class="sxs-lookup"><span data-stu-id="da361-115">Additionally, if you want to optionally provide disaster recovery backup and failover for the pool used for large meetings, you can pair it with a similarly set up dedicated pool in a different data center.</span></span> <span data-ttu-id="da361-116">Para obtener más información, vea [planear la alta disponibilidad y la recuperación ante desastres en Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="da361-116">For details, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

<span data-ttu-id="da361-117">![Configuración de grupo de servidores para reuniones grandes](images/JJ205074.ee00e1c0-c3b2-464d-aa89-a1e877cd034d(OCS.15).jpg "Configuración de grupo de servidores para reuniones grandes")</span><span class="sxs-lookup"><span data-stu-id="da361-117">![Large Meetings pool configuration](images/JJ205074.ee00e1c0-c3b2-464d-aa89-a1e877cd034d(OCS.15).jpg "Large Meetings pool configuration")</span></span>

<span data-ttu-id="da361-118">Las siguientes son notas adicionales sobre la topología:</span><span class="sxs-lookup"><span data-stu-id="da361-118">Additional notes about the topology include:</span></span>

  - <span data-ttu-id="da361-119">Se necesita un recurso compartido de archivos para almacenar el contenido de la reunión y, si el servidor de archivado está implementado y habilitado, para el archivado de los archivos.</span><span class="sxs-lookup"><span data-stu-id="da361-119">A file share is required for storing meeting content and, if Archiving Server is deployed and enabled, for storing the archiving files.</span></span> <span data-ttu-id="da361-120">El recurso compartido de archivos puede estar dedicado al grupo o puede ser el mismo recurso compartido de archivos que usa otro grupo del sitio en el que el grupo está implementado.</span><span class="sxs-lookup"><span data-stu-id="da361-120">The file share can be dedicated to the pool or can be the same file share used by another pool at the site in which the pool is deployed.</span></span> <span data-ttu-id="da361-121">Para obtener más información sobre cómo configurar el recurso compartido de archivos, consulte [configurar el almacenamiento de archivos para Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md).</span><span class="sxs-lookup"><span data-stu-id="da361-121">For details about configuring the file share, see [Configure file storage for Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md).</span></span>

  - <span data-ttu-id="da361-122">Se necesita un servidor de Office Web Apps para habilitar la funcionalidad de presentación de PowerPoint en reuniones grandes.</span><span class="sxs-lookup"><span data-stu-id="da361-122">A Office Web Apps Server is required for enabling the PowerPoint presentation functionality in large meetings.</span></span> <span data-ttu-id="da361-123">El servidor de Office Web Apps se puede dedicar al grupo de reuniones de gran tamaño o puede ser el mismo servidor de Office Web Apps usado por otros grupos en el sitio en el que se implementa el grupo dedicado.</span><span class="sxs-lookup"><span data-stu-id="da361-123">The Office Web Apps Server can be dedicated to the large meeting pool or, it can be the same Office Web Apps Server used by other pools at the site in which the dedicated pool is deployed.</span></span>

  - <span data-ttu-id="da361-124">El equilibrio de carga de los servidores front-end requiere equilibrio de carga de hardware para el tráfico HTTP (como la descarga de contenido de la reunión).</span><span class="sxs-lookup"><span data-stu-id="da361-124">Load balancing of the Front End Servers requires hardware load balancing for the HTTP traffic (such as meeting content download).</span></span> <span data-ttu-id="da361-125">El equilibrio de carga de DNS se recomienda para el tráfico SIP.</span><span class="sxs-lookup"><span data-stu-id="da361-125">DNS load balancing is recommended for SIP traffic.</span></span> <span data-ttu-id="da361-126">Para obtener información detallada, consulte [requisitos de equilibrio de carga para Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="da361-126">For details see [Load balancing requirements for Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span></span>

  - <span data-ttu-id="da361-127">Si desea usar el servidor de supervisión para el grupo de reuniones de gran tamaño dedicado, le recomendamos que use el servidor de supervisión y su base de datos que se comparten en todos los grupos de servidores front-end de su implementación de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="da361-127">If you want to use Monitoring Server for the dedicated large-meeting pool, we recommend using the Monitoring Server and its database that are shared across all of the Front End Server pools in your Lync Server deployment.</span></span>

</div>

<div>

## <a name="hardware-and-software-requirements"></a><span data-ttu-id="da361-128">Requisitos de hardware y software</span><span class="sxs-lookup"><span data-stu-id="da361-128">Hardware and Software Requirements</span></span>

<span data-ttu-id="da361-129">Los requisitos de hardware de los servidores de un grupo de reuniones grande dedicado son los mismos que los de los otros servidores de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="da361-129">The hardware requirements for servers in a dedicated large-meeting pool are the same as for your other Lync Server 2013 servers.</span></span> <span data-ttu-id="da361-130">Para obtener más información sobre los requisitos de hardware, vea "[plataformas de hardware de servidor para Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span><span class="sxs-lookup"><span data-stu-id="da361-130">For details about hardware requirements, see "[Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

<span data-ttu-id="da361-131">Los servidores de un grupo de reuniones dedicado de gran tamaño deben cumplir todos los requisitos de software de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="da361-131">Servers in a dedicated large-meeting pool must meet all Lync Server 2013 software requirements.</span></span> <span data-ttu-id="da361-132">Para obtener más información sobre los requisitos de software, consulte la siguiente documentación:</span><span class="sxs-lookup"><span data-stu-id="da361-132">For details about software requirements, please see the following documentation:</span></span>

  - [<span data-ttu-id="da361-133">Compatibilidad del sistema operativo con el servidor y las herramientas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="da361-133">Server and tools operating system support in Lync Server 2013</span></span>](lync-server-2013-server-and-tools-operating-system-support.md)

  - [<span data-ttu-id="da361-134">Compatibilidad con software de base de datos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="da361-134">Database software support in Lync Server 2013</span></span>](lync-server-2013-database-software-support.md)

  - [<span data-ttu-id="da361-135">Requisitos adicionales de software para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="da361-135">Additional software requirements for Lync Server 2013</span></span>](lync-server-2013-additional-software-requirements.md)

<span data-ttu-id="da361-136">Además, tanto Lync Server 2013 como todos los clientes de Lync Server 2013 deben tener las actualizaciones más recientes.</span><span class="sxs-lookup"><span data-stu-id="da361-136">Additionally, both Lync Server 2013 and all Lync Server 2013 clients must have the latest updates.</span></span>

</div>

<div>

## <a name="configuration-requirements"></a><span data-ttu-id="da361-137">Requisitos de configuración</span><span class="sxs-lookup"><span data-stu-id="da361-137">Configuration Requirements</span></span>

<span data-ttu-id="da361-138">Le recomendamos crear una nueva Directiva de conferencia específicamente para reuniones grandes y, a continuación, asignar la Directiva de conferencia a los usuarios alojados en el grupo de reuniones de gran tamaño dedicado.</span><span class="sxs-lookup"><span data-stu-id="da361-138">We recommend creating a new conferencing policy specifically for large meetings, and then assigning the conferencing policy to the users who are homed on the dedicated large-meeting pool.</span></span> <span data-ttu-id="da361-139">Configure la directiva de conferencias por medio de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="da361-139">Configure the conferencing policy using the following settings:</span></span>

  - <span data-ttu-id="da361-140">Establezca la opción **MaxMeetingSize** en **1000**.</span><span class="sxs-lookup"><span data-stu-id="da361-140">Set the **MaxMeetingSize** option to **1000**.</span></span> <span data-ttu-id="da361-141">(El valor predeterminado es **250**).</span><span class="sxs-lookup"><span data-stu-id="da361-141">(The default is **250**.)</span></span>

  - <span data-ttu-id="da361-142">Establezca la opción **AllowLargeMeetings** en **True**.</span><span class="sxs-lookup"><span data-stu-id="da361-142">Set the **AllowLargeMeetings** option to **True**.</span></span>

  - <span data-ttu-id="da361-143">Establezca la opción **EnableAppDesktopSharing** en **None**.</span><span class="sxs-lookup"><span data-stu-id="da361-143">Set the **EnableAppDesktopSharing** option to **None**.</span></span>

  - <span data-ttu-id="da361-144">Establezca la opción **AllowUserToScheduleMeetingsWithAppSharing** en **False**.</span><span class="sxs-lookup"><span data-stu-id="da361-144">Set the **AllowUserToScheduleMeetingsWithAppSharing** option to **False**.</span></span>

  - <span data-ttu-id="da361-145">Establezca la opción **AllowSharedNotes** en **False**.</span><span class="sxs-lookup"><span data-stu-id="da361-145">Set the **AllowSharedNotes** option to **False**.</span></span>

  - <span data-ttu-id="da361-146">Establezca la opción **AllowAnnotations** en **False**.</span><span class="sxs-lookup"><span data-stu-id="da361-146">Set the **AllowAnnotations** option to **False**.</span></span>

  - <span data-ttu-id="da361-147">Establezca la opción **DisablePowerPointAnnotations** en **True**.</span><span class="sxs-lookup"><span data-stu-id="da361-147">Set the **DisablePowerPointAnnotations** option to **True**.</span></span>

  - <span data-ttu-id="da361-148">Establezca la opción **AllowMultiview** en **False**.</span><span class="sxs-lookup"><span data-stu-id="da361-148">Set the **AllowMultiview** option to **False**.</span></span>

  - <span data-ttu-id="da361-149">Establezca la opción **EnableMultiviewJoin** en **False**.</span><span class="sxs-lookup"><span data-stu-id="da361-149">Set the **EnableMultiviewJoin** option to **False**.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="da361-150">El soporte técnico para las reuniones de gran tamaño del usuario de 1000 en Lync Server 2013 requiere que el valor <STRONG>AllowLargeMeetings</STRONG> de la Directiva de conferencia para el programador de reuniones se establezca en true.</span><span class="sxs-lookup"><span data-stu-id="da361-150">The support for 1000 user large meetings in Lync Server 2013 requires the <STRONG>AllowLargeMeetings</STRONG> setting in the conferencing policy for the meeting scheduler to be set to true.</span></span> <span data-ttu-id="da361-151">Cuando esta configuración se establece en true, la experiencia de Lync se optimizará para las reuniones extra grandes cuando los usuarios se unan a la reunión.</span><span class="sxs-lookup"><span data-stu-id="da361-151">When this setting is set to true, the Lync experience will be optimized for extra large meetings when users joins such meeting.</span></span> <span data-ttu-id="da361-152">En concreto, en una reunión grande, Lync no mostrará el inicio ni la actualización de la lista completa de participantes de la reunión, que es un cuello de botella de rendimiento para el cliente y Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="da361-152">Specifically, in a large meeting, Lync will not show the initial or update of the full meeting participant list, which is a performance bottleneck for both the client and Lync Server 2013.</span></span> <span data-ttu-id="da361-153">En su lugar, Lync solo mostrará información sobre el usuario y la lista de moderadores de la reunión.</span><span class="sxs-lookup"><span data-stu-id="da361-153">Instead, Lync will only show information about the user and the list of presenters of the meeting.</span></span> <span data-ttu-id="da361-154">Lync seguirá correctamente el número total de participantes disponibles en las reuniones grandes.</span><span class="sxs-lookup"><span data-stu-id="da361-154">Lync will still properly shows total number of participants available in the large meetings.</span></span>



</div>

<span data-ttu-id="da361-155">Excepto en la opción **Tamaño máximo de la reunión**, todas las demás opciones de la directiva de conferencia aquí especificadas son necesarias para deshabilitar las funciones de conferencia que no se necesitan en reuniones grandes.</span><span class="sxs-lookup"><span data-stu-id="da361-155">Except for the **Maximum meeting size** setting, all the other conferencing policy settings specified here are required in order to disable conferencing capabilities that are not necessary in large meetings.</span></span>

<span data-ttu-id="da361-156">Además, debe configurar el grupo de reuniones dedicado de gran tamaño para que todos los usuarios de Lync Server 2013 alojados en el grupo y responsables de administrar la programación de la reunión tengan los permisos apropiados.</span><span class="sxs-lookup"><span data-stu-id="da361-156">Additionally, you need to configure the dedicated large-meeting pool so that each Lync Server 2013 user that is homed on the pool and responsible for managing the meeting schedule has the appropriate permissions.</span></span> <span data-ttu-id="da361-157">Para ello, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="da361-157">To do this, do the following:</span></span>

  - <span data-ttu-id="da361-p114">Establezca la opción **Designar como moderador** en **Ninguno**. Normalmente, uno o varios participantes en una reunión grande son moderadores, por lo que los participantes no tienen que ser admitidos automáticamente como moderadores en las reuniones grandes. En su lugar, los moderadores necesitan designarse explícitamente en el momento de programar la reunión o promoverse explícitamente durante la reunión grande.</span><span class="sxs-lookup"><span data-stu-id="da361-p114">Set the **Designate as presenter** option to **None**. Typically, one or just a few users of all the participants of a large meeting are presenters, so participants should not be automatically admitted to large meetings as presenters. Instead, the presenters should be explicitly designated at meeting scheduling time, or be explicitly promoted during the large meeting.</span></span>

  - <span data-ttu-id="da361-161">Asegúrese de que la casilla **Tipo de conferencia asignada de forma predeterminada** no esté activada.</span><span class="sxs-lookup"><span data-stu-id="da361-161">Make sure that the **Assigned conference type by default** check box is not selected.</span></span> <span data-ttu-id="da361-162">Esta configuración controla si el complemento de reunión en línea para Lync 2013 siempre programa las conferencias con la Conferencia asignada al organizador, lo que significa que las reuniones programadas tienen la misma dirección URL de la combinación y la información de audio.</span><span class="sxs-lookup"><span data-stu-id="da361-162">This setting controls whether the Online Meeting Add-in for Lync 2013 always schedules conferences using the organizer’s assigned conference, which means that scheduled meetings have the same join URL and audio information.</span></span> <span data-ttu-id="da361-163">En escenarios de colaboración de grupos pequeños, este tipo de conferencia asignada funciona bien porque todos tienen su propia conferencia asignada individual y la dirección URL de unión y la información de audio constantes ayudan a unirse rápidamente a la reunión.</span><span class="sxs-lookup"><span data-stu-id="da361-163">In small group collaboration scenarios, having such assigned conference type works well because everyone has their own individual assigned conference, and the constant join URL and audio information helps to facilitate faster meeting joining.</span></span> <span data-ttu-id="da361-164">Pero, en un escenario de reuniones grandes, el personal de soporte de reuniones grandes programa las reuniones usando un único conjunto de credenciales y después proporciona las direcciones URL de unión y la información de audio a los convocantes de la reunión.</span><span class="sxs-lookup"><span data-stu-id="da361-164">However, in the large-meeting scenario, the large meeting support staff schedules the large meetings using a single set of user credentials, and then provides join URLs and audio information to the meeting requesters.</span></span> <span data-ttu-id="da361-165">En este caso, usar una dirección URL diferente para unirse a cada reunión funciona mejor.</span><span class="sxs-lookup"><span data-stu-id="da361-165">In this case, using a different URL to join each meeting works better.</span></span>

  - <span data-ttu-id="da361-166">Asegúrese de que la casilla **Admitir usuarios anónimos de forma predeterminada** no esté activada a menos que se necesite.</span><span class="sxs-lookup"><span data-stu-id="da361-166">Ensure that the **Admit anonymous users by default** check box is not selected, unless it is required.</span></span> <span data-ttu-id="da361-167">Esta configuración afecta al tipo de acceso a la reunión predeterminado programado por el complemento de reunión en línea para Lync 2013 cuando no se usa una conferencia asignada.</span><span class="sxs-lookup"><span data-stu-id="da361-167">This setting affects the default meeting access type scheduled by the Online Meeting Add-in for Lync 2013 when not using an assigned conference.</span></span> <span data-ttu-id="da361-168">La opción apropiada para esta opción depende de las necesidades de su organización.</span><span class="sxs-lookup"><span data-stu-id="da361-168">The appropriate option for this setting depends on your organization’s needs.</span></span> <span data-ttu-id="da361-169">Si la mayoría de las reuniones grandes de su organización son reuniones internas, no active esta opción.</span><span class="sxs-lookup"><span data-stu-id="da361-169">If most large meetings for your organization are internal meetings, do not select this option.</span></span> <span data-ttu-id="da361-170">Si la mayoría de las reuniones grandes requiere que los usuarios externos puedan unirse, active esta opción.</span><span class="sxs-lookup"><span data-stu-id="da361-170">If most large meetings require that external users be able to join, select this option.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

