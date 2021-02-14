---
title: Compartir llamadas y atender llamadas grupales
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 02/19/2019
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.users.voice.groupcallpickup.tooltip
- ms.teamsadmincenter.users.voice.callorderanddelay.tooltip
- Phone System
- seo-marvel-mar2020
description: El uso compartido de llamadas y la recogida de llamadas grupales permiten a los usuarios compartir llamadas entrantes con colegas para que las llamadas se puedan capturar cuando el usuario no esté disponible.
ms.openlocfilehash: 825e174a6b6f68adcc7b5aade212689b01309c24
ms.sourcegitcommit: 6b24c82837ca2c11f450a162ca4fab3dfa4ac8d4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620731"
---
# <a name="call-sharing-and-group-call-pickup-in-microsoft-teams"></a><span data-ttu-id="c27ee-103">Compartir llamadas y atender llamadas grupales en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c27ee-103">Call sharing and group call pickup in Microsoft Teams</span></span>

<span data-ttu-id="c27ee-104">Las características de uso compartido de llamadas y recogida de llamadas grupales de Microsoft Teams permiten a los usuarios compartir sus llamadas entrantes con compañeros para que estos puedan responder a las llamadas que se producen mientras el usuario no está disponible.</span><span class="sxs-lookup"><span data-stu-id="c27ee-104">The call sharing and group call pickup features of Microsoft Teams let users share their incoming calls with colleagues so that the colleagues can answer calls that occur while the user is unavailable.</span></span>

<span data-ttu-id="c27ee-105">La recogida de llamadas grupales es menos molesta para los destinatarios que otras formas de uso compartido de llamadas (como el reenvío de llamadas o las llamadas simultáneas) porque los usuarios pueden configurar cómo quieren que se les notifique sobre una llamada compartida entrante (a través de una notificación visual y de audio, solo visual o de banner en la aplicación Teams), y pueden decidir si responden.</span><span class="sxs-lookup"><span data-stu-id="c27ee-105">Group call pickup is less disruptive to recipients than other forms of call sharing (such as call forwarding or simultaneous ringing) because users can configure how they want to be notified of an incoming shared call (via audio and visual notification, visual only, or banner in the Teams app), and they can decide whether to answer it.</span></span>

<span data-ttu-id="c27ee-106">Para compartir llamadas con otras personas, un usuario crea un grupo de llamadas y agrega los usuarios con los que desea compartir sus llamadas.</span><span class="sxs-lookup"><span data-stu-id="c27ee-106">To share calls with others, a user creates a call group and adds the users they want to share their calls with.</span></span> <span data-ttu-id="c27ee-107">A continuación, eligen una configuración de llamada simultánea o de reenvío.</span><span class="sxs-lookup"><span data-stu-id="c27ee-107">Then they choose a simultaneous ring or forward setting.</span></span> <span data-ttu-id="c27ee-108">Consulte [El reenvío de llamadas y las llamadas simultáneas en Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) para obtener detalles.</span><span class="sxs-lookup"><span data-stu-id="c27ee-108">See [Call forwarding and simultaneous ring in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) for details.</span></span> <span data-ttu-id="c27ee-109">Ten en cuenta que los dispositivos móviles solo recibirán una notificación si están configurados para banner y tono.</span><span class="sxs-lookup"><span data-stu-id="c27ee-109">Note that mobile devices will only get notified if they're set for banner and ringtone.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c27ee-110">Los usuarios, el propietario del grupo de llamadas y los miembros del grupo de llamadas deben estar en el modo de implementación Solo en Teams.</span><span class="sxs-lookup"><span data-stu-id="c27ee-110">Users, the call group owner, and members of the call group must be in Teams Only deployment mode.</span></span> <span data-ttu-id="c27ee-111">Para obtener más información sobre los modos de implementación de Teams, consulte [Comprender la coexistencia](teams-and-skypeforbusiness-coexistence-and-interoperability.md) e interoperabilidad de Microsoft Teams y Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="c27ee-111">For more details on Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="c27ee-112">Licencia necesaria</span><span class="sxs-lookup"><span data-stu-id="c27ee-112">License required</span></span>

