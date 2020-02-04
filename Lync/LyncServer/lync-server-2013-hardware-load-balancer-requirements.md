---
title: 'Lync Server 2013: Requisitos del equilibrador de carga de hardware'
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
ms.openlocfilehash: 85ed4195d80ecc755faea74ddedb790c9f41ebfb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727910"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardware-load-balancer-requirements-for-lync-server-2013"></a>Requisitos del equilibrador de carga de hardware en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2015-05-11_

La topología de borde consolidado de Lync Server 2013 escalada está optimizada para el equilibrio de carga de DNS para implementaciones nuevas que se federan principalmente con otras organizaciones que usan Lync Server. Si se requiere una alta disponibilidad para cualquiera de los siguientes escenarios, se debe usar un equilibrador de carga de hardware en los grupos de servidores perimetrales para lo siguiente:

  - Federación con organizaciones que usan Office Communications Server 2007 R2 u Office Communications Server 2007

  - Mensajería unificada de Exchange para usuarios remotos que usan la mensajería unificada de Exchange antes de Exchange 2010 con SP1

  - Conectividad con usuarios de mensajería instantánea (MI) pública

<div>


> [!IMPORTANT]  
> No se admite el uso del equilibrio de carga de DNS en una interfaz y del equilibrio de carga de hardware en otra. Necesita utilizar el equilibrio de carga de hardware o de DNS en ambas interfaces.



</div>

<div>


> [!NOTE]  
> Si usa un equilibrador de carga de hardware, el equilibrador de carga que se haya implementado para las conexiones con la red interna necesitará configurarse para que solo equilibre la carga del tráfico de los servidores que ejecuten el servicio perimetral de acceso y el servicio perimetral A/V. No puede equilibrar la carga del tráfico al servicio perimetral de conferencia web interno o al servicio proxy XMPP interno.



</div>

<div>


> [!NOTE]  
> El NAT de Return de servidor directo (DSR) no es compatible con Lync Server 2013.



</div>

Para determinar si su equilibrador de carga de hardware admite las características necesarias para Lync Server 2013, consulte "Lync Server 2010 de equilibrador de carga [http://go.microsoft.com/fwlink/p/?linkId=202452](http://go.microsoft.com/fwlink/p/?linkid=202452)" en.

<div>

## <a name="hardware-load-balancer-requirements-for-edge-servers-running-the-av-edge-service"></a>Requisitos de equilibrador de carga de hardware para servidores perimetrales que ejecutan el servicio perimetral A/V

Estos son los requisitos del equilibrador de carga de hardware para los servidores perimetrales que ejecutan el servicio perimetral A/V:

  - Deshabilitar el algoritmo de Nagle de TCP para los puertos 443 internos y externos. El algoritmo de Nagle es el proceso de combinación de varios paquetes pequeños en un único paquete más grande para obtener una transmisión más eficiente.

  - Deshabilitar el algoritmo de Nagle de TCP para el intervalo de puertos externos de 50 000 a 59 999.

  - No utilizar NAT en el firewall interno o externo.

  - La interfaz interna de Edge debe estar en una red diferente a la de la interfaz externa del servidor perimetral y el enrutamiento entre ellas debe estar deshabilitado.

  - La interfaz externa del servidor perimetral que ejecuta el servicio de borde A/V debe usar direcciones IP enrutables públicamente y sin traducción de NAT o puerto en ninguna de las direcciones IP externas de Edge.

</div>

<div>

## <a name="hardware-load-balancer-requirements"></a>Requisitos del equilibrador de carga de hardware

Los requisitos de afinidad basados en cookies se reducen enormemente en Lync Server 2013 para servicios Web. Si implementa Lync Server 2013 y no va a conservar ninguno de los servidores front-end de Lync Server 2010 ni los grupos front-end, no necesita persistencia basada en cookies. Sin embargo, si conservará de forma temporal o permanente los servidores front-end de Lync Server 2010 o las agrupaciones front end, seguirá usando la persistencia basada en cookies a medida que se implemente y se configure para Lync Server 2010.

<div>


> [!NOTE]  
> <STRONG>La utilización de la afinidad basada en cookies pese a que su implementación no la necesite</STRONG> no tiene repercusiones.



</div>

Para las implementaciones que **no utilizarán** la afinidad basada en cookies:

  - En la regla de publicación del proxy inverso para el puerto 4443, establezca **Reenviar encabezado de host** en True. Esto garantizará que se reenviará la dirección URL original.

