---
title: 'Lync Server 2013: Descripción de detección automática'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Understanding Autodiscover
ms:assetid: d70a15b7-750b-4e0f-9a7f-0254d6d486c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945654(v=OCS.15)
ms:contentKeyID: 51541522
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: edaa9a938fe893ebca6f4e8abee4a3f41d1527dc
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193193"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="understanding-autodiscover-in-lync-server-2013"></a>Descripción de la detección automática en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-06-03_

El servicio Detección automática de Lync Server 2013 es una característica que se introdujo originalmente en Microsoft Lync Server 2010 como parte de la actualización acumulativa de Lync Server 2010: noviembre de 2011. Además de las correcciones, esta actualización acumulativa proporciona compatibilidad con clientes de Lync Mobile y Lync 2013.

En Lync Server 2013, el servicio de detección automática es una parte integral del funcionamiento de los clientes móviles internos y externos, y la detección automática también se extiende a los nuevos clientes, como la reciente introducción de la tienda Windows para Lync para Windows 8. Detección automática también se usa en los clientes de escritorio de Lync 2013. La detección automática se reconoce en Lync Server mediante el lyncdiscover de registros del sistema de nombres de dominio (DNS) requerido **.\< dominio\> ** y **lyncdiscoverinternal.\< dominio\>**. Además, las versiones más recientes de los clientes de escritorio de Lync 2010 y Lync 2013 prefieren la detección automática en los registros SRV del sistema de nombres de dominio (DNS), usando los registros DNS SRV solo si lyncdiscover. \<dominio\> o lyncdiscoverinternal. \<el\> dominio no responde o no se resuelve. La aplicación Lync para la tienda Windows para Windows 8 y Lync Mobile usa exclusivamente detección automática y no hará referencia a los registros DNS SRV tradicionales.

En Lync Server 2013, la detección automática se expande para comunicar al cliente qué elementos, características y métodos de comunicación están disponibles para el cliente. La información se comunica a través de una solicitud enviada desde el cliente, y los servicios Web de Lync Server responden con una respuesta claramente definida que nombra lo que está disponible para el cliente y cómo ponerse en contacto con dichas características en el formato de la detección automática. Documento de respuesta.

La mejor manera de comprender el documento de respuesta de detección automática, incluido cómo los servicios web comunican las características a los clientes a través de este documento, es dissect y definen cada línea en una respuesta típica del documento de respuesta de detección automática del servicio Web de Lync.

<div class="">


> [!NOTE]  
> En los detalles que se indican a continuación, el usuario ya se ha autenticado en el servidor principal respondiendo a una solicitud de autenticación.



</div>

<div class="">


> [!NOTE]  
> El servicio Web de detección automática de Lync se define en los <STRONG>protocolos de Microsoft Office</STRONG> en la sección de <STRONG>Especificaciones abiertas</STRONG> de la biblioteca de <STRONG>Microsoft Developer Network</STRONG> (MSDN). Para obtener más información, consulte el documento de especificación completa, "Protocolo del servicio Web de detección automática <A href="https://go.microsoft.com/fwlink/?linkid=273839">https://go.microsoft.com/fwlink/?LinkId=273839</A>de Lync" en:. Para obtener más información acerca de la autenticación, consulte "Protocolo de servicio <A href="https://go.microsoft.com/fwlink/?linkid=279015">https://go.microsoft.com/fwlink/?LinkId=279015</A>Web de autenticación de OC" en.



</div>

<div>

## <a name="the-lync-server-web-service-autodiscover-response"></a>Respuesta de detección automática del servicio Web de Lync Server

La respuesta devuelta cuando la solicitud de detección automática se envía es la misma para un cliente interno o externo. Algunos parámetros que tienen en cuenta la ubicación pueden cambiar. Si se recibe una solicitud de cliente, pero el grupo real es distinto del que se ha contactado, el grupo de servidores principal del usuario se establecerá para ese usuario. Un compañero cuya cuenta de usuario se encuentra en un grupo diferente, pero que inicia sesión desde la misma oficina, obtendría una respuesta ligeramente distinta. La respuesta indica el servidor front-end o el grupo de servidores front-end correctos para ese usuario.

