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
ms.openlocfilehash: e3c1a3c4883705f5e9e5ded88cce94fc37da650b
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32204757"
---
# <a name="configure-live-event-settings-in-microsoft-teams"></a>Configurar eventos en directo en Microsoft Teams

Usar la configuración de eventos en directo de los equipos para establecer la configuración para eventos en directo que se conservan en la organización. Puede configurar una dirección URL de soporte y configurar un proveedor de distribución de vídeo de otro fabricante. Esta configuración se aplica a todos los eventos en directo que se crean en la organización. 

Puede administrar fácilmente esta configuración en el centro de administración de Microsoft Teams. En el panel de navegación izquierdo, vaya a **las reuniones** > **configuración de eventos en directo**. 

![settings.png Live (evento)] (../media/teams-live-events-settings.png "Captura de pantalla de los equipos live configuración de eventos que se puede configurar en el centro de administración de equipos de Microsoft") 

## <a name="set-up-event-support-url"></a>Configurar la dirección URL de soporte (evento)

Esta dirección URL se muestra a los asistentes del evento de live. Agregue la dirección URL de soporte para la organización para dar a los asistentes una forma de ponerse en contacto con el soporte técnico durante un evento en directo.

### <a name="teams-logo-30x30pngmediateams-logo-30x30png-using-the-microsoft-teams-admin-center"></a>![los equipos-logotipo-30x30.png](../media/teams-logo-30x30.png) Desde el centro de administración de Microsoft Teams

1. En el panel de navegación izquierdo, vaya a **las reuniones** > **configuración de evento en directo**.
2. En **Dirección URL de soporte**, escriba la dirección URL de soporte técnico de su organización. 

    ![Configuración de la dirección URL de soporte para eventos en el centro de administración de equipos de Microsoft en directo] (../media/teams-live-events-settings-supporturl.png "Captura de pantalla de admite la dirección URL de configuración para los equipos de eventos en directo")

### <a name="using-windows-powershell"></a>Vea Enviar un correo electrónico a un usuario con su información de conferencias de Audio.
Ejecute lo siguiente:
```
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}” 
```
Para obtener más información, vea [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).
## <a name="configure-a-third-party-video-distribution-provider"></a>Configuración de un proveedor de distribución de vídeo de otro fabricante 

Si adquirió y configurar una solución de software definido network (SDN) o una solución de red (eCDN) de entrega de contenido empresarial a través de un socio de entrega de vídeo de Microsoft, configure el proveedor de eventos en directo en los equipos. 

### <a name="teams-logo-30x30pngmediateams-logo-30x30png-using-the-microsoft-teams-admin-center"></a>![los equipos-logotipo-30x30.png](../media/teams-logo-30x30.png) Desde el centro de administración de Microsoft Teams

1. En el panel de navegación izquierdo, vaya a **las reuniones** > **configuración de evento en directo**.
2. En **proveedores de distribución de vídeo de terceros**, complete lo siguiente: 

    ![Configuración del proveedor de distribución de vídeo de terceros en el centro de administración de equipos de Microsoft] (../media/teams-live-events-settings-distribution-provider.png "Captura de pantalla de la configuración del proveedor de distribución de vídeo de otro fabricante para eventos en directo")

    - **Usar un proveedor de distribución de terceros** Desactivar esta sesión en habilitar el proveedor de distribución de vídeo de otro fabricante.
    - **Nombre del proveedor de SDN** Elija el proveedor que está utilizando.
    - **Clave de licencia de proveedor** Escriba el identificador de licencia que obtuvo de su contacto de proveedor.
    - **Dirección URL de la plantilla de API de SDN** Escriba la dirección URL de plantilla de API que obtuvo de su contacto de proveedor.

### <a name="using-windows-powershell"></a>Vea Enviar un correo electrónico a un usuario con su información de conferencias de Audio.
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
- [¿Qué son los eventos en directo en Teams?](what-are-teams-live-events.md)
- [Planear eventos en directo en Teams](plan-for-teams-live-events.md)
- [Configuración de eventos en directo en Teams](set-up-for-teams-live-events.md)