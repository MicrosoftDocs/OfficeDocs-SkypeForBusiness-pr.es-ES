---
title: Visualización de la información de ruta de región de red
TOCTitle: Visualización de la información de ruta de región de red
ms:assetid: 34dd9fa3-e695-4680-b244-3019298b5009
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688021(v=OCS.15)
ms:contentKeyID: 49889042
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Visualización de la información de ruta de región de red

 

_**Última modificación del tema:** 2013-02-23_

Todas las regiones dentro de una configuración de control de admisión de llamadas (CAC) deben poder obtener acceso de alguna forma a todas las demás regiones. Mientras que los vínculos regionales establecen las limitaciones de ancho de banda de las conexiones entre regiones y también representan los vínculos físicos, las rutas determinan la ruta de acceso vinculada que atravesará la conexión de una región a otra. Use los siguientes procedimientos para ver las rutas regionales de red en Panel de control de Lync Server 2013 o Shell de administración de Lync Server 2013. Para obtener detalles acerca de la creación o modificación de rutas regionales de red, vea [Creación o modificación de rutas de regiones de red](lync-server-2013-creating-or-modifying-network-region-routes.md).

## Para ver la información de ruta regional de red en Panel de control de Lync Server

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Configuración de red** y, a continuación, en **Ruta de región** .

4.  En la página **Ruta de región**, haga clic en la ruta regional que desea ver.
    

    > [!NOTE]
    > Solo puede ver una ruta regional cada vez.



5.  En el menú **Editar** , haga clic en **Mostrar detalles** .

## Ver información de ruta regional de red usando los cmdlets de Lync Server PowerShell

La información de ruta regional de red también se puede ver mediante Lync Server PowerShell y el cmdlet Get-CsNetworkInterRegionRoute. Este cmdlet se puede ejecutar desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Ver información de ruta regional de red

  - Para ver información acerca de todas las rutas regionales de red, escriba el siguiente comando en el Shell de administración de Lync Server y, a continuación, presione ENTRAR:
    
        Get-CsNetworkInterRegionRoute
    
    Devolverá información similar a la siguiente:
    
        Identity                  : TransAmericaRoute
        NetworkRegionLinks        : {NorthwestToNortheast}
        InterNetworkRegionRouteID : TransAmericaRoute
        NetworkRegionID1          : Pacific Northwest
        NetworkRegionID2          : Northeast

Para obtener más información, vea el tema de la Ayuda para el cmdlet [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkInterRegionRoute).

## Vea también

#### Tareas

[Creación o modificación de rutas de regiones de red](lync-server-2013-creating-or-modifying-network-region-routes.md)  
[Eliminación de rutas de región de red existentes](lync-server-2013-deleting-existing-network-region-routes.md)

