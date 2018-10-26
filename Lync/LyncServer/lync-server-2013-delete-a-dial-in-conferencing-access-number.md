---
title: Eliminar un número de acceso para conferencia de acceso telefónico local
TOCTitle: Eliminar un número de acceso para conferencia de acceso telefónico local
ms:assetid: 199c5d9c-0489-4ad5-a7f1-ca59fe0e6ac7
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg520956(v=OCS.15)
ms:contentKeyID: 48274574
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Eliminar un número de acceso para conferencia de acceso telefónico local

 

_**Última modificación del tema:** 2013-02-23_

Siga estos pasos para eliminar un número de acceso para conferencia de acceso telefónico local.

## Para eliminar un número de acceso para conferencia de acceso telefónico local

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o se asigne al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que esté en la red en la que haya implementado Lync Server 2013.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación de la izquierda, haga clic en **Conferencias** y, a continuación, en **Número de acceso telefónico**.

4.  En la página, haga clic en el número de acceso telefónico local que desea eliminar de la lista, haga clic en **Editar** y, a continuación, en **Eliminar**.

5.  Haga clic en **Aceptar**.

## Eliminación de números de acceso de conferencia de acceso telefónico mediante los cmdlets de Windows PowerShell

Los números de acceso de conferencia de acceso telefónico también pueden eliminarse con el Windows PowerShell y mediante el cmdlet **Remove-CsDialInConferencingAccessNumber**. Este cmdlet puede ejecutarse desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Eliminación de un número de acceso de conferencia de acceso telefónico específico

  - Este comando elimina el número de acceso de conferencia de acceso telefónico con la identidad sip:RedmondDialInAccess@litwareinc.com:
    
        Remove-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialInAccess@litwareinc.com"

## Eliminación de todos los números de acceso de conferencia de acceso telefónico asignados a una región específica

  - Este comando elimina todos los números de acceso de conferencia de acceso telefónico asociados a la región noroeste:
    
        Get-CsDialInConferencingAccessNumber -Region "Northwest" | Remove-CsDialInConferencingAccessNumber

## Eliminación de números de acceso de conferencia de acceso telefónico en función del idioma principal

  - Este comando elimina todos los números de acceso de conferencia de acceso telefónico para los que el italiano es el idioma principal:
    
        Get-CsDialInConferencingAccessNumber | Where-Object {$_.PrimaryLanguage -eq "it-IT"} | Remove-CsDialInConferencingAccessNumber

Para más información, vea el tema de ayuda del cmdlet [Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsDialInConferencingAccessNumber).

