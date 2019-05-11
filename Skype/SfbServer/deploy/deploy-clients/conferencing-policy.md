---
title: Directiva de conferencias para las cuentas del Sistema de salas de Skype
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: davgroom
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4dd8be28-5156-411b-8ccd-eff7f75cb897
description: Lea este tema para obtener información acerca de cómo asignar directivas de conferencias para cuentas del Sistema de salas de Skype.
ms.openlocfilehash: 7574824e03be7dd48163befb6243bc557833bd5e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33895408"
---
# <a name="conferencing-policy-for-skype-room-system-accounts"></a>Directiva de conferencias para las cuentas del Sistema de salas de Skype
 
Lea este tema para obtener información acerca de cómo asignar directivas de conferencias para cuentas del Sistema de salas de Skype.
  
## <a name="conferencing-policy-features"></a>Características de la directiva de conferencias

La directiva de conferencia asignada a la cuenta del sistema de salas de Skype debe tener determinadas características. La mayoría de los casos, el cliente del sistema de salas de Skype se une a una reunión programada y, por lo tanto, la directiva de conferencia del organizador de la reunión afectará a la conferencia. Sin embargo, en Skype para Business Server, determinadas funcionalidades dependen de configuración del participante. Por ejemplo, si la directiva del participante lo permite una resolución de vídeo máxima de 1080p, los participantes experimentar esta mayor capacidad de vídeo de resolución en la conferencia, incluso si la directiva del organizador no lo permite. En la siguiente tabla se describe varias esas opciones de configuración que deben tener en cuenta al configurar las directivas de conferencia para cuentas del sistema de salas de Skype en su organización. 
  
