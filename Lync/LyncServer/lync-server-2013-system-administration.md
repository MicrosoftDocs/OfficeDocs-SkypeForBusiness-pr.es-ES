---
title: 'Lync Server 2013: administración del sistema'
description: 'Lync Server 2013: administración del sistema.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: System administration
ms:assetid: 063eb962-b96a-4699-8579-bb7125112df4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720318(v=OCS.15)
ms:contentKeyID: 63969577
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b56271d8d90f1d83072af0577692be1ea0b5bc7e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562686"
---
# <a name="system-administration-in-lync-server-2013"></a><span data-ttu-id="2bf9d-103">Administración del sistema en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2bf9d-103">System administration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2bf9d-104">_**Última modificación del tema:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="2bf9d-104">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="2bf9d-105">La administración del sistema incluye las tareas administrativas diarias, tanto planificadas como a petición, que son necesarias para mantener un sistema de ti funcionando sin problemas.</span><span class="sxs-lookup"><span data-stu-id="2bf9d-105">System administration includes the day-to-day administrative tasks, both planned and on-demand, that are required to keep an IT system operating smoothly.</span></span> <span data-ttu-id="2bf9d-106">Normalmente, las tareas de administración del sistema se cubren mediante procedimientos escritos.</span><span class="sxs-lookup"><span data-stu-id="2bf9d-106">Typically, system administration tasks are covered by written procedures.</span></span> <span data-ttu-id="2bf9d-107">Estos procedimientos ayudan a garantizar que todos los miembros del personal de soporte usan las mismas herramientas y métodos estándar.</span><span class="sxs-lookup"><span data-stu-id="2bf9d-107">These procedures help ensure that the same standard tools and methods are used by all support staff.</span></span>

<span data-ttu-id="2bf9d-108">En un entorno de Lync, las tareas típicas de administración del sistema incluyen la copia de seguridad y archivado de los grupos, los registros de supervisión, la creación y administración de usuarios y la actualización del software antivirus.</span><span class="sxs-lookup"><span data-stu-id="2bf9d-108">In a Lync environment, typical system administration tasks include backing up and archiving pools, monitoring logs, creating and managing users, and updating antivirus software.</span></span>

<div>

## <a name="system-troubleshooting"></a><span data-ttu-id="2bf9d-109">Solución de problemas del sistema</span><span class="sxs-lookup"><span data-stu-id="2bf9d-109">System troubleshooting</span></span>

<span data-ttu-id="2bf9d-110">Una organización debe estar preparada para tratar problemas inesperados y debe tener un procedimiento para administrar los problemas desde el punto en el que se informa hasta su resolución.</span><span class="sxs-lookup"><span data-stu-id="2bf9d-110">An organization must be prepared to deal with unexpected issues and should have a procedure to manage issues from the point at which they are reported until their resolution.</span></span> <span data-ttu-id="2bf9d-111">La información acerca de cómo el personal de soporte ha diagnosticado un problema debe registrarse y usarse en el futuro para evitar la repetición del trabajo completado innecesariamente.</span><span class="sxs-lookup"><span data-stu-id="2bf9d-111">Information about how support staff diagnosed an issue should be recorded and used in the future to avoid unnecessarily repeating completed work.</span></span>

</div>

<div>

## <a name="system-troubleshooting-process"></a><span data-ttu-id="2bf9d-112">Proceso de solución de problemas del sistema</span><span class="sxs-lookup"><span data-stu-id="2bf9d-112">System troubleshooting process</span></span>

<span data-ttu-id="2bf9d-113">En el siguiente diagrama se muestra el proceso de solución de problemas del sistema y las interacciones con otros roles de operaciones.</span><span class="sxs-lookup"><span data-stu-id="2bf9d-113">The following diagram shows the system troubleshooting process and the interactions with other operations roles.</span></span>

<span data-ttu-id="2bf9d-114">**Diagrama de solución de problemas del sistema**</span><span class="sxs-lookup"><span data-stu-id="2bf9d-114">**System troubleshooting flowchart**</span></span>

