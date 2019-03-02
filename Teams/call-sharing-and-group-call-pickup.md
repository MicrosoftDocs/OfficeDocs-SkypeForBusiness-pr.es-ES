---
title: Compartir llamadas y atender llamadas grupales en Microsoft Teams
ms.author: lolaj
author: lolaj
manager: serdars
ms.date: 02/19/2019
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Uso compartido de llamadas y respuesta de llamadas en grupo permite a los usuarios compartir las llamadas entrantes con compañeros de trabajo para que las llamadas se pueden capturar cuando el usuario no está disponible.
ms.openlocfilehash: df98dd4df064b23b687ddcc569e6c5a431137527
ms.sourcegitcommit: 59eda0c17ff39a3e6632810391d78bbadc214419
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/01/2019
ms.locfileid: "30351333"
---
# <a name="call-sharing-and-group-call-pickup-in-microsoft-teams"></a><span data-ttu-id="adbc2-103">Compartir llamadas y atender llamadas grupales en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="adbc2-103">Call sharing and group call pickup in Microsoft Teams</span></span>

<span data-ttu-id="adbc2-104">El uso compartido de llamada y el grupo de llamadas pickup características de recurso compartido de permiten a los usuarios de Microsoft Teams sus las llamadas entrantes con compañeros de trabajo para que los compañeros pueden responder a las llamadas que se producen mientras el usuario no está disponible.</span><span class="sxs-lookup"><span data-stu-id="adbc2-104">The call sharing and group call pickup features of Microsoft Teams let users share their incoming calls with colleagues so that the colleagues can answer calls that occur while the user is unavailable.</span></span>

<span data-ttu-id="adbc2-105">Respuesta de llamadas en grupo es menos problemática para los destinatarios que otras formas de llamada de uso compartido (por ejemplo, el desvío de llamadas o las llamadas simultáneas) debido a que los usuarios pueden configurar la forma en que deseen recibir una notificación de una llamada entrante compartida (a través de notificación de audio y vídeo, solo, visual pancarta o en la aplicación de los equipos), y pueden decidir si se debe responder a la llamada.</span><span class="sxs-lookup"><span data-stu-id="adbc2-105">Group call pickup is less disruptive to recipients than other forms of call sharing (such as call forwarding or simultaneous ringing) because users can configure how they want to be notified of an incoming shared call (via audio and visual notification, visual only, or banner in the Teams app), and they can decide whether to answer it.</span></span>

