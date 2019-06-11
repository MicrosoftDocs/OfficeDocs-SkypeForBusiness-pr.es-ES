---
title: 'Lync Server 2013: administración del sistema'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: System administration
ms:assetid: 063eb962-b96a-4699-8579-bb7125112df4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720318(v=OCS.15)
ms:contentKeyID: 63969577
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d62526daf43308b4ed38538e5ea16e15b271fc9a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850522"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="system-administration-in-lync-server-2013"></a><span data-ttu-id="3759e-102">Administración del sistema en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3759e-102">System administration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3759e-103">_**Última modificación del tema:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="3759e-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="3759e-104">La administración del sistema incluye las tareas administrativas cotidianas, tanto planificadas como a petición, que se requieren para mantener el funcionamiento correcto de un sistema de ti.</span><span class="sxs-lookup"><span data-stu-id="3759e-104">System administration includes the day-to-day administrative tasks, both planned and on-demand, that are required to keep an IT system operating smoothly.</span></span> <span data-ttu-id="3759e-105">Normalmente, las tareas de administración del sistema se cubren mediante procedimientos escritos.</span><span class="sxs-lookup"><span data-stu-id="3759e-105">Typically, system administration tasks are covered by written procedures.</span></span> <span data-ttu-id="3759e-106">Estos procedimientos ayudan a garantizar que todos los empleados de soporte utilicen las mismas herramientas y métodos estándar.</span><span class="sxs-lookup"><span data-stu-id="3759e-106">These procedures help ensure that the same standard tools and methods are used by all support staff.</span></span>

<span data-ttu-id="3759e-107">En un entorno de Lync, las tareas típicas de administración del sistema incluyen la realización de copias de seguridad y el archivado de grupos, la supervisión de registros, la creación y administración de usuarios y la actualización de software antivirus.</span><span class="sxs-lookup"><span data-stu-id="3759e-107">In a Lync environment, typical system administration tasks include backing up and archiving pools, monitoring logs, creating and managing users, and updating antivirus software.</span></span>

<div>

## <a name="system-troubleshooting"></a><span data-ttu-id="3759e-108">Solución de problemas del sistema</span><span class="sxs-lookup"><span data-stu-id="3759e-108">System troubleshooting</span></span>

<span data-ttu-id="3759e-109">Una organización debe estar preparada para tratar problemas inesperados y debe tener un procedimiento para administrar los problemas desde el punto en el que se les informa hasta su resolución.</span><span class="sxs-lookup"><span data-stu-id="3759e-109">An organization must be prepared to deal with unexpected issues and should have a procedure to manage issues from the point at which they are reported until their resolution.</span></span> <span data-ttu-id="3759e-110">Información sobre cómo el personal de soporte diagnosticó un problema se debe grabar y usar en el futuro para evitar la repetición del trabajo completado de forma innecesaria.</span><span class="sxs-lookup"><span data-stu-id="3759e-110">Information about how support staff diagnosed an issue should be recorded and used in the future to avoid unnecessarily repeating completed work.</span></span>

</div>

<div>

## <a name="system-troubleshooting-process"></a><span data-ttu-id="3759e-111">Proceso de solución de problemas del sistema</span><span class="sxs-lookup"><span data-stu-id="3759e-111">System troubleshooting process</span></span>

<span data-ttu-id="3759e-112">En el siguiente diagrama se muestra el proceso de solución de problemas del sistema y las interacciones con otros roles de operaciones.</span><span class="sxs-lookup"><span data-stu-id="3759e-112">The following diagram shows the system troubleshooting process and the interactions with other operations roles.</span></span>

<span data-ttu-id="3759e-113">**Diagrama de flujo de solución de problemas del sistema**</span><span class="sxs-lookup"><span data-stu-id="3759e-113">**System troubleshooting flowchart**</span></span>

