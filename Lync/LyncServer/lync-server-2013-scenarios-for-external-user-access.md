---
title: 'Lync Server 2013: Escenarios para el acceso de usuarios externos'
TOCTitle: Escenarios para el acceso de usuarios externos
ms:assetid: 25697446-b045-4d12-9b1c-47f694b4f224
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg425727(v=OCS.15)
ms:contentKeyID: 48274692
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Escenarios para el acceso de usuarios externos en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

Para poder permitir el acceso de usuarios externos para el Lync Server 2013, se debe implementar al menos un Servidor perimetral y un proxy inverso en la red perimetral. Opcionalmente, podría implementar un Director o Grupo de directores en la red interna.

En caso de que necesite más funciones de las que un solo Servidor perimetral puede ofrecer, o bien precise de una gran disponibilidad para la implementación de Servidor perimetral, puede implementar varios Servidores perimetrales y configurar el equilibrio de carga. Si la organización cuenta con varios centros de datos, se pueden tener implementaciones de Servidor perimetral o Grupo de servidores perimetrales en más de una ubicación, si bien solo una de las implementaciones de Servidor perimetral podrá designarse como ruta de federación.

Esta sección define los escenarios para las implementaciones de Servidor perimetral y asigna las secciones de planificación a los posibles escenarios. Por ejemplo, si la implementación requiere gran disponibilidad, federación con contactos de presencia y mensajería extensibles (XMPP) y movilidad de Lync, debe seleccionar las entradas coincidentes de la siguiente tabla que cumplirían con estos requisitos y utilizaría las secciones de planificación mencionadas para definir la implementación, tal como se muestra en diagrama de flujo siguiente.

**Proceso de selección del escenario de implementación del servidor perimetral**

![Diagrama de flujo de la implementación de muestra](images/Gg425727.007100b5-6923-4909-bfd7-897d8867205f(OCS.15).jpg "Diagrama de flujo de la implementación de muestra")

Al utilizar este proceso, puede planificar y documentar la configuración de todas las funciones potenciales que desea implementar para los usuarios. Sin embargo, puede agregar servicios de movilidad y federación luego de haber implementado el Servidor perimetral y haber confirmado la operación correcta antes de agregar las otras funciones. El proceso de agregar funciones a una implementación de Servidor perimetral existente se aborda en la sección Implementación. Para obtener más detalles sobre la implementación, vea [Implementar el acceso de usuarios externos en Lync Server 2013](lync-server-2013-deploying-external-user-access.md). La planificación de estas características durante el proceso de planificación inicial le permitirá preparar el DNS, el firewall y los requisitos de certificado para las características agregadas, lo cual le permitirá adquirir los certificados y configurar los requisitos de protocolo/puerto y DNS por anticipado.

> [!TIP]  
> Si tiene planificado instalar el Servidores perimetrales y proxy inverso y agregar funciones posteriormente (como, por ejemplo, la federación y la movilidad), determine qué certificados necesitará para todos los servicios tras la implementación. La planificación y adquisición de los certificados para todas las funciones por adelantado, inicialmente implementadas o no, le evitarán tener que solicitar nuevos certificados para cumplir con los requisitos de federación (es decir, en el Servidores perimetrales) o el proxy inverso (es decir, para servicios de movilidad).




> [!NOTE]
> Todos los servicios perimetrales se ejecutan en cada Servidor perimetral. Los servicios no pueden dividirse entre dos Servidores perimetrales diferentes. Si implementa un Grupo de servidores perimetrales para la escalabilidad, todos los servicios perimetrales se implementan en cada Servidor perimetral en el grupo de servidores. La federación XMPP, la federación Office Communications Server y Lync Server, la conectividad de mensajería instantánea pública y la movilidad de cliente son servicios adicionales que pueden implementarse una vez que ha implementado el primer Servidor perimetral o Grupo de servidores perimetrales. Los servicios de movilidad son una función que utiliza el proxy inverso. La instalación de los servicios de movilidad no agregará funciones al Servidores perimetrales, pero requerirá que se vuelva a configurar el proxy inverso. La columna <STRONG>Objetivo de instalación</STRONG> que muestra estas funciones proporciona una guía de planificación en la columna asociada en la <STRONG>sección o secciones de planificación del servidor perimetral</STRONG> para planificar simultáneamente estas funciones que se implementarán cuando se instalen y configuren los Servidores perimetrales.



