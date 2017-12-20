---
title: Audioconferencia en Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Guía práctica para implementar la audioconferencia en Microsoft Teams."
MS.collection: Strat_MT_TeamsAdmin
ms.openlocfilehash: 5a65f305d924c5e5e6dac01d2391a62d8abd1243
ms.sourcegitcommit: 3faedb6057da8650b06b05f9c9bdd941d5ade175
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/20/2017
---
<a name="audio-conferencing-in-microsoft-teams"></a><span data-ttu-id="4b93d-103">Audioconferencia en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4b93d-103">Audio Conferencing in Microsoft Teams</span></span>
=====================================

> [!IMPORTANT]
> <span data-ttu-id="4b93d-104">Las funciones de audioconferencia se encuentran en la versión preliminar pública.</span><span class="sxs-lookup"><span data-stu-id="4b93d-104">Audio conferencing is in public preview.</span></span> <span data-ttu-id="4b93d-105">Está disponible para usuarios pioneros y clientes de la versión preliminar. No es una versión definitiva, sino que podría ir cambiando conforme haya nuevas versiones o actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="4b93d-105">It's available to Early Adopters (EA) and preview customers and could change as it is released or updated.</span></span>

<span data-ttu-id="4b93d-106">Audioconferencia en Office 365 (anteriormente conocida como Conferencia RTC) permite a los participantes unirse a las reuniones desde cualquier teléfono.</span><span class="sxs-lookup"><span data-stu-id="4b93d-106">Audio Conferencing in Office 365 (formerly known as PSTN Conferencing) allows participants to join your meetings from any telephone.</span></span> <span data-ttu-id="4b93d-107">Por el momento, esta característica se encuentra en Microsoft Teams (en la versión preliminar pública) y, con ella, los usuarios se pueden unir a las reuniones de Microsoft Teams a través de sus teléfonos.</span><span class="sxs-lookup"><span data-stu-id="4b93d-107">This feature is now available in Microsoft Teams, in public preview, allowing users to join Teams meetings using their phones.</span></span> <span data-ttu-id="4b93d-108">En las instrucciones prácticas que se detallan en este artículo, se revisan con usted todas las fases que conforman el recorrido de cliente de FastTrack para Office 365 hasta llegar a Audioconferencia: Enfoque, Incorporación y Nuevos valores.</span><span class="sxs-lookup"><span data-stu-id="4b93d-108">The practical guidance in this article steps you through the Office 365 FastTrack customer journey framework for Audio Conferencing - Envision, Onboard, and Drive value.</span></span>

