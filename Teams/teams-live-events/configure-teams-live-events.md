---
title: Configurar eventos en directo en Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 03/11/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
audience: admin
search.appverid: MET150
localization_priority: Normal
ms.collection:
- M365-collaboration
description: Obtenga información sobre cómo administrar la configuración de eventos en directo de Teams que se llevan a cabo en su organización.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.liveevents.settings
appliesto:
- Microsoft Teams
ms.openlocfilehash: b87c891d29bcfafa0275f3a500eb8c5db85311a0
ms.sourcegitcommit: b255db7ef816d1884c9c71af86a901bd83a1d9ab
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962861"
---
# <a name="configure-live-event-settings-in-microsoft-teams"></a><span data-ttu-id="982de-103">Configurar eventos en directo en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="982de-103">Configure live event settings in Microsoft Teams</span></span>

<span data-ttu-id="982de-104">Use la configuración de eventos en directo de Teams para establecer la configuración de los eventos en directo de su organización.</span><span class="sxs-lookup"><span data-stu-id="982de-104">Use Teams live events settings to configure settings for live events that are held in your organization.</span></span> <span data-ttu-id="982de-105">Puede configurar una dirección URL de soporte técnico y configurar un proveedor de distribución de vídeo de terceros.</span><span class="sxs-lookup"><span data-stu-id="982de-105">You can set up a support URL and configure a third-party video distribution provider.</span></span> <span data-ttu-id="982de-106">Esta configuración se aplica a todos los eventos en directo creados en la organización.</span><span class="sxs-lookup"><span data-stu-id="982de-106">These settings apply to all live events that are created in your organization.</span></span>

<span data-ttu-id="982de-107">Puede administrar fácilmente estas opciones de configuración en el centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="982de-107">You can easily manage these settings in the Microsoft Teams admin center.</span></span> <span data-ttu-id="982de-108">En el panel de navegación izquierdo, vaya a **Reuniones** > **Configuración eventos en directo**.</span><span class="sxs-lookup"><span data-stu-id="982de-108">In the left navigation, go to **Meetings** > **Live events settings**.</span></span>

<span data-ttu-id="982de-109">![Captura de pantalla de la configuración de eventos en directo de Teams](../media/teams-live-events-settings.png "Captura de pantalla de las opciones de configuración de eventos en directo de Teams que puede configurar en el centro de administración de Microsoft Teams")</span><span class="sxs-lookup"><span data-stu-id="982de-109">![Screen shot of Teams live events settings](../media/teams-live-events-settings.png "Screen shot of Teams live events settings that you can configure in the Microsoft Teams admin center")</span></span>

## <a name="set-up-event-support-url"></a><span data-ttu-id="982de-110">Configurar la URL de soporte de eventos</span><span class="sxs-lookup"><span data-stu-id="982de-110">Set up event support URL</span></span>

<span data-ttu-id="982de-111">Esta dirección URL se muestra a los asistentes del evento en directo.</span><span class="sxs-lookup"><span data-stu-id="982de-111">This URL is shown to live event attendees.</span></span> <span data-ttu-id="982de-112">Agregue la dirección URL de soporte de la organización para ofrecer a los asistentes una manera de ponerse en contacto con el soporte técnico durante un evento en directo.</span><span class="sxs-lookup"><span data-stu-id="982de-112">Add the support URL for your organization to give attendees a way to contact support during a live event.</span></span>

### <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Un icono que muestra el logotipo de Microsoft Teams](../media/teams-logo-30x30.png) <span data-ttu-id="982de-114">Usar el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="982de-114">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="982de-115">En la navegación izquierda, vaya a **Reuniones** > **Configuración de eventos en directo**.</span><span class="sxs-lookup"><span data-stu-id="982de-115">In the left navigation, go to **Meetings** > **Live event settings**.</span></span>
2. <span data-ttu-id="982de-116">En **dirección URL de soporte**, escriba la dirección URL de soporte técnico de su organización.</span><span class="sxs-lookup"><span data-stu-id="982de-116">Under **Support URL**, enter your organization's support URL.</span></span>

    <span data-ttu-id="982de-117">![Configuración de URL de soporte para eventos en directo en el centro de administración](../media/teams-live-events-settings-supporturl.png "Captura de pantalla de la configuración de URL de soporte técnico para los eventos en directo de Teams")</span><span class="sxs-lookup"><span data-stu-id="982de-117">![Support URL setting for live events in the admin center](../media/teams-live-events-settings-supporturl.png "Screen shot of support URL setting for Teams live events")</span></span>

### <a name="using-windows-powershell"></a><span data-ttu-id="982de-118">Usar Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="982de-118">Using Windows PowerShell</span></span>

<span data-ttu-id="982de-119">Ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="982de-119">Run the following:</span></span>

