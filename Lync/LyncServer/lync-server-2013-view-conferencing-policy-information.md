---
title: Visualización de información de directivas de conferencia
TOCTitle: Visualización de información de directivas de conferencia
ms:assetid: e99fdc4d-926a-4e36-ac99-ab5035568847
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ721918(v=OCS.15)
ms:contentKeyID: 49889791
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Visualización de información de directivas de conferencia

 

_**Última modificación del tema:** 2013-02-23_

En Panel de control de Lync Server 2013, las directivas de conferencia se usan para controlar cómo se implementa la conferencia en la implementación. Esto incluye las directivas de conferencia siguientes:

  - Una directiva global que se crea siempre cuando se implementa Lync Server 2013.

  - Una directiva de nivel de sitio y de nivel de usuario que se crea y usa para especificar cómo se implementan las reuniones en sitios o usuarios específicos.

## Para ver la configuración de la directiva de conferencia

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Conferencia** y después en **Directiva de Conferencia**.

4.  En la página **Directiva de conferencia**, haga doble clic en la directiva de conferencia que desee ver.

5.  En **Editar filtro de archivo**, active la casilla **Mostrar detalles…**.
    
    **Editar directiva de conferencia - \<directiva\>** se abre y muestra la configuración de la directiva seleccionada. Para más información sobre la configuración, vea [Creación o modificación de una directiva de conferencia en Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).

## Visualizar directivas de conferencia con los cmdlets de Lync Server PowerShell

Las directivas de conferencia también se pueden ver con Lync Server PowerShell y el cmdlet Get-CsConferencingPolicy. Este cmdlet se puede ejecutar desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Ver directivas de conferencia

  - Para ver información sobre todas las directivas de conferencia, escriba el comando siguiente en el Shell de administración de Lync Server y presione ENTRAR:
    
        Get-CsConferencingPolicy
    
    Devolverá información similar a la siguiente:
    
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

Para más información, vea el tema de la ayuda del cmdlet [Get-CsConferencingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsConferencingPolicy).

