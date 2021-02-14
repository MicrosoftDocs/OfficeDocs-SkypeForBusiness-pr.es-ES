---
title: Cumplimiento de la comunicación con Microsoft Teams
author: robmazz
ms.author: robmazz
manager: laurawi
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: anwara
description: Aprenda sobre el cumplimiento de comunicaciones, parte del conjunto de soluciones de riesgo de Insider, desde la perspectiva de Microsoft Teams (esto forma parte de la funcionalidad de cumplimiento de comunicaciones de M365).
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: bb9400778b8e000a438343e74bc6b030087ff297
ms.sourcegitcommit: 739ffd5893abf6d181877d1110f9dc8230b3bfd2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328259"
---
# <a name="communication-compliance-with-microsoft-teams"></a><span data-ttu-id="3d3f2-103">Cumplimiento de la comunicación con Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3d3f2-103">Communication compliance with Microsoft Teams</span></span>

<span data-ttu-id="3d3f2-104">El cumplimiento de comunicaciones es una solución de riesgo de Insider de Microsoft 365 que ayuda a minimizar los riesgos de comunicación al ayudarle a detectar, capturar y actuar sobre mensajes inadecuados en su organización.</span><span class="sxs-lookup"><span data-stu-id="3d3f2-104">Communication compliance is an insider risk solution in Microsoft 365 that helps minimize communication risks by helping you detect, capture, and act on inappropriate messages in your organization.</span></span>

<span data-ttu-id="3d3f2-105">Para Microsoft Teams, el [](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-feature-reference) cumplimiento de comunicaciones le ayuda a identificar los siguientes tipos de contenido inapropiado en los canales de Teams o en chats grupales y uno a uno:</span><span class="sxs-lookup"><span data-stu-id="3d3f2-105">For Microsoft Teams, communication compliance helps identify the [following types](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-feature-reference) of inappropriate content in Teams channels or in 1:1 and group chats:</span></span>

- <span data-ttu-id="3d3f2-106">Lenguaje ofensivo, obsano y acosante</span><span class="sxs-lookup"><span data-stu-id="3d3f2-106">Offensive, profane, and harassing language</span></span>
- <span data-ttu-id="3d3f2-107">Imágenes para adultos, rdo e imágenes gory</span><span class="sxs-lookup"><span data-stu-id="3d3f2-107">Adult, racy, and gory images</span></span>
- <span data-ttu-id="3d3f2-108">Uso compartido de información confidencial</span><span class="sxs-lookup"><span data-stu-id="3d3f2-108">Sharing of sensitive information</span></span>

<span data-ttu-id="3d3f2-109">Para obtener más información sobre el cumplimiento de comunicaciones y cómo configurar directivas para su organización, vea Cumplimiento de [comunicaciones en Microsoft 365.](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance)</span><span class="sxs-lookup"><span data-stu-id="3d3f2-109">For more information on communication compliance and how to configure policies for your organization, see [Communication compliance in Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance).</span></span>

## <a name="how-to-use-communication-compliance-in-microsoft-teams"></a><span data-ttu-id="3d3f2-110">Cómo usar el cumplimiento de comunicaciones en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3d3f2-110">How to use communication compliance in Microsoft Teams</span></span>

<span data-ttu-id="3d3f2-111">El cumplimiento de las comunicaciones y Microsoft Teams están estrechamente integrados y pueden ayudar a minimizar los riesgos de comunicación en su organización.</span><span class="sxs-lookup"><span data-stu-id="3d3f2-111">Communication compliance and Microsoft Teams are tightly integrated and can help minimize communication risks in your organization.</span></span> <span data-ttu-id="3d3f2-112">Después de configurar las primeras directivas de cumplimiento de comunicaciones, puede administrar de forma activa los mensajes y el contenido inadecuados de Microsoft Teams que se marcan automáticamente en las alertas.</span><span class="sxs-lookup"><span data-stu-id="3d3f2-112">After you've configured your first communication compliance policies, you can actively manage inappropriate Microsoft Teams messages and content that is automatically flagged in alerts.</span></span>

### <a name="getting-started"></a><span data-ttu-id="3d3f2-113">Introducción</span><span class="sxs-lookup"><span data-stu-id="3d3f2-113">Getting started</span></span>

<span data-ttu-id="3d3f2-114">La introducción al cumplimiento de [](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-plan) comunicaciones en Microsoft Teams comienza con la planeación y creación de directivas predefinidas o personalizadas para identificar las actividades de usuario inapropiadas en los canales de Teams o en grupos y uno a uno.</span><span class="sxs-lookup"><span data-stu-id="3d3f2-114">Getting started with communication compliance in Microsoft Teams begins with [planning](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-plan) and creating pre-defined or custom policies to identify inappropriate user activities in Teams channels or in 1:1 and groups.</span></span> <span data-ttu-id="3d3f2-115">Tenga en cuenta que necesitará [](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-configure) configurar algunos permisos y requisitos previos básicos como parte del proceso de configuración.</span><span class="sxs-lookup"><span data-stu-id="3d3f2-115">Keep in mind that you'll need to [configure](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-configure) some permissions and basic prerequisites as part of the configuration process.</span></span>

