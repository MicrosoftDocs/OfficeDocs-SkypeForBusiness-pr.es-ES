---
title: 'Lync Server 2013: visualización de la información de región de red'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network region information
ms:assetid: 665740d0-a3ed-460f-8337-5ed945f90589
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688076(v=OCS.15)
ms:contentKeyID: 49733672
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7222afb226a211609423cb3c5ad1e40383de67e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535727"
---
# <a name="viewing-network-region-information-in-lync-server-2013"></a>Ver la información de región de red en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-23_

Una región de red interconecta varias partes de una red a través de varias zonas geográficas. Cada región de red debe asociarse con un sitio central. El sitio central es el sitio del centro de datos donde se está ejecutando el servicio de directiva de ancho de banda de CAC (servicio de control de admisión de llamadas). Puede usar el panel de control de Lync Server para ver las regiones de red. Las regiones de red incluyen valores de configuración que determinan si se permiten las rutas alterativas a través de Internet para las conexiones de audio y vídeo. Use este tema para ver las regiones de red existentes. Para obtener información detallada acerca de la creación o modificación de regiones de red existentes, consulte [creación o modificación de regiones de red en Lync Server 2013](lync-server-2013-creating-or-modifying-network-regions.md).

<div>

## <a name="to-view-information-about-a-network-region-with-lync-server-control-panel"></a>Para ver información sobre una región de red con el panel de control de Lync Server

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Configuración de red** y en **Región**.

4.  En la página **región** , haga clic en la región que desea ver.
    
    <div>
    

    > [!NOTE]  
    > Solo puede ver una región a la vez.

    
    </div>

5.  En el menú **Editar **, haga clic en **Mostrar detalles **.

</div>

<div>

## <a name="viewing-network-region-information-by-using-windows-powershell-cmdlets"></a>Ver la información de región de red mediante cmdlets de Windows PowerShell

Puede ver la información de la región de red con Windows PowerShell y el cmdlet **Get-CsNetworkRegion** . Puede ejecutar este cmdlet desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server 2010 mediante PowerShell remoto" en [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-view-network-region-information"></a>Para ver la información de la región de red

  - Para ver información sobre todas las regiones de red, escriba el siguiente comando en el shell de administración de Lync Server y, a continuación, presione ENTRAR:
    
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

## <a name="see-also"></a>Consulte también


[Creación o modificación de regiones de red en Lync Server 2013](lync-server-2013-creating-or-modifying-network-regions.md)  
[Eliminación de regiones de red existentes en Lync Server 2013](lync-server-2013-deleting-existing-network-regions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

