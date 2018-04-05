---
title: Directiva de conferencias para las cuentas del Sistema de salas de Skype
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/4/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4dd8be28-5156-411b-8ccd-eff7f75cb897
description: Lea este tema para obtener información acerca de cómo asignar directivas de conferencias para cuentas del Sistema de salas de Skype.
ms.openlocfilehash: 07ce5031bd053837d69d3ed3da27aabb344c3a65
ms.sourcegitcommit: ffca287cf70db2cab14cc1a6cb7cea68317bedd1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/05/2018
---
# <a name="conferencing-policy-for-skype-room-system-accounts"></a>Directiva de conferencias para las cuentas del Sistema de salas de Skype
 
Lea este tema para obtener información acerca de cómo asignar directivas de conferencias para cuentas del Sistema de salas de Skype.
  
## <a name="conferencing-policy-features"></a>Características de la directiva de conferencias

La directiva de conferencia asignada a la cuenta de sistema del sitio de Skype debe tener ciertas características. La mayoría de los casos, el cliente de sistema de sala de Skype se une a una reunión programada y, por tanto, la directiva de conferencia del organizador de la reunión afectará a la conferencia. Sin embargo, en Skype para Business Server, ciertas capacidades dependen configuración del participante en la. Por ejemplo, si la directiva de los participantes permite una resolución máxima de vídeo de 1080p, los participantes experimentar esta capacidad de vídeo de resolución más alto en la conferencia incluso si directiva del organizador no lo permite. La tabla siguiente describe varias la configuración que debe tener en cuenta al configurar las directivas de la conferencia para cuentas de sistema del sitio de Skype en su organización. 
  
