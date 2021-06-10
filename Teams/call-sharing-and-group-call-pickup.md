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
description: El uso compartido de llamadas y la recogida de llamadas grupales permiten a los usuarios compartir llamadas entrantes con compañeros de trabajo para que las llamadas se puedan capturar cuando el usuario no esté disponible.
ms.openlocfilehash: 98094ff0b4b5d7b037915273b2c2730d42517c22
ms.sourcegitcommit: 90615674e9703aa5ea32be64ab3638aa30e83127
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2021
ms.locfileid: "52717841"
---
# <a name="call-sharing-and-group-call-pickup-in-microsoft-teams"></a><span data-ttu-id="6760b-103">Compartir llamadas y atender llamadas grupales en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6760b-103">Call sharing and group call pickup in Microsoft Teams</span></span>

<span data-ttu-id="6760b-104">Las características de uso compartido de llamadas y de recogida de llamadas grupales de Microsoft Teams permiten a los usuarios compartir sus llamadas entrantes con compañeros para que los compañeros puedan responder a las llamadas que se producen mientras el usuario no está disponible.</span><span class="sxs-lookup"><span data-stu-id="6760b-104">The call sharing and group call pickup features of Microsoft Teams let users share their incoming calls with colleagues so that the colleagues can answer calls that occur while the user is unavailable.</span></span>

<span data-ttu-id="6760b-105">La recogida de llamadas grupales es menos perjudicial para los destinatarios que otras formas de uso compartido de llamadas (como el reenvío de llamadas o la llamada simultánea), ya que los usuarios pueden configurar cómo quieren que se les notifique de una llamada compartida entrante (a través de una notificación visual y de audio, solo visual o banner en la aplicación de Teams) y pueden decidir si la responden.</span><span class="sxs-lookup"><span data-stu-id="6760b-105">Group call pickup is less disruptive to recipients than other forms of call sharing (such as call forwarding or simultaneous ringing) because users can configure how they want to be notified of an incoming shared call (via audio and visual notification, visual only, or banner in the Teams app), and they can decide whether to answer it.</span></span>

