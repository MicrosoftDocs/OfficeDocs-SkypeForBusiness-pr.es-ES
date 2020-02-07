---
title: Compartir llamadas y atender llamadas grupales en Microsoft Teams
ms.author: lolaj
author: LolaJacobsen
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
description: El uso compartido de llamadas y la recogida de llamadas de Grupo permiten a los usuarios compartir llamadas entrantes con colegas para que las llamadas se puedan capturar cuando el usuario no está disponible.
ms.openlocfilehash: c3a47c892940762807a86d6690fa59520f137960
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824558"
---
# <a name="call-sharing-and-group-call-pickup-in-microsoft-teams"></a><span data-ttu-id="1c672-103">Compartir llamadas y atender llamadas grupales en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1c672-103">Call sharing and group call pickup in Microsoft Teams</span></span>

<span data-ttu-id="1c672-104">Las características uso compartido de llamadas y recogida de llamadas grupales de Microsoft Teams permiten a los usuarios compartir sus llamadas entrantes con colegas para que los colegas puedan responder a llamadas que se produzcan mientras el usuario no está disponible.</span><span class="sxs-lookup"><span data-stu-id="1c672-104">The call sharing and group call pickup features of Microsoft Teams let users share their incoming calls with colleagues so that the colleagues can answer calls that occur while the user is unavailable.</span></span>

<span data-ttu-id="1c672-105">La recogida de llamadas grupales es menos disruptiva para los destinatarios que otras formas de uso compartido de llamadas (como el desvío de llamadas o el timbre simultáneo) porque los usuarios pueden configurar cómo desean recibir una notificación de una llamada compartida entrante (mediante una notificación de audio y vídeo, solo visual, o banner en la aplicación de Teams) y pueden decidir si desea contestarlos.</span><span class="sxs-lookup"><span data-stu-id="1c672-105">Group call pickup is less disruptive to recipients than other forms of call sharing (such as call forwarding or simultaneous ringing) because users can configure how they want to be notified of an incoming shared call (via audio and visual notification, visual only, or banner in the Teams app), and they can decide whether to answer it.</span></span>

<span data-ttu-id="1c672-106">Para compartir llamadas con otras personas, un usuario crea un grupo de llamadas y agrega los usuarios con los que desean compartir sus llamadas.</span><span class="sxs-lookup"><span data-stu-id="1c672-106">To share calls with others, a user creates a call group and adds the users they want to share their calls with.</span></span> <span data-ttu-id="1c672-107">Luego, eligen una configuración de llamada simultánea o de reenvío.</span><span class="sxs-lookup"><span data-stu-id="1c672-107">Then they choose a simultaneous ring or forward setting.</span></span> <span data-ttu-id="1c672-108">Para obtener más información [, consulta desvío de llamadas y llamadas simultáneas en Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) .</span><span class="sxs-lookup"><span data-stu-id="1c672-108">See [Call forwarding and simultaneous ring in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) for details.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1c672-109">Los usuarios, el propietario del grupo de llamadas y los miembros del grupo de llamadas deben estar en el modo de implementación solo de Teams.</span><span class="sxs-lookup"><span data-stu-id="1c672-109">Users, the call group owner, and members of the call group must be in Teams Only deployment mode.</span></span> <span data-ttu-id="1c672-110">Para obtener más información sobre los modos de implementación de Teams, consulte [comprender la coexistencia y la interoperabilidad de Microsoft Teams y Skype empresarial](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span><span class="sxs-lookup"><span data-stu-id="1c672-110">For more details on Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="1c672-111">Licencia requerida</span><span class="sxs-lookup"><span data-stu-id="1c672-111">License required</span></span>

