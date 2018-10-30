---
title: "Crear o modificar una colección de opciones de configuración de versión de cliente"
TOCTitle: "Créer ou mod. une collection de par. de conf. de la version du client"
ms:assetid: 4e6faffd-a36f-40f1-8734-78d84b7df921
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ898477(v=OCS.15)
ms:contentKeyID: 52061636
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Crear o modificar una colección de opciones de configuración de versión de cliente

 

_**Última modificación del tema:** 2013-02-23_

Los valores de configuración de versión de cliente se usan para activar o desactivar el control de versiones de cliente. La configuración de versión de cliente global se instala con Lync Server y se usa para habilitar o deshabilitar el control de versiones de cliente para toda la implementación del servidor. También puede establecer valores de configuración de versión de cliente para sitios individuales. Puede crear o modificar valores de configuración de versión de cliente desde Panel de control de Lync Server 2013 o Shell de administración de Lync Server 2013.


> [!NOTE]
> Debido a que los usuarios anónimos no están asociados a un usuario, sitio o servicio, estos usuarios solo se ven afectados por las directivas de nivel global.



## Para crear o modificar valores de configuración de versión de cliente mediante Panel de control de Lync Server

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Clientes** y, a continuación, en el botón de navegación **Configuración de versión de cliente**.

4.  En la página **Configuración de versión de cliente**, siga este procedimiento:
    
      - Para crear una nueva configuración, haga clic en **Nueva**, seleccione un sitio, haga clic en **Aceptar**, asígnele un nombre y actualice la configuración.
    
      - Para modificar una configuración, selecciónela, haga clic en **Editar**, haga clic en **Mostrar detalles** y realice los cambios que desee.

## Creación o modificación de valores de configuración de versión de cliente mediante cmdlets de Windows PowerShell

Puede crear valores de configuración de versión de cliente mediante el cmdlet **New-CsClientVersionConfiguration** y modificarlos mediante el cmdlet **Set-CsClientVersionConfiguration**. Estos cmdlets se pueden ejecutar desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Para crear una nueva colección de valores de configuración de versión de cliente

  - El siguiente comando crea una nueva colección de valores de configuración de versión de cliente aplicada al sitio Redmond. En este ejemplo, el control de versiones de cliente está deshabilitado para el sitio Redmond.
    
        New-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $False

## Para habilitar el control de versiones de cliente para un sitio

  - Este comando habilita el control de versiones de cliente para el sitio Redmond.
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

## Para deshabilitar el control de versiones de cliente en toda la organización

  - En este ejemplo, el control de versiones de cliente está deshabilitado para todos los valores de configuración de versión de cliente que se usan en la organización.
    
        Get-CsClientVersionConfiguration | Set-CsClientVersionConfiguration  -Enabled $False

Para obtener información detallada, consulte el tema de Ayuda acerca de los cmdlets [New-CsClientVersionConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsClientVersionConfiguration) y [Set-CsClientVersionConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClientVersionConfiguration).

