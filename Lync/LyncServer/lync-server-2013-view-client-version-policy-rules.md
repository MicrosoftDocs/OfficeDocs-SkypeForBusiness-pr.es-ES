---
title: Ver las reglas de directiva de versión de cliente
TOCTitle: Ver las reglas de directiva de versión de cliente
ms:assetid: f3a0215f-f72f-4e9b-a07b-25858dc4203a
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ923060(v=OCS.15)
ms:contentKeyID: 52061968
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ver las reglas de directiva de versión de cliente

 

_**Última modificación del tema:** 2013-02-23_

Una directiva de versión de cliente está compuesta de un conjunto de reglas de directiva de versión de cliente. Estas reglas definen las acciones que se deben realizar cuando los usuarios intentan iniciar sesión con clientes y versiones de clientes específicos. Las reglas de directiva de versión de cliente se pueden consultar en el Panel de control de Lync Server 2013 o en el Shell de administración de Lync Server 2013.

## Para ver las reglas de directiva de versión de cliente mediante el Panel de control de Lync Server

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Clientes** y, a continuación, en el botón de navegación **Directiva de versión de cliente**.

4.  En la página **Directiva de versión de cliente**, haga doble clic en la directiva de versión de cliente que quiera ver.

5.  Las reglas aparecen recogidas en la página **Editar directiva de versión de cliente**. Para ver los detalles de una regla, selecciónela y haga clic en **Mostrar detalles**.

## Ver las reglas de directiva de versión de cliente mediante cmdlets de Windows PowerShell

Las reglas de directiva de versión de cliente se pueden ver con Shell de administración de Lync Server y el cmdlet **Get-CsClientVersionPolicyRule**. Este cmdlet se puede ejecutar desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Para ver las reglas de directiva de versión de cliente

  - Para ver las reglas de directiva de versión de cliente, escriba el comando siguiente en el Shell de administración de Lync Server y presione ENTRAR:
    
        Get-CsClientVersionPolicyRule
    
    Obtendrá información parecida a la siguiente relativa a cada regla configurada:
    
        Identity          : Global/2336c611-a243-4c5d-994b-eea8a524d0e4
        Priority          : 0
        RuleId            : 2336c611-a243-4c5d-994b-eea8a524d0e4
        Description       :
        Action            : Block
        ActionUrl         :
        MajorVersion      : 1
        MinorVersion      : 3
        BuildNumber       :
        QfeNumber         :
        UserAgent         : RTC
        UserAgentFullName :
        Enabled           : True
        CompareOp         : LEQ

Para información, vea el tema de ayuda del cmdlet [Get-CsClientVersionPolicyRule](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsClientVersionPolicyRule).

