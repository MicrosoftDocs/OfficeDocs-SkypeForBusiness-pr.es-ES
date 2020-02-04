---
title: Configurar las opciones globales del desvío de medios para usar información de sitio y región
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
ms.openlocfilehash: ac820c444f894aabf060c06d6f034f7d92b696c2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757754"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-media-bypass-global-settings-in-lync-server-2013-to-use-site-and-region-information"></a>Configure media bypass global settings in Lync Server 2013 to use site and region information

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-21_

<div>


> [!NOTE]
> En este tema se supone que ya ha configurado la omisión de medios para las conexiones troncales desde el servidor de mediación a un interlocutor (una puerta de enlace de red de telefonía pública conmutada (RTC), una IP-PBX o un controlador de borde de sesión (SBC) en un servicio de telefonía por Internet Proveedor (ITSP) para un sitio o servicio específico para el cual quiere que los medios omitan el servidor de mediación.<BR>En este tema también se da por sentado que ha definido todos los sitios centrales y sucursales en el generador de topologías de forma que coincidan con la región de red, el sitio de red y la configuración de subred que ha realizado según los pasos de <A href="lync-server-2013-create-or-modify-a-network-region.md">crear o modificar una región de red en Lync server 2013</A>, <A href="lync-server-2013-create-or-modify-a-network-site.md">crear o modificar un sitio de red en Lync Server 2013</A>y <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">asociar una 2013 subred</A> Si no coinciden, la omisión de elementos multimedia no se realizará correctamente.



</div>

Además de habilitar la omisión de medios para conexiones troncales individuales asociadas con un mismo nivel, también debe establecer la configuración global. Si usa los pasos de este tema para configurar las opciones globales de omisión de medios, se supone que una o ambas de las siguientes situaciones afectan a la configuración:

  - *No* tiene buena conectividad entre los puntos de conexión de Lync Server y los elementos del mismo nivel para los que configuró el bypass de medios en la conexión troncal.

  - Control de admisión de llamadas (CAC) para la administración del ancho de banda está habilitado.
    
    <div>
    

    > [!NOTE]
    > Para obtener más información sobre las consideraciones para el control de admisión de llamadas y para la omisión de medios, consulte la sección "control de admisión de conexiones RTC" en servidor de omisión y mediación de <A href="lync-server-2013-media-bypass-and-mediation-server.md">multimedia en Lync server 2013</A> en la documentación de planeación.

    
    </div>

La información de región de red y sitio de red se comparte entre las características de Enterprise Voice avanzadas del control de admisión de llamadas y el desvío de medios cuando ambos están habilitados. Por consiguiente, si ya ha configurado el control de admisión de llamadas, no es necesario que realice el siguiente procedimiento para editar la información de región y sitio específica para la omisión de medios. Siga los pasos de este procedimiento si todavía no ha configurado los sitios y regiones de red para el control de admisión de llamadas y desea cambiar las opciones del omisión de medios.

O bien, siga estos pasos si desea usar la información del sitio y de la región para tomar la decisión de omisión, pero no tiene la intención de habilitar el control de admisión de llamadas. En tal caso, los vínculos con restricciones de ancho de banda seguirán representados mediante directivas de intersitio de red, tal y como se describe en [crear directivas entre sitios de red en Lync Server 2013](lync-server-2013-create-network-intersite-policies.md). Las restricciones de ancho de banda reales no son tan importantes en este caso, porque el control de admisión de llamadas no se ha habilitado. En su lugar, estos vínculos se usan para particionar subredes para especificar aquellas que no tienen límites de ancho de banda y que pueden, por consiguiente, emplear omisión de medios. Tenga en cuenta que esto también es cierto cuando ambos están habilitados el control de admisión de llamadas y los medios.

Además, para que el omisión funcione correctamente, es necesario que haya coherencia entre un sitio definido en el generador de topologías y que se defina al configurar las regiones de red y los sitios de red. Por ejemplo, si tiene un sitio de sucursal que ha definido en el generador de topología y tiene una puerta de enlace RTC implementada, ese sitio de sucursal debe estar configurado con una directiva de telefonía IP empresarial que permita a los usuarios de la sucursal enrutar las llamadas RTC a través de la RTC. puerta de enlace en el sitio de la sucursal.

<div>

## <a name="to-configure-site-and-region-information-for-media-bypass"></a>Configurar la información de sitio y región para el desvío de medios

1.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

2.  En la barra de navegación izquierda, haga clic en **Configuración de red**.

3.  Haga doble clic en la configuración **Global** de la tabla.

4.  En la página **Editar configuración global**, seleccione la casilla **Habilitar omisión de medios**.

5.  Haga clic en **Usar la configuración de sitios y regiones**.

6.  Si es necesario, seleccione la casilla **Habilitar omisión para sitios sin asignar**.
    
    <div>
    

    > [!NOTE]
    > Seleccione esta casilla solamente si dispone de uno o más sitios grandes asociados a la misma región que no tengan restricciones de ancho de banda (por ejemplo, un sitio central grande) y si dispone también de algunas sucursales asociadas con la misma región que no tienen restricciones de ancho de banda. Cuando habilita la omisión para sitios sin asignar, la configuración se simplifica ya que solo especifica subredes asociadas con las sucursales, en lugar de tener que especificar todas las subredes asociadas a todos los sitios. Se recomienda no activar esta casilla si se ha habilitado el control de admisión de llamadas.

    
    </div>

7.  Haga clic en **Confirmar**.

A continuación, agregue subredes al sitio de red, como se describe en [asociar subredes con sitios de red para evitar contenido multimedia en Lync Server 2013](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md). (Los procedimientos reales para asociar subredes con sitios de red se describen en [asociar una subred con un sitio de red en Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md)). Una vez que haya asociado todas las subredes a los sitios de red, se completará la implementación de omisión de medios.

<div>


> [!IMPORTANT]
> Si todavía no ha creado regiones de red y sitios de red, deberá crearlos en primer lugar para poder continuar con la implementación de la omisión de medios. Para obtener más información, vea <A href="lync-server-2013-create-or-modify-a-network-region.md">crear o modificar una región de red en Lync server 2013</A> y <A href="lync-server-2013-create-or-modify-a-network-site.md">crear o modificar un sitio de red en Lync Server 2013</A>.



</div>

</div>

<div>

## <a name="see-also"></a>Vea también


[Asociar subredes con sitios de red para evitar contenido multimedia en Lync Server 2013](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

