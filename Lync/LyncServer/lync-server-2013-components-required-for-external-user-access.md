---
title: 'Lync Server 2013: Componentes necesarios para el acceso de usuarios externos'
TOCTitle: Componentes necesarios para el acceso de usuarios externos
ms:assetid: 2d0f9817-14e7-4109-95dc-62420e3c29e2
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg425779(v=OCS.15)
ms:contentKeyID: 48274783
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Componentes necesarios para el acceso de usuarios externos en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

La mayoría de los componentes perimetrales se implementan en una red perimetral (también denominada red perimetral o subred filtrada). Los siguientes componentes conforman la topología perimetral de una red perimetral. A menos que se indique lo contrario, los componentes forman parte de los [Escenarios para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) y se encuentran en la red perimetral. Los componentes perimetrales engloban los siguientes:

  - Servidores perimetrales

  - Proxies inversos

  - Firewalls

  - Directores (opcional, y lógicamente ubicado en la red interna)

  - Equilibrio de carga para topologías perimetrales escaladas (equilibrio de carga de DNS o un equilibrador de carga de hardware)
    
    > [!IMPORTANT]  
    > No se admite el uso del equilibrio de carga de DNS en una interfaz y del equilibrio de carga de hardware en otra. Debe utilizar el equilibrio de carga de hardware o de DNS en ambas interfaces.
    


## Servidores perimetrales

El Servidores perimetrales envía y recibe el tráfico de red para los servicios ofrecidos por parte de los usuarios externos de la implementación interna. El Servidor perimetral ejecuta los siguientes servicios:

  - **Servicio perimetral de acceso**   El servicio perimetral de acceso proporciona un único punto de conexión de confianza para el tráfico SIP (protocolo de inicio de sesión) saliente y entrante.

  - **Servicio perimetral de conferencia web**   El servicio perimetral de conferencia web permite a los usuarios externos unirse a reuniones hospedadas en la implementación interna del Lync Server 2013.

  - **Servicio perimetral A/V**   El servicio perimetral A/V hace que los usuarios externos puedan disfrutar de audio, vídeo, uso compartido de aplicaciones y transferencia de archivos. Los usuarios pueden agregar audio y vídeo a las reuniones con participantes externos y compartir audio y vídeo directamente con un usuario externo en sesiones punto a punto. De igual modo, este servicio permite el uso compartido de escritorio y la transferencia de archivos.

  - **Servicio proxy XMPP**   El servicio proxy XMPP acepta y envía mensajes de protocolo extensible de mensajería y presencia (XMPP) desde los socios federados de XMPP configurados.

Los usuarios externos autorizados pueden tener acceso al Servidores perimetrales para conectarse a la implementación interna de Lync Server 2013, si bien no podrán tener acceso a ningún otro elemento de la red interna a través de estos servidores Servidores perimetrales.


> [!NOTE]
> Los servidores perimetrales se implementan para proporcionar conexiones de clientes habilitados para usar Lync y otros servidores perimetrales de Microsoft (como en escenarios de federación). No están diseñados para permitir conexiones de otros tipos servidor o cliente de extremo. El servidor de la puerta de enlace XMPP puede implementarse para permitir conexiones con socios XMPP configurados. La puerta de enlace XMPP y el servidor perimetral solo son compatibles con conexiones de extremo de estos tipos de cliente y federación.



## Proxy inverso

El proxy inverso se requiere para:

  - Dejar que los usuarios se conecten a reuniones o conferencias de acceso telefónico usando direcciones URL sencillas

  - Dejar que los usuarios descarguen el contenido de las reuniones

  - Dejar que los usuarios externos expandan grupos de distribución

  - Dejar que los usuarios obtengan un certificado individual de usuario para la autenticación basada en certificados

  - Dejar que los usuarios remotos descarguen archivos del servidor de libreta de direcciones o envíen consultas al servicio de consulta web de la libreta de direcciones

  - Dejar que los usuarios remotos obtengan actualizaciones de software de dispositivo y de cliente

  - Habilitar dispositivos móviles para detectar automáticamente servidores front-end Servidores front-end que ofrecen servicios de movilidad

  - Habilitar notificaciones de inserción para dispositivos móviles desde los servicios de notificación de inserción de Office 365 o Apple

Para obtener información adicional relacionada con los servidores proxy inversos y los requisitos que estos deben cumplir, vea los detalles en [Requisitos de configuración del proxy inverso de Lync Server 2013](lync-server-2013-configuration-requirements-for-reverse-proxy.md).


> [!NOTE]
> Los usuarios externos no necesitan una conexión de red privada virtual (VPN) a su organización para participar en las comunicaciones utilizando Lync Server 2013. Si ha implementado una tecnología VPN en la organización y los usuarios utilizan la VPN para Lync, el tráfico multimedia (como conferencias de video) puede verse negativamente afectado. Debería considerar la posibilidad de brindar un medio para que el tráfico multimedia se conecte al servicio perimetral AV directamente y desviarse de la VPN. Para obtener información detallada, consulte el artículo del blog NextHop, “Enabling Lync Media to Bypass a VPN Tunnel”, ("Habilitar desvío de medios de Lync de un túnel VPN") disponible en <A class=uri href="http://go.microsoft.com/fwlink/?linkid=256532">http://go.microsoft.com/fwlink/?linkid=256532</A>.



## Firewall

La topología perimetral se puede implementar con únicamente un firewall externo o con un firewall interno y otro externo. Las arquitecturas de referencia incluyen dos firewall. El uso de dos firewall es el método que se recomienda, en tanto garantiza el enrutamiento estricto desde un perímetro de red al otro, además de proteger la implementación interna detrás de dos niveles de firewall.

## Director

Un Director es un rol de servidor independiente en Lync Server 2013 que no contiene cuentas de usuario principales ni proporciona servicios de presencia o conferencia; en su lugar, actúa como servidor del próximo salto interno al que un Servidor perimetral enruta el tráfico SIP dirigido a los servidores internos. El Director autentica previamente las solicitudes internas y las redirige al servidor o grupo de servidores principal del usuario. La autenticación previa del Director permite la colocación de solicitudes desde las cuentas de usuario desconocidas para la implementación.

Un Director ayuda a aislar los servidores Standard Edition y los servidores front-end de los grupos front-end de Enterprise Edition del tráfico malicioso, como los ataques de denegación de servicio (DoS). Si la red se inunda de tráfico externo no válido en un ataque de estas características, este tráfico termina en el Director. Si desea más información sobre el uso de Directores, consulte [Escenarios para el director en Lync Server 2013](lync-server-2013-scenarios-for-the-director.md).

## Vea también

#### Conceptos

[Requisitos del equilibrador de carga de hardware en Lync Server 2013](lync-server-2013-hardware-load-balancer-requirements.md)

