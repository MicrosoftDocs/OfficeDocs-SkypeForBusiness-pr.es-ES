---
title: 'Lync Server 2013: eliminar vínculos de la región de red'
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
ms.openlocfilehash: 158537f2473beba686daa51c5384a45f01432320
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763028"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-network-region-links-in-lync-server-2013"></a>Eliminar vínculos de regiones de red en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

Puede configurar vínculos entre dos regiones de red como parte de control de admisión de llamadas (CAC). Las regiones dentro de una red están vinculadas a través de la conectividad de red de área extensa (WAN). Puede usar el panel de control de Lync Server para eliminar un vínculo existente entre dos regiones de red. Para obtener más información sobre cómo crear o modificar el vínculo región de red, consulte [configuración de vínculos de regiones de red en Lync Server 2013](lync-server-2013-configuring-network-region-links.md)

<div>

## <a name="to-delete-a-network-region-link"></a>Para eliminar un vínculo a una región de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **configuración de red** y, a continuación, en **vínculo de región**.

4.  En la página vínculo de la **región** , haga clic en el vínculo de la región que desea eliminar.
    
    <div>
    

    > [!NOTE]  
    > Puedes eliminar más de un vínculo de región a la vez. Para ello, presione CTRL y seleccione varios vínculos de región mientras mantiene presionada la tecla CTRL. O bien, para seleccionar todos los vínculos de la región, haga clic en <STRONG>seleccionar todo</STRONG> en el menú <STRONG>edición</STRONG> .

    
    </div>

5.  En el menú **Editar** , seleccione **eliminar**.

6.  Haga clic en **Aceptar**.

</div>

<div>

## <a name="see-also"></a>Vea también


[Configuración de vínculos de regiones de red en Lync Server 2013](lync-server-2013-configuring-network-region-links.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

