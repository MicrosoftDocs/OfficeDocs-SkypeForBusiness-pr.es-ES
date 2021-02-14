---
title: Directiva de conferencia para cuentas del Sistema de sala de Skype
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: sohailta
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4dd8be28-5156-411b-8ccd-eff7f75cb897
description: Lea este tema para obtener información sobre cómo asignar directivas de conferencia para cuentas del Sistema de sala de Skype.
ms.openlocfilehash: 3fb462168bd4121f5feef365f881ed9f02620e25
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812730"
---
# <a name="conferencing-policy-for-skype-room-system-accounts"></a>Directiva de conferencia para cuentas del Sistema de sala de Skype
 
Lea este tema para obtener información sobre cómo asignar directivas de conferencia para cuentas del Sistema de sala de Skype.
  
## <a name="conferencing-policy-features"></a>Características de directiva de conferencia

La directiva de conferencia asignada a la cuenta del Sistema de sala de Skype debe tener ciertas características. La mayoría de las veces, el cliente del Sistema de salas de Skype se une a una reunión programada y, por lo tanto, la directiva de conferencia del organizador de la reunión afectará a la conferencia. Sin embargo, en Skype Empresarial Server, ciertas funcionalidades dependen de la configuración del participante. Por ejemplo, si la directiva del participante permite una resolución de vídeo máxima de 1080p, los participantes experimentarán esta capacidad de vídeo de mayor resolución en la conferencia incluso si la directiva del organizador no la permite. En la tabla siguiente se describen varias opciones de configuración que debe tener en cuenta al configurar directivas de conferencia para cuentas del Sistema de sala de Skype en su organización. 
  
