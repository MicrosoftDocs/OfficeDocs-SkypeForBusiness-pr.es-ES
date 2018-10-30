---
title: Eliminar una directiva de versión de cliente existente
TOCTitle: Eliminar una directiva de versión de cliente existente
ms:assetid: b88aaa25-97ff-4eb6-bd34-b97332cd6890
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ923064(v=OCS.15)
ms:contentKeyID: 52061757
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Eliminar una directiva de versión de cliente existente

 

_**Última modificación del tema:** 2013-02-23_

Si quiere eliminar una directiva de versión de cliente configurada previamente, puede hacerlo desde el Panel de control de Lync Server 2013 o el Shell de administración de Lync Server 2013.

## Para eliminar directivas de versión de cliente mediante el Panel de control de Lync Server

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Clientes** y, a continuación, en el botón de navegación **Directiva de versión de cliente**.

4.  En la página **Directiva de versión de cliente**, seleccione la directiva o directivas de versión de cliente que quiera eliminar, haga clic en **Editar** y, después, en **Eliminar**.

## Eliminar directivas de versión de cliente mediante cmdlets de Windows PowerShell

Se puede usar el cmdlet **Remove-CsClientVersionPolicy** para eliminar directivas de versión de cliente. Este cmdlet se puede ejecutar desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Para quitar una directiva de versión de cliente específica

  - Con este comando se elimina la directiva de versión de cliente aplicada al sitio de Redmond:
    
        Remove-CsClientVersionPolicy -Identity site:Redmond

## Para quitar todas las directivas de versión de cliente que se aplican al ámbito del sitio

  - Con este comando se eliminan todas las directivas de versión de cliente configuradas en el ámbito del sitio:
    
        Get-CsClientVersionPolicy -Fiter "site:*" | Remove-CsClientVersionPolicy

## Para quitar directivas de versión de cliente que no incluyen un agente de usuario específico

  - Con este comando se elimina cualquier directiva de versión de cliente que no incluya una regla relativa al agente de usuario de Lync para Windows Phone (WPLync):
    
        Get-CsClientVersionPolicy | Where-Object {$_.Rules -notmatch "UserAgent=WPLync" | Remove-CsClientVersionPolicy

Para más información detallada, vea el tema de ayuda relativo al cmdlet [Remove-CsClientVersionPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsClientVersionPolicy).

