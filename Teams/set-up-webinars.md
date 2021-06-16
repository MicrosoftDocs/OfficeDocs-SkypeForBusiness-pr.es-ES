---
title: Configurar seminarios web en Microsoft Teams
author: KarliStites
ms.author: kastites
manager: serdars
ms.reviewer: sachung, emryan
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: ''
ms.collection:
- M365-collaboration
- m365initiative-meetings
description: Obtenga información sobre cómo administrar directivas de seminario web para Teams reuniones.
ms.openlocfilehash: 14452b0caeee33f90b59f6581b6fccf4d5e0311b
ms.sourcegitcommit: 4a039550bc5c3a497b6b52c7fed08cadf8268b06
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926752"
---
# <a name="set-up-for-webinars-in-microsoft-teams"></a><span data-ttu-id="7c851-103">Configurar seminarios web en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7c851-103">Set up for webinars in Microsoft Teams</span></span>

<span data-ttu-id="7c851-104">Este artículo le ayudará a configurar su organización para hospedar seminarios web.</span><span class="sxs-lookup"><span data-stu-id="7c851-104">This article will help you set up your organization to host webinars.</span></span>

## <a name="what-are-webinars"></a><span data-ttu-id="7c851-105">¿Qué son los seminarios web?</span><span class="sxs-lookup"><span data-stu-id="7c851-105">What are webinars?</span></span>

<span data-ttu-id="7c851-106">Los seminarios web son reuniones estructuradas en las que los presentadores y los participantes tienen roles claros, a menudo usados con fines de aprendizaje o escenarios de generación de clientes potenciales de ventas y marketing.</span><span class="sxs-lookup"><span data-stu-id="7c851-106">Webinars are structured meetings where presenters and participants have clear roles, often used for training purposes or sales and marketing lead generation scenarios.</span></span>

<span data-ttu-id="7c851-107">Después de configurar seminarios web en su organización, los usuarios pueden programar seminarios web y abrir el registro a los asistentes.</span><span class="sxs-lookup"><span data-stu-id="7c851-107">After setting up webinars in your organization, your users can schedule webinars and open registration to attendees.</span></span> <span data-ttu-id="7c851-108">A diferencia de las reuniones tradicionales que incluyen muchas discusiones y tareas, los seminarios web están diseñados para presentaciones interactivas y proporcionan herramientas para el análisis de los asistentes.</span><span class="sxs-lookup"><span data-stu-id="7c851-108">Unlike traditional meetings that include many discussions and task assignment, webinars are meant for interactive presentations and provide tools for attendee analysis.</span></span>

## <a name="allow-users-to-schedule-webinars-using-powershell"></a><span data-ttu-id="7c851-109">Permitir a los usuarios programar seminarios web con PowerShell</span><span class="sxs-lookup"><span data-stu-id="7c851-109">Allow users to schedule webinars using PowerShell</span></span>

<span data-ttu-id="7c851-110">Puede usar los siguientes atributos dentro del cmdlet **Set-CsTeamsMeetingPolicy de Windows PowerShell set-CsTeamsMeetingPolicy** para configurar seminarios web en Teams.</span><span class="sxs-lookup"><span data-stu-id="7c851-110">You can use the following attributes within the Windows PowerShell **Set-CsTeamsMeetingPolicy** cmdlet to set up for webinars in Teams.</span></span>

- <span data-ttu-id="7c851-111">AllowMeetingRegistration</span><span class="sxs-lookup"><span data-stu-id="7c851-111">AllowMeetingRegistration</span></span>
- <span data-ttu-id="7c851-112">WhoCanRegister</span><span class="sxs-lookup"><span data-stu-id="7c851-112">WhoCanRegister</span></span>
- <span data-ttu-id="7c851-113">AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="7c851-113">AllowPrivateMeetingScheduling</span></span>

<span data-ttu-id="7c851-114">Lea [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) para obtener más información sobre el cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7c851-114">Read [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) for more information on the cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="7c851-115">Antes de poder ejecutar estos cmdlets, debe estar conectado a Microsoft Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7c851-115">Before you can run these cmdlets you must be connected to Microsoft Teams PowerShell.</span></span> <span data-ttu-id="7c851-116">Para obtener más información, vea [Administrar Teams con Microsoft Teams PowerShell](/microsoftteams/teams-powershell-managing-teams).</span><span class="sxs-lookup"><span data-stu-id="7c851-116">For more information, see [Manage Teams with Microsoft Teams PowerShell](/microsoftteams/teams-powershell-managing-teams).</span></span>

### <a name="allow-users-to-schedule-webinars"></a><span data-ttu-id="7c851-117">Permitir a los usuarios programar seminarios web</span><span class="sxs-lookup"><span data-stu-id="7c851-117">Allow users to schedule webinars</span></span>

