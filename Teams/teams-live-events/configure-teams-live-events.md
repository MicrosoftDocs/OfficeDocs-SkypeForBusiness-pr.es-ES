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
description: Obtenga información sobre cómo administrar la configuración de los eventos de Teams Live que se encuentran en su organización.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.liveevents.settings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 222e7e51fcf87e0e76c3ab18f33357f7489a1ce1
ms.sourcegitcommit: a6425a536746e129ab8bda3984b5ae63fb316192
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/07/2020
ms.locfileid: "42558600"
---
# <a name="configure-live-event-settings-in-microsoft-teams"></a>Configurar eventos en directo en Microsoft Teams

Use la configuración de eventos de Teams Live para establecer la configuración de eventos en directo que se encuentran en su organización. Puede configurar una dirección URL de soporte técnico y configurar un proveedor de distribución de vídeo de terceros. Esta configuración se aplica a todos los eventos en directo creados en su organización. 

Puede administrar fácilmente esta configuración en el centro de administración de Microsoft Teams. En el navegación de la izquierda, vaya a**configuración de eventos en directo**de **reuniones** > . 

![Captura de pantalla de la configuración de eventos de Teams Live](../media/teams-live-events-settings.png "Captura de pantalla de la configuración de eventos de Teams Live que puede configurar en el centro de administración de Microsoft Teams") 

## <a name="set-up-event-support-url"></a>Configurar la dirección URL de compatibilidad de eventos

Esta dirección URL se muestra a los asistentes de eventos en directo. Agregue la dirección URL de soporte técnico de su organización para proporcionar a los asistentes una manera de ponerse en contacto con el soporte técnico durante un evento en vivo.

### <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Un icono que muestra el logotipo de Microsoft Teams](../media/teams-logo-30x30.png) Usar el centro de administración de Microsoft Teams

1. En el navegación de la izquierda, vaya a la**configuración de eventos**de **reuniones** > en directo.
2. En **dirección URL de soporte técnico**, escriba la dirección URL de soporte técnico de su organización. 

    ![Configuración de dirección URL de soporte técnico para eventos en directo en el centro de administración](../media/teams-live-events-settings-supporturl.png "Captura de pantalla de la configuración de URL de soporte técnico para los eventos de Teams Live")

### <a name="using-windows-powershell"></a>Vea Enviar un correo electrónico a un usuario con su información de conferencias de Audio.
Ejecute lo siguiente:
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}” 
```
Para obtener más información, consulte [set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).
## <a name="configure-a-third-party-video-distribution-provider"></a>Configurar un proveedor de distribución de video de terceros 

Si compró y configuró una solución de red definida por software (SDN) o una solución de red de entrega de contenido empresarial (eCDN) a través de un socio de envío de video de Microsoft, configure el proveedor de eventos en vivo en Teams. 

### <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Un icono que muestra el logotipo de Microsoft Teams](../media/teams-logo-30x30.png) Usar el centro de administración de Microsoft Teams

1. En el navegación de la izquierda, vaya a la**configuración de eventos**de **reuniones** > en directo.
2. En **proveedores de distribución de vídeo de terceros**, complete lo siguiente: 

    ![Configuración del proveedor de distribución de vídeo de terceros en el centro de administración](../media/teams-live-events-settings-distribution-provider.png "Captura de pantalla de la configuración del proveedor de distribución de vídeo de terceros para eventos en directo")

    - **Usar un proveedor de distribución de terceros** Active esta opción para habilitar el proveedor de distribución de vídeo de terceros.
    - **Nombre del proveedor de Sdn** Elija el proveedor que está usando.
    - **Clave de licencia de proveedor** Escriba el identificador de licencia que recibió del contacto del proveedor.
    - **URL de plantilla** de la API de Sdn Escriba la dirección URL de la plantilla API que recibió del contacto del proveedor.

### <a name="using-windows-powershell"></a>Vea Enviar un correo electrónico a un usuario con su información de conferencias de Audio.
Obtenga el identificador de licencia o el token de API y la plantilla de API de su contacto de proveedor y, a continuación, ejecute uno de los siguientes, según el proveedor que use:

**Subárbol** 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName hive -SdnLicenseId {license ID GUID provided by Hive} -SdnApiTemplateUrl “{API template URL provided by Hive}”
```
**Kollective** 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName kollective -SdnApiTemplateUrl "{API template URL provided by Kollective}" -SdnApiToken {API token GUID provided by Kollective}
```
Para obtener más información, consulte [set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).

> [!NOTE]
> Si planea crear eventos en directo con una aplicación o dispositivo externo, también tendrá que [configurar el proveedor de eCDN con Microsoft Stream](https://docs.microsoft.com/stream/network-caching). 

### <a name="related-topics"></a>Temas relacionados
- [¿Qué son los eventos en directo en Teams?](what-are-teams-live-events.md)
- [Planear eventos en directo en Teams](plan-for-teams-live-events.md)
- [Configuración de eventos en directo en Teams](set-up-for-teams-live-events.md)