<span data-ttu-id="6760b-106">Para compartir llamadas con otros usuarios, un usuario crea un grupo de llamadas y agrega los usuarios con los que desea compartir sus llamadas.</span><span class="sxs-lookup"><span data-stu-id="6760b-106">To share calls with others, a user creates a call group and adds the users they want to share their calls with.</span></span> <span data-ttu-id="6760b-107">A continuación, eligen una configuración de llamada o reenvío simultánea.</span><span class="sxs-lookup"><span data-stu-id="6760b-107">Then they choose a simultaneous ring or forward setting.</span></span> <span data-ttu-id="6760b-108">Vea [Reenvío de llamadas y llamada simultánea en Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="6760b-108">See [Call forwarding and simultaneous ring in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) for details.</span></span> <span data-ttu-id="6760b-109">Ten en cuenta que los dispositivos móviles solo recibirán notificaciones si están configurados para banner y tono de llamada.</span><span class="sxs-lookup"><span data-stu-id="6760b-109">Note that mobile devices will only get notified if they're set for banner and ringtone.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6760b-110">Los usuarios, el propietario del grupo de llamadas y los miembros del grupo de llamadas deben estar Teams modo de implementación solo.</span><span class="sxs-lookup"><span data-stu-id="6760b-110">Users, the call group owner, and members of the call group must be in Teams Only deployment mode.</span></span> <span data-ttu-id="6760b-111">Para obtener más información sobre Teams de implementación, vea Comprender [Microsoft Teams y Skype Empresarial coexistencia e interoperabilidad](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span><span class="sxs-lookup"><span data-stu-id="6760b-111">For more details on Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="6760b-112">Licencia necesaria</span><span class="sxs-lookup"><span data-stu-id="6760b-112">License required</span></span>

<span data-ttu-id="6760b-113">Los usuarios deben tener asignada una Microsoft Teams Sistema telefónico para configurar y usar el uso compartido de llamadas y la recogida de llamadas grupales.</span><span class="sxs-lookup"><span data-stu-id="6760b-113">Users must be assigned a Microsoft Teams Phone System license to set up and use call sharing and group call pickup.</span></span> <span data-ttu-id="6760b-114">Para obtener más información sobre el modelo de licencias, vea Esto es lo [que obtiene](https://docs.microsoft.com/MicrosoftTeams/here-s-what-you-get-with-phone-system)con Sistema telefónico .</span><span class="sxs-lookup"><span data-stu-id="6760b-114">For additional details on the licensing model, see [Here's what you get with Phone System](https://docs.microsoft.com/MicrosoftTeams/here-s-what-you-get-with-phone-system).</span></span>

## <a name="configure-group-call-pickup"></a><span data-ttu-id="6760b-115">Configurar la recogida de llamadas grupales</span><span class="sxs-lookup"><span data-stu-id="6760b-115">Configure group call pickup</span></span>

<span data-ttu-id="6760b-116">Para configurar la recogida de llamadas grupales, un usuario configura primero un grupo de llamadas (esto no es lo mismo que un grupo de seguridad o un grupo de Microsoft 365) y, a continuación, agrega los usuarios con los que desea compartir sus llamadas.</span><span class="sxs-lookup"><span data-stu-id="6760b-116">To set up group call pickup, a user first configures a call group (this is not the same as a security group or a Microsoft 365 group), and then adds the users they want to share their calls with.</span></span> <span data-ttu-id="6760b-117">Después, eligen una configuración de llamada simultánea o de reenvío de llamada.</span><span class="sxs-lookup"><span data-stu-id="6760b-117">Then, they choose a simultaneous ring or call forward setting.</span></span> <span data-ttu-id="6760b-118">Para obtener más información y procedimientos paso a [paso,](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)vea Reenvío de llamadas y llamada simultánea en Teams .</span><span class="sxs-lookup"><span data-stu-id="6760b-118">For more information and step-by-step procedures, see [Call forwarding and simultaneous ring in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e).</span></span>

<span data-ttu-id="6760b-119">Las preferencias de notificación y creación de grupos de llamadas son características controladas por el usuario; los administradores no tienen que configurar estas características para sus usuarios.</span><span class="sxs-lookup"><span data-stu-id="6760b-119">Call group creation and notification preferences are user-driven features; administrators do not have to configure these features for their users.</span></span> <span data-ttu-id="6760b-120">Los grupos de llamadas no se pueden crear a partir de grupos de seguridad Microsoft 365 grupos; deben crearse en Teams.</span><span class="sxs-lookup"><span data-stu-id="6760b-120">Call groups cannot be created from security groups or Microsoft 365 groups; they must be created in Teams.</span></span>

<span data-ttu-id="6760b-121">Los administradores deben habilitar los grupos de llamadas a través de la configuración **TeamsCallingPolicy AllowCallGroups** para un usuario.</span><span class="sxs-lookup"><span data-stu-id="6760b-121">Admins should enable call groups via the **TeamsCallingPolicy AllowCallGroups** setting for a user.</span></span> <span data-ttu-id="6760b-122">Los administradores también pueden habilitar esta opción Teams portal de administración.</span><span class="sxs-lookup"><span data-stu-id="6760b-122">Admins can also enable this via Teams Admin portal.</span></span>  <span data-ttu-id="6760b-123">Además, el usuario configurado también puede configurar sus grupos de llamadas a través del cliente directamente.</span><span class="sxs-lookup"><span data-stu-id="6760b-123">In addition, the configured user can also configure their call groups via the client directly.</span></span> <span data-ttu-id="6760b-124">Los administradores o los usuarios finales no pueden bloquear la configuración entre sí, pero Teams portal de administración y Teams cliente deben mostrar esta relación con precisión en ambos lugares.</span><span class="sxs-lookup"><span data-stu-id="6760b-124">Admin or end users cannot block the configuration by each other, but Teams Admin portal and Teams client should show this relationship accurately in both places.</span></span> 

<span data-ttu-id="6760b-125">Importante: Cuando los administradores desactivan los grupos de llamadas para los usuarios (después de que se haya activado y se hayan configurado las relaciones del grupo de llamadas), los administradores tienen que limpiar las relaciones de grupo de llamadas para los usuarios del centro de administración de Teams para evitar un enrutamiento incorrecto de llamadas.</span><span class="sxs-lookup"><span data-stu-id="6760b-125">Important: When admins turn off call groups for users (after it has been turned on and the call group relationships are configured), the admins have to clean up the call group relationships for users in the Teams admin center to avoid incorrect call routing.</span></span> 

## <a name="limitations"></a><span data-ttu-id="6760b-126">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="6760b-126">Limitations</span></span>

<span data-ttu-id="6760b-127">Cada grupo de llamadas configurado puede tener un máximo de 25 usuarios o 32.768 caracteres.</span><span class="sxs-lookup"><span data-stu-id="6760b-127">Each configured call group can have a maximum of 25 users or 32,768 characters.</span></span> 

## <a name="more-information"></a><span data-ttu-id="6760b-128">Más información</span><span class="sxs-lookup"><span data-stu-id="6760b-128">More information</span></span>

[<span data-ttu-id="6760b-129">Reenvío de llamadas y llamada simultánea en Teams</span><span class="sxs-lookup"><span data-stu-id="6760b-129">Call forwarding and simultaneous ring in Teams</span></span>](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)
