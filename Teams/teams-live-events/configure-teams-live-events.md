---
title: Configurar eventos en directo en Microsoft Teams
author: tonysmith
ms.author: tonysmit
manager: serdars
ms.date: 03/11/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
search.appverid: MET150
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: Obtenga información sobre cómo administrar la configuración para eventos en directo los equipos que se encuentran en la organización.
f1keywords: ms.teamsadmincenter.liveevents.settings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 56a7834f1547c682c690f8c42082af0a314efec9
ms.sourcegitcommit: 70d4d02a3cc894f2f197aeea459ac079cde63877
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/11/2019
ms.locfileid: "30542842"
---
# <a name="configure-live-event-settings-in-microsoft-teams"></a><span data-ttu-id="08f63-103">Configurar eventos en directo en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="08f63-103">Configure live event settings in Microsoft Teams</span></span>
> [!INCLUDE [Preview customer token](../includes/preview-feature.md)]

<span data-ttu-id="08f63-104">Usar la configuración de eventos en directo de los equipos para establecer la configuración para eventos en directo que se conservan en la organización.</span><span class="sxs-lookup"><span data-stu-id="08f63-104">Use Teams live events settings to configure settings for live events that are held in your organization.</span></span> <span data-ttu-id="08f63-105">Puede configurar una dirección URL de soporte y configurar un proveedor de distribución de vídeo de otro fabricante.</span><span class="sxs-lookup"><span data-stu-id="08f63-105">You can set up a support URL and configure a third-party video distribution provider.</span></span> <span data-ttu-id="08f63-106">Esta configuración se aplica a todos los eventos en directo que se crean en la organización.</span><span class="sxs-lookup"><span data-stu-id="08f63-106">These settings apply to all live events that are created in your organization.</span></span> 

<span data-ttu-id="08f63-107">Puede administrar fácilmente esta configuración en el centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="08f63-107">You can easily manage these settings in the Microsoft Teams admin center.</span></span> <span data-ttu-id="08f63-108">En el panel de navegación izquierdo, vaya a **las reuniones** > **configuración de eventos en directo**.</span><span class="sxs-lookup"><span data-stu-id="08f63-108">In the left navigation, go to **Meetings** > **Live events settings**.</span></span> 

<span data-ttu-id="08f63-109">![settings.png Live (evento)] (../media/teams-live-events-settings.png "Captura de pantalla de los equipos live configuración de eventos que se puede configurar en el centro de administración de equipos de Microsoft")</span><span class="sxs-lookup"><span data-stu-id="08f63-109">![live-event-settings.png](../media/teams-live-events-settings.png "Screen shot of Teams live events settings that you can configure in the Microsoft Teams admin center")</span></span> 

## <a name="set-up-event-support-url"></a><span data-ttu-id="08f63-110">Configurar la dirección URL de soporte (evento)</span><span class="sxs-lookup"><span data-stu-id="08f63-110">Set up event support URL</span></span>

<span data-ttu-id="08f63-111">Esta dirección URL se muestra a los asistentes del evento de live.</span><span class="sxs-lookup"><span data-stu-id="08f63-111">This URL is shown to live event attendees.</span></span> <span data-ttu-id="08f63-112">Agregue la dirección URL de soporte para la organización para dar a los asistentes una forma de ponerse en contacto con el soporte técnico durante un evento en directo.</span><span class="sxs-lookup"><span data-stu-id="08f63-112">Add the support URL for your organization to give attendees a way to contact support during a live event.</span></span>

### <a name="teams-logo-30x30pngmediateams-logo-30x30png-using-the-microsoft-teams-admin-center"></a>![los equipos-logotipo-30x30.png](../media/teams-logo-30x30.png) <span data-ttu-id="08f63-114">Desde el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="08f63-114">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="08f63-115">En el panel de navegación izquierdo, vaya a **las reuniones** > **configuración de evento en directo**.</span><span class="sxs-lookup"><span data-stu-id="08f63-115">In the left navigation, go to **Meetings** > **Live event settings**.</span></span>
2. <span data-ttu-id="08f63-116">En **Dirección URL de soporte**, escriba la dirección URL de soporte técnico de su organización.</span><span class="sxs-lookup"><span data-stu-id="08f63-116">Under **Support URL**, enter your organization's support URL.</span></span> 

    <span data-ttu-id="08f63-117">![Configuración de la dirección URL de soporte para eventos en el centro de administración de equipos de Microsoft en directo] (../media/teams-live-events-settings-supporturl.png "Captura de pantalla de admite la dirección URL de configuración para los equipos de eventos en directo")</span><span class="sxs-lookup"><span data-stu-id="08f63-117">![Support URL setting for live events in the Microsoft Teams admin center](../media/teams-live-events-settings-supporturl.png "Screen shot of support URL setting for Teams live events")</span></span>

