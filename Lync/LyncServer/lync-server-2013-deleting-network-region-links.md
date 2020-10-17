---
title: 'Lync Server 2013: eliminación de vínculos de región de red'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting network region links
ms:assetid: 839273cd-d23f-4b38-84e6-d2dc972f49cd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688114(v=OCS.15)
ms:contentKeyID: 49733712
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c467d499b0a0c9a3e85884927aed8ab819467d61
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525347"
---
# <a name="deleting-network-region-links-in-lync-server-2013"></a>Eliminación de vínculos de regiones de red en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

Puede configurar vínculos entre dos regiones de red como parte del control de admisión de llamadas. Las regiones dentro de una red están vinculadas con una conectividad física de red de área extensa (WAN). Puede usar el panel de control de Lync Server para eliminar un vínculo existente entre dos regiones de red. Para obtener información detallada sobre cómo crear o modificar el vínculo de región de red, consulte [configuración de vínculos de región de red en Lync Server 2013](lync-server-2013-configuring-network-region-links.md)

<div>

## <a name="to-delete-a-network-region-link"></a>Para eliminar un vínculo de región de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Configuración de red** y luego en **Vínculo de región**.

4.  En la página **Vínculo de región**, haga clic en el vínculo de región que desea eliminar.
    
    <div>
    

    > [!NOTE]  
    > Se pueden eliminar varios vínculos de región a la vez. Para hacerlo, presione CTRL y seleccione varios vínculos de regiones mientras mantiene presionada la tecla CTRL. O, para seleccionar todos los vínculos de región, haga clic en <STRONG>Seleccionar todo</STRONG> en el menú <STRONG>Editar</STRONG>.

    
    </div>

5.  En el menú **Editar** seleccione **Eliminar**.

6.  Haga clic en **Aceptar**.

</div>

<div>

## <a name="see-also"></a>Consulte también


[Configuración de vínculos de región de red en Lync Server 2013](lync-server-2013-configuring-network-region-links.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

