---
title: 'Lync Server 2013: visualización de la información de la región de red'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Viewing network region information
ms:assetid: 665740d0-a3ed-460f-8337-5ed945f90589
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688076(v=OCS.15)
ms:contentKeyID: 49733672
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 52baf7c9dca4d663630bbf0cb17384916f5a953e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850074"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-network-region-information-in-lync-server-2013"></a>Ver información de la región de red en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-23_

Una región de red interconecta varias partes de una red en varias áreas geográficas. Cada región de la red debe estar asociada con un sitio central. El sitio central es el sitio del centro de datos en el que se está ejecutando el servicio de directivas de ancho de banda de control de admisión de llamadas (CAC). Puede usar el panel de control de Lync Server para ver las regiones de red. Las regiones de red incluyen opciones que determinan si se permiten rutas alternativas a través de Internet para conexiones de audio y vídeo. Use este tema para ver las regiones de red existentes. Para obtener detalles sobre cómo crear o modificar regiones de red existentes, vea [crear o modificar regiones de red en Lync Server 2013](lync-server-2013-creating-or-modifying-network-regions.md).

<div>

## <a name="to-view-information-about-a-network-region-with-lync-server-control-panel"></a>Para ver información sobre una región de red con el panel de control de Lync Server

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **configuración de red** y, después, en **región**.

4.  En la página **región** , haga clic en la región que desea ver.
    
    <div>
    

    > [!NOTE]  
    > Solo puedes ver una región a la vez.

    
    </div>

5.  En el menú **Editar**, haga clic en **Mostrar detalles**.

</div>

<div>

## <a name="viewing-network-region-information-by-using-windows-powershell-cmdlets"></a>Ver información de la región de red mediante cmdlets de Windows PowerShell

Puede ver la información de la región de red mediante Windows PowerShell y el cmdlet **Get-CsNetworkRegion** . Puede ejecutar este cmdlet desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.

<div>

## <a name="to-view-network-region-information"></a>Para ver la información de la región de red

  - Para ver información sobre todas las regiones de la red, escriba el siguiente comando en el shell de administración de Lync Server y, a continuación, presione ENTRAR:
    
        Get-CsNetworkRegion
    
    Devolverá información similar a la siguiente:
    
        Identity         : Pacific Northwest
        Description      :
        BypassID         : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        CentralSite      : Site:Redmond1
        BWAlternatePaths : {BWPolicyModality=Audio;AlternatePath=True, 
                           BWPolicyModality=Video;AlternatePath=True}
        NetworkRegionID  : Pacific Northwest

</div>

Para obtener más información, consulte el tema de ayuda para el cmdlet [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink) .

</div>

<div>

## <a name="see-also"></a>Vea también


[Crear o modificar regiones de red en Lync Server 2013](lync-server-2013-creating-or-modifying-network-regions.md)  
[Eliminar regiones de red existentes en Lync Server 2013](lync-server-2013-deleting-existing-network-regions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

