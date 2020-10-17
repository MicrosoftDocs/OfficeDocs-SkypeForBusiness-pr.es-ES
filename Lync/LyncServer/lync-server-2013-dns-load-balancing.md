---
title: 'Lync Server 2013: equilibrio de carga de DNS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS load balancing
ms:assetid: 7ed0ed20-33ad-4253-926d-21d392590ae7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398634(v=OCS.15)
ms:contentKeyID: 48184625
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 79c2bb8e5bbcb9d00fe687d6f06ac6226a2edf6e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528927"
---
# <a name="dns-load-balancing-in-lync-server-2013"></a>Equilibrio de carga de DNS en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-01-15_

Lync Server habilita el equilibrio de carga de DNS, una solución de software que puede reducir considerablemente la sobrecarga de administración para el equilibrio de carga en la red. El equilibrio de carga de DNS equilibra el tráfico de red que es único en Lync Server, como el tráfico SIP y el tráfico multimedia.

Si implementa el equilibrio de carga de DNS, se minimizará la sobrecarga de administración de la organización para equilibradores de carga de hardware. Además, se evitará la solución de problemas complejos asociados a errores de configuración de equilibradores de carga del tráfico SIP. También puede impedir que se establezcan conexiones de servidores para poder desconectar servidores. El equilibrio de carga de DNS también garantiza que los problemas relacionados con los equilibradores de carga de hardware no afecten a elementos de tráfico SIP, como el enrutamiento de llamadas básico.

