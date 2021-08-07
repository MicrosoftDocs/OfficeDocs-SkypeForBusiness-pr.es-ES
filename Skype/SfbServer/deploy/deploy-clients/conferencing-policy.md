---
title: Directiva de conferencia para Skype del sistema de sala
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
description: Lea este tema para obtener información sobre cómo asignar directivas de conferencia para Skype del sistema de sala.
ms.openlocfilehash: 7f9d1e349563e20d29736d33900b4afce99f39c10b9222b23d291f5a9fa417b7
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54306022"
---
# <a name="conferencing-policy-for-skype-room-system-accounts"></a>Directiva de conferencia para Skype del sistema de sala
 
Lea este tema para obtener información sobre cómo asignar directivas de conferencia para Skype del sistema de sala.
  
## <a name="conferencing-policy-features"></a>Características de directiva de conferencia

La directiva de conferencia asignada a la cuenta Skype sistema de sala debe tener determinadas características. La mayoría de las veces, el cliente del Skype room system se une a una reunión programada y, por lo tanto, la directiva de conferencia del organizador de la reunión afectará a la conferencia. Sin embargo, en Skype Empresarial Server, ciertas capacidades dependen de la configuración del participante. Por ejemplo, si la directiva del participante permite una resolución máxima de vídeo de 1080p, los participantes experimentarán esta capacidad de vídeo de mayor resolución en la conferencia incluso si la directiva del organizador no lo permite. En la tabla siguiente se describen varias de estas opciones de configuración que debe tener en cuenta al configurar directivas de conferencia para las Skype del sistema de sala de la organización. 
  
