---
title: Ver las opciones de configuración de versión de cliente
TOCTitle: Ver las opciones de configuración de versión de cliente
ms:assetid: c72df4e6-a889-4cb6-86f7-8334d7774c6e
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ923062(v=OCS.15)
ms:contentKeyID: 52061742
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ver las opciones de configuración de versión de cliente

 

_**Última modificación del tema:** 2013-02-23_

Los ajustes de configuración de versión de cliente se usan para activar o desactivar el control de versión de cliente. La configuración de versión de cliente global se instala con Lync Server 2013y sirve para habilitar o deshabilitar el control de versión de cliente en toda la implementación del servidor. Si la configuración global está habilitada, las directivas de versión de cliente que tenga activas tendrán efecto cuando los usuarios intenten iniciar sesión. La configuración de versión de cliente se puede consultar en el Panel de control de Lync Server 2013 o en el Shell de administración de Lync Server 2013.


> [!NOTE]
> Debido a que los usuarios anónimos no están asociados a un usuario, sitio o servicio, este tipo de usuarios solo se ve afectado por directivas de nivel global.



## Para ver la configuración de versión de cliente mediante el Panel de control de Lync Server

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Clientes** y, a continuación, en el botón de navegación **Configuración de versión de cliente**.

4.  Haga doble clic en el nombre de la configuración de versión de cliente que quiera ver.

## Ver la configuración de versión de cliente mediante cmdlets de Windows PowerShell

Se puede usar el cmdlet **Get-CsClientVersionConfiguration** para ver las configuraciones de versión de cliente. Este cmdlet se puede ejecutar desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Para ver la información de configuración de versión de cliente

  - Para ver información sobre todas las configuraciones de versión de cliente, escriba el siguiente comando en el Shell de administración de Lync Server y, a continuación, presione ENTRAR:
    
        Get-CsClientVersionConfiguration
    
    Obtendrá información parecida a la siguiente:
    
        Identity      : Global
        DefaultAction : Allow
        DefaultURL    :
        Enabled       : True

Para más información detallada, vea el tema de ayuda relativo al cmdlet [Get-CsClientVersionConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsClientVersionConfiguration).

