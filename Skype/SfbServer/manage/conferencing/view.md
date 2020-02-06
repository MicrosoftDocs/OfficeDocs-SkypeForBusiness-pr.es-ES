---
title: Ver directivas de conferencia en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c1c0976e-2bfb-475b-9255-ed6b093d8798
description: 'Resumen: Aprenda a ver directivas de conferencia en Skype empresarial Server.'
ms.openlocfilehash: 2273e694ce2f34c8d395f87f207de85b409e18af
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818451"
---
# <a name="view-conferencing-policies-in-skype-for-business-server"></a>Ver directivas de conferencia en Skype empresarial Server
 
**Resumen:** Obtenga información sobre cómo ver directivas de conferencia en Skype empresarial Server.
  
Puede ver las directivas de conferencia con el panel de control de Skype empresarial Server o mediante el shell de administración de Skype empresarial Server.
  
## <a name="view-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Ver directivas de conferencia con el panel de control de Skype empresarial Server

1. Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2.  Abra el panel de control de Skype empresarial Server.
    
3. En la barra de navegación izquierda, haga clic en **Conferencia** y después en **Directiva de conferencia**.
    
4. En la página **Directiva de conferencia**, haga doble clic en la directiva de conferencia que desee ver.
    
5. En **Editar filtro de archivo**, active la casilla **Mostrar detalles**.
    
    **Editar Directiva de conferencia \<:\> ** se abre la Directiva y se muestra la configuración de la Directiva seleccionada.
    
    Para obtener más información sobre cómo configurar las opciones, consulte [crear directivas de conferencia en Skype empresarial Server](create-policies.md).
    
## <a name="view-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Ver directivas de conferencia con el shell de administración de Skype empresarial Server

Para ver las directivas de conferencia, use el cmdlet **Get-CsConferencingPolicy**:
  
```PowerShell
Get-CsConferencingPolicy
```

El cmdlet devuelve información como la siguiente:
  
<pre>
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
</pre>

Para obtener más información, incluida una descripción completa de la sintaxis y una lista de parámetros, vea [Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps).
  

