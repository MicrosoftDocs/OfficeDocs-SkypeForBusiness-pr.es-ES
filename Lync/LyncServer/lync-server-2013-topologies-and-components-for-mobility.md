---
title: 'Lync Server 2013: Topologías y componentes para movilidad'
TOCTitle: Topologías y componentes para movilidad
ms:assetid: be3cae7a-095d-4785-91ba-6fac99eba92a
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Hh690037(v=OCS.15)
ms:contentKeyID: 48276531
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Topologías y componentes para movilidad en Lync Server 2013

 

_**Última modificación del tema:** 2013-02-17_

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Lync Server 2013 proporciona tres servicios para admitir las aplicaciones móviles de Lync en dispositivos móviles: Lync Server 2013 el servicio de movilidad Mcx, el servicio Detección automática de Lync Server 2013 y el servicio de notificaciones de inserción de Lync Server 2013. Las actualizaciones acumuladas para Lync Server 2013 de febrero de 2013 incorporan un servicio complementario avanzado para clientes de Lync 2013 Mobile: la compatibilidad de movilidad mediante el uso de la API web de comunicaciones unificadas (o UCWA). En esta sección se explican estos componentes sucintamente y se identifican las topologías de Lync Server 2013 que admiten la movilidad.


> [!NOTE]
> Los servicios de movilidad también se encuentran disponibles en las implementaciones híbridas. Si los usuarios se hospedan en línea, no tiene que implementar servicios para disfrutar de compatibilidad con la movilidad. Tampoco tiene que definir ningún valor para el servicio Detección automática si desea que los usuarios móviles encuentren su identidad en línea.



> [!IMPORTANT]  
> Si tiene previsto usar la conectividad de usuarios externos (por ejemplo, las características de federación, acceso de usuarios externos o movilidad), debe usar Servidores perimetrales con el Servidor Standard Edition, y el Servidor front-end o el Grupo de servidores front-end. El Servidor Standard Edition y el Servidor front-end o Grupo de servidores front-end no cuentan con los componentes necesarios para permitir que los usuarios externos obtengan acceso a la implementación interna, ni para que esta implementación interna se comunique con los usuarios externos. En todos los escenarios que incluyen usuarios externos que colaboran o se comunican con usuarios internos, incluida la movilidad, debe implementar al menos un Servidor perimetral y un proxy inverso.<br />
> La <em>notificación de inserción</em> usa un tipo de federación para los servicios de Lync Online que hospeda el centro de enrutamiento de notificaciones de inserción (PNCH). La notificación de inserción hace referencia a las alertas de sonido, las alertas en pantalla (texto) y los distintivos que las aplicaciones insertan en iPad e iPhone de Apple, así como en Windows Phone, cuando el dispositivo móvil no está activo. El PNCH recibe notificaciones de inserción desde Lync Server. Cuando el PNCH recibe una notificación de un mensaje, reenvía una notificación a los clientes móviles a través de los servicios de notificaciones de inserción de Apple o Lync Server 2013, según el cliente móvil al que vaya dirigido el mensaje. El PNCH es un servicio necesario para estos clientes móviles. Para federarse en Lync Online, PNCH usa Servidores perimetrales y certificados para asegurar la confidencialidad y la autenticación, directivas y registros del sistema de nombres de dominio (DNS) configurados correctamente. Los clientes de Lync Mobile basados en Android y Nokia Symbian no usan el PNCH. Para más información sobre la planeación y e implementación de Servidores perimetrales, vea <a href="lync-server-2013-planning-for-external-user-access.md">Planear acceso de usuarios externos en Lync Server 2013</a> y <a href="lync-server-2013-deploying-external-user-access.md">Implementar el acceso de usuarios externos en Lync Server 2013</a>.<br />
> Los clientes de Lync 2013 Mobile para dispositivos Apple que aparecieron con las actualizaciones acumuladas para Lync Server 2013 de febrero de 2013 ya no usan notificaciones de inserción o el centro de enrutamiento de notificaciones de inserción, pero sí siguen usándolos los clientes de Lync 2013 Mobile en Windows Phone.


## Componentes de movilidad

