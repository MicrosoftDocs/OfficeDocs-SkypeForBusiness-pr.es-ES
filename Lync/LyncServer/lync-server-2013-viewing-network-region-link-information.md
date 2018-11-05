---
title: Visualización de información del vínculo de región de red
TOCTitle: Visualización de información del vínculo de región de red
ms:assetid: 7b6b2ea2-83d8-4376-afb2-70e5d2cf6444
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688102(v=OCS.15)
ms:contentKeyID: 49889241
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Visualización de información del vínculo de región de red

 

_**Última modificación del tema:** 2013-02-23_

Puede ver enlaces entre dos regiones de red como parte de un servicio de control de admisión de llamadas (CAC). Las regiones dentro de una red están vinculadas con una conectividad física de red de área extensa (WAN). Puede usar el Panel de control de Lync Server para ver un vínculo existente entre dos regiones de red. Para obtener detalles acerca de la creación o modificación de un vínculo de región de red, vea [Configuración de vínculos de regiones de red](lync-server-2013-configuring-network-region-links.md).

## Para ver un vínculo de región de red en Panel de control de Lync Server

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Configuración de red** y luego en **Vínculo de región**.

4.  En la página **Vínculo de región**, haga clic en el vínculo de región que desea ver.
    

    > [!NOTE]
    > Solo puede ver información acerca de un vínculo de región a la vez.



5.  En el menú **Editar**, seleccione **Mostrar detalles**.

## Ver la información del vínculo de región de red mediante los cmdlets Shell de administración de Lync Server

También puede ver los vínculos de región mediante el Shell de administración de Lync Server y el cmdlet **Get-CsNetworkRegionLink**. Puede ejecutar este cmdlet desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Para ver la información de un vínculo de región de red

  - Para ver información acerca de todos los vínculos de región de red, escriba el siguiente comando en el Shell de administración de Lync Server y presione ENTRAR:
    
        Get-CsNetworkRegionLink
    
    Este comando devuelve información similar a la siguiente:
    
        Identity            : NorthwestToCalifornia
        BWPolicyProfileID   :
        NetworkRegionLinkID : NorthwestToCalifornia
        NetworkRegionID1    : Pacific Northwest
        NetworkRegionID2    : California

Para obtener información detallada, vea [Get-CsNetworkRegionLink](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkRegionLink).

## Vea también

#### Tareas

[Configuración de vínculos de sitios de red](lync-server-2013-configuring-network-site-links.md)

