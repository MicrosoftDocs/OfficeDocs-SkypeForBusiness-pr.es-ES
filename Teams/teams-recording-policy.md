---
title: Introducción a Teams grabación basada en directivas para llamadas & reuniones
author: cabailey
ms.author: cabailey
manager: laurawi
ms.date: 05/11/2020
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: abybee
localization_priority: Normal
search.appverid: MET150
description: Obtenga más información Teams grabación basada en directivas para llamadas & reuniones
f1.keywords:
- CSH
ms.custom:
- Adopt
- seo-marvel-mar2020
ms.collection:
- Teams_ITAdmin_Adopt
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: df8a0f5b33bbea100b0303d224d7ba50946c6e5b
ms.sourcegitcommit: 56bebf42f545af57fdf387faa90e555abc8acd40
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/18/2021
ms.locfileid: "52513883"
---
# <a name="introduction-to-teams-policy-based-recording-for-callings--meetings"></a><span data-ttu-id="b1530-103">Introducción a la Teams basada en directivas para llamadas & reuniones</span><span class="sxs-lookup"><span data-stu-id="b1530-103">Introduction to Teams policy-based recording for callings & meetings</span></span>

<span data-ttu-id="b1530-104">La grabación basada en directivas permite que las organizaciones que adopten Microsoft Teams para llamadas y reuniones se estipulen mediante una directiva administrativa, cuando las llamadas y las reuniones en línea deben grabarse y capturarse automáticamente para su posterior procesamiento y retención, según lo requiera la directiva corporativa o normativa pertinente.</span><span class="sxs-lookup"><span data-stu-id="b1530-104">Policy-based recording enables organizations that adopt Microsoft Teams for calling and meetings to stipulate, using an administrative policy, when calls and online meetings should be automatically recorded and captured for subsequent processing and retention as required by relevant corporate or regulatory policy.</span></span>

<span data-ttu-id="b1530-105">Teams se ha mejorado para admitir la integración de soluciones de grabación de terceros, incluidas la funcionalidad de la plataforma, las experiencias de usuario y las interfaces administrativas necesarias para proporcionar una solución integral para configurar, administrar, grabar, almacenar y analizar Teams comunicaciones.</span><span class="sxs-lookup"><span data-stu-id="b1530-105">Teams has been enhanced to support integration of third-party recording solutions, including the platform functionality, user experiences, and administrative interfaces needed to provide an end-to-end solution for configuring, managing, recording, storing, and analyzing Teams communications.</span></span> <span data-ttu-id="b1530-106">Entre las mejoras se incluyen las API de la plataforma de comunicaciones y los eventos para la grabación, que proporciona:</span><span class="sxs-lookup"><span data-stu-id="b1530-106">Enhancements include communications platform APIs and events for recording, which provides:</span></span>

- <span data-ttu-id="b1530-107">Captura de medios sin problemas y de alta calidad en todos los dispositivos y todos los puntos de conexión compatibles para audio, vídeo, uso compartido de pantalla y chat.</span><span class="sxs-lookup"><span data-stu-id="b1530-107">Seamless, high-quality media capture across devices and all   supported endpoints for audio, video, screen share, and chat.</span></span>

- <span data-ttu-id="b1530-108">Compatibilidad para la captura de interacción entre Teams usuarios y puntos de conexión de llamadas admitidos (Teams, Teams móvil, Skype Empresarial, RTC)</span><span class="sxs-lookup"><span data-stu-id="b1530-108">Support for interaction capture between Teams users and supported   calling endpoints (Teams, Teams Mobile, Skype for Business, PSTN)</span></span>

- <span data-ttu-id="b1530-109">Nuevas directivas administrativas para la grabación de cumplimiento, incluida la integración con las Teams y las herramientas y directivas de reuniones y llamadas administrativas existentes</span><span class="sxs-lookup"><span data-stu-id="b1530-109">New administrative policies for compliance recording, including   integration with existing Teams administrative calling and   meeting tools and policies</span></span>

<span data-ttu-id="b1530-110">La grabación de cumplimiento se puede habilitar en Microsoft 365 usuarios de A3/A5/E3/E5/Business Premium y Office 365 A3/A5/E3/E5.</span><span class="sxs-lookup"><span data-stu-id="b1530-110">Compliance Recording can be enabled on Microsoft 365 A3/A5/E3/E5/Business Premium and Office 365 A3/A5/E3/E5 users.</span></span> 