<span data-ttu-id="1c672-112">Los usuarios deben tener habilitada la telefonía IP empresarial para configurar y usar el uso compartido de llamadas y la recogida de llamadas grupales.</span><span class="sxs-lookup"><span data-stu-id="1c672-112">Users must be Enterprise Voice enabled to set up and use call sharing and group call pickup.</span></span> <span data-ttu-id="1c672-113">Para obtener más información sobre el modelo de licencias, consulte [licencias de Office 365 para Microsoft Teams](office-365-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="1c672-113">For additional details on the licensing model, See [Office 365 licensing for Microsoft Teams](office-365-licensing.md).</span></span>

## <a name="configure-group-call-pickup"></a><span data-ttu-id="1c672-114">Configurar la recogida de llamadas grupales</span><span class="sxs-lookup"><span data-stu-id="1c672-114">Configure group call pickup</span></span>

<span data-ttu-id="1c672-115">Para configurar la recogida de llamadas grupales, un usuario configura primero un grupo de llamadas (no es lo mismo que un grupo de seguridad o un grupo de Office 365) y, a continuación, agrega los usuarios con los que desea compartir las llamadas.</span><span class="sxs-lookup"><span data-stu-id="1c672-115">To set up group call pickup, a user first configures a call group (this is not the same as a security group or an Office 365 group), and then adds the users they want to share their calls with.</span></span> <span data-ttu-id="1c672-116">Después, eligen una configuración de llamadas simultáneas o de desvío de llamadas.</span><span class="sxs-lookup"><span data-stu-id="1c672-116">Then, they choose a simultaneous ring or call forward setting.</span></span> <span data-ttu-id="1c672-117">Para obtener más información y procedimientos paso a paso, consulte [desvío de llamadas y llamadas simultáneas en Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e).</span><span class="sxs-lookup"><span data-stu-id="1c672-117">For more information and step-by-step procedures, see [Call forwarding and simultaneous ring in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e).</span></span>

<span data-ttu-id="1c672-118">Las preferencias de notificación y creación de grupos de llamadas son características dirigidas por el usuario; los administradores no tienen que configurar estas características para sus usuarios.</span><span class="sxs-lookup"><span data-stu-id="1c672-118">Call group creation and notification preferences are user-driven features; administrators do not have to configure these features for their users.</span></span> <span data-ttu-id="1c672-119">No se pueden crear grupos de llamadas a partir de grupos de seguridad o grupos de Office 365; se deben crear en Teams.</span><span class="sxs-lookup"><span data-stu-id="1c672-119">Call groups cannot be created from security groups or Office 365 groups; they must be created in Teams.</span></span>

<span data-ttu-id="1c672-120">Los administradores deben habilitar los grupos de llamadas a través de la configuración de **TeamsCallingPolicy AllowCallGroups** para un usuario.</span><span class="sxs-lookup"><span data-stu-id="1c672-120">Admins should enable call groups via the **TeamsCallingPolicy AllowCallGroups** setting for a user.</span></span> <span data-ttu-id="1c672-121">Los administradores también pueden habilitar esta opción a través del portal de administración de Teams.</span><span class="sxs-lookup"><span data-stu-id="1c672-121">Admins can also enable this via Teams Admin portal.</span></span>  <span data-ttu-id="1c672-122">Además, el usuario configurado también puede configurar sus grupos de llamadas a través del cliente directamente.</span><span class="sxs-lookup"><span data-stu-id="1c672-122">In addition, the configured user can also configure their call groups via the client directly.</span></span> <span data-ttu-id="1c672-123">Los usuarios finales o administradores no pueden bloquear la configuración entre sí, pero el portal de administración de equipos y el cliente de equipos deberían mostrar esta relación con precisión en ambos lugares.</span><span class="sxs-lookup"><span data-stu-id="1c672-123">Admin or end users cannot block the configuration by each other, but Teams Admin portal and Teams client should show this relationship accurately in both places.</span></span> 

<span data-ttu-id="1c672-124">Importante: cuando los administradores desactivan los grupos de llamadas para los usuarios (una vez que se ha activado y se han configurado las relaciones entre los grupos de llamadas), los administradores deben limpiar las relaciones de los usuarios en el centro de administración de Teams para evitar el enrutamiento incorrecto de las llamadas.</span><span class="sxs-lookup"><span data-stu-id="1c672-124">Important: When admins turn off call groups for users (after it has been turned on and the call group relationships are configured), the admins have to clean up the call group relationships for users in the Teams admin center to avoid incorrect call routing.</span></span> 

## <a name="limitations"></a><span data-ttu-id="1c672-125">Algunas</span><span class="sxs-lookup"><span data-stu-id="1c672-125">Limitations</span></span>

<span data-ttu-id="1c672-126">Un inquilino puede contener un máximo de 32.768 grupos de llamadas.</span><span class="sxs-lookup"><span data-stu-id="1c672-126">A tenant can contain a maximum of 32,768 call groups.</span></span> <span data-ttu-id="1c672-127">Puede haber un máximo de 25 usuarios en cada grupo de llamadas.</span><span class="sxs-lookup"><span data-stu-id="1c672-127">There can be a maximum of 25 users in each call group.</span></span> 

## <a name="more-information"></a><span data-ttu-id="1c672-128">Más información</span><span class="sxs-lookup"><span data-stu-id="1c672-128">More information</span></span>

[<span data-ttu-id="1c672-129">Desvío de llamadas y llamadas simultáneas en Teams</span><span class="sxs-lookup"><span data-stu-id="1c672-129">Call forwarding and simultaneous ring in Teams</span></span>](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)
