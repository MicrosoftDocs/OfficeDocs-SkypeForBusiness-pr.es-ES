---
title: 'Lync Server 2013: información general sobre el acceso de usuarios externos'
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
ms.openlocfilehash: cdf596a16fbed1cab1b622b373febb0f173344cb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216436"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-external-user-access-in-lync-server-2013"></a>Información general sobre el acceso de usuarios externos en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-11-07_

En esta documentación, usamos el término *usuario externo* para definir una categoría grande de usuarios que se comunican con los usuarios de lync Server 2013 y Lync 2013 desde fuera del firewall. Los usuarios externos que puede autorizar para comunicar Lync Server 2013 con usuarios internos (es decir, los usuarios que inician sesión en Lync Server desde dentro del firewall) pueden incluir lo siguiente:

  - **Usuarios remotos**   : usuarios de su organización que inician sesión en Lync Server desde fuera del firewall.

  - **Usuarios federados**   : usuarios que tienen una cuenta con una organización asociada o de cliente de confianza, como Lync Server 2010, Lync Server 2013 u Office Communications Server 2007 R2. Los usuarios federados también pueden ser miembros de organizaciones asociadas definidas mediante el protocolo extensible de mensajería y presencia (XMPP) mediante el proxy XMPP en el servidor perimetral y la puerta de enlace XMPP en el servidor front-end o grupo de servidores. Una relación de confianza definida, denominada Federación, no está relacionada con ni depende de una relación de confianza de los servicios de dominio de Active Directory.
    
    <div>
    

    > [!NOTE]  
    > Una fecha de finalización del ciclo de vida de junio de 2014 para AOL y Yahoo! se ha anunciado. Para obtener más información, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">compatibilidad con la conectividad de mensajería instantánea pública en Lync Server 2013</A>.

    
    </div>

  - **Usuarios de conectividad de mensajería instantánea pública**   contactos que los usuarios establecen a través de servicios de conectividad de mensajería instantánea pública (Windows Live, Yahoo\! y AOL).

  - **Usuarios móviles usuarios**   que son miembros de su organización que usan un teléfono o una tableta inteligentes que ejecutan un cliente móvil de Lync inicie sesión en su implementación interna y puedan comunicarse con las demás clases de usuarios. El usuario móvil usa los servicios de movilidad que se publican a través del proxy inverso para obtener acceso a la implementación interna. Para obtener más información sobre las características y capacidades disponibles para Lync Mobile, consulte las tablas de [https://go.microsoft.com/fwlink/p/?LinkID=234777](https://go.microsoft.com/fwlink/p/?linkid=234777)comparación de clientes móviles en.

  - **Usuarios anónimos**   usuarios que no tienen una cuenta de usuario en los servicios de dominio de Active Directory de la organización o en un dominio federado admitido, pero que recibieron invitaciones para participar remotamente en una conferencia local.

La implementación perimetral proporciona acceso externo para los siguientes tipos de comunicación:

  - **Los usuarios de mi y presencia**   externos autorizados pueden participar en conversaciones y conferencias de mensajería instantánea, y pueden obtener información sobre el estado de presencia de uno de otro. Los usuarios de proveedores de servicios de mensajería instantánea pública pueden participar en las conversaciones de mensajería instantánea con usuarios individuales de Lync Server en la organización y acceder a la información de presencia, pero no pueden participar en conferencias de mensajería instantánea entre varios participantes con Lync Server. Los usuarios de proveedores de servicios de mensajería instantánea pública no pueden utilizar la transferencia de archivos y el audio y el vídeo en comunicaciones de punto a punto. La transferencia de archivos no es compatible con los usuarios de proveedores de servicios de mensajería instantánea pública y el audio o vídeo de las comunicaciones punto a punto se admite para usuarios de Windows Messenger 2011, pero no para otros usuarios de proveedores de servicios de mensajería instantánea pública.
    
    Se admiten los protocolos SIP y XMPP. Para proporcionar servicios para XMPP, vea [planeación de SIP, la Federación XMPP y la mensajería instantánea pública en Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md).

  - **Conferencia web los**   usuarios externos autorizados pueden participar en conferencias que se hospedan en su implementación de Lync Server. Los usuarios remotos, federados y anónimos pueden habilitarse para la participación en conferencias web, pero los usuarios de mensajería instantánea pública no pueden participar en conferencias. Según las opciones que seleccione, los usuarios habilitados para conferencia web podrán participar en el uso compartido de aplicaciones y escritorios, además de actuar como organizadores o moderadores de reuniones.

  - **Conferencia a/V**   los usuarios externos autorizados pueden participar en conferencias de audio y vídeo que hospede su implementación de Lync Server. El audio y vídeo de las comunicaciones punto a punto se admite para usuarios de Windows Messenger 2011, pero no para otros usuarios de proveedores de servicios de mensajería instantánea pública.

Para controlar las comunicaciones, puede configurar una o más directivas que definen cómo los usuarios de dentro y fuera de la organización se comunican entre sí. Además, puede configurar otros parámetros y aplicar directivas para usuarios internos individuales o para tipos específicos de usuarios externos para controlar las comunicaciones con usuarios externos.

Lync Server 2013 roles que se usan para proporcionar acceso externo:

**Servidor perimetral el**   servidor perimetral es un servidor o un grupo de servidores que ejecutan los servicios que permiten el acceso externo a la mensajería instantánea y la presencia, la Conferencia, el audio/vídeo y otros servicios multimedia (por ejemplo, transferencia de archivos). Si lo desea, puede configurar el servidor perimetral para que se federe con otras implementaciones de Lync Server o de Office Communications Server 2007 R2, y otras implementaciones de XMPP. La característica opcional de conectividad de mensajería instantánea pública se habilita y configura mediante el servidor perimetral.

**Director**   el director es un servidor opcional o un grupo de servidores que ejecuta el rol de Director de Lync Server 2013 que realiza la autenticación previa de solicitudes de usuario y enruta las solicitudes al servidor front-end o al grupo de servidores front-end principal de los usuarios, pero no aloja ninguna cuenta de usuario.

**Proxy**   inverso un proxy inverso es un término general que se refiere a los servidores especializados que publican recursos disponibles en la red interna y recuperan información para los clientes del recurso publicado. Lync Server 2013 usa el proxy inverso para publicar una serie de características, como reuniones de conferencia, ubicaciones de unión de conferencia, la libreta de direcciones, expansión de la lista de distribución, descarga del contenido de la reunión, actualizaciones de dispositivos, servicios de movilidad, etc. Se puede usar cualquier proxy inverso que pueda cumplir con los requisitos para la publicación de las ubicaciones de recursos necesarias. Microsoft Forefront Threat Management Gateway (TMG) 2010 se usa como ejemplo para ilustrar las reglas de publicación necesarias, pero Forefront TMG 2010 no es necesario.

<div>


> [!IMPORTANT]  
> Lync Server 2013 admite tanto IPv4 como IPv6. Windows Server&nbsp;2008&nbsp;r2, Windows Server 2012 y Windows Server 2012 R2 usan una pila dual que puede usar tanto IPv4 como IPv6 simultáneamente. Esto es importante debido a la naturaleza transitoria de una implementación que se mueve de IPv4 a IPv6. IPv4 puede ser compatible en algunas áreas, donde en otras áreas de la implementación, se puede usar IPv6. Esto es especialmente importante cuando se refieren a Internet y a las implementaciones internas. Los clientes externos deben comunicarse a través del proxy inverso para usar servicios como la movilidad, las reuniones, la descarga de la libreta de direcciones y otras. Actualmente, Forefront Threat Management Gateway 2010 y Internet Security and Acceleration Server 2006 no admiten el direccionamiento IPv6, independientemente de la versión del sistema operativo en la que se implementen. Debe planear en consecuencia en relación con el uso de IPv6 e IPv4 a medida que se relacionen con los clientes externos.



</div>

</div>

<span> </span>

</div>

</div>

</div>