<span data-ttu-id="adbc2-106">Para compartir las llamadas con otros usuarios, un usuario crea un grupo de llamada y agrega a los usuarios que desean compartir sus llamadas con.</span><span class="sxs-lookup"><span data-stu-id="adbc2-106">To share calls with others, a user creates a call group and adds the users they want to share their calls with.</span></span> <span data-ttu-id="adbc2-107">A continuación, que elija una llamada simultánea o reenvían configuración.</span><span class="sxs-lookup"><span data-stu-id="adbc2-107">Then they choose a simultaneous ring or forward setting.</span></span> <span data-ttu-id="adbc2-108">Para obtener información detallada, vea [llamar anillo desvío y simultánea en los equipos](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) .</span><span class="sxs-lookup"><span data-stu-id="adbc2-108">See [Call forwarding and simultaneous ring in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) for details.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="adbc2-109">Los usuarios, el propietario del grupo de llamada y los miembros del grupo de llamada deben estar en modo de implementación sólo los equipos.</span><span class="sxs-lookup"><span data-stu-id="adbc2-109">Users, the call group owner, and members of the call group must be in Teams Only deployment mode.</span></span> <span data-ttu-id="adbc2-110">Para obtener más detalles sobre los modos de implementación de los equipos, vea [Descripción de los equipos de Microsoft y Skype para la interoperabilidad y coexistencia de negocio](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span><span class="sxs-lookup"><span data-stu-id="adbc2-110">For more details on Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="adbc2-111">Se requiere una licencia</span><span class="sxs-lookup"><span data-stu-id="adbc2-111">License required</span></span>

<span data-ttu-id="adbc2-112">Los usuarios deben ser Enterprise Voice está habilitado para configurar y uso compartido de llamada y respuesta de llamadas de grupo.</span><span class="sxs-lookup"><span data-stu-id="adbc2-112">Users must be Enterprise Voice enabled to set up and use call sharing and group call pickup.</span></span> <span data-ttu-id="adbc2-113">Para obtener más información sobre el modelo de licencias, vea [licencias de Office 365 para equipos de Microsoft](office-365-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="adbc2-113">For additional details on the licensing model, See [Office 365 licensing for Microsoft Teams](office-365-licensing.md).</span></span>

## <a name="configure-group-call-pickup"></a><span data-ttu-id="adbc2-114">Configurar respuesta de llamadas en grupo</span><span class="sxs-lookup"><span data-stu-id="adbc2-114">Configure group call pickup</span></span>

<span data-ttu-id="adbc2-115">Para configurar la respuesta de llamadas en grupo, un usuario en primer lugar configura un grupo de llamada (Esto no es lo mismo como un grupo de seguridad o un grupo de Office 365) y, a continuación, agrega los usuarios que desean compartir sus llamadas con.</span><span class="sxs-lookup"><span data-stu-id="adbc2-115">To set up group call pickup, a user first configures a call group (this is not the same as a security group or an Office 365 group), and then adds the users they want to share their calls with.</span></span> <span data-ttu-id="adbc2-116">A continuación, se elige una llamada simultánea o configuración de reenvío de llamadas.</span><span class="sxs-lookup"><span data-stu-id="adbc2-116">Then, they choose a simultaneous ring or call forward setting.</span></span> <span data-ttu-id="adbc2-117">Para obtener más información y procedimientos paso a paso, vea [llamada anillo desvío y simultánea en los equipos](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e).</span><span class="sxs-lookup"><span data-stu-id="adbc2-117">For more information and step-by-step procedures, see [Call forwarding and simultaneous ring in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e).</span></span>

<span data-ttu-id="adbc2-118">Llamar a la creación del grupo y notificación preferencias son las características de controlado por el usuario; no es necesario que los administradores configurar estas características para sus usuarios.</span><span class="sxs-lookup"><span data-stu-id="adbc2-118">Call group creation and notification preferences are user-driven features; administrators do not have to configure these features for their users.</span></span> <span data-ttu-id="adbc2-119">No se puede crear grupos de llamada de grupos de seguridad o grupos de Office 365; se deben crear en los equipos.</span><span class="sxs-lookup"><span data-stu-id="adbc2-119">Call groups cannot be created from security groups or Office 365 groups; they must be created in Teams.</span></span>

<span data-ttu-id="adbc2-120">Los administradores deben habilitar grupos de llamada a través de la configuración de **TeamsCallingPolicy AllowCallGroups** para un usuario.</span><span class="sxs-lookup"><span data-stu-id="adbc2-120">Admins should enable call groups via the **TeamsCallingPolicy AllowCallGroups** setting for a user.</span></span> <span data-ttu-id="adbc2-121">Los administradores pueden controlar sólo si este usuario puede configurar los grupos de la llamada.</span><span class="sxs-lookup"><span data-stu-id="adbc2-121">Admins can only control whether this user can configure call groups.</span></span> <span data-ttu-id="adbc2-122">Una vez que está establecido el bit a los administradores es true, no puede evitar que el usuario de configuración y la adición de los usuarios del grupo de llamada de su elección.</span><span class="sxs-lookup"><span data-stu-id="adbc2-122">Once the bit is set to true, admins cannot prevent the user from configuring and adding the call group users of their choice.</span></span>

## <a name="limitations"></a><span data-ttu-id="adbc2-123">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="adbc2-123">Limitations</span></span>

<span data-ttu-id="adbc2-124">Un inquilino puede contener un máximo de grupos de llamada 32.768.</span><span class="sxs-lookup"><span data-stu-id="adbc2-124">A tenant can contain a maximum of 32,768 call groups.</span></span> <span data-ttu-id="adbc2-125">Puede haber un máximo de 5 usuarios en cada grupo de llamada.</span><span class="sxs-lookup"><span data-stu-id="adbc2-125">There can be a maximum of 5 users in each call group.</span></span> 

## <a name="more-information"></a><span data-ttu-id="adbc2-126">Más información</span><span class="sxs-lookup"><span data-stu-id="adbc2-126">More information</span></span>

[<span data-ttu-id="adbc2-127">Desvío de llamadas y la llamada simultánea en los equipos</span><span class="sxs-lookup"><span data-stu-id="adbc2-127">Call forwarding and simultaneous ring in Teams</span></span>](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)