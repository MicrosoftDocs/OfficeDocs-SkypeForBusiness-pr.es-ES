---
title: 'Lync Server 2013: crear o modificar sitios de red'
description: 'Lync Server 2013: crear o modificar sitios de red.'
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
ms.openlocfilehash: 700f089cfe190a8f46b5eefc05e656e7c62a59a9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544016"
---
# <a name="creating-or-modifying-network-sites-in-lync-server-2013"></a>Crear o modificar sitios de red en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-08_

Los sitios de red son las oficinas o ubicaciones configuradas dentro de cada región de una implementación de Enhanced 9-1-1 o control de admisión de llamadas (CAC). Puede usar el panel de control de Microsoft Lync Server 2013 para configurar sitios y asociarlos con regiones. Por ejemplo, una región de red para Norteamérica se podría asociar con sitios de red como Chicago, Redmond y Vancouver. Debe crearse un sitio de red CAC para cada sitio de una organización, incluso aunque no tenga limitaciones de ancho de banda. En el panel de control de Lync Server, puede crear, modificar y eliminar sitios de red. Utilice los procedimientos siguientes para crear o modificar un sitio de red. Para obtener más información sobre cómo eliminar un sitio de red existente, consulte [eliminar un sitio de red existente en Lync Server 2013](lync-server-2013-deleting-an-existing-network-site.md).

<div>

## <a name="to-create-a-network-site"></a>Para crear un sitio de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Configuración de red** y, a continuación, en **Sitio**.

4.  En la página **Sitio**, haga clic en **Nuevo**.

5.  En **Sitio nuevo**, escriba un nombre para este sitio en el campo **Nombre**.
    
    <div>
    

    > [!NOTE]  
    > Los nombres de sitio deben ser únicos dentro de la implementación de Lync Server 2013.

    
    </div>

6.  En la lista desplegable **Región**, seleccione una región de red para asociarla con este sitio.

7.  (Opcional) Si desea definir limitaciones de ancho de banda en las llamadas de audio o vídeo para este sitio, seleccione el perfil de directiva de ancho de banda con la configuración adecuada en la lista desplegable **Directiva de ancho de banda**.
    
    <div>
    

    > [!NOTE]  
    > Puede ver la información detallada de los perfiles de directivas de ancho de banda disponibles o crear uno nuevo en la página <STRONG>Perfil de directiva</STRONG> del grupo <STRONG>Configuración de red</STRONG>. Para obtener más información, consulte <A href="lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md">creación o modificación de perfiles de directiva de ancho de banda en Lync Server 2013</A>.

    
    </div>

8.  (Opcional) Si desea proporcionar parámetros de ubicación para este sitio, seleccione una directiva de ubicación de la lista desplegable **Directiva de ubicación**.
    
    <div>
    

    > [!NOTE]  
    > La directiva de ubicación asigna al sitio un Enhanced 9-1-1 (E9-1-1) específico y parámetros de ubicación de cliente. Puede ver la información detallada de las directivas de ubicación disponibles o crear una nueva desde la página <STRONG>Directiva de ubicación</STRONG> del grupo <STRONG>Configuración de red</STRONG>. Para obtener más información, consulte <A href="lync-server-2013-viewing-location-policy-information.md">ver información de directivas de ubicación en Lync Server 2013</A>.

    
    </div>

9.  (Opcional) Escriba un valor en el campo **Descripción** para proporcionar más información acerca de este sitio más allá de lo que se pueda deducir de su nombre.

10. Haga clic en **Confirmar**.
    
    <div>
    

    > [!NOTE]  
    > No use la tabla <STRONG>Subredes asociadas</STRONG> al crear un sitio de red nuevo. Al crear o modificar la subred, asocie una subred con un sitio. Para obtener más información, consulte <A href="lync-server-2013-create-or-modify-network-subnets.md">crear o modificar subredes de red en Lync Server 2013</A>.

    
    </div>

</div>

<div>

## <a name="to-modify-a-network-site"></a>Para modificar un sitio de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Configuración de red** y, a continuación, en **Sitio**.

4.  En la página **Sitio**, haga clic en el sitio que desea modificar.

5.  En el menú **Editar**, haga clic en **Mostrar detalles**.

6.  En la página **Editar sitio**, puede modificar la descripción, la región, el perfil de directiva de ancho de banda y la directiva de ubicación asociados con el sitio. Para obtener más información, consulte la sección "Para crear un sitio de red" que aparece anteriormente en este tema.

7.  Haga clic en **Confirmar**.

No es posible modificar la tabla **Subredes asociadas** de esta página. La lista de subredes asociadas solo es de referencia, por lo que debe conocer qué subredes se verán afectadas cuando modifique la configuración del sitio.

</div>

<div>

## <a name="to-delete-a-network-site"></a>Para eliminar un sitio de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Configuración de red** y, a continuación, en **Sitio**.

4.  En la página **Sitio**, haga clic en el sitio que desea eliminar.
    
    <div>
    

    > [!NOTE]  
    > Puede eliminar más de un sitio en la misma operación. Para hacerlo, pulse CTRL y seleccione varios sitios manteniendo pulsada la tecla CTRL. O bien, para seleccionar todos los sitios, haga clic en <STRONG>Seleccionar todo</STRONG> en el menú <STRONG>Editar</STRONG>.

    
    </div>

5.  En el menú **Editar**, haga clic en **Eliminar**.

6.  Haga clic en **Aceptar**.
    
    <div>
    

    > [!WARNING]  
    > No se puede eliminar un sitio de red si está asociado con la subred de una red. Si intenta quitar un sitio asociado a una subred, recibirá un mensaje de error. Para ver si un sitio está asociado con alguna subred, haga clic en el sitio y, a continuación, haga clic en <STRONG>Mostrar detalles</STRONG> en el menú <STRONG>Editar</STRONG>.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Consulte también


[Eliminación de un sitio de red existente en Lync Server 2013](lync-server-2013-deleting-an-existing-network-site.md)  


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

