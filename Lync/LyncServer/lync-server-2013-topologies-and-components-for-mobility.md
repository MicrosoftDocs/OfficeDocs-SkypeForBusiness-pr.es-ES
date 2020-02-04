---
title: 'Lync Server 2013: Topologías y componentes para movilidad'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Topologies and components for mobility
ms:assetid: be3cae7a-095d-4785-91ba-6fac99eba92a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690037(v=OCS.15)
ms:contentKeyID: 48185282
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 739deecf47e25e57ca0175c29a2721e509f8dbe2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745230"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topologies-and-components-for-mobility-in-lync-server-2013"></a>Topologías y componentes para movilidad en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-17_

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Para admitir las aplicaciones móviles de Lync en dispositivos móviles, Lync Server 2013 proporciona tres servicios: Lync Server 2013 MCX Mobility Service, servicio Detección automática de Lync Server 2013 y servicio de notificaciones push de Lync Server 2013. Las actualizaciones acumulativas para Lync Server 2013: febrero de 2013 agrega un servicio gratuito, pero avanzado, para clientes móviles de Lync 2013, soporte de movilidad mediante el uso de la API Web de comunicaciones unificadas, o UCWA. En esta sección se describen brevemente estos componentes y se identifican las topologías de Lync Server 2013 que admiten movilidad.

<div>


> [!NOTE]  
> Los servicios de movilidad también están disponibles en implementaciones híbridas. No es necesario implementar servicios para admitir la movilidad si los usuarios están conectados. Debe definir una configuración para que el servicio de detección automática permita que los usuarios móviles encuentren su identidad en línea.



</div>

<div>


> [!IMPORTANT]  
> Si planea una conectividad de usuario externa (por ejemplo, Federación, acceso de usuarios externos o características de movilidad), debe usar servidores perimetrales con servidor Standard Edition y el servidor front-end o grupo front-end. El servidor Standard Edition y el servidor front-end o el grupo front-end no tienen los componentes necesarios para permitir a los usuarios externos el acceso a su implementación interna o para que la implementación interna se comunique con los usuarios externos. Para todos los escenarios en los que se incluyen usuarios externos que colaboran o comunican con usuarios internos, incluida la movilidad, debe implementar al menos un servidor perimetral y un proxy inverso.<BR>La <EM>notificación de inserción</EM> usa un tipo de Federación a los servicios de Lync Online, que hospeda el centro de enrutamiento de notificaciones de inserción (PNCH). La notificación push hace referencia a las alertas de sonido, las alertas en pantalla (texto) y los insignias que las aplicaciones envían a Apple iPhone, iPad y Windows Phone, cuando el dispositivo móvil está inactivo. PNCH recibe notificaciones push de Lync Server. Cuando PNCH recibe una notificación de un mensaje, PNCH reenvía una notificación a los clientes móviles a través del servicio de notificaciones push de Apple push Notification Services o Lync Server 2013, en función del cliente móvil al que se destina el mensaje. PNCH es un servicio necesario para estos clientes móviles. Para federarse a Lync Online, PNCH usa servidores perimetrales y certificados para garantizar la confidencialidad, la autenticación, las directivas y los registros del sistema de nombres de dominio (DNS) correctamente configurado. Nokia Symbian y los clientes de Lync Mobile basados en Android no usan PNCH. Para obtener más información sobre la planeación y la implementación de servidores perimetrales, vea <A href="lync-server-2013-planning-for-external-user-access.md">planear el acceso de usuarios externos en Lync server 2013</A> e <A href="lync-server-2013-deploying-external-user-access.md">implementar el acceso de usuarios externos en Lync Server 2013</A>.<BR>Los clientes móviles de Lync 2013 para dispositivos Apple se introdujeron con las actualizaciones acumulativas para Lync Server 2013: febrero de 2013 ya no usan la notificación de inserción o el centro de enrutamiento de notificaciones de inserción (PNCH). Los clientes móviles de Lync 2013 en Windows Phone siguen usando la notificación de inserción y (PNCH).



</div>

<div>

## <a name="mobility-components"></a>Componentes de movilidad

