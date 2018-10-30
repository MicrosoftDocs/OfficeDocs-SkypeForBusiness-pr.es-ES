---
title: Asignación de una directiva de voz por usuario
TOCTitle: Asignación de una directiva de voz por usuario
ms:assetid: 9ee47ee7-1030-43b8-a4dc-bf685ea24659
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688155(v=OCS.15)
ms:contentKeyID: 49889505
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Asignación de una directiva de voz por usuario

 

_**Última modificación del tema:** 2013-02-22_

A todas las cuentas de usuario de Lync Server 2013 habilitadas para Telefonía IP empresarial se les asignan automáticamente directivas de voz a nivel global o de sitio Global. También puede asignar directivas de voz a usuarios específicos si se usa el Panel de control de Lync Server 2013 o el Shell de administración de Lync Server 2013. Siga los procedimientos detallados en este tema para asignar explícitamente directivas por usuario a usuarios de Lync Server.

## Para asignar directivas de voz específicas de usuarios mediante el Panel de control de Lync Server

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Usuarios** y, a continuación, busque en la cuenta de usuario que desea configurar.

4.  En la tabla donde se enumeran los resultados de la búsqueda, haga clic en la cuenta de usuario, en **Editar** y, a continuación, en **Mostrar detalles**.

5.  En **Editar usuario de Lync Server** en **Directiva de voz**, seleccione la directiva de usuario que desea aplicar.
    

    > [!NOTE]
    > En configuración <STRONG>&lt;Automática&gt;</STRONG>, aplique la configuración del servidor o de la directiva global predeterminada.



## Para asignar directivas de voz específicas de usuarios mediante el Shell de administración de Lync Server

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

3.  Para asignar una directiva de voz de usuario existente a un usuario, ejecute lo siguiente en el símbolo del sistema:
    
        Grant-CsVoicePolicy -Identity <UserIdParameter> -PolicyName <String>
    
    Por ejemplo:
    
        Grant-CsVoicePolicy -Identity "Bob Kelly" -PolicyName VoicePolicyJapan
    
    En este ejemplo, al usuario con el nombre para mostrar Carlos Tudela se le asigna la directiva de voz de nombre **VoicePolicyJapan**.

Para ver los detalles acerca de cómo asignar una directiva de voz específica del usuario o ejecutar el cmdlet **Grant-CsVoicePolicy**, consulte la documentación de [Shell de administración de Lync Server](lync-server-2013-lync-server-management-shell.md).

## Asignar una directiva de voz por usuario mediante cmdlets de Windows PowerShell

Las directivas de voz por usuario también pueden asignarse mediante el uso de Windows PowerShell y el cmdlet **Grant-CsVoicePolicy**. Este cmdlet puede ejecutarse bien desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Asignar una directiva de voz por usuario a un solo usuario

  - El siguiente comando permite asignar la directiva de voz por usuario RedmondVoicePolicy al usuario Ken Myer.
    
        Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

## Asignar una directiva de voz por usuario a varios usuarios

  - Este comando asigna la directiva de voz por usuario FinanceVoicePolicy a todos los usuarios que tengan cuentas en el OU Finance de Active Directory. Para más información sobre el parámetro OU que se usa en este comando, consulte la documentación del cmdlet [Get-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser).
    
        Get-CsUser -OU "ou=Finance,ou=North America,dc=litwareinc,dc=com" | Grant-CsVoicePolicy -PolicyName "FinanceVoicePolicy"

## Desasignar una directiva de voz por usuario

  - Este comando desasigna cualquier directiva de voz por usuario previamente asignada a Ken Myer. Una vez desasignada la directiva por usuario, Ken Myer pasará automáticamente a ser administrado mediante la directiva global (o, de existir, por la directiva de su sitio local). Las directivas de sitio tienen prioridad sobre la directiva global.
    
        Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName $Null

Para obtener más información, consulte el tema de ayuda correspondiente al cmdlet [Grant-CsVoicePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsVoicePolicy).

## Vea también

#### Tareas

[Deshabilitar a un usuario para Enterprise Voice en Lync Server 2013](lync-server-2013-disable-a-user-for-enterprise-voice.md)  

#### Otros recursos

[Shell de administración de Lync Server](lync-server-2013-lync-server-management-shell.md)