<span data-ttu-id="3759e-114">![Diagrama de flujo de solución de problemas del sistema] (images/Dn720318.869d0b89-6473-4b1f-9d90-59604b4b8e98(OCS.15).jpg "Diagrama de flujo de solución de problemas del sistema")</span><span class="sxs-lookup"><span data-stu-id="3759e-114">![System Troubleshooting Flowchart](images/Dn720318.869d0b89-6473-4b1f-9d90-59604b4b8e98(OCS.15).jpg "System Troubleshooting Flowchart")</span></span>

  - <span data-ttu-id="3759e-115">**Clasificar y priorizar**   esta tarea normalmente la realiza el servicio de asistencia al cliente.</span><span class="sxs-lookup"><span data-stu-id="3759e-115">**Classify and Prioritize**   This task is typically performed by the service desk.</span></span> <span data-ttu-id="3759e-116">Por ejemplo, un problema puede estar agrupado como un problema de software o un problema de hardware.</span><span class="sxs-lookup"><span data-stu-id="3759e-116">For example, an issue may be grouped as a software issue or a hardware issue.</span></span> <span data-ttu-id="3759e-117">El problema se redirige al equipo de soporte técnico adecuado para que lo investigue.</span><span class="sxs-lookup"><span data-stu-id="3759e-117">The issue is then routed to the appropriate support team for investigation.</span></span> <span data-ttu-id="3759e-118">Las reglas para determinar la prioridad de un problema, junto con el tiempo para responder y el momento de la resolución, se definen normalmente en el SLA.</span><span class="sxs-lookup"><span data-stu-id="3759e-118">The rules for determining the priority of an issue, together with the time to respond and time to resolve, are typically defined in the SLA.</span></span>

  - <span data-ttu-id="3759e-119">**Investigue y diagnostique**   el equipo de soporte técnico adecuado para diagnosticar el problema y proponer cambios para resolver el problema.</span><span class="sxs-lookup"><span data-stu-id="3759e-119">**Investigate and Diagnose**   The appropriate support team diagnoses the issue and proposes changes to resolve the issue.</span></span> <span data-ttu-id="3759e-120">Si la solución es sencilla y no requiere control de cambios, la solución se puede aplicar de inmediato.</span><span class="sxs-lookup"><span data-stu-id="3759e-120">If the solution is simple and does not require change control, the solution can be applied immediately.</span></span> <span data-ttu-id="3759e-121">Si la solución no es sencilla, se debe elevar una solicitud de cambio y el proceso de administración de cambios debe administrar el trabajo propuesto, con frecuencia en un procedimiento de "seguimiento rápido".</span><span class="sxs-lookup"><span data-stu-id="3759e-121">If the solution is not easy, a request for change should be raised and the proposed work should be managed by the change management process, frequently under a “fast-track” procedure.</span></span> <span data-ttu-id="3759e-122">Los cambios que se realicen deben registrarse con el proceso de administración de la configuración.</span><span class="sxs-lookup"><span data-stu-id="3759e-122">Any changes that are made should be recorded using the configuration management process.</span></span>

  - <span data-ttu-id="3759e-123">**Cerrar y grabar**   después de probar la resolución, debe cerrarse el problema.</span><span class="sxs-lookup"><span data-stu-id="3759e-123">**Close and Record**   After testing the resolution, the issue should be closed.</span></span> <span data-ttu-id="3759e-124">Si hay clases que aprender del problema, debe crearse una entrada en la base de conocimientos.</span><span class="sxs-lookup"><span data-stu-id="3759e-124">If there are lessons to be learned from the issue, an entry should be created in the knowledge base.</span></span>

  - <span data-ttu-id="3759e-125">**Revisión y análisis**   de tendencias se deben realizar revisiones periódicas de problemas recientes para identificar tendencias de problemas.</span><span class="sxs-lookup"><span data-stu-id="3759e-125">**Review and Trend Analysis**   Periodic reviews of recent issues should be performed to identify issue trends.</span></span> <span data-ttu-id="3759e-126">Por ejemplo, si los usuarios experimentan problemas frecuentes con los inicios de sesión lentos en sus sitios de Lync, pueden producirse problemas de ancho de banda de red.</span><span class="sxs-lookup"><span data-stu-id="3759e-126">For example, if the users are experiencing frequent issues with slow logons to their Lync sites, network bandwidth issues may be the cause.</span></span> <span data-ttu-id="3759e-127">Deben revisarse las horas de resolución de problemas y el efecto de las interrupciones en la disponibilidad del sistema y compararlas con el SLA.</span><span class="sxs-lookup"><span data-stu-id="3759e-127">Issue resolution times and the effect of any outages on system availability should be reviewed and compared with the SLA.</span></span> <span data-ttu-id="3759e-128">La persona que liaises al cliente sobre problemas del servicio, como un administrador de cuentas, debe estar informada de cualquier problema importante.</span><span class="sxs-lookup"><span data-stu-id="3759e-128">The person who liaises with the customer on service issues, such as an account manager, should be informed of any significant issues.</span></span>