<span data-ttu-id="7c851-118">Puede restringir el registro solo a los usuarios de su organización o abrirlo a todos los usuarios, tanto dentro como fuera de su inquilino.</span><span class="sxs-lookup"><span data-stu-id="7c851-118">You can restrict registration to users only in your organization or open it up to everyone both inside and outside your tenant.</span></span> <span data-ttu-id="7c851-119">De forma predeterminada, **WhoCanRegister** está habilitado y establecido en **Todos.**</span><span class="sxs-lookup"><span data-stu-id="7c851-119">By default, **WhoCanRegister** is enabled and set to **Everyone**.</span></span> <span data-ttu-id="7c851-120">Si desea desactivar el registro de la reunión, establezca **AllowMeetingRegistration** en **False**.</span><span class="sxs-lookup"><span data-stu-id="7c851-120">If you want to turn off meeting registration, set **AllowMeetingRegistration** to **False**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7c851-121">**AllowPrivateMeetingScheduling** debe establecerse en **True** para **que AllowMeetingRegistration** funcione.</span><span class="sxs-lookup"><span data-stu-id="7c851-121">**AllowPrivateMeetingScheduling** must be set to **True** for **AllowMeetingRegistration** to work.</span></span> <span data-ttu-id="7c851-122">Además, las listas de Microsoft deben configurarse en SharePoint.</span><span class="sxs-lookup"><span data-stu-id="7c851-122">Additionally, Microsoft Lists needs to be set up in SharePoint.</span></span> <span data-ttu-id="7c851-123">Para obtener más información, vea [Configuración de control de listas de Microsoft.](/sharepoint/control-lists)</span><span class="sxs-lookup"><span data-stu-id="7c851-123">To learn more, see [Control settings for Microsoft Lists](/sharepoint/control-lists).</span></span>

1. <span data-ttu-id="7c851-124">Activar el registro de la reunión</span><span class="sxs-lookup"><span data-stu-id="7c851-124">Turn on meeting registration</span></span>

```powershell
Set-CsTeamsMeetingPolicy -AllowMeetingRegistration $True
```

2. <span data-ttu-id="7c851-125">Activar la programación de reuniones privadas</span><span class="sxs-lookup"><span data-stu-id="7c851-125">Turn on private meeting scheduling</span></span>

```powershell
Set-CsTeamsMeetingPolicy -AllowPrivateMeetingScheduling $True
```

3. <span data-ttu-id="7c851-126">Configurar quién puede registrarse en seminarios web</span><span class="sxs-lookup"><span data-stu-id="7c851-126">Configure who can register for webinars</span></span>

<span data-ttu-id="7c851-127">**Permitir *que solo* los usuarios de su organización se registren en seminarios web**</span><span class="sxs-lookup"><span data-stu-id="7c851-127">**Allow *only* users in your organization to register for webinars**</span></span>

```powershell
Set-CsTeamsMeetingPolicy -WhoCanRegister EveryoneInCompany
```

<span data-ttu-id="7c851-128">**Para permitir que cualquier usuario, incluidos los usuarios anónimos, se registre en seminarios web, ejecute:**</span><span class="sxs-lookup"><span data-stu-id="7c851-128">**To allow anyone, including anonymous users, to register for webinars, run:**</span></span>

```powershell
Set-CsTeamsMeetingPolicy -WhoCanRegister Everyone
```

> [!CAUTION]
> <span data-ttu-id="7c851-129">Si la combinación anónima está desactivada en la configuración de la reunión, los usuarios anónimos no pueden unirse a seminarios web.</span><span class="sxs-lookup"><span data-stu-id="7c851-129">If anonymous join is turned off in meeting settings, anonymous users can't join webinars.</span></span> <span data-ttu-id="7c851-130">Para obtener más información y habilitar esta configuración, vea [Configuración de la reunión en Teams](meeting-settings-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="7c851-130">To learn more and enable this setting, see [Meeting settings in Teams](meeting-settings-in-teams.md).</span></span>

### <a name="collect-meeting-attendance"></a><span data-ttu-id="7c851-131">Recopilar asistencia a la reunión</span><span class="sxs-lookup"><span data-stu-id="7c851-131">Collect meeting attendance</span></span>

<span data-ttu-id="7c851-132">Si desea que los organizadores analicen quién se registró y asistió a seminarios web, tendrá que activar la directiva **AllowEngagementReport.**</span><span class="sxs-lookup"><span data-stu-id="7c851-132">If you want organizers to analyze who registered and attended webinars, you'll need to turn on the **AllowEngagementReport** policy.</span></span> <span data-ttu-id="7c851-133">Para ello, ejecute el siguiente comando en PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7c851-133">To do this, run the following command in PowerShell.</span></span>

```powershell
Set-CsTeamsMeetingPolicy -AllowEngagementReport Enabled
```

### <a name="configure-webinar-settings"></a><span data-ttu-id="7c851-134">Configurar la configuración del seminario web</span><span class="sxs-lookup"><span data-stu-id="7c851-134">Configure webinar settings</span></span>

<span data-ttu-id="7c851-135">Después de habilitar su entorno para seminarios web, no se requiere más administración de administradores.</span><span class="sxs-lookup"><span data-stu-id="7c851-135">After enabling your environment for webinars, no further admin management is required.</span></span> <span data-ttu-id="7c851-136">La directiva controla qué opciones se muestran para los organizadores de seminarios web.</span><span class="sxs-lookup"><span data-stu-id="7c851-136">The policy controls which options show up for webinar organizers.</span></span>

## <a name="related-topics"></a><span data-ttu-id="7c851-137">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="7c851-137">Related topics</span></span>

- [<span data-ttu-id="7c851-138">Directivas de reunión en Teams - General</span><span class="sxs-lookup"><span data-stu-id="7c851-138">Meeting policies in Teams - General</span></span>](meeting-policies-in-teams-general.md)
- [<span data-ttu-id="7c851-139">Documentación de Set-CsTeamsMeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="7c851-139">Set-CsTeamsMeetingPolicy documentation</span></span>](/powershell/module/skype/set-csteamsmeetingpolicy)
