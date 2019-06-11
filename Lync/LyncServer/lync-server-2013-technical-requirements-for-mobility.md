---
title: 'Lync Server 2013: Requisitos técnicos para la movilidad'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Technical requirements for mobility
ms:assetid: 831be681-4de0-4e42-b04f-8879ca4dcd23
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690030(v=OCS.15)
ms:contentKeyID: 48184679
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac74f7e9e85829e500900e03d4b7cfedf89d1e0b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850453"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-mobility-in-lync-server-2013"></a>Requisitos técnicos para la movilidad en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-07-24_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Los usuarios móviles pueden encontrarse con diversos escenarios de aplicaciones móviles que requieren una planificación especial. Por ejemplo, alguien podría empezar a usar una aplicación móvil mientras está fuera de trabajo conectándose a través de la red 3G, cambiar a la red Wi-Fi corporativa al llegar al trabajo y, a continuación, volver a 3G cuando abandone el edificio. Debe planificar su entorno para que admita dichas transiciones de red y garantizar una experiencia de usuario coherente. En esta sección se describen los requisitos de infraestructura que debe tener para admitir las aplicaciones móviles y el descubrimiento automático de recursos de movilidad.

<div>


> [!NOTE]  
> Aunque las aplicaciones móviles también pueden conectarse a otros servicios de Lync Server 2013, el requisito de enviar todas las solicitudes Web de aplicaciones móviles al mismo nombre de dominio completo (FQDN) de la web externa solo se aplica al servicio de movilidad de Lync Server 2013. Otros servicios de movilidad no requieren esta configuración.



</div>

El requisito de afinidad de cookies en los equilibradores de carga de hardware se reduce drásticamente y usted sustituye la afinidad del Protocolo de control de transmisión (TCP) si usa Lync Mobile entregado con Lync Server 2013. La afinidad de cookies aún puede usarse, pero los servicios web ya no la necesitan.

<div>


> [!IMPORTANT]  
> Todo el tráfico del servicio de movilidad pasa por el proxy inverso, independientemente de dónde se encuentra el punto de origen, ya sea interno o externo. En el caso de un único proxy inverso o de una matriz de proxies inversos, o de un dispositivo que proporciona la función de proxy inverso, puede surgir un problema cuando el tráfico interno está desplazado a través de una interfaz e intenta inmediatamente la entrada en la misma interfaz. Esto suele conducir a una violación de la regla de seguridad conocida como imitación de paquetes TCP o suplantación. <EM>Fijación del pelo</EM> (los ingresos y salidas inmediatos de un paquete o serie de paquetes) deben permitirse para que la movilidad funcione. Una forma de resolver este problema es usar un proxy inverso que sea independiente del firewall (la regla de prevención de suplantaciones debe aplicarse siempre en el firewall, por razones de seguridad). El Hairpin puede producirse en la interfaz externa del proxy inverso, en lugar de en la interfaz externa del firewall. Usted detecta la suplantación de identidad en el firewall y relaja la regla en el proxy inverso, lo que permite el Hairpin que requiere la movilidad.<BR>Use el host del sistema de nombres de dominio (DNS) o los registros CNAME para definir el proxy inverso para el comportamiento Hairpin (no el firewall), si es posible.



</div>

Lync Server 2013 es compatible con los servicios de movilidad para Lync 2010 Mobile y los clientes móviles de Lync 2013. Ambos clientes usan el servicio Detección automática de Lync Server 2013 para encontrar su punto de entrada de movilidad pero varían según el servicio de movilidad que usen. Lync 2010 Mobile usa el servicio de movilidad conocido como *MCX*, presentado con la actualización acumulativa para Lync Server 2010:2011 de noviembre. Los clientes móviles de Lync 2013 usan la API Web de comunicaciones unificadas, o *UCWA*, como su proveedor de servicios de movilidad.

<div>

## <a name="internal-and-external-dns-configuration"></a>Configuración DNS interna y externa

Los servicios de movilidad de MCX (introducidos con la actualización acumulativa para Lync Server 2010: noviembre de 2011) y UCWA (introducidos en las actualizaciones acumulativas para Lync Server 2013: febrero de 2013) usan DNS de la misma manera.