|Característica  <br/> |Valor  <br/> |Comment  <br/> |
|:-----|:-----|:-----|
|AllowIPAudio  <br/> |VERDADERO  <br/> |Debe ser true para el audio del sistema de salas de Skype  <br/> |
|AllowIPVideo  <br/> |VERDADERO  <br/> |Debe ser true para el audio del sistema de salas de Skype para que funcionen en sesiones de Pizarra (ad hoc) Reunirse ahora en el sistema de sala de Skype  <br/> |
|AllowMultiView  <br/> |VERDADERO  <br/> |Permite Skype salón del sistema representar varias vistas, varias secuencias de vídeo  <br/> |
|AllowParticipantControl  <br/> |VERDADERO  <br/> |Afecta a Reunirse ahora las sesiones de Pizarra (ad hoc) en el sistema de sala de Skype  <br/> |
|AllowAnnotations  <br/> |VERDADERO  <br/> |Afecta a Reunirse ahora las sesiones de Pizarra (ad hoc) en el sistema de sala de Skype  <br/> |
|DisablePowerPointAnnotations  <br/> |FALSO  <br/> |Afecta a Reunirse ahora las sesiones de Pizarra (ad hoc) en el sistema de sala de Skype  <br/> |
|AllowUserToScheduleMeetingsWithAppSharing  <br/> |VERDADERO  <br/> |Afecta a Reunirse ahora las sesiones de Pizarra (ad hoc) en el sistema de sala de Skype  <br/> |
|AllowNonEnterpriseVoiceUsersToDialOut  <br/> |FALSO  <br/> |Depende de si la cuenta es Enterprise Voice (EV) habilitado (vea las cuentas del sistema de salas de habilitar Skype para Skype para sección empresarial)  <br/> |
|AllowAnonymousUsersToDialOut  <br/> |FALSO  <br/> |Depende de si la cuenta está habilitada para telefonía IP empresarial (EV)  <br/> |
|AllowAnonymousParticipantsInMeetings  <br/> |VERDADERO  <br/> |Afecta a Reunirse ahora las sesiones de Pizarra (ad hoc) en el sistema de sala de Skype  <br/> |
|AllowExternalUsersToSaveContent  <br/> |VERDADERO  <br/> |Afecta a Reunirse ahora las sesiones de Pizarra (ad hoc) en el sistema de sala de Skype  <br/> |
|AllowExternalUserControl  <br/> |FALSO  <br/> |Afecta a Reunirse ahora las sesiones de Pizarra (ad hoc) en el sistema de sala de Skype  <br/> |
|AllowExternalUsersToRecordMeeting  <br/> |FALSO  <br/> |Afecta a Reunirse ahora las sesiones de Pizarra (ad hoc) en el sistema de sala de Skype  <br/> |
|AllowPolls  <br/> |VERDADERO  <br/> |N/a en Reunirse ahora las reuniones (ad hoc), pero el sistema de sala de Skype puede responder a sondeos en la pantalla en la parte delantera del salón  <br/> |
|AllowSharedNotes  <br/> |VERDADERO  <br/> |N/a en Reunirse ahora las reuniones (ad hoc), pero el sistema de sala de Skype puede responder a sondeos en la pantalla en la parte delantera del salón  <br/> |
|EnableDialInConferencing  <br/> |VERDADERO  <br/> |Afecta a Reunirse ahora las sesiones de Pizarra (ad hoc) en el sistema de sala de Skype  <br/> |
|EnableAppDesktopSharing  <br/> |Escritorio  <br/> |Afecta a Reunirse ahora las sesiones de Pizarra (ad hoc) en el sistema de sala de Skype  <br/> |
|AllowConferenceRecording  <br/> |FALSO  <br/> |No disponible para el sistema de salas de Skype. Si es TRUE, un asistente remoto podría realizar grabaciones  <br/> |
|EnableP2PRecording  <br/> |FALSO  <br/> |No disponible para el sistema de salas de Skype. Si es TRUE, un asistente remoto podría realizar grabaciones  <br/> |
|EnableFileTransfer  <br/> |TRUE  <br/> |N/D  <br/> |
|EnableP2PFileTransfer  <br/> |TRUE  <br/> |N/D  <br/> |
|EnableP2PVideo  <br/> |VERDADERO  <br/> |Permite que el cliente del sistema de salas de Skype participar en las sesiones de vídeo punto a punto  <br/> |
|AllowLargeMeetings  <br/> |FALSE  <br/> |N/D  <br/> |
|EnableDataCollaboration  <br/> |TRUE  <br/> |Afecta a Reunirse ahora las sesiones de Pizarra (ad hoc) en el sistema de sala de Skype  <br/> |
|MaxVideoConferenceResolution  <br/> |VGA  <br/> |Omite por Skype para Business Server, sistema de sala de Skype usa HD1080  <br/> |
|MaxMeetingSize  <br/> |250  <br/> |Afecta a Reunirse ahora las sesiones de Pizarra (ad hoc) en el sistema de sala de Skype  <br/> |
|AudioBitRateKb  <br/> |200  <br/> |Consulte la nota al final de la tabla\*  <br/> |
|VideoBitRateKb  <br/> |5000  <br/> |Esta es la máxima velocidad permitida de vídeo saliente. Sistema de sala de Skype puede enviar una 1080 stream junto con panorámico (si se usa RoundTable) a esta velocidad de bits. \*  <br/> |
|AppSharingBitRateKb  <br/> |5000  <br/> |Consulte la nota al final de la tabla\*  <br/> |
|FileTransferBitRateKb  <br/> |5000  <br/> |N/D  <br/> |
|TotalReceiveVideoBitRateKb  <br/> |20000  <br/> |Le recomendamos que configure esta opción tan alta como pueda. El ancho de banda eficaz depende de las condiciones de red en el momento de las conferencias.\*  <br/> |
|EnableMultiViewJoin  <br/> |TRUE  <br/> |Debe ser TRUE para sistema de sala de Skype para asegurarse de secuencias de vídeo de varias vistas  <br/> |
   
* Para obtener información acerca de la planeación de ancho de banda, vea [requisitos de ancho de banda de red para el tráfico de medios](../../plan-your-deployment/network-requirements/network-requirements.md#network-bandwidth-requirements-for-media-traffic).
  
> [!NOTE]
> Si el cliente del sistema de salas de Skype intenta unirse a una reunión programada organizada por un usuario alojado en un grupo de servidores de Lync Server 2010, directiva de conferencia del organizador de la reunión podría impedir que el cliente del sistema de salas de Skype realización de colaboración. 
  
## <a name="meeting-authentication"></a>Autenticación de reunión

Sistema de sala de Skype solicita a los usuarios para la autenticación al usar la reunión vínculo unirse a unirse a una reunión restringida; Por ejemplo, una reunión para qué sala de reuniones se han configurado las opciones en Outlook. Esta configuración siempre está activada para las reuniones personalizadas y siempre se realizará la solicitud a los usuarios. Sin embargo, en el caso de reuniones no restringidas, los usuarios pueden unirse a la reunión sin autenticación. 
  
El siguiente comando habilita a los administradores para requerir autenticación para todas las reuniones, incluidas las no restringidas: 
  
```
Set-CsMeetingConfiguration -RequireRoomSystemsAuthorization $TRUE
```

De forma predeterminada, RequireRoomSystemsAuthorization es FALSE. 
  

