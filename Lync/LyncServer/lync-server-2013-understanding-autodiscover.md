---
title: Comprender la detección automática
TOCTitle: Comprender la detección automática
ms:assetid: d70a15b7-750b-4e0f-9a7f-0254d6d486c3
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ945654(v=OCS.15)
ms:contentKeyID: 52061775
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Comprender la detección automática

 

_**Última modificación del tema:** 2016-12-08_

El servicio Detección automática de Lync Server 2013 es una característica que apareció inicialmente en Microsoft Lync Server 2010 como parte de la actualización acumulada de Lync Server 2010 de noviembre de 2011. Aparte de las correcciones pertinentes, esta actualización acumulada daba soporte a clientes de Lync Mobile y Lync 2013.

En Lync Server 2013, el servicio Detección automática es parte integral del funcionamiento de los clientes móviles internos y externos y, además, también se amplía a nuevos clientes, como la Aplicación de la Tienda Windows de Lync para Windows 8, de reciente aparición. Los clientes de escritorio de Lync 2013 también hacen uso de Detección automática. Este servicio se identifica en Lync Server por medio de los registros de Sistema de nombres de dominio (DNS) **lyncdiscover.\<dominio\>** y **lyncdiscoverinternal.\<dominio\>**. Además, las versiones más recientes de Lync 2010 y Lync 2013 prefieren Detección automática a los registros SRV de Sistema de nombres de dominio (DNS), a los que recurren únicamente cuando lyncdiscover.\<dominio\> o lyncdiscoverinternal.\<dominio\> no responden o no se resuelven. La Aplicación de la Tienda Windows de Lync para Windows 8 y Lync Mobile solo usan Detección automática, y no remiten a los tradicionales registros SRV de DNS.

En Lync Server 2013, Detección automática se amplía para indicar al cliente qué elementos, características y métodos de comunicación tiene a su disposición. La información se transmite a través de una solicitud que se envía desde el cliente y a la que los servicios web de Lync Server responden con una respuesta perfectamente definida en la que se señalan los nombres que hay disponibles para el cliente y cómo ponerse en contacto con esas características en el formato de documento de respuesta de Detección automática.

La mejor forma de saber qué es un documento de respuesta de Detección automática (así como el modo en que los servicios web informan de las características a los clientes a través de dicho documento) consiste en diseccionar y definir cada línea de una respuesta típica de un documento de respuesta de Detección automática de servicio web de Lync.


> [!NOTE]
> En los siguientes detalles, el usuario ya se ha autenticado en el servidor principal respondiendo a una solicitud.




> [!NOTE]
> El servicio web Detección automática se define en los <STRONG>protocolos de Microsoft&nbsp;Office</STRONG>, en la sección sobre <STRONG>especificaciones abiertas</STRONG> de la biblioteca de <STRONG>red de desarrolladores de Microsoft</STRONG> (MSDN). Si desea obtener información detallada, consulte el documento de especificaciones completo sobre el protocolo de servicio web de Detección automática de Lync, en <A class=uri href="http://go.microsoft.com/fwlink/?linkid=273839">http://go.microsoft.com/fwlink/?linkid=273839</A>. Si desea obtener información detallada sobre la autenticación, consulte el tema sobre el protocolo de servicio web de autenticación OC, en <A class=uri href="http://go.microsoft.com/fwlink/?linkid=279015">http://go.microsoft.com/fwlink/?linkid=279015</A>.



## La respuesta de Detección automática de servicio web de Lync Server

La respuesta que se obtiene cuando la solicitud de Detección automática se envía es la misma en los clientes internos y externos, si bien algunos parámetros en los que se tiene en cuenta la ubicación pueden variar. Cuando se recibe una solicitud de cliente, pero el grupo real difiere del grupo con el que se ha establecido contacto, se establecerá el grupo principal del usuario correspondiente. Un compañero que inicie sesión en la misma oficina, pero cuya cuenta de usuario está en otro grupo, podría obtener una respuesta algo diferente. La respuesta refleja el Servidor front-end o Grupo de servidores front-end correcto para dicho usuario.

Ejemplo de un documento de respuesta de Detección automática:

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

## Detalles del documento de respuesta de Detección automática

El documento de respuesta de Detección automática puede tener dos formatos; el formato predeterminado es una notación de objetos JavaScript (JSON), mientras que el otro es un documento de lenguaje de marcado extensible (XML). En este ejemplo usamos el formato XML. La solicitud y la respuesta son predecibles porque el documento tiene un esquema definido que determina el formato. La línea del documento en la que se describe el esquema utilizado es la primera línea de la solicitud o respuesta:

    <AutodiscoverResponse xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" AccessLocation="External">

La definición de **AccessLocation=”External”** pone de manifiesto que la solicitud se ha realizado desde un usuario externo.

  ```
  <SipServerInternalAccess fqdn="pool01.contoso.com" port="5061"/>
  ```
  ```
  <SipServerExternalAccess fqdn="sip.contoso.com" port="5061"/>
  ```

Las entradas SipServerInternalAccess y SipServerExternalAccess no se usan en este momento, sino que reservarán para un uso futuro.

  ```
  <SipClientInternalAccess fqdn=" pool01.contoso.com" port="443"/>
  ```
  ```
  <SipClientExternalAccess fqdn="sip.contoso.com " port="443"/>
  ```

