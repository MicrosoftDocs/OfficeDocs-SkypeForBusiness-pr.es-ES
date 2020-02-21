---
title: 'Lync Server 2013: requisitos técnicos para la movilidad'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for mobility
ms:assetid: 831be681-4de0-4e42-b04f-8879ca4dcd23
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690030(v=OCS.15)
ms:contentKeyID: 48184679
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9628248922742ce46037c94f8257823e4484d168
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194843"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-mobility-in-lync-server-2013"></a>Requisitos técnicos para la movilidad en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-07-24_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Los usuarios móviles experimentan varios escenarios de aplicaciones móviles que requieren una planeación especial. Por ejemplo, alguien podría empezar a usar una aplicación móvil mientras estaba lejos del trabajo conectándose a través de la red 3G, cambiar a la red Wi-Fi corporativa cuando llegue al trabajo y, a continuación, cambiar de nuevo a 3G cuando abandone el edificio. Debe planear su entorno para admitir estas transiciones de red y garantizar una experiencia del usuario consistente. En esta sección se describen los requisitos de infraestructura necesarios para admitir aplicaciones móviles y la detección automática de recursos de movilidad.

<div>


> [!NOTE]  
> Aunque las aplicaciones móviles también se pueden conectar a otros servicios de Lync Server 2013, el requisito de enviar todas las solicitudes Web de aplicaciones móviles al mismo nombre de dominio completo (FQDN) web externo solo se aplica al servicio de movilidad de Lync Server 2013. Otros servicios de movilidad no requieren esta configuración.



</div>

El requisito de la afinidad de cookies en los equilibradores de carga de hardware se reduce drásticamente y se sustituye la afinidad del Protocolo de control de transmisión (TCP) si se usa Lync Mobile ofrecido con Lync Server 2013. La afinidad de cookies todavía se puede usar, pero los servicios web ya no la necesitan.

<div>


> [!IMPORTANT]  
> Todo el tráfico del servicio de movilidad pasa a través del proxy inverso, independientemente de dónde se encuentra el punto de origen: interno o externo. En el caso de un solo proxy inverso o una granja de servidores proxy inversos, o un dispositivo que proporciona la función de proxy inverso, puede producirse un problema cuando el tráfico interno está en salida a través de una interfaz e intenta inmediatamente realizar la entrada en la misma interfaz. Esto suele conducir a una violación de la regla de seguridad conocida como suplantación de paquetes TCP o simplemente imitación. Se debe permitir el <EM>anclaje del cabello</EM> (la salida y los ingresos inmediatos de un paquete o una serie de paquetes) para que la movilidad funcione. Una forma de solucionar este problema es usar un proxy inverso que sea independiente del firewall (la regla de prevención de suplantación de identidad siempre debe aplicarse en el firewall, por motivos de seguridad). La horquilla puede producirse en la interfaz externa del proxy inverso en lugar de la interfaz externa del firewall. Se detecta la suplantación de identidad en el firewall y se relaja la regla en el proxy inverso, lo que permite el horquilla que requiere la movilidad.<BR>Use el host del sistema de nombres de dominio (DNS) o registros CNAME para definir el proxy inverso para el comportamiento de horquilla (no el firewall), si es posible.



</div>

Lync Server 2013 admite Mobility Services for Lync 2010 Mobile and Lync 2013 Mobile clients. Ambos clientes usan el servicio Detección automática de Lync Server 2013 para encontrar su punto de entrada de movilidad, pero difieren en el servicio de movilidad que usan. Lync 2010 Mobile usa el servicio de movilidad conocido como *MCX*, que se incorporó con la actualización acumulativa para Lync Server 2010:2011 de noviembre. Los clientes móviles de Lync 2013 usan la API Web de comunicaciones unificadas, o *UCWA*, como su proveedor de servicios de movilidad.

<div>

## <a name="internal-and-external-dns-configuration"></a>Configuración de DNS interno y externo

La MCX de los servicios de movilidad (que se incorporó en la actualización acumulativa de Lync Server 2010: noviembre de 2011) y UCWA (presentada en las actualizaciones acumulativas para Lync Server 2013: febrero de 2013) usan DNS de la misma manera.