Cuando se usa el descubrimiento automático, los dispositivos móviles usan DNS para ubicar recursos. Durante la búsqueda de DNS, se intenta primero una conexión con el FQDN asociado al registro DNS interno (lyncdiscoverinternal.\< nombre\>de dominio interno). Si no se puede realizar una conexión mediante el registro DNS interno, se intenta una conexión mediante el registro DNS externo (lyncdiscover.\< sipdomain\>). Un dispositivo móvil que es interno a la red se conecta a la dirección URL del servicio de detección automática interna y un dispositivo móvil que es externo a la red se conecta a la dirección URL del servicio de detección automática externa. Las solicitudes de detección automática externas atraviesan el proxy inverso. El servicio Detección automática de Lync Server 2013 devuelve todas las direcciones URL de servicios web para el grupo de servidores principales del usuario, incluidas las direcciones URL del servicio de movilidad (MCX y UCWA). Sin embargo, la dirección URL del servicio de movilidad interna y la dirección URL del servicio de movilidad externa están asociados con el FQDN de los servicios web externos. Por tanto, independientemente de si un dispositivo móvil es interno o externo a la red, el dispositivo siempre se conecta al servicio de movilidad de Lync Server 2013 externamente a través del proxy inverso.

<div>


> [!NOTE]  
> Es importante comprender que su implementación puede constar de varios espacios de nombres distintos para uso interno y externo. El nombre de dominio SIP puede ser diferente del nombre de dominio de la implementación interna. Por ejemplo, el dominio SIP puede ser <STRONG>contoso.com</STRONG>, mientras que la implementación interna puede ser <STRONG>contoso.net</STRONG>. Los usuarios que inicien sesión en Lync Server usarán el nombre de dominio SIP, como <STRONG>John@contoso.com</STRONG>. Al tratar los servicios web externos (definidos en el generador de topología como <STRONG>servicios web externos</STRONG>), el nombre de dominio y el nombre de dominio SIP serán coherentes, tal y como se define en DNS. Al tratar los servicios Web internos (definidos en el generador de topología como <STRONG>servicios Web internos</STRONG>), el nombre predeterminado de los servicios Web internos será el FQDN del servidor front-end, del grupo de servidores front-end, del director o del grupo de directores. Tiene la opción de invalidar el nombre de los servicios Web internos. Debe usar el nombre de dominio interno (y no el nombre de dominio SIP) para los servicios Web internos y definir el registro del host DNS A (o, para IPv6, AAAA) para reflejar el nombre reemplazado. Por ejemplo, el FQDN predeterminado de los servicios Web internos puede ser <STRONG>pool01.contoso.net</STRONG>. Un FQDN de servicios Web internos invalidado puede ser <STRONG>webpool.contoso.net</STRONG>. La definición de los servicios Web de esta forma ayuda a garantizar que se respete la localidad interna y externa de los servicios, y no la localidad del usuario que los está usando.<BR>Sin embargo, dado que los servicios web se definen en el generador de topología y el nombre de los servicios Web internos puede reemplazarse, siempre que el nombre de los servicios Web resultante, el certificado que lo valide y los registros DNS que lo definen sean coherentes, puede definir la servicios Web internos con cualquier nombre de dominio, incluido el nombre de dominio de SIP, que desee. En última instancia, la resolución del nombre de la dirección IP la determinan los registros de host DNS y un espacio de nombres coherente.<BR>Para los fines de este tema y los ejemplos, se usa el nombre de dominio interno para ilustrar la topología y las definiciones de DNS.



</div>

En el siguiente diagrama se muestra el flujo de solicitudes Web de aplicaciones móviles para el servicio de movilidad y para el servicio de detección automática cuando se usa una configuración de DNS interna y externa.

**Flujo de servicio de movilidad con detección automática**

![cdb96424-96f2-4abf-88d7-1d32d1010ffd] (images/Hh690030.cdb96424-96f2-4abf-88d7-1d32d1010ffd(OCS.15).jpg "cdb96424-96f2-4abf-88d7-1d32d1010ffd")

<div>


> [!NOTE]  
> El diagrama muestra los servicios web genéricos. Un directorio virtual denominado Mobility describe los servicios de movilidad MCX o UCWA. Si no ha aplicado las actualizaciones acumulativas para Lync Server 2013:2013 de febrero, puede que tenga o no el directorio virtual Ucwa definido en los servicios Web internos y externos. Tendrá una detección automática de directorio virtual y es posible que tenga un directorio virtual MCX.<BR>La detección automática y el descubrimiento de servicios funcionan de la misma manera, independientemente de la tecnología de Mobility Services que haya implementado.



</div>

