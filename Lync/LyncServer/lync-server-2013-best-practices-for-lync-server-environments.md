---
title: 'Lync Server 2013: procedimientos recomendados para entornos de Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Best practices for Lync Server environments
ms:assetid: b0e45d84-09c8-4d3e-aad0-bc6f34ce233b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720348(v=OCS.15)
ms:contentKeyID: 63969642
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 00dbbf95990875b8366ce5a03f1d2d70e6652828
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842742"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="best-practices-for-lync-server-2013-environments"></a><span data-ttu-id="c5207-102">Procedimientos recomendados para entornos de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5207-102">Best practices for Lync Server 2013 environments</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c5207-103">_**Última modificación del tema:** 2014-08-04_</span><span class="sxs-lookup"><span data-stu-id="c5207-103">_**Topic Last Modified:** 2014-08-04_</span></span>

<span data-ttu-id="c5207-104">Los siguientes principios generales deben aplicarse a las operaciones en curso de su sistema:</span><span class="sxs-lookup"><span data-stu-id="c5207-104">The following general principles should be applied to ongoing operations of your system:</span></span>

  - <span data-ttu-id="c5207-105">**Comprender y utilizar MOF**   MOF es una colección de procedimientos recomendados, principios y modelos que proporcionan orientación técnica a la organización sobre la administración de activos de ti, como las operaciones diarias de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c5207-105">**Understand and utilize MOF**   MOF is a collection of best practices, principles, and models that provide organizations technical guidance about the management of IT assets, such as daily Lync Server 2013 operations.</span></span> <span data-ttu-id="c5207-106">Las siguientes pautas de MOF pueden ayudarle a lograr la confiabilidad, la disponibilidad, la compatibilidad y la capacidad de administración de los productos de Microsoft de misión crítica.</span><span class="sxs-lookup"><span data-stu-id="c5207-106">Following MOF guidelines can help you achieve mission-critical production system reliability, availability, supportability, and manageability for Microsoft products.</span></span> <span data-ttu-id="c5207-107">Para obtener más información, consulte [Microsoft Operations Framework 4,0](http://go.microsoft.com/fwlink/p/?linkid=40939).</span><span class="sxs-lookup"><span data-stu-id="c5207-107">For more information, see [Microsoft Operations Framework 4.0](http://go.microsoft.com/fwlink/p/?linkid=40939).</span></span>

  - <span data-ttu-id="c5207-108">**Obtenga más información sobre los procedimientos recomendados para Lync Server 2013**   se recomienda implementar procedimientos prácticos y probados para administrar Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c5207-108">**Learn about best practices for Lync Server 2013**   We recommend that you implement practical and proven procedures to manage Lync Server 2013.</span></span> <span data-ttu-id="c5207-109">El uso de métodos probados, probados y documentados de administración de operaciones puede ser más eficaz que el desarrollo de métodos propios.</span><span class="sxs-lookup"><span data-stu-id="c5207-109">By using tried, tested, and documented methods of managing operations may be more efficient than developing your own methods.</span></span>

  - <span data-ttu-id="c5207-110">**Las operaciones independientes en procesos**   diarios, semanales y mensuales documentan las tareas operativas necesarias que realizará regularmente.</span><span class="sxs-lookup"><span data-stu-id="c5207-110">**Separate operations into daily, weekly, and monthly processes**   Document the required operational tasks that you'll regularly perform.</span></span> <span data-ttu-id="c5207-111">Documentar cómo se realizan las tareas ayuda a asegurarse de que su información se conserve cuando haya un cambio en el entorno operativo, como cuando se implementan nuevas tecnologías o se producen cambios en el personal.</span><span class="sxs-lookup"><span data-stu-id="c5207-111">Documenting how you perform tasks helps make sure that your information is preserved when there is a change in your operational environment such as when new technologies are deployed or staff changes occur.</span></span> <span data-ttu-id="c5207-112">Recomendamos que las tareas operativas se separen en cargas de trabajo manejables donde las tareas se realizan diariamente, semanalmente y mensualmente.</span><span class="sxs-lookup"><span data-stu-id="c5207-112">We recommend that operational tasks be separated into manageable workloads where tasks are performed daily, weekly, and monthly.</span></span> <span data-ttu-id="c5207-113">Las tareas diarias podrían centrar esfuerzos en el funcionamiento de un sistema, y las tareas mensuales se centrarían más en asegurar la salud a largo plazo de un sistema.</span><span class="sxs-lookup"><span data-stu-id="c5207-113">Daily tasks would focus efforts on the functioning of a system, and monthly tasks would focus more on ensuring the long-term health of a system.</span></span>
    
    <span data-ttu-id="c5207-114">Este documento se puede usar en entornos que implementan solo los componentes de mensajería instantánea y presencia (mensajes instantáneos/P) o mensajería instantánea/P con Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="c5207-114">This document can be used in environments deploying only instant messaging/presence (IM/P) components or IM/P with Enterprise Voice.</span></span> <span data-ttu-id="c5207-115">Cuando las tareas o los elementos de la lista de comprobación son específicos de Enterprise Voice, esto se menciona y, si su entorno no incluye telefonía IP empresarial, puede que se omita la parte.</span><span class="sxs-lookup"><span data-stu-id="c5207-115">When tasks or checklist items are specific to Enterprise Voice, this is mentioned and if your environment does not include Enterprise Voice the portion may be skipped.</span></span>

  - <span data-ttu-id="c5207-116">**Implementar las herramientas necesarias para el funcionamiento de Lync Server 2013**   muchas de ellas están disponibles para ayudarle a solucionar problemas, automatizar tareas y ayudar a supervisar y mantener el entorno de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c5207-116">**Deploy the tools that are required for operating Lync Server 2013**   Many tools are available to help troubleshoot issues, automate tasks, and help monitor and maintain the Lync Server 2013 environment.</span></span> <span data-ttu-id="c5207-117">Defina un conjunto estándar de herramientas para su organización, de modo que las tareas que realiza el equipo de operaciones se realicen de manera precisa, eficiente, coherente y controlada.</span><span class="sxs-lookup"><span data-stu-id="c5207-117">Define a standard set of tools for your organization so the tasks that are performed by the operations team are performed accurately, efficiently, consistently, and in a controlled manner.</span></span> <span data-ttu-id="c5207-118">También debe implementar procesos para realizar un seguimiento de los incidentes y cambios de configuración importantes.</span><span class="sxs-lookup"><span data-stu-id="c5207-118">You should also implement processes to track incidents and major configuration changes.</span></span>