</div>

<div>

## <a name="issue-management-tools"></a><span data-ttu-id="3759e-129">Herramientas de administración de problemas</span><span class="sxs-lookup"><span data-stu-id="3759e-129">Issue management tools</span></span>

<span data-ttu-id="3759e-130">Las herramientas de servicio de asistencia al cliente permiten a los empleados registrar, clasificar y priorizar nuevos problemas.</span><span class="sxs-lookup"><span data-stu-id="3759e-130">Service desk tools enable staff to record, classify, and prioritize new issues.</span></span> <span data-ttu-id="3759e-131">Las herramientas proporcionarán los procesos de flujo de trabajo para administrar la solicitud de servicio de problemas mediante investigación y diagnóstico, a menudo por más de un equipo de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="3759e-131">Tools will then provide the workflow processes to manage the issue service request through investigation and diagnosis, often by more than one support team.</span></span> <span data-ttu-id="3759e-132">Las herramientas, que a menudo proporcionarán informes sobre los tiempos de resolución y las tendencias históricas, también pueden incluir una base de datos de Knowledge base, que se puede usar para buscar problemas anteriores.</span><span class="sxs-lookup"><span data-stu-id="3759e-132">Tools, which will frequently provide reports about resolution times and historical trends, may also include a knowledge base database, which can be used to search through past issues.</span></span>

<span data-ttu-id="3759e-133">Microsoft Knowledge base es un registro útil de los problemas de soporte técnico que ha encontrado Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3759e-133">The Microsoft Knowledge Base is a useful record of support issues that were encountered by Microsoft.</span></span> <span data-ttu-id="3759e-134">Para obtener más información, consulte el sitio web de<http://go.microsoft.com/fwlink/?linkid=14898>soporte técnico de Microsoft ().</span><span class="sxs-lookup"><span data-stu-id="3759e-134">For more information, see the Microsoft Support website (<http://go.microsoft.com/fwlink/?linkid=14898>).</span></span>

<span data-ttu-id="3759e-135">El software de terceros suele requerir personalización para satisfacer las necesidades de la organización, como la organización de los equipos, los requisitos de informes y las medidas que necesita el SLA.</span><span class="sxs-lookup"><span data-stu-id="3759e-135">Third-party software typically requires customization to suit the organization’s needs, such as the organization of teams, reporting requirements, and measures required by the SLA.</span></span>

</div>

<div>

## <a name="centralized-vs-decentralized-administration"></a><span data-ttu-id="3759e-136">Administración centralizada y descentralizada</span><span class="sxs-lookup"><span data-stu-id="3759e-136">Centralized vs. decentralized administration</span></span>