Para las implementaciones que **utilizarán** la afinidad basada en cookies:

  - En la regla de publicación del proxy inverso para el puerto 4443, establezca **Reenviar encabezado de host** en True. Esto garantizará que se reenviará la dirección URL original.

  - La cookie del equilibrador de carga de hardware NO NECESITA estar marcada como httpOnly

  - La cookie del equilibrador de carga de hardware NO NECESITA tener tiempo de expiración

  - La cookie del equilibrador de carga de hardware NECESITA tener el nombre **MS-WSMAN** (este es el valor esperado por los servicios web y no puede modificarse)

  - La cookie del equilibrador de carga de hardware NECESITA estar establecida en cada respuesta HTTP para la que la solicitud HTTP entrante no tenía una cookie, independientemente de si una respuesta HTTP anterior en la misma conexión TCP ya había obtenido una cookie. Si el equilibrador de carga optimiza la inserción de cookies para que solo ocurra una vez por conexión TCP, la optimización NO NECESITA usarse.

<div>


> [!NOTE]  
> Las configuraciones típicas de equilibrado de carga de hardware usan afinidad de dirección de origen y 20 minutos de duración de la sesión TCP, lo cual es adecuado para clientes de Lync Server y Lync 2013 porque se mantiene el estado de la sesión a través del uso del cliente o la interacción de la aplicación.



</div>

Si se implementan dispositivos móviles, es preciso que el equilibrador de carga de hardware pueda equilibrar la carga de una solicitud individual dentro de una sesión TCP (de hecho, necesita poder equilibrar la carga de una solicitud individual basada en la dirección IP de destino).

<div>


> [!WARNING]  
> Los equilibradores de carga de hardware F5 tienen una característica llamada OneConnect que asegura que cada solicitud dentro de una conexión TCP tenga carga equilibrada individualmente. Si va a implementar dispositivos móviles, asegúrese de que su proveedor del equilibrador de carga de hardware admita la misma función. Las últimas aplicaciones móviles que utilizan Apple iOS requieren la versión 1.2 de la seguridad de la capa de transporte (TLS). Para ellos, F5 proporciona una configuración específica.<BR>Para obtener detalles sobre los equilibradores de carga de hardware de terceros, consulte<A href="http://go.microsoft.com/fwlink/p/?linkid=230700">http://go.microsoft.com/fwlink/p/?linkId=230700</A>



</div>

A continuación, se muestran los requisitos del equilibrador de carga de hardware para los servicios web del grupo de servidores front-end y de directores:

  - Para los VIP de servicios Web internos,\_establezca la persistencia de la dirección de origen (puerto interno 80, 443) en el equilibrador de carga de hardware. Para Lync Server 2013, la\_persistencia de la dirección de origen significa que siempre se envían varias conexiones provenientes de una única dirección IP a un servidor para mantener el estado de la sesión.

  - Use un tiempo de espera de inactividad de TCP de 1800 segundos.

  - En el firewall entre el proxy inverso y el equilibrador de carga de hardware del grupo de servidores del próximo salto, cree una regla que permita el tráfico https: en el puerto 4443, desde el proxy inverso al equilibrador de carga de hardware. El equilibrador de carga de hardware necesita configurarse para que escuche los puertos 80, 443 y 4443.

<div>


> [!IMPORTANT]  
> Para obtener más lecturas sobre la configuración del equilibrador de carga de hardware, consulte <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">Resumen de puerto: borde consolidado escalado con equilibradores de carga de hardware de Lync Server 2013</A>.



</div>

</div>

<div>

## <a name="summary-of-hardware-load-balancer-affinity-requirements"></a>Resumen de los requisitos de afinidad del equilibrador de carga de hardware


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
<td><p>Lync Web App (solo para usuarios internos)</p>
<p>Dispositivo móvil (no implementado)</p></td>
<td><p>Sin afinidad</p></td>
<td><p>Afinidad de direcciones de origen</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="port-monitoring-for-hardware-load-balancers"></a>Supervisión de puertos para los equilibradores de carga de hardware

Es necesario definir la supervisión de puertos en los equilibradores de carga de hardware para determinar cuándo determinados servicios dejan de estar disponibles por errores de comunicaciones o de hardware. Por ejemplo, si se detiene el servicio servidor front-end (RTCSRV) porque se produce un error en el servidor front-end o en la agrupación front end, la supervisión de HLB también debe dejar de recibir tráfico en los servicios Web. La supervisión de puertos en ECH tiene que implementarse para supervisar lo siguiente:

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
<td><p>&lt;Web&gt;del grupo: int_mco_443_vs</p>
<p>443</p></td>
<td><p>443</p></td>
<td><p>Front-end</p>
<p>5061</p></td>
<td><p>Origen</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="even">
<td><p>&lt;Web&gt;del grupo: int_mco_80_vs</p>
<p>80</p></td>
<td><p>80</p></td>
<td><p>Front-end</p>
<p>5061</p></td>
<td><p>Origen</p></td>
<td><p>HTTP</p></td>
</tr>
</tbody>
</table>


### <a name="front-end-server-user-pool--hlb-external-interface"></a>Grupo de usuarios del servidor front-end: HLB externa

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

