---
title: 'Lync Server 2013: Escenarios para el acceso de usuarios externos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Scenarios for external user access
ms:assetid: 25697446-b045-4d12-9b1c-47f694b4f224
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425727(v=OCS.15)
ms:contentKeyID: 48183640
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27e4f7410d7038971c6ddefe1af1c7b3ecd97ab9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822331"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scenarios-for-external-user-access-in-lync-server-2013"></a>Escenarios para el acceso de usuarios externos en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-08_

Para proporcionar acceso a usuarios externos para Lync Server 2013, debe implementar al menos un servidor perimetral y un proxy inverso en la red perimetral. De manera opcional, puede implementar un director o un grupo de directores en su red interna.

Si necesita una mayor capacidad de la que un solo servidor perimetral puede proporcionar, o si necesita una alta disponibilidad para la implementación de su servidor perimetral, puede configurar el equilibrio de carga e implementar varios servidores perimetrales en un grupo de carga equilibrada. Si su organización tiene varios centros de datos, puede tener implementaciones de servidores perimetrales o de conjuntos de límites en más de una ubicación. Sin embargo, solo se puede designar una de las implementaciones de servidor perimetral como la ruta de Federación.

En esta sección se definen los escenarios para las implementaciones de servidores perimetrales y se asignan las secciones de planeación a los posibles escenarios. Por ejemplo, si su implementación requiere alta disponibilidad, Federación con contactos de presencia y mensajería extensible (XMPP) y movilidad de Lync, debe seleccionar las entradas coincidentes de la siguiente tabla que cumplan estos requisitos y usar el se hace referencia a las secciones de planeación para definir la implementación, como se muestra en el siguiente diagrama de flujo.

**Proceso de selección del escenario de implementación del servidor perimetral**

![Diagrama de flujo de implementación de ejemplo] (images/Gg425727.007100b5-6923-4909-bfd7-897d8867205f(OCS.15).jpg "Diagrama de flujo de implementación de ejemplo")

Mediante este proceso, puede planear y documentar la configuración de todas las características potenciales que desea implementar para sus usuarios. Sin embargo, puede agregar servicios de Federación y movilidad después de haber implementado el servidor perimetral y haber confirmado la operación correcta antes de agregar otras características. El proceso de agregar características a una implementación existente de un servidor perimetral se trata en la sección implementación. Para obtener más información sobre la implementación, consulte [implementar el acceso de usuarios externos en Lync Server 2013](lync-server-2013-deploying-external-user-access.md) incluyendo la planificación de estas características durante el proceso de planeación inicial, puede prepararse para los requisitos de DNS, Firewall y certificados para las características agregadas. lo que le permite adquirir los certificados y configurar DNS y los requisitos de puerto y Protocolo por adelantado.

<div>


> [!TIP]  
> Si planea instalar los servidores perimetrales y el proxy inverso y agregar características más adelante (por ejemplo, Federación y movilidad), determine qué certificados necesitará para todos los servicios después de la implementación. Planear y adquirir certificados para todas las características de antemano, inicialmente implementadas o no, evita tener que pedir certificados nuevos para cumplir los requisitos de Federación (es decir, en los servidores perimetrales) o el proxy inverso (es decir, para la movilidad). servicios).



</div>

<div>


> [!NOTE]  
> Todos los servicios de Edge se ejecutan en cada servidor perimetral. Los servicios no se pueden dividir entre dos servidores perimetrales diferentes. Si implementa un grupo perimetral para escalabilidad, todos los servicios perimetrales se implementan en cada servidor perimetral en el grupo. La Federación de XMPP, Office Communications Server y Lync Server, la conectividad de mensajería instantánea pública y la movilidad de clientes son servicios adicionales que se pueden implementar después de implementar el primer servidor perimetral o el grupo perimetral. Mobility Services es una característica que usa el proxy inverso. La instalación de Mobility Services no agregará características a los servidores perimetrales, pero requerirá la reconfiguración de su proxy inverso. La columna <STRONG>objetivo de instalación</STRONG> que contiene estas características proporciona instrucciones de planeación en la columna asociada de la sección de planeación del <STRONG>servidor EDGE o secciones</STRONG> para planear de forma simultánea estas características que se implementarán cuando los servidores perimetrales estén instalado y configurado.



</div>

<div>

