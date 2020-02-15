---
title: 'Lync Server 2013: escenarios para el acceso de usuarios externos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scenarios for external user access
ms:assetid: 25697446-b045-4d12-9b1c-47f694b4f224
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425727(v=OCS.15)
ms:contentKeyID: 48183640
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bd560105303db5d09656c36620c9e8435feed86f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049592"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scenarios-for-external-user-access-in-lync-server-2013"></a>Escenarios para el acceso de usuarios externos en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-08_

Para permitir el acceso de usuarios externos para Lync Server 2013, es necesario que implemente al menos un servidor perimetral y un proxy inverso en la red perimetral. Opcionalmente, puede implementar un director o un grupo de directores en su red interna.

Si necesita una capacidad mayor a la que un solo servidor perimetral puede proporcionar, o si necesita una alta disponibilidad para la implementación del servidor perimetral, puede configurar el equilibrio de carga e implementar varios servidores perimetrales en un grupo de carga equilibrada. Si su organización tiene varios centros de datos, puede tener implementaciones del servidor perimetral o del grupo de servidores perimetrales en más de una ubicación. Sin embargo, solo una de las implementaciones del servidor perimetral se puede designar como la ruta de Federación.

En esta sección se definen los escenarios para las implementaciones del servidor perimetral y se asignan las secciones de planeación a los escenarios posibles. Por ejemplo, si su implementación requiere alta disponibilidad, Federación con contactos extensibles de mensajería y presencia (XMPP) y movilidad de Lync, debe seleccionar las entradas coincidentes que se indican en la siguiente tabla para cumplir con estos requisitos y usar el secciones de planeación a las que se hace referencia para definir la implementación, como se muestra en el siguiente diagrama de flujo.

**Proceso de selección del escenario de implementación del servidor perimetral**

![Diagrama de flujo de implementación de ejemplo](images/Gg425727.007100b5-6923-4909-bfd7-897d8867205f(OCS.15).jpg "Diagrama de flujo de implementación de ejemplo")

Mediante este proceso, puede planear y documentar la configuración de todas las características potenciales que desea implementar para sus usuarios. Sin embargo, puede agregar servicios de Federación y de movilidad después de implementar el servidor perimetral y haber confirmado la operación correcta antes de agregar otras características. En la sección implementación se describe el proceso de agregar características a una implementación de servidor perimetral existente. Para obtener información detallada sobre la implementación, consulte [Deploying external User Access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) al incluir la planeación de estas características durante el proceso de planeación inicial, puede preparar los requisitos de DNS, Firewall y certificado para las características agregadas, lo que le permite adquirir los certificados y configurar los requisitos de protocolo y Puerto DNS con antelación.

<div>


> [!TIP]  
> Si tiene previsto instalar los servidores perimetrales y el proxy inverso y, a continuación, agregar características más adelante (por ejemplo, Federación y movilidad), determine qué certificados necesitará para todos los servicios después de la implementación. La planeación y adquisición de los certificados para todas las características de antemano, implementadas inicialmente o no, le evita tener que pedir nuevos certificados para satisfacer los requisitos de la Federación (es decir, en los servidores perimetrales) o el proxy inverso (es decir, para la movilidad servicios).



</div>

<div>


> [!NOTE]  
> Todos los servicios perimetrales se ejecutan en cada servidor perimetral. Los servicios no se pueden dividir entre dos servidores perimetrales diferentes. Si implementa un grupo de servidores perimetrales para la escalabilidad, todos los servicios perimetrales se implementan en cada servidor perimetral del grupo. La Federación de XMPP, Office Communications Server y Lync Server, la conectividad de mensajería instantánea pública y la movilidad de clientes son servicios adicionales que se pueden implementar una vez que se ha implementado el primer servidor perimetral o el grupo de servidores perimetrales. Los servicios de movilidad son una función que utiliza el proxy inverso. La instalación de los servicios de movilidad no agregará características a los servidores perimetrales, pero será necesario volver a configurar el proxy inverso. La columna de <STRONG>objetivo de instalación</STRONG> que enumera estas características proporciona instrucciones de planeación en la columna asociada de la <STRONG>sección planeación del servidor perimetral o en secciones</STRONG> para planear de forma simultánea estas características que se van a implementar al instalar y configurar los servidores perimetrales.



</div>

<div>

