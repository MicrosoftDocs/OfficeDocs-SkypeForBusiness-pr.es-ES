---
title: Equilibrio de carga de DNS en Lync Server 2013
TOCTitle: Equilibrio de carga de DNS en Lync Server 2013
ms:assetid: 7ed0ed20-33ad-4253-926d-21d392590ae7
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398634(v=OCS.15)
ms:contentKeyID: 48275810
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Equilibrio de carga de DNS en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Lync Server permite el equilibrio de carga de DNS, una solución de software que puede reducir considerablemente la sobrecarga de administración para el equilibrio de carga en la red. El equilibrio de carga de DNS equilibra el tráfico de red que solo pertenece a Lync Server, como el tráfico SIP y el tráfico de medios.

Si implementa el equilibrio de carga de DNS, se reducirá considerablemente la sobrecarga de administración de la organización correspondiente a los equilibradores de carga de hardware. Además, se evitará la solución de problemas complejos asociados a errores de configuración de equilibradores de carga del tráfico SIP. También puede impedir que se establezcan conexiones de servidores para poder desconectar servidores. El equilibrio de carga de DNS también garantiza que los problemas relacionados con los equilibradores de carga de hardware no afecten a elementos de tráfico SIP, como el enrutamiento de llamadas básico.

Si se utiliza el equilibrio de carga de DNS también podría adquirir equilibradores de carga de hardware a un precio más económico que si usa equilibradores de carga de hardware para todos los tipos de tráfico. Deberá utilizar equilibradores de carga que hayan superado las pruebas de cualificación de interoperabilidad con Lync Server. Para obtener información detallada acerca de las pruebas de interoperabilidad de los equilibradores de carga, consulte "Socios del equilibrador de carga de Lync Server 2010", en <http://go.microsoft.com/fwlink/?linkid=202452>.

El equilibrio de carga de DNS es compatible con grupos de servidores front-end, grupos de servidores perimetrales, grupos de servidores de director y grupos de servidores de mediación independientes.

## Equilibrio de carga DNS en grupos de servidores front-end y grupos de servidores de director

Puede usar el equilibrio de carga DNS para el tráfico SIP de los grupos de servidores front-end y grupos de servidores de director. Con el equilibrio de carga DNS implementado, seguirá necesitando usar también equilibradores de carga de hardware para esos grupos de servidores, pero solo para el tráfico HTTPS de cliente a servidor. El equilibrador de carga de hardware se usa para el tráfico HTTPS de los clientes en los puertos 443 y 80.

A pesar de que seguirá necesitando equilibradores de carga de hardware para esos grupos de servidores, su instalación y administración será fundamentalmente para el tráfico HTTPS, al que están habituados los administradores de equilibradores de carga de hardware.

## Equilibrio de carga DNS y compatibilidad con clientes y servidores más antiguos

El equilibrio de carga DNS admite la conmutación automática por error solo en los servidores que ejecutan Lync Server 2013 o Lync Server 2010 y para los clientes de Lync 2013 y Lync 2010. Las versiones anteriores de los clientes y Office Communications Server pueden seguir conectándose a grupos de servidores que ejecuten el equilibrio de carga DNS pero, si no consiguen establecer una conexión con el primer servidor al que los remita el equilibrio de carga DNS, no pueden efectuar la conmutación por error a otro servidor del grupo.

Por otra parte, si usa la mensajería unificada de Exchange, debe utilizar como mínimo Exchange 2010 SP1 para obtener compatibilidad con el equilibrio de carga DNS de Lync Server. Si usa alguna versión anterior de Exchange, no tendrá funcionalidades de conmutación por error para estos escenarios de la mensajería unificada de Exchange:

  - Reproducir el correo de voz de Enterprise Voice en el teléfono

  - Transferir llamadas de un operador automático de la mensajería unificada de Exchange

Todos los demás escenarios de la mensajería unificada de Exchange funcionarán correctamente.

## Implementación del equilibrio de carga DNS en grupos de servidores front-end y grupos de servidores de director

Para implementar el equilibrio de carga DNS en grupos de servidores front-end y grupos de servidores de director, es necesario realizar un par de pasos adicionales con los registros DNS y los FQDN.

  - Si un grupo de servidores usa equilibrio de carga DNS, debe tener dos FQDN: el nombre de dominio completo normal que usa el equilibrio de carga DNS (como, por ejemplo, pool01.contoso.com), y se resuelve como las IP físicas de los servidores del grupo de servidores, y otro nombre de dominio completo para los servicios web del grupo de servidores (como, por ejemplo, web01.contoso.com), que se resuelve como la dirección IP virtual del grupo de servidores.
    
    En Generador de topologías, si desea implementar el equilibrio de carga DNS en un grupo de servidores, para crear el nombre de dominio completo adicional para los servicios web del grupo de servidores, debe activar la casilla **Reemplazar FQDN interno del grupo de servidores de servicios web internos** y escribir el FQDN en la página **Especificar las URL de los servicios web de este grupo de servidores**.

  - Para admitir el FQDN que usa el equilibrio de carga DNS, debe aprovisionar el DNS de modo que resuelva el FQDN del grupo de servidores (como, por ejemplo, pool01.contoso.com) como las direcciones IP de todos los servidores del grupo de servidores (por ejemplo, 192.168.1.1, 192.168.1.2, etc.). Solo deberá incluir las direcciones IP de los servidores implementados actualmente.
    
    > [!WARNING]  
    > Si tiene más de un Grupo de servidores front-end o Servidor front-end los servicios Web externos FQDN deben ser únicos. Por ejemplo, si define los servicios Web externos FQDN de un Servidor front-end como <strong>pool01.contoso.com</strong> no puede usar <strong>pool01.contoso.com</strong> para otro Grupo de servidores front-end o Servidor front-end. Si también está implementando Directores, los servicios Web externos FQDN definidos para un Director o Grupo de directores deben ser diferentes de otro Director o Grupo de directores al igual que cualquier Grupo de servidores front-end o Servidor front-end. Si decide omitir los servicios Web externos con un FQDN autodefinido, todos los FQDN deben ser diferentes de otros Grupo de servidores front-end, Director o Grupo de directores.
    