## <a name="identifying-and-mapping-your-deployment-goals"></a>Identificar y asignar los objetivos de implementación


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Objetivo de instalación</th>
<th>Documentación de planeación del servidor EDGE</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Ha decidido que un solo servidor es suficiente para los servicios de vanguardia de su infraestructura. También desea usar direcciones IP privadas para las interfaces externas de servidor perimetral con NAT a Internet.</p>
<p>Use esta sección de planificación si va a implementar un único servidor perimetral en su perímetro. Implementará un servidor perimetral con direcciones IP privadas asignadas al servidor perimetral y usará NAT para proporcionar las direcciones IP públicas de los usuarios externos en Internet.</p></td>
<td><p><a href="lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md">Servidor perimetral consolidado simple con direcciones IP privadas y NAT en Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Ha decidido que un solo servidor es suficiente para los servicios de vanguardia de su infraestructura. También desea usar direcciones IP públicas para las interfaces externas de servidor perimetral a Internet.</p>
<p>Use esta sección de planificación si va a implementar un único servidor perimetral en su perímetro. Implementará un servidor perimetral con direcciones IP públicas asignadas al servidor perimetral. En lugar de NAT, usará el enrutamiento en este escenario. La dirección IP pública real del servidor perimetral está disponible para las conexiones de usuarios externos.</p></td>
<td><p><a href="lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md">Topología perimetral consolidada de un solo equipo con direcciones IP públicas en Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Ha decidido que la alta disponibilidad de los servicios perimetrales es importante para sus usuarios y que va a implementar dos o más servidores perimetrales en este grupo. También desea usar direcciones IP privadas para las interfaces externas de servidor perimetral con NAT a Internet.</p>
<p>Use esta sección de planificación si está implementando un grupo de servidores perimetrales en el perímetro. Implementará los servidores perimetrales con direcciones IP privadas asignadas al servidor perimetral, usando el equilibrio de carga de DNS para distribuir la comunicación en el grupo. Usará NAT para proporcionar las direcciones IP públicas para los usuarios externos en Internet.</p></td>
<td><p><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md">Servidor perimetral consolidado ampliado, equilibrio de carga DNS con direcciones IP privadas mediante NAT en Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Ha decidido que la alta disponibilidad de los servicios perimetrales es importante para sus usuarios y que va a implementar dos o más servidores perimetrales en este grupo. También desea usar direcciones IP públicas para las interfaces externas de servidor perimetral a Internet.</p>
<p>Use esta sección de planificación si está implementando un grupo de servidores perimetrales en el perímetro. Implementará los servidores perimetrales con direcciones IP públicas asignadas al servidor perimetral, usando el equilibrio de carga de DNS para distribuir la comunicación en el grupo. En lugar de NAT, usará el enrutamiento para proporcionar las direcciones IP públicas de los usuarios externos en Internet.</p></td>
<td><p><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md">Perímetro consolidado escalado, equilibrio de carga DNS con direcciones IP públicas en Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Ha decidido que la alta disponibilidad de los servicios perimetrales es importante para sus usuarios y que va a implementar dos o más servidores perimetrales en este grupo con un equilibrador de carga de hardware.</p>
<p>Use esta sección de planificación si está implementando un grupo de servidores perimetrales en el perímetro. Implementará los servidores perimetrales con direcciones IP públicas asignadas al servidor perimetral, con equilibradores de carga de hardware para distribuir la comunicación en el grupo. En lugar de NAT, usará el enrutamiento para proporcionar las direcciones IP públicas de los usuarios externos en Internet.</p></td>
<td><p><a href="lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md">Servidor perimetral consolidado ampliado con equilibradores de carga de hardware en Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Los escenarios de Federación le permiten planear la característica que extenderá los tipos de socios con los que se pueden comunicar los usuarios.</p>
<ul>
<li><p>Federación de Lync Server</p></li>
<li><p>Federación de Office Communications Server</p></li>
<li><p>Conectividad de mensajería instantánea pública</p></li>
<li><p>Federación XMPP</p></li>
</ul></td>
<td><p>Planeamiento de escenarios de Federación</p>
<ul>
<li><p><a href="lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md">Planificación de la Federación de Lync Server 2013 y Office Communications Server</a></p></li>
<li><p><a href="lync-server-2013-planning-for-public-instant-messaging-connectivity.md">Planeamiento de la conectividad de mensajería instantánea pública en Lync Server 2013</a></p></li>
<li><p><a href="lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md">Planeamiento de la Federación de protocolo de presencia y mensajería extensible (XMPP) en Lync Server 2013</a></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Los servicios de movilidad se ofrecen a través del proxy inverso. Los servicios que permiten la movilidad para los usuarios externos se implementan en el servidor front-end o en el grupo front-end. Puede crear o modificar las reglas de publicación existentes en el proxy inverso para habilitar los servicios de movilidad para los usuarios externos.</p></td>
<td><p><a href="lync-server-2013-planning-for-mobility.md">Planeación de movilidad en Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


<div>


> [!TIP]  
> En las siguientes secciones, se incluyen arquitecturas de referencia, DNS de ejemplo, definiciones de puerto y Protocolo, y requisitos de certificado. También se incluyen diagramas de su DNS, definiciones de puertos y puertos, y necesidades de certificados. Los diagramas proporcionarán una plantilla que le permitirá rellenar y distribuir a otros equipos (por ejemplo, el equipo de red de su organización, el equipo de infraestructura de clave pública y el equipo de implementación de servidores). El objetivo de los diagramas es mejorar la comunicación y garantizar el éxito al comunicar los elementos de configuración del servidor perimetral requeridos a las personas que realizarán el trabajo de configuración real. Le recomendamos que use los diagramas y las arquitecturas de referencia asociadas para planificar su implementación.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

