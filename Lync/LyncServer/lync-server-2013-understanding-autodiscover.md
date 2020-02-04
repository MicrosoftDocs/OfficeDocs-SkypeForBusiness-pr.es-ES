---
title: 'Lync Server 2013: Descripción de la detección automática'
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
ms.openlocfilehash: d9d885654f9222ce3d3e9fb7b03e9b388f0ca0a8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744830"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="understanding-autodiscover-in-lync-server-2013"></a>Descripción de la detección automática en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-06-03_

El servicio de detección automática de Lync Server 2013 es una característica introducida originalmente en Microsoft Lync Server 2010 como parte de la actualización acumulativa para Lync Server 2010: diciembre de 2011. Además de las correcciones, esta actualización acumulativa ofrece compatibilidad con clientes de Lync Mobile y Lync 2013.

En Lync Server 2013, el servicio Detección automática es una parte integral del funcionamiento de clientes móviles externos e internos, y la detección automática también se extiende a los nuevos clientes, como la aplicación de la tienda Windows de Lync recientemente presentada para Windows 8. La detección automática también la usan los clientes de escritorio de Lync 2013. La detección automática se reconoce en Lync Server mediante el lyncdiscover de registros del sistema de nombres de dominio (DNS) requerido **.\< dominio\> ** y **lyncdiscoverinternal.\< dominio\>**. Además, las versiones más recientes de los clientes de escritorio de Lync 2010 y Lync 2013 prefieren la detección automática en los registros SRV del sistema de nombres de dominio (DNS), usando los registros SRV de DNS solo si lyncdiscover. \<dominio\> o lyncdiscoverinternal. \<el\> dominio no responde o no se resuelve. La aplicación de la tienda Windows de Lync para Windows 8 y Lync Mobile usa exclusivamente la detección automática y no hará referencia a los registros SRV de DNS tradicionales.

En Lync Server 2013, la detección automática se ha expandido para comunicar al cliente qué elementos, características y métodos de comunicación están disponibles para el cliente. La información se comunica mediante una solicitud que se envía desde el cliente, y los servicios Web de Lync Server responden con una respuesta claramente definida que denomina lo que está disponible para el cliente y cómo ponerse en contacto con esas características en el formato de la detección automática. Documento de respuesta.

La mejor manera de comprender el documento de respuesta de detección automática, incluido el modo en que los servicios web comunican las características a los clientes a través de este documento, es dissect y definir cada línea en una respuesta típica del documento de respuesta de detección automática del servicio Web de Lync.

<div class="">


> [!NOTE]  
> En los detalles siguientes, el usuario ya se ha autenticado en el servidor principal respondiendo a una solicitud de autenticación.



</div>

<div class="">


> [!NOTE]  
> El servicio Web de detección automática de Lync se define en los <STRONG>protocolos de Microsoft Office</STRONG> , en la sección <STRONG>Especificaciones abiertas</STRONG> de la biblioteca de <STRONG>Microsoft Developer Network</STRONG> (MSDN). Para obtener más información, consulte el documento de especificación completa, "Protocolo de servicio Web de Lync Autodiscover" en: <A href="http://go.microsoft.com/fwlink/?linkid=273839">http://go.microsoft.com/fwlink/?LinkId=273839</A>. Para obtener más información sobre la autenticación, consulte "Protocolo de servicio Web <A href="http://go.microsoft.com/fwlink/?linkid=279015">http://go.microsoft.com/fwlink/?LinkId=279015</A>de autenticación de OC" en.



</div>

<div>

## <a name="the-lync-server-web-service-autodiscover-response"></a>Respuesta de detección automática del servicio Web de Lync Server

La respuesta devuelta cuando se envía la solicitud de detección automática es la misma para un cliente interno o externo. Algunos parámetros que tienen en cuenta la ubicación pueden cambiar. Si se recibe una solicitud de cliente pero la agrupación real es distinta de la que se ha contactado, el grupo de inicio del usuario se establecerá para ese usuario. Un colega cuya cuenta de usuario se encuentra en un grupo diferente, pero que inicia sesión desde la misma oficina, obtendría una respuesta algo diferente. La respuesta indica el servidor frontal o el grupo de servidores front-end correcto para ese usuario.

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

El documento de respuesta de detección automática puede tener uno de los dos formatos siguientes: El formato predeterminado es una notación de objetos de JavaScript (JSON). El otro formato es un documento de lenguaje de marcado extensible (XML). En este ejemplo se usa el código XML. La solicitud y la respuesta son predecibles porque el documento tiene un esquema definido que determina el formato. La línea del documento que describe el esquema utilizado es la primera línea de la solicitud o respuesta:

    <AutodiscoverResponse xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" AccessLocation="External">

La definición de **AccessLocation = "external"** indica que la solicitud se realizó desde un usuario externo.

    <SipServerInternalAccess fqdn="pool01.contoso.com" port="5061"/>

&nbsp;

    <SipServerExternalAccess fqdn="sip.contoso.com" port="5061"/>

Actualmente, SipServerInternalAccess y SipServerExternalAccess no se usan. Estas entradas se reservan para usarlas en el futuro.

    <SipClientInternalAccess fqdn=" pool01.contoso.com" port="443"/>