## Identificación y asignación de los objetivos de implementación


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
<p>Utilice esta sección de planificación si implementa un único Servidor perimetral en el perímetro. Implementará un Servidor perimetral con direcciones de IP privadas asignadas al Servidor perimetral y utilizará NAT para proporcionar direcciones IP públicas para los usuarios externos en internet.</p></td>
<td><p><a href="lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md">Servidor perimetral consolidado simple con direcciones IP privadas y NAT en Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Ha decidido que un único servidor es suficiente para los servicios perimetrales en la infraestructura. También desea utilizar direcciones de IP públicas para las interfaces externas del servidor perimetral en internet.</p>
<p>Utilice esta sección de planificación si implementa un único Servidor perimetral en el perímetro. Implementará un Servidor perimetral con direcciones IP públicas asignadas al Servidor perimetral. En este escenario, se utiliza el enrutamiento en lugar de NAT. La dirección de IP pública real del Servidor perimetral pasa a estar disponible para conexiones de usuarios externos.</p></td>
<td><p><a href="lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md">Topología perimetral consolidada de un solo equipo con direcciones IP públicas en Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Ha decidido que la disponibilidad alta de los servicios perimetrales es importante para los usuarios e implementará dos o más servidores perimetrales en este grupo de servidores. También desea utilizar direcciones IP privadas para las interfaces externas del servidor perimetral con NAT a internet.</p>
<p>Utilice esta sección de planificación si utiliza un grupo de Servidores perimetrales en el perímetro. Implementará el Servidores perimetrales con direcciones IP privadas asignadas al Servidor perimetral, utilizando el equilibrio de carga de DNS para distribuir comunicación en todo el grupo. Se utilizará NAT para proporcionar las direcciones IP públicas para los usuarios externos en internet.</p></td>
<td><p><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md">Servidor perimetral consolidado ampliado, equilibrio de carga DNS con direcciones IP privadas mediante NAT en Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Ha decidido que la disponibilidad alta de los servicios perimetrales es importante para los usuarios e implementará dos o más Servidores perimetrales en este grupo de servidores. También desea utilizar direcciones IP públicas para las interfaces externas del Servidor perimetral a internet.</p>
<p>Utilice esta sección de planificación si utiliza un grupo de Servidores perimetrales en el perímetro. Implementará el Servidores perimetrales con direcciones IP públicas asignadas al Servidor perimetral, utilizando el equilibrio de carga de DNS para distribuir comunicación en todo el grupo. Se utilizará el enrutamiento en lugar de NAT para proporcionar las direcciones IP públicas para los usuarios externos en internet.</p></td>
<td><p><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md">Perímetro consolidado escalado, equilibrio de carga DNS con direcciones IP públicas en Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Ha decidido que la disponibilidad alta de los servicios perimetrales es importante para los usuarios e implementará dos o más Servidores perimetrales en este grupo de servidores utilizando un equilibrador de carga de hardware.</p>
<p>Utilice esta sección de planificación si utiliza un grupo de Servidores perimetrales en el perímetro. Implementará el Servidores perimetrales con direcciones IP públicas asignadas al Servidor perimetral, utilizando equilibradores de hardware para distribuir comunicación en todo el grupo. Se utilizará el enrutamiento en lugar de NAT para proporcionar las direcciones IP públicas para los usuarios externos en internet.</p></td>
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
<li><p><a href="lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md">Planeación de federación de Lync Server y Office Communications Server</a></p></li>
<li><p><a href="lync-server-2013-planning-for-public-instant-messaging-connectivity.md">Planear la conectividad de mensajería instantánea pública en Lync Server 2013</a></p></li>
<li><p><a href="lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md">Planeación de federación de protocolo extensible de mensajería y presencia (XMPP) en Lync Server 2013</a></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Los servicios de movilidad se ofrecen a través del proxy inverso. Los servicios que permiten la movilidad para los usuarios externos se implementan en el Servidor front-end o Grupo de servidores front-end. Para habilitar los servicios de movilidad para los usuarios externos, crea o modifica las reglas de publicación existentes en el proxy inverso.</p></td>
<td><p><a href="lync-server-2013-planning-for-mobility.md">Planeación de movilidad en Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


> [!TIP]  
> En las siguientes secciones Escenarios hay arquitecturas de referencia, DNS de ejemplo, definiciones de puerto/protocolo y requisitos de certificados. También se incluyen diagramas del DNS, las definiciones de puerto/protocolo y los requisitos de certificados. Los diagramas proporcionarán una plantilla para que complete y distribuya a otros equipos (por ejemplo, el equipo de redes de su organización, el equipo de infraestructura de clave pública y el equipo de implementación del servidor). El objetivo de los diagramas es mejorar la comunicación y asegurar que se comuniquen correctamente los elementos necesarios de configuración del Servidor perimetral a las personas que harán el verdadero trabajo de configuración. Se recomienda el uso de los diagramas y de la arquitectura de referencia asociada para planificar la implementación.