Un ejemplo de un documento de respuesta de detección automática:

    <AutodiscoverResponse xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" AccessLocation="External">
       <User>
          <SipServerInternalAccess fqdn="pool01.contoso.com" port="5061"/>
          <SipClientInternalAccess fqdn=" pool01.contoso.com" port="443"/>
          <SipServerExternalAccess fqdn="sip.contoso.com" port="5061"/>
          <SipClientExternalAccess fqdn="sip.contoso.com " port="443"/>
          <Link token ="External/Autodiscover" href="https://webexternal.contoso.com/Autodiscover/AutodiscoverService.svc/root"/>
          <Link token="Internal/Autodiscover" href="https://webinternal.contoso.net/Autodiscover/AutodiscoverService.svc/root"/>
          <Link token="External/AuthBroker" href="https://webexternal.contoso.com/Reach/sip.svc"/>
          <Link token="Internal/AuthBroker" href="https://webinternal.contoso.net/Reach/sip.svc"/>
          <Link token="External/WebScheduler" href="https://webexternal.contoso.com/Scheduler"/>
          <Link token="Internal/WebScheduler" href="https://webinternal.contoso.net/Scheduler"/>
          <Link token="External/Mcx" href="https://webexternal.contoso.com/Mcx/McxService.svc"/>
          <Link token="Internal/Mcx" href="https://webexternal.contoso.net/Mcx/McxService.svc"/>
          <Link token="External/Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>
          <Link token="Internal/Ucwa" href="https://webinternal.contoso.net/ucwa/v1/applications"/>
          <Link token="Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>
          <Link token="External/XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>
          <Link token="Internal/XFrame" href="https://webinternal.contoso.net/Autodiscover/XFrame/XFrame.html"/>
          <Link token="XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>
          <Link token="Self" href="https://webexternal.contoso.net/Autodiscover/AutodiscoverService.svc/root/user"/>
       </User>
    </AutodiscoverResponse>

<div>

## <a name="autodiscover-response-document-details"></a>Detalles del documento de respuesta de detección automática

El documento de respuesta de detección automática puede tener uno de estos dos formatos. El formato predeterminado es una notación de objetos JavaScript (JSON). El otro formato es documento de lenguaje de marcado extensible (XML). El código XML se usa para este ejemplo. La solicitud y la respuesta son predecibles porque el documento tiene un esquema definido que determina el formato. La línea del documento que describe el esquema usado es la primera línea de la solicitud o respuesta:

    <AutodiscoverResponse xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" AccessLocation="External">

La definición de **AccessLocation = "external"** indica que la solicitud se ha realizado desde un usuario externo.

    <SipServerInternalAccess fqdn="pool01.contoso.com" port="5061"/>

&nbsp;

    <SipServerExternalAccess fqdn="sip.contoso.com" port="5061"/>

Actualmente, SipServerInternalAccess y SipServerExternalAccess no se usan. Estas entradas están reservadas para su uso en el futuro.

    <SipClientInternalAccess fqdn=" pool01.contoso.com" port="443"/>

&nbsp;

    <SipClientExternalAccess fqdn="sip.contoso.com " port="443"/>

SipClientInternalAccess y SipClientExternalAccess describen el nombre de dominio completo y el puerto que un cliente interno o externo usará para tener acceso al servidor SIP definido. El cliente de escritorio de Lync y la aplicación Lync de la tienda Windows usan estas entradas, en función de su ubicación (interna o externa) para encontrar el director o el servidor front-end.

    <Link token="Internal/Autodiscover" href="https://webinternal.contoso.net/Autodiscover/AutodiscoverService.svc/root"/>

&nbsp;

    <Link token ="External/Autodiscover" href="https://webexternal.contoso.com/Autodiscover/AutodiscoverService.svc/root"/>