<span data-ttu-id="2bf9d-115">![Diagrama de solución de problemas del sistema](images/Dn720318.869d0b89-6473-4b1f-9d90-59604b4b8e98(OCS.15).jpg "Diagrama de solución de problemas del sistema")</span><span class="sxs-lookup"><span data-stu-id="2bf9d-115">![System Troubleshooting Flowchart](images/Dn720318.869d0b89-6473-4b1f-9d90-59604b4b8e98(OCS.15).jpg "System Troubleshooting Flowchart")</span></span>

  - <span data-ttu-id="2bf9d-116">**Clasificar y establecer prioridades**     Esta tarea suele realizarla el servicio de asistencia al cliente.</span><span class="sxs-lookup"><span data-stu-id="2bf9d-116">**Classify and Prioritize**   This task is typically performed by the service desk.</span></span> <span data-ttu-id="2bf9d-117">Por ejemplo, un problema se puede agrupar como un problema de software o un problema de hardware.</span><span class="sxs-lookup"><span data-stu-id="2bf9d-117">For example, an issue may be grouped as a software issue or a hardware issue.</span></span> <span data-ttu-id="2bf9d-118">A continuación, el problema se enruta al equipo de soporte técnico adecuado para su investigación.</span><span class="sxs-lookup"><span data-stu-id="2bf9d-118">The issue is then routed to the appropriate support team for investigation.</span></span> <span data-ttu-id="2bf9d-119">Las reglas para determinar la prioridad de un problema, junto con el tiempo para responder y la hora de resolución, se suelen definir en el SLA.</span><span class="sxs-lookup"><span data-stu-id="2bf9d-119">The rules for determining the priority of an issue, together with the time to respond and time to resolve, are typically defined in the SLA.</span></span>

  - <span data-ttu-id="2bf9d-120">**Investigar y diagnosticar**     El equipo de soporte técnico adecuado diagnostica el problema y propone cambios para resolver el problema.</span><span class="sxs-lookup"><span data-stu-id="2bf9d-120">**Investigate and Diagnose**   The appropriate support team diagnoses the issue and proposes changes to resolve the issue.</span></span> <span data-ttu-id="2bf9d-121">Si la solución es sencilla y no requiere control de cambios, la solución puede aplicarse de inmediato.</span><span class="sxs-lookup"><span data-stu-id="2bf9d-121">If the solution is simple and does not require change control, the solution can be applied immediately.</span></span> <span data-ttu-id="2bf9d-122">Si la solución no es sencilla, debe producirse una solicitud de cambio y el proceso de administración de cambios debe administrar el trabajo propuesto, con frecuencia en un procedimiento de "rápido seguimiento".</span><span class="sxs-lookup"><span data-stu-id="2bf9d-122">If the solution is not easy, a request for change should be raised and the proposed work should be managed by the change management process, frequently under a “fast-track” procedure.</span></span> <span data-ttu-id="2bf9d-123">Los cambios que se realicen deben registrarse mediante el proceso de administración de la configuración.</span><span class="sxs-lookup"><span data-stu-id="2bf9d-123">Any changes that are made should be recorded using the configuration management process.</span></span>

  - <span data-ttu-id="2bf9d-124">**Cerrar y grabar**     Después de probar la resolución, debe cerrarse el problema.</span><span class="sxs-lookup"><span data-stu-id="2bf9d-124">**Close and Record**   After testing the resolution, the issue should be closed.</span></span> <span data-ttu-id="2bf9d-125">Si hay lecciones que hay que aprender a partir del problema, debe crearse una entrada en la base de conocimientos.</span><span class="sxs-lookup"><span data-stu-id="2bf9d-125">If there are lessons to be learned from the issue, an entry should be created in the knowledge base.</span></span>

  - <span data-ttu-id="2bf9d-126">**Revisión y análisis**     de tendencias Deben realizarse revisiones periódicas de los problemas recientes para identificar las tendencias de problemas.</span><span class="sxs-lookup"><span data-stu-id="2bf9d-126">**Review and Trend Analysis**   Periodic reviews of recent issues should be performed to identify issue trends.</span></span> <span data-ttu-id="2bf9d-127">Por ejemplo, si los usuarios experimentan problemas frecuentes con inicios de sesión lentos en sus sitios de Lync, los problemas de ancho de banda de red podrían ser la causa.</span><span class="sxs-lookup"><span data-stu-id="2bf9d-127">For example, if the users are experiencing frequent issues with slow logons to their Lync sites, network bandwidth issues may be the cause.</span></span> <span data-ttu-id="2bf9d-128">Los tiempos de resolución del problema y el efecto de las interrupciones en la disponibilidad del sistema deben revisarse y compararse con el SLA.</span><span class="sxs-lookup"><span data-stu-id="2bf9d-128">Issue resolution times and the effect of any outages on system availability should be reviewed and compared with the SLA.</span></span> <span data-ttu-id="2bf9d-129">La persona que relacionarse con el cliente sobre problemas del servicio, como un administrador de cuentas, debe ser informada de problemas importantes.</span><span class="sxs-lookup"><span data-stu-id="2bf9d-129">The person who liaises with the customer on service issues, such as an account manager, should be informed of any significant issues.</span></span>