<span data-ttu-id="4b93d-109">Esto es lo que conseguirá con [Audioconferencia](https://go.microsoft.com/fwlink/?linkid=858992) en Office 365.</span><span class="sxs-lookup"><span data-stu-id="4b93d-109">Here's what you get with [Audio Conferencing](https://go.microsoft.com/fwlink/?linkid=858992) in Office 365.</span></span>

> [!NOTE]
> <span data-ttu-id="4b93d-110">Audioconferencia es compatible con Microsoft Teams y Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="4b93d-110">Audio Conferencing supports both Teams and Skype for Business Online.</span></span> <span data-ttu-id="4b93d-111">En este momento, las interfaces administrativas que controlan este servicio se encuentran en el Centro de administración de Skype Empresarial y PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="4b93d-111">Currently, the existing Skype for Business Admin center and remote PowerShell provide the administrative interfaces to manage Audio Conferencing.</span></span>


|  |  |
|---------|---------|
|  <iframe width="350" height="200" src="https://www.youtube.com/embed/AGPvaW4Vg0o" frameborder="0" allowfullscreen></iframe>   | |

<span data-ttu-id="4b93d-112">Enfoque <a name="Envision_AudioConferencing"> </a></span><span class="sxs-lookup"><span data-stu-id="4b93d-112">Envision <a name="Envision_AudioConferencing"> </a></span></span>
=========

<span data-ttu-id="4b93d-113">En la fase de Enfoque, se define el recorrido que tendrá que hacer el cliente de Office 365 y se aplicará a todo tipo de cargas de trabajo, como la de Audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="4b93d-113">The Envision phase provides the foundation for the Office 365 customer journey and is applicable to all workloads such as Audio Conferencing.</span></span>

<span data-ttu-id="4b93d-114">En esta fase se definen los objetivos empresariales, con la participación de todas las partes interesadas del proyecto, para, por último, presentar:</span><span class="sxs-lookup"><span data-stu-id="4b93d-114">In this phase, business goals are captured, with relevant project stakeholders assembled, to ultimately deliver:</span></span>

-   <span data-ttu-id="4b93d-115">un plan de éxito de gran nivel que contenga casos de uso de empresas, las principales partes interesadas, objetivos y resultados principales, indicadores de éxito principales, riesgos, evaluación del entorno, preparación para la adopción y plan operativo;</span><span class="sxs-lookup"><span data-stu-id="4b93d-115">a high-level success plan that contains business use cases, key stakeholders, objectives and key results (OKRs), key success indicators (KSIs), risks, environmental assessment, adoption readiness, and operational plan.</span></span>

-   <span data-ttu-id="4b93d-116">y, posteriormente, un plan detallado de implementación técnica de Audioconferencia para conseguir el estado final deseado.</span><span class="sxs-lookup"><span data-stu-id="4b93d-116">and subsequently, a detailed Audio Conferencing technical implementation plan to achieve the desired end state.</span></span>

<a name="define-business-use-cases-for-audio-conferencing"></a><span data-ttu-id="4b93d-117">Definir casos de uso de empresas para Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="4b93d-117">Define business use cases for Audio Conferencing</span></span>
------------------------------------------------

<span data-ttu-id="4b93d-118">Audioconferencia proporciona a las organizaciones unos puntos de entrada adicionales a reuniones que están programadas. Para ello, los participantes se unen a través de RTC llamando con teléfonos móviles, PBX o fijos tradicionales.</span><span class="sxs-lookup"><span data-stu-id="4b93d-118">Audio Conferencing provides organizations with additional entry points to any scheduled meetings by allowing meeting participants to join via PSTN by dialing in using traditional landline, PBX, or mobile phones.</span></span>

<span data-ttu-id="4b93d-119">Resulta muy útil cuando el organizador o los participantes no tienen delante un ordenador o cuando no hay conexiones de datos o estas no soportan las comunicaciones por voz; por ejemplo, cuando el participante se encuentra en un área remota con una cobertura de datos móviles muy irregular o si se conecta a un servicio de red Wi-Fi público y gratuito con ancho de banda limitado, o bien cuando los participantes de la reunión prefieren acceder a ella por teléfono mediante puntos de conexión de telefonía de fácil acceso.</span><span class="sxs-lookup"><span data-stu-id="4b93d-119">This is useful when the organizer or participants are not in front of a computer, or when data connections are unavailable or unreliable to support voice communications—such as when in a remote area with spotty mobile data coverage, or if connected to a free, public Wi-Fi service with limited bandwidth, or when meeting participants prefer to dial in to the meeting using telephony endpoint readily accessible to them.</span></span>

<span data-ttu-id="4b93d-120">En este paso, los principales participantes del proyecto definirán casos de uso de empresas que admitan la implementación de Audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="4b93d-120">In this step, core project stakeholders will define business use cases that support the implementation of Audio Conferencing.</span></span>

<span data-ttu-id="4b93d-121">Los casos de uso de empresa se aportan con la intención de definir y documentar los resultados que se esperan y que se pueden medir. Incluyen lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4b93d-121">Business use cases are meant to define and document the expected and measurable business outcomes, and include the following:</span></span>

-   <span data-ttu-id="4b93d-122">Descripción del proceso de negocio actual.</span><span class="sxs-lookup"><span data-stu-id="4b93d-122">Description of current business process.</span></span>

-   <span data-ttu-id="4b93d-123">Retos que se deben conseguir con el proceso de negocio actual definido.</span><span class="sxs-lookup"><span data-stu-id="4b93d-123">Challenges with existing business process defined.</span></span>

-   <span data-ttu-id="4b93d-124">De qué manera la tecnología puede ayudar a alcanzar estos retos.</span><span class="sxs-lookup"><span data-stu-id="4b93d-124">How technology can help overcome these challenges.</span></span>

-   <span data-ttu-id="4b93d-125">Los resultados de empresa que se esperan y que se pueden medir si se alcanzan los retos impuestos anteriormente.</span><span class="sxs-lookup"><span data-stu-id="4b93d-125">The expected and measurable business outcome if these challenges are overcome.</span></span>

<table>
<tbody>
<tr class="header">
<th align="left"><p><img src="media/audio_conferencing_image2.png" /></p></th>
<td align="left"><p><span data-ttu-id="4b93d-126"><strong>Descripción del proceso de negocio actual</strong></span><span class="sxs-lookup"><span data-stu-id="4b93d-126"><strong>Description of current business process</strong></span></span></p>
<p><span data-ttu-id="4b93d-127">Contoso utiliza en estos momentos los servicios de Conferencia RTC que ofrece el proveedor de telefonía local que le corresponde y que se cobran por minutos de reunión en reuniones internas y reuniones en las que participan usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="4b93d-127">Contoso currently relies on PSTN conferencing services provided by the incumbent local telephony provider chargeable by meeting minutes for internal meetings and meetings involving external parties.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><img src="media/audio_conferencing_image3.png" /></p></td>
<td align="left"><p><span data-ttu-id="4b93d-128"><strong>Retos que se deben conseguir con el proceso de negocio actual definido</strong></span><span class="sxs-lookup"><span data-stu-id="4b93d-128"><strong>Challenges with existing business process</strong></span></span></p>
<p><span data-ttu-id="4b93d-129">A Contoso, el servicio de Conferencia RTC actual le supone aproximadamente 1 millón de USD al año, de donde el 75 % del coste incurrido es para reuniones internas.</span><span class="sxs-lookup"><span data-stu-id="4b93d-129">Contoso spends roughly USD 1 million per year for the current PSTN conferencing service, with 75% of the cost incurred for internal meetings.</span></span></p>
<p><span data-ttu-id="4b93d-130">El uso de los puntos de conexión de telefonía tradicional para unirse a las reuniones que aloja el servicio de Conferencia RTC no está en línea con el plan que está desarrollando la empresa para adoptar Microsoft Teams como plataforma de colaboración y comunicaciones moderna.</span><span class="sxs-lookup"><span data-stu-id="4b93d-130">The use of traditional telephony endpoints to join the meetings hosted by the PSTN conferencing service is not aligned with the plan for the organization to adopt Teams as modern communications and collaboration platform.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><img src="media/audio_conferencing_image4.png" /></p></td>
<td align="left"><p><span data-ttu-id="4b93d-131"><strong>De qué manera la tecnología puede ayudar a alcanzar estos retos</strong></span><span class="sxs-lookup"><span data-stu-id="4b93d-131"><strong>How technology can overcome these challenges</strong></span></span></p>
<p><span data-ttu-id="4b93d-132">Al adoptar Microsoft Teams como plataforma de colaboración y comunicaciones moderna, los usuarios internos podrán fundamentalmente unirse a las reuniones con sus PC, equipados con auriculares y dispositivos de salas de reuniones adecuados.</span><span class="sxs-lookup"><span data-stu-id="4b93d-132">With the adoption of Microsoft Teams as modern communications and collaboration platform, internal users are expected to primarily join meetings using their PCs equipped with optimized headsets and meeting room devices.</span></span> <span data-ttu-id="4b93d-133">Audioconferencia estará disponible para los usuarios externos o para situaciones en las que a los participantes internos no les vaya bien el audio del PC.</span><span class="sxs-lookup"><span data-stu-id="4b93d-133">Audio Conferencing service will be available to support external participants or to support situations where the use of PC audio is not favorable for the internal participants.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><img src="media/audio_conferencing_image5.png" /></p></td>
<td align="left"><p><span data-ttu-id="4b93d-134"><strong>Propósitos y medición de los resultados de negocio</strong></span><span class="sxs-lookup"><span data-stu-id="4b93d-134"><strong>Expected, measurable, business outcomes</strong></span></span></p>
<p><span data-ttu-id="4b93d-135">El cambio a Microsoft Teams como plataforma de colaboración y comunicaciones moderna, junto con el servicio de Audioconferencia, reducirá enormemente el coste que tiene el servicio de Conferencia RTC de tal manera que se espera que Contoso solo gaste aproximadamente un 20 % del coste que dedica cada año al servicio de Conferencia RTC actual.</span><span class="sxs-lookup"><span data-stu-id="4b93d-135">The move to Teams as modern communications and collaboration platform, combined with Audio Conferencing service, will greatly reduce the cost to deliver the PSTN conferencing service to the point that Contoso is expected to only spend approximately 20% of the annual cost of the existing PSTN conferencing service.</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="4b93d-136">_Tabla 1 Ejemplo de caso de uso de negocio_</span><span class="sxs-lookup"><span data-stu-id="4b93d-136">_Table 1 Business use case example_</span></span>


<span data-ttu-id="4b93d-137">Además de definir los casos de uso de negocio, a la hora de pasar al siguiente paso de la fase de Enfoque, va a ser de gran ayuda tener muy claro el ámbito organizativo y las escalas de tiempo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="4b93d-137">In addition to defining the business use cases, having a clarity around the organizational scope and project timelines at this step helps move onto the next step of the Envision phase.</span></span>

<a name="identify-key-stakeholders"></a><span data-ttu-id="4b93d-138">Identificar las partes interesadas clave</span><span class="sxs-lookup"><span data-stu-id="4b93d-138">Identify key stakeholders</span></span>
-------------------------

<span data-ttu-id="4b93d-139">Los casos de uso de negocio que se definieron en el paso anterior incluirán el ámbito organizativo de la implementación de Audioconferencia y, en función de eso, se completará la matriz de participantes con la adición de las personas que tienen que estar involucradas en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="4b93d-139">The business use cases defined in the previous step will include organizational scope of Audio Conferencing implementation, and based on that, the comprehensive stakeholder matrix can be completed to include the right people to be involved in the project.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4b93d-140">Rol</span><span class="sxs-lookup"><span data-stu-id="4b93d-140">Role</span></span></th>
<th align="left"><span data-ttu-id="4b93d-141">Descripción</span><span class="sxs-lookup"><span data-stu-id="4b93d-141">Description</span></span></th>
<th align="left"><span data-ttu-id="4b93d-142">Nombre, información de contacto, ubicación</span><span class="sxs-lookup"><span data-stu-id="4b93d-142">Name, contact information, location</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="4b93d-143"><strong>Patrocinador ejecutivo del proyecto</strong></span><span class="sxs-lookup"><span data-stu-id="4b93d-143"><strong>Project Executive Sponsor</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="4b93d-144">La autoridad y responsable últimos del proyecto y de la consecución de los objetivos del proyecto.</span><span class="sxs-lookup"><span data-stu-id="4b93d-144">Ultimate authority and accountability for the project and delivery on project objectives</span></span></li>
<li><span data-ttu-id="4b93d-145">Ayuda a resolver problemas que haya remitido el responsable de proyecto.</span><span class="sxs-lookup"><span data-stu-id="4b93d-145">Help resolve issues escalated by Project Lead</span></span></li>
<li><span data-ttu-id="4b93d-146">Promueve la comunicación sobre los objetivos del proyecto dentro de la empresa.</span><span class="sxs-lookup"><span data-stu-id="4b93d-146">Sponsors communication within the company about project goals</span></span></li>
<li><span data-ttu-id="4b93d-147">Responsable de tomar decisiones clave de estrategia.</span><span class="sxs-lookup"><span data-stu-id="4b93d-147">Responsible for making key strategic decisions</span></span></li>
<li><span data-ttu-id="4b93d-148">Responsable de garantizar la disponibilidad de los recursos y el presupuesto necesarios.</span><span class="sxs-lookup"><span data-stu-id="4b93d-148">Responsible for availability of required resources and budget</span></span></p>
<li><span data-ttu-id="4b93d-149">Encargado de realizar revisiones empresariales trimestrales (QBR).</span><span class="sxs-lookup"><span data-stu-id="4b93d-149">Leading Quarterly Business Reviews (QBR)</span></span></li>
<li><span data-ttu-id="4b93d-150">Obtiene el consenso y el respaldo del esfuerzo de la campaña de sensibilización.</span><span class="sxs-lookup"><span data-stu-id="4b93d-150">Buy-In and support of awareness campaign effort</span></span></li>
<li><span data-ttu-id="4b93d-151">Debe actuar como patrocinador de proyecto para el lanzamiento del programa.</span><span class="sxs-lookup"><span data-stu-id="4b93d-151">Serving as the Project Sponsor to the program rollout</span></span></li></ul></td>
<td align="left"><span data-ttu-id="4b93d-152">Por añadir</span><span class="sxs-lookup"><span data-stu-id="4b93d-152">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="4b93d-153"><strong>Responsable de proyecto</strong></span><span class="sxs-lookup"><span data-stu-id="4b93d-153"><strong>Project Lead</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="4b93d-154">Administración y liderazgo en el equipo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="4b93d-154">Managing and leading project team</span></span></li>
<li><span data-ttu-id="4b93d-155">Se coordina con los socios y los equipos de trabajo que están involucrados en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="4b93d-155">Coordinates partners and working teams engaged in the project</span></span></li>
<li><span data-ttu-id="4b93d-156">Responsable de crear y administrar planes de proyecto para alcanzar los principales resultados para el trimestre.</span><span class="sxs-lookup"><span data-stu-id="4b93d-156">Accountable for creating and managing project plans to meet quarterly key results</span></span></li>
<li><span data-ttu-id="4b93d-157">Se encarga de solucionar problemas procedentes de diversas funciones.</span><span class="sxs-lookup"><span data-stu-id="4b93d-157">Resolving cross-functional issues</span></span></li>
<li><span data-ttu-id="4b93d-158">Mantiene informado de forma regular a los patrocinadores del proyecto.</span><span class="sxs-lookup"><span data-stu-id="4b93d-158">Providing regular updates to the project sponsors</span></span></li>
<li><span data-ttu-id="4b93d-159">Se ocupa de la incorporación de aspectos de adopción en el plan de proyecto general.</span><span class="sxs-lookup"><span data-stu-id="4b93d-159">Incorporating Adoption aspects into the all-up project plan</span></span></li>
<li><span data-ttu-id="4b93d-160">Se encarga de realizar revisiones operativas y empresariales mensuales (MBR), como contribución a las revisiones empresariales trimestrales.</span><span class="sxs-lookup"><span data-stu-id="4b93d-160">Leading Monthly Business and Operational Reviews (MBR), contributing to Quarterly Business Reviews</span></span></li></ul></td>
<td align="left"><span data-ttu-id="4b93d-161">Por añadir</span><span class="sxs-lookup"><span data-stu-id="4b93d-161">TBA</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="4b93d-162"><strong>Arquitecto/responsable de colaboración</strong></span><span class="sxs-lookup"><span data-stu-id="4b93d-162"><strong>Collaboration Lead/Architect</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="4b93d-163">Responsable de que los ejecutivos de la empresa lleven a cabo la estrategia de colaboración.</span><span class="sxs-lookup"><span data-stu-id="4b93d-163">Responsible for execution on collaboration strategy defined by company executives</span></span></li>
<li><span data-ttu-id="4b93d-164">Debe analizar y elegir los productos de colaboración para que la empresa cumpla los objetivos de negocio.</span><span class="sxs-lookup"><span data-stu-id="4b93d-164">Analyzing and choosing collaboration products for the company that meets business goals</span></span></li>
<li><span data-ttu-id="4b93d-165">Es responsable de diseñar las operaciones para los productos de colaboración.</span><span class="sxs-lookup"><span data-stu-id="4b93d-165">Responsible for the design of the operations for collaboration products</span></span></li>
<li><span data-ttu-id="4b93d-166">Define el modelo de operación y soporte.</span><span class="sxs-lookup"><span data-stu-id="4b93d-166">Defines operation and support model</span></span></li>
<li><span data-ttu-id="4b93d-167">Debe contribuir a las revisiones empresariales mensuales y trimestrales.</span><span class="sxs-lookup"><span data-stu-id="4b93d-167">Contributing to Monthly and Quarterly Business Reviews</span></span></li><ul></td>
<td align="left"><span data-ttu-id="4b93d-168">Por añadir</span><span class="sxs-lookup"><span data-stu-id="4b93d-168">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="4b93d-169"><strong>Consultor</strong></span><span class="sxs-lookup"><span data-stu-id="4b93d-169"><strong>Consultant</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="4b93d-170">Es responsable de los servicios de configuración.</span><span class="sxs-lookup"><span data-stu-id="4b93d-170">Responsible for configuration services</span></span></li>
<li><span data-ttu-id="4b93d-171">Contribuye a la arquitectura general de soluciones.</span><span class="sxs-lookup"><span data-stu-id="4b93d-171">Contributes in overall solution architecture</span></span></li></ul></td>
<td align="left"><span data-ttu-id="4b93d-172">Por añadir</span><span class="sxs-lookup"><span data-stu-id="4b93d-172">TBA</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="4b93d-173"><strong>Jefe de proyecto</strong></span><span class="sxs-lookup"><span data-stu-id="4b93d-173"><strong>Project Manager</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="4b93d-174">Se encarga de desarrollar y mantener el plan de proyecto.</span><span class="sxs-lookup"><span data-stu-id="4b93d-174">Developing and maintaining project plan</span></span></li>
<li><span data-ttu-id="4b93d-175">Se encarga de que las entregas de proyecto se realicen en línea con el plan y el presupuesto del proyecto.</span><span class="sxs-lookup"><span data-stu-id="4b93d-175">Managing project deliverables in line with project plan and budget</span></span></li>
<li><span data-ttu-id="4b93d-176">Registra y administra los problemas que surgen en el proyecto, incluidas las remisiones a escalas superiores.</span><span class="sxs-lookup"><span data-stu-id="4b93d-176">Recording and managing project issues, including escalations</span></span></li>
<li><span data-ttu-id="4b93d-177">Lleva a cabo llamadas de control semanales.</span><span class="sxs-lookup"><span data-stu-id="4b93d-177">Conducting weekly stand up calls</span></span></li>
<li><span data-ttu-id="4b93d-178">Es el encargado de relacionarse y mantener informados a los patrocinadores ejecutivos del proyecto.</span><span class="sxs-lookup"><span data-stu-id="4b93d-178">Liaises with, and provides updates to project executive sponsors</span></span></li>
<li><span data-ttu-id="4b93d-179">Trabaja con el arquitecto para definir el enfoque de administración de cambios y los planes de comunicación.</span><span class="sxs-lookup"><span data-stu-id="4b93d-179">Working with the Architect to define the Change Management approach and Communication Plans</span></span></li></ul></td>
<td align="left"><span data-ttu-id="4b93d-180">Por añadir</span><span class="sxs-lookup"><span data-stu-id="4b93d-180">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="4b93d-181"><strong>Especialista en adopción/administración de cambios</strong></span><span class="sxs-lookup"><span data-stu-id="4b93d-181"><strong>Change Management/Adoption Specialist</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="4b93d-182">Aporta su punto de vista en la fase de descubrimiento sobre los procesos de adopción y formación.</span><span class="sxs-lookup"><span data-stu-id="4b93d-182">Provide input on Discovery phase into adoption and training processes</span></span></li>
<li><span data-ttu-id="4b93d-183">Participa en los talleres de estrategia de adopción.</span><span class="sxs-lookup"><span data-stu-id="4b93d-183">Participate in adoption strategy workshop</span></span></li>
<li><span data-ttu-id="4b93d-184">Se encarga de desarrollar la estrategia de adopción y es responsable de ella.</span><span class="sxs-lookup"><span data-stu-id="4b93d-184">Developing and responsible for adoption strategy</span></span></li>
<li><span data-ttu-id="4b93d-185">Se encarga de desarrollar y llevar a cabo el plan de comunicación.</span><span class="sxs-lookup"><span data-stu-id="4b93d-185">Developing and executing communication plan</span></span></li>
<li><span data-ttu-id="4b93d-186">Es responsable de proporcionar formación a los usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="4b93d-186">Responsible for delivering trainings to end users</span></span></li>
<li><span data-ttu-id="4b93d-187">Recopila comentarios y realiza encuestas.</span><span class="sxs-lookup"><span data-stu-id="4b93d-187">Collect feedback and conduct surveys</span></span></li></ul></td>
<td align="left"><span data-ttu-id="4b93d-188">Por añadir</span><span class="sxs-lookup"><span data-stu-id="4b93d-188">TBA</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="4b93d-189"><strong>Responsable de redes</strong></span><span class="sxs-lookup"><span data-stu-id="4b93d-189"><strong>Network Lead</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="4b93d-190">Aporta su punto de vista en la fase de descubrimiento sobre el diseño de redes.</span><span class="sxs-lookup"><span data-stu-id="4b93d-190">Providing input on Discovery phase into network design</span></span></li>
<li><span data-ttu-id="4b93d-191">Participa en la planificación durante el taller de Enfoque.</span><span class="sxs-lookup"><span data-stu-id="4b93d-191">Participating in planning during Envisioning workshop</span></span></li>
<li><span data-ttu-id="4b93d-192">Coordina el trabajo del equipo de redes durante la ejecución del proyecto.</span><span class="sxs-lookup"><span data-stu-id="4b93d-192">Coordinates work of networking team during the project execution</span></span></li></ul></td>
<td align="left"><span data-ttu-id="4b93d-193">Por añadir</span><span class="sxs-lookup"><span data-stu-id="4b93d-193">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="4b93d-194"><strong>Responsable de seguridad</strong></span><span class="sxs-lookup"><span data-stu-id="4b93d-194"><strong>Security Lead</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="4b93d-195">Aporta su punto de vista en la fase de descubrimiento sobre los procesos y el diseño de la seguridad.</span><span class="sxs-lookup"><span data-stu-id="4b93d-195">Providing input on Discovery phase into security design and processes</span></span></li>
<li><span data-ttu-id="4b93d-196">Participa en la planificación durante el taller de Enfoque.</span><span class="sxs-lookup"><span data-stu-id="4b93d-196">Participating in planning during Envisioning workshop</span></span></li>
<li><span data-ttu-id="4b93d-197">Coordina el trabajo del equipo de seguridad durante la ejecución del proyecto.</span><span class="sxs-lookup"><span data-stu-id="4b93d-197">Coordinates work of security team during the project execution</span></span></li></ul></td>
<td align="left"><span data-ttu-id="4b93d-198">Por añadir</span><span class="sxs-lookup"><span data-stu-id="4b93d-198">TBA</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="4b93d-199"><strong>Responsable de telefonía</strong></span><span class="sxs-lookup"><span data-stu-id="4b93d-199"><strong>Telephony Lead</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="4b93d-200">Aporta su punto de vista en la fase de descubrimiento sobre el diseño de la telefonía.</span><span class="sxs-lookup"><span data-stu-id="4b93d-200">Providing input on Discovery phase into telephony design</span></span></li>
<li><span data-ttu-id="4b93d-201">Participa en la planificación durante el taller de enfoque.</span><span class="sxs-lookup"><span data-stu-id="4b93d-201">Participating in planning during envisioning workshop</span></span></li>
<li><span data-ttu-id="4b93d-202">Coordina el trabajo del equipo de telefonía durante la ejecución del proyecto.</span><span class="sxs-lookup"><span data-stu-id="4b93d-202">Coordinates work of telephony team during the project execution</span></span></li></ul></td>
<td align="left"><span data-ttu-id="4b93d-203">Por añadir</span><span class="sxs-lookup"><span data-stu-id="4b93d-203">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="4b93d-204"><strong>Responsable de escritorio</strong></span><span class="sxs-lookup"><span data-stu-id="4b93d-204"><strong>Desktop Lead</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="4b93d-205">Aporta su punto de vista en la fase de descubrimiento sobre los clientes y el proceso de actualización.</span><span class="sxs-lookup"><span data-stu-id="4b93d-205">Providing input on Discovery phase into clients and update process</span></span></li>
<li><span data-ttu-id="4b93d-206">Participa en la planificación durante el taller de enfoque.</span><span class="sxs-lookup"><span data-stu-id="4b93d-206">Participating in planning during envisioning workshop</span></span></li>
<li><span data-ttu-id="4b93d-207">Coordina el trabajo del equipo de escritorio durante la ejecución del proyecto.</span><span class="sxs-lookup"><span data-stu-id="4b93d-207">Coordinates work of desktop team during the project execution</span></span></li></ul></td>
<td align="left"><span data-ttu-id="4b93d-208">Por añadir</span><span class="sxs-lookup"><span data-stu-id="4b93d-208">TBA</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="4b93d-209"><strong>Responsable del servicio de asistencia y soporte técnico</strong></span><span class="sxs-lookup"><span data-stu-id="4b93d-209"><strong>Support/Help Desk Lead</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="4b93d-210">Aporta su punto de vista en la fase de descubrimiento sobre el modelo operativo y de soporte.</span><span class="sxs-lookup"><span data-stu-id="4b93d-210">Providing input on Discovery phase into operational and support model</span></span></li>
<li><span data-ttu-id="4b93d-211">Participa en la planificación durante el taller de enfoque.</span><span class="sxs-lookup"><span data-stu-id="4b93d-211">Participating in planning during envisioning workshop</span></span></li>
<li><span data-ttu-id="4b93d-212">Participa en la planificación del modelo de soporte.</span><span class="sxs-lookup"><span data-stu-id="4b93d-212">Participating into support model planning</span></span></li>
<li><span data-ttu-id="4b93d-213">Coordina el trabajo de los recursos y los equipos de soporte técnico durante la ejecución del proyecto.</span><span class="sxs-lookup"><span data-stu-id="4b93d-213">Coordinates work of support teams/resources during the project execution</span></span></li></ul></td>
<td align="left"><span data-ttu-id="4b93d-214">Por añadir</span><span class="sxs-lookup"><span data-stu-id="4b93d-214">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="4b93d-215"><strong>Representantes de la unidad de negocio</strong></span><span class="sxs-lookup"><span data-stu-id="4b93d-215"><strong>Business Unit Representatives</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="4b93d-216">Contribuyen en la creación de los materiales y guías de adopción basados en el usuario final.</span><span class="sxs-lookup"><span data-stu-id="4b93d-216">Contribute in End User based adoption guides and materials</span></span></li>
<li><span data-ttu-id="4b93d-217">Contribuyen en la creación de casos de uso de negocio y los revisan.</span><span class="sxs-lookup"><span data-stu-id="4b93d-217">Contribute to and review Business Use Cases</span></span></li></ul></td>
<td align="left"><span data-ttu-id="4b93d-218">Por añadir</span><span class="sxs-lookup"><span data-stu-id="4b93d-218">TBA</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="4b93d-219"><strong>Responsable de implementación</strong></span><span class="sxs-lookup"><span data-stu-id="4b93d-219"><strong>Deployment Lead</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="4b93d-220">Garantiza que se cumplan los requisitos previos de implementación.</span><span class="sxs-lookup"><span data-stu-id="4b93d-220">Ensure that deployment prerequisites are met</span></span></li>
<li><span data-ttu-id="4b93d-221">Involucra a los recursos del cliente para que se impliquen en la preparación y la implementación de las actividades de las primeras fases.</span><span class="sxs-lookup"><span data-stu-id="4b93d-221">Engage customer resources to engage on prepare and deploy stage activities</span></span></li>
<li><span data-ttu-id="4b93d-222">Participa en reuniones para revisar, preparar e implementar el estado.</span><span class="sxs-lookup"><span data-stu-id="4b93d-222">Participate in meetings to review prepare and deploy status</span></span></li></ul></td>
<td align="left"><span data-ttu-id="4b93d-223">Por añadir</span><span class="sxs-lookup"><span data-stu-id="4b93d-223">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="4b93d-224"><strong>Administradores de TI</strong></span><span class="sxs-lookup"><span data-stu-id="4b93d-224"><strong>IT Admins</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="4b93d-225">Los profesionales de TI se encargan de ayudar en la planificación y ejecución de pruebas.</span><span class="sxs-lookup"><span data-stu-id="4b93d-225">IT Pros responsible for assistance with test planning and execution</span></span></li></ul></td>
<td align="left"><span data-ttu-id="4b93d-226">Por añadir</span><span class="sxs-lookup"><span data-stu-id="4b93d-226">TBA</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="4b93d-227"><strong>Propietario del servicio</strong></span><span class="sxs-lookup"><span data-stu-id="4b93d-227"><strong>Service Owner</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="4b93d-228">Es responsable de que el servicio de Audioconferencia funcione de forma continua.</span><span class="sxs-lookup"><span data-stu-id="4b93d-228">Is responsible for the operation of the Audio Conferencing service all up</span></span></li>
<li><span data-ttu-id="4b93d-229">Propietario del servicio de Audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="4b93d-229">Owner of Audio Conferencing service</span></span></li></ul></td>
<td align="left"><span data-ttu-id="4b93d-230">Por añadir</span><span class="sxs-lookup"><span data-stu-id="4b93d-230">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="4b93d-231"><strong>Experto en calidad</strong></span><span class="sxs-lookup"><span data-stu-id="4b93d-231"><strong>Quality Champion</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="4b93d-232">Genera calidad, fiabilidad y recopila opiniones de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="4b93d-232">Drives quality, reliability and user feedback</span></span></li>
<li><span data-ttu-id="4b93d-233">Identifica las tendencias en la calidad y propicia la corrección de los problemas con los equipos correspondientes.</span><span class="sxs-lookup"><span data-stu-id="4b93d-233">Identifies the quality trends and drive remediation with the respective teams</span></span></li>
<li><span data-ttu-id="4b93d-234">Mantiene informada a la directiva a través del comité directivo.</span><span class="sxs-lookup"><span data-stu-id="4b93d-234">Reports through the steering committee back to leadership</span></span></li>
<li><span data-ttu-id="4b93d-235">Informa sobre la calidad, la fiabilidad y las opiniones de los usuarios a través de Valorar mi llamada y Net Promoter Score.</span><span class="sxs-lookup"><span data-stu-id="4b93d-235">Reports on quality, reliability, and user sentiment through Rate My Call and Net Promoter Score</span></span></li></ul></td>
<td align="left"><span data-ttu-id="4b93d-236">Por añadir</span><span class="sxs-lookup"><span data-stu-id="4b93d-236">TBA</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="4b93d-237">_Tabla 2 Ejemplo de plantilla de matriz de participantes_</span><span class="sxs-lookup"><span data-stu-id="4b93d-237">_Table 2 Stakeholder matrix template example_</span></span>


> [!NOTE]
> <span data-ttu-id="4b93d-238">La tabla de ejemplos anterior y las tablas siguientes que se ofrecen en este documento se pueden usar como plantillas.</span><span class="sxs-lookup"><span data-stu-id="4b93d-238">The example table above and subsequent tables throughout this document serve as a template.</span></span> <span data-ttu-id="4b93d-239">La frase "Por añadir" indica que falta por completar con información como parte del proceso de planificación.</span><span class="sxs-lookup"><span data-stu-id="4b93d-239">You'll see "TBA" (to be added) for information that you need to complete as part of your planning process.</span></span>



<a name="define-objectives-and-key-results-key-success-indicators-and-risks"></a><span data-ttu-id="4b93d-240">Definir objetivos y resultados principales, indicadores de éxito principales y riesgos</span><span class="sxs-lookup"><span data-stu-id="4b93d-240">Define objectives and key results, key success indicators, and risks</span></span>
--------------------------------------------------------------------

<span data-ttu-id="4b93d-241">Con la participación de todas las partes involucradas en el proyecto, los casos de uso, el ámbito organizativo y las escalas de tiempo del proyecto se pueden traducir en objetivos y resultados principales (OKR, del inglés "objectives and key results"), y las medidas de éxito del proyecto se pueden definir en una lista de indicadores de éxito principales (KSI, del inglés "key success indicators").</span><span class="sxs-lookup"><span data-stu-id="4b93d-241">With the project stakeholders assembled, business use cases, organizational scope and project timelines can be translated into objectives and key results (OKRs) and the measures of project success can be defined into a list of key success indicators (KSIs).</span></span>

<span data-ttu-id="4b93d-242">Al contar con la plena participación de todos las partes involucradas en el proyecto a la hora de definir los OKR y los KSI, se garantiza el sentido de propiedad y su adecuación a los requisitos organizativos del negocio.</span><span class="sxs-lookup"><span data-stu-id="4b93d-242">Full participation from project stakeholders when defining the OKRs and KSIs will ensure sense of ownership and they are aligned to organizational business requirements.</span></span>

<span data-ttu-id="4b93d-243">Los OKR contendrán una lista de los objetivos que se establecieron al inicio del proyecto, con los principales resultados que se pueden medir y que se definen trimestralmente.</span><span class="sxs-lookup"><span data-stu-id="4b93d-243">OKRs will contain the list of objectives set in the beginning of the project, with measurable key results defined in a quarterly basis.</span></span> <span data-ttu-id="4b93d-244">Los principales resultados se revisan mensualmente para hacer un seguimiento del estado del proyecto general y, en función de cómo avancen, se podrán ir ajustando los planes trimestrales.</span><span class="sxs-lookup"><span data-stu-id="4b93d-244">The key results are reviewed monthly to track status of the overall project, and based on progress, adjustment to the quarterly plans can be made as needed.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><p><span data-ttu-id="4b93d-245"><strong>Visión:</strong> aumentar la productividad maximizando las inversiones de Office 365</span><span class="sxs-lookup"><span data-stu-id="4b93d-245"><strong>Vision</strong>: Increase productivity by maximizing Office 365 investments</span></span></p>
</th>
<th align="left"></th>
<th align="left"></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="4b93d-246"><strong>Objetivos</strong></span><span class="sxs-lookup"><span data-stu-id="4b93d-246"><strong>Objectives</strong></span></span></td>
<td align="left"><span data-ttu-id="4b93d-247"><strong>Resultados principales</strong></span><span class="sxs-lookup"><span data-stu-id="4b93d-247"><strong>Key Results</strong></span></span></td>
<td align="left"><span data-ttu-id="4b93d-248"><strong>Pendiente</strong></span><span class="sxs-lookup"><span data-stu-id="4b93d-248"><strong>To Do</strong></span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="4b93d-249">Implementar Audioconferencia en Microsoft Teams al final del año fiscal 2018</span><span class="sxs-lookup"><span data-stu-id="4b93d-249">Deploy Audio Conferencing in Teams by end of fiscal year 2018</span></span></td>
<td align="left"><span data-ttu-id="4b93d-250">T1 2018: implementar Audioconferencia en Microsoft Teams globalmente</span><span class="sxs-lookup"><span data-stu-id="4b93d-250">FY18Q1: Deploy Audio Conferencing in Teams globally</span></span></td>
<td align="left"><p><span data-ttu-id="4b93d-251">Enfoque</span><span class="sxs-lookup"><span data-stu-id="4b93d-251">Envision</span></span></p>
<ul><li><span data-ttu-id="4b93d-252">Crear el plan de éxito</span><span class="sxs-lookup"><span data-stu-id="4b93d-252">Create success plan</span></span></li>
<li><span data-ttu-id="4b93d-253">Crear un plan técnico de implementación muy detallado</span><span class="sxs-lookup"><span data-stu-id="4b93d-253">Create detailed technical implementation plan</span></span></li></ul>
<p><span data-ttu-id="4b93d-254">Incorporación</span><span class="sxs-lookup"><span data-stu-id="4b93d-254">Onboard</span></span></p>
<ul><li><span data-ttu-id="4b93d-255">Ejecutar el plan de éxito</span><span class="sxs-lookup"><span data-stu-id="4b93d-255">Execute success plan</span></span></li>
<li><span data-ttu-id="4b93d-256">Ejecutar el plan técnico de implementación</span><span class="sxs-lookup"><span data-stu-id="4b93d-256">Execute technical implementation plan</span></span></li></ul></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="4b93d-257">Retirar globalmente el servicio de Conferencia RTC antiguo a mediados del año fiscal 2018</span><span class="sxs-lookup"><span data-stu-id="4b93d-257">Decommission legacy PSTN Conferencing service globally by mid of fiscal year 2018</span></span></td>
<td align="left"><span data-ttu-id="4b93d-258">T2 2018: retirar globalmente el servicio de Conferencia RTC antiguo</span><span class="sxs-lookup"><span data-stu-id="4b93d-258">FY18Q2: Decommission legacy PSTN Conferencing service globally</span></span></td>
<td align="left"><p><span data-ttu-id="4b93d-259">Nuevos valores</span><span class="sxs-lookup"><span data-stu-id="4b93d-259">Drive Value</span></span></p>
<ul><li><span data-ttu-id="4b93d-260">Potenciar la participación del usuario e impulsar la adopción</span><span class="sxs-lookup"><span data-stu-id="4b93d-260">Boost user engagement and drive adoption</span></span></li>
<li><span data-ttu-id="4b93d-261">Administrar y prepararse para el cambio</span><span class="sxs-lookup"><span data-stu-id="4b93d-261">Manage and prepare change</span></span></li>
<li><span data-ttu-id="4b93d-262">Medir, compartir el éxito e iterar</span><span class="sxs-lookup"><span data-stu-id="4b93d-262">Measure, share success, and iterate</span></span></li></ul></td>
</tr>
</tbody>
</table>

<span data-ttu-id="4b93d-263">_Tabla 3 Ejemplo de OKR_</span><span class="sxs-lookup"><span data-stu-id="4b93d-263">_Table 3 Example of OKRs_</span></span>


<span data-ttu-id="4b93d-264">Los KSI miden la calidad y el éxito de los resultados principales, y complementan la naturaleza binaria de los OKR (conseguidos o no conseguidos) al detallar los buenos o los malos resultados.</span><span class="sxs-lookup"><span data-stu-id="4b93d-264">KSIs measure quality and success of the key results and complement the binary nature of OKRs (achieved or not achieved), by detailing the good and/or bad results.</span></span> <span data-ttu-id="4b93d-265">Para definir los KSI, recomendamos aplicar criterios SMART o criterios "específicos, medibles, atribuibles, realistas y temporales".</span><span class="sxs-lookup"><span data-stu-id="4b93d-265">When defining KSIs, we recommend leveraging the “specific, measurable, assignable, realistic, time-related” or SMART criteria.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4b93d-266">Tipo</span><span class="sxs-lookup"><span data-stu-id="4b93d-266">Type</span></span></th>
<th align="left"><p><span data-ttu-id="4b93d-267">Cuestiones &amp;</span><span class="sxs-lookup"><span data-stu-id="4b93d-267">KSI questions &amp;</span></span></p>
<p><span data-ttu-id="4b93d-268">criterios de KSI</span><span class="sxs-lookup"><span data-stu-id="4b93d-268">criteria</span></span></p></th>
<th align="left"><span data-ttu-id="4b93d-269">Cómo se miden</span><span class="sxs-lookup"><span data-stu-id="4b93d-269">How measured</span></span></th>
<th align="left"><span data-ttu-id="4b93d-270">Criterios de éxito</span><span class="sxs-lookup"><span data-stu-id="4b93d-270">Success criteria</span></span></th>
<th align="left"><span data-ttu-id="4b93d-271">Medidos</span><span class="sxs-lookup"><span data-stu-id="4b93d-271">Measured</span></span></th>
<th align="left"><span data-ttu-id="4b93d-272">Responsable</span><span class="sxs-lookup"><span data-stu-id="4b93d-272">Responsible</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="4b93d-273"><strong>Uso/adopción</strong></span><span class="sxs-lookup"><span data-stu-id="4b93d-273"><strong>Usage/adoption</strong></span></span></td>
<td align="left"><span data-ttu-id="4b93d-274">La calidad de las llamadas es igual o mejor que en la solución anterior</span><span class="sxs-lookup"><span data-stu-id="4b93d-274">Call quality is equal to or better than the previous solution</span></span></td>
<td align="left"><span data-ttu-id="4b93d-275">Encuesta</span><span class="sxs-lookup"><span data-stu-id="4b93d-275">Survey</span></span></td>
<td align="left"><span data-ttu-id="4b93d-276">El 80 % de los usuarios está de acuerdo o muy de acuerdo</span><span class="sxs-lookup"><span data-stu-id="4b93d-276">80% of users agree or strongly agree</span></span></td>
<td align="left"><span data-ttu-id="4b93d-277">Tras la habilitación y trimestralmente</span><span class="sxs-lookup"><span data-stu-id="4b93d-277">After enablement and quarterly</span></span></td>
<td align="left"><span data-ttu-id="4b93d-278">Equipo de tecnología de la información</span><span class="sxs-lookup"><span data-stu-id="4b93d-278">Information Technology team</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="4b93d-279"><strong>Uso/adopción</strong></span><span class="sxs-lookup"><span data-stu-id="4b93d-279"><strong>Usage/adoption</strong></span></span></td>
<td align="left"><span data-ttu-id="4b93d-280">El proceso de comunicación es más sencillo con Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4b93d-280">Teams made the communication process easier</span></span></td>
<td align="left"><span data-ttu-id="4b93d-281">Encuesta</span><span class="sxs-lookup"><span data-stu-id="4b93d-281">Survey</span></span></td>
<td align="left"><span data-ttu-id="4b93d-282">El 80 % de los usuarios está de acuerdo o muy de acuerdo</span><span class="sxs-lookup"><span data-stu-id="4b93d-282">80% of users agree or strongly agree</span></span></td>
<td align="left"><span data-ttu-id="4b93d-283">Tras la habilitación y trimestralmente</span><span class="sxs-lookup"><span data-stu-id="4b93d-283">After enablement and quarterly</span></span></td>
<td align="left"><span data-ttu-id="4b93d-284">Equipo de administración de cambios</span><span class="sxs-lookup"><span data-stu-id="4b93d-284">Change Management team</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="4b93d-285"><strong>Uso/adopción</strong></span><span class="sxs-lookup"><span data-stu-id="4b93d-285"><strong>Usage/adoption</strong></span></span></td>
<td align="left"><span data-ttu-id="4b93d-286">Los usuarios utilizan la solución activamente</span><span class="sxs-lookup"><span data-stu-id="4b93d-286">Users actively use the solution</span></span></td>
<td align="left"><span data-ttu-id="4b93d-287">Informes de Office 365, panel de calidad de llamadas</span><span class="sxs-lookup"><span data-stu-id="4b93d-287">Office 365 reports, Call Quality Dashboard</span></span></td>
<td align="left"><span data-ttu-id="4b93d-288">El 80 % de los usuarios son usuarios activos diarios</span><span class="sxs-lookup"><span data-stu-id="4b93d-288">80% of users are active daily users</span></span></td>
<td align="left"><span data-ttu-id="4b93d-289">A diario</span><span class="sxs-lookup"><span data-stu-id="4b93d-289">Daily</span></span></td>
<td align="left"><span data-ttu-id="4b93d-290">Equipo de administración de cambios</span><span class="sxs-lookup"><span data-stu-id="4b93d-290">Change Management team</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="4b93d-291"><strong>Uso/calidad</strong></span><span class="sxs-lookup"><span data-stu-id="4b93d-291"><strong>Usage/quality</strong></span></span></td>
<td align="left"><span data-ttu-id="4b93d-292">El porcentaje de llamadas/conferencias de mala calidad debe ser mínimo</span><span class="sxs-lookup"><span data-stu-id="4b93d-292">Percentage of poor calls/conferences should be minimal</span></span></td>
<td align="left"><span data-ttu-id="4b93d-293">Panel de calidad de llamadas</span><span class="sxs-lookup"><span data-stu-id="4b93d-293">Call Quality Dashboard</span></span></td>
<td align="left"><span data-ttu-id="4b93d-294">&lt; Un 5 % de llamadas de mala calidad al mes</span><span class="sxs-lookup"><span data-stu-id="4b93d-294">&lt; 5% of poor calls per month</span></span></td>
<td align="left"><span data-ttu-id="4b93d-295">A diario</span><span class="sxs-lookup"><span data-stu-id="4b93d-295">Daily</span></span></td>
<td align="left"><span data-ttu-id="4b93d-296">Equipo de tecnología de la información</span><span class="sxs-lookup"><span data-stu-id="4b93d-296">Information Technology team</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="4b93d-297"><strong>Uso/soporte</strong></span><span class="sxs-lookup"><span data-stu-id="4b93d-297"><strong>Usage/support</strong></span></span></td>
<td align="left"><span data-ttu-id="4b93d-298">Sé cómo conseguir soporte técnico</span><span class="sxs-lookup"><span data-stu-id="4b93d-298">I know how to get technical support</span></span></td>
<td align="left"><span data-ttu-id="4b93d-299">Encuesta</span><span class="sxs-lookup"><span data-stu-id="4b93d-299">Survey</span></span></td>
<td align="left"><span data-ttu-id="4b93d-300">El 90% de los usuarios está de acuerdo o muy de acuerdo</span><span class="sxs-lookup"><span data-stu-id="4b93d-300">90% of users agree or strongly agree</span></span></td>
<td align="left"><span data-ttu-id="4b93d-301">Tras la habilitación y trimestralmente</span><span class="sxs-lookup"><span data-stu-id="4b93d-301">After enablement and quarterly</span></span></td>
<td align="left"><span data-ttu-id="4b93d-302">Equipo de administración de cambios</span><span class="sxs-lookup"><span data-stu-id="4b93d-302">Change Management team</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="4b93d-303"><strong>Uso/soporte</strong></span><span class="sxs-lookup"><span data-stu-id="4b93d-303"><strong>Usage/support</strong></span></span></td>
<td align="left"><span data-ttu-id="4b93d-304">Estoy satisfecho con la calidad del soporte técnico</span><span class="sxs-lookup"><span data-stu-id="4b93d-304">I am satisfied with the quality of technical support</span></span></td>
<td align="left"><span data-ttu-id="4b93d-305">Encuesta</span><span class="sxs-lookup"><span data-stu-id="4b93d-305">Survey</span></span></td>
<td align="left"><span data-ttu-id="4b93d-306">El 80 % de los usuarios está de acuerdo o muy de acuerdo</span><span class="sxs-lookup"><span data-stu-id="4b93d-306">80% of users agree or strongly agree</span></span></td>
<td align="left"><span data-ttu-id="4b93d-307">Tras cada incidente</span><span class="sxs-lookup"><span data-stu-id="4b93d-307">After each incident</span></span></td>
<td align="left"><span data-ttu-id="4b93d-308">Equipo de tecnología de la información</span><span class="sxs-lookup"><span data-stu-id="4b93d-308">Information Technology team</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="4b93d-309"><strong>Financiero</strong></span><span class="sxs-lookup"><span data-stu-id="4b93d-309"><strong>Financial</strong></span></span></td>
<td align="left"><span data-ttu-id="4b93d-310">Reducción de los minutos de conferencias antiguas</span><span class="sxs-lookup"><span data-stu-id="4b93d-310">Reduction of legacy conferencing minutes</span></span></td>
<td align="left"><span data-ttu-id="4b93d-311">Sistema financiero</span><span class="sxs-lookup"><span data-stu-id="4b93d-311">Financial system</span></span></td>
<td align="left"><span data-ttu-id="4b93d-312">Cumplir el ROI definido</span><span class="sxs-lookup"><span data-stu-id="4b93d-312">Meet defined ROI</span></span></td>
<td align="left"><span data-ttu-id="4b93d-313">Basado en ROI</span><span class="sxs-lookup"><span data-stu-id="4b93d-313">Based on ROI</span></span></td>
<td align="left"><span data-ttu-id="4b93d-314">Equipo de administración de cambios</span><span class="sxs-lookup"><span data-stu-id="4b93d-314">Change Management team</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="4b93d-315">_Tabla 4 Ejemplo de KSI_</span><span class="sxs-lookup"><span data-stu-id="4b93d-315">_Table 4 Example of KSIs_</span></span>


<span data-ttu-id="4b93d-316">Como parte de este ejercicio, hay que identificar los riesgos del negocio y definir un plan de mitigación para cada uno de los riesgos que se identifiquen.</span><span class="sxs-lookup"><span data-stu-id="4b93d-316">You need to identify business risks as part of this exercise and define a mitigation plan for each identified risk.</span></span> <span data-ttu-id="4b93d-317">Esta información se puede plasmar en un plan de riesgos.</span><span class="sxs-lookup"><span data-stu-id="4b93d-317">This information can be captured into a risk plan.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4b93d-318">Riesgo</span><span class="sxs-lookup"><span data-stu-id="4b93d-318">Risk</span></span></th>
<th align="left"><span data-ttu-id="4b93d-319">Probabilidad</span><span class="sxs-lookup"><span data-stu-id="4b93d-319">Likelihood</span></span></th>
<th align="left"><span data-ttu-id="4b93d-320">Impacto</span><span class="sxs-lookup"><span data-stu-id="4b93d-320">Impact</span></span></th>
<th align="left"><span data-ttu-id="4b93d-321">General</span><span class="sxs-lookup"><span data-stu-id="4b93d-321">Overall</span></span></th>
<th align="left"><span data-ttu-id="4b93d-322">Plan de mitigación</span><span class="sxs-lookup"><span data-stu-id="4b93d-322">Mitigation plan</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="4b93d-323">Con la próxima fusión se sumarán hasta 1000 personas</span><span class="sxs-lookup"><span data-stu-id="4b93d-323">Upcoming merger will add up to 1,000 people</span></span></td>
<td align="left"><span data-ttu-id="4b93d-324">Alta</span><span class="sxs-lookup"><span data-stu-id="4b93d-324">High</span></span></td>
<td align="left"><span data-ttu-id="4b93d-325">Alta</span><span class="sxs-lookup"><span data-stu-id="4b93d-325">High</span></span></td>
<td align="left"><span data-ttu-id="4b93d-326">Alta</span><span class="sxs-lookup"><span data-stu-id="4b93d-326">High</span></span></td>
<td align="left"><p><span data-ttu-id="4b93d-327">Para las empresas fusionadas, OKR independiente con proceso propio (Enfoque, Incorporación, Nuevos valores).</span><span class="sxs-lookup"><span data-stu-id="4b93d-327">For merged companies, separate OKR with own process (Envision, Onboard, Drive Value)</span></span></p>
<p><span data-ttu-id="4b93d-328">No se deben incluir en los OKR existentes.</span><span class="sxs-lookup"><span data-stu-id="4b93d-328">Do not include them in existing OKRs</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="4b93d-329">La portabilidad de los números de teléfono retrasará la finalización del proyecto.</span><span class="sxs-lookup"><span data-stu-id="4b93d-329">Telephone number porting will delay project completion</span></span></td>
<td align="left"><span data-ttu-id="4b93d-330">Alta</span><span class="sxs-lookup"><span data-stu-id="4b93d-330">High</span></span></td>
<td align="left"><span data-ttu-id="4b93d-331">Alta</span><span class="sxs-lookup"><span data-stu-id="4b93d-331">High</span></span></td>
<td align="left"><span data-ttu-id="4b93d-332">Alta</span><span class="sxs-lookup"><span data-stu-id="4b93d-332">High</span></span></td>
<td align="left"><p><span data-ttu-id="4b93d-333">Se debe preparar con antelación toda la información para la portabilidad de los números de teléfono (registro de servicios al cliente, detalles de facturación, carta de autorización).</span><span class="sxs-lookup"><span data-stu-id="4b93d-333">Prepare all the required information to support telephone number porting ahead of time (i.e.: customer service record, billing details, Letter of Authorization)</span></span></p>
<p><span data-ttu-id="4b93d-334">La escala de tiempo del proyecto se debe ajustar para incluir el tiempo que se tarda en realizar la portabilidad de los números de teléfono.</span><span class="sxs-lookup"><span data-stu-id="4b93d-334">Adjust project timeline to accommodate turnaround time of telephone number porting execution</span></span></p>
<p><span data-ttu-id="4b93d-335">Se debe comunicar el uso de los nuevos números de conferencia de acceso telefónico local a los participantes externos.</span><span class="sxs-lookup"><span data-stu-id="4b93d-335">Communicate the use of new dial-in conferencing numbers to external participants</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="4b93d-336">Se ha planificado rediseñar las redes</span><span class="sxs-lookup"><span data-stu-id="4b93d-336">Planned network redesign</span></span></td>
<td align="left"><span data-ttu-id="4b93d-337">Alta</span><span class="sxs-lookup"><span data-stu-id="4b93d-337">High</span></span></td>
<td align="left"><span data-ttu-id="4b93d-338">Mediana</span><span class="sxs-lookup"><span data-stu-id="4b93d-338">Medium</span></span></td>
<td align="left"><span data-ttu-id="4b93d-339">Mediana</span><span class="sxs-lookup"><span data-stu-id="4b93d-339">Medium</span></span></td>
<td align="left"><span data-ttu-id="4b93d-340">Antes de implementar Microsoft Teams como plataforma de colaboración y comunicaciones moderna, evalúe la preparación de la red en los sitios que se incluyen en el ámbito del proyecto.</span><span class="sxs-lookup"><span data-stu-id="4b93d-340">Before implementing Teams as modern communications and collaboration platform, run network readiness assessment for sites in scope of the project</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="4b93d-341">_Tabla 5 Ejemplo de plan de riesgos_</span><span class="sxs-lookup"><span data-stu-id="4b93d-341">_Table 5 Risk plan example_</span></span>


<a name="assess-environment-and-evaluate-adoption-readiness"></a><span data-ttu-id="4b93d-342">Evaluar el entorno y la preparación que se tiene para la adopción</span><span class="sxs-lookup"><span data-stu-id="4b93d-342">Assess environment and evaluate adoption readiness</span></span>
--------------------------------------------------

<span data-ttu-id="4b93d-343">Para conseguir los OKR que se pretenden, es posible que tenga que definir una arquitectura de alto nivel de la solución.</span><span class="sxs-lookup"><span data-stu-id="4b93d-343">To achieve the intended OKRs, you may have to define the high-level architecture of the solution.</span></span> <span data-ttu-id="4b93d-344">De este modo, se evalúan todos los aspectos relacionados con la infraestructura de TI y telefonía, las redes y las operaciones a través del descubrimiento del entorno.</span><span class="sxs-lookup"><span data-stu-id="4b93d-344">It takes environmental discovery to evaluate all aspects relating to IT and telephony infrastructure, networking, and operations.</span></span>

<span data-ttu-id="4b93d-345">Todas las cuestiones relacionadas con la informática para usuarios finales, como la evaluación de la preparación de los ordenadores personales y los dispositivos móviles para admitir casos de uso de empresas para Audioconferencia, se incluirán como parte del proceso de descubrimiento del entorno.</span><span class="sxs-lookup"><span data-stu-id="4b93d-345">All matters related to end-user computing, such as readiness assessment of the personal computers and mobile devices to support Audio Conferencing business use cases, from hardware requirements to software requirements, will be included as part of the environmental discovery.</span></span>

<span data-ttu-id="4b93d-346">Con el descubrimiento del entorno también se puede poner de manifiesto si hay algún requisito para [transferir números de teléfono a Microsoft](https://support.office.com/article/Transfer-phone-numbers-to-Skype-for-Business-Online-47b3af8e-4171-4dec-8333-c956f108664e).</span><span class="sxs-lookup"><span data-stu-id="4b93d-346">Environmental discovery can also uncover if there are requirements to [transfer phone numbers to Microsoft](https://support.office.com/article/Transfer-phone-numbers-to-Skype-for-Business-Online-47b3af8e-4171-4dec-8333-c956f108664e).</span></span> <span data-ttu-id="4b93d-347">De este modo, la organización podrá ajustar el plan de proyecto y preparar toda la información que necesite para la portabilidad de los números.</span><span class="sxs-lookup"><span data-stu-id="4b93d-347">This will help your organization to adjust the project plan accordingly and prepare the necessary information required for number porting.</span></span> <span data-ttu-id="4b93d-348">El descubrimiento del entorno se puede llevar a cabo mediante el siguiente [cuestionario](https://go.microsoft.com/fwlink/?linkid=858995).</span><span class="sxs-lookup"><span data-stu-id="4b93d-348">You can perform environmental discovery by leveraging the following [questionnaire](https://go.microsoft.com/fwlink/?linkid=858995).</span></span>

<span data-ttu-id="4b93d-349">En el descubrimiento del entorno se debe incluir la evaluación de preparación de la red para asegurarse de que esta pueda soportar la implementación del servicio de Audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="4b93d-349">Environmental discovery must include network readiness assessment to ensure the network is ready to support the implementation of the Audio Conferencing service.</span></span>

<span data-ttu-id="4b93d-350">También se puede determinar si la red está preparada para soportar el servicio de Audioconferencia evaluando la información que se recopila en el descubrimiento del entorno (como los detalles de la conectividad a Internet y la topología de WAN, los vínculos a sitios, el ancho de banda disponible) y los datos de los análisis de personas (que se pueden traducir en el uso que se espera de cada carga de trabajo) en la [herramienta My Advisor Network Planner](https://go.microsoft.com/fwlink/?linkid=858999).</span><span class="sxs-lookup"><span data-stu-id="4b93d-350">Network readiness to support the Audio Conferencing service can be determined by leveraging the information captured through the environmental discovery (such as details of internet connectivity and WAN topology, site links, available bandwidth, and persona analysis data (that can be translated into an expected usage of each workload) into the [My Advisor Network Planner tool](https://go.microsoft.com/fwlink/?linkid=858999).</span></span> <span data-ttu-id="4b93d-351">Para confirmar en mayor medida el estado de la red, se puede realizar una simulación del tráfico multimedia en tiempo real con soluciones que proporcione [Microsoft](https://go.microsoft.com/fwlink/?linkid=859002) o los [socios de las herramientas para la evaluación de la preparación de la red](https://go.microsoft.com/fwlink/?linkid=859003).</span><span class="sxs-lookup"><span data-stu-id="4b93d-351">To further confirm network readiness, real-time media traffic simulation can be performed using the solutions provided by [Microsoft](https://go.microsoft.com/fwlink/?linkid=859002) or by [Network Readiness Assessment tools partners](https://go.microsoft.com/fwlink/?linkid=859003).</span></span>

<span data-ttu-id="4b93d-352">Con los resultados de esta evaluación se podrá tener una idea más clara de la corrección o la optimización que se necesita hacer en la red para que la implementación de Audioconferencia se pueda desarrollar correctamente.</span><span class="sxs-lookup"><span data-stu-id="4b93d-352">The results of the Network Readiness Assessment will paint a clearer picture of the required network optimization or remediation required for the success of Audio Conferencing implementation.</span></span>

<span data-ttu-id="4b93d-353">Para evaluar la preparación para la adopción se puede ejecutar un análisis de personas que genere una lista de las personas de la organización en las que se podrá llevar a cabo la implementación del servicio de Audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="4b93d-353">Adoption readiness can be evaluated by executing persona analysis to come up with a list of personas in the organization who can be targeted for the implementation of Audio Conferencing service.</span></span> <span data-ttu-id="4b93d-354">El análisis de personas incluye la identificación de otros periféricos y dispositivos que se necesitan para obtener los resultados de negocio que se desean.</span><span class="sxs-lookup"><span data-stu-id="4b93d-354">The persona analysis includes the identification of additional peripherals or devices required to realize the intended business outcomes.</span></span>

<span data-ttu-id="4b93d-355">Para realizar el análisis de personas, puede realizar un taller en el que se involucre a todas las partes relevantes del proyecto mediante la plataforma de talleres [Persona Alignment](https://go.microsoft.com/fwlink/?linkid=859005) y [Persona Feature Matrix](https://go.microsoft.com/fwlink/?linkid=859006).</span><span class="sxs-lookup"><span data-stu-id="4b93d-355">To perform persona analysis, you can conduct a workshop by involving relevant project stakeholders, leveraging the [Persona Alignment](https://go.microsoft.com/fwlink/?linkid=859005) workshop deck and [Persona Feature Matrix](https://go.microsoft.com/fwlink/?linkid=859006).</span></span> <span data-ttu-id="4b93d-356">El resultado de este taller de análisis de personas se puede resumir en un informe que se elabora con la plantilla [Persona Analysis Report](https://go.microsoft.com/fwlink/?linkid=859007).</span><span class="sxs-lookup"><span data-stu-id="4b93d-356">The result of persona analysis workshop can be summarized into a report using the [Persona Analysis Report](https://go.microsoft.com/fwlink/?linkid=859007) template.</span></span>


> [!NOTE]
> <span data-ttu-id="4b93d-357">Si bien el cuestionario de descubrimiento y los ejemplos de análisis de personas se crearon en un principio para Skype Empresarial Online, la mayoría del contenido es válido para Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="4b93d-357">While the Discovery Questionnaire and Persona Analysis examples were initially written for Skype for Business Online, a majority of the content is relevant to Teams.</span></span> <span data-ttu-id="4b93d-358">Modifique y quite los elementos que crea que no son relevantes de los objetivos del proyecto.</span><span class="sxs-lookup"><span data-stu-id="4b93d-358">Feel free to modify and remove items that are not relevant to the project goals.</span></span>


<span data-ttu-id="4b93d-359">Los riesgos técnicos se pueden identificar como parte de una evaluación del entorno y la evaluación de la preparación para la adopción, y se puede desarrollar un plan de mitigación para cada uno de los riesgos que se identifiquen.</span><span class="sxs-lookup"><span data-stu-id="4b93d-359">You can identify technical risks as part of an environmental assessment and adoption readiness evaluation and develop a mitigation plan for each identified risk.</span></span> <span data-ttu-id="4b93d-360">Esta información se debe incorporar en el plan de riesgos.</span><span class="sxs-lookup"><span data-stu-id="4b93d-360">This information should be incorporated as part of the risk plan.</span></span>

<a name="map-operational-roles"></a><span data-ttu-id="4b93d-361">Asignar roles operativos</span><span class="sxs-lookup"><span data-stu-id="4b93d-361">Map operational roles</span></span>
---------------------

<span data-ttu-id="4b93d-362">Planificar las operaciones e identificar a los equipos que utilizarán el servicio de Audioconferencia es un paso muy importante, ya que las operaciones deben comenzar cuando se habiliten los primeros usuarios del piloto.</span><span class="sxs-lookup"><span data-stu-id="4b93d-362">Planning for operations and identifying the teams that will operate the Audio Conferencing service is an important step, as operations must start when the first pilot users are enabled.</span></span> <span data-ttu-id="4b93d-363">Cada uno de los equipos que se identifiquen debe revisar y aceptar las tareas y las responsabilidades que se identifiquen y deben comenzar la preparación para utilizar el servicio de Audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="4b93d-363">Each identified team must review and agree on the tasks and responsibilities identified and start the preparation to operate the Audio Conferencing service.</span></span> <span data-ttu-id="4b93d-364">En la fase de preparación se podría incluir formación y capacitación, contratación de más personal o garantizar que los proveedores externos están listos para ofrecer el servicio.</span><span class="sxs-lookup"><span data-stu-id="4b93d-364">The preparation might include training and readiness, additional staffing, or ensuring external providers are set up to deliver the service.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4b93d-365">Rol operativo</span><span class="sxs-lookup"><span data-stu-id="4b93d-365">Operational Role</span></span></th>
<th align="left"><span data-ttu-id="4b93d-366">Descripción</span><span class="sxs-lookup"><span data-stu-id="4b93d-366">Description</span></span></th>
<th align="left"><span data-ttu-id="4b93d-367">Equipo</span><span class="sxs-lookup"><span data-stu-id="4b93d-367">Team</span></span></th>
<th align="left"><span data-ttu-id="4b93d-368">Datos de contacto</span><span class="sxs-lookup"><span data-stu-id="4b93d-368">Contact Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="4b93d-369">Propietario del servicio</span><span class="sxs-lookup"><span data-stu-id="4b93d-369">Service Owner</span></span></td>
<td align="left"><span data-ttu-id="4b93d-370">Propietario del servicio, interactuar con las divisiones de la empresa, estrategia</span><span class="sxs-lookup"><span data-stu-id="4b93d-370">Service owner, interface to business divisions, strategy</span></span></td>
<td align="left"><span data-ttu-id="4b93d-371">Por añadir</span><span class="sxs-lookup"><span data-stu-id="4b93d-371">TBA</span></span></td>
<td align="left"><span data-ttu-id="4b93d-372">Por añadir</span><span class="sxs-lookup"><span data-stu-id="4b93d-372">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="4b93d-373">Operaciones de Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="4b93d-373">Audio Conferencing Operations</span></span></td>
<td align="left"><span data-ttu-id="4b93d-374">Operaciones diarias, transferencia/adición/cambio de cuenta de dispositivo y usuario, supervisión</span><span class="sxs-lookup"><span data-stu-id="4b93d-374">Daily operations, user and device account move/add/change, monitoring</span></span></td>
<td align="left"><span data-ttu-id="4b93d-375">Por añadir</span><span class="sxs-lookup"><span data-stu-id="4b93d-375">TBA</span></span></td>
<td align="left"><span data-ttu-id="4b93d-376">Por añadir</span><span class="sxs-lookup"><span data-stu-id="4b93d-376">TBA</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="4b93d-377">Administrador de inquilinos</span><span class="sxs-lookup"><span data-stu-id="4b93d-377">Tenant Admin</span></span></td>
<td align="left"><span data-ttu-id="4b93d-378">Cambiar la configuración de todos los inquilinos, habilitar nuevas características</span><span class="sxs-lookup"><span data-stu-id="4b93d-378">Change tenant-wide settings, enable new features</span></span></td>
<td align="left"><span data-ttu-id="4b93d-379">Por añadir</span><span class="sxs-lookup"><span data-stu-id="4b93d-379">TBA</span></span></td>
<td align="left"><span data-ttu-id="4b93d-380">Por añadir</span><span class="sxs-lookup"><span data-stu-id="4b93d-380">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="4b93d-381">Servicio de asistencia</span><span class="sxs-lookup"><span data-stu-id="4b93d-381">Help Desk</span></span></td>
<td align="left"><span data-ttu-id="4b93d-382">Interactuar con usuarios finales que necesitan soporte</span><span class="sxs-lookup"><span data-stu-id="4b93d-382">Interface for end-users to get support</span></span></td>
<td align="left"><span data-ttu-id="4b93d-383">Por añadir</span><span class="sxs-lookup"><span data-stu-id="4b93d-383">TBA</span></span></td>
<td align="left"><span data-ttu-id="4b93d-384">Por añadir</span><span class="sxs-lookup"><span data-stu-id="4b93d-384">TBA</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="4b93d-385">Operaciones de red</span><span class="sxs-lookup"><span data-stu-id="4b93d-385">Network Operations</span></span></td>
<td align="left"><span data-ttu-id="4b93d-386">Cubre LAN, WAN, Wi-Fi y acceso a Internet</span><span class="sxs-lookup"><span data-stu-id="4b93d-386">Runs LAN, WAN, Wi-Fi, and Internet Access</span></span></td>
<td align="left"><span data-ttu-id="4b93d-387">Por añadir</span><span class="sxs-lookup"><span data-stu-id="4b93d-387">TBA</span></span></td>
<td align="left"><span data-ttu-id="4b93d-388">Por añadir</span><span class="sxs-lookup"><span data-stu-id="4b93d-388">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="4b93d-389">Cliente y equipo de puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="4b93d-389">Client &amp; Endpoints Team</span></span></td>
<td align="left"><span data-ttu-id="4b93d-390">Administrar implementaciones de escritorio</span><span class="sxs-lookup"><span data-stu-id="4b93d-390">Manage desktop deployments</span></span></td>
<td align="left"><span data-ttu-id="4b93d-391">Por añadir</span><span class="sxs-lookup"><span data-stu-id="4b93d-391">TBA</span></span></td>
<td align="left"><span data-ttu-id="4b93d-392">Por añadir</span><span class="sxs-lookup"><span data-stu-id="4b93d-392">TBA</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="4b93d-393">Operaciones de identidad</span><span class="sxs-lookup"><span data-stu-id="4b93d-393">Identity Operations</span></span></td>
<td align="left"><span data-ttu-id="4b93d-394">Administrar infraestructura de identidad (AD, ADFS, Azure AD)</span><span class="sxs-lookup"><span data-stu-id="4b93d-394">Manage identity infrastructure (AD, ADFS, Azure AD)</span></span></td>
<td align="left"><span data-ttu-id="4b93d-395">Por añadir</span><span class="sxs-lookup"><span data-stu-id="4b93d-395">TBA</span></span></td>
<td align="left"><span data-ttu-id="4b93d-396">Por añadir</span><span class="sxs-lookup"><span data-stu-id="4b93d-396">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="4b93d-397">Adopción/administración de cambios</span><span class="sxs-lookup"><span data-stu-id="4b93d-397">Adoption/change management</span></span></td>
<td align="left"><span data-ttu-id="4b93d-398">Administrar el reconocimiento, la formación y la adopción de la solución</span><span class="sxs-lookup"><span data-stu-id="4b93d-398">Manage awareness, training and adoption for the solution</span></span></td>
<td align="left"><span data-ttu-id="4b93d-399">Por añadir</span><span class="sxs-lookup"><span data-stu-id="4b93d-399">TBA</span></span></td>
<td align="left"><span data-ttu-id="4b93d-400">Por añadir</span><span class="sxs-lookup"><span data-stu-id="4b93d-400">TBA</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="4b93d-401">Operaciones de Exchange</span><span class="sxs-lookup"><span data-stu-id="4b93d-401">Exchange Operations</span></span></td>
<td align="left"><span data-ttu-id="4b93d-402">Administra el entorno de Exchange</span><span class="sxs-lookup"><span data-stu-id="4b93d-402">Manages the Exchange environment</span></span></td>
<td align="left"><span data-ttu-id="4b93d-403">Por añadir</span><span class="sxs-lookup"><span data-stu-id="4b93d-403">TBA</span></span></td>
<td align="left"><span data-ttu-id="4b93d-404">Por añadir</span><span class="sxs-lookup"><span data-stu-id="4b93d-404">TBA</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="4b93d-405">_Tabla 6 Ejemplo de la asignación de roles operativos_</span><span class="sxs-lookup"><span data-stu-id="4b93d-405">_Table 6 Example of operational roles mapping_</span></span>


<span data-ttu-id="4b93d-406">Para que la asignación de roles operativos se pueda llevar a cabo de una forma más detallada, incluidas las tareas asociadas a cada rol operativo, el [libro de trabajo para la asignación de roles operativos](https://www.skypeoperationsframework.com/Downloads?SelectedIDs=4_4_0_16) puede ser muy útil para capturar los detalles que determinarán con claridad cuáles son los roles y las responsabilidades que respaldarán el servicio de Audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="4b93d-406">To facilitate a more detailed operational roles mapping, including the tasks associated with each operational role, you can use the [Operational Role Mapping Workbook](https://www.skypeoperationsframework.com/Downloads?SelectedIDs=4_4_0_16) to capture the details that will provide the clarity around roles and responsibilities to support Audio Conferencing service.</span></span>

<a name="document-success-plan"></a><span data-ttu-id="4b93d-407">Documentar el plan de éxito</span><span class="sxs-lookup"><span data-stu-id="4b93d-407">Document success plan</span></span>
---------------------

<span data-ttu-id="4b93d-408">Un plan de éxito es la documentación que se crea en la fase de Enfoque y que consta del caso de negocio, la preparación del servicio, el plan de adopción y el plan operativo.</span><span class="sxs-lookup"><span data-stu-id="4b93d-408">A success plan is the documentation created in the Envision phase that consists of business case, service readiness, adoption plan, and operational plan.</span></span>

<span data-ttu-id="4b93d-409">El plan de éxito proporcionará al equipo del proyecto (que puede incluir FastTrack o el asociado de implementación) la información que le permita alcanzar los objetivos de la organización con el servicio de Audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="4b93d-409">The success plan will provide the project team, which can include FastTrack or deployment partner, with sufficient information to realize the organization’s goals with Audio Conferencing service.</span></span>

<span data-ttu-id="4b93d-410">En general, un plan de éxito contendrá las siguientes secciones principales:</span><span class="sxs-lookup"><span data-stu-id="4b93d-410">In general, a success plan will contain the following main sections:</span></span>

-   <span data-ttu-id="4b93d-411">Caso de negocio</span><span class="sxs-lookup"><span data-stu-id="4b93d-411">Business case</span></span>

-   <span data-ttu-id="4b93d-412">Preparación del servicio</span><span class="sxs-lookup"><span data-stu-id="4b93d-412">Service readiness</span></span>

-   <span data-ttu-id="4b93d-413">Plan de adopción</span><span class="sxs-lookup"><span data-stu-id="4b93d-413">Adoption plan</span></span>

-   <span data-ttu-id="4b93d-414">Plan operativo</span><span class="sxs-lookup"><span data-stu-id="4b93d-414">Operational plan</span></span>

### <a name="business-case"></a><span data-ttu-id="4b93d-415">Caso de negocio</span><span class="sxs-lookup"><span data-stu-id="4b93d-415">Business case</span></span>

<span data-ttu-id="4b93d-416">Los casos de uso de negocio, las partes interesadas, los OKR y los KSI, los riesgos y las escalas de tiempo del proyecto configuran normalmente la mayor parte de la información requerida para un caso de negocio.</span><span class="sxs-lookup"><span data-stu-id="4b93d-416">Business use cases, stakeholders, OKRs and KSIs, risks, and project timelines typically make up the bulk of information required for a business case.</span></span> <span data-ttu-id="4b93d-417">Es necesario documentarlos como parte del plan de éxito.</span><span class="sxs-lookup"><span data-stu-id="4b93d-417">You need to document them as part of the success plan.</span></span>

### <a name="service-readiness"></a><span data-ttu-id="4b93d-418">Preparación del servicio</span><span class="sxs-lookup"><span data-stu-id="4b93d-418">Service readiness</span></span>

<span data-ttu-id="4b93d-419">Con la evaluación del entorno se obtiene la información inicial que se necesita para determinar la preparación técnica de la organización para implementar la Audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="4b93d-419">Environmental assessment provides the initial information required to determine technical readiness for the organization to implement Audio Conferencing.</span></span>

<span data-ttu-id="4b93d-420">Aquí se incluye el plan para abordar las áreas que necesitan correcciones y que se han detectado durante la evolución del entorno.</span><span class="sxs-lookup"><span data-stu-id="4b93d-420">Included here is the plan to address areas needing remediation discovered through environmental assessment.</span></span> <span data-ttu-id="4b93d-421">Como parte del plan de éxito, hay que incluir la evaluación de preparación del servicio y el plan de corrección.</span><span class="sxs-lookup"><span data-stu-id="4b93d-421">You need to include the service readiness assessment and remediation plan as part of the success plan.</span></span>

### <a name="adoption-plan"></a><span data-ttu-id="4b93d-422">Plan de adopción</span><span class="sxs-lookup"><span data-stu-id="4b93d-422">Adoption plan</span></span>

<span data-ttu-id="4b93d-423">Tras evaluar la preparación de la adopción, es necesario completar otra planificación más detallada para que el equipo del proyecto pueda elaborar un conjunto completo de planes de comunicación, un plan de formación y actividades de adopción previas al lanzamiento, para el lanzamiento y posteriores al lanzamiento.</span><span class="sxs-lookup"><span data-stu-id="4b93d-423">Following an adoption readiness assessment, further detailed planning must be completed for the project team to come up with a comprehensive set of communication plans, training plan, and pre-launch, at-launch, and post-launch adoption activities.</span></span>

<span data-ttu-id="4b93d-424">En este paso también se identifican los recursos que respaldan las actividades de adopción, como prospectos, correos electrónicos de bienvenida y materiales de formación, junto con las personalizaciones que hay que hacer para cumplir los requisitos de la organización.</span><span class="sxs-lookup"><span data-stu-id="4b93d-424">Resources to support adoption activities such as flyers, welcome emails, and training materials are identified at this step, along with any customizations needed to meet organizational requirements.</span></span>

<span data-ttu-id="4b93d-425">Las plantillas para las actividades de adopción están disponibles [aquí](https://www.microsoft.com/download/details.aspx?id=54244).</span><span class="sxs-lookup"><span data-stu-id="4b93d-425">The templates for adoption activities are available [here](https://www.microsoft.com/download/details.aspx?id=54244).</span></span>

### <a name="operational-plan"></a><span data-ttu-id="4b93d-426">Plan operativo</span><span class="sxs-lookup"><span data-stu-id="4b93d-426">Operational plan</span></span>

<span data-ttu-id="4b93d-427">El ejercicio para la asignación de roles operativos establecerá los roles y las responsabilidades, así como los equipos asignados a cada rol operativo para respaldar la implementación de Audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="4b93d-427">Operational roles mapping exercise will establish the roles and responsibilities, and the teams assigned to each operational role to support the implementation of Audio Conferencing.</span></span>

<span data-ttu-id="4b93d-428">Hay que completarlo e incluir el plan operativo como parte del plan de éxito para garantizar la preparación operativa de la solución.</span><span class="sxs-lookup"><span data-stu-id="4b93d-428">You need to complete this and include the operational plan as part of the success plan to ensure operational readiness of the solution.</span></span>

<span data-ttu-id="4b93d-429">Planificación de Audioconferencia en Microsoft Teams  <a name="Planning_AudioConferencing"> </a></span><span class="sxs-lookup"><span data-stu-id="4b93d-429">Planning for Audio Conferencing in Teams  <a name="Planning_AudioConferencing"> </a></span></span>
========================================

<span data-ttu-id="4b93d-430">Para planificar la implementación de Audioconferencia en Microsoft Teams, hay que tomar una serie de decisiones con antelación para preparar mejor a la organización ante la implementación de una solución que cumpla los requisitos del negocio.</span><span class="sxs-lookup"><span data-stu-id="4b93d-430">To plan for the implementation of Audio Conferencing in Teams, a series of decisions must be made ahead of time to better prepare your organization to implement a solution that meets business requirements.</span></span> <span data-ttu-id="4b93d-431">Estas decisiones se documentarán en un plan de implementación técnico.</span><span class="sxs-lookup"><span data-stu-id="4b93d-431">These decisions will be documented into a technical implementation plan.</span></span>

|  |  |
|---------|---------|
|  <iframe width="350" height="200" src="https://www.youtube.com/embed/AWbuvcWcYIc" frameborder="0" allowfullscreen></iframe>    | |


## <a name="availability-of-audio-conferencing"></a><span data-ttu-id="4b93d-432">Disponibilidad de Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="4b93d-432">Availability of Audio Conferencing</span></span>

<span data-ttu-id="4b93d-433">Audioconferencia está disponible en estos [países y regiones](https://support.office.com/article/Countries-and-regions-that-are-supported-for-Skype-for-Business-Online-PSTN-Services-6ba72f37-d303-4795-aa8f-7e1845078ed7?ui=en-US&rs=en-US&ad=US).</span><span class="sxs-lookup"><span data-stu-id="4b93d-433">Audio Conferencing is available in these [countries and regions](https://support.office.com/article/Countries-and-regions-that-are-supported-for-Skype-for-Business-Online-PSTN-Services-6ba72f37-d303-4795-aa8f-7e1845078ed7?ui=en-US&rs=en-US&ad=US).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="4b93d-434">Por imperativo de carácter jurídico, para que Audioconferencia pueda estar disponible en organizaciones multinacionales, el contrato de suscripciones de Office 365 debe provenir de países y regiones que están cubiertos por el servicio de Audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="4b93d-434">Due to legal constraints, for Audio Conferencing to be available to multinational organizations, the contract for Office 365 subscriptions must be sourced from countries and regions covered by Audio Conferencing service.</span></span>

<span data-ttu-id="4b93d-435">Tras confirmar que su organización reúne los requisitos para poder usar el servicio de Audioconferencia, recopile la lista de ubicaciones de usuario u oficinas en las que se implementará el servicio de Audioconferencia según la lista de países y regiones disponibles.</span><span class="sxs-lookup"><span data-stu-id="4b93d-435">After confirming your organization’s eligibility for obtaining the Audio Conferencing service, compile the list of user locations or offices where Audio Conferencing service will be implemented based on the list of available countries and regions.</span></span>

<table>
<thead>
<tr class="header">
<td align="left"><img src="media/audio_conferencing_image7.png" /></td>
<td align="left"><span data-ttu-id="4b93d-436">Puntos de decisión</span><span class="sxs-lookup"><span data-stu-id="4b93d-436">Decision Points</span></span></td>
<td align="left"><p><span data-ttu-id="4b93d-437">Decida qué oficinas o ubicaciones de usuario implementarán el servicio de Audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="4b93d-437">Decide which user locations or offices will implement the Audio Conferencing service.</span></span></p></td>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="media/audio_conferencing_image9.png" /></td>
<td align="left"><span data-ttu-id="4b93d-438">Siguientes pasos</span><span class="sxs-lookup"><span data-stu-id="4b93d-438">Next Steps</span></span></td>
<td align="left"><p><span data-ttu-id="4b93d-439">Decida qué oficinas o ubicaciones de usuario se habilitarán para el servicio de Audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="4b93d-439">Document the user locations or offices to be enabled for the Audio Conferencing service.</span></span></p></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4b93d-440">Oficina</span><span class="sxs-lookup"><span data-stu-id="4b93d-440">Office</span></span></th>
<th align="left"><span data-ttu-id="4b93d-441">Ubicación</span><span class="sxs-lookup"><span data-stu-id="4b93d-441">Location</span></span></th>
<th align="left"><span data-ttu-id="4b93d-442">Servicio de conferencia RTC</span><span class="sxs-lookup"><span data-stu-id="4b93d-442">PSTN Conference Service</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="4b93d-443">One Epping Road</span><span class="sxs-lookup"><span data-stu-id="4b93d-443">One Epping Road</span></span></td>
<td align="left"><span data-ttu-id="4b93d-444">Australia</span><span class="sxs-lookup"><span data-stu-id="4b93d-444">Australia</span></span></td>
<td align="left"><span data-ttu-id="4b93d-445">Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="4b93d-445">Audio Conferencing</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="4b93d-446">100 Cyberport Road</span><span class="sxs-lookup"><span data-stu-id="4b93d-446">100 Cyberport Road</span></span></td>
<td align="left"><span data-ttu-id="4b93d-447">RAE de Hong Kong</span><span class="sxs-lookup"><span data-stu-id="4b93d-447">Hong Kong SAR</span></span></td>
<td align="left"><span data-ttu-id="4b93d-448">Conferencia RTC antigua</span><span class="sxs-lookup"><span data-stu-id="4b93d-448">Legacy PSTN Conferencing</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="4b93d-449">One Marina Boulevard</span><span class="sxs-lookup"><span data-stu-id="4b93d-449">One Marina Boulevard</span></span></td>
<td align="left"><span data-ttu-id="4b93d-450">Singapur</span><span class="sxs-lookup"><span data-stu-id="4b93d-450">Singapore</span></span></td>
<td align="left"><span data-ttu-id="4b93d-451">Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="4b93d-451">Audio Conferencing</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="4b93d-452">32 London Bridge Street</span><span class="sxs-lookup"><span data-stu-id="4b93d-452">32 London Bridge Street</span></span></td>
<td align="left"><span data-ttu-id="4b93d-453">Reino Unido</span><span class="sxs-lookup"><span data-stu-id="4b93d-453">United Kingdom</span></span></td>
<td align="left"><span data-ttu-id="4b93d-454">Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="4b93d-454">Audio Conferencing</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="4b93d-455">39 quai du Président Roosevelt</span><span class="sxs-lookup"><span data-stu-id="4b93d-455">39 quai du Président Roosevelt</span></span></td>
<td align="left"><span data-ttu-id="4b93d-456">Francia</span><span class="sxs-lookup"><span data-stu-id="4b93d-456">France</span></span></td>
<td align="left"><span data-ttu-id="4b93d-457">Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="4b93d-457">Audio Conferencing</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="4b93d-458">_Tabla 7 Ejemplo de una lista de habilitación del sitio de servicio de Audioconferencia_</span><span class="sxs-lookup"><span data-stu-id="4b93d-458">_Table 7 Example of Audio Conferencing service site enablement list_</span></span>


## <a name="licensing-for-audio-conferencing"></a><span data-ttu-id="4b93d-459">Licencias para Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="4b93d-459">Licensing for Audio Conferencing</span></span>

<span data-ttu-id="4b93d-460">La [licencia de Audioconferencia](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7?ui=en-US&rs=en-US&ad=US), anteriormente conocida como licencia de Conferencia RTC para Skype Empresarial, está disponible como parte de los planes de suscripción de Office 365 E5 o como un complemento a los planes de suscripción de Office 365 E3 o E1.</span><span class="sxs-lookup"><span data-stu-id="4b93d-460">[Audio Conferencing license](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7?ui=en-US&rs=en-US&ad=US), formerly known as Skype for Business PSTN Conferencing license, is available as part of Office 365 E5 subscription plans, or as an add-on to Office 365 E1 or Office 365 E3 subscription plans.</span></span>

> [!NOTE]
> <span data-ttu-id="4b93d-p120">Las conferencias de acceso telefónico local o RTC no admiten los proveedores de servicios de audioconferencia de terceros (ACP).<sup></sup> </span><span class="sxs-lookup"><span data-stu-id="4b93d-p120">PSTN or dial-in conferencing in Teams does not support 3<sup>rd</sup>-party Audio Conferencing Providers (ACPs). </span></span><br><span data-ttu-id="4b93d-462">Si está usando la Conferencia RTC para Skype Empresarial Online, puede beneficiarse al instante de Audioconferencia en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="4b93d-462">If you already use Skype for Business Online PSTN Conferencing today, you can immediately take advantage of Audio Conferencing in Teams.</span></span>

<span data-ttu-id="4b93d-463">Para proporcionar números de teléfono gratuitos para puentes de conferencia y admitir las conferencias por aceptación de llamada de números de teléfono internacionales, tendrá que configurar [Créditos de comunicaciones](https://support.office.com/article/What-is-PSTN-Consumption-billing-524dbea7-117f-493d-8005-6461f7f10059) para su organización.</span><span class="sxs-lookup"><span data-stu-id="4b93d-463">To provide toll-free conference bridge phone numbers and to support conferencing dial-out to International phone numbers, you need to setup [Communications Credits](https://support.office.com/article/What-is-PSTN-Consumption-billing-524dbea7-117f-493d-8005-6461f7f10059) for your organization.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="4b93d-464">En algunos países solo se pueden usar números de teléfono gratuitos para puentes de conferencia y, en tal caso, hay que usar obligatoriamente Créditos de comunicaciones para poder admitir el acceso telefónico local para esos países.</span><span class="sxs-lookup"><span data-stu-id="4b93d-464">Some countries are serviced by toll-free conference bridge phone numbers only, and in this case the use of Communications Credits is a mandatory requirement to support dial in for such countries.</span></span>

<span data-ttu-id="4b93d-465">La primera consideración que hay que tener en cuenta a la hora de implementar Créditos de comunicaciones es decidir la cantidad inicial de fondos que se deben adquirir.</span><span class="sxs-lookup"><span data-stu-id="4b93d-465">The first consideration to make when implementing Communications Credits is to decide the initial amount of funds to be purchased.</span></span> <span data-ttu-id="4b93d-466">La cantidad de fondos que se recomienda se puede mencionar en la documentación de [Créditos de comunicaciones](https://support.office.com/en-us/article/What-is-PSTN-Consumption-billing-524dbea7-117f-493d-8005-6461f7f10059).</span><span class="sxs-lookup"><span data-stu-id="4b93d-466">Recommended funding amounts can be referenced from the [Communications Credits](https://support.office.com/en-us/article/What-is-PSTN-Consumption-billing-524dbea7-117f-493d-8005-6461f7f10059) documentation.</span></span>

<span data-ttu-id="4b93d-467">Si su organización decide utilizar la recarga automática, también se incluye en la documentación de [Créditos de comunicaciones](https://support.office.com/article/What-is-PSTN-Consumption-billing-524dbea7-117f-493d-8005-6461f7f10059) una recomendación para el umbral (la cantidad más baja de fondos).</span><span class="sxs-lookup"><span data-stu-id="4b93d-467">If your organization chooses to use auto-recharge, a recommendation on the trigger (lowest amount of funds) is also included in the [Communications Credits](https://support.office.com/article/What-is-PSTN-Consumption-billing-524dbea7-117f-493d-8005-6461f7f10059) documentation.</span></span> <span data-ttu-id="4b93d-468">El importe de recarga automática se determina por el uso real.</span><span class="sxs-lookup"><span data-stu-id="4b93d-468">Auto-recharge amount needs to be determined by the actual usage.</span></span> <span data-ttu-id="4b93d-469">El uso de Créditos de comunicación se debe supervisar con el paso del tiempo y hay que ajustar la cantidad de recarga según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="4b93d-469">Communications Credits usage should be monitored over time and the recharge amount needs to be adjusted as required.</span></span>

<table>
<thead>
<tr class="header">
<td align="left"><img src="media/audio_conferencing_image7.png" /></td>
<td align="left"><span data-ttu-id="4b93d-470">Puntos de decisión</span><span class="sxs-lookup"><span data-stu-id="4b93d-470">Decision Points</span></span></td>
<td align="left"><ul><li><span data-ttu-id="4b93d-471">Si su organización aún no ha adquirido las licencias de Audioconferencia que necesita, decida si las licencias de Audioconferencia se van a adquirir incrementando las suscripciones existentes de Office 365 o comprando complementos de Audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="4b93d-471">If your organization has not already purchased the required Audio Conferencing licensing, decide whether Audio Conferencing licenses will be acquired by stepping up existing Office 365 subscriptions or by acquiring Audio Conferencing add-ons.</span></span></li>
<li><span data-ttu-id="4b93d-472">Decida si los Créditos de comunicaciones son necesarios para la implementación de Audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="4b93d-472">Decide if Communications Credits is required for Audio Conferencing implementation.</span></span> <span data-ttu-id="4b93d-473">En tal caso, decida la cantidad inicial de fondos que se va a comprar.</span><span class="sxs-lookup"><span data-stu-id="4b93d-473">If so, decide the initial amount of funds to be purchased.</span></span> <span data-ttu-id="4b93d-474">Cuando sea necesario, decida la cantidad para el umbral y la cantidad de autorecarga.</span><span class="sxs-lookup"><span data-stu-id="4b93d-474">Where applicable, decide the trigger amount and auto-recharge amount.</span></span></li></ul></td>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="media/audio_conferencing_image9.png" /></td>
<td align="left"><span data-ttu-id="4b93d-475">Siguientes pasos</span><span class="sxs-lookup"><span data-stu-id="4b93d-475">Next Steps</span></span></td>
<td align="left"><ul><li><span data-ttu-id="4b93d-476">Documente los usuarios a los que se les asignará la licencia de Audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="4b93d-476">Document the users that will be assigned Audio Conferencing license.</span></span></li>
<li><span data-ttu-id="4b93d-477">Documente el plan de Créditos de comunicaciones (cantidad inicial, cantidad de umbral, cantidad de recarga automática).</span><span class="sxs-lookup"><span data-stu-id="4b93d-477">Document the Communications Credits plan (initial amount, trigger amount, auto-recharge amount).</span></span></li></ul></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4b93d-478">Usuario</span><span class="sxs-lookup"><span data-stu-id="4b93d-478">User</span></span></th>
<th align="left"><span data-ttu-id="4b93d-479">Oficina</span><span class="sxs-lookup"><span data-stu-id="4b93d-479">Office</span></span></th>
<th align="left"><span data-ttu-id="4b93d-480">Licencia de Office 365</span><span class="sxs-lookup"><span data-stu-id="4b93d-480">Office 365 License</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="4b93d-481">Adele Vance</span><span class="sxs-lookup"><span data-stu-id="4b93d-481">Adele Vance</span></span></td>
<td align="left"><span data-ttu-id="4b93d-482">One Epping Road</span><span class="sxs-lookup"><span data-stu-id="4b93d-482">One Epping Road</span></span></td>
<td align="left"><span data-ttu-id="4b93d-483">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="4b93d-483">Office 365 E5</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="4b93d-484">Alex Wilber</span><span class="sxs-lookup"><span data-stu-id="4b93d-484">Alex Wilber</span></span></td>
<td align="left"><span data-ttu-id="4b93d-485">One Epping Road</span><span class="sxs-lookup"><span data-stu-id="4b93d-485">One Epping Road</span></span></td>
<td align="left"><span data-ttu-id="4b93d-486">Office 365 E3, complemento de Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="4b93d-486">Office 365 E3, Audio Conferencing add-on</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="4b93d-487">Ben Walters</span><span class="sxs-lookup"><span data-stu-id="4b93d-487">Ben Walters</span></span></td>
<td align="left"><span data-ttu-id="4b93d-488">One Epping Road</span><span class="sxs-lookup"><span data-stu-id="4b93d-488">One Epping Road</span></span></td>
<td align="left"><span data-ttu-id="4b93d-489">Office 365 E3, complemento de Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="4b93d-489">Office 365 E3, Audio Conferencing add-on</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="4b93d-490">Christie Cline</span><span class="sxs-lookup"><span data-stu-id="4b93d-490">Christie Cline</span></span></td>
<td align="left"><span data-ttu-id="4b93d-491">One Marina Boulevard</span><span class="sxs-lookup"><span data-stu-id="4b93d-491">One Marina Boulevard</span></span></td>
<td align="left"><span data-ttu-id="4b93d-492">Office 365 E3, complemento de Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="4b93d-492">Office 365 E3, Audio Conferencing add-on</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="4b93d-493">Debra Berger</span><span class="sxs-lookup"><span data-stu-id="4b93d-493">Debra Berger</span></span></td>
<td align="left"><span data-ttu-id="4b93d-494">One Marina Boulevard</span><span class="sxs-lookup"><span data-stu-id="4b93d-494">One Marina Boulevard</span></span></td>
<td align="left"><span data-ttu-id="4b93d-495">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="4b93d-495">Office 365 E5</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="4b93d-496">Lee Gu</span><span class="sxs-lookup"><span data-stu-id="4b93d-496">Lee Gu</span></span></td>
<td align="left"><span data-ttu-id="4b93d-497">One Marina Boulevard</span><span class="sxs-lookup"><span data-stu-id="4b93d-497">One Marina Boulevard</span></span></td>
<td align="left"><span data-ttu-id="4b93d-498">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="4b93d-498">Office 365 E5</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="4b93d-499">Emily Braun</span><span class="sxs-lookup"><span data-stu-id="4b93d-499">Emily Braun</span></span></td>
<td align="left"><span data-ttu-id="4b93d-500">32 London Bridge Street</span><span class="sxs-lookup"><span data-stu-id="4b93d-500">32 London Bridge Street</span></span></td>
<td align="left"><span data-ttu-id="4b93d-501">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="4b93d-501">Office 365 E5</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="4b93d-502">Lidia Holloway</span><span class="sxs-lookup"><span data-stu-id="4b93d-502">Lidia Holloway</span></span></td>
<td align="left"><span data-ttu-id="4b93d-503">32 London Bridge Street</span><span class="sxs-lookup"><span data-stu-id="4b93d-503">32 London Bridge Street</span></span></td>
<td align="left"><span data-ttu-id="4b93d-504">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="4b93d-504">Office 365 E5</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="4b93d-505">Pradeep Gupta</span><span class="sxs-lookup"><span data-stu-id="4b93d-505">Pradeep Gupta</span></span></td>
<td align="left"><span data-ttu-id="4b93d-506">32 London Bridge Street</span><span class="sxs-lookup"><span data-stu-id="4b93d-506">32 London Bridge Street</span></span></td>
<td align="left"><span data-ttu-id="4b93d-507">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="4b93d-507">Office 365 E5</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="4b93d-508">Marcel Beauchamp</span><span class="sxs-lookup"><span data-stu-id="4b93d-508">Marcel Beauchamp</span></span></td>
<td align="left"><span data-ttu-id="4b93d-509">39 quai du Président Roosevelt</span><span class="sxs-lookup"><span data-stu-id="4b93d-509">39 quai du Président Roosevelt</span></span></td>
<td align="left"><span data-ttu-id="4b93d-510">Office 365 E3, complemento de Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="4b93d-510">Office 365 E3, Audio Conferencing add-on</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="4b93d-511">Rachelle Cormier</span><span class="sxs-lookup"><span data-stu-id="4b93d-511">Rachelle Cormier</span></span></td>
<td align="left"><span data-ttu-id="4b93d-512">39 quai du Président Roosevelt</span><span class="sxs-lookup"><span data-stu-id="4b93d-512">39 quai du Président Roosevelt</span></span></td>
<td align="left"><span data-ttu-id="4b93d-513">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="4b93d-513">Office 365 E5</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="4b93d-514">Isabell Potvin</span><span class="sxs-lookup"><span data-stu-id="4b93d-514">Isabell Potvin</span></span></td>
<td align="left"><span data-ttu-id="4b93d-515">39 quai du Président Roosevelt</span><span class="sxs-lookup"><span data-stu-id="4b93d-515">39 quai du Président Roosevelt</span></span></td>
<td align="left"><span data-ttu-id="4b93d-516">Office 365 E3, complemento de Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="4b93d-516">Office 365 E3, Audio Conferencing add-on</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="4b93d-517">_Tabla 8 Ejemplo de una lista de asignación de licencias para los organizadores de reuniones de Audioconferencia_</span><span class="sxs-lookup"><span data-stu-id="4b93d-517">_Table 8 Example of license assignment list for Audio Conferencing meeting organizers_</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4b93d-518">Cantidad inicial</span><span class="sxs-lookup"><span data-stu-id="4b93d-518">Initial amount</span></span></th>
<td align="left"><span data-ttu-id="4b93d-519">1000 $</span><span class="sxs-lookup"><span data-stu-id="4b93d-519">$ 1,000</span></span></td>
</tr>
</thead>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4b93d-520">Cantidad de umbral</span><span class="sxs-lookup"><span data-stu-id="4b93d-520">Trigger amount</span></span></th>
<td align="left"><span data-ttu-id="4b93d-521">400 $</span><span class="sxs-lookup"><span data-stu-id="4b93d-521">$ 400</span></span></td>
</tr>
<tr class="header">
<th align="left"><span data-ttu-id="4b93d-522">Cantidad de recarga automática</span><span class="sxs-lookup"><span data-stu-id="4b93d-522">Auto-recharge amount</span></span></th>
<td align="left"><span data-ttu-id="4b93d-523">Por añadir</span><span class="sxs-lookup"><span data-stu-id="4b93d-523">TBA</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="4b93d-524">_Tabla 9 Ejemplo de números de planificación de Créditos de comunicaciones_</span><span class="sxs-lookup"><span data-stu-id="4b93d-524">_Table 9 Example of Communications Credits planning numbers_</span></span>


## <a name="conference-bridge-phone-numbers"></a><span data-ttu-id="4b93d-525">Números de teléfono para puentes de conferencia</span><span class="sxs-lookup"><span data-stu-id="4b93d-525">Conference bridge phone numbers</span></span>

<span data-ttu-id="4b93d-526">El servicio de Audioconferencia en Office 365 incluye:</span><span class="sxs-lookup"><span data-stu-id="4b93d-526">The Audio Conferencing service in Office 365 includes:</span></span>

-   <span data-ttu-id="4b93d-527">Varios tipos de números de teléfono para puentes de conferencia (gratuitos y de pago)</span><span class="sxs-lookup"><span data-stu-id="4b93d-527">Multiple types of conference bridge phone numbers (Toll and Toll-Free)</span></span>

-   <span data-ttu-id="4b93d-528">Varias categorías del número de teléfono (dedicado y compartido)</span><span class="sxs-lookup"><span data-stu-id="4b93d-528">Multiple categories of the phone number (dedicated and shared)</span></span>

-   <span data-ttu-id="4b93d-529">Soporte para varios idiomas del puente de conferencia (principal y secundario)</span><span class="sxs-lookup"><span data-stu-id="4b93d-529">Support for multiple languages for the conference bridge (primary and secondary)</span></span>

-   <span data-ttu-id="4b93d-530">Un número de teléfono predeterminado para el inquilino.</span><span class="sxs-lookup"><span data-stu-id="4b93d-530">A default phone number for the tenant.</span></span>

<span data-ttu-id="4b93d-531">La descripción completa de las funcionalidades que se incluyen se puede extraer de [Configurar conferencias de acceso telefónico local o RTC para Skype Empresarial](https://support.office.com/article/Set-up-dial-in-or-PSTN-conferencing-for-Skype-for-Business-d01954f1-4f37-4cf5-a636-20039e5c59e9?ui=en-US&rs=en-US&ad=US) y [Números de teléfono para las conferencias de Audio](https://support.office.com/article/Phone-numbers-for-dial-in-conferencing-95a08f84-04e5-4f72-88a8-d6472a7c89d7?ui=en-US&rs=en-US&ad=US)**.**</span><span class="sxs-lookup"><span data-stu-id="4b93d-531">Full description of the included capabilities can be referenced from [Set up dial-in or PSTN conferencing for Skype for Business](https://support.office.com/article/Set-up-dial-in-or-PSTN-conferencing-for-Skype-for-Business-d01954f1-4f37-4cf5-a636-20039e5c59e9?ui=en-US&rs=en-US&ad=US) and [Phone numbers for dial-in conferencing](https://support.office.com/article/Phone-numbers-for-dial-in-conferencing-95a08f84-04e5-4f72-88a8-d6472a7c89d7?ui=en-US&rs=en-US&ad=US)**.**</span></span>

> [!NOTE]
> <span data-ttu-id="4b93d-532">Los números de teléfono dedicados para puentes de conferencia se tienen en cuenta como parte del límite de números de teléfono que se pueden adquirir por inquilino, según el número de licencias que corresponden, como se describe en [Obtener números de teléfono de servicio de Skype Empresarial](https://support.office.com/article/Getting-Skype-for-Business-service-phone-numbers-e434aeb2-af99-40e7-981e-a474f0383734).</span><span class="sxs-lookup"><span data-stu-id="4b93d-532">Dedicated conference bridge phone numbers are counted towards the limit of phone numbers that can be acquired per tenant, based on the number of applicable licenses as described in [Getting Skype for Business service phone numbers](https://support.office.com/article/Getting-Skype-for-Business-service-phone-numbers-e434aeb2-af99-40e7-981e-a474f0383734).</span></span> <span data-ttu-id="4b93d-533">Los números de teléfono gratuitos para puentes de conferencia necesitan los Créditos de comunicaciones.</span><span class="sxs-lookup"><span data-stu-id="4b93d-533">Toll-free conference bridge phone numbers require Communications Credits.</span></span>

<span data-ttu-id="4b93d-534">Si ya hay números de teléfono para puentes de conferencia que hay que transferir al servicio de Audioconferencia, teniendo en cuenta que cumplen los requisitos para cada país o región, los números de teléfono para puentes de conferencia existentes se pueden transferir a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4b93d-534">If there are existing conference bridge phone numbers that must be transferred to the Audio Conferencing service, assuming they are meeting the country-specific requirements, then the existing conference bridge phone numbers can be transferred to Microsoft.</span></span>


> [!NOTE]
> <span data-ttu-id="4b93d-535">La complejidad que entraña la transferencia de los números de teléfono a Microsoft varía enormemente según cuáles sean los países y las regiones, los operadores, el número de circuitos involucrados y muchos otros factores.</span><span class="sxs-lookup"><span data-stu-id="4b93d-535">Complexity of transferring phone numbers to Microsoft varies greatly based on the countries or regions, carriers, the number of circuits involved, and many other contributing factors.</span></span> <span data-ttu-id="4b93d-536">Para planificar la portabilidad de los números de teléfono, revise la [guía de portabilidad de números](https://go.microsoft.com/fwlink/?linkid=859011).</span><span class="sxs-lookup"><span data-stu-id="4b93d-536">To plan for phone number porting, check out the [Number Porting Guide](https://go.microsoft.com/fwlink/?linkid=859011).</span></span>

|  |  |
|---------|---------|
| <iframe width="350" height="200" src="https://www.youtube.com/embed/5k0C21KAsns" frameborder="0" allowfullscreen></iframe>  |  |

<span data-ttu-id="4b93d-537">Encontrará más detalles sobre la transferencia de números de teléfono al servicio de Audioconferencia en [Transferir números de teléfono a Skype Empresarial Online](https://support.office.com/article/Transfer-phone-numbers-to-Skype-for-Business-Online-47b3af8e-4171-4dec-8333-c956f108664e).</span><span class="sxs-lookup"><span data-stu-id="4b93d-537">Additional details on transferring phone numbers to Audio Conferencing service can be found in [Transfer phone numbers to Skype for Business Online](https://support.office.com/article/Transfer-phone-numbers-to-Skype-for-Business-Online-47b3af8e-4171-4dec-8333-c956f108664e).</span></span>

<table>
<thead>
<tr class="header">
<td align="left"><img src="media/audio_conferencing_image7.png" /></td>
<td align="left"><span data-ttu-id="4b93d-538">Puntos de decisión</span><span class="sxs-lookup"><span data-stu-id="4b93d-538">Decision Points</span></span></td>
<td align="left"><ul><li><span data-ttu-id="4b93d-539">Decida si la organización necesita números de teléfono dedicados para puentes de conferencia.</span><span class="sxs-lookup"><span data-stu-id="4b93d-539">Decide whether the organization requires dedicated conference bridge phone numbers</span></span></li>
<li><span data-ttu-id="4b93d-540">Decida cómo se obtendrán los números de teléfono dedicados para puentes de conferencia para las oficinas o ubicaciones de usuario que entran dentro de la implementación de Audioconferencia (obtenerlos de Microsoft o transferir números de teléfono existentes).</span><span class="sxs-lookup"><span data-stu-id="4b93d-540">Decide how the dedicated conference bridge phone numbers will be obtained for user locations or offices in-scope for the Audio Conferencing implementation (obtain from Microsoft or transfer existing phone numbers)</span></span></li>
<li><span data-ttu-id="4b93d-541">Si elige obtenerlos de Microsoft, decida el método para obtener los números de teléfono (envío de formulario o automatizado) para las oficinas o ubicaciones de usuario que entran dentro de la implementación de Audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="4b93d-541">If you choose to obtain from Microsoft, decide the method to obtain phone numbers (form submission or automated) for user locations or offices in-scope for the Audio Conferencing implementation</span></span></li>
<li><span data-ttu-id="4b93d-542">Decida las preferencias de idioma que se deben configurar para cada número de teléfono dedicado para puentes de conferencia.</span><span class="sxs-lookup"><span data-stu-id="4b93d-542">Decide the language preferences to be set up for each dedicated conference bridge phone number</span></span></li>
<li><span data-ttu-id="4b93d-543">Decida el número de teléfono predeterminado para puentes de conferencia del inquilino.</span><span class="sxs-lookup"><span data-stu-id="4b93d-543">Decide the tenant default conference bridge phone number</span></span></li></ul></td>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="media/audio_conferencing_image9.png" /></td>
<td align="left"><span data-ttu-id="4b93d-544">Siguientes pasos</span><span class="sxs-lookup"><span data-stu-id="4b93d-544">Next Steps</span></span></td>
<td align="left"><ul><li><span data-ttu-id="4b93d-545">Documente el plan maestro para la adquisición de números de teléfono y especifique cómo se obtendrán los números de teléfono para cada oficina o ubicación de usuario que entra dentro de la implementación de Audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="4b93d-545">Document the master plan for phone numbers acquisition, detailing how phone numbers will be obtained for each user location or office in-scope for the Audio Conferencing implementation.</span></span></li>
<li><span data-ttu-id="4b93d-546">Si corresponde, complete <a href="https://support.office.com/article/Get-phone-numbers-for-Skype-for-Business-Online-6b61cb3c-361c-48a8-a9ef-d81bddde27bb?ui=en-US&amp;rs=en-US&amp;ad=US">un formulario de solicitud de número de teléfono nuevo</a> por cada oficina o ubicación.</span><span class="sxs-lookup"><span data-stu-id="4b93d-546">If applicable, complete <a href="https://support.office.com/article/Get-phone-numbers-for-Skype-for-Business-Online-6b61cb3c-361c-48a8-a9ef-d81bddde27bb?ui=en-US&amp;rs=en-US&amp;ad=US">the New Telephone Number Request form</a>, one form for each location or office</span></span></li>
<li><span data-ttu-id="4b93d-547">Si elige transferir números de teléfono existentes, revise la <a href="https://go.microsoft.com/fwlink/?linkid=859011">guía de portabilidad de números</a> para planificar y ajustar el tiempo de implementación de Audioconferencia de forma acorde.</span><span class="sxs-lookup"><span data-stu-id="4b93d-547">If you choose to transfer existing phone numbers, check out the <a href="https://go.microsoft.com/fwlink/?linkid=859011">Number Porting Guide</a> to plan it and adjust Audio Conferencing implementation timeline accordingly.</span></span></li>
<li><span data-ttu-id="4b93d-548">Documente las configuraciones de los números de teléfono para puentes de conferencia (números de teléfono compartidos y dedicados para puentes de conferencia, preferencias de idioma para cada número de teléfono dedicado para puente de conferencia, número de teléfono predeterminado para puente de conferencia del inquilino).</span><span class="sxs-lookup"><span data-stu-id="4b93d-548">Document the detailed conference bridge phone number configurations (shared and dedicated conference bridge phone numbers, language preferences for each dedicated conference bridge phone number, tenant default conference bridge phone number)</span></span></li></ul></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4b93d-549">Oficina</span><span class="sxs-lookup"><span data-stu-id="4b93d-549">Office</span></span></th>
<th align="left"><span data-ttu-id="4b93d-550">Adquisición de número de puente y tipo de puente</span><span class="sxs-lookup"><span data-stu-id="4b93d-550">Bridge Number Acquisition and Bridge Type</span></span></th>
<th align="left"><span data-ttu-id="4b93d-551">Número de puente</span><span class="sxs-lookup"><span data-stu-id="4b93d-551">Bridge Number</span></span></th>
<th align="left"><span data-ttu-id="4b93d-552">Idioma de puente</span><span class="sxs-lookup"><span data-stu-id="4b93d-552">Bridge Language</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="4b93d-553">One Epping Road</span><span class="sxs-lookup"><span data-stu-id="4b93d-553">One Epping Road</span></span></td>
<td align="left"><span data-ttu-id="4b93d-554">Adquirir nuevo, dedicado</span><span class="sxs-lookup"><span data-stu-id="4b93d-554">Acquire new, dedicated</span></span></td>
<td align="left"><span data-ttu-id="4b93d-555">Por añadir</span><span class="sxs-lookup"><span data-stu-id="4b93d-555">TBA</span></span></td>
<td align="left"><span data-ttu-id="4b93d-556">Inglés (Australia)</span><span class="sxs-lookup"><span data-stu-id="4b93d-556">English (Australia)</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="4b93d-557">One Marina Boulevard</span><span class="sxs-lookup"><span data-stu-id="4b93d-557">One Marina Boulevard</span></span></td>
<td align="left"><span data-ttu-id="4b93d-558">Adquirir nuevo, compartido</span><span class="sxs-lookup"><span data-stu-id="4b93d-558">Acquire new, shared</span></span></td>
<td align="left"><span data-ttu-id="4b93d-559">Por añadir</span><span class="sxs-lookup"><span data-stu-id="4b93d-559">TBA</span></span></td>
<td align="left"><span data-ttu-id="4b93d-560">Inglés (Estados Unidos), chino (simplificado, RPC)</span><span class="sxs-lookup"><span data-stu-id="4b93d-560">English (United States), Chinese (Simplified, PRC)</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="4b93d-561">32 London Bridge Street</span><span class="sxs-lookup"><span data-stu-id="4b93d-561">32 London Bridge Street</span></span></td>
<td align="left"><span data-ttu-id="4b93d-562">Puerto existente, dedicado</span><span class="sxs-lookup"><span data-stu-id="4b93d-562">Port existing, dedicated</span></span></td>
<td align="left"><span data-ttu-id="4b93d-563">+44 20 7946 0001</span><span class="sxs-lookup"><span data-stu-id="4b93d-563">+44 20 7946 0001</span></span></td>
<td align="left"><span data-ttu-id="4b93d-564">Inglés (Reino Unido)</span><span class="sxs-lookup"><span data-stu-id="4b93d-564">English (United Kingdom)</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="4b93d-565">39 quai du Président Roosevelt</span><span class="sxs-lookup"><span data-stu-id="4b93d-565">39 quai du Président Roosevelt</span></span></td>
<td align="left"><span data-ttu-id="4b93d-566">Adquirir nuevo, dedicado</span><span class="sxs-lookup"><span data-stu-id="4b93d-566">Acquire new, dedicated</span></span></td>
<td align="left"><span data-ttu-id="4b93d-567">Por añadir</span><span class="sxs-lookup"><span data-stu-id="4b93d-567">TBA</span></span></td>
<td align="left"><span data-ttu-id="4b93d-568">Francés (Francia), inglés (Reino Unido)</span><span class="sxs-lookup"><span data-stu-id="4b93d-568">French (France), English (United Kingdom)</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="4b93d-569">_Tabla 10 Ejemplo de detalles de puentes de conferencia_</span><span class="sxs-lookup"><span data-stu-id="4b93d-569">_Table 10 Example of conference bridge details_</span></span>


> [!NOTE]
> <span data-ttu-id="4b93d-570">La tabla de ejemplos anterior y las tablas siguientes que se ofrecen en este documento se pueden usar como plantillas.</span><span class="sxs-lookup"><span data-stu-id="4b93d-570">The example table above and subsequent tables throughout this document serve as a template.</span></span> <span data-ttu-id="4b93d-571">La frase "Por añadir" indica que falta por completar con información como parte del proceso de planificación.</span><span class="sxs-lookup"><span data-stu-id="4b93d-571">You'll see "TBA" (to be added) for information that you need to complete as part of your planning process.</span></span>

## <a name="conference-bridge-settings"></a><span data-ttu-id="4b93d-572">Configuración de puentes de conferencia</span><span class="sxs-lookup"><span data-stu-id="4b93d-572">Conference bridge settings</span></span>

<span data-ttu-id="4b93d-573">Las opciones de configuración que se aplican a toda la organización en torno a la experiencia de unión a reuniones de Audioconferencia (notificación de entrada y salida de la reunión y grabación del nombre de la persona que llama), la longitud del PIN del organizador de la reunión, y la notificación de correo electrónico están disponibles para personalizar aún más la experiencia del usuario final.</span><span class="sxs-lookup"><span data-stu-id="4b93d-573">Organization-wide configuration options around Audio Conferencing meeting join experience (meeting entry and exit notification and caller name recording), meeting organizer’s PIN length, and email notification are available to further tailor the end-user experience.</span></span>

-   <span data-ttu-id="4b93d-574">Las notificaciones de entrada y salida de la reunión están disponibles en la forma de nombre grabado, número de teléfono y tonos.</span><span class="sxs-lookup"><span data-stu-id="4b93d-574">Meeting entry and exit notifications are available in the form of recorded name, phone number, and tones.</span></span>

-   <span data-ttu-id="4b93d-575">La longitud del PIN se puede configurar de 4 a 12 dígitos, siendo el PIN de 5 dígitos el predeterminado.</span><span class="sxs-lookup"><span data-stu-id="4b93d-575">PIN length is configurable from 4 to 12 digits, with a 5-digit PIN as the default.</span></span>

-   <span data-ttu-id="4b93d-576">Los correos electrónicos de notificación tras la habilitación de la licencia de Audioconferencia o cualquier otro cambio impulsado por el administrador se habilitan de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="4b93d-576">Notification emails upon enablement of Audio Conferencing license or any other admin-driven changes are enabled by default.</span></span> <span data-ttu-id="4b93d-577">Esta característica se puede deshabilitar, de manera que tomará el control de las comunicaciones de los usuarios finales de su organización.</span><span class="sxs-lookup"><span data-stu-id="4b93d-577">You can disable this feature and take control of your organization’s end-user communications.</span></span>

<span data-ttu-id="4b93d-578">Para los usuarios a los que se les asigne una licencia de Audioconferencia, los números gratuitos o de pago predeterminados (los cuales se muestra en las coordenadas de Audioconferencia) se pueden configurar para usar:</span><span class="sxs-lookup"><span data-stu-id="4b93d-578">For users who are assigned an Audio Conferencing license, the default toll/toll-free numbers, shown in the Audio Conferencing coordinates, are configurable to use:</span></span>

-   <span data-ttu-id="4b93d-579">el predeterminado a nivel de inquilino,</span><span class="sxs-lookup"><span data-stu-id="4b93d-579">the tenant-level default, or</span></span>

-   <span data-ttu-id="4b93d-580">los números de teléfono para puentes de conferencia que se asignan automáticamente o</span><span class="sxs-lookup"><span data-stu-id="4b93d-580">the automatically-assigned conference bridge phone numbers, or</span></span>

-   <span data-ttu-id="4b93d-581">los números de teléfono para puentes de conferencia que se definen manualmente para cada usuario.</span><span class="sxs-lookup"><span data-stu-id="4b93d-581">manually defined conference bridge phone numbers for each user.</span></span>

<span data-ttu-id="4b93d-582">Los números de teléfono para puentes de conferencia específicos para usuarios son útiles en organizaciones globales y nacionales en las que los usuarios están repartidos en distintas ubicaciones y deben proporcionar números locales como números de teléfono para puentes de conferencia en las invitaciones a reuniones.</span><span class="sxs-lookup"><span data-stu-id="4b93d-582">User-specific conference bridge phone numbers are typically useful in global or nationwide organizations where users are distributed and must provide local numbers as the default conference bridge phone numbers in the meeting invites.</span></span>

<span data-ttu-id="4b93d-583">Los participantes que se unan desde distintas ciudades o desde otros países pueden buscar otros números configurados a nivel de inquilino, pero estos números no aparecen directamente en las invitaciones para las reuniones.</span><span class="sxs-lookup"><span data-stu-id="4b93d-583">Participants joining from different cities or overseas can look up additional numbers configured at the tenant-level, but these numbers do not appear directly in the meeting invites.</span></span> <span data-ttu-id="4b93d-584">Las invitaciones para reuniones incluyen un vínculo con el que los participantes se dirigirán a la página de números de acceso telefónico a conferencias de Microsoft Teams donde pueden buscar los números de teléfono para puentes de conferencia más próximos que estén disponibles para su ubicación.</span><span class="sxs-lookup"><span data-stu-id="4b93d-584">The meeting invites provide a link that will take participants to the Teams Conference Dial-in Numbers page for them to lookup the closest conference bridge phone numbers available from their location.</span></span>

<span data-ttu-id="4b93d-585">También puede configurar cómo gestiona cada organizador de una reunión los autores de llamada que no se han autenticado. Puede elegir que el organizador de la reunión tenga que iniciar la reunión antes de que se admitan los autores de llamada sin autenticar o bien permitir que los autores de llamada que no se han autenticado inicien una reunión.</span><span class="sxs-lookup"><span data-stu-id="4b93d-585">You can also configure how unauthenticated callers are handled by each individual meeting organizer, whether to require meeting organizer to start the meeting before unauthenticated callers are admitted, or to allow unauthenticated callers to start a meeting.</span></span>

<span data-ttu-id="4b93d-586">Hay otras configuraciones que se pueden aplicar para cada usuario y poder controlar el uso de los números de teléfono gratuitos para puentes de conferencia y realizar llamadas desde una conferencia.</span><span class="sxs-lookup"><span data-stu-id="4b93d-586">Additional configurations that can be applied for each user are available to control the use of toll-free conference bridge phone numbers and dial-out from a conference.</span></span>

> [!NOTE]
> <span data-ttu-id="4b93d-587">Estos controles relacionados con los costes solo están disponibles en este momento para clientes de la versión preliminar.</span><span class="sxs-lookup"><span data-stu-id="4b93d-587">These cost-related controls are currently available for preview customers only.</span></span> <span data-ttu-id="4b93d-588">Puede inscribir a su organización en el programa de versión preliminar en [https://www.skypepreview.com](https://go.microsoft.com/fwlink/?linkid=859013).</span><span class="sxs-lookup"><span data-stu-id="4b93d-588">You can enroll your organization in the preview program from [https://www.skypepreview.com](https://go.microsoft.com/fwlink/?linkid=859013).</span></span>

<span data-ttu-id="4b93d-589">Con estos controles, puede decidir si los organizadores de las reuniones pueden proporcionar números de teléfono gratuitos para puentes de conferencia en las reuniones que organicen ellos y controlar si los participantes pueden llamar desde las reuniones que organicen ellos.</span><span class="sxs-lookup"><span data-stu-id="4b93d-589">With these controls, you can decide whether meeting organizers can provide toll-free conference bridge phone numbers for meetings organized by them, and to control whether participants can dial out from the meetings organized by them.</span></span> <span data-ttu-id="4b93d-590">El nivel de control de la aceptación de llamada abarca desde deshabilitar la aceptación de llamada, permitir solo llamar a números nacionales o permitir llamar a números nacionales e internacionales.</span><span class="sxs-lookup"><span data-stu-id="4b93d-590">The level of dial-out control spans from disallowing dial out, only allowing dial out to domestic numbers, to allowing dial out to both domestic and international numbers.</span></span>

<table>
<thead>
<tr class="header">
<td align="left"><img src="media/audio_conferencing_image7.png" /></td>
<td align="left"><span data-ttu-id="4b93d-591">Puntos de decisión</span><span class="sxs-lookup"><span data-stu-id="4b93d-591">Decision Points</span></span></td>
<td align="left"><ul><li><span data-ttu-id="4b93d-592">Decida si la organización necesita notificaciones de entrada y salida y, en caso afirmativo, el tipo de notificación que se implementará (tonos, número de teléfono o nombre grabado).</span><span class="sxs-lookup"><span data-stu-id="4b93d-592">Decide whether the organization requires entry and exit notifications, and if yes, the type of notification to be implemented (tones, phone number, or recorded name).</span></span></li>
<li><span data-ttu-id="4b93d-593">Decida la longitud del PIN de Audioconferencia que cumpla los requisitos de seguridad de la organización.</span><span class="sxs-lookup"><span data-stu-id="4b93d-593">Decide the Audio Conferencing PIN length that meets the organizational security requirements.</span></span></li>
<li><span data-ttu-id="4b93d-594">Decida si la organización quiere controlar las comunicaciones de los usuarios finales que estén relacionadas con el servicio de Audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="4b93d-594">Decide if the organization wants to take control of end-user communications related to Audio Conferencing service.</span></span></li>
<li><span data-ttu-id="4b93d-595">Decida qué números de teléfono para puentes de conferencia se asignarán a cada organizador de reuniones.</span><span class="sxs-lookup"><span data-stu-id="4b93d-595">Decide the conference bridge phone numbers to be assigned to each meeting organizer.</span></span></li>
<li><span data-ttu-id="4b93d-596">Decida si algunos organizadores de reuniones necesitan la opción de usar números de teléfono gratuitos para puentes de conferencia para sus reuniones.</span><span class="sxs-lookup"><span data-stu-id="4b93d-596">Decide whether some meeting organizers require the ability to use toll-free conference bridge phone numbers for their meeings</span></span></li>
<li><span data-ttu-id="4b93d-597">Decida si algunos organizadores de reuniones necesitan la opción de permitir que autores de llamada sin autenticar puedan iniciar una reunión.</span><span class="sxs-lookup"><span data-stu-id="4b93d-597">Decide whether some meeting organizers require the ability to allow unauthenticated callers to start a meeting.</span></span></li>
<li><span data-ttu-id="4b93d-598">Decida si algunos organizadores de reuniones necesitan que se controlen las llamadas desde la conferencia.</span><span class="sxs-lookup"><span data-stu-id="4b93d-598">Decide whether some meeting organizers require conference dial out to be controlled.</span></span></li></ul></td>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="media/audio_conferencing_image9.png" /></td>
<td align="left"><span data-ttu-id="4b93d-599">Siguientes pasos</span><span class="sxs-lookup"><span data-stu-id="4b93d-599">Next Steps</span></span></td>
<td align="left"><ul><li><span data-ttu-id="4b93d-600">Documente la configuración de puentes de conferencia con todos los detalles (notificaciones de entrada y salida, longitud de PIN, notificación por correo electrónico de cambios en la configuración).</span><span class="sxs-lookup"><span data-stu-id="4b93d-600">Document the detailed conference bridge settings (entry and exit notifications, PIN length, configuration change email notification).</span></span></li>
<li><span data-ttu-id="4b93d-601">Documente qué números de teléfono para puentes de conferencia se asignan a cada organizador de reunión y la configuración correspondiente para controlar la directiva de autores de llamada sin autenticar y los controles de llamadas desde la reunión y gratuitas.</span><span class="sxs-lookup"><span data-stu-id="4b93d-601">Document the conference bridge phone numbers to be assinged to each meeting organizer and the corresponding setting to control unauthenticated caller’s policy, and toll-free and dial out controls.</span></span></li></ul></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<td align="left"><span data-ttu-id="4b93d-602"><strong>Habilitar las notificaciones de entrada y salidas de las reuniones</strong></span><span class="sxs-lookup"><span data-stu-id="4b93d-602"><strong>Enable meeting entry and exit notifications</strong></span></span></td>
<td align="left"><span data-ttu-id="4b93d-603">Habilitado</span><span class="sxs-lookup"><span data-stu-id="4b93d-603">Enabled</span></span></td>
</tr>
</thead>
<thead>
<tr class="header">
<td align="left"><span data-ttu-id="4b93d-604"><strong>Tipo de anuncio de entrada/salida</strong></span><span class="sxs-lookup"><span data-stu-id="4b93d-604"><strong>Entry/exit announcement type</strong></span></span></td>
<td align="left"><span data-ttu-id="4b93d-605">Tonos</span><span class="sxs-lookup"><span data-stu-id="4b93d-605">Tones</span></span></td>
</tr>
<tr class="header">
<td align="left"><span data-ttu-id="4b93d-606"><strong>Pedir a los autores de llamada que graben su nombre antes de unirse a la reunión</strong></span><span class="sxs-lookup"><span data-stu-id="4b93d-606"><strong>Ask callers to record their name before joining the meeting</strong></span></span></td>
<td align="left"><span data-ttu-id="4b93d-607">Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="4b93d-607">Disabled</span></span></td>
</tr>
<tr class="header">
<td align="left"><span data-ttu-id="4b93d-608"><strong>Longitud de PIN</strong></span><span class="sxs-lookup"><span data-stu-id="4b93d-608"><strong>PIN length</strong></span></span></td>
<td align="left"><span data-ttu-id="4b93d-609">5</span><span class="sxs-lookup"><span data-stu-id="4b93d-609">5</span></span></td>
</tr>
<tr class="header">
<td align="left"><span data-ttu-id="4b93d-610"><strong>Enviar correos automáticamente a los usuarios si cambia su configuración de acceso telefónico</strong></span><span class="sxs-lookup"><span data-stu-id="4b93d-610"><strong>Automatically send emails to users if their dial-in settings change</strong></span></span></td>
<td align="left"><span data-ttu-id="4b93d-611">Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="4b93d-611">Disabled</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="4b93d-612">_Tabla 11 Ejemplo de configuración de puentes de conferencia_</span><span class="sxs-lookup"><span data-stu-id="4b93d-612">_Table 11 Example of conference bridge settings_</span></span>


<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4b93d-613">Usuario</span><span class="sxs-lookup"><span data-stu-id="4b93d-613">User</span></span></th>
<th align="left"><span data-ttu-id="4b93d-614">Oficina</span><span class="sxs-lookup"><span data-stu-id="4b93d-614">Office</span></span></th>
<th align="left"><span data-ttu-id="4b93d-615">Número de pago predeterminado</span><span class="sxs-lookup"><span data-stu-id="4b93d-615">Default toll number</span></span></th>
<th align="left"><span data-ttu-id="4b93d-616">Número gratuito predeterminado</span><span class="sxs-lookup"><span data-stu-id="4b93d-616">Default toll-free number</span></span></th>
<th align="left"><span data-ttu-id="4b93d-617">Permitir número gratuito</span><span class="sxs-lookup"><span data-stu-id="4b93d-617">Allow toll-free</span></span></th>
<th align="left"><span data-ttu-id="4b93d-618">Los autores de llamadas sin autenticar no pasan por la sala de espera</span><span class="sxs-lookup"><span data-stu-id="4b93d-618">Unauthenticated callers bypass lobby</span></span></th>
<th align="left"><span data-ttu-id="4b93d-619">Llamadas desde la conferencia</span><span class="sxs-lookup"><span data-stu-id="4b93d-619">Conference dial out</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="4b93d-620">Adele Vance</span><span class="sxs-lookup"><span data-stu-id="4b93d-620">Adele Vance</span></span></td>
<td align="left"><span data-ttu-id="4b93d-621">One Epping Road</span><span class="sxs-lookup"><span data-stu-id="4b93d-621">One Epping Road</span></span></td>
<td align="left"><span data-ttu-id="4b93d-622">Por añadir</span><span class="sxs-lookup"><span data-stu-id="4b93d-622">TBA</span></span></td>
<td align="left"><span data-ttu-id="4b93d-623">Por añadir</span><span class="sxs-lookup"><span data-stu-id="4b93d-623">TBA</span></span></td>
<td align="left"><span data-ttu-id="4b93d-624">Sí</span><span class="sxs-lookup"><span data-stu-id="4b93d-624">Yes</span></span></td>
<td align="left"><span data-ttu-id="4b93d-625">Habilitado</span><span class="sxs-lookup"><span data-stu-id="4b93d-625">Enabled</span></span></td>
<td align="left"><span data-ttu-id="4b93d-626">Internacionales y nacionales</span><span class="sxs-lookup"><span data-stu-id="4b93d-626">International and domestic</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="4b93d-627">Alex Wilber</span><span class="sxs-lookup"><span data-stu-id="4b93d-627">Alex Wilber</span></span></td>
<td align="left"><span data-ttu-id="4b93d-628">One Epping Road</span><span class="sxs-lookup"><span data-stu-id="4b93d-628">One Epping Road</span></span></td>
<td align="left"><span data-ttu-id="4b93d-629">Por añadir</span><span class="sxs-lookup"><span data-stu-id="4b93d-629">TBA</span></span></td>
<td align="left"><span data-ttu-id="4b93d-630">Por añadir</span><span class="sxs-lookup"><span data-stu-id="4b93d-630">TBA</span></span></td>
<td align="left"><span data-ttu-id="4b93d-631">No</span><span class="sxs-lookup"><span data-stu-id="4b93d-631">No</span></span></td>
<td align="left"><span data-ttu-id="4b93d-632">Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="4b93d-632">Disabled</span></span></td>
<td align="left"><span data-ttu-id="4b93d-633">No se permiten</span><span class="sxs-lookup"><span data-stu-id="4b93d-633">Not allowed</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="4b93d-634">Ben Walters</span><span class="sxs-lookup"><span data-stu-id="4b93d-634">Ben Walters</span></span></td>
<td align="left"><span data-ttu-id="4b93d-635">One Epping Road</span><span class="sxs-lookup"><span data-stu-id="4b93d-635">One Epping Road</span></span></td>
<td align="left"><span data-ttu-id="4b93d-636">Por añadir</span><span class="sxs-lookup"><span data-stu-id="4b93d-636">TBA</span></span></td>
<td align="left"><span data-ttu-id="4b93d-637">Por añadir</span><span class="sxs-lookup"><span data-stu-id="4b93d-637">TBA</span></span></td>
<td align="left"><span data-ttu-id="4b93d-638">No</span><span class="sxs-lookup"><span data-stu-id="4b93d-638">No</span></span></td>
<td align="left"><span data-ttu-id="4b93d-639">Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="4b93d-639">Disabled</span></span></td>
<td align="left"><span data-ttu-id="4b93d-640">No se permiten</span><span class="sxs-lookup"><span data-stu-id="4b93d-640">Not allowed</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="4b93d-641">Christie Cline</span><span class="sxs-lookup"><span data-stu-id="4b93d-641">Christie Cline</span></span></td>
<td align="left"><span data-ttu-id="4b93d-642">One Marina Boulevard</span><span class="sxs-lookup"><span data-stu-id="4b93d-642">One Marina Boulevard</span></span></td>
<td align="left"><span data-ttu-id="4b93d-643">Por añadir</span><span class="sxs-lookup"><span data-stu-id="4b93d-643">TBA</span></span></td>
<td align="left"><span data-ttu-id="4b93d-644">Por añadir</span><span class="sxs-lookup"><span data-stu-id="4b93d-644">TBA</span></span></td>
<td align="left"><span data-ttu-id="4b93d-645">Sí</span><span class="sxs-lookup"><span data-stu-id="4b93d-645">Yes</span></span></td>
<td align="left"><span data-ttu-id="4b93d-646">Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="4b93d-646">Disabled</span></span></td>
<td align="left"><span data-ttu-id="4b93d-647">Nacionales</span><span class="sxs-lookup"><span data-stu-id="4b93d-647">Domestic</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="4b93d-648">Debra Berger</span><span class="sxs-lookup"><span data-stu-id="4b93d-648">Debra Berger</span></span></td>
<td align="left"><span data-ttu-id="4b93d-649">One Marina Boulevard</span><span class="sxs-lookup"><span data-stu-id="4b93d-649">One Marina Boulevard</span></span></td>
<td align="left"><span data-ttu-id="4b93d-650">Por añadir</span><span class="sxs-lookup"><span data-stu-id="4b93d-650">TBA</span></span></td>
<td align="left"><span data-ttu-id="4b93d-651">Por añadir</span><span class="sxs-lookup"><span data-stu-id="4b93d-651">TBA</span></span></td>
<td align="left"><span data-ttu-id="4b93d-652">Sí</span><span class="sxs-lookup"><span data-stu-id="4b93d-652">Yes</span></span></td>
<td align="left"><span data-ttu-id="4b93d-653">Habilitado</span><span class="sxs-lookup"><span data-stu-id="4b93d-653">Enabled</span></span></td>
<td align="left"><span data-ttu-id="4b93d-654">Nacionales</span><span class="sxs-lookup"><span data-stu-id="4b93d-654">Domestic</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="4b93d-655">Lee Gu</span><span class="sxs-lookup"><span data-stu-id="4b93d-655">Lee Gu</span></span></td>
<td align="left"><span data-ttu-id="4b93d-656">One Marina Boulevard</span><span class="sxs-lookup"><span data-stu-id="4b93d-656">One Marina Boulevard</span></span></td>
<td align="left"><span data-ttu-id="4b93d-657">Por añadir</span><span class="sxs-lookup"><span data-stu-id="4b93d-657">TBA</span></span></td>
<td align="left"><span data-ttu-id="4b93d-658">Por añadir</span><span class="sxs-lookup"><span data-stu-id="4b93d-658">TBA</span></span></td>
<td align="left"><span data-ttu-id="4b93d-659">Sí</span><span class="sxs-lookup"><span data-stu-id="4b93d-659">Yes</span></span></td>
<td align="left"><span data-ttu-id="4b93d-660">Habilitado</span><span class="sxs-lookup"><span data-stu-id="4b93d-660">Enabled</span></span></td>
<td align="left"><span data-ttu-id="4b93d-661">Nacionales</span><span class="sxs-lookup"><span data-stu-id="4b93d-661">Domestic</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="4b93d-662">Emily Braun</span><span class="sxs-lookup"><span data-stu-id="4b93d-662">Emily Braun</span></span></td>
<td align="left"><span data-ttu-id="4b93d-663">32 London Bridge Street</span><span class="sxs-lookup"><span data-stu-id="4b93d-663">32 London Bridge Street</span></span></td>
<td align="left"><span data-ttu-id="4b93d-664">+44 20 7946 0001</span><span class="sxs-lookup"><span data-stu-id="4b93d-664">+44 20 7946 0001</span></span></td>
<td align="left"><span data-ttu-id="4b93d-665">Por añadir</span><span class="sxs-lookup"><span data-stu-id="4b93d-665">TBA</span></span></td>
<td align="left"><span data-ttu-id="4b93d-666">Sí</span><span class="sxs-lookup"><span data-stu-id="4b93d-666">Yes</span></span></td>
<td align="left"><span data-ttu-id="4b93d-667">Habilitado</span><span class="sxs-lookup"><span data-stu-id="4b93d-667">Enabled</span></span></td>
<td align="left"><span data-ttu-id="4b93d-668">No se permiten</span><span class="sxs-lookup"><span data-stu-id="4b93d-668">Not allowed</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="4b93d-669">Lidia Holloway</span><span class="sxs-lookup"><span data-stu-id="4b93d-669">Lidia Holloway</span></span></td>
<td align="left"><span data-ttu-id="4b93d-670">32 London Bridge Street</span><span class="sxs-lookup"><span data-stu-id="4b93d-670">32 London Bridge Street</span></span></td>
<td align="left"><span data-ttu-id="4b93d-671">+44 20 7946 0001</span><span class="sxs-lookup"><span data-stu-id="4b93d-671">+44 20 7946 0001</span></span></td>
<td align="left"><span data-ttu-id="4b93d-672">Por añadir</span><span class="sxs-lookup"><span data-stu-id="4b93d-672">TBA</span></span></td>
<td align="left"><span data-ttu-id="4b93d-673">Sí</span><span class="sxs-lookup"><span data-stu-id="4b93d-673">Yes</span></span></td>
<td align="left"><span data-ttu-id="4b93d-674">Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="4b93d-674">Disabled</span></span></td>
<td align="left"><span data-ttu-id="4b93d-675">No se permiten</span><span class="sxs-lookup"><span data-stu-id="4b93d-675">Not allowed</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="4b93d-676">Pradeep Gupta</span><span class="sxs-lookup"><span data-stu-id="4b93d-676">Pradeep Gupta</span></span></td>
<td align="left"><span data-ttu-id="4b93d-677">32 London Bridge Street</span><span class="sxs-lookup"><span data-stu-id="4b93d-677">32 London Bridge Street</span></span></td>
<td align="left"><span data-ttu-id="4b93d-678">+44 20 7946 0001</span><span class="sxs-lookup"><span data-stu-id="4b93d-678">+44 20 7946 0001</span></span></td>
<td align="left"><span data-ttu-id="4b93d-679">Por añadir</span><span class="sxs-lookup"><span data-stu-id="4b93d-679">TBA</span></span></td>
<td align="left"><span data-ttu-id="4b93d-680">Sí</span><span class="sxs-lookup"><span data-stu-id="4b93d-680">Yes</span></span></td>
<td align="left"><span data-ttu-id="4b93d-681">Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="4b93d-681">Disabled</span></span></td>
<td align="left"><span data-ttu-id="4b93d-682">No se permiten</span><span class="sxs-lookup"><span data-stu-id="4b93d-682">Not allowed</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="4b93d-683">Marcel Beauchamp</span><span class="sxs-lookup"><span data-stu-id="4b93d-683">Marcel Beauchamp</span></span></td>
<td align="left"><span data-ttu-id="4b93d-684">39 quai du Président Roosevelt</span><span class="sxs-lookup"><span data-stu-id="4b93d-684">39 quai du Président Roosevelt</span></span></td>
<td align="left"><span data-ttu-id="4b93d-685">Por añadir</span><span class="sxs-lookup"><span data-stu-id="4b93d-685">TBA</span></span></td>
<td align="left"><span data-ttu-id="4b93d-686">Por añadir</span><span class="sxs-lookup"><span data-stu-id="4b93d-686">TBA</span></span></td>
<td align="left"><span data-ttu-id="4b93d-687">No</span><span class="sxs-lookup"><span data-stu-id="4b93d-687">No</span></span></td>
<td align="left"><span data-ttu-id="4b93d-688">Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="4b93d-688">Disabled</span></span></td>
<td align="left"><span data-ttu-id="4b93d-689">Nacionales</span><span class="sxs-lookup"><span data-stu-id="4b93d-689">Domestic</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="4b93d-690">Rachelle Cormier</span><span class="sxs-lookup"><span data-stu-id="4b93d-690">Rachelle Cormier</span></span></td>
<td align="left"><span data-ttu-id="4b93d-691">39 quai du Président Roosevelt</span><span class="sxs-lookup"><span data-stu-id="4b93d-691">39 quai du Président Roosevelt</span></span></td>
<td align="left"><span data-ttu-id="4b93d-692">Por añadir</span><span class="sxs-lookup"><span data-stu-id="4b93d-692">TBA</span></span></td>
<td align="left"><span data-ttu-id="4b93d-693">Por añadir</span><span class="sxs-lookup"><span data-stu-id="4b93d-693">TBA</span></span></td>
<td align="left"><span data-ttu-id="4b93d-694">Sí</span><span class="sxs-lookup"><span data-stu-id="4b93d-694">Yes</span></span></td>
<td align="left"><span data-ttu-id="4b93d-695">Habilitado</span><span class="sxs-lookup"><span data-stu-id="4b93d-695">Enabled</span></span></td>
<td align="left"><span data-ttu-id="4b93d-696">Internacionales y nacionales</span><span class="sxs-lookup"><span data-stu-id="4b93d-696">International and domestic</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="4b93d-697">Isabell Potvin</span><span class="sxs-lookup"><span data-stu-id="4b93d-697">Isabell Potvin</span></span></td>
<td align="left"><span data-ttu-id="4b93d-698">39 quai du Président Roosevelt</span><span class="sxs-lookup"><span data-stu-id="4b93d-698">39 quai du Président Roosevelt</span></span></td>
<td align="left"><span data-ttu-id="4b93d-699">Por añadir</span><span class="sxs-lookup"><span data-stu-id="4b93d-699">TBA</span></span></td>
<td align="left"><span data-ttu-id="4b93d-700">Por añadir</span><span class="sxs-lookup"><span data-stu-id="4b93d-700">TBA</span></span></td>
<td align="left"><span data-ttu-id="4b93d-701">No</span><span class="sxs-lookup"><span data-stu-id="4b93d-701">No</span></span></td>
<td align="left"><span data-ttu-id="4b93d-702">Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="4b93d-702">Disabled</span></span></td>
<td align="left"><span data-ttu-id="4b93d-703">Nacionales</span><span class="sxs-lookup"><span data-stu-id="4b93d-703">Domestic</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="4b93d-704">_Tabla 12 Ejemplo de asignaciones en la configuración de puentes de conferencia_</span><span class="sxs-lookup"><span data-stu-id="4b93d-704">_Table 12 Example of conference bridge settings assignments_</span></span>


## <a name="dial-plans"></a><span data-ttu-id="4b93d-705">Planes de marcado</span><span class="sxs-lookup"><span data-stu-id="4b93d-705">Dial plans</span></span>

<span data-ttu-id="4b93d-706">Un [plan de marcado](https://support.office.com/article/What-are-PSTN-Calling-dial-plans-2f0cfb59-1ca1-4e31-84ce-09d0b1a7ce1b), una característica de Sistema telefónico de Office 365, es un conjunto de reglas de normalización con las que los números de teléfono que se marcan se traducen en un formato alternativo (normalmente, el formato [E.164](https://go.microsoft.com/fwlink/?linkid=859014)) para poder autorizar la llamada y enrutarla.</span><span class="sxs-lookup"><span data-stu-id="4b93d-706">A [Dial Plan](https://support.office.com/article/What-are-PSTN-Calling-dial-plans-2f0cfb59-1ca1-4e31-84ce-09d0b1a7ce1b), a Phone System feature of Office 365, is a set of normalization rules that translates dialed phone numbers into an alternate format (typically [E.164](https://go.microsoft.com/fwlink/?linkid=859014) format) for call authorization and call routing.</span></span> <span data-ttu-id="4b93d-707">El servicio de Audioconferencia utiliza las mismas funcionalidades de Sistema telefónico para traducir los números de teléfono marcados en escenarios de llamadas desde la conferencia.</span><span class="sxs-lookup"><span data-stu-id="4b93d-707">Audio Conferencing service leverages the same capabilities used by Phone System to translate dialed phone numbers in conference dial out scenarios.</span></span>

<span data-ttu-id="4b93d-708">Con un plan de marcado, los usuarios pueden marcar números de teléfono como suelen hacerlo, como, por ejemplo, omitiendo el código de área para las llamadas locales, omitiendo el código de país para las llamadas domésticas o incluso usando una marcación de dígitos breve cuando se realizan llamadas desde la conferencia.</span><span class="sxs-lookup"><span data-stu-id="4b93d-708">A dial plan allows users to dial phone numbers the way they are accustomed to, such as omitting area code for local calls, omitting country code for domestic calls, or even using short digit dialing when performing conference dial out.</span></span>

<span data-ttu-id="4b93d-709">Dentro de la característica de Sistema telefónico de Office 365, existen dos tipos de planes de marcado:</span><span class="sxs-lookup"><span data-stu-id="4b93d-709">Within the Phone System feature of Office 365, there are two types of dial plans:</span></span>

-   <span data-ttu-id="4b93d-710">**Plan de marcado de servicio**.</span><span class="sxs-lookup"><span data-stu-id="4b93d-710">**Service dial plan**.</span></span> <span data-ttu-id="4b93d-711">Es el plan de marcado predeterminado y se aplica a los usuarios en función de la ubicación de uso de Office 365. No se puede modificar.</span><span class="sxs-lookup"><span data-stu-id="4b93d-711">This is the default dial plan and applied to users based on Office 365 usage location, and it cannot be modified.</span></span>

<!-- -->

-   <span data-ttu-id="4b93d-712">**Plan de marcado de inquilino**.</span><span class="sxs-lookup"><span data-stu-id="4b93d-712">**Tenant dial plan**.</span></span> <span data-ttu-id="4b93d-713">Este plan de marcado se puede personalizar dentro de un inquilino y se puede volver a dividir en dos tipos:</span><span class="sxs-lookup"><span data-stu-id="4b93d-713">This is a customizable dial plan within a tenant, and further divided into two types:</span></span>

    -   <span data-ttu-id="4b93d-714">**Plan de marcado de inquilino global:** el plan de marcado se aplica a todos los usuarios dentro del inquilino.</span><span class="sxs-lookup"><span data-stu-id="4b93d-714">**Tenant-global dial plan**—the dial plan applies to all users within the tenant.</span></span>

    -   <span data-ttu-id="4b93d-715">**Plan de marcado de usuario de inquilino:** el plan se aplica únicamente a determinados usuarios.</span><span class="sxs-lookup"><span data-stu-id="4b93d-715">**Tenant-user dial plan**—the dial plan applies only to specific users.</span></span>


> [!NOTE]
> <span data-ttu-id="4b93d-716">Revise la documentación sobre [planes de marcado del plan de llamadas de Office 365](https://support.office.com/article/What-are-PSTN-Calling-dial-plans-2f0cfb59-1ca1-4e31-84ce-09d0b1a7ce1b) si desea ver más detalles y ejemplos.</span><span class="sxs-lookup"><span data-stu-id="4b93d-716">Check out the [Office 365 Calling Plan dial plans](https://support.office.com/article/What-are-PSTN-Calling-dial-plans-2f0cfb59-1ca1-4e31-84ce-09d0b1a7ce1b) documentation for further details and examples.</span></span>

<span data-ttu-id="4b93d-717">El plan de marcado efectivo que se asigna a los usuarios es la combinación del plan de marcado de servicio (basado en la ubicación de uso de Office 365 del usuario) y el plan de marcado de inquilino (ya sea el de inquilino global o el de usuario de inquilino).</span><span class="sxs-lookup"><span data-stu-id="4b93d-717">The effective dial plan assigned to users is the combination of service dial plan (based on user’s Office 365 usage location) and tenant dial plan (can be either tenant-global dial plan or tenant-user dial plan).</span></span>

![La tabla muestra tres combinaciones de planes de marcado de inquilino y servicio.](media/audio_conferencing_image8.png)

<span data-ttu-id="4b93d-719">Hay un máximo de 25 reglas de normalización en cada plan de marcado de inquilino y, por lo tanto, hay que evitar duplicar las reglas de normalización que ya están disponibles como parte del plan de marcado de servicio.</span><span class="sxs-lookup"><span data-stu-id="4b93d-719">There is a maximum of 25 normalization rules in each tenant dial plan, and thus duplication with normalization rules already available as part of service dial plan needs to be avoided.</span></span>

<table>
<thead>
<tr class="header">
<td align="left"><img src="media/audio_conferencing_image7.png" /></td>
<td align="left"><span data-ttu-id="4b93d-720">Puntos de decisión</span><span class="sxs-lookup"><span data-stu-id="4b93d-720">Decision Points</span></span></td>
<td align="left"><ul><li><span data-ttu-id="4b93d-721">Decida si su organización necesita planes de marcado personalizados (requisitos empresariales, requisitos de adopción, etc.).</span><span class="sxs-lookup"><span data-stu-id="4b93d-721">Decide if your organization requires customized dial plans (business requirements, adoption requirements, etc.).</span></span></li>
<li><span data-ttu-id="4b93d-722">En caso de necesitarlos, decida qué ámbito del plan de marcado de inquilino (inquilino global o usuario de inquilino) se ajusta a los requisitos de los planes de marcado personalizados.</span><span class="sxs-lookup"><span data-stu-id="4b93d-722">If applicable, decide the scope of tenant dial plan (tenant-global or tenant-user) to support the requirements for customized dial plans.</span></span></li>
<li><span data-ttu-id="4b93d-723">En caso necesario, decida los planes de macado de inquilino que se van a crear como soporte a las oficinas o ubicaciones de los usuarios en las que se va a implementar Audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="4b93d-723">If applicable, decide the tenant dial plans that will be created to support user locations or offices in-scope for the Audio Conferencing implementation.</span></span></li>
<li><span data-ttu-id="4b93d-724">En caso necesario, decida qué usuario necesita un plan de marcado personalizado y qué plan de marcado de inquilino se va a asignar a cada usuario.</span><span class="sxs-lookup"><span data-stu-id="4b93d-724">If applicable, decide which user require customized dial plan and the tenant dial plan to be assigned for each user.</span></span></li></ul></td>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="media/audio_conferencing_image9.png" /></td>
<td align="left"><span data-ttu-id="4b93d-725">Siguientes pasos</span><span class="sxs-lookup"><span data-stu-id="4b93d-725">Next Steps</span></span></td>
<td align="left"><ul><li><span data-ttu-id="4b93d-726">Documente qué planes de marcado personalizados y reglas de normalización asociadas se van a configurar como parte de la implementación de Audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="4b93d-726">Document the customized dial plans and the associated normalization rules to be configured as part of Audio Conferencing implementation.</span></span></li>
<li><span data-ttu-id="4b93d-727">Documente a qué usuarios se les va a asignar un plan de marcado personalizado y qué plan de marcado de inquilino se va a asignar a cada usuario.</span><span class="sxs-lookup"><span data-stu-id="4b93d-727">Document the users to be assigned with customized dial plan and the tenant dial plan to be assigned for each user.</span></span></li></ul></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4b93d-728">Nombre/descripción del plan de marcado de inquilino</span><span class="sxs-lookup"><span data-stu-id="4b93d-728">Tenant Dial Plan Name/Description</span></span></th>
<th align="left"><span data-ttu-id="4b93d-729">Nombre/descripción de reglas de normalización</span><span class="sxs-lookup"><span data-stu-id="4b93d-729">Normalization Rules Name/Description</span></span></th>
<th align="left"><span data-ttu-id="4b93d-730">Patrón</span><span class="sxs-lookup"><span data-stu-id="4b93d-730">Pattern</span></span></th>
<th align="left"><span data-ttu-id="4b93d-731">Traducción</span><span class="sxs-lookup"><span data-stu-id="4b93d-731">Translation</span></span></th>
<th align="left"><span data-ttu-id="4b93d-732">IsInternalExtension</span><span class="sxs-lookup"><span data-stu-id="4b93d-732">IsInternalExtension</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4b93d-733"><strong>AU-NSW-NorthRyde-OER</strong></span><span class="sxs-lookup"><span data-stu-id="4b93d-733"><strong>AU-NSW-NorthRyde-OER</strong></span></span></p>
<p><span data-ttu-id="4b93d-734"><em>Plan de marcado de One Epping Road North Ryde, NSW, AU</em></span><span class="sxs-lookup"><span data-stu-id="4b93d-734"><em>One Epping Road North Ryde, NSW, AU Dial Plan</em></span></span></p></td>
<td align="left"><p><span data-ttu-id="4b93d-735"><strong>AU-NSW-NorthRyde-OER-Internal</strong></span><span class="sxs-lookup"><span data-stu-id="4b93d-735"><strong>AU-NSW-NorthRyde-OER-Internal</strong></span></span></p>
<p><span data-ttu-id="4b93d-736"><em>Número interno (x7000 - x7999) para oficina de One Epping Road, North Ryde, NSW, Australia</em></span><span class="sxs-lookup"><span data-stu-id="4b93d-736"><em>Internal number (x7000 - x7999) for One Epping Road office, North Ryde, NSW, Australia</em></span></span></p></td>
<td align="left"><span data-ttu-id="4b93d-737">^(7\d{3})$</span><span class="sxs-lookup"><span data-stu-id="4b93d-737">^(7\d{3})$</span></span></td>
<td align="left"><span data-ttu-id="4b93d-738">+6125550$1</span><span class="sxs-lookup"><span data-stu-id="4b93d-738">+6125550$1</span></span></td>
<td align="left"><span data-ttu-id="4b93d-739">True</span><span class="sxs-lookup"><span data-stu-id="4b93d-739">True</span></span></td>
</tr>
<tr class="even">
<td align="left"></td>
<td align="left"><p><span data-ttu-id="4b93d-740"><strong>AU-NSW-Local</strong></span><span class="sxs-lookup"><span data-stu-id="4b93d-740"><strong>AU-NSW-Local</strong></span></span></p>
<p><span data-ttu-id="4b93d-741"><em>Normalización de número local para NSW, Australia</em></span><span class="sxs-lookup"><span data-stu-id="4b93d-741"><em>Local number normalization for NSW, Australia</em></span></span></p></td>
<td align="left"><span data-ttu-id="4b93d-742">^([2-9]\d{7})$</span><span class="sxs-lookup"><span data-stu-id="4b93d-742">^([2-9]\d{7})$</span></span></td>
<td align="left"><span data-ttu-id="4b93d-743">+612$1</span><span class="sxs-lookup"><span data-stu-id="4b93d-743">+612$1</span></span></td>
<td align="left"><span data-ttu-id="4b93d-744">False</span><span class="sxs-lookup"><span data-stu-id="4b93d-744">False</span></span></td>
</tr>
<tr class="odd">
<td align="left"></td>
<td align="left"><p><span data-ttu-id="4b93d-745"><strong>AU-TollFree</strong></span><span class="sxs-lookup"><span data-stu-id="4b93d-745"><strong>AU-TollFree</strong></span></span></p>
<p><span data-ttu-id="4b93d-746"><em>Normalización de número gratuito para Australia</em></span><span class="sxs-lookup"><span data-stu-id="4b93d-746"><em>Toll Free number normalization for Australia</em></span></span></p></td>
<td align="left"><span data-ttu-id="4b93d-747">^(1[38]\d{4,8})\d*$</span><span class="sxs-lookup"><span data-stu-id="4b93d-747">^(1[38]\d{4,8})\d*$</span></span></td>
<td align="left"><span data-ttu-id="4b93d-748">+61$1</span><span class="sxs-lookup"><span data-stu-id="4b93d-748">+61$1</span></span></td>
<td align="left"><span data-ttu-id="4b93d-749">False</span><span class="sxs-lookup"><span data-stu-id="4b93d-749">False</span></span></td>
</tr>
<tr class="even">
<td align="left"></td>
<td align="left"><p><span data-ttu-id="4b93d-750"><strong>AU-Service</strong></span><span class="sxs-lookup"><span data-stu-id="4b93d-750"><strong>AU-Service</strong></span></span></p>
<p><span data-ttu-id="4b93d-751"><em>Normalización de número de servicio para Australia</em></span><span class="sxs-lookup"><span data-stu-id="4b93d-751"><em>Service number normalization for Australia</em></span></span></p></td>
<td align="left"><span data-ttu-id="4b93d-752">^(000|1[0125]\d{1,8})$</span><span class="sxs-lookup"><span data-stu-id="4b93d-752">^(000|1[0125]\d{1,8})$</span></span></td>
<td align="left"><span data-ttu-id="4b93d-753">1 $</span><span class="sxs-lookup"><span data-stu-id="4b93d-753">$1</span></span></td>
<td align="left"><span data-ttu-id="4b93d-754">False</span><span class="sxs-lookup"><span data-stu-id="4b93d-754">False</span></span></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4b93d-755"><strong>SG-Singapore-OMB</strong></span><span class="sxs-lookup"><span data-stu-id="4b93d-755"><strong>SG-Singapore-OMB</strong></span></span></p>
<p><span data-ttu-id="4b93d-756"><em>Plan de marcado de OMB Singapore, SG</em></span><span class="sxs-lookup"><span data-stu-id="4b93d-756"><em>OMB Singapore, SG Dial Plan</em></span></span></p></td>
<td align="left"><p><span data-ttu-id="4b93d-757"><strong>SG-OMB-Internal</strong></span><span class="sxs-lookup"><span data-stu-id="4b93d-757"><strong>SG-OMB-Internal</strong></span></span></p>
<p><span data-ttu-id="4b93d-758"><em>Número interno (x8000 – x8999) para la oficina de +OMB, Singapur</em></span><span class="sxs-lookup"><span data-stu-id="4b93d-758"><em>Internal number (x8000 – x8999) for OMB office, Singapore</em></span></span></p></td>
<td align="left"><span data-ttu-id="4b93d-759">^(8\d{3})$</span><span class="sxs-lookup"><span data-stu-id="4b93d-759">^(8\d{3})$</span></span></td>
<td align="left"><span data-ttu-id="4b93d-760">+656888$1</span><span class="sxs-lookup"><span data-stu-id="4b93d-760">+656888$1</span></span></td>
<td align="left"><span data-ttu-id="4b93d-761">True</span><span class="sxs-lookup"><span data-stu-id="4b93d-761">True</span></span></td>
</tr>
<tr class="even">
<td align="left"></td>
<td align="left"><p><span data-ttu-id="4b93d-762"><strong>SG-TollFree</strong></span><span class="sxs-lookup"><span data-stu-id="4b93d-762"><strong>SG-TollFree</strong></span></span></p>
<p><span data-ttu-id="4b93d-763"><em>Normalización de número gratuito para Singapur</em></span><span class="sxs-lookup"><span data-stu-id="4b93d-763"><em>Toll Free number normalization for Singapore</em></span></span></p></td>
<td align="left"><span data-ttu-id="4b93d-764">^(1?800\d{7})\d*$</span><span class="sxs-lookup"><span data-stu-id="4b93d-764">^(1?800\d{7})\d*$</span></span></td>
<td align="left"><span data-ttu-id="4b93d-765">+65$1</span><span class="sxs-lookup"><span data-stu-id="4b93d-765">+65$1</span></span></td>
<td align="left"><span data-ttu-id="4b93d-766">False</span><span class="sxs-lookup"><span data-stu-id="4b93d-766">False</span></span></td>
</tr>
<tr class="odd">
<td align="left"></td>
<td align="left"><p><span data-ttu-id="4b93d-767"><strong>SG-Service</strong></span><span class="sxs-lookup"><span data-stu-id="4b93d-767"><strong>SG-Service</strong></span></span></p>
<p><span data-ttu-id="4b93d-768"><em>Normalización de número de servicio para Singapur</em></span><span class="sxs-lookup"><span data-stu-id="4b93d-768"><em>Service number normalization for Singapore</em></span></span></p></td>
<td align="left"><span data-ttu-id="4b93d-769">^(1\d{3,4}|9\d{2})$</span><span class="sxs-lookup"><span data-stu-id="4b93d-769">^(1\d{3,4}|9\d{2})$</span></span></td>
<td align="left"><span data-ttu-id="4b93d-770">1 $</span><span class="sxs-lookup"><span data-stu-id="4b93d-770">$1</span></span></td>
<td align="left"><span data-ttu-id="4b93d-771">False</span><span class="sxs-lookup"><span data-stu-id="4b93d-771">False</span></span></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4b93d-772"><strong>FR-Paris-Issy-39qdPR</strong></span><span class="sxs-lookup"><span data-stu-id="4b93d-772"><strong>FR-Paris-Issy-39qdPR</strong></span></span></p>
<p><span data-ttu-id="4b93d-773"><em>Plan de marcado de 39 quai du Président Roosevelt Issy-les-Moulineaux, Francia</em></span><span class="sxs-lookup"><span data-stu-id="4b93d-773"><em>39 quai du Président Roosevelt Issy-les-Moulineaux, France Dial Plan</em></span></span></p></td>
<td align="left"><p><span data-ttu-id="4b93d-774"><strong>FR-39qdPR-Internal</strong></span><span class="sxs-lookup"><span data-stu-id="4b93d-774"><strong>FR-39qdPR-Internal</strong></span></span></p>
<p><span data-ttu-id="4b93d-775"><em>Número interno (x7000 – x7999) para 39 quai du Président Roosevelt office, Issy-les-Moulineaux, Francia</em></span><span class="sxs-lookup"><span data-stu-id="4b93d-775"><em>Internal number (x7000 – x7999) for 39 quai du Président Roosevelt office, Issy-les-Moulineaux, France</em></span></span></p></td>
<td align="left"><span data-ttu-id="4b93d-776">^(7\d{3})$</span><span class="sxs-lookup"><span data-stu-id="4b93d-776">^(7\d{3})$</span></span></td>
<td align="left"><span data-ttu-id="4b93d-777">+3319999$1</span><span class="sxs-lookup"><span data-stu-id="4b93d-777">+3319999$1</span></span></td>
<td align="left"><span data-ttu-id="4b93d-778">True</span><span class="sxs-lookup"><span data-stu-id="4b93d-778">True</span></span></td>
</tr>
<tr class="odd">
<td align="left"></td>
<td align="left"><p><span data-ttu-id="4b93d-779"><strong>FR-TollFree</strong></span><span class="sxs-lookup"><span data-stu-id="4b93d-779"><strong>FR-TollFree</strong></span></span></p>
<p><span data-ttu-id="4b93d-780"><em>Normalización de número gratuito para Francia</em></span><span class="sxs-lookup"><span data-stu-id="4b93d-780"><em>Toll Free number normalization for France</em></span></span></p></td>
<td align="left"><span data-ttu-id="4b93d-781">^0?(80\d{7})\d*$</span><span class="sxs-lookup"><span data-stu-id="4b93d-781">^0?(80\d{7})\d*$</span></span></td>
<td align="left"><span data-ttu-id="4b93d-782">+33$1</span><span class="sxs-lookup"><span data-stu-id="4b93d-782">+33$1</span></span></td>
<td align="left"><span data-ttu-id="4b93d-783">False</span><span class="sxs-lookup"><span data-stu-id="4b93d-783">False</span></span></td>
</tr>
<tr class="even">
<td align="left"></td>
<td align="left"><p><span data-ttu-id="4b93d-784"><strong>FR-Service</strong></span><span class="sxs-lookup"><span data-stu-id="4b93d-784"><strong>FR-Service</strong></span></span></p>
<p><span data-ttu-id="4b93d-785"><em>Normalización de número de servicio para Francia</em></span><span class="sxs-lookup"><span data-stu-id="4b93d-785"><em>Service number normalization for France</em></span></span></p></td>
<td align="left"><p><span data-ttu-id="4b93d-786">^(1\d{1,2}|11[68]\d{3}|</span><span class="sxs-lookup"><span data-stu-id="4b93d-786">^(1\d{1,2}|11[68]\d{3}|</span></span></p>
<p><span data-ttu-id="4b93d-787">10\d{2}|3\d{3})$</span><span class="sxs-lookup"><span data-stu-id="4b93d-787">10\d{2}|3\d{3})$</span></span></p></td>
<td align="left"><span data-ttu-id="4b93d-788">1 $</span><span class="sxs-lookup"><span data-stu-id="4b93d-788">$1</span></span></td>
<td align="left"><span data-ttu-id="4b93d-789">False</span><span class="sxs-lookup"><span data-stu-id="4b93d-789">False</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="4b93d-790">_Tabla 13 Ejemplo de planes de marcado de inquilino_</span><span class="sxs-lookup"><span data-stu-id="4b93d-790">_Table 13 Example of tenant dial plans_</span></span>


<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4b93d-791">Usuario</span><span class="sxs-lookup"><span data-stu-id="4b93d-791">User</span></span></th>
<th align="left"><span data-ttu-id="4b93d-792">Oficina</span><span class="sxs-lookup"><span data-stu-id="4b93d-792">Office</span></span></th>
<th align="left"><span data-ttu-id="4b93d-793">Tipo de plan de marcado</span><span class="sxs-lookup"><span data-stu-id="4b93d-793">Dial Plan Type</span></span></th>
<th align="left"><span data-ttu-id="4b93d-794">Nombre de plan de marcado</span><span class="sxs-lookup"><span data-stu-id="4b93d-794">Dial Plan Name</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="4b93d-795">Adele Vance</span><span class="sxs-lookup"><span data-stu-id="4b93d-795">Adele Vance</span></span></td>
<td align="left"><span data-ttu-id="4b93d-796">One Epping Road</span><span class="sxs-lookup"><span data-stu-id="4b93d-796">One Epping Road</span></span></td>
<td align="left"><span data-ttu-id="4b93d-797">Plan de marcado de inquilino</span><span class="sxs-lookup"><span data-stu-id="4b93d-797">Tenant dial plan</span></span></td>
<td align="left"><span data-ttu-id="4b93d-798">AU-NSW-NorthRyde-OER</span><span class="sxs-lookup"><span data-stu-id="4b93d-798">AU-NSW-NorthRyde-OER</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="4b93d-799">Alex Wilber</span><span class="sxs-lookup"><span data-stu-id="4b93d-799">Alex Wilber</span></span></td>
<td align="left"><span data-ttu-id="4b93d-800">One Epping Road</span><span class="sxs-lookup"><span data-stu-id="4b93d-800">One Epping Road</span></span></td>
<td align="left"><span data-ttu-id="4b93d-801">Plan de marcado de inquilino</span><span class="sxs-lookup"><span data-stu-id="4b93d-801">Tenant dial plan</span></span></td>
<td align="left"><span data-ttu-id="4b93d-802">AU-NSW-NorthRyde-OER</span><span class="sxs-lookup"><span data-stu-id="4b93d-802">AU-NSW-NorthRyde-OER</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="4b93d-803">Ben Walters</span><span class="sxs-lookup"><span data-stu-id="4b93d-803">Ben Walters</span></span></td>
<td align="left"><span data-ttu-id="4b93d-804">One Epping Road</span><span class="sxs-lookup"><span data-stu-id="4b93d-804">One Epping Road</span></span></td>
<td align="left"><span data-ttu-id="4b93d-805">Plan de marcado de inquilino</span><span class="sxs-lookup"><span data-stu-id="4b93d-805">Tenant dial plan</span></span></td>
<td align="left"><span data-ttu-id="4b93d-806">AU-NSW-NorthRyde-OER</span><span class="sxs-lookup"><span data-stu-id="4b93d-806">AU-NSW-NorthRyde-OER</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="4b93d-807">Christie Cline</span><span class="sxs-lookup"><span data-stu-id="4b93d-807">Christie Cline</span></span></td>
<td align="left"><span data-ttu-id="4b93d-808">One Marina Boulevard</span><span class="sxs-lookup"><span data-stu-id="4b93d-808">One Marina Boulevard</span></span></td>
<td align="left"><span data-ttu-id="4b93d-809">Plan de marcado de inquilino</span><span class="sxs-lookup"><span data-stu-id="4b93d-809">Tenant dial plan</span></span></td>
<td align="left"><span data-ttu-id="4b93d-810">SG-Singapore-OMB</span><span class="sxs-lookup"><span data-stu-id="4b93d-810">SG-Singapore-OMB</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="4b93d-811">Debra Berger</span><span class="sxs-lookup"><span data-stu-id="4b93d-811">Debra Berger</span></span></td>
<td align="left"><span data-ttu-id="4b93d-812">One Marina Boulevard</span><span class="sxs-lookup"><span data-stu-id="4b93d-812">One Marina Boulevard</span></span></td>
<td align="left"><span data-ttu-id="4b93d-813">Plan de marcado de inquilino</span><span class="sxs-lookup"><span data-stu-id="4b93d-813">Tenant dial plan</span></span></td>
<td align="left"><span data-ttu-id="4b93d-814">SG-Singapore-OMB</span><span class="sxs-lookup"><span data-stu-id="4b93d-814">SG-Singapore-OMB</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="4b93d-815">Lee Gu</span><span class="sxs-lookup"><span data-stu-id="4b93d-815">Lee Gu</span></span></td>
<td align="left"><span data-ttu-id="4b93d-816">One Marina Boulevard</span><span class="sxs-lookup"><span data-stu-id="4b93d-816">One Marina Boulevard</span></span></td>
<td align="left"><span data-ttu-id="4b93d-817">Plan de marcado de inquilino</span><span class="sxs-lookup"><span data-stu-id="4b93d-817">Tenant dial plan</span></span></td>
<td align="left"><span data-ttu-id="4b93d-818">SG-Singapore-OMB</span><span class="sxs-lookup"><span data-stu-id="4b93d-818">SG-Singapore-OMB</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="4b93d-819">Emily Braun</span><span class="sxs-lookup"><span data-stu-id="4b93d-819">Emily Braun</span></span></td>
<td align="left"><span data-ttu-id="4b93d-820">32 London Bridge Street</span><span class="sxs-lookup"><span data-stu-id="4b93d-820">32 London Bridge Street</span></span></td>
<td align="left"><span data-ttu-id="4b93d-821">Plan de marcado de servicio</span><span class="sxs-lookup"><span data-stu-id="4b93d-821">Service dial plan</span></span></td>
<td align="left"><span data-ttu-id="4b93d-822">N/D</span><span class="sxs-lookup"><span data-stu-id="4b93d-822">N/A</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="4b93d-823">Lidia Holloway</span><span class="sxs-lookup"><span data-stu-id="4b93d-823">Lidia Holloway</span></span></td>
<td align="left"><span data-ttu-id="4b93d-824">32 London Bridge Street</span><span class="sxs-lookup"><span data-stu-id="4b93d-824">32 London Bridge Street</span></span></td>
<td align="left"><span data-ttu-id="4b93d-825">Plan de marcado de servicio</span><span class="sxs-lookup"><span data-stu-id="4b93d-825">Service dial plan</span></span></td>
<td align="left"><span data-ttu-id="4b93d-826">N/D</span><span class="sxs-lookup"><span data-stu-id="4b93d-826">N/A</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="4b93d-827">Pradeep Gupta</span><span class="sxs-lookup"><span data-stu-id="4b93d-827">Pradeep Gupta</span></span></td>
<td align="left"><span data-ttu-id="4b93d-828">32 London Bridge Street</span><span class="sxs-lookup"><span data-stu-id="4b93d-828">32 London Bridge Street</span></span></td>
<td align="left"><span data-ttu-id="4b93d-829">Plan de marcado de servicio</span><span class="sxs-lookup"><span data-stu-id="4b93d-829">Service dial plan</span></span></td>
<td align="left"><span data-ttu-id="4b93d-830">N/D</span><span class="sxs-lookup"><span data-stu-id="4b93d-830">N/A</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="4b93d-831">Marcel Beauchamp</span><span class="sxs-lookup"><span data-stu-id="4b93d-831">Marcel Beauchamp</span></span></td>
<td align="left"><span data-ttu-id="4b93d-832">39 quai du Président Roosevelt</span><span class="sxs-lookup"><span data-stu-id="4b93d-832">39 quai du Président Roosevelt</span></span></td>
<td align="left"><span data-ttu-id="4b93d-833">Plan de marcado de inquilino</span><span class="sxs-lookup"><span data-stu-id="4b93d-833">Tenant dial plan</span></span></td>
<td align="left"><span data-ttu-id="4b93d-834">FR-Paris-Issy-39qdPR</span><span class="sxs-lookup"><span data-stu-id="4b93d-834">FR-Paris-Issy-39qdPR</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="4b93d-835">Rachelle Cormier</span><span class="sxs-lookup"><span data-stu-id="4b93d-835">Rachelle Cormier</span></span></td>
<td align="left"><span data-ttu-id="4b93d-836">39 quai du Président Roosevelt</span><span class="sxs-lookup"><span data-stu-id="4b93d-836">39 quai du Président Roosevelt</span></span></td>
<td align="left"><span data-ttu-id="4b93d-837">Plan de marcado de inquilino</span><span class="sxs-lookup"><span data-stu-id="4b93d-837">Tenant dial plan</span></span></td>
<td align="left"><span data-ttu-id="4b93d-838">FR-Paris-Issy-39qdPR</span><span class="sxs-lookup"><span data-stu-id="4b93d-838">FR-Paris-Issy-39qdPR</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="4b93d-839">Isabell Potvin</span><span class="sxs-lookup"><span data-stu-id="4b93d-839">Isabell Potvin</span></span></td>
<td align="left"><span data-ttu-id="4b93d-840">39 quai du Président Roosevelt</span><span class="sxs-lookup"><span data-stu-id="4b93d-840">39 quai du Président Roosevelt</span></span></td>
<td align="left"><span data-ttu-id="4b93d-841">Plan de marcado de inquilino</span><span class="sxs-lookup"><span data-stu-id="4b93d-841">Tenant dial plan</span></span></td>
<td align="left"><span data-ttu-id="4b93d-842">FR-Paris-Issy-39qdPR</span><span class="sxs-lookup"><span data-stu-id="4b93d-842">FR-Paris-Issy-39qdPR</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="4b93d-843">_Tabla 14 Ejemplo de asignaciones de plan de marcado_</span><span class="sxs-lookup"><span data-stu-id="4b93d-843">_Table 14 Example of dial plan assignments_</span></span>


## <a name="microsoft-teams-configurations"></a><span data-ttu-id="4b93d-844">Configuraciones de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4b93d-844">Microsoft Teams configurations</span></span>

<span data-ttu-id="4b93d-845">Como Audioconferencia solo está disponible para reuniones programadas, hay que habilitar las configuraciones a nivel de inquilino que rigen la programación de las reuniones (reuniones privadas y de canal).</span><span class="sxs-lookup"><span data-stu-id="4b93d-845">Since Audio Conferencing is only available for scheduled meetings, tenant-level configurations that govern meeting scheduling (private and channel meetings) must be enabled.</span></span>


> [!NOTE]
> <span data-ttu-id="4b93d-846">Por el momento, si su organización tiene ciertas normativas por las que se tienen que poder detectar todas las discusiones de las reuniones, debe deshabilitar las reuniones privadas si el organizador tiene un buzón de correo local de Exchange.</span><span class="sxs-lookup"><span data-stu-id="4b93d-846">Currently, if your organization has compliance requirements to ensure all meeting discussions are discoverable, you should disable private meetings if the organizer has an Exchange on-premises mailbox.</span></span><br><br>
> <span data-ttu-id="4b93d-847">En otros casos, si todas las reuniones de la organización solo pueden estar visibles <strong>para las partes invitadas</strong> y así evitar que se revele la información de reuniones a partes que no están invitadas, le recomendamos que deshabilite la capacidad de programar reuniones en <strong>canales</strong>.</span><span class="sxs-lookup"><span data-stu-id="4b93d-847">In another use case, if all meetings in the organization must be visible <strong>to invited parties</strong> only, to avoid disclosing meeting information to uninvited parties, we recommend that you disable the ability to schedule meetings in <strong>channels</strong>.</span></span>

<span data-ttu-id="4b93d-848">Las configuraciones, disponibles como configuraciones a nivel de inquilino, se aplican a todos los usuarios de la organización y repercutirán en la programación de todas las reuniones de Microsoft Teams, no solo en las reuniones de Microsoft Teams **con** Audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="4b93d-848">The settings, available as tenant-level configurations, are applicable to all users in the organization, and will impact all meeting scheduling in Teams, not specific to Teams meetings **with** Audio Conferencing.</span></span>

<table>
<thead>
<tr class="header">
<td align="left"><img src="media/audio_conferencing_image7.png" /></td>
<td align="left"><span data-ttu-id="4b93d-849">Punto de decisión</span><span class="sxs-lookup"><span data-stu-id="4b93d-849">Decision Point</span></span></td>
<td align="left"><p><span data-ttu-id="4b93d-850">Decida si la organización tiene que habilitar o deshabilitar la programación de reuniones privadas.</span><span class="sxs-lookup"><span data-stu-id="4b93d-850">Decide if the organization requires to enable or disable scheduling of private meetings.</span></span></p>
<p><span data-ttu-id="4b93d-851">Decida si la organización tiene que habilitar o deshabilitar la programación de reuniones de canal.</span><span class="sxs-lookup"><span data-stu-id="4b93d-851">Decide if the organization requires to enable or disable scheduling of channel meetings.</span></span></p></td>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="media/audio_conferencing_image9.png" /></td>
<td align="left"><span data-ttu-id="4b93d-852">Siguientes pasos</span><span class="sxs-lookup"><span data-stu-id="4b93d-852">Next Steps</span></span></td>
<td align="left"><p><span data-ttu-id="4b93d-853">Documente las configuraciones para la programación de reuniones de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="4b93d-853">Document the meeting scheduling configurations for Teams.</span></span></p></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<td align="left"><span data-ttu-id="4b93d-854"><strong>Permitir la programación de reuniones privadas</strong></span><span class="sxs-lookup"><span data-stu-id="4b93d-854"><strong>Allow scheduling for private meetings</strong></span></span></td>
<td align="left"><span data-ttu-id="4b93d-855">Habilitado</span><span class="sxs-lookup"><span data-stu-id="4b93d-855">Enabled</span></span></td>
</tr>
</thead>
<thead>
<tr class="odd">
<td align="left"><span data-ttu-id="4b93d-856"><strong>Permitir la programación de reuniones de canal</strong></span><span class="sxs-lookup"><span data-stu-id="4b93d-856"><strong>Allow scheduling for channel meetings</strong></span></span></td>
<td align="left"><span data-ttu-id="4b93d-857">Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="4b93d-857">Disabled</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="4b93d-858">_Tabla 15 Ejemplo de configuraciones de reuniones de Microsoft Teams_</span><span class="sxs-lookup"><span data-stu-id="4b93d-858">_Table 15 Example of Microsoft Teams meetings configurations_</span></span>


## <a name="document-technical-implementation-plan"></a><span data-ttu-id="4b93d-859">Documentar el plan técnico de implementación</span><span class="sxs-lookup"><span data-stu-id="4b93d-859">Document technical implementation plan</span></span>

<span data-ttu-id="4b93d-860">Utilice los puntos de decisión anteriores como referencia para documentar el plan de implementación técnico.</span><span class="sxs-lookup"><span data-stu-id="4b93d-860">Use the decision points above to document your technical implementation plan.</span></span>

<span data-ttu-id="4b93d-861">Este plan de implementación técnico proporcionará al equipo del proyecto (que puede incluir FastTrack o el asociado de implementación) la información que le permita ejecutar la incorporación de técnicos para la implementación de Audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="4b93d-861">This technical implementation plan will provide the project team, which can include FastTrack or a deployment partner, with the information required to execute the technical onboarding for the implementation of Audio Conferencing.</span></span>

<span data-ttu-id="4b93d-862">En general, un plan de implementación técnico contendrá las siguientes secciones principales:</span><span class="sxs-lookup"><span data-stu-id="4b93d-862">In general, a technical implementation plan will contain the following main sections:</span></span>

-   <span data-ttu-id="4b93d-863">Lista de habilitación del sitio de servicio de Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="4b93d-863">Audio Conferencing service site enablement list</span></span>

-   <span data-ttu-id="4b93d-864">Lista de asignación de licencias para los organizadores de reuniones de Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="4b93d-864">License assignment list for Audio Conferencing meeting organizers</span></span>

-   <span data-ttu-id="4b93d-865">Números de planificación de Créditos de comunicaciones</span><span class="sxs-lookup"><span data-stu-id="4b93d-865">Communications Credits planning numbers</span></span>

-   <span data-ttu-id="4b93d-866">Detalles de puentes de conferencia</span><span class="sxs-lookup"><span data-stu-id="4b93d-866">Conference bridge details</span></span>

-   <span data-ttu-id="4b93d-867">Configuración de puentes de conferencia</span><span class="sxs-lookup"><span data-stu-id="4b93d-867">Conference bridge settings</span></span>

-   <span data-ttu-id="4b93d-868">Asignaciones de configuraciones de puentes de conferencia</span><span class="sxs-lookup"><span data-stu-id="4b93d-868">Conference bridge settings assignments</span></span>

-   <span data-ttu-id="4b93d-869">Planes de marcado de inquilino</span><span class="sxs-lookup"><span data-stu-id="4b93d-869">Tenant dial plans</span></span>

-   <span data-ttu-id="4b93d-870">Asignaciones de planes de marcado</span><span class="sxs-lookup"><span data-stu-id="4b93d-870">Dial plan assignments</span></span>

-   <span data-ttu-id="4b93d-871">Configuraciones de reuniones de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4b93d-871">Microsoft Teams meetings configurations</span></span>

<span data-ttu-id="4b93d-872">Una vez que complete el plan de éxito y el plan de implementación técnico, podrá seguir con el recorrido de cliente de Office 365.</span><span class="sxs-lookup"><span data-stu-id="4b93d-872">With the completion of success plan and technical implementation plan, you are now ready to take your organization to the next steps along the Office 365 customer journey.</span></span>

<a name="onboard"></a><span data-ttu-id="4b93d-873">Incorporación</span><span class="sxs-lookup"><span data-stu-id="4b93d-873">Onboard</span></span>
=======

<span data-ttu-id="4b93d-874">*Próximamente*</span><span class="sxs-lookup"><span data-stu-id="4b93d-874">*Coming soon.*</span></span>

<a name="drive-value"></a><span data-ttu-id="4b93d-875">Nuevos valores</span><span class="sxs-lookup"><span data-stu-id="4b93d-875">Drive Value</span></span>
===========

<span data-ttu-id="4b93d-876">*Próximamente*</span><span class="sxs-lookup"><span data-stu-id="4b93d-876">*Coming soon.*</span></span>



### <a name="see-also"></a><span data-ttu-id="4b93d-877">Vea también</span><span class="sxs-lookup"><span data-stu-id="4b93d-877">See also</span></span>
[<span data-ttu-id="4b93d-878">Configurar conferencias de acceso telefónico local o RTC para Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="4b93d-878">Set up dial-in or PSTN conferencing for Skype for Business</span></span>](https://support.office.com/article/Set-up-audio-conferencing-for-Skype-for-Business-and-Microsoft-Teams-d01954f1-4f37-4cf5-a636-20039e5c59e9)