```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}”
```
<span data-ttu-id="982de-120">Para obtener más información, vea [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="982de-120">For more information, see [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span></span>
## <a name="configure-a-third-party-video-distribution-provider"></a><span data-ttu-id="982de-121">Configurar un proveedor de distribución de vídeo de terceros</span><span class="sxs-lookup"><span data-stu-id="982de-121">Configure a third-party video distribution provider</span></span> 

<span data-ttu-id="982de-122">Si compró y configuró una solución de red definida por software (SDN) o una solución de red de entrega de contenido para empresas (eCDN) a través de un partner de entrega de vídeo de Microsoft, configure el proveedor para eventos en directo en Teams.</span><span class="sxs-lookup"><span data-stu-id="982de-122">If you purchased and set up a software defined network (SDN) solution or enterprise content delivery network (eCDN) solution through a Microsoft video delivery partner, configure the provider for live events in Teams.</span></span> 

### <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Un icono que muestra el logotipo de Microsoft Teams](../media/teams-logo-30x30.png) <span data-ttu-id="982de-124">Usar el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="982de-124">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="982de-125">En la navegación izquierda, vaya a **Reuniones** > **Configuración de eventos en directo**.</span><span class="sxs-lookup"><span data-stu-id="982de-125">In the left navigation, go to **Meetings** > **Live event settings**.</span></span>
2. <span data-ttu-id="982de-126">En **Proveedores de distribución de vídeo de terceros**, siga este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="982de-126">Under **Third-party video distribution providers**, complete the following:</span></span> 

    <span data-ttu-id="982de-127">![Configuración del proveedor de distribución de vídeo de terceros en el centro de administración](../media/teams-live-events-settings-distribution-provider.png "Captura de pantalla de la configuración del proveedor de distribución de vídeo de terceros para eventos en directo")</span><span class="sxs-lookup"><span data-stu-id="982de-127">![Third-party video distribution provider settings in the admin center](../media/teams-live-events-settings-distribution-provider.png "Screen shot of the third-party video distribution provider settings for live events")</span></span>

    - <span data-ttu-id="982de-128">**Usar un proveedor de distribución de terceros** active esta opción para habilitar el proveedor de distribución de vídeo de terceros.</span><span class="sxs-lookup"><span data-stu-id="982de-128">**Use a third-party distribution provider** Turn this on to enable the third-party video distribution provider.</span></span>
    - <span data-ttu-id="982de-129">**Nombre del proveedor de SDN** elija el proveedor que está usando.</span><span class="sxs-lookup"><span data-stu-id="982de-129">**SDN provider name** Choose the provider you're using.</span></span>
    - <span data-ttu-id="982de-130">**Clave de licencia de proveedor** especifique el ID. de licencia que obtuvo del proveedor.</span><span class="sxs-lookup"><span data-stu-id="982de-130">**Provider license key** Enter the license ID that you got from your provider contact.</span></span>
    - <span data-ttu-id="982de-131">**URL de la plantilla de API de SDN** especifique la dirección URL de la plantilla API que obtuvo del proveedor.</span><span class="sxs-lookup"><span data-stu-id="982de-131">**SDN API template URL** Enter the API template URL that you got from your provider contact.</span></span>

### <a name="using-windows-powershell"></a><span data-ttu-id="982de-132">Usar Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="982de-132">Using Windows PowerShell</span></span>
<span data-ttu-id="982de-133">Obtenga el ID. de licencia, el token de API y la plantilla de API del proveedor y, después, ejecute uno de los siguientes procedimientos, en función del proveedor que use:</span><span class="sxs-lookup"><span data-stu-id="982de-133">Get the license ID or API token and API template from your provider contact, and then run one of the following, depending on the provider you're using:</span></span>

<span data-ttu-id="982de-134">**Hive**</span><span class="sxs-lookup"><span data-stu-id="982de-134">**Hive**</span></span> 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName hive -SdnLicenseId {license ID GUID provided by Hive} -SdnApiTemplateUrl “{API template URL provided by Hive}”
```
<span data-ttu-id="982de-135">**Kollective**</span><span class="sxs-lookup"><span data-stu-id="982de-135">**Kollective**</span></span> 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName kollective -SdnApiTemplateUrl "{API template URL provided by Kollective}" -SdnApiToken {API token GUID provided by Kollective}
```
<span data-ttu-id="982de-136">**Riverbed**</span><span class="sxs-lookup"><span data-stu-id="982de-136">**Riverbed**</span></span> 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName riverbed -SdnApiTemplateUrl "{API template URL provided by Riverbed}" -SdnApiToken {API token GUID provided by Riverbed}
```

<span data-ttu-id="982de-137">Para obtener más información, vea [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="982de-137">For more information, see [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span></span>

> [!NOTE]
> <span data-ttu-id="982de-138">Si tiene previsto crear eventos en directo con una aplicación o dispositivo externo, también tendrá que [configurar el proveedor de eCDN con Microsoft Stream](https://docs.microsoft.com/stream/network-caching).</span><span class="sxs-lookup"><span data-stu-id="982de-138">If you plan to create live events using an external app or device, you'll also need to [configure your eCDN provider with Microsoft Stream](https://docs.microsoft.com/stream/network-caching).</span></span> 

### <a name="related-topics"></a><span data-ttu-id="982de-139">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="982de-139">Related topics</span></span>
- [<span data-ttu-id="982de-140">¿Qué son los eventos en directo en Teams?</span><span class="sxs-lookup"><span data-stu-id="982de-140">What are Teams live events?</span></span>](what-are-teams-live-events.md)
- [<span data-ttu-id="982de-141">Planear eventos en directo en Teams</span><span class="sxs-lookup"><span data-stu-id="982de-141">Plan for Teams live events</span></span>](plan-for-teams-live-events.md)
- [<span data-ttu-id="982de-142">Configuración de eventos en directo en Teams</span><span class="sxs-lookup"><span data-stu-id="982de-142">Set up for Teams live events</span></span>](set-up-for-teams-live-events.md)