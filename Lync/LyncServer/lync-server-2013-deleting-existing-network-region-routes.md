---
title: 'Lync Server 2013: eliminar rutas de región de red existentes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting existing network region routes
ms:assetid: 6256ff80-5f1e-48b4-928b-24aeb3c1a0e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688074(v=OCS.15)
ms:contentKeyID: 49733669
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f07a0331563c4d78c4e8fc3391b7f8423a2ecc21
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525397"
---
# <a name="deleting-existing-network-region-routes-in-lync-server-2013"></a>Eliminación de rutas de región de red existentes en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

Todas las regiones dentro de una configuración de control de admisión de llamadas (CAC) deben poder obtener acceso de alguna forma a todas las demás regiones. Mientras que los vínculos regionales establecen las limitaciones de ancho de banda de las conexiones entre regiones y también representan los vínculos físicos, las rutas determinan la ruta de acceso vinculada que atravesará la conexión de una región a otra. Puede usar el panel de control de Lync Server para configurar rutas de región de red. En el panel de control de Lync Server, puede crear, modificar o eliminar una ruta de región de red. Use este tema para eliminar las rutas de región de red existentes. Para obtener información detallada sobre cómo crear o modificar rutas de región de red, vea [crear o modificar rutas de regiones de red en Lync Server 2013](lync-server-2013-creating-or-modifying-network-region-routes.md).

<div>

## <a name="to-delete-a-network-region-route"></a>Para eliminar una ruta regional de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Configuración de red** y, a continuación, en **Ruta regional**.

4.  En la página **Ruta regional**, haga clic en la ruta regional que quiera eliminar.
    
    <div>
    

    > [!NOTE]  
    > Puede eliminar más de una ruta regional en la misma operación. Para hacerlo, presione la tecla CTRL y seleccione varias rutas regionales sin dejar de presionar CTRL. También puede seleccionar todas las rutas regionales haciendo clic en <STRONG>Seleccionar todo</STRONG> en el menú <STRONG>Editar</STRONG>.

    
    </div>

5.  En el menú **Editar**, haga clic en **Eliminar**.

6.  Haga clic en **Aceptar**.

</div>

<div>

## <a name="see-also"></a>Consulte también


[Creación o modificación de rutas de región de red en Lync Server 2013](lync-server-2013-creating-or-modifying-network-region-routes.md)  


[Configurar una ruta de región de red](https://technet.microsoft.com/library/gg133706\(v=ocs.15\))  


[New-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)  
[Set-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute)  
[Remove-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  
[Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

