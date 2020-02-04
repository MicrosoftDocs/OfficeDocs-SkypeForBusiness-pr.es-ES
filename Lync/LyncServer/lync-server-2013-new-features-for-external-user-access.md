---
title: 'Lync Server 2013: Nuevas características para acceso de usuario externo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New features for external user access
ms:assetid: 99da6bd5-ec14-4ad9-8f7d-37fbddf567dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398794(v=OCS.15)
ms:contentKeyID: 48184884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d8c27df6befdba620407b3b1fd4fe537b8da831d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723980"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-features-for-external-user-access-in-lync-server-2013"></a>Nuevas características para acceso de usuario externo en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-17_

Lync Server 2013 presenta nuevas características que amplían las características y los métodos de comunicación para los usuarios. Además, Lync Server 2013 introduce cambios en los servicios existentes para mejorar la integración y la ampliación de los servicios que están disponibles para su organización. A continuación se resume un resumen de los cambios que pueden afectar a la planificación y la implementación de los servicios del servidor perimetral 2013 de Lync Server.

  - **La compatibilidad con IPv6 con las direcciones**   de Lync Server 2013 admite el direccionamiento IPv6 para todos los servicios de servidor perimetral. Si ha proporcionado direcciones IPv6 para las interfaces mediante la configuración de Windows Server, puede usar direcciones IPv6 en la configuración de su servidor perimetral a través de la configuración de dirección IP en el generador de topologías.
    
    <div>
    

    > [!IMPORTANT]  
    > El uso de direcciones IPv6 en Lync Server 2013 depende de la compatibilidad de IPv6 en los enrutadores y los firewalls implementados por su organización, así como la compatibilidad con el proveedor de servicios de Internet.

    
    </div>

  - **El protocolo de presencia y mensajería extensible (XMPP)**   Lync Server 2013 introduce un proxy XMPP totalmente integrado (implementado en los servidores perimetrales) y una puerta de enlace XMPP implementada en los servidores front-end. Puede implementar la Federación XMPP como un componente opcional. Agregar y configurar el proxy XMPP y la puerta de enlace XMPP permiten a los usuarios de Microsoft Lync 2013 agregar contactos de socios basados en XMPP para mensajería instantánea (mi) y presencia.
    
    <div>
    

    > [!NOTE]  
    > Actualmente, los servicios XMPP de Lync Server 2013 solo proporcionan mensajería instantánea y presencia entre los clientes de Lync y los contactos basados en XMPP.

    
    </div>

  - **Servicios de movilidad para clientes**   móviles introducidos en una actualización de cliente para Lync Server 2010, los servicios de movilidad de Lync Server 2013 permiten clientes móviles de Microsoft Lync en teléfonos móviles y tabletas con dispositivos móviles compatibles de Apple iOS, Android, Windows Phone o Nokia para realizar estas actividades, como enviar y recibir mensajes instantáneos, ver contactos y ver presencia. Además, los dispositivos móviles admiten algunas características de Enterprise Voice, como hacer clic para unirse a una conferencia, llamar a través del trabajo, acceso a un número único, correo de voz y notificación de llamada perdida.
    
    <div>
    

    > [!NOTE]  
    > Los servicios de movilidad usan el proxy inverso y los servicios publicados que se implementan en los servidores front-end. No es necesario realizar cambios en los servidores perimetrales.

    
    </div>

  - **Los directores son un rol**   opcional la función del servidor Director en la topología de Lync Server 2013 no ha cambiado. Aún, hospeda servicios Web, autentica previamente las solicitudes de usuarios entrantes y dirige a los usuarios externos a su grupo de servidores principales. Cambiar el director de un rol recomendado a un rol opcional no disminuye el valor del Director, pero enfatiza la reducción del número de servidores y otros requisitos de hardware (por ejemplo, los equilibradores de carga de hardware del Director) sin poner en peligro las características y la funcionalidad. Como los servidores front-end pueden hacer el mismo trabajo que el director sin impacto alguno en los servicios proporcionados, también puede implementar directores si así lo desea. Puede excluir sin riesgos al director con la confianza de que los servidores front-end proporcionarán los mismos servicios en su lugar.

<div>

## <a name="see-also"></a>Vea también


[Planificación y configuración de IPv6 en Lync Server 2013](lync-server-2013-planning-for-and-configuring-ipv6.md)  


[Planear acceso de usuarios externos en Lync Server 2013](lync-server-2013-planning-for-external-user-access.md)  
[Planeamiento de la Federación de protocolo de presencia y mensajería extensible (XMPP) en Lync Server 2013](lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