Para admitir usuarios móviles de dentro y fuera de la red corporativa, los FQDN de la web interna y externa deben cumplir algunos requisitos previos. Además, es posible que tenga que cumplir con otros requisitos, dependiendo de las características que decida implementar:

  - Nuevos registros DNS, CNAME o A (host, si IPv6, AAAA), para el descubrimiento automático.

  - Nueva regla de firewall, si desea admitir notificaciones de inserción a través de la red Wi-Fi.

  - Para el descubrimiento automático, los nombres alternativos del firmante en certificados de servidor interno y en los certificados de proxy inverso.

  - La configuración del equilibrador de carga de hardware de servidor front-end cambia la afinidad de origen.

Su topología debe cumplir con los siguientes requisitos para admitir el servicio de movilidad y el servicio Detección automática:

  - El FQDN de la web interna del grupo de servidores front-end debe ser distinto del FQDN de la web externa del grupo de servidores front-end.

  - El FQDN de la web interna solo debe resolver y ser accesible desde dentro de la red corporativa.

  - El FQDN de la web externa solo debe resolver y ser accesible desde Internet.

  - Para un usuario que está dentro de la red corporativa, la dirección URL del servicio de movilidad debe dirigirse al FQDN de la web externa. Este requisito es para el servicio de movilidad y solo se aplica a esta dirección URL.

  - Para un usuario que está fuera de la red corporativa, la solicitud debe ir al FQDN de la web externa del grupo o del Director de front-end.

Si admite el descubrimiento automático, debe crear los siguientes registros DNS para cada dominio SIP:

  - Un registro DNS interno para admitir usuarios móviles que se conectan desde la red de su organización.

  - Registro DNS externo o público para admitir usuarios móviles que se conectan desde Internet.

La URL de detección automática interna no tiene que ser direccionable desde fuera de su red. La dirección URL de detección automática externa no tiene que ser direccionable desde dentro de su red. Sin embargo, si no puede cumplir con este requisito para la dirección URL externa, es probable que el cliente móvil no se vea afectado, ya que la dirección URL interna siempre se prueba en primer lugar.

Los registros DNS pueden ser registros CNAME o (host, si IPv6, AAAA).

<div>


> [!NOTE]  
> Los clientes de dispositivos móviles no admiten varios certificados de capa de sockets seguros (SSL) de diferentes dominios. Por lo tanto, no se admite la redirección CNAME a dominios diferentes a través de HTTPS. Por ejemplo, un registro CNAME de DNS para lyncdiscover.contoso.com que redirige a una dirección de director.contoso.net no es compatible con HTTPS. En una topología de este tipo, un cliente de dispositivo móvil debe usar HTTP para la primera solicitud, de modo que la redirección CNAME se resuelva por HTTP. Después, las solicitudes posteriores usan HTTPS. Para admitir este escenario, debe configurar el proxy inverso con una regla de publicación web para el puerto 80 (HTTP). Para obtener más información, consulte "para crear una regla de publicación web para el puerto 80" en <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">configurar el proxy inverso para la movilidad en Lync Server 2013</A>.<BR>El redireccionamiento CNAME para el mismo dominio es compatible con HTTPS. En este caso, el certificado del dominio de destino cubre el dominio de origen.



</div>

Para obtener más información sobre los registros DNS necesarios para su escenario, consulte [Resumen de DNS-detección automática en Lync Server 2013](lync-server-2013-dns-summary-autodiscover.md).

</div>

<div>

## <a name="port-and-firewall-requirements"></a>Requisitos de puertos y firewalls