&nbsp;

    <SipClientExternalAccess fqdn="sip.contoso.com " port="443"/>

SipClientInternalAccess y SipClientExternalAccess describen el nombre de dominio completo y el puerto que usará un cliente interno o externo para acceder al servidor SIP definido. El cliente de escritorio de Lync y la aplicación de la tienda Windows de Lync usan estas entradas, en función de su ubicación (interna o externa) para buscar el director o el servidor front-end.

    <Link token="Internal/Autodiscover" href="https://webinternal.contoso.net/Autodiscover/AutodiscoverService.svc/root"/>

&nbsp;

    <Link token ="External/Autodiscover" href="https://webexternal.contoso.com/Autodiscover/AutodiscoverService.svc/root"/>

Las `Autodiscover` referencias contienen los puntos de entrada de servicio del servicio Detección automática. El atributo token contiene el nombre del servicio y el href es una dirección URL que define el cliente en el que se puede encontrar el servicio. Los clientes de una red externa usan `External/Autodiscover`el. El servicio de detección automática se instala como parte del proceso de implementación. `Internal/Autodiscover`no se utiliza actualmente y se reserva para su uso futuro.

    <Link token="Internal/AuthBroker" href="https://webinternal.contoso.net/Reach/sip.svc"/>

&nbsp;

    <Link token="External/AuthBroker" href="https://webexternal.contoso.com/Reach/sip.svc"/>

Las `AuthBroker` referencias contienen los puntos de entrada de servicio para el servicio agente de autenticación interno y externo, en este caso, SIP. SVC. El atributo token contiene el nombre del servicio y el href es una dirección URL que define el cliente en el que se puede encontrar el servicio. Clientes de la red interna que usan `Internal/AuthBroker`. Los clientes de una red externa usan `External/AuthBroker`el. El servicio de AuthBroker se instala como parte del proceso de implementación de los servicios Web internos de la implementación de Lync Server 2013.

    <Link token="Internal/WebScheduler" href="https://webinternal.contoso.net/Scheduler"/>

&nbsp;

    <Link token="External/WebScheduler" href="https://webexternal.contoso.com/Scheduler"/>

El `WebScheduler` token hace referencia a las direcciones URL para el acceso de cliente a la programación basada en web para conferencias de Lync Server. En este momento, `External/WebScheduler` solo se usa el. El programa web se instala como parte del proceso de implementación de los servicios Web internos de la implementación de Lync Server 2013.

    <Link token="Internal/Mcx" href="https://webexternal.contoso.net/Mcx/McxService.svc"/>

&nbsp;

    <Link token="External/Mcx" href="https://webexternal.contoso.com/Mcx/McxService.svc"/>

`Internal/Mcx`y `External/Mcx` son las ubicaciones de los servicios de movilidad que se introdujeron en la actualización acumulativa para Lync Server 2010:2011 de noviembre. Estas referencias seguirán siendo usadas por Lync 2010 Mobile en todos los dispositivos compatibles. El servicio de MCX se instala como parte del proceso de implementación de los servicios Web internos de la implementación de Lync Server 2013.

    <Link token="Internal/Ucwa" href="https://webinternal.contoso.net/ucwa/v1/applications"/>

&nbsp;

    <Link token="External/Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>

&nbsp;

    <Link token="Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>

**Interno/ucwa**, **externo/ucwa** y **ucwa** proporcionan un medio para que los clientes tengan acceso a la interfaz de programación de aplicaciones Web de comunicaciones unificadas (API de ucwa o simplemente Ucwa). `Internal/Ucwa`y `External/Ucwa` los directorios virtuales son puntos de acceso reservados para futuras mejoras de características, y no se usan. El `Ucwa` directorio virtual se usa para Microsoft Lync Mobile (introducido con lync Server 2013) en todos los dispositivos compatibles. El servicio UCWA se instala como parte del proceso de implementación de los servicios Web internos de la implementación de Lync Server 2013.

    <Link token="Internal/XFrame" href="https://webinternal.contoso.net/Autodiscover/XFrame/XFrame.html"/>

&nbsp;

    <Link token="External/XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>

&nbsp;

    <Link token="XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>

`Internal/XFrame`, **Externo/XFrame** y **XFrame** proporcionan acceso a las aplicaciones de servidor basadas en UCWA. XFrame se instala como parte del proceso de implementación de los servicios Web internos de la implementación de Lync Server 2013.

    <Link token="Self" href="https://webexternal.contoso.net/Autodiscover/AutodiscoverService.svc/root/user"/>

El `Self` token hace referencia a información específica del cliente (tipo de respuesta de usuario) que está realizando la solicitud. El cliente que hizo esta solicitud era externo, y esta referencia de la detección automática es a la parte de usuario del servicio de detección automática.

</div>

</div>

<div>

## <a name="see-also"></a>Vea también


[Requisitos del sistema para componentes perimetrales para Lync Server 2013](lync-server-2013-system-requirements-for-external-user-access-components.md)  
[Planificación de la detección automática en Lync Server 2013](lync-server-2013-planning-for-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

