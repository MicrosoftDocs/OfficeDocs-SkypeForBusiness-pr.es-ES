---
title: Configurar las opciones globales de omisión de medios para usar información de sitio y región
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure media bypass global settings to use site and region information
ms:assetid: 0a21cdf1-f350-49da-b346-70806f256bea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398150(v=OCS.15)
ms:contentKeyID: 48183360
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2e730b1e44bbe6e6fbec4d84a2c81ce474cff693
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507627"
---
# <a name="configure-media-bypass-global-settings-in-lync-server-2013-to-use-site-and-region-information"></a>Configurar las opciones globales de omisión de medios en Lync Server 2013 para usar la información de sitio y región

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-21_

<div>


> [!NOTE]
> En este tema se asume que ya ha configurado el desvío de medios para todas las conexiones basadas en troncos desde el servidor de mediación a un servidor del mismo nivel (una puerta de enlace de la red telefónica conmutada (RTC), un sistema IP-PBX, o un controlador de borde de sesión (SBC) en un proveedor de servicios de telefonía por Internet (ITSP)) para un servicio o sitio específico para el que desea que los medios se desvíen del servidor de mediación.<BR>En este tema también se da por hecho que se han definido todos los sitios centrales y los sitios de sucursal en el generador de topologías de forma que coincidan con la región de red, el sitio de red y la configuración de subred que haya llevado a cabo siguiendo los pasos descritos en <A href="lync-server-2013-create-or-modify-a-network-region.md">Create or Modify a Network region in Lync server 2013</A>, <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or 2013 Modify</A>a Network site <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">in Lync Server 2013</A> Si no coinciden, el desvío de medios no se realizará.



</div>

Además de la habilitación del desvío de medios para conexiones individuales basadas en troncos asociadas a un servidor del mismo nivel, también deberá configurar opciones globales. Si usa los pasos que se muestran en este tema para configurar las opciones globales para el desvío de medios, se asume que una de las siguientes situaciones, o ambas, repercutirán en su configuración:

  - *No* tiene buena conectividad entre los extremos de Lync Server y los homólogos para los que configuró el desvío de medios en la conexión troncal.

  - El control de admisión de llamadas (CAC) para la administración del ancho de banda está habilitado.
    
    <div>
    

    > [!NOTE]
    > Para obtener más información acerca de las consideraciones para el control de admisión de llamadas y el desvío de medios, consulte la sección "control de admisión de llamadas de conexiones RTC" en servidor de omisión y mediación de <A href="lync-server-2013-media-bypass-and-mediation-server.md">medios en Lync Server 2013</A> en la documentación referente a la planeación.

    
    </div>

La información de región de red y sitio de red se comparte entre las características de Enterprise Voice avanzadas del control de admisión de llamadas y el desvío de medios cuando ambos están habilitados. Por consiguiente, si ya ha configurado el control de admisión de llamadas, no es necesario que realice el siguiente procedimiento para editar la información de región y sitio específica para el desvío de medios. Siga los pasos de este procedimiento si todavía no ha configurado los sitios y regiones de red para el control de admisión de llamadas y desea cambiar las opciones del desvío de medios.

O bien, siga estos pasos si desea usar la información de sitio y región al tomar la decisión de desvío, pero no pretende habilitar el control de admisión de llamadas. En este caso, los vínculos restringidos de ancho de banda tendrán que representarse mediante directivas entre sitios de red, tal y como se describe en [Create Network intersite policies in Lync Server 2013](lync-server-2013-create-network-intersite-policies.md). En este caso, las restricciones del ancho de banda real no son tan importantes, ya que no se ha habilitado el control de admisión de llamadas. En su lugar, se usan estos vínculos para que las subredes de división especifiquen cuáles son las que no presentan límites de ancho de banda y pueden usar, por consiguiente, el desvío de medios. Tenga en cuenta que esto también es posible cuando se ha habilitado tanto el control de admisión de llamadas como el desvío de medios.

Además, para que el desvío funcione correctamente, debe existir coherencia entre un sitio definido en el generador de topologías y, como se define al configurar regiones de red y sitios de red. Por ejemplo, si tiene un sitio de sucursal que ha definido en el generador de topologías que tiene solo una puerta de enlace RTC implementada, dicho sitio de sucursal debe configurarse con una directiva de telefonía IP empresarial que permita a los usuarios de sitios de sucursal tener sus llamadas RTC enrutadas a través de la puerta de enlace RTC en el sitio de sucursal.

<div>

## <a name="to-configure-site-and-region-information-for-media-bypass"></a>Configurar la información de sitio y región para el desvío de medios

1.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

2.  En la barra de navegación izquierda, haga clic en **Configuración de red**.

3.  Haga doble clic en la configuración **Global** de la tabla.

4.  En la página **Editar configuración global**, seleccione la casilla **Habilitar desvío de medios**.

5.  Haga clic en **Usar la configuración de sitios y regiones**.

6.  Si es necesario, seleccione la casilla **Habilitar desvío para sitios sin asignar**.
    
    <div>
    

    > [!NOTE]
    > Seleccione esta casilla solamente si dispone de uno o más sitios grandes asociados a la misma región que no tenga restricciones de ancho de banda (por ejemplo, un sitio central grande) y si dispone también de algunas sucursales asociadas con la misma región que no tienen restricciones de ancho de banda. Cuando habilita el desvío para sitios sin asignar, la configuración se simplifica ya que solo especifica subredes asociadas con las sucursales, en lugar de tener que especificar todas las subredes asociadas a todos los sitios. Se recomienda no activar esta casilla si se ha habilitado el control de admisión de llamadas.

    
    </div>

7.  Haga clic en **Confirmar**.

A continuación, agregue subredes al sitio de red, como se describe en [asociar subredes con sitios de red para el desvío de medios en Lync Server 2013](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md). (Los procedimientos reales para la Asociación de subredes con sitios de red se describen en [asociar una subred con un sitio de red en Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md)). Una vez que haya asociado todas las subredes a los sitios de red, se completará la implementación de la omisión de medios.

<div>


> [!IMPORTANT]
> Si todavía no ha creado regiones de red y sitios de red, deberá crearlos en primer lugar para poder continuar con la implementación del desvío de medios. Para obtener más información, consulte <A href="lync-server-2013-create-or-modify-a-network-region.md">crear o modificar una región de red en Lync server 2013</A> y <A href="lync-server-2013-create-or-modify-a-network-site.md">crear o modificar un sitio de red en Lync Server 2013</A>.



</div>

</div>

<div>

## <a name="see-also"></a>Consulte también


[Asociar subredes con sitios de red para el desvío de medios en Lync Server 2013](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