</div>

<div>

## <a name="issue-management-tools"></a><span data-ttu-id="2bf9d-130">Herramientas de administración de problemas</span><span class="sxs-lookup"><span data-stu-id="2bf9d-130">Issue management tools</span></span>

<span data-ttu-id="2bf9d-131">Las herramientas del servicio de asistencia al cliente permiten que el personal registre, clasifique y priorice los nuevos problemas.</span><span class="sxs-lookup"><span data-stu-id="2bf9d-131">Service desk tools enable staff to record, classify, and prioritize new issues.</span></span> <span data-ttu-id="2bf9d-132">A continuación, las herramientas proporcionan los procesos de flujo de trabajo para administrar la solicitud del servicio Issue a través de investigación y diagnóstico, a menudo por más de un equipo de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="2bf9d-132">Tools will then provide the workflow processes to manage the issue service request through investigation and diagnosis, often by more than one support team.</span></span> <span data-ttu-id="2bf9d-133">Las herramientas, que a menudo proporcionarán informes sobre los tiempos de resolución y las tendencias históricas, también pueden incluir una base de datos de Knowledge base, que se puede usar para buscar en problemas anteriores.</span><span class="sxs-lookup"><span data-stu-id="2bf9d-133">Tools, which will frequently provide reports about resolution times and historical trends, may also include a knowledge base database, which can be used to search through past issues.</span></span>

<span data-ttu-id="2bf9d-134">Microsoft Knowledge base es un registro útil de los problemas de soporte técnico que ha encontrado Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2bf9d-134">The Microsoft Knowledge Base is a useful record of support issues that were encountered by Microsoft.</span></span> <span data-ttu-id="2bf9d-135">Para obtener más información, vea el sitio web de soporte técnico de Microsoft ( <https://go.microsoft.com/fwlink/?linkid=14898> ).</span><span class="sxs-lookup"><span data-stu-id="2bf9d-135">For more information, see the Microsoft Support website (<https://go.microsoft.com/fwlink/?linkid=14898>).</span></span>

<span data-ttu-id="2bf9d-136">El software de terceros suele requerir personalización para satisfacer las necesidades de la organización, como la organización de los equipos, los requisitos de informes y las medidas que requiere el SLA.</span><span class="sxs-lookup"><span data-stu-id="2bf9d-136">Third-party software typically requires customization to suit the organization’s needs, such as the organization of teams, reporting requirements, and measures required by the SLA.</span></span>

</div>

<div>

## <a name="centralized-vs-decentralized-administration"></a><span data-ttu-id="2bf9d-137">Administración centralizada frente a la administración descentralizada</span><span class="sxs-lookup"><span data-stu-id="2bf9d-137">Centralized vs. decentralized administration</span></span>

