---
title: Ver información de directivas PIN
TOCTitle: Ver información de directivas PIN
ms:assetid: 1d48b060-d77f-44ee-b70f-3ce128aedac4
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ687985(v=OCS.15)
ms:contentKeyID: 49888911
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ver información de directivas PIN

 

_**Última modificación del tema:** 2013-02-23_

Puede usar la pestaña **Directiva de PIN** para ver la autenticación mediante un número de identificación personal (PIN) de los usuarios que se conectan a Lync 2013 con teléfonos IP. Para usar la autenticación de PIN, asegúrese de que esté marcado **Habilitar autenticación PIN** en la configuración del servicio web. Para obtener más información, consulte [Modificación de la configuración de un servicio web existente](lync-server-2013-modify-existing-web-service-configuration-settings.md).

Siga estos pasos para modificar una directiva de PIN de nivel de usuario o de sitio.

## Para ver información sobre una directiva de PIN de Panel de control de Lync Server

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o se asigne al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que esté en la red en la que haya implementado Lync Server 2013.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Seguridad** y, a continuación, en **Directiva de PIN**.

4.  En la página **Directiva de PIN**, haga clic en **Editar** y, a continuación, haga clic en **Mostrar detalles**.

## Ver directivas de PIN utilizando los cmdlets de Lync Server PowerShell

También puede ver directivas de PIN utilizando Windows PowerShell y el cmdlet Get-CsPinPolicy. Este cmdlet puede ejecutarse ya sea desde el Shell de administración de Lync Server 2013 o bien desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Ver directivas de PIN

  - Para ver información sobre todas sus directivas de PIN, escriba el siguiente comando en el Shell de administración de Lync Server y, a continuación, presione ENTRAR:
    
        Get-CsPinPolicy
    
    Eso devolverá información similar a esto:
    
        Identity             : Global
        Description          :
        MinPasswordLength    : 5
        PINHistoryCount      : 0
        AllowCommonPatterns  : False
        PINLifetime          : 0
        MaximumLogonAttempts :

Para obtener más información, consulte el tema de ayuda del cmdlet [Get-CsPinPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsPinPolicy).

## Vea también

#### Tareas

[Modificación de la configuración de un servicio web existente](lync-server-2013-modify-existing-web-service-configuration-settings.md)  
[Crear una directiva de PIN nueva](lync-server-2013-create-a-new-pin-policy.md)

