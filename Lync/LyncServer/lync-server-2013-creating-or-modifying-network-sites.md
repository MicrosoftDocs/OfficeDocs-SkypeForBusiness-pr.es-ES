---
title: 'Lync Server 2013: crear o modificar sitios de red'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying network sites
ms:assetid: 358aa08a-c5bc-45fc-8017-19e6202f88c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520975(v=OCS.15)
ms:contentKeyID: 48183801
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4c77c343bff92e25ffc1678bc06e7a0ef05d3f96
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728770"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-network-sites-in-lync-server-2013"></a>Crear o modificar sitios de red en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-08_

Los sitios de red son las oficinas o ubicaciones configuradas dentro de cada región de control de admisión de llamadas (CAC) o implementación mejorada de 9-1-1. Puede usar el panel de control de Microsoft Lync Server 2013 para configurar sitios y asociarlos con regiones. Por ejemplo, una región de red para Norteamérica puede estar asociada a sitios de redes como Chicago, Redmond y Vancouver. Es necesario crear un sitio de red CAC para cada sitio dentro de una organización, incluso si ese sitio no tiene limitaciones de ancho de banda. En el panel de control de Lync Server puede crear, modificar y eliminar sitios de red. Use los procedimientos siguientes para crear o modificar un sitio de red. Para obtener más información sobre cómo eliminar un sitio de red existente, consulte [eliminar un sitio de red existente en Lync Server 2013](lync-server-2013-deleting-an-existing-network-site.md).

<div>

## <a name="to-create-a-network-site"></a>Para crear un sitio de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **configuración de red** y, después, en **sitio**.

4.  En la página **sitio** , haga clic en **nuevo**.

5.  En **nuevo sitio**, escriba un nombre para este sitio en el campo **nombre** .
    
    <div>
    

    > [!NOTE]  
    > Los nombres de los sitios deben ser únicos en la implementación de Lync Server 2013.

    
    </div>

6.  En la lista desplegable **región** , seleccione la región de red que se va a asociar con este sitio.

7.  Faculta Si desea colocar limitaciones de ancho de banda en las llamadas de audio o vídeo a este sitio, seleccione el perfil de directiva de ancho de banda con la configuración adecuada de la lista desplegable **Directiva de ancho de banda** .
    
    <div>
    

    > [!NOTE]  
    > Puede ver los detalles de los perfiles de directiva de ancho de banda disponibles o crear un nuevo perfil de directiva de ancho de banda en la página <STRONG>Perfil de directiva</STRONG> del grupo <STRONG>configuración de red</STRONG> . Para obtener más información, vea <A href="lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md">crear o modificar perfiles de directiva de ancho de banda en Lync Server 2013</A>.

    
    </div>

8.  Faculta Si desea proporcionar la configuración de ubicación para este sitio, seleccione una directiva de ubicación en la lista desplegable **Directiva de ubicación** .
    
    <div>
    

    > [!NOTE]  
    > La Directiva de ubicación asigna una configuración de ubicación de cliente, 9-1-1 (E9-1-1) específica y mejorada al sitio. Puede ver los detalles de las directivas de ubicación disponibles o crear una nueva Directiva de ubicación desde la página de <STRONG>directivas</STRONG> de ubicación del grupo <STRONG>configuración de red</STRONG> . Para obtener más información, consulte <A href="lync-server-2013-viewing-location-policy-information.md">ver información de directivas de ubicación en Lync Server 2013</A>.

    
    </div>

9.  Faculta Escriba un valor en el campo **Descripción** para proporcionar más información sobre este sitio que no puede expresarse solo por el nombre.

10. Haga clic en **Confirmar**.
    
    <div>
    

    > [!NOTE]  
    > No use la tabla de <STRONG>subredes asociada</STRONG> cuando cree un nuevo sitio de red. Al crear o modificar la subred, se asocia una subred con un sitio. Para obtener más información, consulte <A href="lync-server-2013-create-or-modify-network-subnets.md">crear o modificar subredes de red en Lync Server 2013</A>.

    
    </div>

</div>

<div>

## <a name="to-modify-a-network-site"></a>Para modificar un sitio de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **configuración de red** y, después, en **sitio**.

4.  En la página del **sitio** , haga clic en el sitio que desea modificar.

5.  En el menú **Editar**, haga clic en **Mostrar detalles**.

6.  En la página **Editar sitio** , puede modificar la descripción, la región, el perfil de la Directiva de ancho de banda y la Directiva de ubicación asociada al sitio. Para obtener más información, vea la sección "para crear un sitio de red" anteriormente en este tema.

7.  Haga clic en **Confirmar**.

No puede modificar la tabla de **subredes asociada** en esta página. La lista de subredes asociadas se proporciona para que sea consciente de las subredes que se verán afectadas al modificar la configuración del sitio.

</div>

<div>

## <a name="to-delete-a-network-site"></a>Para eliminar un sitio de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **configuración de red** y, después, en **sitio**.

4.  En la página del **sitio** , haga clic en el sitio que desea eliminar.
    
    <div>
    

    > [!NOTE]  
    > Puede eliminar más de un sitio a la vez. Para ello, presione CTRL y seleccione varios sitios mientras mantiene presionada la tecla CTRL. O bien, para seleccionar todos los sitios, haga clic en <STRONG>seleccionar todo</STRONG> en el menú <STRONG>edición</STRONG> .

    
    </div>

5.  En el menú **Editar** , haga clic en **eliminar**.

6.  Haga clic en **Aceptar**.
    
    <div>
    

    > [!WARNING]  
    > No puede quitar un sitio de red si está asociado con una subred de red. Si intenta quitar un sitio asociado a una subred, recibirá un mensaje de error. Para ver si un sitio está asociado con cualquier subred, haga clic en el sitio y, a continuación, haga clic en <STRONG>Mostrar detalles</STRONG> en el menú <STRONG>edición</STRONG> .

    
    </div>

</div>

<div>

## <a name="see-also"></a>Vea también


[Eliminar un sitio de red existente en Lync Server 2013](lync-server-2013-deleting-an-existing-network-site.md)  


[New-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)  
[Set-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)  
[Remove-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)  
[Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

