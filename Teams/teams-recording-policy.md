---
title: Introducción a la grabación basada en directivas de Teams para llamar & reuniones
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
description: Obtener información sobre la grabación basada en directivas de Teams para llamar & reuniones
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
ms.openlocfilehash: af369a04836fd12c032f468324bbaf920417878d
ms.sourcegitcommit: 3a577c07b4f399c81d8650a2bba8cfc00b695b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2020
ms.locfileid: "48650973"
---
# <a name="introduction-to-teams-policy-based-recording-for-callings--meetings"></a><span data-ttu-id="9a10d-103">Introducción a la grabación basada en directivas de Teams para realizar llamadas & reuniones</span><span class="sxs-lookup"><span data-stu-id="9a10d-103">Introduction to Teams policy-based recording for callings & meetings</span></span>

<span data-ttu-id="9a10d-104">La grabación basada en directivas permite a las organizaciones que adoptan Microsoft Teams las llamadas y reuniones que estipulan, mediante una directiva administrativa, cuando las llamadas y las reuniones en línea deben grabarse y capturarse automáticamente para su procesamiento y retención posterior, según lo requiera la política corporativa o normativa pertinente.</span><span class="sxs-lookup"><span data-stu-id="9a10d-104">Policy-based recording enables organizations that adopt Microsoft Teams for calling and meetings to stipulate, using an administrative policy, when calls and online meetings should be automatically recorded and captured for subsequent processing and retention as required by relevant corporate or regulatory policy.</span></span>

<span data-ttu-id="9a10d-105">Teams ha sido mejorado para admitir la integración de soluciones de grabación de terceros, entre las que se incluyen la funcionalidad de plataforma, las experiencias de usuario y las interfaces administrativas necesarias para proporcionar una solución completa para configurar, administrar, registrar, almacenar y analizar comunicaciones de Teams.</span><span class="sxs-lookup"><span data-stu-id="9a10d-105">Teams has been enhanced to support integration of third-party recording solutions, including the platform functionality, user experiences, and administrative interfaces needed to provide an end-to-end solution for configuring, managing, recording, storing, and analyzing Teams communications.</span></span> <span data-ttu-id="9a10d-106">Esto incluye las API y eventos de la plataforma de comunicaciones para la grabación, que ofrece:</span><span class="sxs-lookup"><span data-stu-id="9a10d-106">This includes communications platform APIs and events for recording, which provides:</span></span>

- <span data-ttu-id="9a10d-107">Captura multimedia sin problemas y de alta calidad en todos los dispositivos y todos los puntos de conexión compatibles con audio, vídeo, pantalla compartida y chat.</span><span class="sxs-lookup"><span data-stu-id="9a10d-107">Seamless, high-quality media capture across devices and all   supported endpoints for audio, video, screen share, and chat.</span></span>

- <span data-ttu-id="9a10d-108">Compatibilidad con la captura de interacción entre usuarios de equipos y puntos de conexión de llamadas compatibles (equipos, equipos móviles, Skype empresarial, RTC)</span><span class="sxs-lookup"><span data-stu-id="9a10d-108">Support for interaction capture between Teams users and supported   calling endpoints (Teams, Teams Mobile, Skype for Business, PSTN)</span></span>

- <span data-ttu-id="9a10d-109">Nuevas directivas administrativas para la grabación de cumplimiento, incluida la integración con las herramientas y políticas de reuniones y herramientas administrativas existentes de Teams</span><span class="sxs-lookup"><span data-stu-id="9a10d-109">New administrative policies for compliance recording, including   integration with existing Teams administrative calling and   meeting tools and policies</span></span>

<span data-ttu-id="9a10d-110">Las capacidades de integración de soluciones de grabación de cumplimiento también fueron revisadas en el encendido 2019 de la [<span class="underline">sesión de cumplimiento y Microsoft Teams</span>](https://myignite.techcommunity.microsoft.com/sessions/83184?source=sessions).</span><span class="sxs-lookup"><span data-stu-id="9a10d-110">The compliance recording solution integration capabilities were also reviewed at Ignite 2019 in the [<span class="underline">Compliance Recording and Microsoft Teams session</span>](https://myignite.techcommunity.microsoft.com/sessions/83184?source=sessions).</span></span>

## <a name="teams-interaction-recording-overview"></a><span data-ttu-id="9a10d-111">Introducción a la grabación de interacción de Teams</span><span class="sxs-lookup"><span data-stu-id="9a10d-111">Teams interaction recording overview</span></span>

<span data-ttu-id="9a10d-112">Los casos de uso de grabación de interacción pueden dividirse en cuatro categorías principales de funcionalidad de grabación: conveniencia, funcional, organizacional e intercepta legal, tal y como se muestra en la imagen:</span><span class="sxs-lookup"><span data-stu-id="9a10d-112">Interaction recording use cases can effectively be separated into four primary categories of recording functionality – Convenience, Functional, Organizational, and Lawful Intercept, as shown in the image:</span></span>

<span data-ttu-id="9a10d-113">![Captura de pantalla que muestra la interacción que registra qué es y por qué.](media/recording-taxonomy.png "La imagen muestra las categorías de grabación.")</span><span class="sxs-lookup"><span data-stu-id="9a10d-113">![Screenshot showing the interaction recording what and why.](media/recording-taxonomy.png "The image shows the recording categories.")</span></span>

<span data-ttu-id="9a10d-114">Cada una de las categorías conlleva diferentes requisitos sobre cómo se inician las grabaciones, qué se graba, dónde se almacenan las grabaciones, a quién se notifica, quién controla Access y cómo se administra la retención.</span><span class="sxs-lookup"><span data-stu-id="9a10d-114">Each of the categories entails different requirements for how recordings are initiated, what is recorded, where recordings are stored, who is notified, who controls access, and how retention is handled.</span></span>

|                        | <span data-ttu-id="9a10d-115">Prácticos</span><span class="sxs-lookup"><span data-stu-id="9a10d-115">Convenience</span></span>        | <span data-ttu-id="9a10d-116">Funcionan</span><span class="sxs-lookup"><span data-stu-id="9a10d-116">Functional</span></span>         | <span data-ttu-id="9a10d-117">Organización general</span><span class="sxs-lookup"><span data-stu-id="9a10d-117">Org - General</span></span>      | <span data-ttu-id="9a10d-118">Regulado por la organización</span><span class="sxs-lookup"><span data-stu-id="9a10d-118">Org - Regulated</span></span> | <span data-ttu-id="9a10d-119">Interceptación lícita</span><span class="sxs-lookup"><span data-stu-id="9a10d-119">Lawful Intercept</span></span>   |
| ---------------------- | ------------------ | ------------------ | ------------------ | --------------- | ------------------ |
| <span data-ttu-id="9a10d-120">Inició</span><span class="sxs-lookup"><span data-stu-id="9a10d-120">Initiator</span></span>              | <span data-ttu-id="9a10d-121">Usuario</span><span class="sxs-lookup"><span data-stu-id="9a10d-121">User</span></span>               | <span data-ttu-id="9a10d-122">Aplicación/solución</span><span class="sxs-lookup"><span data-stu-id="9a10d-122">App/Solution</span></span>       | <span data-ttu-id="9a10d-123">Administrador (sistema)</span><span class="sxs-lookup"><span data-stu-id="9a10d-123">Admin (system)</span></span>     | <span data-ttu-id="9a10d-124">Administrador (sistema)</span><span class="sxs-lookup"><span data-stu-id="9a10d-124">Admin (system)</span></span>  | <span data-ttu-id="9a10d-125">LEA</span><span class="sxs-lookup"><span data-stu-id="9a10d-125">LEA</span></span>                |
| <span data-ttu-id="9a10d-126">Target</span><span class="sxs-lookup"><span data-stu-id="9a10d-126">Target</span></span>                 | <span data-ttu-id="9a10d-127">Por llamada/reunión</span><span class="sxs-lookup"><span data-stu-id="9a10d-127">Per-call / meeting</span></span> | <span data-ttu-id="9a10d-128">Por llamada/reunión</span><span class="sxs-lookup"><span data-stu-id="9a10d-128">Per-call / meeting</span></span> | <span data-ttu-id="9a10d-129">Por llamada/reunión</span><span class="sxs-lookup"><span data-stu-id="9a10d-129">Per-call / meeting</span></span> | <span data-ttu-id="9a10d-130">Por usuario</span><span class="sxs-lookup"><span data-stu-id="9a10d-130">Per-user</span></span>        | <span data-ttu-id="9a10d-131">Por punto de conexión/ha</span><span class="sxs-lookup"><span data-stu-id="9a10d-131">Per-endpoint / DID</span></span> |
| <span data-ttu-id="9a10d-132">Propietario del almacenamiento</span><span class="sxs-lookup"><span data-stu-id="9a10d-132">Storage owner</span></span>          | <span data-ttu-id="9a10d-133">Usuario</span><span class="sxs-lookup"><span data-stu-id="9a10d-133">User</span></span>               | <span data-ttu-id="9a10d-134">Aplicación</span><span class="sxs-lookup"><span data-stu-id="9a10d-134">App</span></span>                | <span data-ttu-id="9a10d-135">Administrador</span><span class="sxs-lookup"><span data-stu-id="9a10d-135">Admin</span></span>              | <span data-ttu-id="9a10d-136">Cumplimiento</span><span class="sxs-lookup"><span data-stu-id="9a10d-136">Compliance</span></span>      | <span data-ttu-id="9a10d-137">LEA</span><span class="sxs-lookup"><span data-stu-id="9a10d-137">LEA</span></span>                |
| <span data-ttu-id="9a10d-138">¿Se requiere notificación?</span><span class="sxs-lookup"><span data-stu-id="9a10d-138">Notification required?</span></span> | <span data-ttu-id="9a10d-139">Sí</span><span class="sxs-lookup"><span data-stu-id="9a10d-139">Yes</span></span>                | <span data-ttu-id="9a10d-140">Sí</span><span class="sxs-lookup"><span data-stu-id="9a10d-140">Yes</span></span>                | <span data-ttu-id="9a10d-141">Sí</span><span class="sxs-lookup"><span data-stu-id="9a10d-141">Yes</span></span>                | <span data-ttu-id="9a10d-142">Sí</span><span class="sxs-lookup"><span data-stu-id="9a10d-142">Yes</span></span>             | <span data-ttu-id="9a10d-143">No</span><span class="sxs-lookup"><span data-stu-id="9a10d-143">No</span></span>                 |
| <span data-ttu-id="9a10d-144">Propietario de acceso</span><span class="sxs-lookup"><span data-stu-id="9a10d-144">Access Owner</span></span>           | <span data-ttu-id="9a10d-145">Usuario</span><span class="sxs-lookup"><span data-stu-id="9a10d-145">User</span></span>               | <span data-ttu-id="9a10d-146">Aplicación</span><span class="sxs-lookup"><span data-stu-id="9a10d-146">App</span></span>                | <span data-ttu-id="9a10d-147">Administrador</span><span class="sxs-lookup"><span data-stu-id="9a10d-147">Admin</span></span>              | <span data-ttu-id="9a10d-148">Cumplimiento</span><span class="sxs-lookup"><span data-stu-id="9a10d-148">Compliance</span></span>      | <span data-ttu-id="9a10d-149">LEA</span><span class="sxs-lookup"><span data-stu-id="9a10d-149">LEA</span></span>                |
| <span data-ttu-id="9a10d-150">¿Directiva de retención?</span><span class="sxs-lookup"><span data-stu-id="9a10d-150">Retention Policy?</span></span>      | <span data-ttu-id="9a10d-151">Opcional</span><span class="sxs-lookup"><span data-stu-id="9a10d-151">Optional</span></span>           | <span data-ttu-id="9a10d-152">Sí</span><span class="sxs-lookup"><span data-stu-id="9a10d-152">Yes</span></span>                | <span data-ttu-id="9a10d-153">Sí</span><span class="sxs-lookup"><span data-stu-id="9a10d-153">Yes</span></span>                | <span data-ttu-id="9a10d-154">Sí</span><span class="sxs-lookup"><span data-stu-id="9a10d-154">Yes</span></span>             | <span data-ttu-id="9a10d-155">Sí</span><span class="sxs-lookup"><span data-stu-id="9a10d-155">Yes</span></span>                |

<span data-ttu-id="9a10d-156">Teams proporciona diversas funciones para la grabación [<span class="underline">cómoda</span>](https://docs.microsoft.com/microsoftteams/cloud-recording) y funcional de reuniones y eventos en directo.</span><span class="sxs-lookup"><span data-stu-id="9a10d-156">Teams provides various capabilities for [<span class="underline">convenient</span>](https://docs.microsoft.com/microsoftteams/cloud-recording) and functional recording for meetings and live events.</span></span> <span data-ttu-id="9a10d-157">La grabación organizacional significa permitir a las organizaciones que adoptan equipos de llamadas y reuniones establecerse, a través de una directiva administrativa, cuando las llamadas y las reuniones en línea deben grabarse y capturarse de forma automática para su procesamiento y retención posterior, según lo requiera la política corporativa o normativa pertinente.</span><span class="sxs-lookup"><span data-stu-id="9a10d-157">Organizational recording means enabling organizations adopting Teams for calling and meetings to stipulate, by way of an administrative policy, when calls and online meetings should be automatically recorded and captured for subsequent processing and retention as required by relevant corporate or regulatory policy.</span></span> <span data-ttu-id="9a10d-158">Los usuarios de esta Directiva serán conscientes de que sus interacciones digitales con equipos se graban, pero no podrán deshabilitar la grabación y no tendrán acceso a la grabación una vez completada la interacción.</span><span class="sxs-lookup"><span data-stu-id="9a10d-158">Users under this policy will be aware that their digital interactions with Teams are being recorded but will not be able to disable the recording and will not have access to the recording once the interaction is complete.</span></span> <span data-ttu-id="9a10d-159">La grabación se convierte en parte del archivo organizativo disponible para el cumplimiento y el personal legal de eDiscovery, la retención legal y otros usos de la retención corporativa.</span><span class="sxs-lookup"><span data-stu-id="9a10d-159">The recording becomes part of the organizational archive available to compliance and legal personnel for eDiscovery, legal hold, and other corporate retention uses.</span></span>

## <a name="example-user-needs"></a><span data-ttu-id="9a10d-160">Necesidades de usuario de ejemplo</span><span class="sxs-lookup"><span data-stu-id="9a10d-160">Example user needs</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="9a10d-161"><strong>Rol</strong></span><span class="sxs-lookup"><span data-stu-id="9a10d-161"><strong>Persona</strong></span></span></th>
<th><span data-ttu-id="9a10d-162"><strong>Necesaria</strong></span><span class="sxs-lookup"><span data-stu-id="9a10d-162"><strong>Needs</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="9a10d-163">Usuarios grabados</span><span class="sxs-lookup"><span data-stu-id="9a10d-163">Recorded users</span></span></td>
<td><ul>
<li><p><span data-ttu-id="9a10d-164">Recibir una notificación cuando la grabación esté en curso.</span><span class="sxs-lookup"><span data-stu-id="9a10d-164">Be notified when recording is in progress.</span></span></p></li>
<li><p><span data-ttu-id="9a10d-165">Informarse cuando el error de la Directiva o de la grabadora provoca cambios en el comportamiento de la llamada.</span><span class="sxs-lookup"><span data-stu-id="9a10d-165">Be informed when policy and/or recorder error is causing changes in calling behavior.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="9a10d-166">Administrador de comunicaciones</span><span class="sxs-lookup"><span data-stu-id="9a10d-166">Communications admin</span></span></td>
<td><ul>
<li><p><span data-ttu-id="9a10d-167">Comprender por qué y cómo aplicar o exigir directivas de registro a usuarios y puntos de conexión de Teams.</span><span class="sxs-lookup"><span data-stu-id="9a10d-167">Understand why and how to apply / enforce recording policies to Teams users / endpoints.</span></span></p></li>
<li><p><span data-ttu-id="9a10d-168">Configurar y mantener directivas de grabación de Teams para la organización.</span><span class="sxs-lookup"><span data-stu-id="9a10d-168">Configure and maintain Teams recording policies for the organization.</span></span></p></li>
<li><p><span data-ttu-id="9a10d-169">Supervisar y solucionar problemas relacionados con el registro con llamadas y reuniones de Teams.</span><span class="sxs-lookup"><span data-stu-id="9a10d-169">Monitor and troubleshoot recording-related issues with Teams calls and meetings.</span></span></p></li>
<li><p><span data-ttu-id="9a10d-170">Apoyar al funcionario de cumplimiento interno con análisis operacional sobre el uso, la calidad y la confiabilidad.</span><span class="sxs-lookup"><span data-stu-id="9a10d-170">Support internal compliance officer with operational analytics on usage, quality, and reliability.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="9a10d-171">Funcionario encargado del cumplimiento</span><span class="sxs-lookup"><span data-stu-id="9a10d-171">Compliance officer</span></span></td>
<td><ul>
<li><p><span data-ttu-id="9a10d-172">Recopilar todas las comunicaciones de Teams de la forma requerida para cumplir con las obligaciones reglamentarias vigentes.</span><span class="sxs-lookup"><span data-stu-id="9a10d-172">Collect all Teams communications in the manner required to meet compliance obligations in appropriate regional boundaries.</span></span></p></li>
<li><p><span data-ttu-id="9a10d-173">Buscar interacciones en función de metadatos relacionados con la comunicación o contenido de interacción.</span><span class="sxs-lookup"><span data-stu-id="9a10d-173">Search for interactions based on communication-related metadata or interaction content.</span></span> <span data-ttu-id="9a10d-174">Algunos ejemplos comunes son:</span><span class="sxs-lookup"><span data-stu-id="9a10d-174">Common examples include:</span></span></p>
<ul>
<li><p><span data-ttu-id="9a10d-175"><strong>Metadatos</strong> - Participantes, hora, dirección, número marcado, número de origen, datos profesionales personalizados</span><span class="sxs-lookup"><span data-stu-id="9a10d-175"><strong>Metadata</strong> - Participants, time, direction, dialed number, origin number, Custom business data</span></span></p></li>
<li><p><span data-ttu-id="9a10d-176"><strong>Contenido</strong> : transcripción, sentimientos, fonética, interacciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="9a10d-176"><strong>Content</strong> – Transcription, sentiment, phonetics, related interactions</span></span></p></li>
</ul></li>
<li><p><span data-ttu-id="9a10d-177">Analizar e interactuar con las comunicaciones recopiladas, incluida la capacidad de supervisar las interacciones a medida que se recopilan.</span><span class="sxs-lookup"><span data-stu-id="9a10d-177">Analyze and interact with collected communications, including the ability to monitor interactions as they are being collected.</span></span></p></li>
<li><p><span data-ttu-id="9a10d-178">Garantizar la seguridad de las comunicaciones recopiladas e impedir alteraciones en todas las etapas.</span><span class="sxs-lookup"><span data-stu-id="9a10d-178">Ensure security of collected communications and prevent tampering at all stages.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="solution-architecture-overview"></a><span data-ttu-id="9a10d-179">Descripción general de la arquitectura de soluciones</span><span class="sxs-lookup"><span data-stu-id="9a10d-179">Solution architecture overview</span></span>

<span data-ttu-id="9a10d-180">Las soluciones de grabación de cumplimiento están integradas con Teams, tal y como se muestra en el siguiente diagrama:</span><span class="sxs-lookup"><span data-stu-id="9a10d-180">Compliance recording solutions are integrated with Teams as shown in the following diagram:</span></span>

<span data-ttu-id="9a10d-181">![Captura de pantalla que muestra la configuración de la aplicación personalizada del equipo](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "Las imágenes muestran el flujo cuando se envía y recibe una llamada o una reunión de Teams.")</span><span class="sxs-lookup"><span data-stu-id="9a10d-181">![Screenshot showing the team custom app setting](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "The images shows the flow when a Teams meeting or call is sent and received.")</span></span>

## <a name="recorder"></a><span data-ttu-id="9a10d-182">Magnetoscopio</span><span class="sxs-lookup"><span data-stu-id="9a10d-182">Recorder</span></span>

<span data-ttu-id="9a10d-183">El componente principal de la solución de grabación de cumplimiento es el grabador.</span><span class="sxs-lookup"><span data-stu-id="9a10d-183">The core component of the compliance recording solution is the recorder.</span></span>
<span data-ttu-id="9a10d-184">Los grabadores se crean como servicios escalables basados en Azure (bots) que [<span class="underline">aprovechan la plataforma de comunicaciones de Microsoft</span>](https://docs.microsoft.com/graph/cloud-communications-concept-overview) y se registran como aplicaciones con Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="9a10d-184">Recorders are built as scalable Azure-based services (bots) that [<span class="underline">leverage Microsoft’s communications platform</span>](https://docs.microsoft.com/graph/cloud-communications-concept-overview) and register as applications with Microsoft Graph.</span></span> <span data-ttu-id="9a10d-185">La grabadora proporciona la interacción directa con las API de la [<span class="underline">plataforma de comunicaciones</span>](https://docs.microsoft.com/graph/api/resources/communications-api-overview?view=graph-rest-1.0) de las llamadas y reuniones de Teams y proporciona el punto final para la recopilación de medios.</span><span class="sxs-lookup"><span data-stu-id="9a10d-185">The recorder provides the direct interaction with the Teams calls and meetings [<span class="underline">communications platform APIs</span>](https://docs.microsoft.com/graph/api/resources/communications-api-overview?view=graph-rest-1.0) and provides the endpoint for media ingestion.</span></span>

<span data-ttu-id="9a10d-186">[<span class="underline">Hay disponible una aplicación de grabadora de cumplimiento de ejemplo</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) que muestra cómo configurar el bot, crear la instancia de la aplicación y asignar las directivas de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="9a10d-186">A [<span class="underline">sample compliance recorder application is available</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) that shows how to configure the bot, create the app instance and assign the compliance policies.</span></span> <span data-ttu-id="9a10d-187">El ejemplo también tiene ejemplos sobre el uso de la API para registrar interacciones específicas, como el control del enrutamiento de [<span class="underline">llamadas entrantes</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244) , el [<span class="underline">cambio de Estados de grabación</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138)y [<span class="underline">la eliminación del usuario que se está grabando</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126).</span><span class="sxs-lookup"><span data-stu-id="9a10d-187">The sample also has examples on API usage for recording specific interactions such as handling [<span class="underline">incoming call</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244) routing, [<span class="underline">changing recording states</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138), and [<span class="underline">removing the user who is being recorded</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126).</span></span>
<span data-ttu-id="9a10d-188">La documentación de Graph en las API específicas se puede encontrar aquí para [<span class="underline">updateRecordingStatus</span>](https://docs.microsoft.com/graph/api/call-updaterecordingstatus?view=graph-rest-1.0&tabs=http) y [<span class="underline">incomingContext</span>](https://docs.microsoft.com/graph/api/resources/incomingcontext?view=graph-rest-1.0).</span><span class="sxs-lookup"><span data-stu-id="9a10d-188">Graph documentation on the specific APIs can be found here for [<span class="underline">updateRecordingStatus</span>](https://docs.microsoft.com/graph/api/call-updaterecordingstatus?view=graph-rest-1.0&tabs=http) and [<span class="underline">incomingContext</span>](https://docs.microsoft.com/graph/api/resources/incomingcontext?view=graph-rest-1.0).</span></span>

<span data-ttu-id="9a10d-189">La implementación exacta del servicio de grabadora varía según el socio, pero debe estar diseñada para admitir varios registros a fin de lograr una alta disponibilidad y una distribución geográfica de la implementación a fin de reducir la latencia de los equipos a la grabadora.</span><span class="sxs-lookup"><span data-stu-id="9a10d-189">The exact implementation of the recorder service will vary by partner but must be designed to support multiple recorders in order to achieve high availability and geographical distribution of deployment to reduce latency from Teams to the recorder.</span></span> <span data-ttu-id="9a10d-190">Además, se espera que los grabadores se diseñen con la resistencia y la redundancia en mente.</span><span class="sxs-lookup"><span data-stu-id="9a10d-190">In addition, it is expected that Recorders themselves be designed with resiliency and redundancy in mind.</span></span>

<span data-ttu-id="9a10d-191">Los socios deben confirmar la versión de lanzamiento mínima requerida de las API y SDK de comunicaciones de Microsoft Graph con Microsoft antes de enviar su solución de certificación para garantizar que se admitan todos los requisitos de integración de grabaciones de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="9a10d-191">Partners must confirm the minimum required release version of the Microsoft Graph communications APIs and SDKs with Microsoft before submitting their solution for certification to ensure that all requirements of compliance recording integration are supported.</span></span>

<span data-ttu-id="9a10d-192">Dos requisitos específicos fundamentales para el escenario de grabación de cumplimiento son:</span><span class="sxs-lookup"><span data-stu-id="9a10d-192">Two specific requirements that are fundamental for compliance recording scenario are:</span></span>

- <span data-ttu-id="9a10d-193">El bot de grabadora debe implementarse en Azure</span><span class="sxs-lookup"><span data-stu-id="9a10d-193">Recorder bot must be deployed in Azure</span></span>

- <span data-ttu-id="9a10d-194">El bot de grabadora debe ejecutarse en una VM de Windows en Azure</span><span class="sxs-lookup"><span data-stu-id="9a10d-194">Recorder bot must run on a Windows VM in Azure</span></span>

<span data-ttu-id="9a10d-195">Los requisitos de Windows VM de Azure y Windows solo se aplican al componente bot de Teams, lo que significa que un asociado puede implementar el resto de la plataforma de su elección, siempre y cuando cumplan con los requisitos de rendimiento y funcionales pertinentes para la grabación de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="9a10d-195">The Azure and Windows VM requirements only apply to the Teams Bot component, which means that a partner may implement the rest of the platform of their choice provided they can meet the relevant performance and functional requirements for compliance recording.</span></span>

## <a name="compliance-recording-policy-assignment-and-provisioning"></a><span data-ttu-id="9a10d-196">Aprovisionamiento y asignación de directivas de grabación de cumplimiento normativo</span><span class="sxs-lookup"><span data-stu-id="9a10d-196">Compliance recording policy assignment and provisioning</span></span>

<span data-ttu-id="9a10d-197">Los administradores de TI pueden determinar qué usuarios se grabarán y qué grabadora se usará para cada usuario mediante la creación y asignación de directivas de grabación de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="9a10d-197">IT Administrators can determine which users are to be recorded and which recorder will be used for each user, by creating and assigning compliance recording policies.</span></span> <span data-ttu-id="9a10d-198">Los grabadores se invitan automáticamente a participar en las conversaciones basándose en la configuración de estas directivas cuando tiene lugar una interacción de comunicación.</span><span class="sxs-lookup"><span data-stu-id="9a10d-198">Recorders are automatically invited to participate in conversations based on the configuration of these policies when a communication interaction takes place.</span></span> <span data-ttu-id="9a10d-199">Las directivas de grabación de cumplimiento se administran con [<span class="underline">Microsoft PowerShell</span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview) y se pueden aplicar a nivel de inquilino, por usuario y de seguridad para cada organización.</span><span class="sxs-lookup"><span data-stu-id="9a10d-199">Compliance recording policies are managed using [<span class="underline">Microsoft Powershell</span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview) and can be applied at the tenant, per-user, and security group level for each organization.</span></span> <span data-ttu-id="9a10d-200">Puede encontrar más información sobre [<span class="underline">las directivas de reunión</span>](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams), [<span class="underline">las directivas de llamada</span>](https://docs.microsoft.com/microsoftteams/teams-calling-policy) y las directivas de  [<span class="underline">Grupo</span>](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-group)en Microsoft docs.</span><span class="sxs-lookup"><span data-stu-id="9a10d-200">You can find more information on Microsoft Docs for [<span class="underline">Meeting policies</span>](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams), [<span class="underline">calling policies</span>](https://docs.microsoft.com/microsoftteams/teams-calling-policy) and  [<span class="underline">group policies</span>](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-group).</span></span>

1. <span data-ttu-id="9a10d-201">Cree una instancia de la aplicación en su espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="9a10d-201">Create an application instance in your tenant.</span></span>

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

2. <span data-ttu-id="9a10d-202">Crear una directiva de grabación de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="9a10d-202">Create a Compliance Recording policy.</span></span>

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

   [<span data-ttu-id="9a10d-203"><span class="underline">Set-CsTeamsComplianceRecordingPolicy</span></span><span class="sxs-lookup"><span data-stu-id="9a10d-203"><span class="underline">Set-CsTeamsComplianceRecordingPolicy</span></span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamscompliancerecordingpolicy?view=skype-ps)

3. <span data-ttu-id="9a10d-204">Asignar la Directiva de grabación de cumplimiento a un usuario.</span><span class="sxs-lookup"><span data-stu-id="9a10d-204">Assign the Compliance Recording policy to a user.</span></span>

   ```powershell
   PS C:\> Grant-CsTeamsComplianceRecordingPolicy -Identity testuser@contoso.onmicrosoft.com -PolicyName TestComplianceRecordingPolicy
   ```

   [<span data-ttu-id="9a10d-205"><span class="underline">Grant-CsTeamsComplianceRecordingPolicy</span></span><span class="sxs-lookup"><span data-stu-id="9a10d-205"><span class="underline">Grant-CsTeamsComplianceRecordingPolicy</span></span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamscompliancerecordingpolicy?view=skype-ps)

   ```powershell
   PS C:\> Get-CsOnlineUser testuser@contoso.onmicrosoft.com | select SipAddress, TenantId, TeamsComplianceRecordingPolicy | fl

   UserPrincipalName              : testuser@contoso.onmicrosoft.com
   TenantId                       : 5b943d7c-5e14-474b-8237-5022eb8e0dc9
   TeamsComplianceRecordingPolicy : TestComplianceRecordingPolicy
   ```

## <a name="user-experiences"></a><span data-ttu-id="9a10d-206">Experiencias de usuario</span><span class="sxs-lookup"><span data-stu-id="9a10d-206">User experiences</span></span>

<span data-ttu-id="9a10d-207">La compatibilidad con las notificaciones se habilita con las experiencias del cliente de Teams.</span><span class="sxs-lookup"><span data-stu-id="9a10d-207">Support for notifications is enabled using the Teams client experiences.</span></span> <span data-ttu-id="9a10d-208">Las experiencias pueden ser visuales o de audio.</span><span class="sxs-lookup"><span data-stu-id="9a10d-208">The experiences can be either visual or audio.</span></span>

<span data-ttu-id="9a10d-209">**Clientes de Teams: aviso visual**</span><span class="sxs-lookup"><span data-stu-id="9a10d-209">**Teams clients - visual notice**</span></span>
- <span data-ttu-id="9a10d-210">Escritorio/web</span><span class="sxs-lookup"><span data-stu-id="9a10d-210">Desktop/web</span></span>
- <span data-ttu-id="9a10d-211">Móvil (iOS/Android)</span><span class="sxs-lookup"><span data-stu-id="9a10d-211">Mobile (iOS/Android)</span></span>
- <span data-ttu-id="9a10d-212">Teléfonos de equipos</span><span class="sxs-lookup"><span data-stu-id="9a10d-212">Teams phones</span></span>
- <span data-ttu-id="9a10d-213">Salas de equipos</span><span class="sxs-lookup"><span data-stu-id="9a10d-213">Teams rooms</span></span>

<span data-ttu-id="9a10d-214">**Otros puntos de conexión-aviso de audio**</span><span class="sxs-lookup"><span data-stu-id="9a10d-214">**Other endpoints - audio notice**</span></span>
- <span data-ttu-id="9a10d-215">Teléfonos SIP</span><span class="sxs-lookup"><span data-stu-id="9a10d-215">SIP phones</span></span>
- <span data-ttu-id="9a10d-216">Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="9a10d-216">Skype for Business</span></span>
- <span data-ttu-id="9a10d-217">Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="9a10d-217">Audio conferencing</span></span>
- <span data-ttu-id="9a10d-218">Autores de llamadas RTC</span><span class="sxs-lookup"><span data-stu-id="9a10d-218">PSTN callers</span></span>

## <a name="compliance-recording-for-teams-certification-programs"></a><span data-ttu-id="9a10d-219">Grabación de cumplimiento para los programas de certificación de Teams</span><span class="sxs-lookup"><span data-stu-id="9a10d-219">Compliance recording for Teams certification programs</span></span>

<span data-ttu-id="9a10d-220">Además de publicar API disponibles públicamente para que los socios puedan desarrollar e integrar soluciones de CCaaS con Teams, hemos desarrollado el programa de certificación de la grabación de cumplimiento para Microsoft Teams a fin de proporcionar a los clientes la seguridad de que la solución de cada socio participante ha sido probada y verificada para proporcionar la calidad, la compatibilidad y la confiabilidad que esperan de las soluciones de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9a10d-220">In addition to publishing publicly-available APIs allowing partners to develop and integrate CCaaS solutions with Teams, we have developed the compliance recording for Microsoft Teams certification program to provide customers with the assurance that each participating partner’s solution has been tested and verified to provide the quality, compatibility and reliability they expect from Microsoft solutions.</span></span>  

<span data-ttu-id="9a10d-221">Los siguientes socios están en el proceso de certificar su solución para Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9a10d-221">The following partners are in the process of certifying their solution for Microsoft Teams.</span></span>

|<span data-ttu-id="9a10d-222">Servidor</span><span class="sxs-lookup"><span data-stu-id="9a10d-222">Partner</span></span>|<span data-ttu-id="9a10d-223">Sitio web de soluciones</span><span class="sxs-lookup"><span data-stu-id="9a10d-223">Solution website</span></span> |
|:--|:--|
|<span data-ttu-id="9a10d-224">Tecnologías ASC</span><span class="sxs-lookup"><span data-stu-id="9a10d-224">ASC Technologies</span></span> |[https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html](https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html) |
|<span data-ttu-id="9a10d-225">AudioCodes</span><span class="sxs-lookup"><span data-stu-id="9a10d-225">AudioCodes</span></span> |[https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/smarttap-360-recording](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/smarttap-360-recording) |
|<span data-ttu-id="9a10d-226">CallCabinet</span><span class="sxs-lookup"><span data-stu-id="9a10d-226">CallCabinet</span></span> |[https://www.callcabinet.com/compliance-microsoft-teams-call-recording](https://www.callcabinet.com/compliance-microsoft-teams-call-recording ) |
|<span data-ttu-id="9a10d-227">Un doblador</span><span class="sxs-lookup"><span data-stu-id="9a10d-227">Dubber</span></span> |[https://www.dubber.net/call-recording/](https://www.dubber.net/call-recording/) |
|<span data-ttu-id="9a10d-228">Tecnologías de Landis</span><span class="sxs-lookup"><span data-stu-id="9a10d-228">Landis Technologies</span></span> |[https://landistechnologies.com/](https://landistechnologies.com/) |
|<span data-ttu-id="9a10d-229">Luware</span><span class="sxs-lookup"><span data-stu-id="9a10d-229">Luware</span></span> |[https://luware.com/en/solution/microsoft-teams-recording/](https://luware.com/en/solution/microsoft-teams-recording/) |
|<span data-ttu-id="9a10d-230">ALINEA</span><span class="sxs-lookup"><span data-stu-id="9a10d-230">NICE</span></span> |[https://www.niceactimize.com/compliance/ms-teams-recording.html](https://www.niceactimize.com/compliance/ms-teams-recording.html) |
|<span data-ttu-id="9a10d-231">Numonix</span><span class="sxs-lookup"><span data-stu-id="9a10d-231">Numonix</span></span> |[https://numonix.cloud](https://numonix.cloud)    |
|<span data-ttu-id="9a10d-232">Innovación en roble</span><span class="sxs-lookup"><span data-stu-id="9a10d-232">Oak Innovation</span></span> |[https://www.oakinnovate.com/call-recording](https://www.oakinnovate.com/call-recording) |
|<span data-ttu-id="9a10d-233">Cuadro rojo</span><span class="sxs-lookup"><span data-stu-id="9a10d-233">Red Box</span></span> |[https://www.redboxvoice.com/compliance-recording-for-microsoft-teams](https://www.redboxvoice.com/compliance-recording-for-microsoft-teams)  |
|<span data-ttu-id="9a10d-234">Verint</span><span class="sxs-lookup"><span data-stu-id="9a10d-234">Verint</span></span> |[https://www.verba.com/solutions/microsoft-teams-recording](https://www.verba.com/solutions/microsoft-teams-recording) |

<span data-ttu-id="9a10d-235">Esta lista se actualizará a medida que se unan más socios y cumplan los criterios de certificación.</span><span class="sxs-lookup"><span data-stu-id="9a10d-235">This list will be updated as more partners join and meet the certification criteria.</span></span>

## <a name="next-steps"></a><span data-ttu-id="9a10d-236">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="9a10d-236">Next steps</span></span>

<span data-ttu-id="9a10d-237">Si eres un proveedor y deseas participar en el programa de certificación, envía un mensaje de correo  <a href= "mailto:Teamscategorypartner@microsoft.com">Teamscategorypartner@microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="9a10d-237">If you are a vendor seeking to join the certification program, please mail  <a href= "mailto:Teamscategorypartner@microsoft.com">Teamscategorypartner@microsoft.com</a>.</span></span>
