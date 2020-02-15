---
title: 'Lync Server 2013: topologías y componentes para movilidad'
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
ms.openlocfilehash: 0ac03d6b98b0b209a50f08e660fe6665b975d2ce
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045532"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topologies-and-components-for-mobility-in-lync-server-2013"></a>Topologías y componentes para movilidad en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-17_

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Para admitir aplicaciones móviles de Lync en dispositivos móviles, Lync Server 2013 proporciona tres servicios: Lync Server 2013 MCX Mobility Service, Lync Server 2013 Autodiscover Service y Lync Server 2013 Push Notification Service. Las actualizaciones acumulativas de Lync Server 2013: febrero de 2013 agrega un servicio complementario, pero avanzado, para clientes móviles de Lync 2013, compatibilidad con movilidad mediante el uso de la API Web de comunicaciones unificadas o UCWA. En esta sección se describen brevemente estos componentes y se identifican las topologías de Lync Server 2013 que admiten la movilidad.

<div>


> [!NOTE]  
> Los servicios de movilidad también se encuentran disponibles en las implementaciones híbridas. Si los usuarios se hospedan en línea, no tiene que implementar servicios para disfrutar de compatibilidad con la movilidad. Debe definir una configuración para el servicio Detección automática para que los usuarios móviles puedan encontrar su identidad en línea.



</div>

<div>


> [!IMPORTANT]  
> Si planea la conectividad de usuarios externos (por ejemplo, la Federación, el acceso de usuarios externos o las características de movilidad), debe usar servidores perimetrales con el servidor Standard Edition y el servidor front-end o el grupo de servidores front-end. El servidor Standard Edition y el servidor front-end o el grupo de servidores front-end no tienen los componentes necesarios para permitir que los usuarios externos tengan acceso a la implementación interna, o para que la implementación interna se comunique con los usuarios externos. Para todos los escenarios que incluyan usuarios externos que colaboren o se comuniquen con usuarios internos, incluida la movilidad, debe implementar al menos un servidor perimetral y un proxy inverso.<BR>La <EM>notificación de inserción</EM> usa un tipo de Federación a los servicios de Lync Online, que hospeda el centro de enrutamiento de notificaciones de inserción (PNCH). La notificación de inserción hace referencia a las alertas de sonido, alertas en pantalla (texto) y distintivos que envían las aplicaciones al iPhone, iPad y Windows Phone de Apple, cuando el dispositivo móvil está inactivo. PNCH recibe notificaciones de inserción de Lync Server. Cuando PNCH recibe una notificación de un mensaje, PNCH reenvía una notificación a los clientes móviles a través del servicio de notificaciones push de Apple push Notification Services o Lync Server 2013, en función del cliente móvil para el que está dirigido el mensaje. El PNCH es un servicio necesario para estos clientes móviles. Para federar a Lync Online, PNCH usa servidores perimetrales y certificados para garantizar la confidencialidad y la autenticación, las directivas y los registros del sistema de nombres de dominio (DNS) configurados correctamente. Los clientes móviles de Lync Symbian y basados en Android no usan PNCH. Para obtener más información sobre la planeación y la implementación de servidores perimetrales, consulte <A href="lync-server-2013-planning-for-external-user-access.md">Planning for external User Access in Lync server 2013</A> e <A href="lync-server-2013-deploying-external-user-access.md">Deploying external User Access in Lync Server 2013</A>.<BR>Los clientes móviles de Lync 2013 para dispositivos Apple que se incluyeron con las actualizaciones acumulativas para Lync Server 2013: febrero de 2013 ya no usan la notificación de inserción o el centro de enrutamiento de notificaciones de inserción (PNCH). Los clientes móviles de Lync 2013 en Windows Phone siguen usando la notificación de inserción y (PNCH).



</div>

<div>

## <a name="mobility-components"></a>Componentes de movilidad

