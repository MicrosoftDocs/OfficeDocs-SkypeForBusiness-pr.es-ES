---
title: Visualización de la información del sitio de red
TOCTitle: Visualización de la información del sitio de red
ms:assetid: 24a97d98-b168-4016-81bf-c2c478092b87
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ687996(v=OCS.15)
ms:contentKeyID: 49888925
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Visualización de la información del sitio de red

 

_**Última modificación del tema:** 2013-02-23_

Los sitios de red son las oficinas o ubicaciones configuradas dentro de cada región de una implementación de Enhanced 9-1-1 o control de admisión de llamadas (CAC). Puede ver la información de sitio de red en Panel de control de Lync Server 2013 o Shell de administración de Lync Server. Para obtener detalles acerca de la creación o modificación de sitios de red, vea [Creación o modificación de sitios de red](lync-server-2013-creating-or-modifying-network-sites.md).

## Para ver información de sitio de red en Panel de control de Lync Server

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Configuración de red** y, a continuación, en **Sitio** .

4.  En la página **Sitio**, haga clic en el sitio que desea ver.
    

    > [!NOTE]
    > Solo puede ver información para un sitio cada vez.



5.  En el menú **Editar** , haga clic en **Mostrar detalles** .

## Para ver información de sitio de red usando los cmdlets de Shell de administración de Lync Server

Puede ver la información de sitio de red usando el cmdlet Get-CsNetworkSite. Este cmdlet se puede ejecutar desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Para ver la información de sitio de red

  - Para ver la información acerca de todos sus sitios de red, escriba el siguiente comando en el Shell de administración de Lync Server y, a continuación, presione ENTRAR:
    
        Get-CsNetworkSite
    
    Devolverá información similar a la siguiente:
    
        Identity          : Redmond
        NetworkSiteID     : Redmond
        Description       :
        NetworkRegionID   : Pacific Northwest
        BypassID          : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        BWPolicyProfileID :
        LocationPolicy    :

Para obtener más información, vea el tema de la Ayuda para el cmdlet [Get-CsNetworkSite](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkSite).

## Vea también

#### Tareas

[Creación o modificación de sitios de red](lync-server-2013-creating-or-modifying-network-sites.md)  
[Eliminación de un sitio de red existente](lync-server-2013-deleting-an-existing-network-site.md)

