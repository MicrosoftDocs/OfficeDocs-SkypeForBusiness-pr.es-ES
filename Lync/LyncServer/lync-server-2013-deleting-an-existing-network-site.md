---
title: 'Lync Server 2013: eliminar un sitio de red existente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deleting an existing network site
ms:assetid: 2762149b-3572-4513-b838-beda7fa9e81e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688001(v=OCS.15)
ms:contentKeyID: 49733589
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 772d653e0bde803f47a5742a4f3824bdef01c3f1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835585"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-an-existing-network-site-in-lync-server-2013"></a>Eliminar un sitio de red existente en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

Los sitios de red son las oficinas o ubicaciones configuradas dentro de cada región de control de admisión de llamadas (CAC) o implementación mejorada de 9-1-1. Puede usar el panel de control de Lync Server 2013 para configurar sitios y asociarlos con regiones. Por ejemplo, una región de red para Norteamérica puede estar asociada a sitios de redes como Chicago, Redmond y Vancouver. Es necesario crear un sitio de red CAC para cada sitio dentro de una organización, incluso si ese sitio no tiene limitaciones de ancho de banda. En el panel de control de Lync Server puede crear, modificar y eliminar sitios de red. Use el siguiente procedimiento para eliminar un sitio de red existente. Para obtener detalles sobre cómo crear o modificar sitios de red, vea [crear o modificar sitios de red en Lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md)

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

</div>

<span> </span>

</div>

</div>

</div>

