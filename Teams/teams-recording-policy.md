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
ms.openlocfilehash: 9a7a40a4f7e99f79f67c0aaea0e5259652b5a8d8
ms.sourcegitcommit: ee217e1d7188842c7becd19387fd421b485c3575
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2020
ms.locfileid: "48908579"
---
# <a name="introduction-to-teams-policy-based-recording-for-callings--meetings"></a><span data-ttu-id="06988-103">Introducción a la grabación basada en directivas de Teams para realizar llamadas & reuniones</span><span class="sxs-lookup"><span data-stu-id="06988-103">Introduction to Teams policy-based recording for callings & meetings</span></span>

<span data-ttu-id="06988-104">La grabación basada en directivas permite a las organizaciones que adoptan Microsoft Teams las llamadas y reuniones que estipulan, mediante una directiva administrativa, cuando las llamadas y las reuniones en línea deben grabarse y capturarse automáticamente para su procesamiento y retención posterior, según lo requiera la política corporativa o normativa pertinente.</span><span class="sxs-lookup"><span data-stu-id="06988-104">Policy-based recording enables organizations that adopt Microsoft Teams for calling and meetings to stipulate, using an administrative policy, when calls and online meetings should be automatically recorded and captured for subsequent processing and retention as required by relevant corporate or regulatory policy.</span></span>

<span data-ttu-id="06988-105">Teams ha sido mejorado para admitir la integración de soluciones de grabación de terceros, entre las que se incluyen la funcionalidad de plataforma, las experiencias de usuario y las interfaces administrativas necesarias para proporcionar una solución completa para configurar, administrar, registrar, almacenar y analizar comunicaciones de Teams.</span><span class="sxs-lookup"><span data-stu-id="06988-105">Teams has been enhanced to support integration of third-party recording solutions, including the platform functionality, user experiences, and administrative interfaces needed to provide an end-to-end solution for configuring, managing, recording, storing, and analyzing Teams communications.</span></span> <span data-ttu-id="06988-106">Esto incluye las API y eventos de la plataforma de comunicaciones para la grabación, que ofrece:</span><span class="sxs-lookup"><span data-stu-id="06988-106">This includes communications platform APIs and events for recording, which provides:</span></span>

- <span data-ttu-id="06988-107">Captura multimedia sin problemas y de alta calidad en todos los dispositivos y todos los puntos de conexión compatibles con audio, vídeo, pantalla compartida y chat.</span><span class="sxs-lookup"><span data-stu-id="06988-107">Seamless, high-quality media capture across devices and all   supported endpoints for audio, video, screen share, and chat.</span></span>

- <span data-ttu-id="06988-108">Compatibilidad con la captura de interacción entre usuarios de equipos y puntos de conexión de llamadas compatibles (equipos, equipos móviles, Skype empresarial, RTC)</span><span class="sxs-lookup"><span data-stu-id="06988-108">Support for interaction capture between Teams users and supported   calling endpoints (Teams, Teams Mobile, Skype for Business, PSTN)</span></span>

- <span data-ttu-id="06988-109">Nuevas directivas administrativas para la grabación de cumplimiento, incluida la integración con las herramientas y políticas de reuniones y herramientas administrativas existentes de Teams</span><span class="sxs-lookup"><span data-stu-id="06988-109">New administrative policies for compliance recording, including   integration with existing Teams administrative calling and   meeting tools and policies</span></span>

<span data-ttu-id="06988-110">La grabación de cumplimiento puede habilitarse en los usuarios de Microsoft 365 A3/A5/E3/E5 y Office 365 A3/A5/E3/E5.</span><span class="sxs-lookup"><span data-stu-id="06988-110">Compliance Recording can be enabled on Microsoft 365 A3/A5/E3/E5 and Office 365 A3/A5/E3/E5 users.</span></span> 

