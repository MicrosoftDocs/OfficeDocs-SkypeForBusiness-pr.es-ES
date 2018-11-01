---
title: "Lync Server 2013: Restablecer la directiva global para el acceso de usuarios externos"
TOCTitle: Restablecer la directiva global para el acceso de usuarios externos
ms:assetid: 8207e1b1-de9e-461f-975f-fcc5c526849a
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg182545(v=OCS.15)
ms:contentKeyID: 48275864
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Restablecer la directiva global para el acceso de usuarios externos en Lync Server 2013

 

_**Última modificación del tema:** 2013-02-22_

No se puede eliminar íntegramente una política global. Si se usa la opción **Eliminar** en la directiva global solamente se restablece la directiva global según la configuración predeterminada, que no incluye compatibilidad con opciones de acceso para usuarios externos.

## Para restablecer la directiva global según la configuración predeterminada

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Acceso para usuarios externos** y en **Directiva de acceso externo** .

4.  En la ficha **Directiva de acceso externo** , haga clic en la directiva global, haga en **Editar** y, a continuación, haga clic en **Eliminar** .

5.  Cuando se le solicite confirmar la eliminación, haga clic en **Aceptar** . Aparecerá un mensaje en la parte superior de la página donde se le comunica que la directiva global se ha restablecido.

## Restablecer la directiva de acceso externo global usando los cmdlets de Windows PowerShell

La directiva de acceso externo global puede restablecerse mediante el Windows PowerShell y el cmdlet Remove-CsExternalAccessPolicy. Este cmdlet puede ejecutarse desde el Shell de administración de Lync Server 2013 o desde una sesión remota Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Para restablecer la directiva de acceso externo global

  - Este comando restablece la directiva de acceso externo global:
    
        Remove-CsExternalAccessPolicy -Identity "global"

Si desea más información, consulte el tema de ayuda relativo al cmdlet [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy).

