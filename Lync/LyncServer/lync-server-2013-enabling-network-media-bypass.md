---
title: 'Lync Server 2013: habilitar el desvío de medios de red'
description: 'Lync Server 2013: habilitar el desvío de medios de red.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling network media bypass
ms:assetid: 95c4fa06-49d3-41ac-acdc-7dcda66e5508
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182552(v=OCS.15)
ms:contentKeyID: 48184846
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1218376903aa42e1ea55205e3a9e8d16aade9a3a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546556"
---
# <a name="enabling-network-media-bypass-in-lync-server-2013"></a>Habilitación del desvío de medios de red en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

La configuración del desvío de medios se aplica globalmente en una implementación de Microsoft Lync Server 2013. Con el desvío de medios, las llamadas pueden omitir el servidor de mediación. Para obtener información detallada sobre Cuándo usar la omisión de medios, consulte [planeación de la omisión de medios en Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) en la sección planeación.

Puede habilitar y configurar la omisión de medios desde el panel de control de Lync Server.

<div>

## <a name="to-enable-and-configure-media-bypass"></a>Para habilitar y configurar el desvío de medios

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Configuración de red** y, a continuación, en **Global**.

4.  En la página **Global**, haga clic en la configuración **Global**. En todos los casos hay solo una configuración y siempre se llama Global.

5.  En el menú **Editar**, haga clic en **Ver detalles**.

6.  En la página **Editar configuración global**, haga clic en la casilla **Habilitar desvío de medios**.

7.  Seleccione una de las siguientes opciones:
    
      - **Omitir siempre**     Seleccione esta opción para intentar la omisión de medios en todas las llamadas. Esta opción no estará disponible si se ha habilitado el control de admisión de llamadas (CAC). Si el CAC no está habilitado, seleccione esta opción en las situaciones siguientes:
        
          - No es necesario controlar el ancho de banda.
        
          - No se necesita una configuración específica para saber cuándo debe producirse el desvío.
        
          - Existe plena conectividad entre las puertas de enlace y los clientes.
    
      - **Usar configuración**     de sitios y regiones Si el CAC está habilitado, esta opción está seleccionada de forma predeterminada y no se puede cambiar. Cuando se selecciona esta opción, los sitios y regiones de configuración de red se usarán para determinar cuando resulta posible el desvío de medios. Si selecciona esta opción, puede optar por habilitar el desvío para sitios que no se han asignado. Haga clic en la casilla **Habilitar desvío para sitios sin asignar** solamente si dispone de uno o más sitios grandes asociados con la misma región que no tenga restricciones de ancho de banda (por ejemplo, un sitio central grande) y si dispone también de algunos sitios de sucursal asociados con la misma región que no tienen restricciones de ancho de banda. Cuando habilita el desvío para sitios sin asignar, la configuración se simplifica porque solo especifica subredes asociadas con los sitios de sucursal en lugar de tener que especificar todas las subredes asociadas a todos los sitios. Se recomienda no seleccionar la casilla **Habilitar desvío para sitios sin asignar** si se ha habilitado el CAC.

8.  Haga clic en **Confirmar** para guardar los cambios.

</div>

<div>

## <a name="see-also"></a>Consulte también


[Deshabilitar el desvío de medios de red en Lync Server 2013](lync-server-2013-disabling-network-media-bypass.md)  


[Opciones de omisión de medios globales en Lync Server 2013](lync-server-2013-global-media-bypass-options.md)  


[Planeación de la omisión de medios en Lync Server 2013](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

