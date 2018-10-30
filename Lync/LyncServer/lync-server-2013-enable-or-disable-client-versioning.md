---
title: Habilitar o deshabilitar el control de versiones de cliente
TOCTitle: Habilitar o deshabilitar el control de versiones de cliente
ms:assetid: 33a98cb9-a979-4bb6-afb2-512f601d7ac5
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ898475(v=OCS.15)
ms:contentKeyID: 52061627
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Habilitar o deshabilitar el control de versiones de cliente

 

_**Última modificación del tema:** 2013-02-23_

Los valores de configuración de versión de cliente se usan para activar o desactivar el control de versiones de cliente, ya sea de forma global o para sitios en particular. La configuración de versión de cliente global se instala con Lync Server 2013 y se usa para habilitar o deshabilitar el control de versiones de cliente para toda la implementación del servidor. Si habilita la configuración global, las directivas de versión de cliente que tenga activas tendrán efecto cuando los usuarios intenten iniciar sesión. Puede deshabilitar la configuración de versión de cliente global si no desea que se produzca ningún control de versiones de cliente. Puede habilitar o deshabilitar el control de versiones de cliente desde Panel de control de Lync Server 2013 o Shell de administración de Lync Server 2013.


> [!NOTE]
> Debido a que los usuarios anónimos no están asociados a un usuario, sitio o servicio, estos usuarios solo se ven afectados por las directivas de nivel global.



## Para habilitar o deshabilitar el control de versiones de cliente mediante Panel de control de Lync Server

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Clientes** y, a continuación, en el botón de navegación **Configuración de versión de cliente**.

4.  Siga este procedimiento:
    
      - Para habilitar o deshabilitar el control de versiones de cliente de forma global, haga doble clic en la configuración **Global** y, a continuación, modifique los valores.
    
      - Para habilitar o deshabilitar el control de versiones de cliente para un sitio en particular, haga clic en **Nuevo**, seleccione el sitio, haga clic en **Aceptar** y, a continuación, modifique los valores para el sitio.

## Habilitar o deshabilitar el control de versiones de cliente mediante cmdlets de Windows PowerShell

Puede habilitar o deshabilitar el control de versiones de cliente mediante el cmdlet **Set-CsClientVersionConfiguration**. Este cmdlet se puede ejecutar desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Para habilitar el control de versiones de cliente

  - Puede habilitar el control de versiones de cliente estableciendo la propiedad **Enabled** en True ($True).
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

## Para deshabilitar el control de versiones de cliente

  - Puede deshabilitar el control de versiones de cliente estableciendo la propiedad **Enabled** en False ($False).
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

Para obtener información detallada, consulte el tema de Ayuda acerca del cmdlet [Set-CsClientVersionConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClientVersionConfiguration).

