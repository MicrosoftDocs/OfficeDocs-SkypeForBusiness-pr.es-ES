---
title: Cumplimiento de la comunicación con Microsoft Teams
author: robmazz
ms.author: robmazz
manager: laurawi
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: anwara
description: Aprender sobre el cumplimiento de las comunicaciones, parte de la solución de riesgos de Insider, desde la perspectiva de Microsoft Teams (esta es parte de la funcionalidad de cumplimiento de comunicaciones de M365).
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a8fa1bcc7190050fd06c15717aebf8648f94b090
ms.sourcegitcommit: 8816b58e175031cb0a71e0d0e89e447a7b83a760
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/08/2020
ms.locfileid: "46597154"
---
# <a name="communication-compliance-with-microsoft-teams"></a><span data-ttu-id="92a73-103">Cumplimiento de la comunicación con Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="92a73-103">Communication compliance with Microsoft Teams</span></span>

<span data-ttu-id="92a73-104">El cumplimiento de la comunicación es una solución de riesgo de Insider en Microsoft 365 que ayuda a minimizar los riesgos de comunicación ayudándole a detectar, capturar y actuar en los mensajes inapropiados de su organización.</span><span class="sxs-lookup"><span data-stu-id="92a73-104">Communication compliance is an insider risk solution in Microsoft 365 that helps minimize communication risks by helping you detect, capture, and act on inappropriate messages in your organization.</span></span>

<span data-ttu-id="92a73-105">Para Microsoft Teams, el cumplimiento de la comunicación ayuda a identificar los [siguientes tipos](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-feature-reference) de contenido inadecuado en canales de equipos o en 1:1 y chats grupales:</span><span class="sxs-lookup"><span data-stu-id="92a73-105">For Microsoft Teams, communication compliance helps identify the [following types](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-feature-reference) of inappropriate content in Teams channels or in 1:1 and group chats:</span></span>

- <span data-ttu-id="92a73-106">Lenguaje ofensivo, irreverente y de acoso</span><span class="sxs-lookup"><span data-stu-id="92a73-106">Offensive, profane, and harassing language</span></span>
- <span data-ttu-id="92a73-107">Imágenes de adultos, racy y Gory</span><span class="sxs-lookup"><span data-stu-id="92a73-107">Adult, racy, and gory images</span></span>
- <span data-ttu-id="92a73-108">Uso compartido de información confidencial</span><span class="sxs-lookup"><span data-stu-id="92a73-108">Sharing of sensitive information</span></span>

>[!IMPORTANT]
><span data-ttu-id="92a73-109">Los canales privados de Microsoft Teams no son compatibles con el cumplimiento de la comunicación.</span><span class="sxs-lookup"><span data-stu-id="92a73-109">Private Microsoft Teams channels are not supported by communication compliance.</span></span> <span data-ttu-id="92a73-110">Las comunicaciones por chat enviadas por usuarios invitados a los usuarios de los equipos no se supervisan para el contenido inapropiado.</span><span class="sxs-lookup"><span data-stu-id="92a73-110">Chat communications sent by guest users to Teams users aren't monitored for inappropriate content.</span></span>

<span data-ttu-id="92a73-111">Para obtener más información sobre el cumplimiento de las comunicaciones y sobre cómo configurar directivas para su organización, consulte [cumplimiento de la comunicación en Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance).</span><span class="sxs-lookup"><span data-stu-id="92a73-111">For more information on communication compliance and how to configure policies for your organization, see [Communication compliance in Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance).</span></span>

## <a name="how-to-use-communication-compliance-in-microsoft-teams"></a><span data-ttu-id="92a73-112">Cómo usar el cumplimiento de la comunicación en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="92a73-112">How to use communication compliance in Microsoft Teams</span></span>

<span data-ttu-id="92a73-113">El cumplimiento de las comunicaciones y Microsoft Teams están estrechamente integrados y pueden ayudar a minimizar los riesgos de comunicación de su organización.</span><span class="sxs-lookup"><span data-stu-id="92a73-113">Communication compliance and Microsoft Teams are tightly integrated and can help minimize communication risks in your organization.</span></span> <span data-ttu-id="92a73-114">Una vez que haya configurado las primeras directivas de cumplimiento de comunicaciones, puede administrar activamente los mensajes y el contenido inapropiados de Microsoft teams que se marcan automáticamente en las alertas.</span><span class="sxs-lookup"><span data-stu-id="92a73-114">After you've configured your first communication compliance policies, you can actively manage inappropriate Microsoft Teams messages and content that is automatically flagged in alerts.</span></span>

### <a name="getting-started"></a><span data-ttu-id="92a73-115">Introducción</span><span class="sxs-lookup"><span data-stu-id="92a73-115">Getting started</span></span>

<span data-ttu-id="92a73-116">Introducción a la comunicación el cumplimiento en Microsoft Teams comienza a [planear](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-plan) y crear directivas predefinidas o personalizadas para identificar actividades de usuario inadecuadas en los canales de Teams o en 1:1 y grupos.</span><span class="sxs-lookup"><span data-stu-id="92a73-116">Getting started with communication compliance in Microsoft Teams begins with [planning](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-plan) and creating pre-defined or custom policies to identify inappropriate user activities in Teams channels or in 1:1 and groups.</span></span> <span data-ttu-id="92a73-117">Tenga en cuenta que tendrá que [configurar](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-configure) algunos permisos y los requisitos previos básicos como parte del proceso de configuración.</span><span class="sxs-lookup"><span data-stu-id="92a73-117">Keep in mind that you'll need to [configure](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-configure) some permissions and basic prerequisites as part of the configuration process.</span></span>