Si se utiliza el equilibrio de carga de DNS también podría adquirir equilibradores de carga de hardware a un precio más económico que si usa equilibradores de carga de hardware para todos los tipos de tráfico. Debe usar equilibradores de carga que han superado las pruebas de calificación de interoperabilidad con Lync Server. Para obtener más información sobre las pruebas de interoperabilidad del equilibrador de carga, consulte "Lync Server 2010 load balancer Partners" en [https://go.microsoft.com/fwlink/p/?linkId=202452](https://go.microsoft.com/fwlink/p/?linkid=202452) .

El equilibrio de carga de DNS es compatible con grupos de servidores front-end, grupos de servidores perimetrales, grupos de servidores de director y grupos de servidores de mediación independientes.

<div>

## <a name="dns-load-balancing-on-front-end-pools-and-director-pools"></a>Equilibrio de carga DNS en grupos de servidores front-end y grupos de servidores de director

Puede usar el equilibrio de carga DNS para el tráfico SIP de los grupos de servidores front-end y grupos de servidores de director. Con el equilibrio de carga DNS implementado, seguirá necesitando usar también equilibradores de carga de hardware para esos grupos de servidores, pero solo para el tráfico HTTPS de cliente a servidor. El equilibrador de carga de hardware se usa para el tráfico HTTPS de los clientes en los puertos 443 y 80.

A pesar de que seguirá necesitando equilibradores de carga de hardware para esos grupos de servidores, su instalación y administración será fundamentalmente para el tráfico HTTPS, al que están habituados los administradores de equilibradores de carga de hardware.

<div>

## <a name="dns-load-balancing-and-supporting-older-clients-and-servers"></a>Equilibrio de carga DNS y compatibilidad con clientes y servidores más antiguos

El equilibrio de carga de DNS admite la conmutación por error automática solo para servidores que ejecutan Lync Server 2013 o Lync Server 2010 y para clientes de Lync 2013 y Lync 2010. Las versiones anteriores de clientes y Office Communications Server todavía pueden conectarse a grupos que ejecutan el equilibrio de carga de DNS, pero si no pueden realizar una conexión con el primer servidor al que el equilibrio de carga de DNS hace referencia a, no pueden conmutar por error a otro servidor del grupo.

Además, si usa la mensajería unificada de Exchange, debe usar un mínimo de Exchange 2010 SP1 para obtener compatibilidad con el equilibrio de carga de DNS de Lync Server. Si usa una versión anterior de Exchange, los usuarios no tendrán capacidades de conmutación por error para estos escenarios de mensajería unificada de Exchange:

  - Reproducir el correo de voz de Enterprise Voice en el teléfono

  - Transferir llamadas de un operador automático de la mensajería unificada de Exchange

Todos los demás escenarios de la mensajería unificada de Exchange funcionarán correctamente.

</div>

<div>

## <a name="deploying-dns-load-balancing-on-front-end-pools-and-director-pools"></a>Implementación del equilibrio de carga DNS en grupos de servidores front-end y grupos de servidores de director

Para implementar el equilibrio de carga DNS en grupos de servidores front-end y grupos de servidores de director, es necesario realizar un par de pasos adicionales con los registros DNS y los FQDN.

  - Si un grupo de servidores usa equilibrio de carga DNS, debe tener dos FQDN: el nombre de dominio completo normal que usa el equilibrio de carga DNS (como, por ejemplo, pool01.contoso.com), y se resuelve como las IP físicas de los servidores del grupo de servidores, y otro nombre de dominio completo para los servicios web del grupo de servidores (como, por ejemplo, web01.contoso.com), que se resuelve como la dirección IP virtual del grupo de servidores.
    
    En el generador de topologías, si desea implementar el equilibrio de carga de DNS para un grupo de servidores, para crear este FQDN adicional para los servicios web del grupo de servidores, debe activar la casilla **invalidar el FQDN del grupo de servicios Web internos** y escribir el FQDN en la página **especificar las direcciones URL de servicios web para este grupo de** servidores.

  - Para admitir el FQDN que usa el equilibrio de carga DNS, debe aprovisionar el DNS de modo que resuelva el FQDN del grupo de servidores (como, por ejemplo, pool01.contoso.com) como las direcciones IP de todos los servidores del grupo de servidores (por ejemplo, 192.168.1.1, 192.168.1.2, etc.). Solo deberá incluir las direcciones IP de los servidores implementados actualmente.
    
    <div>
    

    > [!WARNING]  
    > Si tiene más de un grupo de servidores front-end o un servidor front-end, el FQDN de los servicios web externos debe ser único. Por ejemplo, si define el FQDN de servicios web externos de un servidor front-end como <STRONG>pool01.contoso.com</STRONG>, no puede usar <STRONG>pool01.contoso.com</STRONG> para otro grupo de servidores front-end o servidor front-end. Si también está implementando directores, el FQDN de servicios Web externo definido para cualquier Director o grupo de directores debe ser único de cualquier otro director o grupo de directores, así como cualquier grupo de servidores front-end o servidor front-end. Si decide reemplazar los servicios Web internos con un FQDN autodefinido, cada FQDN debe ser único en cualquier otro grupo de servidores front-end, director o grupo de directores.

    
    </div>

</div>

</div>

<div>

## <a name="dns-load-balancing-on-edge-server-pools"></a>Equilibrio de carga DNS en grupos de servidores perimetrales

Puede implementar el equilibrio de carga DNS en grupos de servidores perimetrales. Si lo hace, debe tener en cuenta varias consideraciones.

El uso del equilibrio de carga DNS en los servidores perimetrales provoca una pérdida en la capacidad de conmutación por error, en los siguientes escenarios:

  - Federación con organizaciones que ejecutan versiones de Office Communications Server que se publican antes de Lync Server 2010.

  - Intercambio de mensajes instantáneos con usuarios de servicios de mensajería instantánea pública (mi) AOLand Yahoo \! , además de servidores y proveedores basados en XMPP, como Google Talk.
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P>Actualmente, Google Talk es el único socio de XMPP admitido.</P>
    > <LI>
    > <P>A partir del 1 de septiembre de 2012, la licencia de suscripción de usuario de conectividad de mensajería instantánea pública de Microsoft Lync ("PIC USL") ya no está disponible para la compra de contratos nuevos o de renovación. Los clientes con licencias activas podrán seguir federando a Yahoo! Messenger hasta que se cierre la fecha del servicio. Una fecha de finalización del ciclo de vida de junio de 2014 para AOL y Yahoo! se ha anunciado. Para obtener más información, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">compatibilidad con la conectividad de mensajería instantánea pública en Lync Server 2013</A>.</P></LI></UL>

    
    </div>

Estos escenarios funcionarán siempre que se ejecuten correctamente todos los servidores perimetrales del grupo de servidores pero, si un servidor perimetral no está disponible, fallarán todas las solicitudes de estos escenarios que se envíen a él, en lugar de enrutarse a otro servidor perimetral.

Si usa la mensajería unificada de Exchange, debe usar un mínimo de Exchange 2013 para obtener compatibilidad con el equilibrio de carga de DNS de Lync Server en el servidor perimetral. Si usa una versión anterior de Exchange, los usuarios remotos no tendrán capacidades de conmutación por error para estos escenarios de mensajería unificada de Exchange:

  - Reproducir el correo de voz de Enterprise Voice en el teléfono

  - Transferir llamadas de un operador automático de la mensajería unificada de Exchange

Todos los demás escenarios de la mensajería unificada de Exchange funcionarán correctamente.

La interfaz perimetral interna y la interfaz perimetral externa deben usar el mismo tipo de equilibrio de carga. No puede usar equilibrio de carga DNS en una interfaz perimetral y equilibrio de carga de hardware en la otra interfaz perimetral.

<div>

## <a name="deploying-dns-load-balancing-on-edge-server-pools"></a>Implementación del equilibrio de carga DNS en grupos de servidores perimetrales

Para implementar el equilibrio de carga DNS en la interfaz externa de su grupo de servidores perimetrales, necesita las siguientes entradas DNS:

  - Para el servicio perimetral de acceso, necesita una entrada por cada servidor del grupo. Cada entrada debe resolver el nombre de dominio completo (FQDN) del servicio perimetral de acceso (por ejemplo, sip.contoso.com) en la dirección IP del servicio perimetral de acceso en uno de los servidores perimetrales del grupo.

  - Para el servicio perimetral de conferencia Web, necesita una entrada por cada servidor del grupo. Cada entrada debe resolver el FQDN del servicio perimetral de conferencia web (por ejemplo, webconf.contoso.com) en la dirección IP del servicio perimetral de conferencia web en uno de los servidores perimetrales del grupo.

  - Para el servicio perimetral de audio y vídeo, necesita una entrada por cada servidor del grupo. Cada entrada debe resolver el FQDN del servicio perimetral de audio y vídeo (por ejemplo, av.contoso.com) en la dirección IP del servicio perimetral A/V en uno de los servidores perimetrales del grupo.

Para implementar el equilibrio de carga DNS en la interfaz interna del grupo de servidores perimetrales, debe agregar un registro DNS A que resuelva el FQDN interno del grupo de servidores perimetrales en la dirección IP de cada servidor del grupo de servidores.

</div>

</div>

<div>

## <a name="using-dns-load-balancing-on-mediation-server-pools"></a>Uso del equilibrio de carga DNS en grupos de servidores de mediación

Puede usar el equilibrio de carga DNS en grupos de servidores de mediación independientes. Todo el tráfico de medios y SIP se equilibra con el equilibrio de carga DNS.

Para implementar el equilibrio de carga DNS en un grupo de servidores de mediación, debe aprovisionar el DNS de modo que resuelva el FQDN del grupo de servidores (por ejemplo, mediationpool1.contoso.com) como las direcciones IP de todos los servidores del grupo de servidores (por ejemplo, 192.168.1.1, 192.168.1.2, etc.).

</div>

<div>

## <a name="blocking-traffic-to-a-server-with-dns-load-balancing"></a>Bloqueo del tráfico a un servidor con equilibrio de carga de DNS

Si usa el equilibrio de carga de DNS y necesita bloquear el tráfico a un equipo específico, no basta con quitar las entradas de dirección IP del FQDN del grupo de servidores. También debe quitar la entrada DNS del equipo.

Tenga en cuenta que para el tráfico de servidor a servidor, Lync Server 2013 usa el equilibrio de carga consciente de la topología. Los servidores leen la topología Publicada en el almacén de administración central para obtener los FQDN de los servidores en la topología y distribuyen automáticamente el tráfico entre los servidores. Para impedir que un servidor reciba tráfico de servidor a servidor, debe quitar el servidor de la topología.

</div>

</div>

<span> </span>

</div>

</div>

</div>

