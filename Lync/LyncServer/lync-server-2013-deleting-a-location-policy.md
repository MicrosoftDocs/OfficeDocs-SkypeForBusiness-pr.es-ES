---
title: 'Lync Server 2013: eliminar una directiva de ubicación'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deleting a location policy
ms:assetid: 8ca9ba10-f45f-435a-b39c-519d251e9085
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688125(v=OCS.15)
ms:contentKeyID: 49733724
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4766d2b05cef89ab29b9c303c5ba1ec456843669
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835590"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-a-location-policy-in-lync-server-2013"></a>Eliminar una directiva de ubicación en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-10_

En Lync Server 2013, puede usar la Directiva de ubicación para aplicar la configuración relacionada con la funcionalidad mejorada de 9-1-1 (E9-1-1) y la configuración de ubicación de los usuarios o los contactos. La Directiva de ubicación determina si un usuario está habilitado para E9-1-1 y, si es así, cuál es el comportamiento de una llamada de emergencia. Por ejemplo, puede usar la política de ubicación para definir qué número constituye una llamada de emergencia (por ejemplo, 911 en los Estados Unidos), si se debe notificar automáticamente la seguridad corporativa y cómo debe dirigirse la llamada.

Puede configurar directivas de ubicación desde el grupo **configuración de red** en el panel de control de Lync Server 2013. En el panel de control de Lync Server puede ver, crear, modificar o eliminar directivas de ubicación. Use los siguientes procedimientos para eliminar una política de ubicación. Para obtener más información sobre cómo crear o modificar directivas de ubicación, vea [crear o modificar una directiva de ubicación en Lync Server 2013](lync-server-2013-creating-or-modifying-a-location-policy.md).

<div>

## <a name="to-delete-a-location-policy"></a>Para eliminar una directiva de ubicación

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **configuración de red** y luego en **Directiva de ubicación**.

4.  En la página **Directiva de ubicación** , seleccione la Directiva de ubicación que desea eliminar.
    
    <div>
    

    > [!NOTE]  
    > Puede eliminar más de una política de ubicación a la vez. Para ello, presione CTRL y seleccione varias directivas mientras mantiene presionada la tecla CTRL. O bien, para seleccionar todas las directivas, haga clic en <STRONG>seleccionar todo</STRONG> en el menú <STRONG>edición</STRONG> .

    
    </div>

5.  En el menú **Editar** , haga clic en **eliminar**.

6.  Haga clic en **Aceptar**.
    
    <div>
    

    > [!IMPORTANT]  
    > No se puede eliminar la Directiva de ubicación global. Si intenta eliminar la directiva global, recibirá un mensaje de advertencia y esa Directiva se restablecerá a sus valores predeterminados.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Vea también


[Crear o modificar una directiva de ubicación en Lync Server 2013](lync-server-2013-creating-or-modifying-a-location-policy.md)  
[Ver información de la Directiva de ubicación en Lync Server 2013](lync-server-2013-viewing-location-policy-information.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

