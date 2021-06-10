---
title: Cumplimiento de comunicaciones con Microsoft Teams
author: robmazz
ms.author: robmazz
manager: laurawi
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: anwara
description: Información sobre el cumplimiento de las comunicaciones, parte del conjunto de soluciones de riesgo de Insider, desde la perspectiva Microsoft Teams (esto forma parte de la funcionalidad de cumplimiento de comunicaciones M365).
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: cf032669edc7255571e2501774ac0d0ee0df47d8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121538"
---
# <a name="communication-compliance-with-microsoft-teams"></a><span data-ttu-id="4f2c4-103">Cumplimiento de comunicaciones con Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4f2c4-103">Communication compliance with Microsoft Teams</span></span>

<span data-ttu-id="4f2c4-104">El cumplimiento de las comunicaciones es una solución de riesgo de insider en Microsoft 365 que ayuda a minimizar los riesgos de comunicación al ayudarle a detectar, capturar y actuar en mensajes inadecuados en su organización.</span><span class="sxs-lookup"><span data-stu-id="4f2c4-104">Communication compliance is an insider risk solution in Microsoft 365 that helps minimize communication risks by helping you detect, capture, and act on inappropriate messages in your organization.</span></span>

<span data-ttu-id="4f2c4-105">Por Microsoft Teams, el cumplimiento de [](/microsoft-365/compliance/communication-compliance-feature-reference) las comunicaciones ayuda a identificar los siguientes tipos de contenido inadecuado en Teams canales o en chats grupales y de 1:1:</span><span class="sxs-lookup"><span data-stu-id="4f2c4-105">For Microsoft Teams, communication compliance helps identify the [following types](/microsoft-365/compliance/communication-compliance-feature-reference) of inappropriate content in Teams channels or in 1:1 and group chats:</span></span>

- <span data-ttu-id="4f2c4-106">Lenguaje ofensivo, profano y acosante</span><span class="sxs-lookup"><span data-stu-id="4f2c4-106">Offensive, profane, and harassing language</span></span>
- <span data-ttu-id="4f2c4-107">Imágenes de adultos, radas y peludos</span><span class="sxs-lookup"><span data-stu-id="4f2c4-107">Adult, racy, and gory images</span></span>
- <span data-ttu-id="4f2c4-108">Uso compartido de información confidencial</span><span class="sxs-lookup"><span data-stu-id="4f2c4-108">Sharing of sensitive information</span></span>

<span data-ttu-id="4f2c4-109">Para obtener más información sobre el cumplimiento de las comunicaciones y cómo configurar directivas para su organización, vea Cumplimiento de comunicaciones [en Microsoft 365](/microsoft-365/compliance/communication-compliance).</span><span class="sxs-lookup"><span data-stu-id="4f2c4-109">For more information on communication compliance and how to configure policies for your organization, see [Communication compliance in Microsoft 365](/microsoft-365/compliance/communication-compliance).</span></span>

## <a name="how-to-use-communication-compliance-in-microsoft-teams"></a><span data-ttu-id="4f2c4-110">Cómo usar el cumplimiento de comunicaciones en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4f2c4-110">How to use communication compliance in Microsoft Teams</span></span>

<span data-ttu-id="4f2c4-111">El cumplimiento y Microsoft Teams comunicación están estrechamente integrados y pueden ayudar a minimizar los riesgos de comunicación en su organización.</span><span class="sxs-lookup"><span data-stu-id="4f2c4-111">Communication compliance and Microsoft Teams are tightly integrated and can help minimize communication risks in your organization.</span></span> <span data-ttu-id="4f2c4-112">Después de configurar las primeras directivas de cumplimiento de comunicaciones, puede administrar de forma activa los mensajes Microsoft Teams y el contenido que se marca automáticamente en las alertas.</span><span class="sxs-lookup"><span data-stu-id="4f2c4-112">After you've configured your first communication compliance policies, you can actively manage inappropriate Microsoft Teams messages and content that is automatically flagged in alerts.</span></span>

### <a name="getting-started"></a><span data-ttu-id="4f2c4-113">Introducción</span><span class="sxs-lookup"><span data-stu-id="4f2c4-113">Getting started</span></span>

<span data-ttu-id="4f2c4-114">Empezar a trabajar con el cumplimiento [](/microsoft-365/compliance/communication-compliance-plan) de las comunicaciones en Microsoft Teams comienza con la planificación y creación de directivas predefinidas o personalizadas para identificar actividades de usuario inadecuadas en Teams canales o en 1:1 y grupos.</span><span class="sxs-lookup"><span data-stu-id="4f2c4-114">Getting started with communication compliance in Microsoft Teams begins with [planning](/microsoft-365/compliance/communication-compliance-plan) and creating pre-defined or custom policies to identify inappropriate user activities in Teams channels or in 1:1 and groups.</span></span> <span data-ttu-id="4f2c4-115">Tenga en cuenta que necesitará [](/microsoft-365/compliance/communication-compliance-configure) configurar algunos permisos y requisitos previos básicos como parte del proceso de configuración.</span><span class="sxs-lookup"><span data-stu-id="4f2c4-115">Keep in mind that you'll need to [configure](/microsoft-365/compliance/communication-compliance-configure) some permissions and basic prerequisites as part of the configuration process.</span></span>

