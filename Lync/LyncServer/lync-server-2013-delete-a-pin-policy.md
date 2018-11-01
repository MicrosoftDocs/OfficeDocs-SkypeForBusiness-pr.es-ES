---
title: Eliminar una directiva de PIN
TOCTitle: Eliminar una directiva de PIN
ms:assetid: 7c378927-2e41-418e-9721-327021bd2e45
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg521020(v=OCS.15)
ms:contentKeyID: 48275781
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Eliminar una directiva de PIN

 

_**Última modificación del tema:** 2013-02-23_

Siga estos pasos para eliminar una directiva de número de identificación personal (PIN).


> [!NOTE]
> No puede eliminar la directiva global de PIN.



## Para eliminar una directiva de PIN en Panel de control de Lync Server 2013

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o se asigne al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que esté en la red en la que haya implementado Lync Server 2013.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Seguridad** y, a continuación, en **Directiva de PIN**.

4.  En la página **Directiva de PIN**, escriba en el campo de búsqueda el nombre completo o parcial de la directiva que desea eliminar.

5.  En la lista de directivas, seleccione la directiva que desee, haga clic en **Editar** y, a continuación, en **Eliminar**.

6.  Haga clic en **Aceptar**.

## Eliminar las Directivas de PIN mediante el Shell de administración de Lync Server y los Cmdlets

Puede eliminar las Directivas de PIN mediante el Windows PowerShell y el cmdlet Remove-CsPinPolicy. Puede ejecutar este cmdlet desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Eliminar una Directiva de PIN específica

  - Este comando elimina la Directiva de PIN con la RedmondPinPolicy de identidad:
    
        Remove-CsPinPolicy -Identity "RedmondPinPolicy"

## Eliminar todas las Directivas de PIN que se aplican al ámbito del sitio

  - Este comando elimina todas las Directivas de PIN configuradas en el ámbito del sitio:
    
        Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy

## Eliminar todas las Directivas de PIN que permiten el uso de patrones comunes

  - Y este elimina todas las Directivas de PIN que permiten el uso de patrones comunes:G
    
        et-CsPinPolicy | Where-Object {$_.AllowCommonPatterns -eq $True} | Remove-CsPinPolicy

Para más información, vea el tema de ayuda para el cmdlet [Remove-CsPinPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsPinPolicy).