<span data-ttu-id="06988-111">Las capacidades de integración de soluciones de grabación de cumplimiento también fueron revisadas en el encendido 2019 de la [<span class="underline">sesión de cumplimiento y Microsoft Teams</span>](https://myignite.techcommunity.microsoft.com/sessions/83184?source=sessions).</span><span class="sxs-lookup"><span data-stu-id="06988-111">The compliance recording solution integration capabilities were also reviewed at Ignite 2019 in the [<span class="underline">Compliance Recording and Microsoft Teams session</span>](https://myignite.techcommunity.microsoft.com/sessions/83184?source=sessions).</span></span>

## <a name="teams-interaction-recording-overview"></a><span data-ttu-id="06988-112">Introducción a la grabación de interacción de Teams</span><span class="sxs-lookup"><span data-stu-id="06988-112">Teams interaction recording overview</span></span>

<span data-ttu-id="06988-113">Los casos de uso de grabación de interacción pueden dividirse en cuatro categorías principales de funcionalidad de grabación: conveniencia, funcional, organizacional e intercepta legal, tal y como se muestra en la imagen:</span><span class="sxs-lookup"><span data-stu-id="06988-113">Interaction recording use cases can effectively be separated into four primary categories of recording functionality – Convenience, Functional, Organizational, and Lawful Intercept, as shown in the image:</span></span>

<span data-ttu-id="06988-114">![Captura de pantalla que muestra la interacción que registra qué es y por qué.](media/recording-taxonomy.png "La imagen muestra las categorías de grabación.")</span><span class="sxs-lookup"><span data-stu-id="06988-114">![Screenshot showing the interaction recording what and why.](media/recording-taxonomy.png "The image shows the recording categories.")</span></span>

<span data-ttu-id="06988-115">Cada una de las categorías conlleva diferentes requisitos sobre cómo se inician las grabaciones, qué se graba, dónde se almacenan las grabaciones, a quién se notifica, quién controla Access y cómo se administra la retención.</span><span class="sxs-lookup"><span data-stu-id="06988-115">Each of the categories entails different requirements for how recordings are initiated, what is recorded, where recordings are stored, who is notified, who controls access, and how retention is handled.</span></span>

| <span data-ttu-id="06988-116">Tipo</span><span class="sxs-lookup"><span data-stu-id="06988-116">Type</span></span>                   | <span data-ttu-id="06988-117">Prácticos</span><span class="sxs-lookup"><span data-stu-id="06988-117">Convenience</span></span>        | <span data-ttu-id="06988-118">Funcionan</span><span class="sxs-lookup"><span data-stu-id="06988-118">Functional</span></span>         | <span data-ttu-id="06988-119">Organización general</span><span class="sxs-lookup"><span data-stu-id="06988-119">Org - General</span></span>      | <span data-ttu-id="06988-120">Regulado por la organización</span><span class="sxs-lookup"><span data-stu-id="06988-120">Org - Regulated</span></span> | <span data-ttu-id="06988-121">Interceptación lícita</span><span class="sxs-lookup"><span data-stu-id="06988-121">Lawful Intercept</span></span>   |
| ---------------------- | ------------------ | ------------------ | ------------------ | --------------- | ------------------ |
| <span data-ttu-id="06988-122">Inició</span><span class="sxs-lookup"><span data-stu-id="06988-122">Initiator</span></span>              | <span data-ttu-id="06988-123">Usuario</span><span class="sxs-lookup"><span data-stu-id="06988-123">User</span></span>               | <span data-ttu-id="06988-124">Aplicación/solución</span><span class="sxs-lookup"><span data-stu-id="06988-124">App/Solution</span></span>       | <span data-ttu-id="06988-125">Administrador (sistema)</span><span class="sxs-lookup"><span data-stu-id="06988-125">Admin (system)</span></span>     | <span data-ttu-id="06988-126">Administrador (sistema)</span><span class="sxs-lookup"><span data-stu-id="06988-126">Admin (system)</span></span>  | <span data-ttu-id="06988-127">LEA</span><span class="sxs-lookup"><span data-stu-id="06988-127">LEA</span></span>                |
| <span data-ttu-id="06988-128">Target</span><span class="sxs-lookup"><span data-stu-id="06988-128">Target</span></span>                 | <span data-ttu-id="06988-129">Por llamada/reunión</span><span class="sxs-lookup"><span data-stu-id="06988-129">Per-call / meeting</span></span> | <span data-ttu-id="06988-130">Por llamada/reunión</span><span class="sxs-lookup"><span data-stu-id="06988-130">Per-call / meeting</span></span> | <span data-ttu-id="06988-131">Por llamada/reunión</span><span class="sxs-lookup"><span data-stu-id="06988-131">Per-call / meeting</span></span> | <span data-ttu-id="06988-132">Por usuario</span><span class="sxs-lookup"><span data-stu-id="06988-132">Per-user</span></span>        | <span data-ttu-id="06988-133">Por punto de conexión/ha</span><span class="sxs-lookup"><span data-stu-id="06988-133">Per-endpoint / DID</span></span> |
| <span data-ttu-id="06988-134">Propietario del almacenamiento</span><span class="sxs-lookup"><span data-stu-id="06988-134">Storage owner</span></span>          | <span data-ttu-id="06988-135">Usuario</span><span class="sxs-lookup"><span data-stu-id="06988-135">User</span></span>               | <span data-ttu-id="06988-136">Aplicación</span><span class="sxs-lookup"><span data-stu-id="06988-136">App</span></span>                | <span data-ttu-id="06988-137">Administrador</span><span class="sxs-lookup"><span data-stu-id="06988-137">Admin</span></span>              | <span data-ttu-id="06988-138">Cumplimiento</span><span class="sxs-lookup"><span data-stu-id="06988-138">Compliance</span></span>      | <span data-ttu-id="06988-139">LEA</span><span class="sxs-lookup"><span data-stu-id="06988-139">LEA</span></span>                |
| <span data-ttu-id="06988-140">¿Se requiere notificación?</span><span class="sxs-lookup"><span data-stu-id="06988-140">Notification required?</span></span> | <span data-ttu-id="06988-141">Sí</span><span class="sxs-lookup"><span data-stu-id="06988-141">Yes</span></span>                | <span data-ttu-id="06988-142">Sí</span><span class="sxs-lookup"><span data-stu-id="06988-142">Yes</span></span>                | <span data-ttu-id="06988-143">Sí</span><span class="sxs-lookup"><span data-stu-id="06988-143">Yes</span></span>                | <span data-ttu-id="06988-144">Sí</span><span class="sxs-lookup"><span data-stu-id="06988-144">Yes</span></span>             | <span data-ttu-id="06988-145">No</span><span class="sxs-lookup"><span data-stu-id="06988-145">No</span></span>                 |
| <span data-ttu-id="06988-146">Propietario de acceso</span><span class="sxs-lookup"><span data-stu-id="06988-146">Access Owner</span></span>           | <span data-ttu-id="06988-147">Usuario</span><span class="sxs-lookup"><span data-stu-id="06988-147">User</span></span>               | <span data-ttu-id="06988-148">Aplicación</span><span class="sxs-lookup"><span data-stu-id="06988-148">App</span></span>                | <span data-ttu-id="06988-149">Administrador</span><span class="sxs-lookup"><span data-stu-id="06988-149">Admin</span></span>              | <span data-ttu-id="06988-150">Cumplimiento</span><span class="sxs-lookup"><span data-stu-id="06988-150">Compliance</span></span>      | <span data-ttu-id="06988-151">LEA</span><span class="sxs-lookup"><span data-stu-id="06988-151">LEA</span></span>                |
| <span data-ttu-id="06988-152">¿Directiva de retención?</span><span class="sxs-lookup"><span data-stu-id="06988-152">Retention Policy?</span></span>      | <span data-ttu-id="06988-153">Opcional</span><span class="sxs-lookup"><span data-stu-id="06988-153">Optional</span></span>           | <span data-ttu-id="06988-154">Sí</span><span class="sxs-lookup"><span data-stu-id="06988-154">Yes</span></span>                | <span data-ttu-id="06988-155">Sí</span><span class="sxs-lookup"><span data-stu-id="06988-155">Yes</span></span>                | <span data-ttu-id="06988-156">Sí</span><span class="sxs-lookup"><span data-stu-id="06988-156">Yes</span></span>             | <span data-ttu-id="06988-157">Sí</span><span class="sxs-lookup"><span data-stu-id="06988-157">Yes</span></span>                |

<span data-ttu-id="06988-158">Teams proporciona diversas funciones para la grabación [<span class="underline">cómoda</span>](https://docs.microsoft.com/microsoftteams/cloud-recording) y funcional de reuniones y eventos en directo.</span><span class="sxs-lookup"><span data-stu-id="06988-158">Teams provides various capabilities for [<span class="underline">convenient</span>](https://docs.microsoft.com/microsoftteams/cloud-recording) and functional recording for meetings and live events.</span></span> <span data-ttu-id="06988-159">La grabación organizacional significa permitir a las organizaciones que adoptan equipos de llamadas y reuniones establecerse, a través de una directiva administrativa, cuando las llamadas y las reuniones en línea deben grabarse y capturarse de forma automática para su procesamiento y retención posterior, según lo requiera la política corporativa o normativa pertinente.</span><span class="sxs-lookup"><span data-stu-id="06988-159">Organizational recording means enabling organizations adopting Teams for calling and meetings to stipulate, by way of an administrative policy, when calls and online meetings should be automatically recorded and captured for subsequent processing and retention as required by relevant corporate or regulatory policy.</span></span> <span data-ttu-id="06988-160">Los usuarios de esta Directiva serán conscientes de que sus interacciones digitales con equipos se graban, pero no podrán deshabilitar la grabación y no tendrán acceso a la grabación una vez completada la interacción.</span><span class="sxs-lookup"><span data-stu-id="06988-160">Users under this policy will be aware that their digital interactions with Teams are being recorded but will not be able to disable the recording and will not have access to the recording once the interaction is complete.</span></span> <span data-ttu-id="06988-161">La grabación se convierte en parte del archivo organizativo disponible para el cumplimiento y el personal legal de eDiscovery, la retención legal y otros usos de la retención corporativa.</span><span class="sxs-lookup"><span data-stu-id="06988-161">The recording becomes part of the organizational archive available to compliance and legal personnel for eDiscovery, legal hold, and other corporate retention uses.</span></span>

## <a name="example-user-needs"></a><span data-ttu-id="06988-162">Necesidades de usuario de ejemplo</span><span class="sxs-lookup"><span data-stu-id="06988-162">Example user needs</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="06988-163"><strong>Rol</strong></span><span class="sxs-lookup"><span data-stu-id="06988-163"><strong>Persona</strong></span></span></th>
<th><span data-ttu-id="06988-164"><strong>Necesaria</strong></span><span class="sxs-lookup"><span data-stu-id="06988-164"><strong>Needs</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="06988-165">Usuarios grabados</span><span class="sxs-lookup"><span data-stu-id="06988-165">Recorded users</span></span></td>
<td><ul>
<li><p><span data-ttu-id="06988-166">Recibir una notificación cuando la grabación esté en curso.</span><span class="sxs-lookup"><span data-stu-id="06988-166">Be notified when recording is in progress.</span></span></p></li>
<li><p><span data-ttu-id="06988-167">Informarse cuando el error de la Directiva o de la grabadora provoca cambios en el comportamiento de la llamada.</span><span class="sxs-lookup"><span data-stu-id="06988-167">Be informed when policy and/or recorder error is causing changes in calling behavior.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="06988-168">Administrador de comunicaciones</span><span class="sxs-lookup"><span data-stu-id="06988-168">Communications admin</span></span></td>
<td><ul>
<li><p><span data-ttu-id="06988-169">Comprender por qué y cómo aplicar o exigir directivas de registro a usuarios y puntos de conexión de Teams.</span><span class="sxs-lookup"><span data-stu-id="06988-169">Understand why and how to apply / enforce recording policies to Teams users / endpoints.</span></span></p></li>
<li><p><span data-ttu-id="06988-170">Configurar y mantener directivas de grabación de Teams para la organización.</span><span class="sxs-lookup"><span data-stu-id="06988-170">Configure and maintain Teams recording policies for the organization.</span></span></p></li>
<li><p><span data-ttu-id="06988-171">Supervisar y solucionar problemas relacionados con el registro con llamadas y reuniones de Teams.</span><span class="sxs-lookup"><span data-stu-id="06988-171">Monitor and troubleshoot recording-related issues with Teams calls and meetings.</span></span></p></li>
<li><p><span data-ttu-id="06988-172">Apoyar al funcionario de cumplimiento interno con análisis operacional sobre el uso, la calidad y la confiabilidad.</span><span class="sxs-lookup"><span data-stu-id="06988-172">Support internal compliance officer with operational analytics on usage, quality, and reliability.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="06988-173">Funcionario encargado del cumplimiento</span><span class="sxs-lookup"><span data-stu-id="06988-173">Compliance officer</span></span></td>
<td><ul>
<li><p><span data-ttu-id="06988-174">Recopilar todas las comunicaciones de Teams de la forma requerida para cumplir con las obligaciones reglamentarias vigentes.</span><span class="sxs-lookup"><span data-stu-id="06988-174">Collect all Teams communications in the manner required to meet compliance obligations in appropriate regional boundaries.</span></span></p></li>
<li><p><span data-ttu-id="06988-175">Buscar interacciones en función de metadatos relacionados con la comunicación o contenido de interacción.</span><span class="sxs-lookup"><span data-stu-id="06988-175">Search for interactions based on communication-related metadata or interaction content.</span></span> <span data-ttu-id="06988-176">Algunos ejemplos comunes son:</span><span class="sxs-lookup"><span data-stu-id="06988-176">Common examples include:</span></span></p>
<ul>
<li><p><span data-ttu-id="06988-177"><strong>Metadatos</strong> - Participantes, hora, dirección, número marcado, número de origen, datos profesionales personalizados</span><span class="sxs-lookup"><span data-stu-id="06988-177"><strong>Metadata</strong> - Participants, time, direction, dialed number, origin number, Custom business data</span></span></p></li>
<li><p><span data-ttu-id="06988-178"><strong>Contenido</strong> : transcripción, sentimientos, fonética, interacciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="06988-178"><strong>Content</strong> – Transcription, sentiment, phonetics, related interactions</span></span></p></li>
</ul></li>
<li><p><span data-ttu-id="06988-179">Analizar e interactuar con las comunicaciones recopiladas, incluida la capacidad de supervisar las interacciones a medida que se recopilan.</span><span class="sxs-lookup"><span data-stu-id="06988-179">Analyze and interact with collected communications, including the ability to monitor interactions as they are being collected.</span></span></p></li>
<li><p><span data-ttu-id="06988-180">Garantizar la seguridad de las comunicaciones recopiladas e impedir alteraciones en todas las etapas.</span><span class="sxs-lookup"><span data-stu-id="06988-180">Ensure security of collected communications and prevent tampering at all stages.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="solution-architecture-overview"></a><span data-ttu-id="06988-181">Descripción general de la arquitectura de soluciones</span><span class="sxs-lookup"><span data-stu-id="06988-181">Solution architecture overview</span></span>

<span data-ttu-id="06988-182">Las soluciones de grabación de cumplimiento están integradas con Teams, tal y como se muestra en el siguiente diagrama:</span><span class="sxs-lookup"><span data-stu-id="06988-182">Compliance recording solutions are integrated with Teams as shown in the following diagram:</span></span>

<span data-ttu-id="06988-183">![Captura de pantalla que muestra la configuración de la aplicación personalizada del equipo](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "Las imágenes muestran el flujo cuando se envía y recibe una llamada o una reunión de Teams.")</span><span class="sxs-lookup"><span data-stu-id="06988-183">![Screenshot showing the team custom app setting](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "The images shows the flow when a Teams meeting or call is sent and received.")</span></span>

## <a name="recorder"></a><span data-ttu-id="06988-184">Magnetoscopio</span><span class="sxs-lookup"><span data-stu-id="06988-184">Recorder</span></span>

<span data-ttu-id="06988-185">El componente principal de la solución de grabación de cumplimiento es el grabador.</span><span class="sxs-lookup"><span data-stu-id="06988-185">The core component of the compliance recording solution is the recorder.</span></span>
<span data-ttu-id="06988-186">Los grabadores se crean como servicios escalables basados en Azure (bots) que [<span class="underline">aprovechan la plataforma de comunicaciones de Microsoft</span>](https://docs.microsoft.com/graph/cloud-communications-concept-overview) y se registran como aplicaciones con Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="06988-186">Recorders are built as scalable Azure-based services (bots) that [<span class="underline">leverage Microsoft’s communications platform</span>](https://docs.microsoft.com/graph/cloud-communications-concept-overview) and register as applications with Microsoft Graph.</span></span> <span data-ttu-id="06988-187">La grabadora proporciona la interacción directa con las API de la [<span class="underline">plataforma de comunicaciones</span>](https://docs.microsoft.com/graph/api/resources/communications-api-overview?view=graph-rest-1.0) de las llamadas y reuniones de Teams y proporciona el punto final para la recopilación de medios.</span><span class="sxs-lookup"><span data-stu-id="06988-187">The recorder provides the direct interaction with the Teams calls and meetings [<span class="underline">communications platform APIs</span>](https://docs.microsoft.com/graph/api/resources/communications-api-overview?view=graph-rest-1.0) and provides the endpoint for media ingestion.</span></span>

<span data-ttu-id="06988-188">[<span class="underline">Hay disponible una aplicación de grabadora de cumplimiento de ejemplo</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) que muestra cómo configurar el bot, crear la instancia de la aplicación y asignar las directivas de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="06988-188">A [<span class="underline">sample compliance recorder application is available</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) that shows how to configure the bot, create the app instance and assign the compliance policies.</span></span> <span data-ttu-id="06988-189">El ejemplo también tiene ejemplos sobre el uso de la API para registrar interacciones específicas, como el control del enrutamiento de [<span class="underline">llamadas entrantes</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244) , el [<span class="underline">cambio de Estados de grabación</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138)y [<span class="underline">la eliminación del usuario que se está grabando</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126).</span><span class="sxs-lookup"><span data-stu-id="06988-189">The sample also has examples on API usage for recording specific interactions such as handling [<span class="underline">incoming call</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244) routing, [<span class="underline">changing recording states</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138), and [<span class="underline">removing the user who is being recorded</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126).</span></span>
<span data-ttu-id="06988-190">La documentación de Graph en las API específicas se puede encontrar aquí para [<span class="underline">updateRecordingStatus</span>](https://docs.microsoft.com/graph/api/call-updaterecordingstatus?view=graph-rest-1.0&tabs=http) y [<span class="underline">incomingContext</span>](https://docs.microsoft.com/graph/api/resources/incomingcontext?view=graph-rest-1.0).</span><span class="sxs-lookup"><span data-stu-id="06988-190">Graph documentation on the specific APIs can be found here for [<span class="underline">updateRecordingStatus</span>](https://docs.microsoft.com/graph/api/call-updaterecordingstatus?view=graph-rest-1.0&tabs=http) and [<span class="underline">incomingContext</span>](https://docs.microsoft.com/graph/api/resources/incomingcontext?view=graph-rest-1.0).</span></span>

<span data-ttu-id="06988-191">La implementación exacta del servicio de grabadora varía según el socio, pero debe estar diseñada para admitir varios registros a fin de lograr una alta disponibilidad y una distribución geográfica de la implementación a fin de reducir la latencia de los equipos a la grabadora.</span><span class="sxs-lookup"><span data-stu-id="06988-191">The exact implementation of the recorder service will vary by partner but must be designed to support multiple recorders in order to achieve high availability and geographical distribution of deployment to reduce latency from Teams to the recorder.</span></span> <span data-ttu-id="06988-192">Además, se espera que los grabadores se diseñen con la resistencia y la redundancia en mente.</span><span class="sxs-lookup"><span data-stu-id="06988-192">In addition, it is expected that Recorders themselves be designed with resiliency and redundancy in mind.</span></span>

<span data-ttu-id="06988-193">Los socios deben confirmar la versión de lanzamiento mínima requerida de las API y SDK de comunicaciones de Microsoft Graph con Microsoft antes de enviar su solución de certificación para garantizar que se admitan todos los requisitos de integración de grabaciones de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="06988-193">Partners must confirm the minimum required release version of the Microsoft Graph communications APIs and SDKs with Microsoft before submitting their solution for certification to ensure that all requirements of compliance recording integration are supported.</span></span>

<span data-ttu-id="06988-194">Dos requisitos específicos fundamentales para el escenario de grabación de cumplimiento son:</span><span class="sxs-lookup"><span data-stu-id="06988-194">Two specific requirements that are fundamental for compliance recording scenario are:</span></span>

- <span data-ttu-id="06988-195">El bot de grabadora debe implementarse en Azure</span><span class="sxs-lookup"><span data-stu-id="06988-195">Recorder bot must be deployed in Azure</span></span>

- <span data-ttu-id="06988-196">El bot de grabadora debe ejecutarse en una VM de Windows en Azure</span><span class="sxs-lookup"><span data-stu-id="06988-196">Recorder bot must run on a Windows VM in Azure</span></span>

<span data-ttu-id="06988-197">Los requisitos de Windows VM de Azure y Windows solo se aplican al componente bot de Teams, lo que significa que un asociado puede implementar el resto de la plataforma de su elección, siempre y cuando cumplan con los requisitos de rendimiento y funcionales pertinentes para la grabación de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="06988-197">The Azure and Windows VM requirements only apply to the Teams Bot component, which means that a partner may implement the rest of the platform of their choice provided they can meet the relevant performance and functional requirements for compliance recording.</span></span>

## <a name="compliance-recording-policy-assignment-and-provisioning"></a><span data-ttu-id="06988-198">Aprovisionamiento y asignación de directivas de grabación de cumplimiento normativo</span><span class="sxs-lookup"><span data-stu-id="06988-198">Compliance recording policy assignment and provisioning</span></span>

<span data-ttu-id="06988-199">Los administradores de TI pueden determinar qué usuarios se grabarán y qué grabadora se usará para cada usuario mediante la creación y asignación de directivas de grabación de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="06988-199">IT Administrators can determine which users are to be recorded and which recorder will be used for each user, by creating and assigning compliance recording policies.</span></span> <span data-ttu-id="06988-200">Los grabadores se invitan automáticamente a participar en las conversaciones basándose en la configuración de estas directivas cuando tiene lugar una interacción de comunicación.</span><span class="sxs-lookup"><span data-stu-id="06988-200">Recorders are automatically invited to participate in conversations based on the configuration of these policies when a communication interaction takes place.</span></span> <span data-ttu-id="06988-201">Las directivas de grabación de cumplimiento se administran con [<span class="underline">Microsoft PowerShell</span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview) y se pueden aplicar a nivel de inquilino, por usuario y de seguridad para cada organización.</span><span class="sxs-lookup"><span data-stu-id="06988-201">Compliance recording policies are managed using [<span class="underline">Microsoft Powershell</span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview) and can be applied at the tenant, per-user, and security group level for each organization.</span></span> <span data-ttu-id="06988-202">Puede encontrar más información sobre [<span class="underline">las directivas de reunión</span>](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams), [<span class="underline">las directivas de llamada</span>](https://docs.microsoft.com/microsoftteams/teams-calling-policy) y las directivas de  [<span class="underline">Grupo</span>](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-group)en Microsoft docs.</span><span class="sxs-lookup"><span data-stu-id="06988-202">You can find more information on Microsoft Docs for [<span class="underline">Meeting policies</span>](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams), [<span class="underline">calling policies</span>](https://docs.microsoft.com/microsoftteams/teams-calling-policy) and  [<span class="underline">group policies</span>](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-group).</span></span>

1. <span data-ttu-id="06988-203">Cree una instancia de la aplicación en su espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="06988-203">Create an application instance in your tenant.</span></span>

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

2. <span data-ttu-id="06988-204">Crear una directiva de grabación de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="06988-204">Create a Compliance Recording policy.</span></span>

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

   [<span data-ttu-id="06988-205"><span class="underline">Set-CsTeamsComplianceRecordingPolicy</span></span><span class="sxs-lookup"><span data-stu-id="06988-205"><span class="underline">Set-CsTeamsComplianceRecordingPolicy</span></span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamscompliancerecordingpolicy?view=skype-ps)

3. <span data-ttu-id="06988-206">Asignar la Directiva de grabación de cumplimiento a un usuario.</span><span class="sxs-lookup"><span data-stu-id="06988-206">Assign the Compliance Recording policy to a user.</span></span>

   ```powershell
   PS C:\> Grant-CsTeamsComplianceRecordingPolicy -Identity testuser@contoso.onmicrosoft.com -PolicyName TestComplianceRecordingPolicy
   ```

   [<span data-ttu-id="06988-207"><span class="underline">Grant-CsTeamsComplianceRecordingPolicy</span></span><span class="sxs-lookup"><span data-stu-id="06988-207"><span class="underline">Grant-CsTeamsComplianceRecordingPolicy</span></span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamscompliancerecordingpolicy?view=skype-ps)

   ```powershell
   PS C:\> Get-CsOnlineUser testuser@contoso.onmicrosoft.com | select SipAddress, TenantId, TeamsComplianceRecordingPolicy | fl

   UserPrincipalName              : testuser@contoso.onmicrosoft.com
   TenantId                       : 5b943d7c-5e14-474b-8237-5022eb8e0dc9
   TeamsComplianceRecordingPolicy : TestComplianceRecordingPolicy
   ```

## <a name="user-experiences"></a><span data-ttu-id="06988-208">Experiencias de usuario</span><span class="sxs-lookup"><span data-stu-id="06988-208">User experiences</span></span>

<span data-ttu-id="06988-209">La compatibilidad con las notificaciones se habilita con las experiencias del cliente de Teams.</span><span class="sxs-lookup"><span data-stu-id="06988-209">Support for notifications is enabled using the Teams client experiences.</span></span> <span data-ttu-id="06988-210">Las experiencias pueden ser visuales o de audio.</span><span class="sxs-lookup"><span data-stu-id="06988-210">The experiences can be either visual or audio.</span></span>

<span data-ttu-id="06988-211">**Clientes de Teams: aviso visual**</span><span class="sxs-lookup"><span data-stu-id="06988-211">**Teams clients - visual notice**</span></span>
- <span data-ttu-id="06988-212">Escritorio/web</span><span class="sxs-lookup"><span data-stu-id="06988-212">Desktop/web</span></span>
- <span data-ttu-id="06988-213">Móvil (iOS/Android)</span><span class="sxs-lookup"><span data-stu-id="06988-213">Mobile (iOS/Android)</span></span>
- <span data-ttu-id="06988-214">Teléfonos de equipos</span><span class="sxs-lookup"><span data-stu-id="06988-214">Teams phones</span></span>
- <span data-ttu-id="06988-215">Salas de equipos</span><span class="sxs-lookup"><span data-stu-id="06988-215">Teams rooms</span></span>

<span data-ttu-id="06988-216">**Otros puntos de conexión-aviso de audio**</span><span class="sxs-lookup"><span data-stu-id="06988-216">**Other endpoints - audio notice**</span></span>
- <span data-ttu-id="06988-217">Teléfonos SIP</span><span class="sxs-lookup"><span data-stu-id="06988-217">SIP phones</span></span>
- <span data-ttu-id="06988-218">Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="06988-218">Skype for Business</span></span>
- <span data-ttu-id="06988-219">Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="06988-219">Audio conferencing</span></span>
- <span data-ttu-id="06988-220">Autores de llamadas RTC</span><span class="sxs-lookup"><span data-stu-id="06988-220">PSTN callers</span></span>

## <a name="compliance-recording-for-teams-certification-programs"></a><span data-ttu-id="06988-221">Grabación de cumplimiento para los programas de certificación de Teams</span><span class="sxs-lookup"><span data-stu-id="06988-221">Compliance recording for Teams certification programs</span></span>

<span data-ttu-id="06988-222">Además de publicar API disponibles públicamente para que los socios puedan desarrollar e integrar soluciones de CCaaS con Teams, hemos desarrollado el programa de certificación de la grabación de cumplimiento para Microsoft Teams a fin de proporcionar a los clientes la seguridad de que la solución de cada socio participante ha sido probada y verificada para proporcionar la calidad, la compatibilidad y la confiabilidad que esperan de las soluciones de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="06988-222">In addition to publishing publicly-available APIs allowing partners to develop and integrate CCaaS solutions with Teams, we have developed the compliance recording for Microsoft Teams certification program to provide customers with the assurance that each participating partner’s solution has been tested and verified to provide the quality, compatibility and reliability they expect from Microsoft solutions.</span></span>  

<span data-ttu-id="06988-223">Los siguientes socios han certificado su solución para Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="06988-223">The following partners have certified their solution for Microsoft Teams.</span></span>

|<span data-ttu-id="06988-224">Servidor</span><span class="sxs-lookup"><span data-stu-id="06988-224">Partner</span></span>|<span data-ttu-id="06988-225">Sitio web de soluciones</span><span class="sxs-lookup"><span data-stu-id="06988-225">Solution website</span></span> |
|:--|:--|
|<span data-ttu-id="06988-226">ALINEA</span><span class="sxs-lookup"><span data-stu-id="06988-226">NICE</span></span> |[https://www.niceactimize.com/compliance/ms-teams-recording.html](https://www.niceactimize.com/compliance/ms-teams-recording.html) |


<span data-ttu-id="06988-227">Los siguientes socios están en el proceso de certificar su solución para Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="06988-227">The following partners are in the process of certifying their solution for Microsoft Teams.</span></span>

|<span data-ttu-id="06988-228">Servidor</span><span class="sxs-lookup"><span data-stu-id="06988-228">Partner</span></span>|<span data-ttu-id="06988-229">Sitio web de soluciones</span><span class="sxs-lookup"><span data-stu-id="06988-229">Solution website</span></span> |
|:--|:--|
|<span data-ttu-id="06988-230">Tecnologías ASC</span><span class="sxs-lookup"><span data-stu-id="06988-230">ASC Technologies</span></span> |[https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html](https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html) |
|<span data-ttu-id="06988-231">AudioCodes</span><span class="sxs-lookup"><span data-stu-id="06988-231">AudioCodes</span></span> |[https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/smarttap-360-recording](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/smarttap-360-recording) |
|<span data-ttu-id="06988-232">CallCabinet</span><span class="sxs-lookup"><span data-stu-id="06988-232">CallCabinet</span></span> |[https://www.callcabinet.com/compliance-microsoft-teams-call-recording](https://www.callcabinet.com/compliance-microsoft-teams-call-recording ) |
|<span data-ttu-id="06988-233">Un doblador</span><span class="sxs-lookup"><span data-stu-id="06988-233">Dubber</span></span> |[https://www.dubber.net/call-recording/](https://www.dubber.net/call-recording/) |
|<span data-ttu-id="06988-234">Tecnologías de Landis</span><span class="sxs-lookup"><span data-stu-id="06988-234">Landis Technologies</span></span> |[https://landistechnologies.com/](https://landistechnologies.com/) |
|<span data-ttu-id="06988-235">Luware</span><span class="sxs-lookup"><span data-stu-id="06988-235">Luware</span></span> |[https://luware.com/en/solution/microsoft-teams-recording/](https://luware.com/en/solution/microsoft-teams-recording/) |
|<span data-ttu-id="06988-236">Numonix</span><span class="sxs-lookup"><span data-stu-id="06988-236">Numonix</span></span> |[https://numonix.cloud](https://numonix.cloud)    |
|<span data-ttu-id="06988-237">Innovación en roble</span><span class="sxs-lookup"><span data-stu-id="06988-237">Oak Innovation</span></span> |[https://www.oakinnovate.com/call-recording](https://www.oakinnovate.com/call-recording) |
|<span data-ttu-id="06988-238">Cuadro rojo</span><span class="sxs-lookup"><span data-stu-id="06988-238">Red Box</span></span> |[https://www.redboxvoice.com/compliance-recording-for-microsoft-teams](https://www.redboxvoice.com/compliance-recording-for-microsoft-teams)  |
|<span data-ttu-id="06988-239">Verint</span><span class="sxs-lookup"><span data-stu-id="06988-239">Verint</span></span> |[https://www.verba.com/solutions/microsoft-teams-recording](https://www.verba.com/solutions/microsoft-teams-recording) |

<span data-ttu-id="06988-240">Esta lista se actualizará a medida que se unan más socios y cumplan los criterios de certificación.</span><span class="sxs-lookup"><span data-stu-id="06988-240">This list will be updated as more partners join and meet the certification criteria.</span></span>

## <a name="next-steps"></a><span data-ttu-id="06988-241">Siguientes pasos</span><span class="sxs-lookup"><span data-stu-id="06988-241">Next steps</span></span>

<span data-ttu-id="06988-242">Si eres un proveedor y deseas participar en el programa de certificación, envía un mensaje de correo  <a href= "mailto:Teamscategorypartner@microsoft.com">Teamscategorypartner@microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="06988-242">If you are a vendor seeking to join the certification program, please mail  <a href= "mailto:Teamscategorypartner@microsoft.com">Teamscategorypartner@microsoft.com</a>.</span></span>
