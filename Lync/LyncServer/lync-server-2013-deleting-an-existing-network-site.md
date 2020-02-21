---
title: 'Lync Server 2013: eliminar un sitio de red existente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting an existing network site
ms:assetid: 2762149b-3572-4513-b838-beda7fa9e81e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688001(v=OCS.15)
ms:contentKeyID: 49733589
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7b9db3328ef79dcbbd95592a7bb3149c3d6f64a7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206976"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deleting-an-existing-network-site-in-lync-server-2013"></a>Eliminación de un sitio de red existente en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

Los sitios de red son las oficinas o ubicaciones configuradas dentro de cada región de una implementación de Enhanced 9-1-1 o control de admisión de llamadas (CAC). Puede usar el panel de control de Lync Server 2013 para configurar sitios y asociarlos con regiones. Por ejemplo, una región de red para Norteamérica se podría asociar con sitios de red como Chicago, Redmond y Vancouver. Debe crearse un sitio de red CAC para cada sitio de una organización, incluso aunque no tenga limitaciones de ancho de banda. En el panel de control de Lync Server, puede crear, modificar y eliminar sitios de red. Utilice el procedimiento siguiente para eliminar un sitio de red existente. Para obtener información detallada sobre cómo crear o modificar sitios de red, vea [crear o modificar sitios de red en Lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md)

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

</div>

<span> </span>

</div>

</div>

</div>

