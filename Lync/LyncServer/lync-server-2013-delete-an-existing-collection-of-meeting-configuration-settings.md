---
title: "Suppr. d’une collection existante de paramètres de configuration de réunion"
TOCTitle: "Suppr. d’une collection existante de paramètres de configuration de réunion"
ms:assetid: 92ff8a91-05c5-4047-a533-5dff12f22299
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688136(v=OCS.15)
ms:contentKeyID: 49889385
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Eliminación de un conjunto existente de opciones de configuración de reunión

 

_**Última modificación del tema:** 2013-02-23_

Es posible eliminar una configuración de sitio o de usuario. La configuración global no se puede quitar. Si elimina la configuración global, esta se restablece automáticamente a sus valores predeterminados.

## Para eliminar la configuración de reunión de un sitio o usuario

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Conferencia** y, a continuación, en **Configuración de reuniones** .

4.  En la lista de configuraciones de reunión, haga clic en la configuración de sitio o de grupo que desea eliminar, haga clic en Editar y, a continuación, en Eliminar.

## Eliminación de las opciones de configuración de reunión mediante los cmdlets de Lync Server PowerShell

Las opciones de configuración de reunión también se pueden eliminar mediante Windows PowerShell y el cmdlet Remove-CsMeetingConfiguration. Este cmdlet se puede ejecutar desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Eliminación de una colección especificada de opciones de configuración de reunión

  - Este comando quita las opciones de configuración de reunión que se aplican al sitio Redmond:
    
        Remove-CsMeetingConfiguration -Identity "site:Redmond"

## Eliminación de todas las opciones de configuración que se aplican al ámbito del sitio

  - Este comando quita todas las opciones de configuración de reunión que se aplican al ámbito del sitio:
    
        Get-CsMeetingConfiguration -Filter "site:*" | Remove-CsMeetingConfiguration

## Eliminación de todas las opciones de configuración de reunión que admiten usuarios anónimos de forma predeterminada

  - Y esta quita todas las opciones de configuración que permiten la admisión de usuarios anónimos de forma predeterminada:
    
        Get-CsMeetingConfiguration | Where-Object {$_.AdmitAnonymousUsersByDefault -eq $True} | Remove-CsMeetingConfiguration

Para obtener más información, consulte el tema sobre el cmdlet [Remove-CsMeetingConfiguration](ttps://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsMeetingConfiguration).

