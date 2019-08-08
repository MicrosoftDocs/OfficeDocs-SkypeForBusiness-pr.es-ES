---
title: Configurar eventos en directo en Microsoft Teams
author: chuckedmonson
ms.author: chucked
manager: serdars
ms.date: 03/11/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
audience: admin
search.appverid: MET150
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: Obtenga información sobre cómo administrar la configuración de los eventos de Teams Live que se encuentran en su organización.
f1keywords: ms.teamsadmincenter.liveevents.settings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6a1d60ce0e8796d038c6ea8890066c1aee5f0ec6
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243707"
---
# <a name="configure-live-event-settings-in-microsoft-teams"></a><span data-ttu-id="3f2d4-103">Configurar eventos en directo en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3f2d4-103">Configure live event settings in Microsoft Teams</span></span>

<span data-ttu-id="3f2d4-104">Use la configuración de eventos de Teams Live para establecer la configuración de eventos en directo que se encuentran en su organización.</span><span class="sxs-lookup"><span data-stu-id="3f2d4-104">Use Teams live events settings to configure settings for live events that are held in your organization.</span></span> <span data-ttu-id="3f2d4-105">Puede configurar una dirección URL de soporte técnico y configurar un proveedor de distribución de vídeo de terceros.</span><span class="sxs-lookup"><span data-stu-id="3f2d4-105">You can set up a support URL and configure a third-party video distribution provider.</span></span> <span data-ttu-id="3f2d4-106">Esta configuración se aplica a todos los eventos en directo creados en su organización.</span><span class="sxs-lookup"><span data-stu-id="3f2d4-106">These settings apply to all live events that are created in your organization.</span></span> 

<span data-ttu-id="3f2d4-107">Puede administrar fácilmente esta configuración en el centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3f2d4-107">You can easily manage these settings in the Microsoft Teams admin center.</span></span> <span data-ttu-id="3f2d4-108">En el navegación de la izquierda, vaya a**configuración de eventos en directo**de **reuniones** > .</span><span class="sxs-lookup"><span data-stu-id="3f2d4-108">In the left navigation, go to **Meetings** > **Live events settings**.</span></span> 

<span data-ttu-id="3f2d4-109">![Captura de pantalla de la configuración de eventos de Teams Live] (../media/teams-live-events-settings.png "Captura de pantalla de la configuración de eventos de Teams Live que puede configurar en el centro de administración de Microsoft Teams")</span><span class="sxs-lookup"><span data-stu-id="3f2d4-109">![Screen shot of Teams live events settings](../media/teams-live-events-settings.png "Screen shot of Teams live events settings that you can configure in the Microsoft Teams admin center")</span></span> 

## <a name="set-up-event-support-url"></a><span data-ttu-id="3f2d4-110">Configurar la dirección URL de compatibilidad de eventos</span><span class="sxs-lookup"><span data-stu-id="3f2d4-110">Set up event support URL</span></span>

<span data-ttu-id="3f2d4-111">Esta dirección URL se muestra a los asistentes de eventos en directo.</span><span class="sxs-lookup"><span data-stu-id="3f2d4-111">This URL is shown to live event attendees.</span></span> <span data-ttu-id="3f2d4-112">Agregue la dirección URL de soporte técnico de su organización para proporcionar a los asistentes una manera de ponerse en contacto con el soporte técnico durante un evento en vivo.</span><span class="sxs-lookup"><span data-stu-id="3f2d4-112">Add the support URL for your organization to give attendees a way to contact support during a live event.</span></span>

