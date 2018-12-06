---
title: Quitar una cuenta de usuario de Lync Server
TOCTitle: Quitar una cuenta de usuario de Lync Server
ms:assetid: 2f512aba-e358-45ae-af58-74312ee9c514
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688008(v=OCS.15)
ms:contentKeyID: 49889023
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Quitar una cuenta de usuario de Lync Server

 

_**Última modificación del tema:** 2013-02-22_

Puede utilizar el siguiente procedimiento para eliminar una cuenta de usuario agregada anteriormente en Lync Server 2013.


> [!NOTE]
> Eliminar un usuario provocará que pierda los parámetros que haya configurado para la cuenta de usuario. Si en cambio quisiera deshabilitar temporalmente una cuenta de usuario, consulte el tema <A href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Deshabilitación o rehabilitación de la cuenta de usuario de Lync Server en Lync Server 2013</A>.



## Para quitar una cuenta de usuario de Lync Server Lync Server

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Usuarios**.

4.  En el cuadro **Buscar usuarios**, escriba la primera parte del nombre para mostrar el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de línea de la cuenta de usuario que desee deshabilitar o volver a habilitar y, a continuación, haga clic en **Buscar**.

5.  En la tabla, haga clic en la cuenta de usuario que desee quitar.

6.  En el menú **Acción**, seleccione **Quitar de Lync Server** y, a continuación, aparecerá un cuadro de diálogo.

7.  En el cuadro de diálogo, seleccione **Aceptar** para quitar el usuario.

## Quitar una cuenta de usuario utilizando los cmdlets de Lync Server PowerShell

También puede quitar cuentas de usuario utilizando el cmdlet Disable-CsUser. Este cmdlet puede ejecutarse ya sea desde el Shell de administración de Lync Server 2013 o bien desde una sesión remota Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Quitar una cuenta de usuario

  - Para quitar una cuenta de usuario, utilice el cmdlet Disable-CsUser. Por ejemplo:
    
        Disable-CsUser -Identity "Ken Myer"
    
    Una vez que se haya ejecutado este comando, no hay manera de volver a habilitar la cuenta y las configuraciones previas. En su lugar, necesitará utilizar el cmdlet Enable-CsUser para crear una cuenta nueva para Ken Myer.

Para obtener más información, consulte el tema de ayuda del cmdlet [Disable-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Disable-CsUser).

## Vea también

#### Tareas

[Deshabilitación o rehabilitación de la cuenta de usuario de Lync Server en Lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  

#### Otros recursos

[Habilitar y deshabilitar usuarios para Lync Server 2013](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)