Si admite las notificaciones de inserción y desea que los dispositivos móviles de Apple reciban notificaciones Push a través de su red WiFi, también tendrá que abrir el puerto 5223 en la red Wi-Fi de su empresa. El puerto 5223 es un puerto TCP saliente usado por el servicio de notificaciones push de Apple (APN). El dispositivo móvil inicia la conexión. Para obtener más información [http://support.apple.com/kb/TS1629](http://support.apple.com/kb/ts1629) , consulte.

<div>


> [!WARNING]  
> Un dispositivo Apple que use el cliente móvil de Lync 2013 no necesita notificaciones Push.



</div>

Tenga en cuenta que si un usuario está alojado en un dispositivo de sucursal con la supervivencia (SBA), se necesitan los puertos siguientes:

  - UcwaSipExternalListeningPort necesita el puerto 5088

  - UcwaSipPrimaryListeningPort necesita el puerto 5089

Para obtener más información y orientación sobre los requisitos de puerto y protocolo para la detección automática, consulte [Resumen de puertos-detección automática en Lync Server 2013](lync-server-2013-port-summary-autodiscover.md).

</div>

<div>

## <a name="certificate-requirements"></a>Requisitos de certificados

Si admite el descubrimiento automático para clientes móviles de Lync, debe modificar las listas de nombres alternativos de asunto de los certificados para admitir conexiones seguras desde los clientes móviles. Debe solicitar y asignar certificados nuevos, agregando las entradas de nombre alternativo de asunto descritas en esta sección para cada servidor y director de front-end que ejecute el servicio Detección automática. El enfoque recomendado es modificar también las listas de nombres alternativos de asunto en los certificados de los proxies inversos. Debe agregar entradas de nombre alternativo para todos los dominios SIP de su organización.

La reemisión de certificados mediante una entidad emisora de certificados interna suele ser un proceso simple, pero la adición de varias entradas de nombre alternativo de asunto a certificados públicos que usa el proxy inverso puede ser costosa. Si tiene muchos dominios SIP, lo que hace que la adición de nombres alternativos del sujeto sea muy costosa, puede configurar el proxy inverso para hacer que el servicio de detección automática inicial se solicite en el puerto 80 mediante HTTP, en lugar de con el puerto 443 con HTTPS (la configuración predeterminada). Después, la solicitud se redirige al puerto 8080 del director o del grupo front-end. Al publicar la solicitud de servicio de detección automática inicial en el puerto 80, no es necesario cambiar los certificados del proxy inverso porque la solicitud usa HTTP en lugar de HTTPS. Este enfoque es compatible, pero no lo recomendamos.

</div>

<div>

## <a name="internet-information-services-iis-requirements"></a>Requisitos de servicios de Internet Information Server (IIS)

Le recomendamos que use IIS 7,5, IIS 8,0 o IIS 8,5 para la movilidad. El instalador del servicio de movilidad establece indicadores en ASP.NET para mejorar el rendimiento. IIS 7,5 está instalado de forma predeterminada en Windows Server 2008 R2, IIS 8,0 está instalado en Windows Server 2012 y IIS 8,5 está instalado en Windows Server 2012 R2. El instalador del servicio de movilidad cambia automáticamente la configuración de ASP.NET.

</div>

<div>

## <a name="hardware-load-balancer-requirements"></a>Requisitos del equilibrador de carga de hardware

En el equilibrador de carga de hardware que admite el grupo de servidores front-end, el tráfico de IP virtual de servicios web externos (VIP) del tráfico de servicios web se debe configurar para el origen. La afinidad de origen ayuda a garantizar que se envíen varias conexiones de un solo cliente a un servidor para mantener el estado de la sesión. Para obtener más información sobre los requisitos de afinidad, consulte [requisitos de equilibrio de carga para Lync Server 2013](lync-server-2013-load-balancing-requirements.md).

Si tiene previsto admitir clientes móviles de Lync solo en su red Wi-Fi interna, debe configurar los VIP de los servicios Web internos como se describe para los VIP de servicios web externos. En esta situación, debe usar la afinidad\_de dirección de origen (o TCP) para los VIP de los servicios Web internos en el equilibrador de carga de hardware. Para obtener más información, consulte [requisitos de equilibrio de carga para Lync Server 2013](lync-server-2013-load-balancing-requirements.md).

</div>

<div>

## <a name="reverse-proxy-requirements"></a>Requisitos del proxy inverso

Si admite el descubrimiento automático para clientes móviles de Lync, debe actualizar la regla de publicación actual de la siguiente manera:

  - Si decide actualizar las listas Subject Alternative names en los certificados de proxy inverso y usa HTTPS para la solicitud de servicio de detección automática, debe actualizar la regla de publicación web para lyncdiscover. \<sipdomain\>. Normalmente, se combina con la regla de publicación de la dirección URL de servicios web externos en el grupo de servidores front-end.

  - Si decide usar HTTP para la solicitud de servicio de detección automática inicial para que no tenga que actualizar la lista de nombres alternativos de asunto en los certificados de proxy inverso, debe crear una nueva regla de publicación web para el puerto HTTP/TCP 80, si aún no existe. Si ya existe una regla para HTTP/TCP 80, puede actualizarla para que incluya el lyncdiscover. \<entrada\> sipdomain.

</div>

</div>

<span> </span>

</div>

</div>

</div>

