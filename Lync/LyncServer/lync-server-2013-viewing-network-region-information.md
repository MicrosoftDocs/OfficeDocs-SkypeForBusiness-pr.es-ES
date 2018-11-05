---
title: Visualización de la información de región de red
TOCTitle: Visualización de la información de región de red
ms:assetid: 665740d0-a3ed-460f-8337-5ed945f90589
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688076(v=OCS.15)
ms:contentKeyID: 49889207
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Visualización de la información de región de red

 

_**Última modificación del tema:** 2013-02-23_

Una región de red interconecta varias partes de una red a través de varias zonas geográficas. Cada región de red debe asociarse con un sitio central. El sitio central es el sitio del centro de datos donde se está ejecutando el servicio de directiva de ancho de banda de CAC (control de admisión de llamadas). Puede usar Panel de control de Lync Server para ver las regiones de red. Las regiones de red incluyen valores de configuración que determinan si se permiten las rutas alterativas a través de Internet para las conexiones de audio y vídeo. Use este tema para ver las regiones de red existentes. Para obtener información sobre cómo crear o modificar o regiones de red, consulte [Creación o modificación de regiones de red](lync-server-2013-creating-or-modifying-network-regions.md).

## Para ver información sobre una región de red con Panel de control de Lync Server

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Configuración de red** y, a continuación, en **Región**.

4.  En la página **Región**, haga clic en la región que quiera ver.
    

    > [!NOTE]
    > Solo puede ver una región en la misma operación.



5.  En el menú **Editar**, haga clic en **Mostrar detalles**.

## Visualización de información de una región de red mediante cmdlets de Windows PowerShell

Puede ver información de una región de red mediante el Windows PowerShell y el cmdlet **Get-CsNetworkRegion**. Puede ejecutar este cmdlet desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Para ver información de una región de red

  - Para ver información sobre todas las regiones de red, escriba el siguiente comando en el Shell de administración de Lync Server y presione ENTRAR:
    
        Get-CsNetworkRegion
    
    Obtendrá información parecida a la siguiente:
    
        Identity         : Pacific Northwest
        Description      :
        BypassID         : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        CentralSite      : Site:Redmond1
        BWAlternatePaths : {BWPolicyModality=Audio;AlternatePath=True, 
                           BWPolicyModality=Video;AlternatePath=True}
        NetworkRegionID  : Pacific Northwest

Para obtener más información, consulte el tema de ayuda del cmdlet [Get-CsNetworkRegion](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkRegionLink).

## Vea también

#### Tareas

[Creación o modificación de regiones de red](lync-server-2013-creating-or-modifying-network-regions.md)  
[Eliminación de regiones de red existentes](lync-server-2013-deleting-existing-network-regions.md)

