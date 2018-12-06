---
title: Eliminación de una directiva de conferencias existente
TOCTitle: Eliminación de una directiva de conferencias existente
ms:assetid: 709ed771-790f-4bf1-a4de-b37ca5168688
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688089(v=OCS.15)
ms:contentKeyID: 49889225
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Eliminación de una directiva de conferencias existente

 

_**Última modificación del tema:** 2013-02-23_

Siga estos pasos para eliminar una directiva de conferencia de nivel de usuario o de nivel de sitio.


> [!NOTE]
> No puede eliminar la directiva de conferencia global.



## Para eliminar una directiva de conferencia de usuario o sitio

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Conferencia** y, a continuación, en **Directiva de conferencia**.

4.  En la lista de directivas de conferencia, haga clic en la directiva de usuario o sitio que desea eliminar, haga clic en Editar y, después, en Eliminar .

## Eliminación de directivas de conferencia utilizando cmdlets del Shell de administración de Lync Server

También puede eliminar las opciones de configuración de tronco con Shell de administración de Lync Server y el cmdlet **Remove-CsConferencingPolicy**. Puede ejecutar el cmdlet desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Para quitar una directiva de conferencia determinada

  - El comando siguiente quita la directiva de conferencia con el valor de identidad RedmondConferencingPolicy:
    
        Remove-CsConferencingPolicy -Identity "RedmondConferencingPolicy"

## Para quitar todas las directivas de conferencia aplicadas en el ámbito por usuario

  - El comando siguiente quita todas las directivas de conferencia configuradas en el ámbito por usuario:
    
        Get-CsConferencingPolicy -Filter "tag:*" | Remove-CsConferencingPolicy

## Para quitar todas las directivas de conferencia que permiten la grabación por parte de usuarios externos

  - El comando siguiente quita todas las directivas de conferencia que permiten que usuarios externos graben la conferencia:
    
        Get-CsConferencingPolicy | Where-Object {$_.AllowExternalUsersToRecordMeetings -eq $True} | Remove-CsConferencingPolicy

Para más información, consulte [Remove-CsConferencingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsConferencingPolicy).

