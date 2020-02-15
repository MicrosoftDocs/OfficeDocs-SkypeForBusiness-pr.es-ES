---
title: Requisitos del equilibrador de carga de hardware de Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardware load balancer requirements
ms:assetid: 32891268-2059-43d0-adf4-af4ff1e9ce66
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ656815(v=OCS.15)
ms:contentKeyID: 49287208
ms.date: 05/11/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c89c600c822bc4e830bf60ed8131f747172018e2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030323"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardware-load-balancer-requirements-for-lync-server-2013"></a>Requisitos del equilibrador de carga de hardware para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2015-05-11_

La topología perimetral consolidada escalada 2013 de Lync Server está optimizada para el equilibrio de carga de DNS para implementaciones nuevas que se federan principalmente con otras organizaciones que usan Lync Server. En caso de que se necesite una gran disponibilidad en cualquiera de los siguientes escenarios, se deberá usar un equilibrador de carga de hardware en grupos de servidores perimetrales:

  - Federación con organizaciones que usan Office Communications Server 2007 R2 u Office Communications Server 2007

  - Mensajería unificada de Exchange para usuarios remotos con Exchange UM antes de Exchange 2010 con SP1

  - Conectividad con usuarios de mensajería instantánea pública

<div>


> [!IMPORTANT]  
> No se admite el uso del equilibrio de carga de DNS en una interfaz y del equilibrio de carga de hardware en otra. Debe utilizar el equilibrio de carga de hardware o de DNS en ambas interfaces.



</div>

<div>


> [!NOTE]  
> Si usa un equilibrador de carga de hardware, el equilibrador de carga que se haya implementado para las conexiones con la red interna deberá configurarse de modo que solo equilibre la carga del tráfico de los servidores que ejecuten el servicio perimetral de acceso y el servicio perimetral A/V. No puede equilibrar la carga del tráfico al servicio perimetral de conferencia web interno o al servicio proxy XMPP interno.



</div>

<div>


> [!NOTE]  
> La NAT de Direct Server Return (DSR) no es compatible con Lync Server 2013.



</div>