SipClientInternalAccess y SipClientExternalAccess describen el nombre de dominio completo y el puerto que un cliente interno o externo va a usar para acceder al servidor SIP definido. El cliente de escritorio de Lync y la Aplicación de la Tienda Windows de Lync usan estas entradas en función de sus ubicaciones (interna o externa) para encontrar el Director o el Servidor front-end.

  ```
  <Link token="Internal/Autodiscover" href="https://webinternal.contoso.net/Autodiscover/AutodiscoverService.svc/root"/>
  ```

  ```
  <Link token ="External/Autodiscover" href="https://webexternal.contoso.com/Autodiscover/AutodiscoverService.svc/root"/>
  ```
La referencias de `Autodiscover` contienen los puntos de entrada de servicio del servicio Detección automática. El atributo de token contiene el nombre del servicio, mientras que href es una dirección URL que se define para el cliente donde se puede detectar el servicio. Los clientes en una red externa usan `External/Autodiscover`. El servicio Detección automática se instala como parte del proceso de implementación. `Internal/Autodiscover` no se usa por el momento, sino que se reserva para un uso futuro.

  ```
  <Link token="Internal/AuthBroker" href="https://webinternal.contoso.net/Reach/sip.svc"/>
  ```
  ```
  <Link token="External/AuthBroker" href="https://webexternal.contoso.com/Reach/sip.svc"/>
  ```
Las referencias de `AuthBroker` contienen los puntos de entrada de servicio del servicio de agente de autenticación interno y externo, en este caso, sip.svc. El atributo de token contiene el nombre del servicio, mientras que href es una dirección URL que se define para el cliente donde se puede detectar el servicio. Los clientes en una red interna usan `Internal/AuthBroker` y los clientes en una red externa, `External/AuthBroker`. El servicio AuthBroker se instala como parte del proceso de implementación de los servicios web de implementación de Lync Server 2013 internos.

  ```
  <Link token="Internal/WebScheduler" href="https://webinternal.contoso.net/Scheduler"/>
  ```
  ```
  <Link token="External/WebScheduler" href="https://webexternal.contoso.com/Scheduler"/>
  ```
El token `WebScheduler` hace referencia a las direcciones URL para el acceso de clientes a la programación basada en web de las conferencias de Lync Server. Actualmente, solo se usa `External/WebScheduler`. WebScheduler se instala como parte del proceso de implementación de los servicios web de implementación de Lync Server 2013 internos.

  ```
  <Link token="Internal/Mcx" href="https://webexternal.contoso.net/Mcx/McxService.svc"/>
  ```
  ```
  <Link token="External/Mcx" href="https://webexternal.contoso.com/Mcx/McxService.svc"/>
  ```
`Internal/Mcx` y `External/Mcx` son las ubicaciones de los servicios de movilidad, que aparecieron con la actualización acumulada para Lync Server 2010 de noviembre de 2011. Lync 2010 Mobile seguirá usando estas referencias en todos los dispositivos compatibles. El servicio Mcx se instala como parte del proceso de implementación de los servicios web de implementación de Lync Server 2013 internos.

  ```
  <Link token="Internal/Ucwa" href="https://webinternal.contoso.net/ucwa/v1/applications"/>
  ```
  ```
  <Link token="External/Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>
  ```
  ```
  <Link token="Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>
  ```
**Internal/Ucwa**, **External/Ucwa** y **Ucwa** proporcionan el medio para que los clientes puedan acceder a la interfaz de programación de aplicaciones web de comunicaciones unificadas (API de UCWA o, simplemente, UCWA). Los directorios virtuales `Internal/Ucwa` y `External/Ucwa` son puntos de acceso que se reservan para futuras mejoras de las características y no se usan. El directorio virtual `Ucwa` se usa para Microsoft Lync Mobile (incluido en Lync Server 2013) en todos los dispositivos compatibles. El servicio UCWA se instala como parte del proceso de implementación de los servicios web de implementación de Lync Server 2013 internos.

  ```
  <Link token="Internal/XFrame" href="https://webinternal.contoso.net/Autodiscover/XFrame/XFrame.html"/>
  ```
  ```
  <Link token="External/XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>
  ```
  ```
  <Link token="XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>
  ```

`Internal/XFrame`, **External/XFrame** y **XFrame** dan acceso a las aplicaciones de servidor basadas en UCWA. XFrame se instala como parte del proceso de implementación de los servicios web de implementación de Lync Server 2013 internos.

    <Link token="Self" href="https://webexternal.contoso.net/Autodiscover/AutodiscoverService.svc/root/user"/>

El token `Self` hace referencia a la información específica del cliente (tipo de respuesta del usuario) que está realizando la solicitud. El cliente que ha realizado esta solicitud es externo, y esta referencia de Detección automática corresponde a la parte de usuario del servicio Detección automática.

## Vea también

#### Otros recursos

[Requisitos del sistema para componentes perimetrales para Lync Server 2013](lync-server-2013-system-requirements-for-external-user-access-components.md)  
[Planear la detección automática en Lync Server 2013](lync-server-2013-planning-for-autodiscover.md)