### <a name="using-windows-powershell"></a><span data-ttu-id="08f63-118">Usar Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="08f63-118">Using Windows PowerShell</span></span>
<span data-ttu-id="08f63-119">Ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="08f63-119">Run the following:</span></span>
```
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}” 
```
<span data-ttu-id="08f63-120">Para obtener más información, vea [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="08f63-120">For more information, see [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span></span>
## <a name="configure-a-third-party-video-distribution-provider"></a><span data-ttu-id="08f63-121">Configuración de un proveedor de distribución de vídeo de otro fabricante</span><span class="sxs-lookup"><span data-stu-id="08f63-121">Configure a third-party video distribution provider</span></span> 

<span data-ttu-id="08f63-122">Si adquirió y configurar una solución de software definido network (SDN) o una solución de red (eCDN) de entrega de contenido empresarial a través de un socio de entrega de vídeo de Microsoft, configure el proveedor de eventos en directo en los equipos.</span><span class="sxs-lookup"><span data-stu-id="08f63-122">If you purchased and set up a software defined network (SDN) solution or enterprise content delivery network (eCDN) solution through a Microsoft video delivery partner, configure the provider for live events in Teams.</span></span> 

### <a name="teams-logo-30x30pngmediateams-logo-30x30png-using-the-microsoft-teams-admin-center"></a>![los equipos-logotipo-30x30.png](../media/teams-logo-30x30.png) <span data-ttu-id="08f63-124">Desde el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="08f63-124">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="08f63-125">En el panel de navegación izquierdo, vaya a **las reuniones** > **configuración de evento en directo**.</span><span class="sxs-lookup"><span data-stu-id="08f63-125">In the left navigation, go to **Meetings** > **Live event settings**.</span></span>
2. <span data-ttu-id="08f63-126">En **proveedores de distribución de vídeo de terceros**, complete lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="08f63-126">Under **Third-party video distribution providers**, complete the following:</span></span> 

    <span data-ttu-id="08f63-127">![Configuración del proveedor de distribución de vídeo de terceros en el centro de administración de equipos de Microsoft] (../media/teams-live-events-settings-distribution-provider.png "Captura de pantalla de la configuración del proveedor de distribución de vídeo de otro fabricante para eventos en directo")</span><span class="sxs-lookup"><span data-stu-id="08f63-127">![Third-party video distribution provider settings in the Microsoft Teams admin center](../media/teams-live-events-settings-distribution-provider.png "Screen shot of the third-party video distribution provider settings for live events")</span></span>

    - <span data-ttu-id="08f63-128">**Usar un proveedor de distribución de terceros** Desactivar esta sesión en habilitar el proveedor de distribución de vídeo de otro fabricante.</span><span class="sxs-lookup"><span data-stu-id="08f63-128">**Use a third-party distribution provider** Turn this on to enable the third-party video distribution provider.</span></span>
    - <span data-ttu-id="08f63-129">**Nombre del proveedor de SDN** Elija el proveedor que está utilizando.</span><span class="sxs-lookup"><span data-stu-id="08f63-129">**SDN provider name** Choose the provider you're using.</span></span>
    - <span data-ttu-id="08f63-130">**Clave de licencia de proveedor** Escriba el identificador de licencia que obtuvo de su contacto de proveedor.</span><span class="sxs-lookup"><span data-stu-id="08f63-130">**Provider license key** Enter the license ID that you got from your provider contact.</span></span>
    - <span data-ttu-id="08f63-131">**Dirección URL de la plantilla de API de SDN** Escriba la dirección URL de plantilla de API que obtuvo de su contacto de proveedor.</span><span class="sxs-lookup"><span data-stu-id="08f63-131">**SDN API template URL** Enter the API template URL that you got from your provider contact.</span></span>

### <a name="using-windows-powershell"></a><span data-ttu-id="08f63-132">Usar Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="08f63-132">Using Windows PowerShell</span></span>
<span data-ttu-id="08f63-133">Obtener el token de licencia de identificador o API y la plantilla de la API de su contacto de proveedor y, a continuación, ejecute uno de los siguientes, según el proveedor que está utilizando:</span><span class="sxs-lookup"><span data-stu-id="08f63-133">Get the license ID or API token and API template from your provider contact, and then run one of the following, depending on the provider you're using:</span></span>

<span data-ttu-id="08f63-134">**Subárbol**</span><span class="sxs-lookup"><span data-stu-id="08f63-134">**Hive**</span></span> 
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName hive -SdnLicenseId {license ID GUID provided by Hive} -SdnApiTemplateUrl “{API template URL provided by Hive}”
```
<span data-ttu-id="08f63-135">**Kollective**</span><span class="sxs-lookup"><span data-stu-id="08f63-135">**Kollective**</span></span> 
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName kollective -SdnApiTemplateUrl "{API template URL provided by Kollective}" -SdnApiToken {API token GUID provided by Kollective}
```
<span data-ttu-id="08f63-136">Para obtener más información, vea [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="08f63-136">For more information, see [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span></span>

> [!NOTE]
> <span data-ttu-id="08f63-137">Si va a crear eventos en directo que usar codificadores externos, también necesitará [configurar su proveedor eCDN con la secuencia de Microsoft](https://docs.microsoft.com/stream/network-caching).</span><span class="sxs-lookup"><span data-stu-id="08f63-137">If you plan to create live events that use external encoders, you'll also need to [configure your eCDN provider with Microsoft Stream](https://docs.microsoft.com/stream/network-caching).</span></span> 

### <a name="related-topics"></a><span data-ttu-id="08f63-138">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="08f63-138">Related topics</span></span>
- [<span data-ttu-id="08f63-139">¿Qué son los eventos en directo en Teams?</span><span class="sxs-lookup"><span data-stu-id="08f63-139">What are Teams live events?</span></span>](what-are-teams-live-events.md)
- [<span data-ttu-id="08f63-140">Planear eventos en directo en Teams</span><span class="sxs-lookup"><span data-stu-id="08f63-140">Plan for Teams live events</span></span>](plan-for-teams-live-events.md)
- [<span data-ttu-id="08f63-141">Configuración de eventos en directo en Teams</span><span class="sxs-lookup"><span data-stu-id="08f63-141">Set up for Teams live events</span></span>](set-up-for-teams-live-events.md)