Para determinar si el equilibrador de carga de hardware admite las características necesarias para Lync Server 2013, consulte "Lync Server 2010 load balancer Partners" [http://go.microsoft.com/fwlink/p/?linkId=202452](http://go.microsoft.com/fwlink/p/?linkid=202452)en.

<div>

## <a name="hardware-load-balancer-requirements-for-edge-servers-running-the-av-edge-service"></a>Requisitos de equilibrador de carga de hardware para servidores perimetrales que ejecutan el servicio perimetral A/V

A continuación, se indican los requisitos del equilibrador de carga de hardware para los servidores perimetrales que ejecutan el servicio perimetral A/V:

  - Inhabilitar la aplicación del algoritmo de Nagle TCP para los puertos 443 internos y externos. La aplicación del algoritmo de Nagle es la combinación de varios paquetes pequeños en un único paquete más grande para obtener una transmisión más eficiente.

  - Inhabilitar la aplicación del algoritmo de Nagle TCP para el intervalo de puertos externos de 50.000 a 59.999.

  - No usar NAT en el firewall interno o externo.

  - La interfaz interna del servidor perimetral y la interfaz externa del servidor perimetral deben estar en redes diferentes, y debe inhabilitarse el enrutamiento entre ellas.

  - La interfaz externa del servidor perimetral que ejecuta el servicio perimetral A/V debe usar direcciones IP enrutables públicamente y no NAT o traducción de puerto en ninguna de las direcciones IP externas del servidor perimetral.

</div>

<div>

## <a name="hardware-load-balancer-requirements"></a>Requisitos del equilibrador de carga de hardware

Los requisitos de afinidad basada en cookies se reducen en gran medida en Lync Server 2013 para los servicios Web. Si va a implementar Lync Server 2013 y no va a conservar ningún servidor front-end de Lync Server 2010 o grupo de servidores front-end, no necesita persistencia basada en cookies. Sin embargo, si va a conservar de forma temporal o permanente los servidores front-end de Lync Server 2010 o los grupos de servidores front-end, seguirá usando la persistencia basada en cookies mientras se implementa y configura para Lync Server 2010.

<div>


> [!NOTE]  
> <STRONG>La utilización de la afinidad basada en cookies pese a que su implementación no la necesite</STRONG> no tiene repercusiones.



</div>

Para las implementaciones que **no utilicen** la afinidad basada en cookies:

  - En la regla de publicación del proxy inverso para el puerto 4443, establezca **Transferir encabezado de host** en True. Esto garantizará que se transfiera la URL original.

Para las implementaciones que **utilicen** la afinidad basada en cookies:

  - En la regla de publicación del proxy inverso para el puerto 4443, establezca **Transferir encabezado de host** en True. Esto garantizará que se transfiera la URL original.

  - La cookie de equilibrio de carga de hardware NO DEBE estar marcada como httpOnly

  - La cookie de equilibrio de carga de hardware NO DEBE tener tiempo de expiración

  - La cookie de equilibrio de carga de hardware DEBE tener el nombre **MS-WSMAN** (este es el esperado por los servicios web y no puede modificarse)

  - La cookie de equilibrio de carga de hardware DEBE estar establecida en cada respuesta HTTP para la que la solicitud HTTP entrante no tenía una cookie, independientemente de si una respuesta HTTP anterior en la misma conexión TCP ya había obtenido una cookie. Si el equilibrador de carga optimiza la inserción de cookies para que solo ocurra una vez por conexión TCP, la optimización NO debe usarse.

<div>


> [!NOTE]  
> Las configuraciones típicas del equilibrador de carga de hardware usan la afinidad de dirección de origen y una duración de la sesión TCP mín. TCP, que es adecuada para clientes de Lync Server y Lync 2013 porque el estado de sesión se mantiene a través del uso del cliente o la interacción de la aplicación.



</div>

Si se implementan dispositivos móviles, el equilibrador de carga de hardware debe poder equilibrar la carga de una solicitud individual dentro de una sesión TCP (de hecho, debe poder equilibrar la carga de una solicitud individual basada en la dirección IP de destino).

<div>


> [!WARNING]  
> Los equilibradores de carga de hardware F5 tienen una característica llamada OneConnect que asegura que cada solicitud dentro de una conexión TCP tenga carga equilibrada individualmente. Si va a implementar dispositivos móviles, asegúrese de que su proveedor del equilibrador de carga de hardware admita la misma funcionalidad. Las últimas aplicaciones móviles que utilizan el sistema Apple iOS requieren el uso seguridad de capa de transporte (TLS), versión 1.2. F5 proporciona opciones de configuración específicas para este sistema.<BR>Para obtener más información sobre los equilibradores de carga de hardware de terceros, consulte<A href="http://go.microsoft.com/fwlink/p/?linkid=230700">http://go.microsoft.com/fwlink/p/?linkId=230700</A>



</div>

A continuación se muestran los requisitos del equilibrador de carga de hardware para servicios web de grupo de directores y de servidores front-end:

  - Para VIP de servicios Web internos, establezca\_la persistencia de la dirección de origen (puerto interno 80, 443) en el equilibrador de carga de hardware. Para Lync Server 2013, la\_persistencia de la dirección de origen significa que siempre se envían varias conexiones procedentes de una dirección IP a un servidor para mantener el estado de la sesión.

  - Use un tiempo de espera de inactividad TCP de 1.800 segundos.

  - En el firewall entre el proxy inverso y el equilibrador de carga de hardware del grupo de servidores del próximo salto, cree una regla que permita el tráfico https: en el puerto 4443, del proxy inverso al equilibrador de carga de hardware. El equilibrador de carga de hardware debe configurarse de modo que escuche los puertos 80, 443 y 4443.

<div>


> [!IMPORTANT]  
> Para obtener más información sobre la configuración del equilibrador de carga de hardware, revise <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">Resumen de puertos-servidor perimetral consolidado ampliado con equilibradores de carga de hardware en Lync Server 2013</A>.



</div>

</div>

<div>

## <a name="summary-of-hardware-load-balancer-affinity-requirements"></a>Resumen de requisitos de afinidad del equilibrador de carga de hardware


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Ubicación de cliente/usuario</th>
<th>Requisitos de afinidad del FQDN de servicios web externos</th>
<th>Requisitos de afinidad del FQDN de servicios web internos</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Web App (usuarios internos y externos)</p>
<p>Dispositivo móvil (usuarios internos y externos)</p></td>
<td><p>Sin afinidad</p></td>
<td><p>Afinidad de direcciones de origen</p></td>
</tr>
<tr class="even">
<td><p>Lync Web App (solo usuarios externos)</p>
<p>Dispositivo móvil (usuarios internos y externos)</p></td>
<td><p>Sin afinidad</p></td>
<td><p>Afinidad de direcciones de origen</p></td>
</tr>
<tr class="odd">
<td><p>Lync Web App (solo usuarios internos)</p>
<p>Dispositivo móvil (no implementado)</p></td>
<td><p>Sin afinidad</p></td>
<td><p>Afinidad de direcciones de origen</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="port-monitoring-for-hardware-load-balancers"></a>Supervisión de puertos para los equilibradores de carga de hardware

Es necesario definir la supervisión de puertos en los equilibradores de carga de hardware para determinar cuándo determinados servicios dejan de estar disponibles debido a errores de comunicaciones o de hardware. Por ejemplo, si el servicio de servidor front-end (RTCSRV) se detiene debido a un error en el servidor front-end o en el grupo de servidores front-end, la supervisión de HLB también debe dejar de recibir tráfico en los servicios Web. La supervisión de puertos en el equilibrador de carga de hardware debe implementarse para supervisar lo siguiente:

### <a name="front-end-server-user-pool--hlb-internal-interface"></a>Grupo de usuarios del servidor front-end – interfaz interna de HLB

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>Puerto/IP virtual</th>
<th>Puerto de nodo</th>
<th>Monitor/máquina de nodo</th>
<th>Perfil de persistencia</th>
<th>Notas</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&lt;Web&gt;-int_mco_443_vs de grupo</p>
<p>443</p></td>
<td><p>443</p></td>
<td><p>Front-end</p>
<p>5061</p></td>
<td><p>Origen</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="even">
<td><p>&lt;Web&gt;-int_mco_80_vs de grupo</p>
<p>80</p></td>
<td><p>80</p></td>
<td><p>Front-end</p>
<p>5061</p></td>
<td><p>Origen</p></td>
<td><p>HTTP</p></td>
</tr>
</tbody>
</table>


### <a name="front-end-server-user-pool--hlb-external-interface"></a>Grupo de usuarios del servidor front-end: interfaz externa de HLB

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>Puerto/IP virtual</th>
<th>Puerto de nodo</th>
<th>Monitor/máquina de nodo</th>
<th>Perfil de persistencia</th>
<th>Notas</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&lt;web_mco_443_vs&gt;de grupo</p>
<p>443</p></td>
<td><p>4443</p></td>
<td><p>Front-end</p>
<p>5061</p></td>
<td><p>Ninguno</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="even">
<td><p>&lt;web_mco_80_vs&gt;de grupo</p>
<p>80</p></td>
<td><p>8080</p></td>
<td><p>Front-end</p>
<p>5061</p></td>
<td><p>Ninguno</p></td>
<td><p>HTTP</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

