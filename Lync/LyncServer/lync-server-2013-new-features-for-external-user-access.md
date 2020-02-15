---
title: 'Lync Server 2013: nuevas características para el acceso de usuarios externos'
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
ms.openlocfilehash: e85c9e83a6dde06c7c091241bea903a3ddd1d813
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042347"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-features-for-external-user-access-in-lync-server-2013"></a>Nuevas características para el acceso de usuarios externos en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-17_

Lync Server 2013 presenta nuevas características que amplían las características y los métodos de comunicación para los usuarios. Además, Lync Server 2013 introduce cambios en los servicios existentes para una mejor integración y ampliación de los servicios que están disponibles para su organización. A continuación, se resumen los cambios que pueden afectar a la planeación y la implementación de los servicios del servidor perimetral de Lync Server 2013.

  - **Compatibilidad**   con la dirección IPv6 Lync Server 2013 admite el direccionamiento IPv6 para todos los servicios del servidor perimetral. Si ha proporcionado direcciones IPv6 para las interfaces mediante la configuración de Windows Server, puede usar direcciones IPv6 en la configuración del servidor perimetral a través de la configuración de dirección IP en el generador de topologías.
    
    <div>
    

    > [!IMPORTANT]  
    > El uso de direcciones IPv6 en Lync Server 2013 depende de la compatibilidad de IPv6 en los enrutadores y los firewalls que implementa su organización, así como la compatibilidad con su proveedor de servicios de Internet.

    
    </div>

  - **El protocolo extensible de mensajería y presencia (XMPP)**   Lync Server 2013 presenta un proxy XMPP completamente integrado (implementado en los servidores perimetrales) y una puerta de enlace XMPP implementada en los servidores front-end. Puede implementar la federación de XMPP como componente opcional. Agregar y configurar el proxy XMPP y la puerta de enlace XMPP permitirá a los usuarios de Microsoft Lync 2013 agregar contactos de socios basados en XMPP para la mensajería instantánea (mi) y la presencia.
    
    <div>
    

    > [!NOTE]  
    > Actualmente, los servicios XMPP en Lync Server 2013 solo proporcionan mensajería instantánea y presencia entre clientes de Lync y contactos basados en XMPP.

    
    </div>

  - **Los servicios de movilidad para los clientes**   móviles que se incluyen en la actualización de un cliente para Lync Server 2010, los servicios de movilidad de Lync Server 2013 permiten que los clientes móviles de Microsoft Lync en teléfonos móviles y tabletas usen dispositivos móviles compatibles con Apple iOS, Android, Windows Phone o Nokia para realizar actividades como enviar y recibir mensajes instantáneos, ver contactos y ver la presencia. Además, los dispositivos móviles admiten algunas características de Telefonía IP empresarial como hacer clic para unirse a una conferencia, Vía trabajo, conexión con un solo número, correo de voz y notificación de llamadas perdidas.
    
    <div>
    

    > [!NOTE]  
    > Los servicios de movilidad usan el proxy inverso y los servicios publicados que se implementan en los servidores front-end. No es necesario realizar cambios en los servidores perimetrales.

    
    </div>

  - **Los directores son un rol**   opcional el rol del servidor Director en la topología de Lync Server 2013 no ha cambiado. Aún hospeda servicios web, autentica previamente las solicitudes de usuarios entrantes y dirige a los usuarios externos a su grupo de servidores principal. Cambiar el director de un rol recomendado a un rol opcional no disminuye el valor del Director, pero enfatiza la reducción del número de servidores y otros requisitos de hardware (por ejemplo, los equilibradores de carga de hardware del Director) sin poner en peligro las características y la funcionalidad. Como los servidores front-end pueden realizar el mismo trabajo que el director sin afectar a los servicios proporcionados, puede implementar de forma opcional directores si lo prefiere. Puede excluir con seguridad el director con confianza de que los servidores front-end proporcionarán los mismos servicios en su ubicación.

<div>

## <a name="see-also"></a>Vea también


[Planeación y configuración de IPv6 en Lync Server 2013](lync-server-2013-planning-for-and-configuring-ipv6.md)  


[Planeación del acceso de usuarios externos en Lync Server 2013](lync-server-2013-planning-for-external-user-access.md)  
[Planeación de la Federación de protocolo extensible de mensajería y presencia (XMPP) en Lync Server 2013](lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