<div>

## <a name="reference"></a><span data-ttu-id="c5207-119">Referencia</span><span class="sxs-lookup"><span data-stu-id="c5207-119">Reference</span></span>

<span data-ttu-id="c5207-120">Para los lectores que aún no están familiarizados con los conceptos básicos de la administración de servidores, proporcionamos una descripción general de las prácticas de administración de servidores.</span><span class="sxs-lookup"><span data-stu-id="c5207-120">For the benefit of readers not already familiar with the basics of server management in general, we provide an overview of server management practices.</span></span> <span data-ttu-id="c5207-121">Los lectores que ya están familiarizados con la administración de servidores pueden omitir esta sección.</span><span class="sxs-lookup"><span data-stu-id="c5207-121">Readers already familiar with server management may choose to skip this section.</span></span>

<span data-ttu-id="c5207-122">Los procedimientos recomendados son recomendaciones que se basan en el conocimiento y la experiencia que los profesionales de TI han ganado en muchos entornos.</span><span class="sxs-lookup"><span data-stu-id="c5207-122">Best practices are recommendations that are based on the knowledge and experience that IT professionals have gained across many environments.</span></span> <span data-ttu-id="c5207-123">Proporcionan procedimientos estándar para las tareas típicas que los administradores de Lync Server deben realizar diariamente y muestran las herramientas que deben usar para administrar un entorno de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c5207-123">They provide standard procedures for typical tasks that your Lync Server administrators must perform daily, and list the tools that they should use to manage a Lync Server environment.</span></span>

