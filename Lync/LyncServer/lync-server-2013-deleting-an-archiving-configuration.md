---
title: Eliminar una configuración de archivado
TOCTitle: Eliminar una configuración de archivado
ms:assetid: a8744d39-5cf2-474c-9a99-a0f3a37f846f
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205167(v=OCS.15)
ms:contentKeyID: 48276291
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Eliminar una configuración de archivado

 

_**Última modificación del tema:** 2013-02-23_

Puede eliminar una configuración de sitio o de grupo. La configuración global no se puede quitar. Si elimina la configuración global, esta se restablece automáticamente a los valores predeterminados. Para más información sobre cómo se implementan las configuraciones de archivado, incluidas las opciones que puede especificar y la jerarquía de configuraciones de archivado, vea [Cómo funciona el archivado en Lync Server 2013](lync-server-2013-how-archiving-works.md) en la documentación sobre planeación, implementación u operaciones.

## Para eliminar una configuración de sitio o de grupo para archivado

1.  Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, después, en **Configuración de archivado**.

4.  En la lista de configuraciones de archivado, haga clic en la configuración de sitio o de grupo que desea eliminar y, después, haga clic en **Editar** y en **Eliminar**.

5.  Haga clic en **Confirmar**.

## Quitar las opciones de configuración de archivado con los cmdlets del Shell de administración de Lync Server

Las opciones de configuración de archivado también se pueden eliminar con Windows PowerShell y el cmdlet Remove-CsArchivingConfiguration. Este cmdlet se puede ejecutar desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Windows PowerShellPara más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Quitar una colección específica de opciones de configuración de archivado

  - El siguiente comando quita las opciones de configuración de archivado aplicadas al sitio Redmond:
    
        Remove-CsArchivingConfiguration -Identity "site:Redmond"

## Quitar todas las opciones de configuración de archivado aplicadas al ámbito de sitio

  - Este comando quita todas las opciones de configuración de archivado aplicadas al ámbito de servicio:
    
        Get-CsArchivingConfiguration -Filter "site:*" | Remove-CsArchivingConfiguration

## Quitar las opciones de configuración de archivado según un valor de propiedad específico

  - Este comando quita todas las opciones de configuración de archivado en las que se deshabilitó el archivado de Exchange:
    
        Get-CsArchivingConfiguration | Where-Object {$_.EnableExchangeArchiving -eq $False} | Remove-CsArchivingConfiguration

Para más información, vea el tema de ayuda del cmdlet [Remove-CsArchivingConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsArchivingConfiguration).

## Vea también

#### Conceptos

[Cómo funciona el archivado en Lync Server 2013](lync-server-2013-how-archiving-works.md)  

#### Otros recursos

[Administrar el archivado de las comunicaciones internas y externas en Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)

