---
title: "Eliminar una colección existente de opciones de configuración de versión de cliente"
TOCTitle: "Supp. une coll. existante de par. de configuration de version du client"
ms:assetid: 70bf1216-d0d2-45ce-881f-b8edadf3cec7
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ898480(v=OCS.15)
ms:contentKeyID: 52061658
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Eliminar una colección existente de opciones de configuración de versión de cliente

 

_**Última modificación del tema:** 2013-02-23_

Si quiere quitar las opciones de configuración de cliente que se han configurado previamente para un sitio, puede hacerlo desde el Panel de control de Lync Server 2013 o desde el Shell de administración de Lync Server 2013.

## Para quitar las opciones de configuración de cliente desde el Panel de control de Lync Server

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Clientes** y luego haga clic en el botón de navegación **Configuración de versión de cliente**.

4.  Seleccione el sitio, haga clic en **Editar**, luego en **Eliminar** y después en **Aceptar**.

## Quitar las opciones de configuración de la versión de cliente con cmdlets de Windows PowerShell

Puede eliminar las opciones de configuración de la versión de cliente con el cmdlet de **Remove-CsClientVersionConfiguration**. Este cmdlet se puede ejecutar tanto desde el Shell de administración de Lync Server 2013 como desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Para quitar una colección especificada de opciones de configuración de la versión de cliente

  - El siguiente comando elimina las opciones de configuración de la versión de cliente aplicadas al sitio Redmond:
    
        Remove-CsClientVersionConfiguration -Identity "site:Redmond"

## Para quitar todas las opciones de configuración de la versión de cliente aplicadas al ámbito de sitio

  - Este comando elimina todas las opciones de configuración de la versión de cliente configuradas en el ámbito de sitio:
    
        Get-CsClientVersionConfiguration -Filter site:* | Remove-CsClientVersionConfiguration

## Para quitar todas las opciones de configuración de la versión de cliente basadas en el valor de la propiedad DefaultAction

  - Por último, este comando quita todas las opciones de configuración de la versión de cliente en las que la acción predeterminada se ha establecido en “Bloquear”:
    
        Get-CsClientVersionConfiguration | Where-Object {$_.DefaultAction -eq "Block" | Remove-CsClientVersionConfiguration

Para más información, consulte el tema de ayuda del cmdlet [Remove-CsClientVersionConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsClientVersionConfiguration).