<span data-ttu-id="4f2c4-116">Teams administradores pueden configurar directivas de cumplimiento de comunicaciones en los siguientes niveles:</span><span class="sxs-lookup"><span data-stu-id="4f2c4-116">Teams administrators can configure communication compliance policies at the following levels:</span></span>

- <span data-ttu-id="4f2c4-117">**Nivel de usuario:** las directivas de este nivel se aplican a un usuario Teams usuario o se pueden aplicar a todos los Teams usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="4f2c4-117">**User level**: Policies at this level apply to an individual Teams user or may be applied to all Teams users in your organization.</span></span> <span data-ttu-id="4f2c4-118">Estas directivas cubren los mensajes que estos usuarios pueden enviar en chats grupales o 1:1.</span><span class="sxs-lookup"><span data-stu-id="4f2c4-118">These policies cover messages that these users may send in 1:1 or group chats.</span></span> <span data-ttu-id="4f2c4-119">Las comunicaciones de chat para los usuarios se supervisan automáticamente en todos los Microsoft Teams donde los usuarios son miembros.</span><span class="sxs-lookup"><span data-stu-id="4f2c4-119">Chat communications for the users are automatically monitored across all Microsoft Teams where the users are a member.</span></span>
- <span data-ttu-id="4f2c4-120">**Teams:** las directivas de este nivel se aplican a un canal de Microsoft Team.</span><span class="sxs-lookup"><span data-stu-id="4f2c4-120">**Teams level**: Policies at this level apply to a Microsoft Team channel.</span></span> <span data-ttu-id="4f2c4-121">Estas directivas abarcan solo los mensajes enviados Teams canal.</span><span class="sxs-lookup"><span data-stu-id="4f2c4-121">These policies cover messages sent in the Teams channel only.</span></span>

### <a name="act-on-inappropriate-messages-in-microsoft-teams"></a><span data-ttu-id="4f2c4-122">Actuar sobre mensajes inadecuados en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4f2c4-122">Act on inappropriate messages in Microsoft Teams</span></span>

<span data-ttu-id="4f2c4-123">Después de configurar las directivas y haber recibido alertas de cumplimiento de comunicaciones para mensajes Microsoft Teams, es el momento de que los revisores de cumplimiento de su organización tomen medidas sobre estos mensajes.</span><span class="sxs-lookup"><span data-stu-id="4f2c4-123">After you have configured your policies and have received communication compliance alerts for Microsoft Teams messages, it's time for compliance reviewers in your organization to take action on these messages.</span></span> <span data-ttu-id="4f2c4-124">Los revisores pueden ayudar a proteger su organización revisando las alertas de cumplimiento de comunicaciones y quitando los mensajes marcados de la vista en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="4f2c4-124">Reviewers can help safeguard your organization by reviewing communication compliance alerts and removing flagged messages from view in Microsoft Teams.</span></span>

![Quitar un mensaje en Teams](./media/communication-compliance-remove-teams-message.png)

<span data-ttu-id="4f2c4-126">Los mensajes y el contenido eliminados se reemplazan por notificaciones para los visores que explican que el mensaje o el contenido se ha quitado y qué directiva se aplica a la eliminación.</span><span class="sxs-lookup"><span data-stu-id="4f2c4-126">Removed messages and content are replaced with notifications for viewers explaining that the message or content has been removed and what policy is applicable to the removal.</span></span> <span data-ttu-id="4f2c4-127">Al remitente del mensaje o contenido quitado también se le notifica el estado de eliminación y se le proporciona el contenido original del mensaje para el contexto relacionado con su eliminación.</span><span class="sxs-lookup"><span data-stu-id="4f2c4-127">The sender of the removed message or content is also notified of the removal status and provided with original message content for context relating to its removal.</span></span> <span data-ttu-id="4f2c4-128">El remitente también puede ver la condición de directiva específica que se aplica a la eliminación del mensaje.</span><span class="sxs-lookup"><span data-stu-id="4f2c4-128">The sender can also view the specific policy condition that applies to the message removal.</span></span>

<span data-ttu-id="4f2c4-129">Ejemplo de sugerencia de directiva que ve el remitente:</span><span class="sxs-lookup"><span data-stu-id="4f2c4-129">Example of policy tip seen by sender:</span></span>

![Sugerencia de directiva para remitente](./media/communication-compliance-warning-1.png)

<span data-ttu-id="4f2c4-131">Ejemplo de notificación de condición de directiva que ha visto el remitente:</span><span class="sxs-lookup"><span data-stu-id="4f2c4-131">Example of policy condition notification seen by the sender:</span></span>

![Información de condición de directiva para el remitente](./media/communication-compliance-warning-2.png)

<span data-ttu-id="4f2c4-133">Ejemplo de sugerencia de directiva que ve el destinatario:</span><span class="sxs-lookup"><span data-stu-id="4f2c4-133">Example of policy tip seen by recipient:</span></span>

![Sugerencia de directiva para el destinatario](./media/communication-compliance-warning-3.png)