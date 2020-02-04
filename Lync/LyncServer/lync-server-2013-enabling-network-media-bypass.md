---
title: 'Lync Server 2013: habilitar la omisión de medios de red'
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
ms.openlocfilehash: 4e0b5e7b060d056a785e80fdf29ded718d120bc1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735800"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-network-media-bypass-in-lync-server-2013"></a>Habilitar el omisión de medios de red en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

La configuración de omisión de medios se aplica globalmente en una implementación de Microsoft Lync Server 2013. La omisión de medios permite que las llamadas omitan el servidor de mediación. Para obtener información sobre Cuándo usar la omisión de medios, consulte [planificación de la omisión de medios en Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) en la sección planificación.

Puede habilitar y configurar la omisión de medios en el panel de control de Lync Server.

<div>

## <a name="to-enable-and-configure-media-bypass"></a>Para habilitar y configurar la omisión de medios

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **configuración de red** y, después, en **global**.

4.  En la página **global** , haga clic en la configuración **global** . Siempre hay una sola configuración y siempre se denomina global.

5.  En el menú **Editar** , haga clic en **Ver detalles**.

6.  En la página **Editar configuración global** , haga clic en la casilla de verificación **Habilitar omisión de medios** .

7.  Seleccione una de las siguientes opciones:
    
      - **Omitir siempre seleccione**   esta opción para intentar la omisión de medios en todas las llamadas. Esta opción no estará disponible si el control de admisión de llamada (CAC) está habilitado. Si CAC no está habilitado, seleccione esta opción en las siguientes situaciones:
        
          - No es necesario el control del ancho de banda.
        
          - No es necesario que la configuración específica determine Cuándo debe pasar el bypass.
        
          - Hay conectividad completa entre las puertas de enlace y los clientes.
    
      - **Usar la configuración**   de sitios y regiones si CAC está habilitado, esta opción está seleccionada de forma predeterminada y no se puede cambiar. Cuando esta opción está seleccionada, se usarán regiones y sitios de configuración de red para determinar cuándo es posible la omisión de medios. Si selecciona esta opción, puede habilitar el omisión de sitios que no están asignados. Haga clic en la casilla **de verificación Habilitar el omisión de sitios no asignados** solo si tiene uno o varios sitios grandes asociados a la misma región que no tienen restricciones de ancho de banda (por ejemplo, un sitio central grande) y también tiene algunos sitios de rama asociados a la misma región que tienen restricciones de ancho de banda. Cuando habilita el bypass para sitios no asignados, la configuración se simplifica porque especifica solo las subredes asociadas a las sucursales en lugar de tener que especificar todas las subredes asociadas a todos los sitios. Le recomendamos que no active la casilla **Habilitar omisión para sitios no asignados** si CAC está habilitado.

8.  Haga clic en **confirmar** para guardar los cambios.

</div>

<div>

## <a name="see-also"></a>Vea también


[Deshabilitar la omisión de medios de red en Lync Server 2013](lync-server-2013-disabling-network-media-bypass.md)  


[Opciones de omisión de multimedia global en Lync Server 2013](lync-server-2013-global-media-bypass-options.md)  


[Planificar la omisión de medios en Lync Server 2013](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

