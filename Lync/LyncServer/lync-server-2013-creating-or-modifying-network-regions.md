---
title: 'Lync Server 2013: crear o modificar regiones de red'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying network regions
ms:assetid: bd08bb66-5976-4ece-b45c-7de19569f814
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182579(v=OCS.15)
ms:contentKeyID: 48185266
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fbebccd02b74c4fbfb69225a6397c1dd7cef862d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756284"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-network-regions-in-lync-server-2013"></a>Crear o modificar regiones de red en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

Una región de red interconecta varias partes de una red en varias áreas geográficas. Cada región de la red debe estar asociada con un sitio central. El sitio central es el sitio del centro de datos en el que se está ejecutando el servicio de directivas de ancho de banda de control de admisión de llamadas (CAC). Puede usar el panel de control de Lync Server para configurar regiones de red. Las regiones de red incluyen opciones que determinan si se permiten rutas alternativas a través de Internet para conexiones de audio y vídeo. En el panel de control de Lync Server, puede crear, modificar o eliminar una región de red. Use este tema para crear y modificar regiones de red. Para obtener más información sobre cómo eliminar regiones de red existentes, consulte [eliminar regiones de red existentes en Lync Server 2013](lync-server-2013-deleting-existing-network-regions.md).

<div>

## <a name="to-create-a-network-region"></a>Para crear una región de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **configuración de red** y, después, en **región**.

4.  En la página **región** , haga clic en **nuevo**.

5.  En la página **nueva región** , escriba un valor en el campo **nombre** . Este valor debe ser único dentro de la implementación de Microsoft Lync Server 2013.

6.  En la lista desplegable **sitio central** , seleccione el sitio central de esta región de red.

7.  La casilla de verificación **Habilitar ruta alternativa de audio** está activada de forma predeterminada. Este campo determina si las llamadas de audio se redirigirán a través de una ruta de acceso alternativa si el ancho de banda adecuado no existe en la ruta de acceso principal. Desactive esta casilla solo si necesita desactivar la descarga en Internet. Si cualquiera de las llamadas va a ser de Internet, esta casilla debe estar activada, independientemente de la configuración del ancho de banda.

8.  La casilla de verificación **Habilitar ruta alternativa de vídeo** está activada de forma predeterminada. Este campo determina si las videollamadas se redirigirán a través de una ruta alternativa si el ancho de banda adecuado no existe en la ruta de acceso principal. Desactive esta casilla solo si necesita desactivar la descarga en Internet. Si cualquiera de las llamadas va a ser de Internet, esta casilla debe estar activada, independientemente de la configuración del ancho de banda.

9.  Faculta Escriba un valor en el campo **Descripción** para proporcionar más información sobre esta región que no puede expresarse solo por el nombre.

10. Haga clic en **Confirmar**.

La tabla de **sitios asociados** no se usa para crear una región de red. Al crear o modificar el sitio, se asocia un sitio con una región. Para obtener más información, vea [crear o modificar sitios de red en Lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md).

</div>

<div>

## <a name="to-modify-a-network-region"></a>Para modificar una región de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **configuración de red** y, después, en **región**.

4.  En la página **región** , haga clic en la región que desea modificar.

5.  En el menú **Editar**, haga clic en **Mostrar detalles**.

6.  En la página **Editar región** , puede modificar la configuración para habilitar y deshabilitar rutas de audio y vídeo alternativas, y cambiar la descripción (para obtener información detallada, consulte la sección "para crear una región de red" anteriormente en este tema.

7.  Haga clic en **Confirmar**.

No puede modificar los **sitios asociados** en esta página. La lista de sitios asociados se proporciona como referencia para que usted sepa qué sitios se verán afectados al modificar la configuración de la región.

</div>

<div>

## <a name="see-also"></a>Vea también


[Eliminar regiones de red existentes en Lync Server 2013](lync-server-2013-deleting-existing-network-regions.md)  
[Configurar regiones de red para CAC en Lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md)  


[New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)  
[Set-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)  
[Remove-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)  
[Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