<span data-ttu-id="92a73-118">Los administradores de equipos pueden configurar directivas de cumplimiento de comunicaciones en los siguientes niveles:</span><span class="sxs-lookup"><span data-stu-id="92a73-118">Teams administrators can configure communication compliance policies at the following levels:</span></span>

- <span data-ttu-id="92a73-119">**Nivel de usuario**: las directivas de este nivel se aplican a un usuario individual de Teams o se pueden aplicar a todos los usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="92a73-119">**User level**: Policies at this level apply to an individual Teams user or may be applied to all Teams users in your organization.</span></span> <span data-ttu-id="92a73-120">Estas directivas cubren los mensajes que estos usuarios pueden enviar en 1:1 o chats grupales.</span><span class="sxs-lookup"><span data-stu-id="92a73-120">These policies cover messages that these users may send in 1:1 or group chats.</span></span> <span data-ttu-id="92a73-121">Las comunicaciones por chat de los usuarios se supervisan automáticamente en todos los equipos de Microsoft en los que los usuarios son miembros.</span><span class="sxs-lookup"><span data-stu-id="92a73-121">Chat communications for the users are automatically monitored across all Microsoft Teams where the users are a member.</span></span>
- <span data-ttu-id="92a73-122">**Nivel de Teams**: las directivas de este nivel se aplican a un canal de equipo de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="92a73-122">**Teams level**: Policies at this level apply to a Microsoft Team channel.</span></span> <span data-ttu-id="92a73-123">Estas directivas cubren los mensajes enviados solo en el canal de Teams.</span><span class="sxs-lookup"><span data-stu-id="92a73-123">These policies cover messages sent in the Teams channel only.</span></span>

### <a name="act-on-inappropriate-messages-in-microsoft-teams"></a><span data-ttu-id="92a73-124">Actuar sobre mensajes inapropiados en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="92a73-124">Act on inappropriate messages in Microsoft Teams</span></span>

<span data-ttu-id="92a73-125">Una vez que haya configurado las directivas y haya recibido alertas de cumplimiento para las comunicaciones de los mensajes de Microsoft Teams, es el momento de que los revisores de cumplimiento de normas de su organización tomen medidas en estos mensajes.</span><span class="sxs-lookup"><span data-stu-id="92a73-125">After you have configured your policies and have received communication compliance alerts for Microsoft Teams messages, it's time for compliance reviewers in your organization to take action on these messages.</span></span> <span data-ttu-id="92a73-126">Los revisores pueden ayudar a proteger su organización revisando las alertas de cumplimiento de comunicaciones y eliminando los mensajes marcados de la vista en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="92a73-126">Reviewers can help safeguard your organization by reviewing communication compliance alerts and removing flagged messages from view in Microsoft Teams.</span></span>

![Quitar un mensaje de Teams](./media/communication-compliance-remove-teams-message.png)

<span data-ttu-id="92a73-128">Los mensajes y el contenido quitados se reemplazan por notificaciones para visores que explican que el mensaje o contenido se ha quitado y qué directiva es aplicable a la eliminación.</span><span class="sxs-lookup"><span data-stu-id="92a73-128">Removed messages and content are replaced with notifications for viewers explaining that the message or content has been removed and what policy is applicable to the removal.</span></span> <span data-ttu-id="92a73-129">El remitente del mensaje o contenido eliminado también recibe la notificación del estado de eliminación y se proporciona con el contenido del mensaje original para el contexto relacionado con su eliminación.</span><span class="sxs-lookup"><span data-stu-id="92a73-129">The sender of the removed message or content is also notified of the removal status and provided with original message content for context relating to its removal.</span></span> <span data-ttu-id="92a73-130">El remitente también puede ver la condición de la Directiva específica que se aplica a la eliminación del mensaje.</span><span class="sxs-lookup"><span data-stu-id="92a73-130">The sender can also view the specific policy condition that applies to the message removal.</span></span>

<span data-ttu-id="92a73-131">Ejemplo de sugerencia de directiva visto por el remitente:</span><span class="sxs-lookup"><span data-stu-id="92a73-131">Example of policy tip seen by sender:</span></span>

![Sugerencia de directiva para el remitente](./media/communication-compliance-warning-1.png)

<span data-ttu-id="92a73-133">Ejemplo de notificación de condición de la Directiva visto por el remitente:</span><span class="sxs-lookup"><span data-stu-id="92a73-133">Example of policy condition notification seen by the sender:</span></span>

![Información de condición de la Directiva para el remitente](./media/communication-compliance-warning-2.png)

<span data-ttu-id="92a73-135">Ejemplo de sugerencia de directiva visto por el destinatario:</span><span class="sxs-lookup"><span data-stu-id="92a73-135">Example of policy tip seen by recipient:</span></span>

![Sugerencia de directiva para el destinatario](./media/communication-compliance-warning-3.png)