Cuando se usa la detección automática, los dispositivos móviles usan DNS para buscar recursos. Durante la búsqueda de DNS, se intenta primero una conexión con el FQDN asociado con el registro DNS interno (lyncdiscoverinternal.\< nombre\>de dominio interno). Si no se puede realizar una conexión mediante el registro DNS interno, se intenta establecer una conexión mediante el registro DNS externo (lyncdiscover.\< sipdomain\>). Un dispositivo móvil que es interno respecto a la red se conecta a la URL del servicio Detección automática interna y un dispositivo móvil que es externo respecto a la red se conecta a la URL del servicio Detección automática externa. Las solicitudes de detección automática externas van a través del proxy inverso. El servicio Detección automática de Lync Server 2013 devuelve todas las direcciones URL de servicios web para el grupo de servidores principales del usuario, incluidas las direcciones URL del servicio de movilidad (MCX y UCWA). No obstante, la URL del servicio de movilidad interno y la URL del servicio de movilidad externo están asociadas al FQDN de servicios web externos. Por lo tanto, independientemente de si un dispositivo móvil es interno o externo a la red, el dispositivo siempre se conecta al servicio de movilidad de Lync Server 2013 de forma externa a través del proxy inverso.

<div>


> [!NOTE]  
> Es importante comprender que la implementación puede constar de varios espacios de nombres distintos para uso interno y externo. El nombre de dominio SIP puede ser diferente del nombre de dominio de implementación interna. Por ejemplo, el dominio SIP puede ser <STRONG>contoso.com</STRONG>, mientras que la implementación interna puede ser <STRONG>contoso.net</STRONG>. Los usuarios que inicien sesión en Lync Server usarán el nombre de dominio SIP, como <STRONG>John@contoso.com</STRONG>. Al tratar los servicios web externos (definidos en el generador de topologías como <STRONG>servicios web externos</STRONG>), el nombre de dominio y el nombre de dominio SIP serán coherentes, tal y como se define en DNS. Al tratar los servicios Web internos (definidos en el generador de topologías como <STRONG>servicios Web internos</STRONG>), el nombre predeterminado de los servicios Web internos será el FQDN del servidor front-end, del grupo de servidores front-end, del director o del grupo de directores. Tiene la opción de invalidar el nombre de los servicios Web internos. Debe usar el nombre de dominio interno (y no el nombre de dominio SIP) para los servicios Web internos y definir el registro de host DNS A (o, para IPv6, AAAA) para reflejar el nombre reemplazado. Por ejemplo, el FQDN de servicios Web interno predeterminado puede ser <STRONG>pool01.contoso.net</STRONG>. Un FQDN de servicios Web interno invalidado puede ser <STRONG>webpool.contoso.net</STRONG>. La definición de los servicios Web de esta forma ayuda a garantizar que la localidad interna y externa de los servicios, y no la localidad del usuario que los usa, se observa.<BR>Sin embargo, dado que los servicios web se definen en Topology Builder y el nombre de los servicios Web internos se puede invalidar, siempre que el nombre de los servicios Web resultante, el certificado que lo valida y los registros DNS que lo definen sean coherentes, puede definir el servicios Web internos con cualquier nombre de dominio, incluido el nombre de dominio SIP, que desee. En última instancia, la resolución del nombre de la dirección IP se determina por los registros de host DNS y un espacio de nombres coherente.<BR>Para los fines de este tema y los ejemplos, el nombre de dominio interno se usa para ilustrar la topología y las definiciones de DNS.



</div>

El siguiente diagrama ilustra el flujo de solicitudes Web de aplicaciones móviles para el servicio de movilidad y para el servicio de detección automática cuando se usa una configuración de DNS interna y externa.

**Flujo del servicio de movilidad con detección automática**

![cdb96424-96f2-4abf-88d7-1d32d1010ffd](images/Hh690030.cdb96424-96f2-4abf-88d7-1d32d1010ffd(OCS.15).jpg "cdb96424-96f2-4abf-88d7-1d32d1010ffd")

<div>


> [!NOTE]  
> El diagrama ilustra los servicios web genéricos. Un directorio virtual denominado Mobility describe los servicios de movilidad MCX o UCWA. Si no ha aplicado las actualizaciones acumulativas para Lync Server 2013:2013 de febrero, puede o no tener el directorio virtual Ucwa definido en los servicios Web internos y externos. Tendrá un directorio virtual detección automática, y es posible que tenga un directorio virtual MCX.<BR>La detección automática y la detección de servicios funcionan del mismo modo, independientemente de la tecnología de los servicios de movilidad que haya implementado.



</div>