<span data-ttu-id="c5207-124">Entre las tareas típicas de los administradores de Lync se incluyen las siguientes:</span><span class="sxs-lookup"><span data-stu-id="c5207-124">Typical tasks for Lync administrators include the following:</span></span>

  - <span data-ttu-id="c5207-125">**La administración**   de la capacidad y la disponibilidad definen cómo y qué se debe medir para predecir futuros requisitos de capacidad y para informar sobre la capacidad, la confiabilidad y la disponibilidad de sus sistemas.</span><span class="sxs-lookup"><span data-stu-id="c5207-125">**Capacity and Availability Management**   Define how and what to measure to predict future capacity requirements and to report about the capacity, reliability, and availability of your systems.</span></span> <span data-ttu-id="c5207-126">Debe comprobar que los servidores que ejecutan Lync Server tienen el tamaño adecuado para controlar la carga del sistema y que el tiempo de inactividad imprevisto se mantiene bajo los niveles definidos en el contrato de nivel de servicio (SLA).</span><span class="sxs-lookup"><span data-stu-id="c5207-126">You must verify that servers that are running Lync Server are sized to handle the load on the system, and that unplanned downtime is kept under the levels defined in the service level agreement (SLA).</span></span> <span data-ttu-id="c5207-127">Además, tendrá que actualizar el hardware para seguir cumpliendo los requisitos definidos.</span><span class="sxs-lookup"><span data-stu-id="c5207-127">Additionally, you'll have to upgrade hardware to continue to meet the defined requirements.</span></span>

  - <span data-ttu-id="c5207-128">**Administración de cambios y**   administración de la configuración controle cómo se realizan cambios en los sistemas de ti.</span><span class="sxs-lookup"><span data-stu-id="c5207-128">**Change Management and Configuration Management**   Control how changes are made to IT systems.</span></span> <span data-ttu-id="c5207-129">Esto debe incluir pruebas, comentarios sobre la aplicación y planes de contingencias, documentación de todos los cambios y aprobación de la administración si se producen problemas.</span><span class="sxs-lookup"><span data-stu-id="c5207-129">This should include testing, application feedback and contingency plans, documentation of all changes, and approval from management if issues occur.</span></span> <span data-ttu-id="c5207-130">Mantenga un registro de los activos de software y hardware, así como de sus configuraciones.</span><span class="sxs-lookup"><span data-stu-id="c5207-130">Keep a record of your software and hardware assets and their configurations.</span></span>

  - <span data-ttu-id="c5207-131">**Administración del sistema**   métodos estándar para realizar tareas administrativas, como la administración de bases de datos y la administración de sitios.</span><span class="sxs-lookup"><span data-stu-id="c5207-131">**System Administration**   Outline standard methods for doing administrative tasks such as database administration and site administration.</span></span>

  - <span data-ttu-id="c5207-132">**Administración de seguridad**   tenga una política y un plan pormenorizados que protejan la confidencialidad de los datos, la integridad de los datos y la disponibilidad de los datos de la infraestructura de ti.</span><span class="sxs-lookup"><span data-stu-id="c5207-132">**Security Administration**   Have a detailed policy and plan that protects data confidentiality, data integrity, and data availability of the IT infrastructure.</span></span> <span data-ttu-id="c5207-133">Esto incluye las actividades diarias y las tareas relacionadas con el mantenimiento y el ajuste de la infraestructura de seguridad de ti.</span><span class="sxs-lookup"><span data-stu-id="c5207-133">This includes day-to-day activities and tasks that are related to maintaining and adjusting the IT security infrastructure.</span></span>

  - <span data-ttu-id="c5207-134">**Solución de problemas del sistema**   métodos de esquema para tratar problemas inesperados, como pasos para evitar problemas similares en el futuro.</span><span class="sxs-lookup"><span data-stu-id="c5207-134">**System Troubleshooting**   Outline methods for dealing with unexpected issues, including steps to prevent similar issues in the future.</span></span>

  - <span data-ttu-id="c5207-135">**Los acuerdos**   de nivel de servicio mantienen un conjunto de objetivos para el rendimiento de los sistemas de ti y miden regularmente el rendimiento frente a estos objetivos.</span><span class="sxs-lookup"><span data-stu-id="c5207-135">**Service Level Agreements**   Maintain a set of goals for the performance of the IT systems and regularly measure performance against these goals.</span></span>

  - <span data-ttu-id="c5207-136">**Documentación**   procedimientos estándar del documento, como la información de configuración y las lecciones aprendidas, y ponerlos a disposición de los miembros del personal que los necesiten.</span><span class="sxs-lookup"><span data-stu-id="c5207-136">**Documentation**   Document standard procedures, such as configuration information and lessons learned, and make them available to the staff members that need them.</span></span> <span data-ttu-id="c5207-137">Cuando se realicen cambios en la configuración, actualice la documentación según corresponda.</span><span class="sxs-lookup"><span data-stu-id="c5207-137">As changes to the configuration are made, update the documentation accordingly.</span></span>

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="c5207-138">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="c5207-138">Related Sections</span></span>

<span data-ttu-id="c5207-139">Revise los temas siguientes relacionados con las operaciones del sistema antes de continuar:</span><span class="sxs-lookup"><span data-stu-id="c5207-139">Review the following topics concerning system operations before proceeding:</span></span>

  - [<span data-ttu-id="c5207-140">Administración de la capacidad y disponibilidad de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5207-140">Capacity and availability management in Lync Server 2013</span></span>](lync-server-2013-capacity-and-availability-management.md)

  - [<span data-ttu-id="c5207-141">Administración de cambios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5207-141">Change management in Lync Server 2013</span></span>](lync-server-2013-change-management.md)

  - [<span data-ttu-id="c5207-142">Administración de la configuración en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5207-142">Configuration management in Lync Server 2013</span></span>](lync-server-2013-configuration-management.md)

  - [<span data-ttu-id="c5207-143">Administración del sistema en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5207-143">System administration in Lync Server 2013</span></span>](lync-server-2013-system-administration.md)

  - [<span data-ttu-id="c5207-144">Acuerdos de nivel de servicio en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5207-144">Service level agreements in Lync Server 2013</span></span>](lync-server-2013-service-level-agreements.md)

  - [<span data-ttu-id="c5207-145">Documentación de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5207-145">Documentation in Lync Server 2013</span></span>](lync-server-2013-documentation.md)

  - [<span data-ttu-id="c5207-146">Procedimientos estándar de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5207-146">Standard procedures in Lync Server 2013</span></span>](lync-server-2013-standard-procedures.md)

  - [<span data-ttu-id="c5207-147">Procedimientos de emergencia en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5207-147">Emergency procedures in Lync Server 2013</span></span>](lync-server-2013-emergency-procedures.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c5207-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="c5207-148">See Also</span></span>


[<span data-ttu-id="c5207-149">Microsoft Operations Framework 4,0</span><span class="sxs-lookup"><span data-stu-id="c5207-149">Microsoft Operations Framework 4.0</span></span>](http://go.microsoft.com/fwlink/p/?linkid=40939)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

