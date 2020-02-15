---
title: 'Lync Server 2013: componentes necesarios para el acceso de usuarios externos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components required for external user access
ms:assetid: 2d0f9817-14e7-4109-95dc-62420e3c29e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425779(v=OCS.15)
ms:contentKeyID: 48183711
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e225f63da97ea48d98a5a2540a6b35a9c63c08f2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007960"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-required-for-external-user-access-in-lync-server-2013"></a>Componentes necesarios para el acceso de usuarios externos en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-05-29_

La mayoría de los componentes perimetrales se implementan en una red perimetral. Los siguientes componentes conforman la topología perimetral de una red perimetral. Excepto donde se indique, los componentes forman parte de los [escenarios para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) y se encuentran en la red perimetral. Los componentes perimetrales engloban los siguientes:

  - Servidores perimetrales

  - Proxies inversos

  - Firewalls

  - Directores (opcionales y ubicados lógicamente en la red interna)

  - Equilibrio de carga para topologías perimetrales escaladas (equilibrio de carga de DNS o un equilibrador de carga de hardware)
    
    <div>
    

    > [!IMPORTANT]  
    > No se admite el uso del equilibrio de carga de DNS en una interfaz y del equilibrio de carga de hardware en otra. Debe utilizar el equilibrio de carga de hardware o de DNS en ambas interfaces.

    
    </div>

<div>

## <a name="edge-servers"></a>Servidores perimetrales

Los servidores perimetrales envían y reciben tráfico de red para los servicios ofrecidos por la implementación interna por los usuarios externos. El servidor perimetral ejecuta los siguientes servicios:

  - **Servicio perimetral de acceso**   el servicio perimetral de acceso proporciona un único punto de conexión de confianza para el tráfico SIP (Protocolo de inicio de sesión) saliente y entrante.

  - **Servicio perimetral de conferencia web**   el servicio perimetral de conferencia web permite a los usuarios externos unirse a reuniones hospedadas en la implementación interna de Lync Server 2013.

  - **Servicio perimetral a/v**   el servicio perimetral a/v hace que el audio, vídeo, uso compartido de aplicaciones y transferencia de archivos estén disponibles para los usuarios externos. Los usuarios pueden agregar audio y vídeo a las reuniones que incluyen participantes externos, y pueden comunicarse mediante audio o vídeo directamente con un usuario externo en sesiones punto a punto. De igual modo, este servicio permite el uso compartido de escritorio y la transferencia de archivos.

  - **Servicio Proxy XMPP**   el servicio Proxy XMPP acepta y envía mensajes del Protocolo de mensajería y presencia extensible (XMPP) a y desde socios federados de XMPP configurados.

Los usuarios externos autorizados pueden tener acceso a los servidores perimetrales para conectarse a la implementación interna de Lync Server 2013, pero los servidores perimetrales no proporcionan medios para otros tipos de acceso a la red interna.

<div>


> [!NOTE]  
> Los servidores perimetrales se implementan para proporcionar conexiones para los clientes de Lync habilitados y otros servidores de Microsoft Edge (como en los escenarios de Federación). Estos servidores no están diseñados para permitir conexiones desde otros tipos de servidores o clientes de extremos. El servidor de puerta de enlace XMPP puede implementarse para permitir conexiones con socios XMPP configurados. El servidor perimetral y la puerta de enlace XMPP solo admite conexiones de extremos procedentes de estos clientes y de estos tipos de federación



</div>

</div>

<div>

## <a name="reverse-proxy"></a>Proxy inverso

El proxy inverso se requiere para:

  - Dejar que los usuarios se conecten a reuniones o conferencias de acceso telefónico usando direcciones URL sencillas

  - Dejar que los usuarios descarguen el contenido de las reuniones

  - Dejar que los usuarios externos expandan grupos de distribución

  - Dejar que los usuarios obtengan un certificado individual de usuario para la autenticación basada en certificados

  - Dejar que los usuarios remotos descarguen archivos del servidor de libreta de direcciones o envíen consultas al servicio de consulta web de la libreta de direcciones

  - Dejar que los usuarios remotos obtengan actualizaciones de software de dispositivo y de cliente

  - Para habilitar dispositivos móviles para detectar automáticamente servidores front-end que ofrecen servicios de movilidad

  - Para habilitar notificaciones de inserción para dispositivos móviles desde los servicios de notificación de inserción de Office 365 o Apple

Para obtener información adicional relacionada con los proxies inversos y los requisitos que deben cumplir los servidores proxy inversos, consulte los detalles de [los requisitos de configuración para el proxy inverso en Lync Server 2013](lync-server-2013-configuration-requirements-for-reverse-proxy.md).

<div>


> [!NOTE]  
> Los usuarios externos no necesitan una conexión de red privada virtual (VPN) a la organización para poder participar en las comunicaciones con Lync Server 2013. Si ha implementado la tecnología VPN en su organización y los usuarios usan la VPN para Lync, el tráfico multimedia (por ejemplo, la videoconferencia) puede verse afectado negativamente. Debe considerar la posibilidad de ofrecer un medio para que el tráfico de medios se conecte directamente con el servicio perimetral AV y omita la VPN. Para obtener más información, consulte el artículo del blog NextHop, "Enabling Lync media to bypass a VPN Tunnel <A href="http://go.microsoft.com/fwlink/p/?linkid=256532">http://go.microsoft.com/fwlink/p/?LinkId=256532</A>", en.



</div>

</div>

<div>

## <a name="firewall"></a>Éste

La topología perimetral se puede implementar con únicamente un firewall externo o con un firewall interno y otro externo. Las arquitecturas de escenario incluyen dos firewalls. El uso de dos firewall es el método que se recomienda, en tanto garantiza el enrutamiento estricto desde un perímetro de red al otro, además de proteger la implementación interna detrás de dos niveles de firewall.

</div>

<div>

## <a name="director"></a>Dirección

Un director es un rol de servidor opcional e independiente en Lync Server 2013 que no aloja cuentas de usuario ni proporciona servicios de presencia o conferencia. Actúa como un servidor interno del próximo salto en el que un servidor perimetral enruta el tráfico SIP entrante destinado a los servidores internos. El director autentica las solicitudes de entrada y las redirige al servidor o grupo de servidores principales del usuario. Mediante la autenticación previa en el director, puede colocar solicitudes de cuentas de usuario que son desconocidas para la implementación.

Un director ayuda a aislar los servidores Standard Edition y los servidores front-end de los grupos de servidores front-end Enterprise Edition de tráfico malintencionado, como los ataques por denegación de servicio (DoS). Si la red está inundada con tráfico externo no válido en un ataque de este tipo, el tráfico termina en el director. Para obtener más información sobre el uso de los directores, consulte [escenarios del Director en Lync Server 2013](lync-server-2013-scenarios-for-the-director.md).

</div>

<div>

## <a name="see-also"></a>Vea también


[Requisitos del equilibrador de carga de hardware para Lync Server 2013](lync-server-2013-hardware-load-balancer-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

