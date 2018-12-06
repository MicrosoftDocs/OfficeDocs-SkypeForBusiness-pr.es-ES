---
title: Visualización de las opciones de configuración de reuniones
TOCTitle: Visualización de las opciones de configuración de reuniones
ms:assetid: d03a4684-9d8b-4728-917d-5b5c91511e2c
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ721894(v=OCS.15)
ms:contentKeyID: 49889744
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Visualización de las opciones de configuración de reuniones

 

_**Última modificación del tema:** 2013-02-23_

En Panel de control de Lync Server 2013, las configuraciones de reuniones se usan para controlar el modo en que se implementan las reuniones en la implementación efectuada. Esto incluye las configuraciones de reuniones siguientes:

  - La configuración global que se crea normalmente al implementar Lync Server 2013.

  - Configuraciones de nivel de sitio y de nivel de usuario que se crean y usan para especificar cómo se implementan las reuniones en sitios o usuarios específicos.

## Para ver la configuración de reuniones

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Conferencia** y después en **Configuración de reunión**.

4.  En la página **Configuración de reunión**, haga clic en la configuración de reunión que desee ver.

5.  En **Modificar filtro de archivo**, active la casilla **Mostrar detalles…**.
    
    **Editar configuración de reunión - \<directiva\>** se abre para mostrar la configuración de la directiva seleccionada. Para más información sobre la configuración, consulte [Creación o modificación de un conjunto de opciones de configuración de reuniones en Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md).

## Ver información de configuración de reuniones con los cmdlets de Lync Server PowerShell

La configuración de las reuniones también se puede ver con Lync Server PowerShell y el cmdlet Get-CsMeetingConfiguration. Este cmdlet se puede ejecutar desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Ver información de configuración de reuniones

  - Para ver información sobre todas las configuraciones de reuniones, escriba el comando siguiente en el Shell de administración de Lync Server y presione ENTRAR:
    
        Get-CsMeetingConfiguration
    
    Devolverá información similar a la siguiente:
    
        Identity                        : Global
        PstnCallersBypassLobby          : True
        EnableAssignedConferenceType    : True
        DesignateAsPresenter            : Company
        AssignedConferenceTypeByDefault : True
        AdmitAnonymousUsersByDefault    : True
        RequireRoomSystemsAuthorization : False
        LogoURL                         :
        LegalURL                        :
        HelpURL                         :
        CustomFooterText                :
        AllowConferenceRecording        : True

Para más información, vea el tema de ayuda del cmdlet [Get-CsMeetingConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsMeetingConfiguration).