|Característica  <br/> |Valor  <br/> |Comentario  <br/> |
|:-----|:-----|:-----|
|AllowIPAudio  <br/> |TRUE  <br/> |Debe ser true para Skype audio del sistema de sala  <br/> |
|AllowIPVideo  <br/> |TRUE  <br/> |Debe ser true para que Skype audio del sistema de sala funcione en las sesiones de pizarra Reunirse ahora (ad hoc) en Skype room system  <br/> |
|AllowMultiView  <br/> |TRUE  <br/> |Permite Skype room system para representar varias secuencias de vídeo de varias vistas  <br/> |
|AllowParticipantControl  <br/> |TRUE  <br/> |Afecta a las sesiones de pizarra Reunirse ahora (ad hoc) en Skype room system  <br/> |
|AllowAnnotations  <br/> |TRUE  <br/> |Afecta a las sesiones de pizarra Reunirse ahora (ad hoc) en Skype room system  <br/> |
|DisablePowerPointAnnotations  <br/> |FALSE  <br/> |Afecta a las sesiones de pizarra Reunirse ahora (ad hoc) en Skype room system  <br/> |
|AllowUserToScheduleMeetingsWithAppSharing  <br/> |TRUE  <br/> |Afecta a las sesiones de pizarra Reunirse ahora (ad hoc) en Skype room system  <br/> |
|AllowNonEnterpriseVoiceUsersToDialOut  <br/> |FALSE  <br/> |Depende de si la cuenta está Telefonía IP empresarial (EV) habilitada (consulte la sección Habilitar Skype del sistema de sala para Skype Empresarial)  <br/> |
|AllowAnonymousUsersToDialOut  <br/> |FALSE  <br/> |Depende de si la cuenta está Telefonía IP empresarial (EV) habilitada  <br/> |
|AllowAnonymousParticipantsInMeetings  <br/> |TRUE  <br/> |Afecta a las sesiones de pizarra Reunirse ahora (ad hoc) en Skype room system  <br/> |
|AllowExternalUsersToSaveContent  <br/> |TRUE  <br/> |Afecta a las sesiones de pizarra Reunirse ahora (ad hoc) en Skype room system  <br/> |
|AllowExternalUserControl  <br/> |FALSE  <br/> |Afecta a las sesiones de pizarra Reunirse ahora (ad hoc) en Skype room system  <br/> |
|AllowExternalUsersToRecordMeeting  <br/> |FALSE  <br/> |Afecta a las sesiones de pizarra Reunirse ahora (ad hoc) en Skype room system  <br/> |
|AllowPolls  <br/> |TRUE  <br/> |N/A en reuniones reunirse ahora (ad hoc), pero Skype sistema de salas puede responder a sondeos en la pantalla en la parte frontal de la sala  <br/> |
|AllowSharedNotes  <br/> |TRUE  <br/> |N/A en reuniones reunirse ahora (ad hoc), pero Skype sistema de salas puede responder a sondeos en la pantalla en la parte frontal de la sala  <br/> |
|EnableDialInConferencing  <br/> |TRUE  <br/> |Afecta a las sesiones de pizarra Reunirse ahora (ad hoc) en Skype room system  <br/> |
|EnableAppDesktopSharing  <br/> |Escritorio  <br/> |Afecta a las sesiones de pizarra Reunirse ahora (ad hoc) en Skype room system  <br/> |
|AllowConferenceRecording  <br/> |FALSE  <br/> |N/A para Skype room system. Si es TRUE, un usuario remoto podría grabar  <br/> |
|EnableP2PRecording  <br/> |FALSE  <br/> |N/A para Skype room system. Si es TRUE, un usuario remoto podría grabar  <br/> |
|EnableFileTransfer  <br/> |TRUE  <br/> |N/D  <br/> |
|EnableP2PFileTransfer  <br/> |TRUE  <br/> |N/D  <br/> |
|EnableP2PVideo  <br/> |TRUE  <br/> |Permite al Skype room system participar en sesiones de vídeo punto a punto  <br/> |
|AllowLargeMeetings  <br/> |FALSE  <br/> |N/D  <br/> |
|EnableDataCollaboration  <br/> |TRUE  <br/> |Afecta a las sesiones de pizarra Reunirse ahora (ad hoc) en Skype room system  <br/> |
|MaxVideoConferenceResolution  <br/> |VGA  <br/> |Ignorado por Skype Empresarial Server, Skype room system usa HD1080  <br/> |
|MaxMeetingSize  <br/> |250  <br/> |Afecta a las sesiones de pizarra Reunirse ahora (ad hoc) en Skype room system  <br/> |
|AudioBitRateKb  <br/> |200  <br/> |Ver nota al final de la tabla\*  <br/> |
|VideoBitRateKb  <br/> |5000  <br/> |Esta es la velocidad máxima de bits de vídeo saliente permitida. Skype Room System puede enviar una secuencia 1080 junto con pano (si se usa RoundTable) a esta velocidad de bits. \*  <br/> |
|AppSharingBitRateKb  <br/> |5000  <br/> |Ver nota al final de la tabla\*  <br/> |
|FileTransferBitRateKb  <br/> |5000  <br/> |N/D  <br/> |
|TotalReceiveVideoBitRateKb  <br/> |20000  <br/> |Se recomienda establecer esto lo más alto posible. El ancho de banda efectivo depende de las condiciones de red en el momento de las conferencias.\*  <br/> |
|EnableMultiViewJoin  <br/> |TRUE  <br/> |Debe ser TRUE para Skype room system para garantizar secuencias de vídeo de varias vistas  <br/> |
   
* Para obtener información sobre la planeación del ancho de banda, vea [Requisitos de ancho de banda de red para el tráfico multimedia.](../../plan-your-deployment/network-requirements/network-requirements.md#network-bandwidth-requirements-for-media-traffic)
  
> [!NOTE]
> Si el cliente del sistema de salas de Skype intenta unirse a una reunión programada organizada por un usuario que se encuentra en un grupo de servidores de Lync Server 2010, la directiva de conferencia del organizador de la reunión podría impedir que el cliente del sistema de salas de Skype realice la colaboración. 
  
## <a name="meeting-authentication"></a>Autenticación de reuniones

Skype El sistema de salas pide autenticación a los usuarios cuando usan el vínculo de unión a la reunión para unirse a una reunión restringida; por ejemplo, una reunión para la que se han configurado las opciones de la sala de reuniones en Outlook. Esta configuración siempre está en las reuniones personalizadas y siempre se pide a los usuarios. Sin embargo, para reuniones sin restricciones, los usuarios pueden unirse a la reunión sin autenticación. 
  
El siguiente comando permite a los administradores requerir autenticación para todas las reuniones, incluidas las reuniones sin restricciones: 
  
```powershell
Set-CsMeetingConfiguration -RequireRoomSystemsAuthorization $TRUE
```

De forma predeterminada, RequireRoomSystemsAuthorization es FALSE. 
  

