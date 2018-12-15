---
title: Uso compartido de llamada y el grupo de atención de llamadas en Microsoft Teams
ms.author: lolaj
author: lolaj
manager: serdars
ms.date: 12/13/2018
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service:
- msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Uso compartido de llamadas y respuesta de llamadas en grupo permite a los usuarios compartir las llamadas entrantes con compañeros de trabajo para que las llamadas se pueden capturar cuando el usuario no está disponible.
ms.openlocfilehash: 7f05484f0ba780eb8ed00df68b455d8555c1e4c0
ms.sourcegitcommit: 5f7e078125f810a9e9a89052854ef63916afe7d3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/14/2018
ms.locfileid: "27283154"
---
# <a name="call-sharing-and-group-call-pickup-in-microsoft-teams"></a><span data-ttu-id="8126c-103">Uso compartido de llamada y el grupo de atención de llamadas en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8126c-103">Call sharing and group call pickup in Microsoft Teams</span></span>

<span data-ttu-id="8126c-104">El uso compartido de llamada y el grupo de llamadas pickup características de recurso compartido de permiten a los usuarios de Microsoft Teams sus las llamadas entrantes con compañeros de trabajo para que los compañeros pueden responder a las llamadas que se producen mientras el usuario no está disponible.</span><span class="sxs-lookup"><span data-stu-id="8126c-104">The call sharing and group call pickup features of Microsoft Teams let users share their incoming calls with colleagues so that the colleagues can answer calls that occur while the user is unavailable.</span></span>

<span data-ttu-id="8126c-105">Respuesta de llamadas en grupo es menos problemática para los destinatarios que otras formas de llamada de uso compartido (por ejemplo, el desvío de llamadas o las llamadas simultáneas) debido a que los usuarios pueden configurar la forma en que deseen recibir una notificación de una llamada entrante compartida (a través de notificación de audio y vídeo, solo, visual pancarta o en la aplicación de los equipos), y pueden decidir si se debe responder a la llamada.</span><span class="sxs-lookup"><span data-stu-id="8126c-105">Group call pickup is less disruptive to recipients than other forms of call sharing (such as call forwarding or simultaneous ringing) because users can configure how they want to be notified of an incoming shared call (via audio and visual notification, visual only, or banner in the Teams app), and they can decide whether to answer it.</span></span>

<span data-ttu-id="8126c-106">Para compartir las llamadas con otros usuarios, un usuario crea un grupo de llamada y agrega a los usuarios que desean compartir sus llamadas con.</span><span class="sxs-lookup"><span data-stu-id="8126c-106">To share calls with others, a user creates a call group and adds the users they want to share their calls with.</span></span> <span data-ttu-id="8126c-107">A continuación, que elija una llamada simultánea o reenvían configuración.</span><span class="sxs-lookup"><span data-stu-id="8126c-107">Then they choose a simultaneous ring or forward setting.</span></span> <span data-ttu-id="8126c-108">Para obtener información detallada, vea [llamar anillo desvío y simultánea en los equipos](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) .</span><span class="sxs-lookup"><span data-stu-id="8126c-108">See [Call forwarding and simultaneous ring in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) for details.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8126c-109">Los usuarios, el propietario del grupo de llamada y los miembros del grupo de llamada deben estar en modo de implementación sólo los equipos.</span><span class="sxs-lookup"><span data-stu-id="8126c-109">Users, the call group owner, and members of the call group must be in Teams Only deployment mode.</span></span> <span data-ttu-id="8126c-110">Para obtener más detalles sobre los modos de implementación de los equipos, vea [Descripción de los equipos de Microsoft y Skype para la interoperabilidad y coexistencia de negocio](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span><span class="sxs-lookup"><span data-stu-id="8126c-110">For more details on Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="8126c-111">Se requiere una licencia</span><span class="sxs-lookup"><span data-stu-id="8126c-111">License required</span></span>

