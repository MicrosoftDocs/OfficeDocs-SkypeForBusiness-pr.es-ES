---
title: Eliminar una directiva de archivado
TOCTitle: Eliminar una directiva de archivado
ms:assetid: 4739a691-41cc-4128-8bb8-6d5a4c02107a
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg520989(v=OCS.15)
ms:contentKeyID: 48275153
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Eliminar una directiva de archivado

 

_**Última modificación del tema:** 2013-02-23_

Es posible eliminar directivas de usuario o de sitio. Las directivas globales no se pueden quitar. Si elimina la directiva global, Lync Server 2013 se restablece automáticamente a sus valores predeterminados.


> [!NOTE]
> Si habilitó la integración de Microsoft Exchange en la implementación, las directivas de Exchange controlar está habilitado el archivado para los usuarios que están alojados en Exchange 2013 y han colocado sus buzones en Conservación local. Para más información, vea <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Configuración de directivas para el archivado al usar la integración de Exchange Server</A> en la documentación de implementación.



## Para eliminar una directiva de usuario o de sitio para archivado

1.  Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, después, en **Directiva de archivado**.

4.  En la lista de directivas, haga clic en la directiva de usuario o sitio que desea eliminar, haga clic en **Editar** y, a continuación, en **Eliminar**.

5.  Haga clic en **Confirmar**.

## Quitar directivas de archivado con los cmdlets de Shell de administración de Lync Server

Las directivas de archivado también pueden eliminarse con Windows PowerShell y el cmdlet **Remove-CsArchivingPolicy**. Este cmdlet se puede ejecutar desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Quitar una directiva de archivado especificada

  - Como ejemplo, **Remove-CsArchivingPolicy** elimina la directiva con el sitio de identidad: Redmond. Tenga en cuenta que, cuando se elimina una directiva configurada en el ámbito de aplicación de sitio, los usuarios anteriormente administrados por la directiva del sitio, en su lugar, se regirán automáticamente por la directiva global de archivado. El comando siguiente quita el archivado aplicado en el sitio Redmond:
    
        Remove-CsArchivingPolicy -Identity site:Redmond

## Quitar todas las directivas de archivado aplicadas al ámbito por usuario

  - Este comando quita todas las directivas de archivado aplicadas al ámbito por usuario:
    
        Get-CsArchivingPolicy -Filter "tag:*" | Remove-CsArchivingPolicy

## Quitar todas las directivas de archivado que deshabilitan el archivado interno

  - Este comando quita todas las directivas de archivado donde se deshabilitó el archivado interno:
    
        Get-CsArchivingPolicy | Where-Object {$_.ArchiveInternal -eq $False} | Remove-CsArchivingPolicy

Para más información, vea el tema de ayuda del cmdlet [Remove-CsArchivingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsArchivingPolicy).

## Vea también

#### Otros recursos

[Administrar el archivado de las comunicaciones internas y externas en Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)

