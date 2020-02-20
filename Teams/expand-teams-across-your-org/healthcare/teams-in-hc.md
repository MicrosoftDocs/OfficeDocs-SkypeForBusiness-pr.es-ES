---
title: Introducción a Teams para organizaciones sanitarias
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Introducción a Teams para organizaciones sanitarias
ms.openlocfilehash: 15e10a69174787d104a990f8b71a6e8ef4f8be04
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147693"
---
# <a name="get-started-with-teams-for-healthcare-organizations"></a><span data-ttu-id="bcb94-103">Introducción a Teams para organizaciones sanitarias</span><span class="sxs-lookup"><span data-stu-id="bcb94-103">Get started with Teams for Healthcare organizations</span></span>

<span data-ttu-id="bcb94-104">Microsoft Teams ofrece una serie de características útiles para hospitales y otras organizaciones de salud.</span><span class="sxs-lookup"><span data-stu-id="bcb94-104">Microsoft Teams offers a number of features useful for hospitals and other Healthcare organizations.</span></span> <span data-ttu-id="bcb94-105">Las características de Teams están en desarrollo para ayudar a los hospitales a:</span><span class="sxs-lookup"><span data-stu-id="bcb94-105">Teams features are under development to aid hospitals with:</span></span>

- <span data-ttu-id="bcb94-106">Coordinación y colaboración de cuidados</span><span class="sxs-lookup"><span data-stu-id="bcb94-106">Care Coordination and collaboration</span></span>
- <span data-ttu-id="bcb94-107">Mensajería segura</span><span class="sxs-lookup"><span data-stu-id="bcb94-107">Secure Messaging</span></span>
- <span data-ttu-id="bcb94-108">TeleHealth</span><span class="sxs-lookup"><span data-stu-id="bcb94-108">Telehealth</span></span>
- <span data-ttu-id="bcb94-109">Integración de registro de asistencia electrónica (EHR)</span><span class="sxs-lookup"><span data-stu-id="bcb94-109">Electronic Healthcare Record (EHR) integration</span></span> 
- <span data-ttu-id="bcb94-110">Integración del sistema de los Firstline Worker</span><span class="sxs-lookup"><span data-stu-id="bcb94-110">Firstline Worker system integration</span></span> 

<span data-ttu-id="bcb94-111">El contenido de esta sección se basa en las funciones fundamentales de los equipos, como las reuniones, las llamadas y la mensajería, y supone que ya ha implementado los equipos de su organización.</span><span class="sxs-lookup"><span data-stu-id="bcb94-111">The content in this section builds on the foundational capabilities of Teams, such as meetings, calling, and messaging, and assumes that you've already deployed Teams in your organization.</span></span> <span data-ttu-id="bcb94-112">Si aún no ha implementado Teams, empiece por leer [cómo implementar Microsoft Teams](../../How-to-roll-out-teams.md).</span><span class="sxs-lookup"><span data-stu-id="bcb94-112">If you haven't yet rolled out Teams, start by reading [How to roll out Microsoft Teams](../../How-to-roll-out-teams.md).</span></span>

## <a name="care-coordination---microsoft-teams-patients-app"></a><span data-ttu-id="bcb94-113">Coordinación de cuidados-aplicación de pacientes de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bcb94-113">Care Coordination - Microsoft Teams Patients app</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="bcb94-114">Microsoft Teams ahora tiene una solución de coordinación de cuidados específica para las organizaciones de salud que les ayudan a proporcionar el mejor cuidado del paciente.</span><span class="sxs-lookup"><span data-stu-id="bcb94-114">Microsoft Teams now has a care coordination solution specific to healthcare organizations to help them provide the best patient care.</span></span> <span data-ttu-id="bcb94-115">La Crux de la solución de coordinación de cuidados, la aplicación de pacientes de Microsoft Teams, es una primera aplicación de pestañas que se integra con sistemas de registro de estado electrónico (EHR) mediante una interfaz de recursos de interoperabilidad de Fast Healthcare ([FHIR](https://www.hl7.org/fhir/)) para proporcionar valiosa información médica a Microsoft Teams, en contexto para permitir la colaboración y la comunicación clínicas.</span><span class="sxs-lookup"><span data-stu-id="bcb94-115">The crux of the care coordination solution, the  Microsoft Teams Patients app, is a first party tab app that integrates with electronic health record (EHR) systems using a Fast Healthcare Interoperability Resources ([FHIR](https://www.hl7.org/fhir/)) interface to bring valuable medical information into Microsoft Teams in context to enable clinical collaboration and communication.</span></span>  

