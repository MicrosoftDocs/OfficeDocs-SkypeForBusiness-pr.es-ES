---
title: Ver directivas de conferencia en Skype Empresarial Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1c0976e-2bfb-475b-9255-ed6b093d8798
description: 'Resumen: Conozca cómo ver las directivas de la conferencia en Skype para Business Server 2015.'
ms.openlocfilehash: 4d91a04456f7c9d877e58caed1d576edc0f80b41
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="view-conferencing-policies-in-skype-for-business-server-2015"></a>Ver directivas de conferencia en Skype Empresarial Server 2015
 
**Resumen:** Aprenda a ver las directivas de la conferencia de Skype para Business Server 2015.
  
Puede ver las directivas de la conferencia utilizando Skype para Panel de Control de servidor empresarial o mediante Skype para el Shell de administración de servidor empresarial.
  
## <a name="view-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Ver directivas de conferencia utilizando Skype para Panel de Control de servidor empresarial

1. Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2.  Abre Skype para Panel de Control del servidor de empresa.
    
3. En la barra de navegación izquierda, haga clic en **Conferencia** y después en **Directiva de conferencia**.
    
4. En la página **Directiva de conferencia**, haga doble clic en la directiva de conferencia que desee ver.
    
5. En **Editar filtro de archivo**, active la casilla **Mostrar detalles**.
    
    **Editar directiva de conferencia - \<directiva\> ** se abre mostrando la configuración para la directiva seleccionada.
    
    Para obtener más información acerca de cómo configurar las opciones, consulte [crear directivas de conferencia en Skype para Business Server 2015](create-policies.md).
    
## <a name="view-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Ver directivas de conferencia utilizando Skype para el Shell de administración de servidor empresarial

Para ver las directivas de conferencia, use el cmdlet **Get-CsConferencingPolicy**:
  
```
Get-CsConferencingPolicy
```

El cmdlet devuelve información como la siguiente:
  
```
Identity                                  : Global
AllowIPAudio                              : True
AllowIPVideo                              : True
AllowMultiView                            : True
Description                               :
AllowParticipantControl                   : True
AllowAnnotations                          : True
DisablePowerPointAnnotations              : False
AllowUserToScheduleMeetingsWithAppSharing : True
AllowNonEnterpriseVoiceUsersToDialOut     : False
AllowAnonymousUsersToDialOut              : False
AllowAnonymousParticipantsInMeetings      : True
AllowExternalUsersToSaveContent           : True
AllowExternalUserControl                  : False
AllowExternalUsersToRecordMeeting         : False
AllowPolls                                : True
AllowSharedNotes                          : True
EnableDialInConferencing                  : True
EnableAppDesktopSharing                   : Desktop
AllowConferenceRecording                  : False
EnableP2PRecording                        : False
EnableFileTransfer                        : True
EnableP2PFileTransfer                     : True
EnableP2PVideo                            : True
AllowLargeMeetings                        : False
EnableDataCollaboration                   : True
MaxVideoConferenceResolution              : VGA
MaxMeetingSize                            : 250
AudioBitRateKb                            : 200
VideoBitRateKb                            : 50000
AppSharingBitRateKb                       : 50000
FileTransferBitRateKb                     : 50000
TotalReceiveVideoBitRateKb                : 6000
EnableMultiViewJoin                       : True

```

Para obtener más información, incluida una descripción de la sintaxis completa y lista de parámetros, vea [Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps).
  

