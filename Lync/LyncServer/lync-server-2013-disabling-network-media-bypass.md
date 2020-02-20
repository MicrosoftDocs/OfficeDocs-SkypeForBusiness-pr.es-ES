---
title: 'Lync Server 2013: deshabilitar el desvío de medios de red'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disabling network media bypass
ms:assetid: 936d2678-d712-4589-b172-b5793013652f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688141(v=OCS.15)
ms:contentKeyID: 49733741
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ee2ef091b9288406285de099cc0aa427feb008d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151652"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="disabling-network-media-bypass-in-lync-server-2013"></a>Deshabilitar el desvío de medios de red en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-15_

La configuración del desvío de medios se aplica globalmente en una implementación de Microsoft Lync Server 2013. Con el desvío de medios, las llamadas pueden omitir el servidor de mediación. Para obtener información detallada sobre Cuándo usar la omisión de medios, consulte [planeación de la omisión de medios en Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) en la sección planeación. Puede deshabilitar la omisión de medios en el panel de control de Lync Server. Para obtener más información sobre cómo habilitar y configurar la omisión de datos, consulte [Habilitar el desvío de medios de red en Lync Server 2013](lync-server-2013-enabling-network-media-bypass.md)

<div>

## <a name="to-disable-media-bypass"></a>Para deshabilitar el desvío de medios

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Configuración de red** y, a continuación, en **Global**.

4.  En la página **Global**, haga clic en la configuración **Global**. En todos los casos hay solo una configuración y siempre se llama Global.

5.  En el menú **Editar**, haga clic en **Ver detalles**.

6.  En la página  **Editar configuración global **, desactive la casilla  **Habilitar desvío de medios **.

7.  Haga clic en  **Confirmar ** para guardar los cambios.

</div>

<div>

## <a name="see-also"></a>Vea también


[Habilitación del desvío de medios de red en Lync Server 2013](lync-server-2013-enabling-network-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