<span data-ttu-id="bcb94-116">La solución de coordinación de cuidados puede ser una interfaz con proveedores de software independientes (ISV) líderes que pueden conectar la aplicación de pacientes a sus sistemas HCI usando estándares de datos de estado existentes como HL7v2 y FHIR.</span><span class="sxs-lookup"><span data-stu-id="bcb94-116">The care coordination solution can interface with leading Independent Software Vendors (ISVs) that can connect the Patients app to your EHR systems using existing health data standards like HL7v2 and FHIR.</span></span> <span data-ttu-id="bcb94-117">Microsoft se asocia con los siguientes líderes del sector para establecer la integración de registros electrónicos de salud con equipos:</span><span class="sxs-lookup"><span data-stu-id="bcb94-117">Microsoft partners with the following industry leaders to establish electronic health record integration with Teams:</span></span>

- <span data-ttu-id="bcb94-118">Datica (a través de la oferta de [CMI](https://datica.com/compliant-managed-integration/) )</span><span class="sxs-lookup"><span data-stu-id="bcb94-118">Datica (through their [CMI](https://datica.com/compliant-managed-integration/) offering)</span></span>
- <span data-ttu-id="bcb94-119">Infor cloverleaf (a través del [puente de FHIR de Infor](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html))</span><span class="sxs-lookup"><span data-stu-id="bcb94-119">Infor Cloverleaf (through the [Infor FHIR Bridge](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html))</span></span>
- <span data-ttu-id="bcb94-120">Redox (a través del [servidor R ^ FHIR](https://www.redoxengine.com/fhir/))</span><span class="sxs-lookup"><span data-stu-id="bcb94-120">Redox (through the [R^FHIR server](https://www.redoxengine.com/fhir/))</span></span>
- <span data-ttu-id="bcb94-121">Dapasoft (a través [de Corolar en FHIR](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/))</span><span class="sxs-lookup"><span data-stu-id="bcb94-121">Dapasoft (through [Corolar on FHIR](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/))</span></span>

<span data-ttu-id="bcb94-122">Un socio de integración y interoperabilidad de EHR que intente implementar Microsoft Teams para una organización de proveedor de cuidados de la salud debe proporcionar a la aplicación de pacientes una conexión segura y autenticada con los sistemas HCI de la organización de proveedores de cuidados de la salud.</span><span class="sxs-lookup"><span data-stu-id="bcb94-122">An EHR integration and interop partner trying to implement Microsoft Teams for a healthcare provider organization needs to provide the Patients app a secure and authenticated connection with the healthcare provider organization's EHR systems.</span></span> <span data-ttu-id="bcb94-123">Esto permite el flujo unidireccional (solo lectura) de los registros del paciente relevante en la aplicación de pacientes.</span><span class="sxs-lookup"><span data-stu-id="bcb94-123">This enables the one-directional (Read only) flow of the relevant patient records into to the Patients app.</span></span> <span data-ttu-id="bcb94-124">La aplicación de pacientes comprende el formato FHIR, por lo que el socio también es responsable de transformar los datos agregados de varios otros formatos como HL7v2, etc. en FHIR DSTU2 o STU3.</span><span class="sxs-lookup"><span data-stu-id="bcb94-124">The Patients app understands the FHIR format, so the partner is also responsible for transforming the aggregated data from various other formats like HL7v2, etc. into FHIR DSTU2 or STU3.</span></span>

<br>

![Resaltado de la ilustración coordinación y colaboración de la salud](../../media/ehr-1.png)

<br>

<span data-ttu-id="bcb94-126">La aplicación de pacientes se integra con sistemas de registro de estado electrónico (EHR) y permite a los proveedores de atención médica comunicarse con la atención del paciente en tiempo real en la plataforma segura de los equipos.</span><span class="sxs-lookup"><span data-stu-id="bcb94-126">The Patients app integrates with electronic health records (EHR) systems and enables care providers to communicate about patient care in real-time within Teams’ secure platform.</span></span> <span data-ttu-id="bcb94-127">La aplicación de pacientes es la primera inversión importante en el área de coordinación de cuidados que tiene el objetivo de afrontar los siguientes desafíos:</span><span class="sxs-lookup"><span data-stu-id="bcb94-127">The Patients app is the first major investment in the care coordination area which aims to address the following challenges:</span></span>

- <span data-ttu-id="bcb94-128">Bajo nivel de eficacia a mano y comunicaciones críticas a través de la experiencia del paciente</span><span class="sxs-lookup"><span data-stu-id="bcb94-128">Low efficiency in hand-offs and critical communication through the patient experience</span></span>
- <span data-ttu-id="bcb94-129">Información en silos que crea cargas administrativas</span><span class="sxs-lookup"><span data-stu-id="bcb94-129">Siloed information that creates administrative burdens</span></span>
- <span data-ttu-id="bcb94-130">Insatisfacción entre los médicos con herramientas de colaboración complejas y fragmentadas</span><span class="sxs-lookup"><span data-stu-id="bcb94-130">Dissatisfaction among clinicians with complex and fragmented collaboration tools</span></span>
- <span data-ttu-id="bcb94-131">Coordinación de cuidados ineficaces que pueden suplantar demasiados minutos clínicos</span><span class="sxs-lookup"><span data-stu-id="bcb94-131">Inefficient in-person care coordination that can burn too much expensive clinical time</span></span>

<span data-ttu-id="bcb94-132">Microsoft Teams permite que los médicos, los médicos, los enfermeras y otras personas colaboren de manera eficaz por:</span><span class="sxs-lookup"><span data-stu-id="bcb94-132">Microsoft Teams enables physicians, clinicians, nurses, and other staff to collaborate efficiently by:</span></span>

- <span data-ttu-id="bcb94-133">Formar parte de un único equipo virtualizado que funciona y colabora en documentos de Office</span><span class="sxs-lookup"><span data-stu-id="bcb94-133">Being part of a single virtualized team that works and collaborates on Office documents</span></span>
- <span data-ttu-id="bcb94-134">Hacer conversaciones persistentes sobre diferentes pacientes que necesitan atención</span><span class="sxs-lookup"><span data-stu-id="bcb94-134">Having persistent conversations about different patients needing attention</span></span>
- <span data-ttu-id="bcb94-135">Usar canales con pestañas para estructurar su trabajo, con ayuda adicional de las pestañas a las que pueden anclar fuentes de información</span><span class="sxs-lookup"><span data-stu-id="bcb94-135">Using channels with tabs as a way to structure their work, with additional help from tabs to which they can pin information sources</span></span>
- <span data-ttu-id="bcb94-136">Usar reuniones de canal con la potencia de los equipos características de audio, vídeo, pantalla compartida, grabación y transcripción para administrar reuniones diarias</span><span class="sxs-lookup"><span data-stu-id="bcb94-136">Using channel meetings with the power of Teams audio, video, screen sharing, recording, and transcription features to manage daily meetings</span></span>
- <span data-ttu-id="bcb94-137">Uso de la aplicación de pacientes para ajustar una lista de los pacientes de alto riesgo que deben supervisarse y extrae los detalles más recientes del sistema HCI.</span><span class="sxs-lookup"><span data-stu-id="bcb94-137">Using the Patients app to curate a list of high-risk patients that must be monitored, and pulls their latest details from the EHR system.</span></span> <span data-ttu-id="bcb94-138">La aplicación de pacientes en sí agrega las siguientes características a Microsoft Teams:</span><span class="sxs-lookup"><span data-stu-id="bcb94-138">The Patients app itself adds the following features to Microsoft Teams:</span></span>

    - <span data-ttu-id="bcb94-139">Posibilidad de crear varias listas de pacientes en un solo canal.</span><span class="sxs-lookup"><span data-stu-id="bcb94-139">Ability to create multiple patient lists within a single channel.</span></span>
    - <span data-ttu-id="bcb94-140">Posibilidad de ver y ordenar la información que se muestra acerca de pacientes a través de columnas configurables.</span><span class="sxs-lookup"><span data-stu-id="bcb94-140">Ability to view and sort information displayed about patients through configurable columns.</span></span>
    - <span data-ttu-id="bcb94-141">Capacidad de aprovisionar automáticamente la aplicación a través de una plantilla de equipo.</span><span class="sxs-lookup"><span data-stu-id="bcb94-141">Ability to auto-provision the app through a team template.</span></span>
    - <span data-ttu-id="bcb94-142">Disponible en la aplicación de Teams para iOS y Android para los primeros trabajadores sanitarios móviles, así como en Microsoft Teams web y el cliente de escritorio.</span><span class="sxs-lookup"><span data-stu-id="bcb94-142">Available on the Teams App for iOS and Android for mobile first healthcare workers as well as Microsoft Teams web and desktop client.</span></span>
    - <span data-ttu-id="bcb94-143">Compatibilidad con las versiones de FHIR DSTU2 y STU3 mediante el análisis de una instrucción de conformidad.</span><span class="sxs-lookup"><span data-stu-id="bcb94-143">Support for FHIR DSTU2 and STU3 versions via parsing of conformance statement.</span></span>
    - <span data-ttu-id="bcb94-144">Registros de auditoría para todas las acciones de visualización y búsqueda de su interfaz de usuario para salvaguardar la PHI según las pautas de la HIPAA.</span><span class="sxs-lookup"><span data-stu-id="bcb94-144">Audit Logs for all view and search actions on its user interface to safeguard PHI per HIPAA guidelines.</span></span>

<span data-ttu-id="bcb94-145">La aplicación de pacientes se ha creado en la plataforma de extensibilidad de equipos y se aprovecha del marco de pestañas para mostrar contenido enriquecido de pacientes dentro de un canal.</span><span class="sxs-lookup"><span data-stu-id="bcb94-145">The Patients app is built on the Teams extensibility platform and takes advantage of the Tabs framework to display rich patient content within a channel.</span></span> <span data-ttu-id="bcb94-146">Para obtener más información sobre otras aplicaciones de Teams y la propia plataforma, consulte [aplicaciones para Microsoft Teams](/microsoftteams/platform/concepts/apps/apps-overview).</span><span class="sxs-lookup"><span data-stu-id="bcb94-146">To learn more about other Teams apps and the platform itself, please see [Apps for Microsoft Teams](/microsoftteams/platform/concepts/apps/apps-overview).</span></span>  

> [!NOTE]
> <span data-ttu-id="bcb94-147">La aplicación de pacientes está en versión preliminar privada y la interfaz de FHIR está en versión beta.</span><span class="sxs-lookup"><span data-stu-id="bcb94-147">The Patients app is in private preview and the FHIR interface is in beta.</span></span> <span data-ttu-id="bcb94-148">No se espera que las versiones publicadas sean compatibles con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="bcb94-148">Released versions are not expected to be backward compatible.</span></span>

![Captura de pantalla de la aplicación de pacientes en dispositivos móviles y de escritorio](../../media/ehr-2.png)

<span data-ttu-id="bcb94-150">Para obtener más información sobre la implementación, consulte [integrar registros de asistencia electrónica en Microsoft Teams](patients-app.md) .</span><span class="sxs-lookup"><span data-stu-id="bcb94-150">See [Integrating Electronic Healthcare Records into Microsoft Teams](patients-app.md) for implementation details,.</span></span>

## <a name="templates"></a><span data-ttu-id="bcb94-151">Plantillas</span><span class="sxs-lookup"><span data-stu-id="bcb94-151">Templates</span></span>

<span data-ttu-id="bcb94-152">Las nuevas plantillas para crear equipos fueron desarrolladas para aplicarse a una configuración hospitalaria y pronto se espera más.</span><span class="sxs-lookup"><span data-stu-id="bcb94-152">New templates for creating Teams were developed to apply to a Hospital setting, and more are expected soon.</span></span> <span data-ttu-id="bcb94-153">Esto facilita la creación de equipos que los trabajadores de cuidado de la salud usan para coordinar la atención de pacientes en varios departamentos o en adelante.</span><span class="sxs-lookup"><span data-stu-id="bcb94-153">This makes it easier to create Teams that Healthcare workers use to coordinate care for patients in various departments or wards.</span></span> <span data-ttu-id="bcb94-154">Consulte [Introducción a las plantillas de Teams para organizaciones de salud](healthcare-templates.md).</span><span class="sxs-lookup"><span data-stu-id="bcb94-154">See [Get started with Teams templates for Healthcare organizations](healthcare-templates.md).</span></span> <span data-ttu-id="bcb94-155">Los equipos se pueden iniciar para departamentos internos, como Cardiología, o por cuidados y más plantillas en desarrollo.</span><span class="sxs-lookup"><span data-stu-id="bcb94-155">Teams can be started for internal departments such as cardiology, or for care wards, and more templates are in development.</span></span>

## <a name="secure-messaging"></a><span data-ttu-id="bcb94-156">Mensajería segura</span><span class="sxs-lookup"><span data-stu-id="bcb94-156">Secure Messaging</span></span>

<span data-ttu-id="bcb94-157">Mensajería segura admite la colaboración en equipos de atención médica, incluidas varias características nuevas:</span><span class="sxs-lookup"><span data-stu-id="bcb94-157">Secure messaging supports collaboration within care teams, including several new features:</span></span>

- <span data-ttu-id="bcb94-158">El remitente de un mensaje puede establecer una prioridad especial para el mensaje, de modo que el destinatario reciba una notificación repetida hasta que lea el mensaje.</span><span class="sxs-lookup"><span data-stu-id="bcb94-158">A message sender can set a special priority for their message, so the recipient is repeatedly notified until they read the message.</span></span>
- <span data-ttu-id="bcb94-159">El remitente de un mensaje puede solicitar una confirmación de lectura, de modo que se le notifique cuando el destinatario del mensaje Lea un mensaje enviado.</span><span class="sxs-lookup"><span data-stu-id="bcb94-159">A message sender can request a read receipt, so they are notified when a message they sent was read by the message recipient.</span></span>


<span data-ttu-id="bcb94-160">En conjunto, estas características permiten una atención más rápida a los mensajes urgentes y confían en que el mensaje se ha recibido y leído.</span><span class="sxs-lookup"><span data-stu-id="bcb94-160">Together, these features allow quicker attention to urgent messages and confidence that the message was received and read.</span></span> <span data-ttu-id="bcb94-161">Los nuevos equipos de atención médica que usan estas características se pueden crear para cada paciente.</span><span class="sxs-lookup"><span data-stu-id="bcb94-161">New care teams using these features can be created on a per-patient basis.</span></span> <span data-ttu-id="bcb94-162">Estas características se basan en directivas y se pueden asignar a individuos o a equipos completos.</span><span class="sxs-lookup"><span data-stu-id="bcb94-162">These features are policy-based, and can be assigned to individuals or entire Teams.</span></span>

<span data-ttu-id="bcb94-163">Para obtener más información, consulte [Introducción a las directivas de mensajería segura para organizaciones de sanidad](messaging-policies-hc.md) .</span><span class="sxs-lookup"><span data-stu-id="bcb94-163">See [Get started with Secure Messaging policies for Healthcare organizations](messaging-policies-hc.md) for further details.</span></span>

<span data-ttu-id="bcb94-164">También relacionada con la mensajería segura es la capacidad de tener otros inquilinos federados por organizaciones de cuidado de la salud, lo que permite una comunicación entre inquilinos más rica.</span><span class="sxs-lookup"><span data-stu-id="bcb94-164">Also related to secure messaging is the ability to have other tenants federated by Healthcare organizations, allowing richer inter-tenant communication.</span></span> <span data-ttu-id="bcb94-165">(consulte [administrar el acceso externo (Federación) en Microsoft Teams](../../manage-external-access.md)).</span><span class="sxs-lookup"><span data-stu-id="bcb94-165">(see [Manage external access (federation) in Microsoft Teams](../../manage-external-access.md)).</span></span>

## <a name="firstline-worker-integration"></a><span data-ttu-id="bcb94-166">Integración de trabajadores de los Firstline</span><span class="sxs-lookup"><span data-stu-id="bcb94-166">Firstline Worker integration</span></span>

<span data-ttu-id="bcb94-167">Microsoft Teams se integra con los Firstline Worker, que se puede usar para coordinar las características de personal de turnos y mucho más.</span><span class="sxs-lookup"><span data-stu-id="bcb94-167">Microsoft Teams integrates with Firstline Worker, which can be used to coordinate shift staffing features and more.</span></span>

 <span data-ttu-id="bcb94-168">Consulte los artículos siguientes:</span><span class="sxs-lookup"><span data-stu-id="bcb94-168">See the following articles:</span></span>

- [<span data-ttu-id="bcb94-169">Mover los equipos de Microsoft StaffHub a turnos en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bcb94-169">Move your Microsoft StaffHub teams to Shifts in Microsoft Teams</span></span>](../shifts/move-staffhub-teams-to-shifts-in-teams.md)

- [<span data-ttu-id="bcb94-170">Administrar la aplicación Turnos para su organización en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bcb94-170">Manage the Shifts app for your organization in Microsoft Teams</span></span>](../shifts/manage-the-shifts-app-for-your-organization-in-teams.md)
