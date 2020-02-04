---
title: 'Lync Server 2013: configuración de vínculos de región de red'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring network region links
ms:assetid: 952bc93e-e6aa-4539-85c7-2b15f14eb382
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182551(v=OCS.15)
ms:contentKeyID: 48184829
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5d069bb5215fc977a35481a916f49e86fa644284
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743480"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-network-region-links-in-lync-server-2013"></a>Configuración de vínculos de regiones de red en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

Puede configurar vínculos entre dos regiones de red como parte de control de admisión de llamadas (CAC). Las regiones dentro de una red están vinculadas a través de la conectividad de red de área extensa (WAN). Puede usar el panel de control de Lync Server para definir un vínculo entre dos regiones de red y establecer las limitaciones de ancho de banda en las conexiones de audio y vídeo entre estas regiones. Para más información sobre cómo eliminar un vínculo de región de red existente, vea [eliminar vínculos de región de red en Lync Server 2013](lync-server-2013-deleting-network-region-links.md).

<div>

## <a name="to-create-a-network-region-link"></a>Para crear un vínculo a región de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **configuración de red** y, a continuación, en **vínculo de región**.

4.  En la página vínculo de la **región** , haga clic en **nuevo**.

5.  En el **vínculo nueva región**, escriba un valor en el campo **nombre** .
    
    <div>
    

    > [!NOTE]  
    > Este valor debe ser único dentro de la implementación de Lync Server 2013.

    
    </div>

6.  En la lista desplegable ** \#región de red 1** , seleccione una de las dos regiones para vincular.

7.  En la lista desplegable ** \#región de red 2** , seleccione la otra región que desea vincular. Esta región debe ser diferente de la región seleccionada para la región \#de red 1.

8.  Faculta Si desea colocar limitaciones de ancho de banda en las llamadas de audio o vídeo entre estas regiones, seleccione un perfil de directiva de ancho de banda en la lista desplegable **Directiva de ancho de banda** .

9.  Haga clic en **Confirmar**.

</div>

<div>

## <a name="to-modify-a-network-region-link"></a>Para modificar un vínculo de región de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **configuración de red** y, a continuación, en **vínculo de región**.

4.  En la página vínculo de la **región** , haga clic en el vínculo de la región que desea modificar.

5.  En el menú **Editar**, haga clic en **Mostrar detalles**.

6.  En el **vínculo editar región**, puede modificar las regiones vinculadas o el perfil de directiva de ancho de banda para este vínculo.

7.  Haga clic en **Confirmar**.

</div>

<div>

## <a name="see-also"></a>Vea también


[Eliminar vínculos de regiones de red en Lync Server 2013](lync-server-2013-deleting-network-region-links.md)  


[New-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)  
[Set-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)  
[Remove-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)  
[Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>
