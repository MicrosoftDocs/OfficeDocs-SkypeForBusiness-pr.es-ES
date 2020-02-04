---
title: 'Lync Server 2013: Componentes necesarios para el acceso de usuarios externos'
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
ms.openlocfilehash: 550eb864ff7cc26eb0bfeace37759bb15b9816f6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757104"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-required-for-external-user-access-in-lync-server-2013"></a>Componentes necesarios para el acceso de usuarios externos en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-05-29_

La mayoría de los componentes perimetrales se implementan en una red perimetral. Los siguientes componentes forman la topología perimetral de la red perimetral. Excepto donde se indique lo contrario, los componentes forman parte de los [escenarios para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) y en la red perimetral. Los componentes perimetrales engloban los siguientes:

  - Edge Servers

  - Reverse proxies

  - Firewalls

  - Directores (opcional y, lógicamente, ubicado en la red interna)

  - Equilibrio de carga para topologías perimetrales escaladas (equilibrio de carga de DNS o un equilibrador de carga de hardware)
    
    <div>
    

    > [!IMPORTANT]  
    > No se admite el uso del equilibrio de carga de DNS en una interfaz y del equilibrio de carga de hardware en otra. Necesita utilizar el equilibrio de carga de hardware o de DNS en ambas interfaces.

    
    </div>

<div>

## <a name="edge-servers"></a>Servidores perimetrales

Los servidores perimetrales envían y reciben tráfico de red para los servicios ofrecidos por los usuarios externos en la implementación interna. El servidor perimetral ejecuta los siguientes servicios:

  - **Servicio perimetral de acceso**   el servicio perimetral de acceso proporciona un único punto de conexión de confianza para el tráfico de protocolo de inicio de sesión entrante y saliente (SIP).

  - **Servicio perimetral de conferencias web**   el servicio perimetral de conferencias web permite a los usuarios externos unirse a reuniones hospedadas en la implementación interna de Lync Server 2013.

  - **Servicio perimetral a/v**   el servicio a/v Edge hace que el audio, el video, el uso compartido de aplicaciones y la transferencia de archivos estén disponibles para los usuarios externos. Los usuarios pueden agregar audio y vídeo a las reuniones que incluyen participantes externos, y pueden comunicarse con audio o video directamente con un usuario externo en sesiones punto a punto. El servicio perimetral A/V también proporciona compatibilidad con el uso compartido de escritorio y la transferencia de archivos.

  - **Servicio de proxy XMPP**   el servicio de proxy XMPP acepta y envía mensajes de protocolo de presencia y mensajería extensible (XMPP) a los socios de XMPP federados configurados.

Los usuarios externos autorizados pueden tener acceso a los servidores perimetrales para conectarse a la implementación interna de Lync Server 2013, pero los servidores perimetrales no proporcionan medios para ningún otro tipo de acceso a la red interna.

<div>


> [!NOTE]  
> Los servidores perimetrales se implementan para proporcionar conexiones para clientes de Lync habilitados y otros servidores Microsoft Edge (como en los escenarios de Federación). No están diseñados para permitir conexiones de otros tipos de clientes o servidores de punto final. El servidor de puerta de enlace XMPP puede implementarse para permitir conexiones con socios XMPP configurados. El servidor perimetral y la puerta de enlace XMPP solo admiten conexiones de punto final de estos tipos de Federación y cliente.



</div>

</div>

<div>

## <a name="reverse-proxy"></a>Proxy inverso

El proxy inverso es necesario para lo siguiente:

  - Para permitir que los usuarios se conecten a reuniones o conferencias de acceso telefónico local con direcciones URL simples

  - Para permitir que los usuarios externos descarguen contenido de la reunión

  - Para permitir a los usuarios externos expandir grupos de distribución

  - Para permitir que el usuario obtenga un certificado basado en el usuario para la autenticación basada en certificados de cliente

  - Para permitir que los usuarios remotos descarguen archivos desde el servidor de la libreta de direcciones o para enviar consultas al servicio de consulta Web de la libreta de direcciones

  - Para permitir que los usuarios remotos obtengan actualizaciones del software del cliente y del dispositivo

  - Para habilitar dispositivos móviles para detectar automáticamente los servidores front-end que ofrecen servicios de movilidad

  - Para habilitar las notificaciones de inserción en dispositivos móviles desde el Office 365 o servicios de notificaciones push de Apple

Para obtener más información relacionada con los proxies inversos y los requisitos que deben cumplir los proxies inversos, consulte los detalles de [los requisitos de configuración para el proxy inverso en Lync Server 2013](lync-server-2013-configuration-requirements-for-reverse-proxy.md).

<div>


> [!NOTE]  
> Los usuarios externos no necesitan una conexión de red privada virtual (VPN) a la organización para poder participar en las comunicaciones con Lync Server 2013. Si ha implementado tecnología VPN en su organización y los usuarios usan la VPN para Lync, el tráfico multimedia (como las videoconferencias) puede verse afectado negativamente. Debe considerar proporcionar un medio para que el tráfico de medios se conecte directamente con el servicio perimetral de AV y omita la red privada virtual. Para obtener más información, vea el artículo del blog de NextHop, "habilitar medios de Lync para eludir <A href="http://go.microsoft.com/fwlink/p/?linkid=256532">http://go.microsoft.com/fwlink/p/?LinkId=256532</A>un túnel VPN" en.



</div>

</div>

<div>

## <a name="firewall"></a>Firewall

Puede implementar su topología perimetral solo con un firewall externo o con firewalls externos e internos. Las arquitecturas de escenario incluyen dos firewalls. El uso de dos firewalls es el método recomendado, ya que garantiza el enrutamiento estricto desde un perímetro de red al otro y protege la implementación interna detrás de dos niveles de Firewall.

</div>

<div>

## <a name="director"></a>Director

Un director es un rol de servidor independiente y opcional de Lync Server 2013 que no aloja cuentas de usuario o proporciona servicios de presencia o de conferencia. Actúa como un servidor interno del próximo salto al que un servidor perimetral enruta el tráfico SIP entrante destinado a los servidores internos. El director preautentica las solicitudes entrantes y las redirige al grupo de servidores o al grupo de servidores principal del usuario. Al autenticar en el director, puede colocar solicitudes de cuentas de usuario desconocidas para la implementación.

Un director ayuda a aislar servidores Standard Edition y servidores de aplicaciones para el usuario de las agrupaciones front end de Enterprise Edition de tráfico malintencionado, como ataques de denegación de servicio (DoS). Si la red se inunda con tráfico externo no válido en tal ataque, el tráfico termina en el director. Para obtener más información sobre el uso de los directores, consulte [escenarios del Director de Lync Server 2013](lync-server-2013-scenarios-for-the-director.md).

</div>

<div>

## <a name="see-also"></a>Vea también


[Requisitos del equilibrador de carga de hardware en Lync Server 2013](lync-server-2013-hardware-load-balancer-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