### <a name="an-icon-showing-the-microsoft-teams-logomediateams-logo-30x30png-using-the-microsoft-teams-admin-center"></a>![Un icono que muestra el logotipo de Microsoft Teams](../media/teams-logo-30x30.png) <span data-ttu-id="3f2d4-114">Usar el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3f2d4-114">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="3f2d4-115">En el navegación de la izquierda, vaya a la**configuración de eventos**de **reuniones** > en directo.</span><span class="sxs-lookup"><span data-stu-id="3f2d4-115">In the left navigation, go to **Meetings** > **Live event settings**.</span></span>
2. <span data-ttu-id="3f2d4-116">En **dirección URL de soporte técnico**, escriba la dirección URL de soporte técnico de su organización.</span><span class="sxs-lookup"><span data-stu-id="3f2d4-116">Under **Support URL**, enter your organization's support URL.</span></span> 

    <span data-ttu-id="3f2d4-117">![Configuración de dirección URL de soporte técnico para eventos en directo en el centro de administración] (../media/teams-live-events-settings-supporturl.png "Captura de pantalla de la configuración de URL de soporte técnico para los eventos de Teams Live")</span><span class="sxs-lookup"><span data-stu-id="3f2d4-117">![Support URL setting for live events in the admin center](../media/teams-live-events-settings-supporturl.png "Screen shot of support URL setting for Teams live events")</span></span>