Los servicios compatibles con la movilidad son los siguientes:

  - **API web de comunicaciones unificadas de Lync Server 2013 (UCWA)**   Presta servicios para establecer comunicaciones en tiempo real con clientes web y móviles en Lync Server 2013. Cuando se implementan las actualizaciones acumuladas para Lync Server 2013 de febrero de 2013 en el Servidor front-end y el Director, con la instalación se crea un directorio virtual en los servicios web internos y externos (Ucwa). Un componente web que forme parte de este directorio acepta las llamadas procedentes de los clientes que estén habilitados para UCWA. Las aplicaciones cliente se comunican a través de una interfaz de REST para poder disfrutar de las características de presencia, contactos, mensajería instantánea, VoIP, videoconferencia y colaboración. UCWA usa un canal basado en P-GET para enviar eventos como una llamada entrante, un mensaje instantáneo entrante o un mensaje enviado a la aplicación cliente.
    

    > [!NOTE]
    > <EM>REST</EM> (o transferencia de estado representacional) es un estilo de arquitectura de software para sistemas distribuidos de uso muy extendido en diversas formas que resulta idónea para los requisitos de los servicios web en general.



  - **Servicio de movilidad de Lync Server 2013 (Mcx)**   Este servicio admite la funcionalidad de Lync, como la mensajería instantánea (MI), la presencia y los contactos, en los dispositivos móviles. El servicio de movilidad se instala en cada Servidor front-end de todos los grupos que deban admitir la funcionalidad de Lync en los dispositivos móviles. Al instalar Lync Server 2013, se crea un directorio virtual (Mcx) en los sitios web interno y externo de los Servidores front-end.
    
    > [!IMPORTANT]  
    > Lync Server 2013 con las actualizaciones acumuladas para Lync Server 2013 de febrero de 2013 admite el servicio de movilidad presentado en la actualización acumulada para Lync Server 2010 de noviembre de 2011 (comúnmente conocido como Mcx), así como el componente web UCWA. Al combinar estos dos servicios de movilidad, se proporciona interoperabilidad y posibilidad de uso por parte de los usuarios con clientes de Lync 2010 Mobile y Lync 2013 Mobile en Lync Server 2013.
    


  - **Servicio Detección automática de Lync Server 2013**   Este servicio identifica la ubicación del usuario y permite a los dispositivos móviles y a otros clientes de Lync localizar recursos, como direcciones URL internas y externas para los servicios web de Lync Server 2013 y la dirección URL para los servicios Mxc o UCWA, independientemente de la ubicación de red. La detección automática usa nombres de host codificados de forma rígida (lyncdiscoverinternal para usuarios internos de la red y lyncdiscover para los externos) y el dominio SIP del usuario. Admite conexiones de cliente con HTTP o HTTPS.
    
    El servicio Detección automática se instala en cada Servidor front-end y en cada Director de los distintos grupos compatibles con la funcionalidad de Lync en dispositivos móviles. Al instalar el servicio Detección automática, se crea un nuevo directorio virtual (Autodiscover) en los sitios web interno y externo de Servidores front-end y Directores.
    

    > [!NOTE]
    > Incluimos aquí el servicio Detección automática porque sigue siendo un componente esencial a la hora de proporcionar servicios de cliente móvil. El rol de Detección automática en Lync Server 2013 se ha ampliado para proporcionar servicios a todos los clientes. Para más información sobre cómo planear este servicio, vea <A href="lync-server-2013-planning-for-autodiscover.md">Planear la detección automática en Lync Server 2013</A>.



  - **Servicio de notificaciones de inserción**   Se trata de un servicio basado en la nube que se ubica en el centro de datos de Lync Online. Cuando la aplicación móvil de Lync de un dispositivo compatible Apple iOS o Windows Phone está inactiva, no puede responder a nuevos eventos, como una nueva invitación de mensajería instantánea (MI), un mensaje instantáneo perdido, una llamada perdida o correo de voz, porque estos dispositivos no son compatibles con las aplicaciones móviles que se ejecutan en segundo plano. En estos casos, se envía al dispositivo móvil una notificación del nuevo evento, denominada *notificación de inserción*. El servicio de movilidad envía la notificación al servicio de notificaciones de inserción basado en la nube que, a su vez, envía la notificación al servicio de notificaciones de inserción de Apple (APNS) (para dispositivos Apple iOS compatibles) o de Microsoft (MPNS) (para Windows Phone), que la envía al dispositivo móvil. El usuario puede responder a la notificación en el dispositivo móvil para activar la aplicación.
    
    Lync 2010 Mobile en dispositivos de Apple y Windows Phone usan las notificaciones de inserción. El cliente de Lync 2013 Mobile para dispositivos de Apple que se presentó con las actualizaciones acumuladas para Lync Server 2013 de febrero de 2013 ya no usa este tipo de notificaciones o el centro de enrutamiento de notificaciones de inserción (PNCH).

En el siguiente diagrama se ilustra cómo se adapta el servicio de notificaciones de inserción a una topología de Lync Server 2013 que usa UCWA y clientes de Lync 2013 Mobile.

![Servicio de notificaciones push UCWA](images/Hh690037.166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae(OCS.15).jpg "Servicio de notificaciones push UCWA")

Incluido en la actualización acumulada para Lync Server 2010 de noviembre de 2011, el servicio Mcx ofrece servicios a los clientes de Lync 2010 Mobile. En el siguiente diagrama se ilustra el servicio de notificaciones de inserción aplicado a una topología en la que se usa Mcx y clientes de Lync 2010 Mobile.

![Servicio de notificaciones push MCX](images/Hh690037.3081634e-60e7-4348-b24e-bbbf05a90f5f(OCS.15).jpg "Servicio de notificaciones push MCX")

## Topologías admitidas

Cuando se aplican las actualizaciones acumuladas para Lync Server 2013 de febrero de 2013, se agregan los componentes web de UCWA para admitir la movilidad de cara a obtener las características de cliente de Lync 2013 Mobile en las siguientes topologías:

  - Lync Server 2013  Standard Edition

  - Lync Server 2013 Enterprise Edition

El Servidor perimetral puede ser un Servidor perimetral de Lync Server 2010.

Una implementación de Lync Server 2013 en la que se hayan instalado las actualizaciones acumuladas para Lync Server 2013 de febrero de 2013 usará el servicio de movilidad Mcx y solo proporcionará servicios para Lync 2010 Mobile.

> [!IMPORTANT]  
> El servicio de movilidad se admite en los Servidores front-end que se hayan colocado con el rol Servidor de mediación con dos interfaces de red, si bien se deben realizar los pasos necesarios para configurar ambas interfaces. Así, hay que asignar las direcciones IP a la interfaz concreta que se vaya a comunicar como Servidor de mediación, así como la dirección IP de interfaz de red que se vaya a comunicar como Servidor front-end. Esto se puede realizar en el Generador de topologías, seleccionando la dirección IP adecuada para cada servicio en lugar de usar la opción predeterminada <strong>Usar todas las direcciones IP configuradas</strong>.



## Vea también

#### Otros recursos

[Planear acceso de usuarios externos en Lync Server 2013](lync-server-2013-planning-for-external-user-access.md)  
[Implementar el acceso de usuarios externos en Lync Server 2013](lync-server-2013-deploying-external-user-access.md)  
[Planear la detección automática en Lync Server 2013](lync-server-2013-planning-for-autodiscover.md)

