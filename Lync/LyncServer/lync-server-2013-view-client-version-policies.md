---
title: Ver las directivas de versión de cliente
TOCTitle: Ver las directivas de versión de cliente
ms:assetid: 6cd9a897-c694-4d6a-8259-2d3c01fce275
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ898479(v=OCS.15)
ms:contentKeyID: 52061653
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ver las directivas de versión de cliente

 

_**Última modificación del tema:** 2013-02-23_

Las directivas de versión de cliente se usan para aplicar un conjunto de reglas de control de versiones de cliente de forma global o en un sitio, grupo o conjunto de usuarios en particular. Puede ver las directivas de versión de cliente que se han configurado en su entorno de Lync Server 2013 desde Panel de control de Lync Server 2013 o Shell de administración de Lync Server 2013.

## Para ver las directivas de versión de cliente mediante Panel de control de Lync Server

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Clientes** y, a continuación, en el botón de navegación **Directiva de versión de cliente**.

4.  Si desea ver las reglas de una directiva de versión de cliente, en la página **Directiva de versión de cliente**, haga doble clic en la directiva que desea ver.

## Visualización de directivas de versión de cliente mediante cmdlets de Windows PowerShell

Puede ver las directivas de versión de cliente mediante el cmdlet **Get-CsClientVersionPolicy**. Este cmdlet se puede ejecutar desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Para ver las directivas de versión de cliente

  - Para ver información sobre todas las directivas de versión de cliente, escriba el comando siguiente en el Shell de administración de Lync Server y presione ENTRAR:
    
        Get-CsClientVersionPolicy
    
    Se devolverá información similar a la siguiente:
    
        Identity    : Global
        Rules       : {RuleId=2336c611-a243-4c5d-994b-eea8a524d0e4;
                      Description=;Action=Block;ActionUrl=;MajorVersion=1;
                      MinorVersion=3;BuildNumber=;QfeNumber=;
                      UserAgent=RTC;UserAgentFullName=;Enabled=True;
                      CompareOp=LEQ, RuleId=342c9b90-4cef-483a-a73a-
                      4fe75c88711d;Description=;Action=Block;ActionUrl=;
                      MajorVersion=5;MinorVersion=;BuildNumber=;QfeNumber=;
                      UserAgent=WM;UserAgentFullName=;Enabled=True;
                      CompareOp=LEQ,RuleId=ea03af61-9db5-4bf9-af3f-042
                      ab8dd9994;Description=;Action=Block;ActionUrl=;
                      MajorVersion=3;MinorVersion=5;BuildNumber=6907;
                      QfeNumber=83;UserAgent=OC;UserAgentFullName=;
                      Enabled=True;CompareOp=LEQ, RuleId=831edb68-
                      e482-4431-a10e-add365ba8099;Description=;
                      Action=Block;ActionUrl=;MajorVersion=2;MinorVersion=0;
                      BuildNumber=5999;QfeNumber=;UserAgent=UCCP;
                      UserAgentFullName=;Enabled=True;CompareOp=LEQ...}
        Description :

Para obtener información detallada, consulte el tema de Ayuda acerca del cmdlet [Get-CsClientVersionPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsClientVersionPolicy).

