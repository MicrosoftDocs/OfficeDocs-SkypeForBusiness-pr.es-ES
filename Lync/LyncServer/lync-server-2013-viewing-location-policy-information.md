---
title: 'Lync Server 2013: visualización de información de directivas de ubicación'
description: 'Lync Server 2013: visualización de información de directivas de ubicación.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing location policy information
ms:assetid: 14e41bcb-ea0a-49c2-99b3-1f61fc34416d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520954(v=OCS.15)
ms:contentKeyID: 48183489
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2fecc5de5fb71014a1641038e9e09afba0e90cdb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565426"
---
# <a name="viewing-location-policy-information-in-lync-server-2013"></a>Ver información de directiva de ubicación en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

En Lync Server 2013, puede usar la Directiva de ubicación para aplicar la configuración relacionada con la funcionalidad mejorada 9-1-1 (E9-1-1) y la configuración de ubicación de usuarios o contactos. La directiva de ubicación determina si un usuario está habilitado para E9-1-1 y, si es así, cuál es el comportamiento de una llamada de emergencia. Por ejemplo, puede usar la Directiva de ubicación para definir el número que constituye una llamada de emergencia (por ejemplo, 911 en Estados Unidos), si se debe notificar automáticamente a la seguridad corporativa y cómo se debe enrutar la llamada.

Puede configurar directivas de ubicación desde el grupo de **configuración de red** en el panel de control de Lync Server 2013. En el panel de control de Lync Server, puede ver, crear, modificar o eliminar directivas de ubicación. Use el siguiente procedimiento para ver información acerca de las directivas de ubicación. Para obtener más información sobre cómo crear o modificar directivas de ubicación, consulte [creación o modificación de una directiva de ubicación en Lync Server 2013](lync-server-2013-creating-or-modifying-a-location-policy.md).

<div>

## <a name="to-view-information-about-a-location-policy"></a>Para ver información acerca de una directiva de ubicación

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Configuración de red** y, a continuación, en **Directiva de ubicación**.

4.  En la página **Directiva de ubicación**, seleccione la directiva de ubicación que desea modificar.

5.  En el menú **Editar**, haga clic en **Mostrar detalles**.
    
    <div>
    

    > [!NOTE]  
    > Solo puede ver información sobre una directiva de ubicación a la vez.

    
    </div>

Una sola directiva, denominada global, existe de forma predeterminada y no se puede eliminar ni cambiar de nombre. Sin embargo, puede modificar la directiva global. Esta Directiva se aplicará a todos los usuarios y contactos, a menos que cree directivas de sitio o directivas por usuario. Las directivas por usuario deben aplicarse a usuarios específicos.

</div>

<div>

## <a name="see-also"></a>Consulte también


[Creación o modificación de una directiva de ubicación en Lync Server 2013](lync-server-2013-creating-or-modifying-a-location-policy.md)  
[Crear directivas de ubicación en Lync Server 2013](lync-server-2013-create-location-policies.md)  
[Crear o modificar un sitio de red en Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md)  


[New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy)  
[Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy)  
[Remove-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsLocationPolicy)  
[Get-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsLocationPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