Para admitir usuarios móviles de dentro y de fuera de la red corporativa, los FQDN de web interno y externo deben cumplir algunos requisitos previos. Además, es posible que deba cumplir otros requisitos en función de las características que decida implementar:

  - Nuevos registros DNS, CNAME o A (host, si IPv6, AAAA) para la detección automática.

  - Nueva regla de firewall, si desea admitir notificaciones de inserción a través de la red Wi-Fi.

  - Nombres alternativos de sujeto en certificados de servidor interno y en certificados de proxy inverso para la detección automática.

  - La afinidad de origen de los cambios de configuración del equilibrador de carga de hardware del servidor front-end.

La topología debe cumplir los siguientes requisitos para admitir el servicio de movilidad y el servicio Detección automática:

  - El FQDN Web interno del grupo de servidores front-end debe ser distinto del FQDN Web externo del grupo de servidores front-end.

  - El FQDN de web interno debe resolverse solamente en la red corporativa y ser accesible desde ella.

  - El FQDN de Web externo solo debe resolver y ser accesible desde Internet.

  - Para un usuario que está dentro de la red corporativa, la URL del servicio de movilidad debe dirigirse al FQDN de web externo. Este requisito es para el servicio de movilidad y se aplica solamente a esta URL.

  - Para un usuario que está fuera de la red corporativa, la solicitud debe ir al FQDN de Web externo del grupo o el director front-end.

Si admite la detección automática, debe crear los siguientes registros DNS para cada dominio SIP:

  - Un registro DNS interno para admitir usuarios móviles que se conectan desde dentro de la red de la organización.

  - Un registro DNS externo, o público, para admitir usuarios móviles que se conectan desde Internet.

La URL de detección automática interna no debería ser direccionable desde fuera de su red. La URL de detección automática externa no debería ser direccionable desde dentro de su red. Sin embargo, si no cumple este requisito para la dirección URL externa, es probable que el cliente móvil no se vea afectado, ya que la dirección URL interna siempre se prueba en primer lugar.

Los registros DNS pueden ser registros CNAME o registros (host, en el caso de IPv6, AAAA).

<div>


> [!NOTE]  
> Los clientes de dispositivos móviles no admiten varios certificados de capa de sockets seguros (SSL) de distintos dominios. Por lo tanto, la redirección de CNAME a distintos dominios no se admite a través de HTTPS. Por ejemplo, un registro CNAME de DNS para lyncdiscover.contoso.com que se redirige a una dirección de director.contoso.net no se admite a través de HTTPS. En una topología así, un cliente de dispositivo móvil necesita usar HTTP para la primera solicitud, de modo que la redirección de CNAME se resuelva a través de HTTP. A continuación, las solicitudes posteriores usan HTTPS. Para admitir este escenario, debe configurar el proxy inverso con una regla de publicación web para el puerto 80 (HTTP). Para obtener información detallada, consulte "para crear una regla de publicación web para el puerto 80" en <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Configuring the inverso proxy for Mobility in Lync Server 2013</A>.<BR>La redirección de CNAME al mismo dominio se admite a través de HTTPS. En este caso, el certificado del dominio de destino cubre el dominio de origen.



</div>

Para obtener más información sobre los registros DNS necesarios para su escenario, consulte [Resumen de DNS-detección automática en Lync Server 2013](lync-server-2013-dns-summary-autodiscover.md).

</div>

<div>

## <a name="port-and-firewall-requirements"></a>Requisitos de puerto y de firewall