<span data-ttu-id="3759e-137">Los roles y las responsabilidades para realizar las tareas de administración del sistema dependen de si la organización sigue un modelo centralizado, un modelo descentralizado o una combinación de ambos.</span><span class="sxs-lookup"><span data-stu-id="3759e-137">Roles and responsibilities for performing system administration tasks depend on whether the organization follows a centralized model, a decentralized model, or a combination of both.</span></span>

  - <span data-ttu-id="3759e-138">**Modelo centralizado**   en un modelo centralizado, uno o varios grupos administrativos mantienen un control total de todo el entorno de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3759e-138">**Centralized Model**   In a centralized model, one or several administrative groups maintain complete control of the whole Lync Server environment.</span></span> <span data-ttu-id="3759e-139">Este modelo administrativo se asemeja a un centro de datos en el que todas las tareas de administración las realiza un único grupo de tecnología de la información.</span><span class="sxs-lookup"><span data-stu-id="3759e-139">This administrative model resembles a data center where all administration tasks are performed by a single information technology group.</span></span> <span data-ttu-id="3759e-140">Las funciones y responsabilidades dentro del equipo deben definirse en función de la experiencia y la experiencia.</span><span class="sxs-lookup"><span data-stu-id="3759e-140">Roles and responsibilities within the team should be defined according to experience and expertise.</span></span>

  - <span data-ttu-id="3759e-141">**Modelo**   descentralizado las organizaciones descentralizadas se encuentran en varias ubicaciones geográficas y tienen servidores de Lync Server y equipos de administradores en diferentes ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="3759e-141">**Decentralized Model**   Decentralized organizations are located in several geographic locations and have functioning Lync Server servers and teams of administrators in different locations.</span></span> <span data-ttu-id="3759e-142">Por ejemplo, es posible que haya personal de administración local y uno o más servidores que ejecuten Lync Server 2013 para cada país o región.</span><span class="sxs-lookup"><span data-stu-id="3759e-142">For example, there may be local administration staff and one or more servers that are running Lync Server 2013 for each country/region.</span></span> <span data-ttu-id="3759e-143">O bien, puede haber un grupo de servidores que ejecuten Lync Server 2013 y un equipo administrativo para Norteamérica y otro para Europa.</span><span class="sxs-lookup"><span data-stu-id="3759e-143">Or, there may be a pool of servers that are running Lync Server 2013 and an administrative team for North America and one for Europe.</span></span> <span data-ttu-id="3759e-144">En ocasiones, es posible que desee que los administradores sean responsables de su propio área geográfica y restringir los permisos para administrar los recursos de otras áreas.</span><span class="sxs-lookup"><span data-stu-id="3759e-144">Sometimes, you may want administrators to be responsible only for their own geographical area and restrict permissions to administer resources in other areas.</span></span>

<span data-ttu-id="3759e-145">Lync Server también le permite delegar tareas administrativas específicas a personas o grupos específicos mediante el control de acceso basado en roles (RBAC).</span><span class="sxs-lookup"><span data-stu-id="3759e-145">Lync Server also allows you to delegate specific administrative tasks to specific people or groups by using role-based access control (RBAC).</span></span> <span data-ttu-id="3759e-146">RBAC permite que los administradores deleguen permisos y derechos de usuario específicos a otros administradores para realizar un subconjunto de las tareas administrativas posibles.</span><span class="sxs-lookup"><span data-stu-id="3759e-146">RBAC allows administrators to delegate specific user rights and permissions to other administrators to perform a subset of the administrative tasks possible.</span></span> <span data-ttu-id="3759e-147">Al usar RBAC, la capacidad del usuario para realizar tareas administrativas específicas depende de los roles RBAC que se asignan al usuario.</span><span class="sxs-lookup"><span data-stu-id="3759e-147">By using RBAC, the user’s ability to perform specific administrative tasks depends on the RBAC roles that are assigned to the user.</span></span> <span data-ttu-id="3759e-148">RBAC proporciona una lista de cmdlets que el usuario puede ejecutar en función de los roles RBAC de los que es miembro el usuario.</span><span class="sxs-lookup"><span data-stu-id="3759e-148">RBAC provides a list of cmdlets that the user can run based on the RBAC roles that the user is a member of.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

