---
title: Ver directivas de conferencia en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c1c0976e-2bfb-475b-9255-ed6b093d8798
description: 'Resumen: obtenga información sobre cómo ver directivas de conferencia en Skype Empresarial Server.'
ms.openlocfilehash: 39b37a1335f8b257f9dec1fff28bea90ac7a6db9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817510"
---
# <a name="view-conferencing-policies-in-skype-for-business-server"></a>Ver directivas de conferencia en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre cómo ver directivas de conferencia en Skype Empresarial Server.
  
Puede ver las directivas de conferencia con el Panel de control de Skype Empresarial Server o con el Shell de administración de Skype Empresarial Server.
  
## <a name="view-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Ver directivas de conferencia con el Panel de control de Skype Empresarial Server

1. Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.
    
2.  Abra el Panel de control de Skype Empresarial Server.
    
3. En la barra de navegación izquierda, haga clic **en Conferencia** y, a continuación, haga clic en Directiva **de conferencia.**
    
4. En la página **Directiva de conferencia**, haga doble clic en la directiva de conferencia que desee ver.
    
5. En **Editar filtro de archivos,** active la casilla **Mostrar** detalles.
    
    **Editar directiva de \<policy\> conferencia:** se abre mostrando la configuración de la directiva seleccionada.
    
    Para obtener más información sobre cómo configurar las opciones, consulte Crear directivas de conferencia [en Skype Empresarial Server.](create-policies.md)
    
## <a name="view-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Ver directivas de conferencia mediante el Shell de administración de Skype Empresarial Server

Para ver directivas de conferencia, use el cmdlet **Get-CsConferencingPolicy:**
  
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

Para obtener más información, incluida una descripción de sintaxis completa y una lista de parámetros, vea [Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps).
  