|Característica  <br/> |Valor  <br/> |Comment  <br/> |
|:-----|:-----|:-----|
|AllowIPAudio  <br/> |TRUE  <br/> |Debe ser true para el sonido del sistema de sala de Skype  <br/> |
|AllowIPVideo  <br/> |TRUE  <br/> |Debe ser true para audio de sistema del sitio de Skype trabajar en sesiones de Pizarra (ad hoc) Reunirse ahora en el sistema del sitio de Skype  <br/> |
|AllowMultiView  <br/> |TRUE  <br/> |Permite sistema Skype sala representar vistas múltiples, varias secuencias de vídeo  <br/> |
|AllowParticipantControl  <br/> |TRUE  <br/> |Afecta a Reunirse ahora sesiones de Pizarra (ad hoc) en el sistema del sitio de Skype  <br/> |
|AllowAnnotations  <br/> |TRUE  <br/> |Afecta a Reunirse ahora sesiones de Pizarra (ad hoc) en el sistema del sitio de Skype  <br/> |
|DisablePowerPointAnnotations  <br/> |FALSE  <br/> |Afecta a Reunirse ahora sesiones de Pizarra (ad hoc) en el sistema del sitio de Skype  <br/> |
|AllowUserToScheduleMeetingsWithAppSharing  <br/> |TRUE  <br/> |Afecta a Reunirse ahora sesiones de Pizarra (ad hoc) en el sistema del sitio de Skype  <br/> |
|AllowNonEnterpriseVoiceUsersToDialOut  <br/> |FALSE  <br/> |Depende de si la cuenta es de Telefonía IP empresarial (EV) habilitado (vea las cuentas del sistema de sala de habilitar Skype de Skype para la sección de negocios)  <br/> |
|AllowAnonymousUsersToDialOut  <br/> |FALSE  <br/> |Depende de si la cuenta está habilitada para telefonía IP empresarial (EV)  <br/> |
|AllowAnonymousParticipantsInMeetings  <br/> |TRUE  <br/> |Afecta a Reunirse ahora sesiones de Pizarra (ad hoc) en el sistema del sitio de Skype  <br/> |
|AllowExternalUsersToSaveContent  <br/> |TRUE  <br/> |Afecta a Reunirse ahora sesiones de Pizarra (ad hoc) en el sistema del sitio de Skype  <br/> |
|AllowExternalUserControl  <br/> |FALSE  <br/> |Afecta a Reunirse ahora sesiones de Pizarra (ad hoc) en el sistema del sitio de Skype  <br/> |
|AllowExternalUsersToRecordMeeting  <br/> |FALSE  <br/> |Afecta a Reunirse ahora sesiones de Pizarra (ad hoc) en el sistema del sitio de Skype  <br/> |
|AllowPolls  <br/> |TRUE  <br/> |N/A en Reunirse ahora reuniones (ad hoc), pero el sistema de sala de Skype puede responder a sondeos en la pantalla en la parte delantera de la sala  <br/> |
|AllowSharedNotes  <br/> |TRUE  <br/> |N/A en Reunirse ahora reuniones (ad hoc), pero el sistema de sala de Skype puede responder a sondeos en la pantalla en la parte delantera de la sala  <br/> |
|EnableDialInConferencing  <br/> |TRUE  <br/> |Afecta a Reunirse ahora sesiones de Pizarra (ad hoc) en el sistema del sitio de Skype  <br/> |
|EnableAppDesktopSharing  <br/> |Escritorio  <br/> |Afecta a Reunirse ahora sesiones de Pizarra (ad hoc) en el sistema del sitio de Skype  <br/> |
|AllowConferenceRecording  <br/> |FALSE  <br/> |No disponible para el sistema del sitio de Skype. Si es TRUE, un asistente remoto podría realizar grabaciones  <br/> |
|EnableP2PRecording  <br/> |FALSE  <br/> |No disponible para el sistema del sitio de Skype. Si es TRUE, un asistente remoto podría realizar grabaciones  <br/> |
|EnableFileTransfer  <br/> |TRUE  <br/> |N/D  <br/> |
|EnableP2PFileTransfer  <br/> |TRUE  <br/> |N/D  <br/> |
|EnableP2PVideo  <br/> |TRUE  <br/> |Permite que el cliente de sistema de sala de Skype participar en las sesiones de video de peer-to-peer  <br/> |
|AllowLargeMeetings  <br/> |FALSE  <br/> |N/D  <br/> |
|EnableDataCollaboration  <br/> |TRUE  <br/> |Afecta a Reunirse ahora sesiones de Pizarra (ad hoc) en el sistema del sitio de Skype  <br/> |
|MaxVideoConferenceResolution  <br/> |VGA  <br/> |Ignorado por Skype para Business Server, sistema de sala de Skype utiliza HD1080  <br/> |
|MaxMeetingSize  <br/> |250  <br/> |Afecta a Reunirse ahora sesiones de Pizarra (ad hoc) en el sistema del sitio de Skype  <br/> |
|AudioBitRateKb  <br/> |200  <br/> |Ver Nota al final de la tabla\*  <br/> |
|VideoBitRateKb  <br/> |5000  <br/> |Esta es la máxima velocidad permitida de vídeo saliente. Sistema de sala de Skype puede enviar uno 1080 de secuencia junto con pano (si se utiliza RoundTable) a esta velocidad de bits. \*  <br/> |
|AppSharingBitRateKb  <br/> |5000  <br/> |Ver Nota al final de la tabla\*  <br/> |
|FileTransferBitRateKb  <br/> |5000  <br/> |N/D  <br/> |
|TotalReceiveVideoBitRateKb  <br/> |20000  <br/> |Le recomendamos que configure esta opción tan alta como pueda. El ancho de banda efectivo depende de las condiciones de la red en el momento de conferencias.\*  <br/> |
|EnableMultiViewJoin  <br/> |TRUE  <br/> |Debe ser TRUE para el sistema de sala de Skype para asegurar vistas múltiples secuencias de vídeo  <br/> |
   
* Para obtener información acerca de cómo planear el ancho de banda, vea [Requisitos de ancho de banda de red para el tráfico de medios](https://technet.microsoft.com/en-us/library/jj688118%28v=ocs.15%29.aspx).
  
> [!NOTE]
> Si el cliente de sistema de sala de Skype intenta unirse a una reunión programada organizada por un usuario que está alojado en un grupo de Lync Server 2010, directiva de conferencia del organizador de la reunión podría impedir al cliente del sistema de sala de Skype realización de colaboración. 
  
## <a name="meeting-authentication"></a>Autenticación de reunión

Sistema de sala de Skype pide a los usuarios para la autenticación cuando utilicen la reunión vínculo unirse para unirse a una reunión restringida; Por ejemplo, una reunión de la sala de reuniones se han configurado opciones de Outlook. Esta configuración siempre está activada para las reuniones personalizadas y siempre se realizará la solicitud a los usuarios. Sin embargo, en el caso de reuniones no restringidas, los usuarios pueden unirse a la reunión sin autenticación. 
  
El siguiente comando habilita a los administradores para requerir autenticación para todas las reuniones, incluidas las no restringidas: 
  
```
Set-CsMeetingConfiguration -RequireRoomSystemsAuthorization $TRUE
```

De forma predeterminada, RequireRoomSystemsAuthorization es FALSE. 
  