## <a name="identifying-and-mapping-your-deployment-goals"></a>Identificación y asignación de los objetivos de implementación


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Objetivo de instalación</th>
<th>Documentación de planificación del servidor perimetral</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Ha decidido que un único servidor es suficiente para los servicios perimetrales en la infraestructura. También desea utilizar direcciones de IP privadas para las interfaces externas del servidor perimetral con NAT a internet.</p>
<p>Use esta sección de planeación si va a implementar un solo servidor perimetral en el perímetro. Implementará un servidor perimetral con direcciones IP privadas asignadas al servidor perimetral y usará NAT para proporcionar las direcciones IP públicas para los usuarios externos en Internet.</p></td>
<td><p><a href="lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md">Servidor perimetral consolidado único con direcciones IP privadas y NAT en Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Ha decidido que un único servidor es suficiente para los servicios perimetrales en la infraestructura. También desea utilizar direcciones de IP públicas para las interfaces externas del servidor perimetral en internet.</p>
<p>Use esta sección de planeación si va a implementar un solo servidor perimetral en el perímetro. Implementará un servidor perimetral con direcciones IP públicas asignadas al servidor perimetral. En este escenario, se utiliza el enrutamiento en lugar de NAT. La dirección IP pública real del servidor perimetral está disponible para las conexiones de usuarios externos.</p></td>
<td><p><a href="lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md">Servidor perimetral consolidado único con direcciones IP públicas en Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Ha decidido que la disponibilidad alta de los servicios perimetrales es importante para los usuarios e implementará dos o más servidores perimetrales en este grupo de servidores. También desea utilizar direcciones IP privadas para las interfaces externas del servidor perimetral con NAT a internet.</p>
<p>Use esta sección de planeación si va a implementar un grupo de servidores perimetrales en el perímetro. Implementará los servidores perimetrales con direcciones IP privadas asignadas al servidor perimetral mediante el equilibrio de carga de DNS para distribuir la comunicación en el grupo. Se utilizará NAT para proporcionar las direcciones IP públicas para los usuarios externos en internet.</p></td>
<td><p><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md">Servidor perimetral consolidado ampliado, equilibrio de carga DNS con direcciones IP privadas mediante NAT en Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Ha decidido que la disponibilidad alta de los servicios perimetrales es importante para los usuarios e implementará dos o más servidores perimetrales en este grupo de servidores. También tiene previsto usar direcciones IP públicas para las interfaces externas del servidor perimetral a Internet.</p>
<p>Use esta sección de planeación si va a implementar un grupo de servidores perimetrales en el perímetro. Implementará los servidores perimetrales con direcciones IP públicas asignadas al servidor perimetral mediante el equilibrio de carga de DNS para distribuir la comunicación en el grupo. Se utilizará el enrutamiento en lugar de NAT para proporcionar las direcciones IP públicas para los usuarios externos en internet.</p></td>
<td><p><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md">Servidor perimetral consolidado escalado, equilibrio de carga DNS con direcciones IP públicas en Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Ha decidido que la alta disponibilidad de los servicios perimetrales es importante para los usuarios e implementará dos o más servidores perimetrales en este grupo mediante un equilibrador de carga de hardware.</p>
<p>Use esta sección de planeación si va a implementar un grupo de servidores perimetrales en el perímetro. Implementará los servidores perimetrales con direcciones IP públicas asignadas al servidor perimetral, mediante equilibradores de carga de hardware para distribuir la comunicación en el grupo. Se utilizará el enrutamiento en lugar de NAT para proporcionar las direcciones IP públicas para los usuarios externos en internet.</p></td>
<td><p><a href="lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md">Servidor perimetral consolidado ampliado con equilibradores de carga de hardware en Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Los escenarios de federación permiten planificar la función que ampliará los tipos de socios con los que pueden comunicarse los usuarios.</p>
<ul>
<li><p>Federación de Lync Server</p></li>
<li><p>Federación de Office Communications Server</p></li>
<li><p>Conectividad de mensajería instantánea pública</p></li>
<li><p>Federación XMPP</p></li>
</ul></td>
<td><p>Planificación de escenarios de federación</p>
<ul>
<li><p><a href="lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md">Planeación de la Federación de Lync Server 2013 y Office Communications Server</a></p></li>
<li><p><a href="lync-server-2013-planning-for-public-instant-messaging-connectivity.md">Planeación de la conectividad de mensajería instantánea pública en Lync Server 2013</a></p></li>
<li><p><a href="lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md">Planeación de la Federación de protocolo extensible de mensajería y presencia (XMPP) en Lync Server 2013</a></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Los servicios de movilidad se ofrecen a través del proxy inverso. Los servicios que habilitan la movilidad para los usuarios externos se implementan en el servidor front-end o en el grupo de servidores front-end. Para habilitar los servicios de movilidad para los usuarios externos, crea o modifica las reglas de publicación existentes en el proxy inverso.</p></td>
<td><p><a href="lync-server-2013-planning-for-mobility.md">Planeación de movilidad en Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


<div>


> [!TIP]  
> En las siguientes secciones Escenarios hay arquitecturas de referencia, DNS de ejemplo, definiciones de puerto/protocolo y requisitos de certificados. También se incluyen diagramas del DNS, las definiciones de puerto/protocolo y los requisitos de certificados. Los diagramas proporcionarán una plantilla para que complete y distribuya a otros equipos (por ejemplo, el equipo de redes de su organización, el equipo de infraestructura de clave pública y el equipo de implementación del servidor). El objetivo de los diagramas es mejorar la comunicación y garantizar el éxito al comunicar los elementos de configuración del servidor perimetral necesario a las personas que van a realizar el trabajo de configuración real. Se recomienda el uso de los diagramas y de la arquitectura de referencia asociada para planificar la implementación.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