<span data-ttu-id="8126c-112">Los usuarios deben ser Enterprise Voice está habilitado para configurar y uso compartido de llamada y respuesta de llamadas de grupo.</span><span class="sxs-lookup"><span data-stu-id="8126c-112">Users must be Enterprise Voice enabled to set up and use call sharing and group call pickup.</span></span> <span data-ttu-id="8126c-113">Para obtener más información sobre el modelo de licencias, vea [licencias de Office 365 para equipos de Microsoft](office-365-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="8126c-113">For additional details on the licensing model, See [Office 365 licensing for Microsoft Teams](office-365-licensing.md).</span></span>

## <a name="configure-group-call-pickup"></a><span data-ttu-id="8126c-114">Configurar respuesta de llamadas en grupo</span><span class="sxs-lookup"><span data-stu-id="8126c-114">Configure group call pickup</span></span>

<span data-ttu-id="8126c-115">Para configurar la respuesta de llamadas en grupo, un usuario en primer lugar configura un grupo de llamada y, a continuación, agrega los usuarios que desean compartir sus llamadas con.</span><span class="sxs-lookup"><span data-stu-id="8126c-115">To set up group call pickup, a user first configures a call group and then adds the users they want to share their calls with.</span></span> <span data-ttu-id="8126c-116">A continuación, se elige una llamada simultánea o configuración de reenvío de llamadas.</span><span class="sxs-lookup"><span data-stu-id="8126c-116">Then, they choose a simultaneous ring or call forward setting.</span></span> <span data-ttu-id="8126c-117">Para obtener más información, vea [anillo desvío y simultánea en los equipos de llamadas](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e).</span><span class="sxs-lookup"><span data-stu-id="8126c-117">For more information, see [Call forwarding and simultaneous ring in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e).</span></span>

<span data-ttu-id="8126c-118">Llamar a la creación del grupo y notificación preferencias son las características de controlado por el usuario; no es necesario que los administradores configurar estas características para sus usuarios.</span><span class="sxs-lookup"><span data-stu-id="8126c-118">Call group creation and notification preferences are user-driven features; administrators do not have to configure these features for their users.</span></span> <span data-ttu-id="8126c-119">No se puede crear grupos de llamada de grupos de seguridad o grupos de Office 365; se deben crear en los equipos.</span><span class="sxs-lookup"><span data-stu-id="8126c-119">Call groups cannot be created from security groups or Office 365 groups; they must be created in Teams.</span></span>

<span data-ttu-id="8126c-120">Los administradores no pueden impedir que los usuarios crear grupos y cambiar otro valor de configuración de recogida de llamada.</span><span class="sxs-lookup"><span data-stu-id="8126c-120">Admins cannot prevent users from creating groups and changing other call pickup setting.</span></span> <span data-ttu-id="8126c-121">No se bloquea la funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="8126c-121">The functionality is not blocked.</span></span>

## <a name="limitations"></a><span data-ttu-id="8126c-122">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="8126c-122">Limitations</span></span>

<span data-ttu-id="8126c-123">Un inquilino puede contener un máximo de grupos de llamada 32.768.</span><span class="sxs-lookup"><span data-stu-id="8126c-123">A tenant can contain a maximum of 32,768 call groups.</span></span> <span data-ttu-id="8126c-124">Puede haber un máximo de 5 usuarios en cada grupo de llamada.</span><span class="sxs-lookup"><span data-stu-id="8126c-124">There can be a maximum of 5 users in each call group.</span></span> 

## <a name="more-information"></a><span data-ttu-id="8126c-125">Más información</span><span class="sxs-lookup"><span data-stu-id="8126c-125">More information</span></span>

[<span data-ttu-id="8126c-126">Desvío de llamadas y la llamada simultánea en los equipos</span><span class="sxs-lookup"><span data-stu-id="8126c-126">Call forwarding and simultaneous ring in Teams</span></span>](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)