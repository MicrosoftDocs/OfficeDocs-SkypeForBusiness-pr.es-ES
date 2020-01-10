---
title: Directiva de conferencias para las cuentas del Sistema de salas de Skype
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: sohailta
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4dd8be28-5156-411b-8ccd-eff7f75cb897
description: Lea este tema para obtener información acerca de cómo asignar directivas de conferencias para cuentas del Sistema de salas de Skype.
ms.openlocfilehash: e235ac84b92f770ae16eec3bd99511e4beea8871
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003550"
---
# <a name="conferencing-policy-for-skype-room-system-accounts"></a>Directiva de conferencias para las cuentas del Sistema de salas de Skype
 
Lea este tema para obtener información acerca de cómo asignar directivas de conferencias para cuentas del Sistema de salas de Skype.
  
## <a name="conferencing-policy-features"></a>Características de la directiva de conferencias

La Directiva de conferencia asignada a la cuenta del sistema de salas de Skype debe tener ciertas características. La mayoría de las veces, el cliente del sistema de salas de Skype se une a una reunión programada y, por lo tanto, la Directiva de conferencia del organizador de la reunión afectará a la Conferencia. Sin embargo, en Skype empresarial Server determinadas capacidades dependen de la configuración del participante. Por ejemplo, si la política del participante permite una resolución máxima de video de 1080p, los participantes experimentarán esta mayor capacidad de video en la Conferencia incluso si la política del organizador no lo permite. En la tabla siguiente se describen algunas de estas opciones de configuración que debe tener en cuenta al configurar directivas de conferencia para cuentas del sistema de salas de Skype en su organización. 
  