### <a name="using-windows-powershell"></a><span data-ttu-id="3f2d4-118">Vea Enviar un correo electrónico a un usuario con su información de conferencias de Audio.</span><span class="sxs-lookup"><span data-stu-id="3f2d4-118">Using Windows PowerShell</span></span>
<span data-ttu-id="3f2d4-119">Ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3f2d4-119">Run the following:</span></span>
```
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}” 
```
<span data-ttu-id="3f2d4-120">Para obtener más información, consulte [set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="3f2d4-120">For more information, see [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span></span>
## <a name="configure-a-third-party-video-distribution-provider"></a><span data-ttu-id="3f2d4-121">Configurar un proveedor de distribución de video de terceros</span><span class="sxs-lookup"><span data-stu-id="3f2d4-121">Configure a third-party video distribution provider</span></span> 

<span data-ttu-id="3f2d4-122">Si compró y configuró una solución de red definida por software (SDN) o una solución de red de entrega de contenido empresarial (eCDN) a través de un socio de envío de video de Microsoft, configure el proveedor de eventos en vivo en Teams.</span><span class="sxs-lookup"><span data-stu-id="3f2d4-122">If you purchased and set up a software defined network (SDN) solution or enterprise content delivery network (eCDN) solution through a Microsoft video delivery partner, configure the provider for live events in Teams.</span></span> 

### <a name="an-icon-showing-the-microsoft-teams-logomediateams-logo-30x30png-using-the-microsoft-teams-admin-center"></a>![Un icono que muestra el logotipo de Microsoft Teams](../media/teams-logo-30x30.png) <span data-ttu-id="3f2d4-124">Usar el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3f2d4-124">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="3f2d4-125">En el navegación de la izquierda, vaya a la**configuración de eventos**de **reuniones** > en directo.</span><span class="sxs-lookup"><span data-stu-id="3f2d4-125">In the left navigation, go to **Meetings** > **Live event settings**.</span></span>
2. <span data-ttu-id="3f2d4-126">En **proveedores de distribución de vídeo de terceros**, complete lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3f2d4-126">Under **Third-party video distribution providers**, complete the following:</span></span> 

    <span data-ttu-id="3f2d4-127">![Configuración del proveedor de distribución de vídeo de terceros en el centro de administración] (../media/teams-live-events-settings-distribution-provider.png "Captura de pantalla de la configuración del proveedor de distribución de vídeo de terceros para eventos en directo")</span><span class="sxs-lookup"><span data-stu-id="3f2d4-127">![Third-party video distribution provider settings in the admin center](../media/teams-live-events-settings-distribution-provider.png "Screen shot of the third-party video distribution provider settings for live events")</span></span>

    - <span data-ttu-id="3f2d4-128">**Usar un proveedor de distribución de terceros** Active esta opción para habilitar el proveedor de distribución de vídeo de terceros.</span><span class="sxs-lookup"><span data-stu-id="3f2d4-128">**Use a third-party distribution provider** Turn this on to enable the third-party video distribution provider.</span></span>
    - <span data-ttu-id="3f2d4-129">**Nombre del proveedor de Sdn** Elija el proveedor que está usando.</span><span class="sxs-lookup"><span data-stu-id="3f2d4-129">**SDN provider name** Choose the provider you're using.</span></span>
    - <span data-ttu-id="3f2d4-130">**Clave de licencia de proveedor** Escriba el identificador de licencia que recibió del contacto del proveedor.</span><span class="sxs-lookup"><span data-stu-id="3f2d4-130">**Provider license key** Enter the license ID that you got from your provider contact.</span></span>
    - <span data-ttu-id="3f2d4-131">**URL de plantilla** de la API de Sdn Escriba la dirección URL de la plantilla API que recibió del contacto del proveedor.</span><span class="sxs-lookup"><span data-stu-id="3f2d4-131">**SDN API template URL** Enter the API template URL that you got from your provider contact.</span></span>

### <a name="using-windows-powershell"></a><span data-ttu-id="3f2d4-132">Vea Enviar un correo electrónico a un usuario con su información de conferencias de Audio.</span><span class="sxs-lookup"><span data-stu-id="3f2d4-132">Using Windows PowerShell</span></span>
<span data-ttu-id="3f2d4-133">Obtenga el identificador de licencia o el token de API y la plantilla de API de su contacto de proveedor y, a continuación, ejecute uno de los siguientes, según el proveedor que use:</span><span class="sxs-lookup"><span data-stu-id="3f2d4-133">Get the license ID or API token and API template from your provider contact, and then run one of the following, depending on the provider you're using:</span></span>

<span data-ttu-id="3f2d4-134">**Subárbol**</span><span class="sxs-lookup"><span data-stu-id="3f2d4-134">**Hive**</span></span> 
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName hive -SdnLicenseId {license ID GUID provided by Hive} -SdnApiTemplateUrl “{API template URL provided by Hive}”
```
<span data-ttu-id="3f2d4-135">**Kollective**</span><span class="sxs-lookup"><span data-stu-id="3f2d4-135">**Kollective**</span></span> 
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName kollective -SdnApiTemplateUrl "{API template URL provided by Kollective}" -SdnApiToken {API token GUID provided by Kollective}
```
<span data-ttu-id="3f2d4-136">Para obtener más información, consulte [set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="3f2d4-136">For more information, see [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span></span>

> [!NOTE]
> <span data-ttu-id="3f2d4-137">Si planea crear eventos en directo con una aplicación o dispositivo externo, también tendrá que [configurar el proveedor de eCDN con Microsoft Stream](https://docs.microsoft.com/stream/network-caching).</span><span class="sxs-lookup"><span data-stu-id="3f2d4-137">If you plan to create live events using an external app or device, you'll also need to [configure your eCDN provider with Microsoft Stream](https://docs.microsoft.com/stream/network-caching).</span></span> 

### <a name="related-topics"></a><span data-ttu-id="3f2d4-138">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="3f2d4-138">Related topics</span></span>
- [<span data-ttu-id="3f2d4-139">¿Qué son los eventos en directo en Teams?</span><span class="sxs-lookup"><span data-stu-id="3f2d4-139">What are Teams live events?</span></span>](what-are-teams-live-events.md)
- [<span data-ttu-id="3f2d4-140">Planear eventos en directo en Teams</span><span class="sxs-lookup"><span data-stu-id="3f2d4-140">Plan for Teams live events</span></span>](plan-for-teams-live-events.md)
- [<span data-ttu-id="3f2d4-141">Configuración de eventos en directo en Teams</span><span class="sxs-lookup"><span data-stu-id="3f2d4-141">Set up for Teams live events</span></span>](set-up-for-teams-live-events.md)