---
title: 'Lync Server 2013: Información general sobre el acceso de usuarios externos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of external user access
ms:assetid: 97aded6c-5fa3-4225-95a6-9ad094d61654
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398775(v=OCS.15)
ms:contentKeyID: 48184934
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1007dfb330aaa21dbac269f606102c51712c9bf7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755564"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-external-user-access-in-lync-server-2013"></a>Información general sobre el acceso de usuarios externos en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-11-07_

En esta documentación, usamos el término *usuario externo* para definir una categoría grande de usuarios que se comunican con los usuarios de lync Server 2013 y Lync 2013 desde fuera del firewall. Los usuarios externos que pueden autorizar para comunicar Lync Server 2013 con usuarios internos (es decir, los usuarios que inician sesión en Lync Server desde dentro del firewall) pueden incluir lo siguiente:

  - **Usuarios remotos**   usuarios de su organización que inician sesión en Lync Server desde fuera del firewall.

  - **Usuarios federados**   usuarios que tienen una cuenta con un cliente de confianza o una organización asociada, como Lync Server 2010, Lync Server 2013 u Office Communications Server 2007 R2. Los usuarios federados también pueden ser miembros de organizaciones de socios definidas con el protocolo de presencia y mensajería extensible (XMPP) a través del proxy XMPP en el servidor perimetral y la puerta de enlace XMPP en el servidor o grupo de servidores front-end. Una relación de confianza definida, denominada Federación, no está relacionada o depende de una relación de confianza de los servicios de dominio de Active Directory.
    
    <div>
    

    > [!NOTE]  
    > Una fecha de fin de vida de junio de 2014 para AOL y Yahoo! ha sido anunciado. Para obtener más información, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">compatibilidad de la conectividad de mensajería instantánea pública en Lync Server 2013</A>.

    
    </div>

  - **Usuarios de conectividad de mensajería instantánea pública**   contactos que los usuarios establecen a través de servicios de conectividad de mensajería instantánea pública (Windows Live, Yahoo\! y AOL).

  - **Usuarios móviles usuarios**   que son miembros de su organización que usan un teléfono inteligente o una tableta con un cliente de Lync Mobile inicie sesión en su implementación interna y podrá comunicarse con las otras clases de usuarios. El usuario móvil usa los servicios de movilidad que se publican a través del proxy inverso para obtener acceso a la implementación interna. Para obtener más información sobre las características y capacidades disponibles para Lync Mobile, consulte las tablas de [http://go.microsoft.com/fwlink/p/?LinkID=234777](http://go.microsoft.com/fwlink/p/?linkid=234777)comparación de clientes móviles en.

  - **Usuarios anónimos**   usuarios que no tienen una cuenta de usuario en los servicios de dominio de Active Directory de su organización o en un dominio federado admitido, pero que han recibido invitaciones para que participen de forma remota en una conferencia local.

La implementación del extremo proporciona acceso externo para los siguientes tipos de comunicación:

  - **La mensajería instantánea y**   los usuarios externos autorizados pueden participar en conversaciones y conferencias de mensajería instantánea, y pueden obtener información sobre el estado de presencia de los demás. Los usuarios de proveedores de servicios de mensajería instantánea pública pueden participar en conversaciones de mensajería instantánea con usuarios individuales de Lync Server en la organización y obtener acceso a información de presencia, pero no pueden participar en conferencias de mensajería instantánea con Lync Server. Es estrictamente una comunicación de punto a punto. La transferencia de archivos no es compatible con los usuarios de proveedores de servicios de mensajería instantánea pública, y el audio o vídeo de las comunicaciones de punto a punto es compatible con los usuarios de Windows Messenger 2011, pero no con otros usuarios de proveedores de servicios de mensajería instantánea pública.
    
    Se admiten los protocolos SIP y XMPP. Para proporcionar servicios para XMPP, consulte [planificación de SIP, Federación XMPP y mensajería instantánea pública en Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md).

  - **Las conferencias**   web autorizadas a los usuarios externos pueden participar en conferencias que se hospedan en la implementación de Lync Server. Los usuarios remotos, los usuarios federados y los usuarios anónimos pueden habilitarse para la participación en conferencias web, pero los usuarios de la mensajería instantánea pública no pueden participar en conferencias. En función de las opciones que seleccione, los usuarios habilitados para conferencias web pueden participar en el escritorio y compartir aplicaciones, y pueden actuar como organizadores o moderadores de reuniones.

  - **Conferencias a/V**   los usuarios externos autorizados pueden participar en conferencias de audio y vídeo que aloje su implementación de Lync Server. El audio o vídeo de las comunicaciones de punto a punto es compatible con los usuarios de Windows Messenger 2011, pero no con otros usuarios de proveedores de servicios de mensajería instantánea pública.

Para controlar las comunicaciones, puede configurar una o más directivas que definan cómo los usuarios de dentro y fuera de la organización se comunican entre sí. También puede configurar opciones y aplicar directivas para usuarios internos individuales o para determinados tipos de usuarios externos para controlar las comunicaciones con usuarios externos.

Roles de 2013 de Lync Server que se usan para proporcionar acceso externo:

**Servidor perimetral el**   servidor perimetral es un servidor o un grupo de servidores que ejecutan los servicios que permiten acceso externo a los servicios de mensajería instantánea y presencia, Conferencia, audio/vídeo y otros elementos multimedia (por ejemplo, la transferencia de archivos). De manera opcional, puede configurar el servidor perimetral para federarse con otras implementaciones de Lync Server o de Office Communications Server 2007 R2 y otras implementaciones de XMPP. La característica de conectividad de mensajería instantánea pública opcional está habilitada y configurada a través del servidor perimetral.

**Director**   el director es un servidor opcional o un grupo de servidores que ejecuta el rol de Director de Lync Server 2013 que previamente autentica las solicitudes de usuario y enruta las solicitudes al servidor front-end de los usuarios o al grupo de servidores front-end, pero no aloja ninguna cuenta de usuario.

**Proxy**   inverso un proxy inverso es un término general para servidores especializados que publican recursos disponibles en la red interna y recuperan información para los clientes del recurso publicado. Lync Server 2013 usa el proxy inverso para publicar varias características, como reuniones de conferencia, ubicaciones de combinación de conferencias, la libreta de direcciones, expansión de la lista de distribución, descarga del contenido de la reunión, actualizaciones de dispositivos, servicios de movilidad, etc. Se puede usar cualquier proxy inverso que cumpla los requisitos para publicar las ubicaciones de recursos que sean necesarias. Microsoft Forefront Threat Management Gateway (TMG) 2010 se usa como ejemplo para ilustrar las reglas de publicación necesarias, pero Forefront TMG 2010 no es necesario.

<div>


> [!IMPORTANT]  
> Lync Server 2013 admite IPv4 e IPv6. Windows Server&nbsp;2008&nbsp;r2, Windows Server 2012 y Windows Server 2012 R2 usan una pila doble que puede usar IPv4 y IPv6 al mismo tiempo. Esto es importante debido a la naturaleza transitoria de una implementación que se mueve de IPv4 a IPv6. IPv4 puede ser compatible en algunas áreas, donde en otras áreas de la implementación, se puede usar IPv6. Esto es especialmente importante cuando se trata de Internet y de las implementaciones internas. Los clientes externos deben comunicarse a través del proxy inverso para usar servicios como la movilidad, las reuniones, la descarga de la libreta de direcciones y otros. En la actualidad, Forefront Threat Management Gateway 2010 e Internet Security and Acceleration Server 2006 no admiten las direcciones IPv6, independientemente de la versión del sistema operativo en el que se hayan implementado. Debe planificar según corresponda en relación con el uso que usted hace de IPv6 e IPv4 en relación con clientes externos.



</div>

</div>

<span> </span>

</div>

</div>

</div>

