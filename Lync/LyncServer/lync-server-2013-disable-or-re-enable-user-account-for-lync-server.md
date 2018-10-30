---
title: 'Deshabilitar o rehabilitar cuenta de usuario de Lync Server en Lync Server 2013'
TOCTitle: Deshabilitación o rehabilitación de la cuenta de usuario de Lync Server en Lync Server 2013
ms:assetid: 12497d00-f665-4a97-be68-854c5a8be4fc
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg429696(v=OCS.15)
ms:contentKeyID: 48274483
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Deshabilitación o rehabilitación de la cuenta de usuario de Lync Server en Lync Server 2013

 

_**Última modificación del tema:** 2016-04-04_

Puede usar los procedimientos que se describen a continuación para deshabilitar una cuenta de usuario previamente habilitada en Lync Server 2013 sin perder la configuración de Lync Server establecida para la cuenta de usuario. Como no pierde la configuración de la cuenta de usuario de Lync Server, puede volver a habilitar una cuenta de usuario habilitada anteriormente sin tener que volver a configurarla.

## Para deshabilitar o volver a habilitar una cuenta de usuario habilitada anteriormente para Lync Server

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Usuarios**.

4.  En el cuadro **Buscar usuarios**, escriba la primera parte del nombre para mostrar el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de línea de la cuenta de usuario que desee deshabilitar o volver a habilitar y luego haga clic en **Buscar**.

5.  En la tabla, haga clic en la cuenta de usuario que desee deshabilitar o volver a habilitar.

6.  En el menú **Acción**, lleve a cabo alguna de las operaciones siguientes:
    
      - Para deshabilitar temporalmente la cuenta de usuario para Lync Server 2013, haga clic en **Deshabilitar temporalmente para Lync Server**.
    
      - Para habilitar la cuenta de usuario para Lync Server 2013, haga clic en **Volver a habilitar para Lync Server**.

## Deshabilitación y habilitación de una cuenta de usuario con los cmdlets de Windows PowerShell

Es posible deshabilitar las cuentas de usuario de forma temporal para volver a habilitarlas más adelante con el cmdlet **Set-CsUser**. Dicho cmdlet puede ejecutarse desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Deshabilitación de una cuenta de usuario

  - Para deshabilitar temporalmente una cuenta de usuario, establezca el valor de la propiedad Enabled en False ($False). Por ejemplo:
    
        Set-CsUser -Identity "Ken Myer" -Enabled $False

## Habilitación de una cuenta de usuario

  - Para volver a habilitar una cuenta de usuario deshabilitada, establezca el valor de la propiedad Enabled en True ($True). Por ejemplo:
    
        Set-CsUser -Identity "Ken Myer" -Enabled $True

Para más información, vea el tema de ayuda del cmdlet [Set-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsUser).

## Vea también

#### Tareas

[Adición y habilitación de una cuenta de usuario de Lync Server](lync-server-2013-add-and-enable-user-account-for-lync-server.md)  

#### Otros recursos

[Habilitar y deshabilitar usuarios para Lync Server 2013](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)

