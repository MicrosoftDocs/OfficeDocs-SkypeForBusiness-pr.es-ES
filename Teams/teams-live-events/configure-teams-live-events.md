---
title: Configurar las opciones de evento en directo en Microsoft Teams
author: tonysmith
ms.author: tonysmit
manager: serdars
ms.date: 10/23/2018
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
search.appverid: MET150
localization_priority: Normal
MS.collection: Teams_ITAdmin_Help
description: Obtenga información sobre cómo administrar la configuración para eventos en directo los equipos que se encuentran en la organización.
f1keywords: ms.teamsadmincenter.liveevents.settings
appliesto:
- Microsoft Teams
ms.openlocfilehash: b8e12b6b85b61bb8c6312054be07dc37365c62c0
ms.sourcegitcommit: 2e9761a3b195d31080bff3c9cc17a18adcd5350e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2018
ms.locfileid: "25748152"
---
# <a name="configure-live-event-settings-in-microsoft-teams"></a>Configurar las opciones de evento en directo en Microsoft Teams
> [!INCLUDE [Preview customer token](../includes/preview-feature.md)]

Usar la configuración de eventos en directo de los equipos para establecer la configuración para eventos en directo que se conservan en la organización. Puede configurar una dirección URL de soporte y configurar un proveedor de distribución de vídeo de otro fabricante. Esta configuración se aplica a todos los eventos en directo que se crean en la organización. 

Puede administrar fácilmente esta configuración en el Microsoft Teams & Skype para el centro de administración de negocio. En el panel de navegación izquierdo, vaya a **las reuniones** > **configuración de eventos en directo**. 

![settings.png Live (evento)] (../media/teams-live-events-settings.png "Captura de pantalla de los equipos live configuración de eventos que se puede configurar en los equipos de Microsoft & Skype para el centro de administración de negocio") 

## <a name="set-up-event-support-url"></a>Configurar la dirección URL de soporte (evento)

Esta dirección URL se muestra a los asistentes del evento de live. Agregue la dirección URL de soporte para la organización para dar a los asistentes una forma de ponerse en contacto con el soporte técnico durante un evento en directo.

### <a name="teams-logo-30x30pngmediateams-logo-30x30png-using-the-microsoft-teams--skype-for-business-admin-center"></a>![los equipos-logotipo-30x30.png](../media/teams-logo-30x30.png) Uso de la Microsoft Teams & Skype para el centro de administración de negocio

1. En el panel de navegación izquierdo, vaya a **las reuniones** > **configuración de evento en directo**.
2. En **Dirección URL de soporte**, escriba la dirección URL de soporte técnico de su organización. 

    ![Configuración de la dirección URL de soporte para live eventos en los equipos de Microsoft & Skype para el centro de administración de negocio] (../media/teams-live-events-settings-supporturl.png "Captura de pantalla de admite la dirección URL de configuración para los equipos de eventos en directo")

### <a name="using-windows-powershell"></a>Usar Windows PowerShell
Ejecute lo siguiente:
```
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}” 
```
Para obtener más información, vea [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).
## <a name="configure-a-third-party-video-distribution-provider"></a>Configuración de un proveedor de distribución de vídeo de otro fabricante 

Si adquirió y configurar una solución de software definido network (SDN) o una solución de red (eCDN) de entrega de contenido empresarial a través de un socio de entrega de vídeo de Microsoft, configure el proveedor de eventos en directo en los equipos. 

### <a name="teams-logo-30x30pngmediateams-logo-30x30png-using-the-microsoft-teams--skype-for-business-admin-center"></a>![los equipos-logotipo-30x30.png](../media/teams-logo-30x30.png) Uso de la Microsoft Teams & Skype para el centro de administración de negocio

1. En el panel de navegación izquierdo, vaya a **las reuniones** > **configuración de evento en directo**.
2. En **proveedores de distribución de vídeo de terceros**, complete lo siguiente: 

    ![Configuración del proveedor de distribución de vídeo de terceros en los equipos de Microsoft & Skype para el centro de administración de negocio] (../media/teams-live-events-settings-distribution-provider.png "Captura de pantalla de la configuración del proveedor de distribución de vídeo de otro fabricante para eventos en directo")

    - **Usar un proveedor de distribución de terceros** Desactivar esta sesión en habilitar el proveedor de distribución de vídeo de otro fabricante.
    - **Nombre del proveedor de SDN** Elija el proveedor que está utilizando.
    - **Clave de licencia de proveedor** Escriba el identificador de licencia que obtuvo de su contacto de proveedor.
    - **Dirección URL de la plantilla de API de SDN** Escriba la dirección URL de plantilla de API que obtuvo de su contacto de proveedor.

### <a name="using-windows-powershell"></a>Usar Windows PowerShell
Obtener el token de licencia de identificador o API y la plantilla de la API de su contacto de proveedor y, a continuación, ejecute uno de los siguientes, según el proveedor que está utilizando:

**Subárbol** 
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName hive -SdnLicenseId {license ID GUID provided by Hive} -SdnApiTemplateUrl “{API template URL provided by Hive}”
```
**Kollective** 
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName kollective -SdnApiTemplateUrl "{API template URL provided by Kollective}" -SdnApiToken {API token GUID provided by Kollective}
```
Para obtener más información, vea [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).

> [!NOTE]
> Si va a crear eventos en directo que usar codificadores externos, también necesitará [configurar su proveedor eCDN con la secuencia de Microsoft](https://docs.microsoft.com/stream/network-caching). 

### <a name="related-topics"></a>Temas relacionados
- [¿Cuáles son los equipos de eventos en directo?](what-are-teams-live-events.md)
- [Plan para los equipos eventos en directo](plan-for-teams-live-events.md)
- [Configurar para los equipos de eventos en directo](set-up-for-teams-live-events.md)