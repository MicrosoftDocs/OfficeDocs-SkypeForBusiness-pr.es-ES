---
title: Visualización de la información de la subred de red
TOCTitle: Visualización de la información de la subred de red
ms:assetid: 46f165f2-efe3-4cc1-9fee-a78b7f2ed41e
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688044(v=OCS.15)
ms:contentKeyID: 49889067
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Visualización de la información de la subred de red

 

_**Última modificación del tema:** 2013-02-23_

Puede usar el siguiente procedimiento para ver una subred de la red. En el Panel de control de Lync Server, puede crear, modificar o eliminar una subred de la red. Para más información sobre la creación o modificación de subredes de la red, vea [Crear o modificar subredes de red](lync-server-2013-create-or-modify-network-subnets.md).

## Para ver una subred de la red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Configuración de red** y, a continuación, en **Subred**.

4.  En la página **Subred** , haga clic en la subred que desea ver.
    

    > [!NOTE]
    > Solo puede ver una subred de cada vez.



5.  En el menú **Editar** , haga clic en **Mostrar detalles...**.

## Visualización de información de configuración de subred de la red con los cmdlets de Lync Server PowerShell

La información de subred de la red también se puede ver con Lync Server PowerShell y el cmdlet Get-CsNetworkSubnet. Este cmdlet se puede ejecutar desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Visualización de información de subred de la red

  - Para ver información sobre todas las subredes de la red, escriba el comando siguiente en el Shell de administración de Lync Server y luego presione ENTRAR:
    
        Get-CsNetworkSubnet
    
    Eso devolverá información similar a esta:
    
        Identity      : 172.11.15.0
        MaskBits      : 28
        Description   :
        NetworkSiteID : Redmond
        SubnetID      : 172.11.15.0

Para más información, vea el tema de ayuda del cmdlet [Get-CsNetworkSubnet](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkSubnet).

## Vea también

#### Tareas

[Crear o modificar subredes de red](lync-server-2013-create-or-modify-network-subnets.md)  
[Eliminación de subredes de red](lync-server-2013-deleting-network-subnets.md)