<span data-ttu-id="c27ee-113">Los usuarios deben estar Telefonía IP empresarial para configurar y usar el uso compartido de llamadas y la recogida de llamadas grupales.</span><span class="sxs-lookup"><span data-stu-id="c27ee-113">Users must be Enterprise Voice enabled to set up and use call sharing and group call pickup.</span></span> <span data-ttu-id="c27ee-114">Para obtener más información sobre el modelo de licencias, consulte la [descripción del servicio Microsoft Teams.](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)</span><span class="sxs-lookup"><span data-stu-id="c27ee-114">For additional details on the licensing model, see [Microsoft Teams service description](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span></span>

## <a name="configure-group-call-pickup"></a><span data-ttu-id="c27ee-115">Configurar la recogida de llamadas grupales</span><span class="sxs-lookup"><span data-stu-id="c27ee-115">Configure group call pickup</span></span>

<span data-ttu-id="c27ee-116">Para configurar la recogida de llamadas grupales, un usuario configura primero un grupo de llamadas (esto no es lo mismo que un grupo de seguridad o un grupo de Microsoft 365) y, a continuación, agrega a los usuarios con los que desea compartir las llamadas.</span><span class="sxs-lookup"><span data-stu-id="c27ee-116">To set up group call pickup, a user first configures a call group (this is not the same as a security group or a Microsoft 365 group), and then adds the users they want to share their calls with.</span></span> <span data-ttu-id="c27ee-117">A continuación, eligen una configuración de llamada simultánea o de reenvío de llamada.</span><span class="sxs-lookup"><span data-stu-id="c27ee-117">Then, they choose a simultaneous ring or call forward setting.</span></span> <span data-ttu-id="c27ee-118">Para obtener más información y procedimientos paso a paso, vea El reenvío de llamadas y las llamadas [simultáneas en Teams.](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)</span><span class="sxs-lookup"><span data-stu-id="c27ee-118">For more information and step-by-step procedures, see [Call forwarding and simultaneous ring in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e).</span></span>

<span data-ttu-id="c27ee-119">Las preferencias de notificación y creación de grupos de llamadas son características controladas por el usuario; los administradores no tienen que configurar estas características para sus usuarios.</span><span class="sxs-lookup"><span data-stu-id="c27ee-119">Call group creation and notification preferences are user-driven features; administrators do not have to configure these features for their users.</span></span> <span data-ttu-id="c27ee-120">Los grupos de llamadas no se pueden crear desde grupos de seguridad ni grupos de Microsoft 365; deben crearse en Teams.</span><span class="sxs-lookup"><span data-stu-id="c27ee-120">Call groups cannot be created from security groups or Microsoft 365 groups; they must be created in Teams.</span></span>

<span data-ttu-id="c27ee-121">Los administradores deben habilitar los grupos de llamadas a través de la configuración **TeamsCallingPolicy AllowCallGroups** para un usuario.</span><span class="sxs-lookup"><span data-stu-id="c27ee-121">Admins should enable call groups via the **TeamsCallingPolicy AllowCallGroups** setting for a user.</span></span> <span data-ttu-id="c27ee-122">Los administradores también pueden habilitar esta opción a través del Portal de administración de Teams.</span><span class="sxs-lookup"><span data-stu-id="c27ee-122">Admins can also enable this via Teams Admin portal.</span></span>  <span data-ttu-id="c27ee-123">Además, el usuario configurado también puede configurar sus grupos de llamadas directamente a través del cliente.</span><span class="sxs-lookup"><span data-stu-id="c27ee-123">In addition, the configured user can also configure their call groups via the client directly.</span></span> <span data-ttu-id="c27ee-124">El administrador o los usuarios finales no pueden bloquear la configuración entre sí, pero el Portal de administración de Teams y el cliente de Teams deben mostrar esta relación de forma precisa en ambos lugares.</span><span class="sxs-lookup"><span data-stu-id="c27ee-124">Admin or end users cannot block the configuration by each other, but Teams Admin portal and Teams client should show this relationship accurately in both places.</span></span> 

<span data-ttu-id="c27ee-125">Importante: Cuando los administradores desactivan los grupos de llamadas para los usuarios (después de que se ha activado y las relaciones del grupo de llamadas están configuradas), los administradores tienen que limpiar las relaciones del grupo de llamadas para los usuarios en el centro de administración de Teams para evitar un enrutamiento de llamada incorrecto.</span><span class="sxs-lookup"><span data-stu-id="c27ee-125">Important: When admins turn off call groups for users (after it has been turned on and the call group relationships are configured), the admins have to clean up the call group relationships for users in the Teams admin center to avoid incorrect call routing.</span></span> 

## <a name="limitations"></a><span data-ttu-id="c27ee-126">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="c27ee-126">Limitations</span></span>

<span data-ttu-id="c27ee-127">Un inquilino puede contener un máximo de 32.768 grupos de llamadas.</span><span class="sxs-lookup"><span data-stu-id="c27ee-127">A tenant can contain a maximum of 32,768 call groups.</span></span> <span data-ttu-id="c27ee-128">Puede haber un máximo de 25 usuarios en cada grupo de llamadas.</span><span class="sxs-lookup"><span data-stu-id="c27ee-128">There can be a maximum of 25 users in each call group.</span></span> 

## <a name="more-information"></a><span data-ttu-id="c27ee-129">Más información</span><span class="sxs-lookup"><span data-stu-id="c27ee-129">More information</span></span>

[<span data-ttu-id="c27ee-130">Reenvío de llamadas y llamadas simultáneas en Teams</span><span class="sxs-lookup"><span data-stu-id="c27ee-130">Call forwarding and simultaneous ring in Teams</span></span>](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)