|Característica  <br/> |Valor  <br/> |Comentario  <br/> |
|:-----|:-----|:-----|
|AllowIPAudio  <br/> |TRUE  <br/> |Debe ser true para el audio del Sistema de sala de Skype  <br/> |
|AllowIPVideo  <br/> |TRUE  <br/> |Debe ser true para que el audio del Sistema de sala de Skype funcione en sesiones de pizarra reunirse ahora (ad hoc) en el Sistema de sala de Skype  <br/> |
|AllowMultiView  <br/> |TRUE  <br/> |Permite que el Sistema de sala de Skype represente varias secuencias de vídeo de varias vistas  <br/> |
|AllowParticipantControl  <br/> |TRUE  <br/> |Afecta a las sesiones de pizarra reunirse ahora (ad hoc) en el Sistema de sala de Skype  <br/> |
|AllowAnnotations  <br/> |TRUE  <br/> |Afecta a las sesiones de pizarra reunirse ahora (ad hoc) en el Sistema de sala de Skype  <br/> |
|DisablePowerPointAnnotations  <br/> |FALSE  <br/> |Afecta a las sesiones de pizarra reunirse ahora (ad hoc) en el Sistema de sala de Skype  <br/> |
|AllowUserToScheduleMeetingsWithAppSharing  <br/> |TRUE  <br/> |Afecta a las sesiones de pizarra reunirse ahora (ad hoc) en el Sistema de sala de Skype  <br/> |
|AllowNonEnterpriseVoiceUsersToDialOut  <br/> |FALSE  <br/> |Depende de si la cuenta está Telefonía IP empresarial (EV) habilitada (vea la sección Habilitar cuentas del sistema de sala de Skype para Skype Empresarial)  <br/> |
|AllowAnonymousUsersToDialOut  <br/> |FALSE  <br/> |Depende de si la cuenta está Telefonía IP empresarial (EV) habilitada  <br/> |
|AllowAnonymousParticipantsInMeetings  <br/> |TRUE  <br/> |Afecta a las sesiones de pizarra reunirse ahora (ad hoc) en el Sistema de sala de Skype  <br/> |
|AllowExternalUsersToSaveContent  <br/> |TRUE  <br/> |Afecta a las sesiones de pizarra reunirse ahora (ad hoc) en el Sistema de sala de Skype  <br/> |
|AllowExternalUserControl  <br/> |FALSE  <br/> |Afecta a las sesiones de pizarra reunirse ahora (ad hoc) en el Sistema de sala de Skype  <br/> |
|AllowExternalUsersToRecordMeeting  <br/> |FALSE  <br/> |Afecta a las sesiones de pizarra reunirse ahora (ad hoc) en el Sistema de sala de Skype  <br/> |
|AllowPolls  <br/> |TRUE  <br/> |N/A en reuniones reunirse ahora (ad hoc), pero el Sistema de salas de Skype puede responder a sondeos en la pantalla en la parte frontal de la sala  <br/> |
|AllowSharedNotes  <br/> |TRUE  <br/> |N/A en reuniones reunirse ahora (ad hoc), pero el Sistema de salas de Skype puede responder a sondeos en la pantalla en la parte frontal de la sala  <br/> |
|EnableDialInConferencing  <br/> |TRUE  <br/> |Afecta a las sesiones de pizarra reunirse ahora (ad hoc) en el Sistema de sala de Skype  <br/> |
|EnableAppDesktopSharing  <br/> |Desktop  <br/> |Afecta a las sesiones de pizarra reunirse ahora (ad hoc) en el Sistema de sala de Skype  <br/> |
|AllowConferenceRecording  <br/> |FALSE  <br/> |N/A para el Sistema de sala de Skype. Si es TRUE, un usuario remoto podría grabar  <br/> |
|EnableP2PRecording  <br/> |FALSE  <br/> |N/A para el Sistema de sala de Skype. Si es TRUE, un usuario remoto podría grabar  <br/> |
|EnableFileTransfer  <br/> |TRUE  <br/> |N/D  <br/> |
|EnableP2PFileTransfer  <br/> |TRUE  <br/> |N/D  <br/> |
|EnableP2PVideo  <br/> |TRUE  <br/> |Permite que el cliente del Sistema de sala de Skype participe en sesiones de vídeo punto a punto  <br/> |
|AllowLargeMeetings  <br/> |FALSE  <br/> |N/D  <br/> |
|EnableDataCollaboration  <br/> |TRUE  <br/> |Afecta a las sesiones de pizarra reunirse ahora (ad hoc) en el Sistema de sala de Skype  <br/> |
|MaxVideoConferenceResolution  <br/> |VGA  <br/> |Ignorado por Skype Empresarial Server, el Sistema de sala de Skype usa HD1080  <br/> |
|MaxMeetingSize  <br/> |250  <br/> |Afecta a las sesiones de pizarra reunirse ahora (ad hoc) en el Sistema de sala de Skype  <br/> |
|AudioBitRateKb  <br/> |200  <br/> |Ver nota al final de la tabla\*  <br/> |
|VideoBitRateKb  <br/> |5000  <br/> |Esta es la velocidad de bits máxima de vídeo saliente permitida. El Sistema de sala de Skype puede enviar una secuencia de 1080 junto con el pano (si se usa RoundTable) a esta velocidad de bits. \*  <br/> |
|AppSharingBitRateKb  <br/> |5000  <br/> |Ver nota al final de la tabla\*  <br/> |
|FileTransferBitRateKb  <br/> |5000  <br/> |N/D  <br/> |
|TotalReceiveVideoBitRateKb  <br/> |20000  <br/> |Le recomendamos que lo establezca lo más alto posible. El ancho de banda efectivo depende de las condiciones de red en el momento de las conferencias.\*  <br/> |
|EnableMultiViewJoin  <br/> |TRUE  <br/> |Debe ser TRUE para que el Sistema de sala de Skype garantice secuencias de vídeo de varias vistas  <br/> |
   
* Para obtener información sobre la planeación del ancho de banda, consulte [Requisitos de ancho de banda de red para el tráfico de medios.](../../plan-your-deployment/network-requirements/network-requirements.md#network-bandwidth-requirements-for-media-traffic)
  
> [!NOTE]
> Si el cliente del Sistema de salas de Skype intenta unirse a una reunión programada organizada por un usuario que se encuentra en un grupo de Lync Server 2010, la directiva de conferencia del organizador de la reunión podría impedir que el cliente del Sistema de salas de Skype realice la colaboración. 
  
## <a name="meeting-authentication"></a>Autenticación de reuniones

El Sistema de salas de Skype pide autenticación a los usuarios cuando usan el vínculo para unirse a la reunión para unirse a una reunión restringida; por ejemplo, una reunión para la que se han configurado opciones de sala de espera de reuniones en Outlook. Esta configuración siempre está en función de las reuniones personalizadas y siempre se pide a los usuarios. Sin embargo, para las reuniones sin restricciones, los usuarios pueden unirse a la reunión sin autenticación. 
  
El siguiente comando permite a los administradores requerir autenticación para todas las reuniones, incluidas las reuniones sin restricciones: 
  
```powershell
Set-CsMeetingConfiguration -RequireRoomSystemsAuthorization $TRUE
```

De forma predeterminada, RequireRoomSystemsAuthorization es FALSE. 
  

