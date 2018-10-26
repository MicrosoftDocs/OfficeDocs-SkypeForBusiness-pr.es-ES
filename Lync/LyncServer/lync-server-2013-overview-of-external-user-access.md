---
title: 'Lync Server 2013: Información general sobre el acceso de usuarios externos'
TOCTitle: Información general sobre el acceso de usuarios externos
ms:assetid: 97aded6c-5fa3-4225-95a6-9ad094d61654
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398775(v=OCS.15)
ms:contentKeyID: 48276095
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Información general sobre el acceso de usuarios externos en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

En esta documentación, se usa el término *usuario externo* para definir a una gran categoría de usuarios que se comunican con sus usuarios de Lync Server 2013 y Lync 2013 desde fuera del firewall. Los usuarios externos que puede autorizar para que usen Lync Server 2013 para comunicarse con usuarios internos (es decir, usuarios que inician sesión en Lync Server desde dentro del firewall) son:

  - **Usuarios remotos**   Usuarios de su organización que inician sesión en Lync Server desde fuera del firewall.

  - **Usuarios federados :** usuarios que tienen una cuenta con un cliente o una organización socia de confianza, como Lync Server 2010, Lync Server 2013 o Office Communications Server 2007 R2. Los usuarios federados también pueden ser miembros de organizaciones de socios definidas utilizando el Protocolo extensible de mensajería y presencia (XMPP) mediante el proxy XMPP del Servidor perimetral y de la puerta de enlace XMPP del Servidor front-end o del grupo. Una relación de confianza definida, denominada una federación, no está relacionada ni depende de la relación de confianza de Servicios de dominio de Active Directory.
    

    > [!NOTE]
    > Se anunció que la fecha de finalización de AOL y Yahoo! será en junio de 2014. Para obtener detalles, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Soporte para la conectividad de mensajería instantánea pública en Lync Server 2013</A>.



  - **Usuarios de Conectividad de mensajería instantánea pública**   Contactos que sus usuarios establecen mediante servicios de conectividad de mensajería instantánea pública (Windows Live, Yahoo\! y AOL).

  - **Usuarios móviles :** usuarios miembros de su organización que utilizan un smartphone o tableta que ejecuta un inicio de sesión de cliente de Lync Mobile en su implementación interna y que son capaces de comunicarse con los otros tipos de usuarios. El usuario móvil utiliza los servicios de movilidad publicados en el servidor inverso para acceder a la implementación interna. Para obtener información detallada acerca de las funciones y capacidades disponibles para Lync Mobile, consulte las tablas de comparación de clientes en [http://go.microsoft.com/fwlink/?linkid=234777\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=234777%26clcid=0xc0a).

  - **Usuarios anónimos :** usuarios que no disponen de una cuenta de usuario en los Servicios de dominio de Active Directory de la organización o en un dominio federado permitido, pero que han recibido una invitación para participar de forma remota en una conferencia local.

La implementación perimetral sirve para autenticar estos tipos de usuarios externos y controlar el acceso externo para los siguientes tipos de comunicación:

  - **Mensajería instantánea y presencia :** los usuarios externos autorizados pueden participar en conversaciones y conferencias de mensajería instantánea y pueden obtener información sobre el estado de presencia de otros usuarios. Los usuarios de proveedores del servicio de mensajería instantánea pública pueden participar en conversaciones de mensajería instantánea con usuarios individuales de Lync Server de la misma organización y obtener acceso a información de presencia, pero no pueden participar en conferencias de mensajería instantánea entre varias partes de Lync Server, sino que se restringen a comunicación punto a punto. Los usuarios de proveedores de servicios de mensajería instantánea pública no pueden utilizar la transferencia de archivos, y el audio y el vídeo en comunicaciones de punto a punto solo se permite a los usuarios de Windows Messenger y no a los de proveedores de servicios de mensajería instantánea pública.
    
    Se admiten los protocolos SIP y XMPP. Para ofrecer servicios para XMPP, consulte [Planeación de la federación SIP, la federación XMPP y la mensajería instantánea pública en Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md).

  - **Conferencia web :** los usuarios externos autorizados pueden participar en conferencias hospedadas en la implementación de Lync Server. Los usuarios remotos, federados y anónimos pueden habilitarse para la participación en conferencias web, pero los usuarios de mensajería instantánea pública no pueden participar en conferencias. Según las opciones que seleccione, los usuarios habilitados para conferencia web podrán participar en el uso compartido de aplicaciones y escritorios, además de actuar como organizadores o moderadores de reuniones.

  - **Conferencia A/V :** los usuarios externos autorizados pueden participar en conferencias de audio y video que hospeda su host de Lync Server. Los usuarios de Windows Messenger pueden utilizar el audio y el video en las comunicaciones punto a punto, pero no lo pueden hacer otros usuarios de proveedores de servicios de mensajería instantánea.

Para controlar las comunicaciones a través del firewall, puede configurar una o más directivas que sirvan para definir el modo en que se comunican los usuarios de dentro y fuera del firewall. Además, puede configurar otros parámetros y aplicar directivas para usuarios internos individuales o para tipos específicos de usuarios externos para controlar las comunicaciones con usuarios externos.

Roles de Lync Server 2013 que se utilizan para ofrecer acceso externo:

**Servidor perimetral :** el Servidor perimetral es un servidor o grupo de servidores que ejecuta los servicios que permiten el acceso externo a los servicios de mensajería instantánea y presencia, conferencia, audio y video y otros medios (por ejemplo, la transferencia de archivos). Opcionalmente, puede configurar el Servidor perimetral para establecer relaciones de federación con las demás implementaciones de Lync Server o Office Communications Server 2007 R2 y otras federaciones XMPP. La característica opcional de conectividad de mensajería instantánea pública se habilita y se configura mediante el Servidor perimetral.

**Director :** el Director es un servidor o grupo de servidores opcional que ejecuta el rol de Lync Server 2013  Director que autentica previamente las solicitudes de los usuarios y las redirige al inicio de los usuarios de Servidor front-end o Grupo de servidores front-end, pero no hospeda ninguna cuenta de usuario.

**Servidor inverso :** un servidor inverso es un término general para los servidores especializados que publican recursos disponibles en la red interna y recuperan información para los clientes desde el recurso publicado. Lync Server 2013 utiliza el servidor inverso para publicar varias características, como las reuniones de conferencia, las ubicaciones de unión a conferencias, la libreta de direcciones, la expansión de la lista de distribución, la descarga del contenido de las reuniones, las actualizaciones de los dispositivos, los servicios de movilidad, y mucho más. Se puede utilizar cualquier servidor inverso que cumpla los requisitos de la publicación de las ubicaciones de recursos necesarias. Microsoft Forefront Threat Management Gateway (TMG) 2010 se utiliza como ejemplo para los fines de ilustración de las reglas de publicación necesarias, pero Forefront TMG 2010 no es necesario.

> [!IMPORTANT]  
> Lync Server 2013 admite tanto IPv4 como IPv6. Windows Server 2008 R2, Windows Server 2012 y Windows Server 2012 R2 usan una pila doble que puede usar IPv4 e IPv6 simultáneamente. Esto es importante debido a la naturaleza transicional de una implementación que se mueve de IPv4 a IPv6. IPv4 se puede admitir en algunas áreas, mientras que IPv6 se puede utilizar en otras áreas de la implementación. Esto es especialmente importante cuando hay implementaciones de Internet e internas implicadas. Los clientes externos deben comunicarse a través del proxy inverso para usar servicios como movilidad, reuniones o descarga de libretas de direcciones, entre otros. Actualmente, Forefront Threat Management Gateway 2010 e Internet Security and Acceleration Server 2006 no admiten el direccionamiento IPv6, independientemente de la versión del sistema operativo donde estén implementados. Debe realizar la planeación de acuerdo con el uso que haga de IPv6 e IPv4 en relación con los clientes externos.