|Característica  <br/> |Valor  <br/> |Comment  <br/> |
|:-----|:-----|:-----|
|AllowIPAudio  <br/> |VERDADERO  <br/> |Debe ser verdadero para el audio del sistema de la sala de Skype  <br/> |
|AllowIPVideo  <br/> |VERDADERO  <br/> |Debe ser verdadero para que el audio del sistema de la sala de Skype funcione en sesiones de pizarra reunirse ahora (ad hoc) en el sistema de salas de Skype  <br/> |
|AllowMultiView  <br/> |VERDADERO  <br/> |Permite que el sistema de salas de Skype presente videollamadas múltiples y de vista múltiple  <br/> |
|AllowParticipantControl  <br/> |VERDADERO  <br/> |Afecta a las sesiones de pizarra reunirse ahora (ad hoc) en el sistema de salas de Skype  <br/> |
|AllowAnnotations  <br/> |VERDADERO  <br/> |Afecta a las sesiones de pizarra reunirse ahora (ad hoc) en el sistema de salas de Skype  <br/> |
|DisablePowerPointAnnotations  <br/> |FALSO  <br/> |Afecta a las sesiones de pizarra reunirse ahora (ad hoc) en el sistema de salas de Skype  <br/> |
|AllowUserToScheduleMeetingsWithAppSharing  <br/> |VERDADERO  <br/> |Afecta a las sesiones de pizarra reunirse ahora (ad hoc) en el sistema de salas de Skype  <br/> |
|AllowNonEnterpriseVoiceUsersToDialOut  <br/> |FALSO  <br/> |Depende de si la cuenta es Enterprise Voice (EV) habilitada (consulte la sección habilitar las cuentas de sistema de la sala de Skype para Skype empresarial)  <br/> |
|AllowAnonymousUsersToDialOut  <br/> |FALSO  <br/> |Depende de si la cuenta está habilitada para telefonía IP empresarial (EV)  <br/> |
|AllowAnonymousParticipantsInMeetings  <br/> |VERDADERO  <br/> |Afecta a las sesiones de pizarra reunirse ahora (ad hoc) en el sistema de salas de Skype  <br/> |
|AllowExternalUsersToSaveContent  <br/> |VERDADERO  <br/> |Afecta a las sesiones de pizarra reunirse ahora (ad hoc) en el sistema de salas de Skype  <br/> |
|AllowExternalUserControl  <br/> |FALSO  <br/> |Afecta a las sesiones de pizarra reunirse ahora (ad hoc) en el sistema de salas de Skype  <br/> |
|AllowExternalUsersToRecordMeeting  <br/> |FALSO  <br/> |Afecta a las sesiones de pizarra reunirse ahora (ad hoc) en el sistema de salas de Skype  <br/> |
|AllowPolls  <br/> |VERDADERO  <br/> |No hay reuniones para reunirse ahora (ad hoc), pero el sistema de salas de Skype puede responder a los sondeos en la pantalla al frente de la habitación.  <br/> |
|AllowSharedNotes  <br/> |VERDADERO  <br/> |No hay reuniones para reunirse ahora (ad hoc), pero el sistema de salas de Skype puede responder a los sondeos en la pantalla al frente de la habitación.  <br/> |
|EnableDialInConferencing  <br/> |VERDADERO  <br/> |Afecta a las sesiones de pizarra reunirse ahora (ad hoc) en el sistema de salas de Skype  <br/> |
|EnableAppDesktopSharing  <br/> |Escritorio  <br/> |Afecta a las sesiones de pizarra reunirse ahora (ad hoc) en el sistema de salas de Skype  <br/> |
|AllowConferenceRecording  <br/> |FALSO  <br/> |No disponible para el sistema de salas de Skype. Si es TRUE, un asistente remoto podría realizar grabaciones  <br/> |
|EnableP2PRecording  <br/> |FALSO  <br/> |No disponible para el sistema de salas de Skype. Si es TRUE, un asistente remoto podría realizar grabaciones  <br/> |
|EnableFileTransfer  <br/> |TRUE  <br/> |N/D  <br/> |
|EnableP2PFileTransfer  <br/> |TRUE  <br/> |N/D  <br/> |
|EnableP2PVideo  <br/> |VERDADERO  <br/> |Permite que el cliente del sistema de salas de Skype participe en sesiones de vídeo de punto a punto  <br/> |
|AllowLargeMeetings  <br/> |FALSE  <br/> |N/D  <br/> |
|EnableDataCollaboration  <br/> |TRUE  <br/> |Afecta a las sesiones de pizarra reunirse ahora (ad hoc) en el sistema de salas de Skype  <br/> |
|MaxVideoConferenceResolution  <br/> |VGA  <br/> |Skype empresarial Server pasa por alto el sistema de salas de Skype para usar HD1080  <br/> |
|MaxMeetingSize  <br/> |250  <br/> |Afecta a las sesiones de pizarra reunirse ahora (ad hoc) en el sistema de salas de Skype  <br/> |
|AudioBitRateKb  <br/> |200  <br/> |Consulte la nota al final de la tabla\*  <br/> |
|VideoBitRateKb  <br/> |5000  <br/> |Esta es la máxima velocidad permitida de vídeo saliente. El sistema de salas de Skype puede enviar un flujo de 1 1080 junto con Pano (si se usa RoundTable) a esta tarifa de bits. \*  <br/> |
|AppSharingBitRateKb  <br/> |5000  <br/> |Consulte la nota al final de la tabla\*  <br/> |
|FileTransferBitRateKb  <br/> |5000  <br/> |N/D  <br/> |
|TotalReceiveVideoBitRateKb  <br/> |20000  <br/> |Le recomendamos que configure esta opción tan alta como pueda. El ancho de banda efectivo depende de las condiciones de la red en el momento de las conferencias.\*  <br/> |
|EnableMultiViewJoin  <br/> |TRUE  <br/> |Debe ser verdadero para que el sistema de salas de Skype garantice las transmisiones de video de vista múltiple  <br/> |
   
* Para obtener información sobre la planeación del ancho de banda, consulte [requisitos de ancho de banda de red para tráfico de multimedia](../../plan-your-deployment/network-requirements/network-requirements.md#network-bandwidth-requirements-for-media-traffic).
  
> [!NOTE]
> Si el cliente del sistema de Skype Room intenta unirse a una reunión programada organizada por un usuario alojado en un grupo de servidores de Lync Server 2010, la Directiva de conferencia del organizador de la reunión puede impedir que el cliente del sistema de la sala de Skype realice la colaboración. 
  
## <a name="meeting-authentication"></a>Autenticación de reunión

El sistema de salas de Skype solicita autenticación a los usuarios cuando usan el vínculo unirse a la reunión para unirse a una reunión restringida; por ejemplo, una reunión para la que las opciones de la sala de reuniones se han configurado en Outlook. Esta configuración siempre está activada para las reuniones personalizadas y siempre se realizará la solicitud a los usuarios. Sin embargo, en el caso de reuniones no restringidas, los usuarios pueden unirse a la reunión sin autenticación. 
  
El siguiente comando habilita a los administradores para requerir autenticación para todas las reuniones, incluidas las no restringidas: 
  
```powershell
Set-CsMeetingConfiguration -RequireRoomSystemsAuthorization $TRUE
```

De forma predeterminada, RequireRoomSystemsAuthorization es FALSE. 
  

