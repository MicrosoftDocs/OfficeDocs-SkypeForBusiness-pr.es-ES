---
title: "Eliminar un sitio o una directiva de usuario para el acceso de usuarios externos"
TOCTitle: Eliminar un sitio o una directiva de usuario para el acceso de usuarios externos
ms:assetid: 6d907507-825b-4354-9c03-337a459f72de
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg521013(v=OCS.15)
ms:contentKeyID: 48275630
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Eliminar un sitio o una directiva de usuario para el acceso de usuarios externos en Lync Server 2013

 

_**Última modificación del tema:** 2013-02-22_

Puede eliminar cualquier directiva de sitio o usuario que aparezca en el Panel de control de Lync Server, en la página **Directiva de acceso externo** . La eliminación de la directiva global no la elimina realmente, sino que solo la restablece según la configuración predeterminada, que no incluye compatibilidad con opciones de acceso para usuarios externos. Para más información sobre cómo restablecer una directiva global, consulte [Restablecer la directiva global para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-reset-the-global-policy-for-external-user-access.md).

## Para eliminar una directiva de sitio o usuario para el acceso de usuarios externos

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Haga clic en **Acceso de usuarios externos** y seleccione **Directiva de acceso externo** .

4.  En la ficha **Directiva de acceso externo** , haga clic en la directiva de sitio o usuario que desea eliminar, seleccione **Editar** y, a continuación, haga clic en **Eliminar** .

5.  Cuando se le solicite que confirme la eliminación, haga clic en **Aceptar** .

## Eliminar las Directivas de PIN mediante cmdlets de Windows PowerShell

Las directivas de acceso externo también se pueden eliminar con Windows PowerShell y el cmdlet Remove-CsExternalAccessPolicy. Puede ejecutar el cmdlet desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Para quitar una directivas de acceso externo específica

  - Con este comando se quita la directiva de acceso externo aplicada al sitio de Redmond:
    
        Remove-CsExternalAccessPolicy -Identity "site:Redmond"

## Para quitar todas las directivas de acceso externo que se aplican al ámbito por usuario

  - Con este comando se quitan todas las directivas de acceso externo configuradas en el ámbito por usuario:
    
        Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy

## Para quitar todas las directivas de acceso externo cuando el acceso de usuarios externos está deshabilitado

  - Con este comando se quitan todas las directivas de acceso externo cuando el acceso de usuarios externos se ha deshabilitado:
    
        Get-CsExternalAccessPolicy | Where-Object {$_.EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy

Si desea más información, consulte el tema de ayuda relativo al cmdlet [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy).