<span data-ttu-id="b1530-111">Las capacidades de integración de la solución de grabación de cumplimiento también se revisaron en Ignite 2019 en la sesión Grabación de cumplimiento [y Microsoft Teams cumplimiento.](https://myignite.microsoft.com/archives/IG19-VCE40)</span><span class="sxs-lookup"><span data-stu-id="b1530-111">The compliance recording solution integration capabilities were also reviewed at Ignite 2019 in the [Compliance Recording and Microsoft Teams session](https://myignite.microsoft.com/archives/IG19-VCE40).</span></span>

## <a name="teams-interaction-recording-overview"></a><span data-ttu-id="b1530-112">Teams información general sobre la grabación de interacciones</span><span class="sxs-lookup"><span data-stu-id="b1530-112">Teams interaction recording overview</span></span>

<span data-ttu-id="b1530-113">Los casos de uso de grabaciones de interacción se pueden separar en cuatro categorías principales de funcionalidad de grabación: Comodidad, Funcionalidad, Organización e Interceptación legal, como se muestra en la imagen:</span><span class="sxs-lookup"><span data-stu-id="b1530-113">Interaction recording use cases can effectively be separated into four primary categories of recording functionality – Convenience, Functional, Organizational, and Lawful Intercept, as shown in the image:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b1530-114">![Captura de pantalla que muestra la interacción que registra qué y por qué.](media/recording-taxonomy.png "La imagen muestra las categorías de grabación.")</span><span class="sxs-lookup"><span data-stu-id="b1530-114">![Screenshot showing the interaction recording what and why.](media/recording-taxonomy.png "The image shows the recording categories.")</span></span>

<span data-ttu-id="b1530-115">Cada una de las categorías implica requisitos diferentes para cómo se inician las grabaciones, qué se graba, dónde se almacenan las grabaciones, quién se notifica, quién controla el acceso y cómo se controla la retención.</span><span class="sxs-lookup"><span data-stu-id="b1530-115">Each of the categories entails different requirements for how recordings are initiated, what is recorded, where recordings are stored, who is notified, who controls access, and how retention is handled.</span></span>

| <span data-ttu-id="b1530-116">Tipo</span><span class="sxs-lookup"><span data-stu-id="b1530-116">Type</span></span>                   | <span data-ttu-id="b1530-117">Comodidad (grabación Teams normal)</span><span class="sxs-lookup"><span data-stu-id="b1530-117">Convenience (Regular Teams Recording)</span></span> | <span data-ttu-id="b1530-118">Organización: regulado (grabación de cumplimiento)</span><span class="sxs-lookup"><span data-stu-id="b1530-118">Org - Regulated (Compliance Recording)</span></span> |
| ---------------------- | ------------------ | --------------- |
| <span data-ttu-id="b1530-119">Iniciador</span><span class="sxs-lookup"><span data-stu-id="b1530-119">Initiator</span></span>              | <span data-ttu-id="b1530-120">Usuario</span><span class="sxs-lookup"><span data-stu-id="b1530-120">User</span></span>               | <span data-ttu-id="b1530-121">Administrador (sistema)</span><span class="sxs-lookup"><span data-stu-id="b1530-121">Admin (system)</span></span>  |
| <span data-ttu-id="b1530-122">Destino</span><span class="sxs-lookup"><span data-stu-id="b1530-122">Target</span></span>                 | <span data-ttu-id="b1530-123">Por llamada /reunión</span><span class="sxs-lookup"><span data-stu-id="b1530-123">Per-call / meeting</span></span> | <span data-ttu-id="b1530-124">Por usuario</span><span class="sxs-lookup"><span data-stu-id="b1530-124">Per-user</span></span>        |
| <span data-ttu-id="b1530-125">Storage propietario</span><span class="sxs-lookup"><span data-stu-id="b1530-125">Storage owner</span></span>          | <span data-ttu-id="b1530-126">Usuario</span><span class="sxs-lookup"><span data-stu-id="b1530-126">User</span></span>               | <span data-ttu-id="b1530-127">Cumplimiento</span><span class="sxs-lookup"><span data-stu-id="b1530-127">Compliance</span></span>      |
| <span data-ttu-id="b1530-128">¿Se requiere notificación?</span><span class="sxs-lookup"><span data-stu-id="b1530-128">Notification required?</span></span> | <span data-ttu-id="b1530-129">Sí</span><span class="sxs-lookup"><span data-stu-id="b1530-129">Yes</span></span>                | <span data-ttu-id="b1530-130">Sí</span><span class="sxs-lookup"><span data-stu-id="b1530-130">Yes</span></span>             |
| <span data-ttu-id="b1530-131">Propietario de Access</span><span class="sxs-lookup"><span data-stu-id="b1530-131">Access Owner</span></span>           | <span data-ttu-id="b1530-132">Usuario</span><span class="sxs-lookup"><span data-stu-id="b1530-132">User</span></span>               | <span data-ttu-id="b1530-133">Cumplimiento</span><span class="sxs-lookup"><span data-stu-id="b1530-133">Compliance</span></span>      |
| <span data-ttu-id="b1530-134">¿Directiva de retención?</span><span class="sxs-lookup"><span data-stu-id="b1530-134">Retention Policy?</span></span>      | <span data-ttu-id="b1530-135">Opcional</span><span class="sxs-lookup"><span data-stu-id="b1530-135">Optional</span></span>           | <span data-ttu-id="b1530-136">Sí</span><span class="sxs-lookup"><span data-stu-id="b1530-136">Yes</span></span>             |

<span data-ttu-id="b1530-137">Teams ofrece varias capacidades para [la grabación](./cloud-recording.md) práctica y funcional para reuniones y eventos en directo.</span><span class="sxs-lookup"><span data-stu-id="b1530-137">Teams provides various capabilities for [convenient](./cloud-recording.md) and functional recording for meetings and live events.</span></span> <span data-ttu-id="b1530-138">La grabación de la organización significa permitir que las organizaciones que adopten Teams para llamadas y reuniones se estipulen, mediante una directiva administrativa, cuando las llamadas y las reuniones en línea deben grabarse automáticamente y capturarse para su posterior procesamiento y retención según lo requiera la directiva corporativa o normativa pertinente.</span><span class="sxs-lookup"><span data-stu-id="b1530-138">Organizational recording means enabling organizations adopting Teams for calling and meetings to stipulate, by way of an administrative policy, when calls and online meetings should be automatically recorded and captured for subsequent processing and retention as required by relevant corporate or regulatory policy.</span></span> <span data-ttu-id="b1530-139">Los usuarios de esta directiva serán conscientes de que se están grabando sus interacciones digitales con Teams, pero no podrán deshabilitar la grabación y no tendrán acceso a la grabación una vez completada la interacción.</span><span class="sxs-lookup"><span data-stu-id="b1530-139">Users under this policy will be aware that their digital interactions with Teams are being recorded but will not be able to disable the recording and will not have access to the recording once the interaction is complete.</span></span> <span data-ttu-id="b1530-140">La grabación forma parte del archivo organizativo disponible para el personal legal y de cumplimiento para eDiscovery, retención legal y otros usos de retención corporativa.</span><span class="sxs-lookup"><span data-stu-id="b1530-140">The recording becomes part of the organizational archive available to compliance and legal personnel for eDiscovery, legal hold, and other corporate retention uses.</span></span>

## <a name="example-user-needs"></a><span data-ttu-id="b1530-141">Necesidades de usuario de ejemplo</span><span class="sxs-lookup"><span data-stu-id="b1530-141">Example user needs</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="b1530-142">Rol</span><span class="sxs-lookup"><span data-stu-id="b1530-142">Persona</span></span></th>
<th><span data-ttu-id="b1530-143">Necesidades</span><span class="sxs-lookup"><span data-stu-id="b1530-143">Needs</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="b1530-144">Usuarios grabados</span><span class="sxs-lookup"><span data-stu-id="b1530-144">Recorded users</span></span></td>
<td><ul>
<li><p><span data-ttu-id="b1530-145">Recibir una notificación cuando la grabación esté en curso.</span><span class="sxs-lookup"><span data-stu-id="b1530-145">Be notified when recording is in progress.</span></span></p></li>
<li><p><span data-ttu-id="b1530-146">Esté informado cuando el error de la directiva o la grabadora esté provocando cambios en el comportamiento de las llamadas.</span><span class="sxs-lookup"><span data-stu-id="b1530-146">Be informed when policy and/or recorder error is causing changes in calling behavior.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="b1530-147">Administrador de comunicaciones</span><span class="sxs-lookup"><span data-stu-id="b1530-147">Communications admin</span></span></td>
<td><ul>
<li><p><span data-ttu-id="b1530-148">Comprender por qué y cómo aplicar o aplicar directivas de grabación a Teams usuarios o puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="b1530-148">Understand why and how to apply / enforce recording policies to Teams users / endpoints.</span></span></p></li>
<li><p><span data-ttu-id="b1530-149">Configure y mantenga Teams de grabación para la organización.</span><span class="sxs-lookup"><span data-stu-id="b1530-149">Configure and maintain Teams recording policies for the organization.</span></span></p></li>
<li><p><span data-ttu-id="b1530-150">Supervise y solucione problemas relacionados con la grabación Teams llamadas y reuniones.</span><span class="sxs-lookup"><span data-stu-id="b1530-150">Monitor and troubleshoot recording-related issues with Teams calls and meetings.</span></span></p></li>
<li><p><span data-ttu-id="b1530-151">Soporte técnico de cumplimiento interno con análisis operativos sobre uso, calidad y confiabilidad.</span><span class="sxs-lookup"><span data-stu-id="b1530-151">Support internal compliance officer with operational analytics on usage, quality, and reliability.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="b1530-152">Oficial de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="b1530-152">Compliance officer</span></span></td>
<td><ul>
<li><p><span data-ttu-id="b1530-153">Recopile todas Teams comunicaciones de la forma necesaria para cumplir con las obligaciones de cumplimiento en los límites regionales adecuados.</span><span class="sxs-lookup"><span data-stu-id="b1530-153">Collect all Teams communications in the manner required to meet compliance obligations in appropriate regional boundaries.</span></span></p></li>
<li><p><span data-ttu-id="b1530-154">Busque interacciones basadas en metadatos relacionados con la comunicación o contenido de interacción.</span><span class="sxs-lookup"><span data-stu-id="b1530-154">Search for interactions based on communication-related metadata or interaction content.</span></span> <span data-ttu-id="b1530-155">Algunos ejemplos comunes son:</span><span class="sxs-lookup"><span data-stu-id="b1530-155">Common examples include:</span></span></p>
<ul>
<li><p><span data-ttu-id="b1530-156"><strong>Metadatos</strong> - Participantes, hora, dirección, número marcado, número de origen, datos empresariales personalizados</span><span class="sxs-lookup"><span data-stu-id="b1530-156"><strong>Metadata</strong> - Participants, time, direction, dialed number, origin number, Custom business data</span></span></p></li>
<li><p><span data-ttu-id="b1530-157"><strong>Contenido:</strong> transcripción, sentimientos, fonéticas, interacciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="b1530-157"><strong>Content</strong> – Transcription, sentiment, phonetics, related interactions</span></span></p></li>
</ul></li>
<li><p><span data-ttu-id="b1530-158">Analice e interactúe con las comunicaciones recopiladas, incluida la capacidad de supervisar las interacciones a medida que se recopilan.</span><span class="sxs-lookup"><span data-stu-id="b1530-158">Analyze and interact with collected communications, including the ability to monitor interactions as they are being collected.</span></span></p></li>
<li><p><span data-ttu-id="b1530-159">Garantizar la seguridad de las comunicaciones recopiladas y evitar la manipulación en todas las fases.</span><span class="sxs-lookup"><span data-stu-id="b1530-159">Ensure security of collected communications and prevent tampering at all stages.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="solution-architecture-overview"></a><span data-ttu-id="b1530-160">Introducción a la arquitectura de la solución</span><span class="sxs-lookup"><span data-stu-id="b1530-160">Solution architecture overview</span></span>

<span data-ttu-id="b1530-161">Las soluciones de grabación de cumplimiento se integran Teams como se muestra en el siguiente diagrama:</span><span class="sxs-lookup"><span data-stu-id="b1530-161">Compliance recording solutions are integrated with Teams as shown in the following diagram:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b1530-162">![Captura de pantalla que muestra la configuración de la aplicación personalizada del equipo](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "Las imágenes muestran el flujo cuando se envía y recibe Teams reunión o llamada.")</span><span class="sxs-lookup"><span data-stu-id="b1530-162">![Screenshot showing the team custom app setting](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "The images shows the flow when a Teams meeting or call is sent and received.")</span></span>

## <a name="recorder"></a><span data-ttu-id="b1530-163">Grabadora</span><span class="sxs-lookup"><span data-stu-id="b1530-163">Recorder</span></span>

<span data-ttu-id="b1530-164">El componente principal de la solución de grabación de cumplimiento es la grabadora.</span><span class="sxs-lookup"><span data-stu-id="b1530-164">The core component of the compliance recording solution is the recorder.</span></span>
<span data-ttu-id="b1530-165">Las grabadoras se han creado como servicios escalables basados en Azure (bots) que aprovechan la plataforma de comunicaciones de [Microsoft](/graph/cloud-communications-concept-overview) y se registran como aplicaciones con Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="b1530-165">Recorders are built as scalable Azure-based services (bots) that [leverage Microsoft’s communications platform](/graph/cloud-communications-concept-overview) and register as applications with Microsoft Graph.</span></span> <span data-ttu-id="b1530-166">La grabadora proporciona la interacción directa con las [](/graph/api/resources/communications-api-overview?view=graph-rest-1.0) API Teams de la plataforma de comunicaciones de llamadas y reuniones y proporciona el punto de conexión para la ingestión de medios.</span><span class="sxs-lookup"><span data-stu-id="b1530-166">The recorder provides the direct interaction with the Teams calls and meetings [communications platform APIs](/graph/api/resources/communications-api-overview?view=graph-rest-1.0) and provides the endpoint for media ingestion.</span></span>

<span data-ttu-id="b1530-167">Hay [disponible una aplicación de](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) grabadora de cumplimiento de ejemplo que muestra cómo configurar el bot, crear la instancia de la aplicación y asignar las directivas de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="b1530-167">A [sample compliance recorder application is available](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) that shows how to configure the bot, create the app instance and assign the compliance policies.</span></span> <span data-ttu-id="b1530-168">El ejemplo también tiene ejemplos sobre el uso [](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244) de la API para registrar interacciones específicas, como el control del enrutamiento de llamadas entrantes, [](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138)el cambio de estados de grabación y la eliminación del usuario que se está [grabando.](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126)</span><span class="sxs-lookup"><span data-stu-id="b1530-168">The sample also has examples on API usage for recording specific interactions such as handling [incoming call](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244) routing, [changing recording states](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138), and [removing the user who is being recorded](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126).</span></span>
<span data-ttu-id="b1530-169">Graph documentación sobre las API específicas se puede encontrar aquí para [updateRecordingStatus](/graph/api/call-updaterecordingstatus?tabs=http&view=graph-rest-1.0) y [incomingContext](/graph/api/resources/incomingcontext?view=graph-rest-1.0).</span><span class="sxs-lookup"><span data-stu-id="b1530-169">Graph documentation on the specific APIs can be found here for [updateRecordingStatus](/graph/api/call-updaterecordingstatus?tabs=http&view=graph-rest-1.0) and [incomingContext](/graph/api/resources/incomingcontext?view=graph-rest-1.0).</span></span>

<span data-ttu-id="b1530-170">La implementación exacta del servicio de grabadora variará según el asociado, pero debe diseñarse para admitir varias grabadoras con el fin de lograr una alta disponibilidad y distribución geográfica de la implementación para reducir la latencia de Teams a la grabadora.</span><span class="sxs-lookup"><span data-stu-id="b1530-170">The exact implementation of the recorder service will vary by partner but must be designed to support multiple recorders in order to achieve high availability and geographical distribution of deployment to reduce latency from Teams to the recorder.</span></span> <span data-ttu-id="b1530-171">Además, se espera que los propios Grabadores se diseñen pensando en la resistencia y redundancia.</span><span class="sxs-lookup"><span data-stu-id="b1530-171">In addition, it is expected that Recorders themselves be designed with resiliency and redundancy in mind.</span></span>

<span data-ttu-id="b1530-172">Los partners deben confirmar la versión mínima necesaria de las API y SDK de comunicaciones de Microsoft Graph con Microsoft antes de enviar su solución para la certificación para asegurarse de que todos los requisitos de integración de grabaciones de cumplimiento son compatibles.</span><span class="sxs-lookup"><span data-stu-id="b1530-172">Partners must confirm the minimum required release version of the Microsoft Graph communications APIs and SDKs with Microsoft before submitting their solution for certification to ensure that all requirements of compliance recording integration are supported.</span></span>

<span data-ttu-id="b1530-173">Dos requisitos específicos que son fundamentales para el escenario de grabación de cumplimiento son:</span><span class="sxs-lookup"><span data-stu-id="b1530-173">Two specific requirements that are fundamental for compliance recording scenario are:</span></span>

- <span data-ttu-id="b1530-174">El bot de grabadora debe implementarse en Azure</span><span class="sxs-lookup"><span data-stu-id="b1530-174">Recorder bot must be deployed in Azure</span></span>

- <span data-ttu-id="b1530-175">El bot grabadora debe ejecutarse en una máquina Windows en Azure</span><span class="sxs-lookup"><span data-stu-id="b1530-175">Recorder bot must run on a Windows VM in Azure</span></span>

<span data-ttu-id="b1530-176">Los requisitos de máquina virtual de Azure y Windows solo se aplican al componente bot de Teams, lo que significa que un partner puede implementar el resto de la plataforma de su elección siempre que puedan cumplir los requisitos de rendimiento y funcionalidad relevantes para la grabación de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="b1530-176">The Azure and Windows VM requirements only apply to the Teams Bot component, which means that a partner may implement the rest of the platform of their choice provided they can meet the relevant performance and functional requirements for compliance recording.</span></span>

## <a name="compliance-recording-policy-assignment-and-provisioning"></a><span data-ttu-id="b1530-177">Asignación y aprovisionamiento de directivas de registro de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="b1530-177">Compliance recording policy assignment and provisioning</span></span>

<span data-ttu-id="b1530-178">Los administradores de TI pueden determinar qué usuarios se van a grabar y qué grabadora se usará para cada usuario, creando y asignando directivas de grabación de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="b1530-178">IT Administrators can determine which users are to be recorded and which recorder will be used for each user, by creating and assigning compliance recording policies.</span></span> <span data-ttu-id="b1530-179">Las grabadoras se invitan automáticamente a participar en conversaciones en función de la configuración de estas directivas cuando se produce una interacción de comunicación.</span><span class="sxs-lookup"><span data-stu-id="b1530-179">Recorders are automatically invited to participate in conversations based on the configuration of these policies when a communication interaction takes place.</span></span> <span data-ttu-id="b1530-180">Las directivas de registro de cumplimiento se administran con [Microsoft PowerShell](./teams-powershell-overview.md) y se pueden aplicar en el nivel de inquilino, por usuario y grupo de seguridad de cada organización.</span><span class="sxs-lookup"><span data-stu-id="b1530-180">Compliance recording policies are managed using [Microsoft PowerShell](./teams-powershell-overview.md) and can be applied at the tenant, per-user, and security group level for each organization.</span></span> <span data-ttu-id="b1530-181">Puede encontrar más información sobre directivas de Microsoft Docs para [reuniones,](./meeting-policies-in-teams.md)directivas [de llamadas y](./teams-calling-policy.md) directivas de [grupo.](./assign-policies.md#assign-a-policy-to-a-group)</span><span class="sxs-lookup"><span data-stu-id="b1530-181">You can find more information on Microsoft Docs for [Meeting policies](./meeting-policies-in-teams.md), [calling policies](./teams-calling-policy.md) and  [group policies](./assign-policies.md#assign-a-policy-to-a-group).</span></span>

1. <span data-ttu-id="b1530-182">Cree una instancia de aplicación en el espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="b1530-182">Create an application instance in your tenant.</span></span>

   ```powershell
   PS C:\> New-CsOnlineApplicationInstance -UserPrincipalName cr.instance@contoso.onmicrosoft.com -DisplayName ComplianceRecordingBotInstance -ApplicationId fcc88ff5-a42d-49cf-b3d8-f2e1f609d511

   RunspaceId        : 4c13efa6-77bc-42db-b5bf-bdd62cdfc5df
   ObjectId          : 5069aae5-c451-4983-9e57-9455ced220b7
   TenantId          : 5b943d7c-5e14-474b-8237-5022eb8e0dc9
   UserPrincipalName : cr.instance@contoso.onmicrosoft.com
   ApplicationId     : fcc88ff5-a42d-49cf-b3d8-f2e1f609d511
   DisplayName       : ComplianceRecordingBotInstance
   PhoneNumber       :
   ```

   ```powershell
   PS C:\> Sync-CsOnlineApplicationInstance -ObjectId 5069aae5-c451-4983-9e57-9455ced220b7
   ```

2. <span data-ttu-id="b1530-183">Crear una directiva de grabación de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="b1530-183">Create a Compliance Recording policy.</span></span>

   ```powershell
   PS C:\> New-CsTeamsComplianceRecordingPolicy -Identity TestComplianceRecordingPolicy -Enabled $true -Description "Test policy created by tenant admin"

   Identity                        : Global
   ComplianceRecordingApplications : {}
   Enabled                         : True
   WarnUserOnRemoval               : True
   Description                     : Test policy created by tenant admin
   ```

   ```powershell
   PS C:\> Set-CsTeamsComplianceRecordingPolicy -Identity TestComplianceRecordingPolicy `
   -ComplianceRecordingApplications @(New-CsTeamsComplianceRecordingApplication -Id 5069aae5-c451-4983-9e57-9455ced220b7 -Parent TestComplianceRecordingPolicy)
   ```

   <span data-ttu-id="b1530-184">Vea [Set-CsTeamsComplianceRecordingPolicy](/powershell/module/skype/set-csteamscompliancerecordingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="b1530-184">See [Set-CsTeamsComplianceRecordingPolicy](/powershell/module/skype/set-csteamscompliancerecordingpolicy?view=skype-ps).</span></span>

3. <span data-ttu-id="b1530-185">Asigne la directiva grabación de cumplimiento a un usuario.</span><span class="sxs-lookup"><span data-stu-id="b1530-185">Assign the Compliance Recording policy to a user.</span></span>

   ```powershell
   PS C:\> Grant-CsTeamsComplianceRecordingPolicy -Identity testuser@contoso.onmicrosoft.com -PolicyName TestComplianceRecordingPolicy
   ```

   <span data-ttu-id="b1530-186">Vea [Grant-CsTeamsComplianceRecordingPolicy](/powershell/module/skype/grant-csteamscompliancerecordingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="b1530-186">See [Grant-CsTeamsComplianceRecordingPolicy](/powershell/module/skype/grant-csteamscompliancerecordingpolicy?view=skype-ps).</span></span>

   ```powershell
   PS C:\> Get-CsOnlineUser testuser@contoso.onmicrosoft.com | select SipAddress, TenantId, TeamsComplianceRecordingPolicy | fl

   UserPrincipalName              : testuser@contoso.onmicrosoft.com
   TenantId                       : 5b943d7c-5e14-474b-8237-5022eb8e0dc9
   TeamsComplianceRecordingPolicy : TestComplianceRecordingPolicy
   ```

## <a name="user-experiences"></a><span data-ttu-id="b1530-187">Experiencias de usuario</span><span class="sxs-lookup"><span data-stu-id="b1530-187">User experiences</span></span>

<span data-ttu-id="b1530-188">El soporte para notificaciones está habilitado con las Teams cliente.</span><span class="sxs-lookup"><span data-stu-id="b1530-188">Support for notifications is enabled using the Teams client experiences.</span></span> <span data-ttu-id="b1530-189">Las experiencias pueden ser visuales o de audio.</span><span class="sxs-lookup"><span data-stu-id="b1530-189">The experiences can be either visual or audio.</span></span>

<span data-ttu-id="b1530-190">**Teams clientes: aviso visual**</span><span class="sxs-lookup"><span data-stu-id="b1530-190">**Teams clients - visual notice**</span></span>
- <span data-ttu-id="b1530-191">Escritorio/web</span><span class="sxs-lookup"><span data-stu-id="b1530-191">Desktop/web</span></span>
- <span data-ttu-id="b1530-192">Móvil (iOS/Android)</span><span class="sxs-lookup"><span data-stu-id="b1530-192">Mobile (iOS/Android)</span></span>
- <span data-ttu-id="b1530-193">Teams teléfonos</span><span class="sxs-lookup"><span data-stu-id="b1530-193">Teams phones</span></span>
- <span data-ttu-id="b1530-194">Teams salas</span><span class="sxs-lookup"><span data-stu-id="b1530-194">Teams rooms</span></span>

<span data-ttu-id="b1530-195">**Otros puntos de conexión: aviso de audio**</span><span class="sxs-lookup"><span data-stu-id="b1530-195">**Other endpoints - audio notice**</span></span>
- <span data-ttu-id="b1530-196">Teléfonos SIP</span><span class="sxs-lookup"><span data-stu-id="b1530-196">SIP phones</span></span>
- <span data-ttu-id="b1530-197">Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="b1530-197">Skype for Business</span></span>
- <span data-ttu-id="b1530-198">Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="b1530-198">Audio conferencing</span></span>
- <span data-ttu-id="b1530-199">Autores de llamadas RTC</span><span class="sxs-lookup"><span data-stu-id="b1530-199">PSTN callers</span></span>

## <a name="compliance-recording-for-teams-certification-programs"></a><span data-ttu-id="b1530-200">Grabación de cumplimiento para Teams de certificación</span><span class="sxs-lookup"><span data-stu-id="b1530-200">Compliance recording for Teams certification programs</span></span>

<span data-ttu-id="b1530-201">Además de publicar API disponibles públicamente que permiten a los partners desarrollar e integrar soluciones de CCaaS con Teams Microsoft Teams, hemos desarrollado la grabación de cumplimiento para un programa de certificación para proporcionar a los clientes la garantía de que la solución de cada partner participante se ha probado y comprobado para proporcionar la calidad, compatibilidad y confiabilidad que esperan de las soluciones de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b1530-201">In addition to publishing publicly available APIs allowing partners to develop and integrate CCaaS solutions with Teams, we have developed the compliance recording for Microsoft Teams certification program to provide customers with the assurance that each participating partner’s solution has been tested and verified to provide the quality, compatibility and reliability they expect from Microsoft solutions.</span></span>  

<span data-ttu-id="b1530-202">Los siguientes partners han certificado su solución para Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b1530-202">The following partners have certified their solution for Microsoft Teams.</span></span><br/><br/>

|<span data-ttu-id="b1530-203">Partner</span><span class="sxs-lookup"><span data-stu-id="b1530-203">Partner</span></span>|<span data-ttu-id="b1530-204">Sitio web de soluciones</span><span class="sxs-lookup"><span data-stu-id="b1530-204">Solution website</span></span> |
|:--|:--|
|<span data-ttu-id="b1530-205">TECNOLOGÍAS ASC</span><span class="sxs-lookup"><span data-stu-id="b1530-205">ASC Technologies</span></span> |[https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html](https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html) |
|<span data-ttu-id="b1530-206">AudioCodes</span><span class="sxs-lookup"><span data-stu-id="b1530-206">AudioCodes</span></span> |[https://www.audiocodes.com/solutions-products/voiceai/meetings-and-recording/smarttap-360](https://www.audiocodes.com/solutions-products/voiceai/meetings-and-recording/smarttap-360) |
|<span data-ttu-id="b1530-207">CallCabinet</span><span class="sxs-lookup"><span data-stu-id="b1530-207">CallCabinet</span></span> |[https://www.callcabinet.com/compliance-microsoft-teams-call-recording](https://www.callcabinet.com/compliance-microsoft-teams-call-recording ) |
|<span data-ttu-id="b1530-208">Dubber</span><span class="sxs-lookup"><span data-stu-id="b1530-208">Dubber</span></span> |[https://www.dubber.net/call-recording/](https://www.dubber.net/call-recording/) |
|<span data-ttu-id="b1530-209">Muy bien</span><span class="sxs-lookup"><span data-stu-id="b1530-209">NICE</span></span> |[https://www.niceactimize.com/compliance/ms-teams-recording.html](https://www.niceactimize.com/compliance/ms-teams-recording.html) |
|<span data-ttu-id="b1530-210">Numonix</span><span class="sxs-lookup"><span data-stu-id="b1530-210">Numonix</span></span> |[https://numonix.cloud](https://numonix.cloud)    |
|<span data-ttu-id="b1530-211">Lago Theta</span><span class="sxs-lookup"><span data-stu-id="b1530-211">Theta Lake</span></span> |[https://thetalake.com/integrations/microsoft/](https://thetalake.com/integrations/microsoft/) |
|<span data-ttu-id="b1530-212">Verint</span><span class="sxs-lookup"><span data-stu-id="b1530-212">Verint</span></span> |[https://www.verba.com/solutions/microsoft-teams-recording](https://www.verba.com/solutions/microsoft-teams-recording) |

<br/>
<span data-ttu-id="b1530-213">Los siguientes partners están en proceso de certificar su solución para Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b1530-213">The following partners are in the process of certifying their solution for Microsoft Teams.</span></span><br/><br/>

|<span data-ttu-id="b1530-214">Partner</span><span class="sxs-lookup"><span data-stu-id="b1530-214">Partner</span></span>|<span data-ttu-id="b1530-215">Sitio web de soluciones</span><span class="sxs-lookup"><span data-stu-id="b1530-215">Solution website</span></span> |
|:--|:--|
|<span data-ttu-id="b1530-216">Tecnología perspicaz</span><span class="sxs-lookup"><span data-stu-id="b1530-216">Insightful Technology</span></span> |[http://www.insightfultechnology.com/what-we-do/fixed-line-voice-recording/](http://www.insightfultechnology.com/what-we-do/fixed-line-voice-recording/) |
|<span data-ttu-id="b1530-217">Landis Technologies</span><span class="sxs-lookup"><span data-stu-id="b1530-217">Landis Technologies</span></span> |[https://landistechnologies.com/](https://landistechnologies.com/) |
|<span data-ttu-id="b1530-218">Luware</span><span class="sxs-lookup"><span data-stu-id="b1530-218">Luware</span></span> |[https://luware.com/en/solution/microsoft-teams-recording/](https://luware.com/en/solution/microsoft-teams-recording/) |
|<span data-ttu-id="b1530-219">Innovación de roble</span><span class="sxs-lookup"><span data-stu-id="b1530-219">Oak Innovation</span></span> |[https://www.oakinnovate.com/call-recording](https://www.oakinnovate.com/call-recording) |
|<span data-ttu-id="b1530-220">Cuadro rojo</span><span class="sxs-lookup"><span data-stu-id="b1530-220">Red Box</span></span> |[https://www.redboxvoice.com/compliance-recording-for-microsoft-teams](https://www.redboxvoice.com/compliance-recording-for-microsoft-teams)  |

<span data-ttu-id="b1530-221">Esta lista se actualizará a medida que más partners se unan y cumplan los criterios de certificación.</span><span class="sxs-lookup"><span data-stu-id="b1530-221">This list will be updated as more partners join and meet the certification criteria.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b1530-222">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="b1530-222">Next steps</span></span>

<span data-ttu-id="b1530-223">Si es un proveedor que desea unirse al programa de certificación, envíe un correo  <a href= "mailto:Teamscategorypartner@microsoft.com">electrónico Teamscategorypartner@microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="b1530-223">If you are a vendor seeking to join the certification program, please mail  <a href= "mailto:Teamscategorypartner@microsoft.com">Teamscategorypartner@microsoft.com</a>.</span></span>