<span data-ttu-id="2bf9d-138">Los roles y las responsabilidades para realizar tareas de administración de sistemas dependen de si la organización sigue un modelo centralizado, un modelo descentralizado o una combinación de ambos.</span><span class="sxs-lookup"><span data-stu-id="2bf9d-138">Roles and responsibilities for performing system administration tasks depend on whether the organization follows a centralized model, a decentralized model, or a combination of both.</span></span>

  - <span data-ttu-id="2bf9d-139">**Modelo**     centralizado En un modelo centralizado, uno o varios grupos administrativos mantienen un control completo de todo el entorno de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2bf9d-139">**Centralized Model**   In a centralized model, one or several administrative groups maintain complete control of the whole Lync Server environment.</span></span> <span data-ttu-id="2bf9d-140">Este modelo administrativo se asemeja a un centro de datos en el que todas las tareas de administración las realiza un solo grupo de tecnología de la información.</span><span class="sxs-lookup"><span data-stu-id="2bf9d-140">This administrative model resembles a data center where all administration tasks are performed by a single information technology group.</span></span> <span data-ttu-id="2bf9d-141">Las funciones y las responsabilidades del equipo se deben definir en función de la experiencia y los conocimientos.</span><span class="sxs-lookup"><span data-stu-id="2bf9d-141">Roles and responsibilities within the team should be defined according to experience and expertise.</span></span>

  - <span data-ttu-id="2bf9d-142">Modelo descentralizado **Decentralized Model**     Las organizaciones descentralizadas se encuentran en varias ubicaciones geográficas y tienen servidores de Lync Server y equipos de administradores en diferentes ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="2bf9d-142">**Decentralized Model**   Decentralized organizations are located in several geographic locations and have functioning Lync Server servers and teams of administrators in different locations.</span></span> <span data-ttu-id="2bf9d-143">Por ejemplo, puede que haya personal de administración local y uno o más servidores que ejecuten Lync Server 2013 para cada país o región.</span><span class="sxs-lookup"><span data-stu-id="2bf9d-143">For example, there may be local administration staff and one or more servers that are running Lync Server 2013 for each country/region.</span></span> <span data-ttu-id="2bf9d-144">O bien, puede haber un grupo de servidores que ejecuten Lync Server 2013 y un equipo administrativo para Norteamérica y otro para Europa.</span><span class="sxs-lookup"><span data-stu-id="2bf9d-144">Or, there may be a pool of servers that are running Lync Server 2013 and an administrative team for North America and one for Europe.</span></span> <span data-ttu-id="2bf9d-145">A veces, es posible que desee que los administradores se encarguen solo en su propio área geográfica y restrinjan los permisos para administrar los recursos en otras áreas.</span><span class="sxs-lookup"><span data-stu-id="2bf9d-145">Sometimes, you may want administrators to be responsible only for their own geographical area and restrict permissions to administer resources in other areas.</span></span>

<span data-ttu-id="2bf9d-146">Lync Server también le permite delegar tareas administrativas específicas a personas o grupos específicos mediante el control de acceso basado en roles (RBAC).</span><span class="sxs-lookup"><span data-stu-id="2bf9d-146">Lync Server also allows you to delegate specific administrative tasks to specific people or groups by using role-based access control (RBAC).</span></span> <span data-ttu-id="2bf9d-147">RBAC permite a los administradores delegar derechos de usuario y permisos específicos a otros administradores para que realicen un subconjunto de las tareas administrativas posibles.</span><span class="sxs-lookup"><span data-stu-id="2bf9d-147">RBAC allows administrators to delegate specific user rights and permissions to other administrators to perform a subset of the administrative tasks possible.</span></span> <span data-ttu-id="2bf9d-148">Mediante RBAC, la capacidad del usuario para realizar tareas administrativas específicas depende de los roles RBAC asignados al usuario.</span><span class="sxs-lookup"><span data-stu-id="2bf9d-148">By using RBAC, the user’s ability to perform specific administrative tasks depends on the RBAC roles that are assigned to the user.</span></span> <span data-ttu-id="2bf9d-149">RBAC proporciona una lista de cmdlets que el usuario puede ejecutar en función de los roles RBAC de los que el usuario es miembro.</span><span class="sxs-lookup"><span data-stu-id="2bf9d-149">RBAC provides a list of cmdlets that the user can run based on the RBAC roles that the user is a member of.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