Si admite notificaciones de inserción y desea que dispositivos móviles de Apple las reciban a través de su red Wi-Fi, también debe abrir el puerto 5223 en la red Wi-Fi de su empresa. El puerto 5223 es un puerto TCP saliente usado por el servicio de notificación de inserción de Apple (APNS). El dispositivo móvil inicia la conexión. Para obtener más información [http://support.apple.com/kb/TS1629](http://support.apple.com/kb/ts1629) , consulte.

<div>


> [!WARNING]  
> Un dispositivo Apple que use el cliente móvil de Lync 2013 no necesita notificaciones de inserción.



</div>

Tenga en cuenta que si un usuario se hospeda en una aplicación de sucursal con funciones de supervivencia (SBA), se requieren los siguientes puertos:

  - UcwaSipExternalListeningPort requiere el puerto 5088

  - UcwaSipPrimaryListeningPort requiere el puerto 5089

Para obtener información adicional y orientación sobre los requisitos de puertos y protocolos para la detección automática, consulte [Port Summary-Autodiscover en Lync Server 2013](lync-server-2013-port-summary-autodiscover.md).

</div>

<div>

## <a name="certificate-requirements"></a>Requisitos de certificado

Si admite la detección automática para clientes móviles de Lync, debe modificar las listas de nombres alternativos de sujeto en los certificados para admitir conexiones seguras desde los clientes móviles. Debe solicitar y asignar certificados nuevos, agregando las entradas de nombre alternativo de sujeto descritas en esta sección, para cada servidor front-end y director que ejecuta el servicio de detección automática. El enfoque recomendado es modificar también las listas de nombres alternativos de sujeto en certificados para sus proxies inversos. Debe agregar entradas de nombre alternativo de sujeto para cada dominio SIP de su organización.

La reemisión de certificados mediante una entidad de certificación interna suele ser un proceso sencillo, pero agregar varias entradas de nombre alternativo de sujeto a certificados públicos usados por el proxy inverso puede ser caro. Si tiene muchos dominios SIP, lo que provoca que agregar nombres alternativos de sujeto sea muy caro, puede configurar el proxy inverso para realizar la solicitud inicial del servicio Detección automática a través del puerto 80 usando HTTP, en lugar del puerto 443 usando HTTPS (la configuración predeterminada). A continuación, la solicitud se redirige al puerto 8080 en el director o en el grupo de servidores front-end. Al publicar la solicitud inicial del servicio Detección automática en el puerto 80, no debe cambiar los certificados para el proxy inverso, porque la solicitud usa HTTP en lugar de HTTPS. Este enfoque es compatible, pero no lo recomendamos.

</div>

<div>

## <a name="internet-information-services-iis-requirements"></a>Requisitos de Internet Information Services (IIS)

Se recomienda usar IIS 7,5, IIS 8,0 o IIS 8,5 para la movilidad. El instalador del servicio de movilidad establece marcas en ASP.NET para mejorar el rendimiento. IIS 7,5 está instalado de forma predeterminada en Windows Server 2008 R2, IIS 8,0 está instalado en Windows Server 2012 y IIS 8,5 está instalado en Windows Server 2012 R2. El instalador del servicio de movilidad cambia automáticamente la configuración de ASP.NET.

</div>

<div>

## <a name="hardware-load-balancer-requirements"></a>Requisitos del equilibrador de carga de hardware

En el equilibrador de carga de hardware que admite el grupo de servidores front-end, las direcciones IP virtuales (VIP) de servicios web externos para el tráfico de servicios web deben configurarse para el origen. La afinidad de origen ayuda a garantizar que varias conexiones de un único cliente se envían a un servidor para mantener el estado de la sesión. Para obtener más información sobre los requisitos de afinidad, consulte [requisitos de equilibrio de carga para Lync Server 2013](lync-server-2013-load-balancing-requirements.md).

Si planea admitir clientes móviles de Lync solo a través de la red Wi-Fi interna, debe configurar VIP de servicios Web internos para el origen como se describe para VIP de servicios web externos. En esta situación, debe usar la afinidad\_de dirección de origen (o TCP) para los VIP de servicios Web internos en el equilibrador de carga de hardware. Para obtener más información, consulte [requisitos de equilibrio de carga para Lync Server 2013](lync-server-2013-load-balancing-requirements.md).

</div>

<div>

## <a name="reverse-proxy-requirements"></a>Requisitos de proxy inverso

Si admite la detección automática para clientes móviles de Lync, debe actualizar la regla de publicación actual de la siguiente manera:

  - Si decide actualizar las listas de nombres alternativos de sujeto en los certificados de proxy inverso y usa HTTPS para la solicitud de servicio de detección automática inicial, debe actualizar la regla de publicación web para lyncdiscover. \<sipdomain\>. Normalmente, se combina con la regla de publicación para la dirección URL de servicios web externos en el grupo de servidores front-end.

  - Si decide usar HTTP para la solicitud de servicio de detección automática inicial para que no tenga que actualizar la lista de nombres alternativos de sujeto en los certificados de proxy inverso, debe crear una nueva regla de publicación web para el puerto HTTP/TCP 80, si no existe uno ya. Si ya existe una regla para HTTP/TCP 80, puede actualizar dicha regla para que incluya la lyncdiscover. \<entrada\> sipdomain.

</div>

</div>

<span> </span>

</div>

</div>

</div>