Los servicios compatibles con la movilidad son los siguientes:

  - **Lync Server 2013 la API Web de comunicaciones unificadas (UCWA)**   proporciona servicios para comunicaciones en tiempo real con clientes móviles y Web en Lync Server 2013. Al implementar las actualizaciones acumulativas para Lync Server 2013: el 2013 de febrero al Director y al servidor front-end, la instalación crea un directorio virtual en los servicios Web internos y externos (Ucwa). Un componente web que forma parte del directorio virtual Ucwa acepta llamadas de clientes habilitados con UCWA. Las aplicaciones cliente se comunican a través de una interfaz REST para presencia, contactos, mensajería instantánea, VoIP, videoconferencia y colaboración. UCWA usa un canal basado en P-GET para enviar eventos, como una llamada entrante, un mensaje instantáneo entrante o un mensaje a la aplicación cliente.
    
    <div>
    

    > [!NOTE]  
    > El <EM>resto</EM> o la representationidad del estado de la representación es un estilo de arquitectura de software para sistemas distribuidos que se ha adoptado ampliamente en muchas formas y es muy adecuado para los requisitos de los servicios web en general.

    
    </div>

  - **Lync Server 2013 Mobility Service (MCX)**   este servicio admite la funcionalidad de Lync, como la mensajería instantánea (mi), la presencia y los contactos, en dispositivos móviles. El servicio de movilidad se instala en todos los servidores front-end de cada grupo de servidores que admitan la funcionalidad de Lync en dispositivos móviles. Al instalar Lync Server 2013, se crea un nuevo directorio virtual (MCX) en el sitio Web interno y en el sitio web externo de los servidores front-end.
    
    <div>
    

    > [!IMPORTANT]  
    > Lync Server 2013 con las actualizaciones acumulativas para Lync Server 2013: el 2013 de febrero admite tanto el servicio de movilidad que se incluye en la actualización acumulativa de Lync Server 2010:2011 de noviembre, conocido como MCX, y el componente web UCWA. La combinación de estos dos servicios de movilidad proporciona interoperabilidad y uso por parte de los usuarios con los clientes móviles de Lync 2010 y Lync 2013 en Lync Server 2013.

    
    </div>

  - **Servicio Detección automática de Lync Server 2013**   este servicio identifica la ubicación del usuario y habilita los dispositivos móviles y otros clientes de Lync para localizar recursos (como las direcciones URL internas y externas para los servicios Web de Lync Server 2013) y la dirección URL de MCX o UCWA, independientemente de la ubicación de red. La detección automática usa nombres de host codificados (lyncdiscoverinternal para los usuarios dentro de la red; lyncdiscover para los usuarios fuera de la red) y el dominio SIP del usuario. Admite conexiones de cliente que usan HTTP o HTTPS.
    
    El servicio de detección automática se instala en todos los servidores front-end y en todos los directores de cada grupo que es compatible con la funcionalidad de Lync en dispositivos móviles. Al instalar el servicio Detección automática, se crea un nuevo directorio virtual (detección automática) en el sitio Web interno y en el sitio web externo, tanto en los servidores front-end como en los directores.
    
    <div>
    

    > [!NOTE]  
    > El servicio Detección automática aparece aquí porque sigue siendo un componente crítico al ofrecer servicios de cliente móvil. El rol de detección automática en Lync Server 2013 se ha ampliado para proporcionar servicios a todos los clientes. Para obtener más información sobre la planeación del servicio de detección automática, consulte <A href="lync-server-2013-planning-for-autodiscover.md">planeación de la detección automática en Lync Server 2013</A>.

    
    </div>

  - **Servicio de notificaciones de inserción**   este servicio es un servicio basado en la nube que se encuentra en el centro de datos de Lync Online. Cuando la aplicación móvil de Lync en un dispositivo iOS de Apple compatible o Windows Phone está inactiva, no puede responder a nuevos eventos, como una nueva invitación de mensajería instantánea (mi), un mensaje instantáneo perdido, una llamada perdida o un correo de voz, porque estos dispositivos no admiten aplicaciones móviles que se ejecutan en segundo plano. En estos casos, se envía una notificación del nuevo evento (denominado *notificación de inserción*) al dispositivo móvil. El servicio de movilidad envía la notificación al servicio de notificación de inserción basado en la nube, que, a continuación, envía la notificación al servicio de notificaciones push de Apple (APN) (para dispositivos Apple iOS compatibles) o al servicio de notificación de inserción de Microsoft (MPNS ) (para Windows Phone), que a su vez la envía al dispositivo móvil. A continuación, el usuario puede responder a la notificación en el dispositivo móvil para activar la aplicación.
    
    Lync 2010 Mobile en dispositivos Apple y Windows Phone usan notificaciones de inserción. El cliente móvil de Lync 2013 para dispositivos Apple que se incorporó con las actualizaciones acumulativas para Lync Server 2013: febrero de 2013 ya no usa la notificación de inserción ni el centro de enrutamiento de notificaciones de inserción (PNCH).

El siguiente diagrama ilustra cómo encaja el servicio de notificaciones de inserción dentro de una topología de Lync Server 2013 que usa UCWA y clientes móviles de Lync 2013.

![166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae](images/Hh690037.166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae(OCS.15).jpg "166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae")

Se incorporó en la actualización acumulativa de Lync Server 2010:2011 de noviembre de, el servicio MCX proporciona servicios a clientes móviles de Lync 2010. El siguiente diagrama ilustra el servicio de notificaciones de inserción tal como se aplica a una topología con MCX y clientes móviles de Lync 2010.

![3081634e-60e7-4348-b24e-bbbf05a90f5f](images/Hh690037.3081634e-60e7-4348-b24e-bbbf05a90f5f(OCS.15).jpg "3081634e-60e7-4348-b24e-bbbf05a90f5f")

</div>

<div>

## <a name="supported-topologies"></a>Topologías admitidas

Aplicar las actualizaciones acumulativas para Lync Server 2013: febrero de 2013 agrega los componentes Web de UCWA para admitir la movilidad para las características de cliente móvil de Lync 2013 en las siguientes topologías:

  - Lync Server 2013 Standard Edition

  - Lync Server 2013 Enterprise Edition

El servidor perimetral puede ser un servidor perimetral de Lync Server 2010.

Una implementación de Lync Server 2013 sin las actualizaciones acumulativas para Lync Server 2013: febrero de 2013 usará el servicio de movilidad MCX y solo puede proporcionar servicios para Lync 2010 Mobile.

<div>


> [!IMPORTANT]  
> El servicio de movilidad es compatible con los servidores front-end combinados con el rol de servidor de mediación con dos interfaces de red, pero debe seguir los pasos apropiados para configurar las interfaces. Debe asignar las direcciones IP a la interfaz específica que se comunicará como servidor de mediación y la IP de la interfaz de red que se comunicará como servidor front-end. Puede hacerlo en Topology Builder seleccionando la dirección IP correcta para cada servicio, en lugar de usar el valor predeterminado <STRONG>usar todas las direcciones IP configuradas</STRONG>.



</div>

</div>

<div>

## <a name="see-also"></a>Vea también


[Planeación del acceso de usuarios externos en Lync Server 2013](lync-server-2013-planning-for-external-user-access.md)  
[Implementar el acceso de usuarios externos en Lync Server 2013](lync-server-2013-deploying-external-user-access.md)  
[Planeación de la detección automática en Lync Server 2013](lync-server-2013-planning-for-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