<span data-ttu-id="3d3f2-116">Los administradores de Teams pueden configurar directivas de cumplimiento de comunicaciones en los niveles siguientes:</span><span class="sxs-lookup"><span data-stu-id="3d3f2-116">Teams administrators can configure communication compliance policies at the following levels:</span></span>

- <span data-ttu-id="3d3f2-117">**Nivel de usuario:** las directivas de este nivel se aplican a un usuario individual de Teams o se pueden aplicar a todos los usuarios de Teams de su organización.</span><span class="sxs-lookup"><span data-stu-id="3d3f2-117">**User level**: Policies at this level apply to an individual Teams user or may be applied to all Teams users in your organization.</span></span> <span data-ttu-id="3d3f2-118">Estas directivas abarcan los mensajes que estos usuarios pueden enviar en chats grupales o uno a uno.</span><span class="sxs-lookup"><span data-stu-id="3d3f2-118">These policies cover messages that these users may send in 1:1 or group chats.</span></span> <span data-ttu-id="3d3f2-119">Las comunicaciones por chat de los usuarios se supervisan automáticamente en todos los equipos de Microsoft Teams en los que los usuarios son miembros.</span><span class="sxs-lookup"><span data-stu-id="3d3f2-119">Chat communications for the users are automatically monitored across all Microsoft Teams where the users are a member.</span></span>
- <span data-ttu-id="3d3f2-120">**Nivel de** teams: las directivas de este nivel se aplican a un canal de Microsoft Team.</span><span class="sxs-lookup"><span data-stu-id="3d3f2-120">**Teams level**: Policies at this level apply to a Microsoft Team channel.</span></span> <span data-ttu-id="3d3f2-121">Estas directivas cubren los mensajes enviados solo en el canal de Teams.</span><span class="sxs-lookup"><span data-stu-id="3d3f2-121">These policies cover messages sent in the Teams channel only.</span></span>

### <a name="act-on-inappropriate-messages-in-microsoft-teams"></a><span data-ttu-id="3d3f2-122">Actuar sobre mensajes inadecuados en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3d3f2-122">Act on inappropriate messages in Microsoft Teams</span></span>

<span data-ttu-id="3d3f2-123">Una vez que haya configurado las directivas y haya recibido alertas de cumplimiento de comunicaciones para los mensajes de Microsoft Teams, es el momento de que los revisores de cumplimiento de la organización tomen medidas con respecto a estos mensajes.</span><span class="sxs-lookup"><span data-stu-id="3d3f2-123">After you have configured your policies and have received communication compliance alerts for Microsoft Teams messages, it's time for compliance reviewers in your organization to take action on these messages.</span></span> <span data-ttu-id="3d3f2-124">Los revisores pueden ayudar a salvaguardar su organización revisando las alertas de cumplimiento de comunicaciones y quitando los mensajes marcados de la vista en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3d3f2-124">Reviewers can help safeguard your organization by reviewing communication compliance alerts and removing flagged messages from view in Microsoft Teams.</span></span>

![Quitar un mensaje en Teams](./media/communication-compliance-remove-teams-message.png)

<span data-ttu-id="3d3f2-126">Los mensajes y el contenido eliminados se reemplazan con notificaciones para los lectores que explican que el mensaje o el contenido se ha quitado y qué directiva es aplicable a la eliminación.</span><span class="sxs-lookup"><span data-stu-id="3d3f2-126">Removed messages and content are replaced with notifications for viewers explaining that the message or content has been removed and what policy is applicable to the removal.</span></span> <span data-ttu-id="3d3f2-127">Al remitente del mensaje o el contenido eliminado también se le notifica el estado de eliminación y se le proporciona el contenido del mensaje original para el contexto relacionado con su eliminación.</span><span class="sxs-lookup"><span data-stu-id="3d3f2-127">The sender of the removed message or content is also notified of the removal status and provided with original message content for context relating to its removal.</span></span> <span data-ttu-id="3d3f2-128">El remitente también puede ver la condición de directiva específica que se aplica a la eliminación del mensaje.</span><span class="sxs-lookup"><span data-stu-id="3d3f2-128">The sender can also view the specific policy condition that applies to the message removal.</span></span>

<span data-ttu-id="3d3f2-129">Ejemplo de sugerencia de directiva que ha visto el remitente:</span><span class="sxs-lookup"><span data-stu-id="3d3f2-129">Example of policy tip seen by sender:</span></span>

![Sugerencia de directiva para el remitente](./media/communication-compliance-warning-1.png)

<span data-ttu-id="3d3f2-131">Ejemplo de notificación de condición de directiva que ha visto el remitente:</span><span class="sxs-lookup"><span data-stu-id="3d3f2-131">Example of policy condition notification seen by the sender:</span></span>

![Información de condiciones de directiva para el remitente](./media/communication-compliance-warning-2.png)

<span data-ttu-id="3d3f2-133">Ejemplo de sugerencia de directiva que ha visto el destinatario:</span><span class="sxs-lookup"><span data-stu-id="3d3f2-133">Example of policy tip seen by recipient:</span></span>

![Sugerencia de directiva para destinatario](./media/communication-compliance-warning-3.png)