Las `Autodiscover` referencias contienen los puntos de entrada de servicio para el servicio Detección automática. El atributo token contiene el nombre del servicio y Href es una dirección URL que define el cliente en el que se puede encontrar el servicio. Los clientes de una red externa usan `External/Autodiscover`el. El servicio de detección automática se instala como parte del proceso de implementación. `Internal/Autodiscover`no se usa actualmente y se reserva para su uso en el futuro.

    <Link token="Internal/AuthBroker" href="https://webinternal.contoso.net/Reach/sip.svc"/>

&nbsp;

    <Link token="External/AuthBroker" href="https://webexternal.contoso.com/Reach/sip.svc"/>

Las `AuthBroker` referencias contienen los puntos de entrada de servicio para el servicio de agente de autenticación interno y externo, en este caso, SIP. SVC. El atributo token contiene el nombre del servicio y Href es una dirección URL que define el cliente en el que se puede encontrar el servicio. Clientes de la red interna que usan `Internal/AuthBroker`. Los clientes de una red externa usan `External/AuthBroker`el. El servicio AuthBroker se instala como parte del proceso de implementación de los servicios Web internos de implementación de Lync Server 2013.

    <Link token="Internal/WebScheduler" href="https://webinternal.contoso.net/Scheduler"/>

&nbsp;

    <Link token="External/WebScheduler" href="https://webexternal.contoso.com/Scheduler"/>

El `WebScheduler` token hace referencia a las direcciones URL para el acceso de cliente a la programación basada en web para conferencias de Lync Server. Actualmente, solo se `External/WebScheduler` usa el. Webprogramation se instala como parte del proceso de implementación de los servicios Web internos de implementación de Lync Server 2013.

    <Link token="Internal/Mcx" href="https://webexternal.contoso.net/Mcx/McxService.svc"/>

&nbsp;

    <Link token="External/Mcx" href="https://webexternal.contoso.com/Mcx/McxService.svc"/>

`Internal/Mcx`y `External/Mcx` son las ubicaciones de los servicios de movilidad que se incluyen en la actualización acumulativa para Lync Server 2010: noviembre de 2011. Lync 2010 Mobile seguirá usando estas referencias en todos los dispositivos compatibles. El servicio MCX se instala como parte del proceso de implementación de los servicios Web internos de implementación de Lync Server 2013.

    <Link token="Internal/Ucwa" href="https://webinternal.contoso.net/ucwa/v1/applications"/>

&nbsp;

    <Link token="External/Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>

&nbsp;

    <Link token="Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>

**Interno/ucwa**, **external/ucwa** y **Ucwa** proporcionan un medio para que los clientes tengan acceso a la interfaz de programación de aplicaciones Web de comunicaciones unificadas (API de Ucwa o simplemente a Ucwa). `Internal/Ucwa`los `External/Ucwa` directorios virtuales son puntos de acceso reservados para futuras mejoras de características, y no se usan. El `Ucwa` directorio virtual se usa para Microsoft Lync Mobile (incluido en Lync Server 2013) en todos los dispositivos compatibles. El servicio UCWA se instala como parte del proceso de implementación de los servicios Web internos de implementación de Lync Server 2013.

    <Link token="Internal/XFrame" href="https://webinternal.contoso.net/Autodiscover/XFrame/XFrame.html"/>

&nbsp;

    <Link token="External/XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>

&nbsp;

    <Link token="XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>

`Internal/XFrame`, **External/XFrame** y **XFrame** proporcionan acceso a las aplicaciones de servidor basadas en UCWA. XFrame se instala como parte del proceso de implementación de los servicios Web internos de implementación de Lync Server 2013.

    <Link token="Self" href="https://webexternal.contoso.net/Autodiscover/AutodiscoverService.svc/root/user"/>

El `Self` token hace referencia a la información específica del cliente (tipo de respuesta de usuario) que realiza la solicitud. El cliente que realizó esta solicitud era externo y esta referencia de detección automática es a la parte de usuario del servicio Detección automática.

</div>

</div>

<div>

## <a name="see-also"></a>Consulta también


[Requisitos del sistema para componentes de acceso de usuarios externos para Lync Server 2013](lync-server-2013-system-requirements-for-external-user-access-components.md)  
[Planeación de la detección automática en Lync Server 2013](lync-server-2013-planning-for-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