Los servicios que admiten la movilidad son los siguientes:

  - **La API Web de comunicaciones unificadas de Lync Server 2013 (UCWA)**   proporciona servicios para las comunicaciones en tiempo real con clientes móviles y Web en Lync Server 2013. Al implementar las actualizaciones acumulativas para Lync Server 2013:2013 de febrero al servidor front-end y el director, la instalación crea un directorio virtual en los servicios Web internos y externos (Ucwa). Un componente web que forma parte del directorio virtual Ucwa acepta llamadas de clientes habilitados en UCWA. Las aplicaciones cliente se comunican a través de una interfaz REST de presencia, contactos, mensajería instantánea, VoIP, videoconferencias y colaboración. UCWA usa un canal basado en P-GET para enviar eventos, como una llamada entrante, un mensaje instantáneo entrante o un mensaje a la aplicación cliente.
    
    <div>
    

    > [!NOTE]  
    > El <EM>resto</EM> de la transferencia del estado de la presentación, es un estilo arquitectónico de software para sistemas distribuidos que se ha adoptado ampliamente en muchas formas y es muy adecuado para los requisitos de los servicios web en general.

    
    </div>

  - **Lync Server 2013 Mobility Service (MCX)**   este servicio admite la funcionalidad de Lync, como la mensajería instantánea (mi), la presencia y los contactos, en dispositivos móviles. El servicio de movilidad se instala en todos los servidores front-end de cada grupo para admitir la funcionalidad de Lync en dispositivos móviles. Al instalar Lync Server 2013, se crea un nuevo directorio virtual (MCX) en el sitio Web interno y en el sitio web externo de los servidores front-end.
    
    <div>
    

    > [!IMPORTANT]  
    > Lync Server 2013 con las actualizaciones acumulativas para Lync Server 2013: el 2013 de febrero es compatible con el servicio de movilidad introducido en la actualización acumulativa para Lync Server 2010:2011 de noviembre (conocido comúnmente como MCX y el componente Web de UCWA). La combinación de estos dos servicios de movilidad proporciona interoperabilidad y uso por parte de los usuarios con Lync 2010 Mobile y clientes móviles de Lync 2013 en Lync Server 2013.

    
    </div>

  - **Servicio Detección automática de Lync Server 2013**   este servicio identifica la ubicación del usuario y permite que los dispositivos móviles y otros clientes de Lync encuentren recursos, como las direcciones URL internas y externas para los servicios Web de Lync Server 2013 y la dirección URL de MCX o UCWA, independientemente de la ubicación de red. El descubrimiento automático usa nombres de host codificados (lyncdiscoverinternal para los usuarios de la red; lyncdiscover para usuarios ajenos a la red) y el dominio SIP del usuario. Admite conexiones de cliente con HTTP o HTTPS.
    
    El servicio de detección automática se instala en todos los servidores front-end y en cada director de cada grupo que sea compatible con la funcionalidad de Lync en dispositivos móviles. Al instalar el servicio Detección automática, se crea un nuevo directorio virtual (detección automática) en el sitio Web interno y en el sitio web externo, tanto en servidores de aplicaciones para el usuario como en directores.
    
    <div>
    

    > [!NOTE]  
    > El servicio Detección automática aparece aquí porque sigue siendo un componente crítico al proporcionar servicios de cliente móvil. El rol de detección automática en Lync Server 2013 se ha expandido para proporcionar servicios para todos los clientes. Para obtener más información sobre cómo planear el servicio de detección automática, consulte <A href="lync-server-2013-planning-for-autodiscover.md">planificación de la detección automática en Lync Server 2013</A>.

    
    </div>

  - **Servicio de notificaciones push**   este servicio es un servicio basado en la nube que se encuentra en el centro de datos de Lync Online. Cuando la aplicación móvil de Lync en un dispositivo iOS de Apple compatible o en Windows Phone no está activa, no puede responder a eventos nuevos, como una nueva invitación de mensajería instantánea (mi), un mensaje instantáneo perdido, una llamada perdida o correo de voz, porque estos dispositivos no son compatibles aplicaciones móviles que se ejecutan en segundo plano. En estos casos, se envía al dispositivo móvil una notificación del nuevo evento (denominado *notificación de inserción*). El servicio de movilidad envía la notificación al servicio de notificaciones de inserción basado en la nube, que después envía la notificación al servicio de notificaciones push de Apple (APN) (para dispositivos Apple iOS compatibles) o al servicio de notificaciones push de Microsoft (MPNS ) (para Windows Phone), que a su vez la envía al dispositivo móvil. Después, el usuario puede responder a la notificación en el dispositivo móvil para activar la aplicación.
    
    Lync 2010 Mobile en dispositivos Apple y Windows Phone usa notificaciones Push. El cliente móvil de Lync 2013 para dispositivos Apple introducido con las actualizaciones acumulativas para Lync Server 2013: el 2013 de febrero ya no usa la notificación de inserción ni el centro de enrutamiento de notificaciones de inserción (PNCH).

En el siguiente diagrama se muestra cómo el servicio de notificaciones de inserción encaja en una topología de Lync Server 2013 que usa UCWA y clientes móviles de Lync 2013.

![166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae](images/Hh690037.166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae(OCS.15).jpg "166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae")

Introducido en la actualización acumulativa para Lync Server 2010:2011 de noviembre, el servicio MCX ofrece servicios a clientes móviles de Lync 2010. En el siguiente diagrama se muestra el servicio de notificaciones push tal y como se aplica a una topología mediante MCX y clientes móviles de Lync 2010.

![3081634e-60e7-4348-b24e-bbbf05a90f5f](images/Hh690037.3081634e-60e7-4348-b24e-bbbf05a90f5f(OCS.15).jpg "3081634e-60e7-4348-b24e-bbbf05a90f5f")

</div>

<div>

## <a name="supported-topologies"></a>Topologías admitidas

Aplicar las actualizaciones acumulativas para Lync Server 2013: el 2013 de febrero agrega los componentes Web de UCWA para admitir la movilidad de las características de cliente móvil de Lync 2013 en las siguientes topologías:

  - Lync Server 2013 Standard Edition

  - Lync Server 2013 Enterprise Edition

El servidor perimetral puede ser un servidor perimetral de Lync Server 2010.

Una implementación de Lync Server 2013 sin las actualizaciones acumulativas para Lync Server 2013: el 2013 de febrero usará el servicio de movilidad MCX y solo puede proporcionar servicios para Lync 2010 Mobile.

<div>


> [!IMPORTANT]  
> El servicio de movilidad es compatible con los servidores front-end que se colocan con la función de servidor de mediación con dos interfaces de red, pero debe seguir los pasos adecuados para configurar las interfaces. Debe asignar las direcciones IP a la interfaz específica que se comunicará como el servidor de mediación y la IP de la interfaz de red que se comunicará como servidor front-end. Puede hacerlo en el generador de topología seleccionando la dirección IP correcta para cada servicio, en lugar de <STRONG>usar las direcciones IP configuradas</STRONG>de forma predeterminada.



</div>

</div>

<div>

## <a name="see-also"></a>Vea también


[Planear acceso de usuarios externos en Lync Server 2013](lync-server-2013-planning-for-external-user-access.md)  
[Implementar el acceso de usuarios externos en Lync Server 2013](lync-server-2013-deploying-external-user-access.md)  
[Planificación de la detección automática en Lync Server 2013](lync-server-2013-planning-for-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