## Equilibrio de carga DNS en grupos de servidores perimetrales

Puede implementar el equilibrio de carga DNS en grupos de servidores perimetrales. Si lo hace, debe tener en cuenta varias consideraciones.

El uso del equilibrio de carga DNS en los servidores perimetrales provoca una pérdida en la capacidad de conmutación por error, en los siguientes escenarios:

  - Federación con organizaciones que ejecutan versiones de Office Communications Server anteriores a Lync Server 2010.

  - Intercambio de mensajes instantáneos con usuarios de servicios de mensajería instantánea (MI) pública, como AOL y Yahoo\!, además de servidores y proveedores basados en XMPP, como Google Talk.
    
    > [!IMPORTANT]  
	> <ul>
    > <li><p>Actualmente, Google Talk es el único socio XMPP admitido.</p></li>
    > <li><p>El 1 de septiembre de 2012, la licencia de suscripción del usuario de Public IM Connectivity de Microsoft Lync (&quot;PIC USL&quot;) dejó de estar disponible para su compra en los contratos nuevos y en las prórrogas de contratos. Los clientes que tengan licencias activas podrán seguir federándose con Yahoo! Messenger hasta la fecha de cierre del servicio. La fecha anunciada para el fin de vida de AOL y Yahoo! es junio de 2014. Para más detalles, vea <a href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Soporte para la conectividad de mensajería instantánea pública en Lync Server 2013</a>.</p></li>
    > </ul>


Estos escenarios funcionarán siempre que se ejecuten correctamente todos los servidores perimetrales del grupo de servidores pero, si un servidor perimetral no está disponible, fallarán todas las solicitudes de estos escenarios que se envíen a él, en lugar de enrutarse a otro servidor perimetral.

si usa la mensajería unificada de Exchange, debe utilizar como mínimo Exchange 2013 para obtener compatibilidad con el equilibrio de carga DNS de Lync Server en los servidores perimetrales. Si usa alguna versión anterior de Exchange, sus usuarios remotos no tendrán funcionalidades de conmutación por error para estos entornos de mensajería unificada de Exchange:

  - Reproducir el correo de voz de Enterprise Voice en el teléfono

  - Transferir llamadas de un operador automático de la mensajería unificada de Exchange

Todos los demás escenarios de la mensajería unificada de Exchange funcionarán correctamente.

La interfaz perimetral interna y la interfaz perimetral externa deben usar el mismo tipo de equilibrio de carga. No puede usar equilibrio de carga DNS en una interfaz perimetral y equilibrio de carga de hardware en la otra interfaz perimetral.

## Implementación del equilibrio de carga DNS en grupos de servidores perimetrales

Para implementar el equilibrio de carga DNS en la interfaz externa de su grupo de servidores perimetrales, necesita las siguientes entradas DNS:

  - Para el servicio perimetral de acceso, necesita una entrada por cada servidor del grupo de servidores. Cada entrada debe resolver el FQDN del servicio perimetral de acceso (por ejemplo, sip.contoso.com) como la dirección IP del servicio perimetral de acceso de uno de los servidores perimetrales del grupo de servidores.

  - Para el servicio perimetral de conferencia web, necesita una entrada por cada servidor del grupo de servidores. Cada entrada debe resolver el FQDN del servicio perimetral de conferencia web (por ejemplo, webconf.contoso.com) como la dirección IP del servicio perimetral de conferencia web de uno de los servidores perimetrales del grupo de servidores.

  - Para el servicio perimetral de audio y vídeo, necesita una entrada por cada servidor del grupo de servidores. Cada entrada debe resolver el FQDN del servicio perimetral de audio y vídeo (por ejemplo, av.contoso.com) como la dirección IP del servicio perimetral de audio y vídeo de uno de los servidores perimetrales del grupo de servidores.

Para implementar el equilibrio de carga DNS en la interfaz interna del grupo de servidores perimetrales, debe agregar un registro DNS A que resuelva el FQDN interno del grupo de servidores perimetrales en la dirección IP de cada servidor del grupo de servidores.

## Uso del equilibrio de carga DNS en grupos de servidores de mediación

Puede usar el equilibrio de carga DNS en grupos de servidores de mediación independientes. Todo el tráfico de medios y SIP se equilibra con el equilibrio de carga DNS.

Para implementar el equilibrio de carga DNS en un grupo de servidores de mediación, debe aprovisionar el DNS de modo que resuelva el FQDN del grupo de servidores (por ejemplo, mediationpool1.contoso.com) como las direcciones IP de todos los servidores del grupo de servidores (por ejemplo, 192.168.1.1, 192.168.1.2, etc.).

## Bloquear tráfico a un servidor con equilibrio de carga de DNS

Si utiliza el equilibrio de carga de DNS y debe bloquear el tráfico a un PC específico, no es suficiente con solo eliminar las entradas de direcciones IP del grupo FQDN. También debe eliminar la entrada DNS para el PC.

Tenga en cuenta que para el tráfico de servidor a servidor, Lync Server 2013 usa un equilibrio de carga preparado para topología. Los servidores leen la topología publicada en el Almacén de administración central para obtener los FQDN de los servidores en la topología y distribuyen automáticamente el tráfico entre los servidores. Para bloquear un servidor para que no reciba tráfico específico de servidor a servidor, debe eliminar el servidor de la topología.

