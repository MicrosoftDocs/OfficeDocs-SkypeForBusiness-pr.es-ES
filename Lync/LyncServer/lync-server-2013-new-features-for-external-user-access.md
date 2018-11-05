---
title: "Lync Server 2013 : Nlles fonct. liées à l’accès des ut. Ext."
TOCTitle: Nuevas características para acceso de usuario externo
ms:assetid: 99da6bd5-ec14-4ad9-8f7d-37fbddf567dd
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398794(v=OCS.15)
ms:contentKeyID: 48276174
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Nuevas características para acceso de usuario externo en Lync Server 2013

 

_**Última modificación del tema:** 2012-10-17_

Lync Server 2013 incluye nuevas características que amplían las características y los métodos de comunicación de los usuarios. Además, Lync Server 2013 presenta cambios en los servicios existentes para integrar y ampliar de mejor forma los servicios que están disponibles para la organización. A continuación figura un resumen de los cambios que pueden afectar a la planeación e implementación de servicios del Servidor perimetral de Lync Server 2013.

  - **Compatibilidad con direcciones IPv6:** Lync Server 2013 admite direcciones IPv6 para todos los servicios de Servidor perimetral. Si ha proporcionado direcciones IPv6 para las interfaces a través de la configuración de Windows Server, puede usar las direcciones IPv6 en la configuración del Servidor perimetral a través de la configuración de dirección IP en la Generador de topologías.
    
    > [!IMPORTANT]  
    > El uso de direcciones IPv6 en Lync Server 2013 depende de la compatibilidad de IPv6 en los enrutadores y firewalls que implementa la organización, así como de la compatibilidad a través de su proveedor de servicios de Internet.
    


  - **Protocolo extensible de mensajería y presencia (XMPP):** Lync Server 2013 introduce un proxy XMPP totalmente integrado (implementado en los Servidores perimetrales) y una puerta de enlace XMPP implementada en los Servidores front-end. Puede implementar la federación de XMPP como componente opcional. La adición y configuración del proxy XMPP y de la puerta de enlace XMPP permitirá a los usuarios de Microsoft Lync 2013 agregar contactos de socios basados en XMPP para mensajería instantánea (MI) y presencia.
    

    > [!NOTE]
    > Actualmente, los servicios de XMPP en el Lync Server 2013 solo proporcionan mensajería instantánea y presencia entre los clientes de Lync y contactos basados en XMPP.



  - **Servicios de movilidad para clientes móviles** Introducidos en una actualización de cliente para Lync Server 2010, los servicios de movilidad en Lync Server 2013 permiten a los clientes de Microsoft Lync Mobile en teléfonos móviles y dispositivos de tableta que usan dispositivos móviles Apple iOS, Android, Windows Phone o Nokia compatibles realizar actividades como enviar y recibir mensajes instantáneos, ver contactos y ver la presencia. Además, los dispositivos móviles admiten algunas características de Telefonía IP empresarial como hacer clic para unirse a una conferencia, Vía trabajo, conexión con un solo número, correo de voz y notificación de llamadas perdidas.
    

    > [!NOTE]
    > Los servicios de movilidad usan el proxy inverso y servicios publicados que se implementan en los Servidores front-end. No se requieren cambios en los Servidores perimetrales.



  - **Directores son un rol opcional** El rol del servidor Director en la topología de Lync Server 2013 no ha cambiado. Aún hospeda servicios web, autentica previamente las solicitudes de usuarios entrantes y dirige a los usuarios externos a su grupo de servidores principal. El cambio de Director de un rol recomendado a uno opcional no disminuye el valor del Director, pero enfatiza la reducción del recuento de servidores y otros requisitos de hardware (por ejemplo, equilibradores de carga de hardware para el Director) sin afectar a las características y a la funcionalidad. Puesto que los Servidores front-end pueden hacer el mismo trabajo que el Director sin impacto en los servicios proporcionados, puede implementar Directores de manera opcional si así lo elige. Puede excluir de manera segura el Director con la certeza de que los Servidores front-end proporcionarán los mismos servicios.

## Vea también

#### Conceptos

[Planeación y configuración de IPv6 en Lync Server 2013](lync-server-2013-planning-for-and-configuring-ipv6.md)  

#### Otros recursos

[Planear acceso de usuarios externos en Lync Server 2013](lync-server-2013-planning-for-external-user-access.md)  
[Planeación de federación de protocolo extensible de mensajería y presencia (XMPP) en Lync Server 2013](lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md)

