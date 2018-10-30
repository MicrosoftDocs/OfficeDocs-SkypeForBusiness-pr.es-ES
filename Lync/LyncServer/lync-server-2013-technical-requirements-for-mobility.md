---
title: 'Lync Server 2013: Requisitos técnicos para la movilidad'
TOCTitle: Requisitos técnicos para la movilidad
ms:assetid: 831be681-4de0-4e42-b04f-8879ca4dcd23
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Hh690030(v=OCS.15)
ms:contentKeyID: 48275875
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Requisitos técnicos para la movilidad en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Los usuarios móviles experimentan varios escenarios de aplicaciones móviles que requieren una planeación especial. Por ejemplo, un usuario puede comenzar a usar una aplicación móvil fuera del trabajo conectándose a través de la red 3G; posteriormente, puede cambiar a la red Wi-Fi corporativa al llegar al trabajo y volver a cambiar a 3G al salir del edificio. Es necesario planear el entorno para admitir estas transiciones de red y garantizar una experiencia del usuario uniforme. En esta sección se describen los requisitos de infraestructura que se deben cumplir para admitir aplicaciones móviles y la detección automática de recursos de movilidad.


> [!NOTE]
> Aunque las aplicaciones móviles también se pueden conectar a otros servicios de Lync Server 2013, este requisito de enviar todas las solicitudes web de aplicaciones móviles al mismo nombre de dominio completo (FQDN) de web externo solo se aplica al servicio Movilidad de Lync Server 2013. El resto de servicios de movilidad no necesitan esta configuración.



El requisito para la afinidad de cookie en los equilibradores de carga de hardware se reduce considerablemente y usted sustituye la afinidad del protocolo de control de transmisión (TCP) si está usando Lync Mobile suministrado con Lync Server 2013. Aún puede utilizarse la afinidad de cookies, pero los servicios web ya no lo exigen.

> [!IMPORTANT]  
> Todo el tráfico del servicio Movilidad pasa por el proxy inverso, independientemente de cuál sea el punto de origen (interno o externo). En el caso de que haya un proxy inverso único, una granja de proxies inversos o un dispositivo que proporciona la función de proxy inverso, se puede producir un problema cuando el tráfico interno está saliendo de una interfaz e intentando ingresar inmediatamente a la misma interfaz. A menudo, esto conduce a una violación de las reglas de seguridad conocida como suplantación de identidad de paquetes TCP o simplemente suplantación de identidad. La <em>horquilla</em> (es decir, la salida e inmediata entrada de un paquete o series de paquetes) debe estar permitido para que pueda funcionar la movilidad. Una solución a este problema es usar un proxy inverso independiente del firewall (la regla para prevenir la suplantación de identidad debe aplicarse en el firewall por motivos de seguridad). La horquilla puede producirse en la interfaz externa del proxy inverso en lugar de en la interfaz interna del firewall. La suplantación de identidad se detectará en el firewall, mientras que puede “relajarse” en el proxy inverso, lo que permite la horquilla necesaria para la movilidad.<br />
> Use el host del Sistema de nombres de dominio (DNS) o los registros CNAME para definir el proxy inverso para el comportamiento de horquilla (no el firewall) en caso de ser posible.


Lync Server 2013 es compatible con servicios de movilidad par clientes móviles de Lync 2010 Mobile y Lync 2013. Ambos clientes usan el servicio Detección automática de Lync Server 2013 para encontrar su punto de entrada de movilidad, pero se diferencian en el servicio de movilidad que emplean. Lync 2010 Mobile usa el servicio de movilidad conocido como *Mcx* , introducido con la actualización acumulativa para Lync Server 2010 de noviembre de 2011. Los clientes móviles de Lync 2013 usan la API web de comunicaciones unificadas ( *UCWA* ) como su proveedor de servicios de movilidad.

## Configuración interna y externa de DNS

Los servicios de movilidad Mcx (introducidos con la actualización acumulativa de Lync Server 2010 de noviembre de 2011) y UCWA (introducido en las actualizaciones acumulativas de Lync Server 2013 de febrero de 2013) usan el DNS del mismo modo.

Al usar Detección automática, los dispositivos móviles usan el Sistema de nombres de dominio (DNS) para localizar recursos. Durante la búsqueda de DNS, primero se intenta una conexión al FQDN asociado al registro DNS interno (lyncdiscoverinternal. *\<internal domain name\>*). Si no se puede realizar una conexión usando el registro DNS interno, se intenta una conexión usando el registro DNS externo (lyncdiscover. *\<sipdomain\>*). Un dispositivo móvil que es interno respecto a la red se conecta a la URL interna del servicio Detección automática y un dispositivo móvil que es externo respecto a la red se conecta a la URL del servicio Detección automática externa. Las solicitudes externas de detección automática circulan a través del proxy inverso. El servicio Detección automática de Lync Server 2013 devuelve todas las URL de servicios web del grupo de servidores principales del usuario, incluidas las URL del servicio Movilidad (Mcx y UCWA). No obstante, la URL interna del servicio Movilidad y la URL externa del servicio Movilidad están asociadas al FQDN de servicios web externos. Por lo tanto, independientemente de si un dispositivo móvil es interno o externo a la red, el dispositivo siempre se conecta al servicio Movilidad de Lync Server 2013 de forma externa a través del proxy inverso.


> [!NOTE]
> Es importante que comprenda que su implementación puede constar de varios espacios de nombres definidos para uso interno y externo. Su nombre de dominio SIP puede ser distinto al nombre interno de dominio de implementación. Por ejemplo, el dominio SIP puede ser <STRONG>contoso.com</STRONG>, mientras que la implementación interna puede ser <STRONG>contoso.net</STRONG>. Los usuarios que inician sesión en Lync Server usarán el nombre de dominio SIP, como <STRONG>juan@contoso.com</STRONG>. Cuando se dirija a los servicios web externos (definidos en Generador de topologías como <STRONG>Servicios web externos</STRONG>), el nombre de dominio y el nombre de dominio SIP serán coherentes según lo que se define en el DNS. Cuando se dirija a los servicios web internos (definidos en Generador de topologías como <STRONG>Servicios web internos</STRONG>), el nombre predeterminado de los servicios web internos será el FQDN del Servidor front-end, Grupo de servidores front-end, Director o Grupo de directores. Si lo desea, puede sustituir el nombre de los servicios web internos. Debe usar el nombre de dominio interno (y no el nombre de dominio SIP) para los servicios web internos y definir el registro del host de DNS A (o, para IPv6, AAAA) para que refleje el nombre sustituido. Por ejemplo, el FQDN predeterminado de los servicios web internos puede ser <STRONG>pool01.contoso.net</STRONG>. Un FQDN sustituido de servicios web internos puede ser <STRONG>webpool.contoso.net</STRONG>. Si definimos los servicios web de esta manera podemos asegurar que se observa la ubicación interna o externa de los servicios, y no la del usuario que los está utilizando.<BR>No obstante, y debido a que los servicios web están definidos en Generador de topologías y el nombre de servicios web internos puede sustituirse, mientras el nombre de los servicios web resultantes, el certificado que lo valida y los registros DNS que lo definen sean coherentes, podrá definir los servicios web internos con cualquier nombre de dominio que elija, incluso el nombre de dominio SIP. En última instancia, la resolución del nombre para la dirección IP está determinada por los registros del host de DNS y un espacio de nombre coherente.<BR>En este tema y en los ejemplos, el nombre de dominio interno se usa para ilustrar la topología y las definiciones de DNS.



El siguiente diagrama ilustra el flujo de solicitudes web de aplicaciones móviles para el servicio Movilidad y el servicio Detección automática al usar una configuración DNS interna y externa.

**Flujo del servicio Movilidad con Detección automática**

![Flujo de solicitud de movilidad](images/Hh690030.cdb96424-96f2-4abf-88d7-1d32d1010ffd(OCS.15).jpg "Flujo de solicitud de movilidad")


> [!NOTE]
> En el diagrama se muestran servicios web genéricos. Un directorio virtual llamado Movilidad representa los servicios de movilidad Mcx y/o UCWA. Si no ha aplicado las actualizaciones acumulativas de Lync Server 2013 de febrero de 2013, es posible que no tenga el directorio virtual Ucwa definido en sus servicios web internos y externos. Tendrá un directorio virtual Detección automática y quizá un directorio virtual Mcx.<BR>La detección automática y la detección de servicios funcionan del mismo modo, independientemente de la tecnología de servicios de movilidad que se haya implementado.



Para admitir usuarios móviles de dentro y de fuera de la red corporativa, los FQDN de web interno y externo deben cumplir algunos requisitos previos. Además, es posible que deba cumplir otros requisitos en función de las características que decida implementar:

  - Nuevos registros CNAME o A (host, si es IPv6, AAAA) de DNS para la detección automática.

  - Nueva regla de firewall, si desea admitir notificaciones de inserción a través de la red Wi-Fi.

  - Nombres alternativos de sujeto en certificados de servidor interno y en certificados de proxy inverso para la detección automática.

  - Afinidad de origen para cambios en la configuración del equilibrador de carga de hardware de Servidor front-end.

Su topología debe cumplir los siguientes requisitos para admitir el servicio Movilidad y el servicio Detección automática:

  - El FQDN de web interno de Grupo de servidores front-end debe ser distinto al FQDN de web externo de Grupo de servidores front-end.

  - El FQDN de web interno debe resolverse solamente en la red corporativa y ser accesible desde ella.

  - El FQDN de web externo debe resolverse solamente en Internet y ser accesible desde Internet.

  - Para un usuario que está dentro de la red corporativa, la URL del servicio de movilidad debe dirigirse al FQDN de web externo. Este requisito es para el servicio de movilidad y se aplica solamente a esta URL.

  - Para un usuario que está fuera de la red corporativa, la solicitud debe ir al FQDN de web externo del Grupo de servidores front-end o del Director.

Si admite la detección automática, debe crear los siguientes registros DNS para cada dominio SIP:

  - Un registro DNS interno para admitir usuarios móviles que se conectan desde la red de su organización.

  - Un registro DNS externo, o público, para admitir usuarios móviles que se conectan desde Internet.

La URL de detección automática interna no debería ser direccionable desde fuera de su red. La URL de detección automática externa no debería ser direccionable desde dentro de su red. Sin embargo, aunque no pueda cumplir este requisito para la URL externa, es probable que la funcionalidad del cliente móvil no se vea afectada, ya que la URL interna siempre se intenta primero.

los registros DNS pueden ser registros CNAME o registros A (host, si es IPv6, AAAA).


> [!NOTE]
> Los clientes de dispositivos móviles no admiten varios certificados de capa de sockets seguros (SSL) de distintos dominios. Por lo tanto, la redirección de CNAME a distintos dominios no se admite a través de HTTPS. Por ejemplo, un registro CNAME de DNS para lyncdiscover.contoso.com que se redirige a una dirección de director.contoso.net no se admite a través de HTTPS. En una topología así, un cliente de dispositivo móvil necesita usar HTTP para la primera solicitud, de modo que la redirección de CNAME se resuelva a través de HTTP. A continuación, las solicitudes posteriores usan HTTPS. Para admitir este escenario, debe configurar el proxy inverso con una regla de publicación web para el puerto 80 (HTTP). Para más información, vea "Para crear una regla de publicación web para el puerto 80" en <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Configuración del proxy inverso para movilidad en Lync Server 2013</A>.<BR>La redirección de CNAME al mismo dominio se admite a través de HTTPS. En este caso, el certificado del dominio de destino cubre el dominio originario.



Para información sobre los registros DNS necesarios para su escenario, consulte [Resumen de DNS: detección automática en Lync Server 2013](lync-server-2013-dns-summary-autodiscover.md).

## Requisitos de puerto y de firewall

Si admite notificaciones de inserción y desea que dispositivos móviles de Apple las reciban a través de su red Wi-Fi, también deberá abrir el puerto 5223 en la red Wi-Fi de su empresa. El puerto 5223 es un puerto TCP saliente usado por el servicio de notificación de inserción de Apple (APNS). El dispositivo móvil inicia la conexión. Para más información, vea [http://support.apple.com/kb/TS1629](http://support.apple.com/kb/ts1629?viewlocale=es_es)

> [!WARNING]  
> Un dispositivo Apple que use el cliente Lync 2013 Mobile no requiere notificaciones de inserción.



Tenga en cuenta que si un usuario se aloja en una sucursal con funciones de supervivencia (SBA) se necesitan los siguientes puertos:

  - UcwaSipExternalListeningPort requiere el puerto 5088

  - UcwaSipPrimaryListeningPort requiere el puerto 5089

Para obtener más información e instrucciones sobre requisitos de puertos y protocolos para Detección automática, vea [Resumen del puerto: detección automática en Lync Server 2013](lync-server-2013-port-summary-autodiscover.md).

## Requisitos de certificado

Si admite la detección automática para clientes móviles de Lync, debe modificar las listas de nombres alternativos de sujeto en los certificados para admitir conexiones seguras desde los clientes móviles. Debe solicitar y asignar nuevos certificados, agregando las entradas de nombre alternativo de sujeto descritas en esta sección, para cada Servidor front-end y Director que ejecutan el servicio Detección automática. El enfoque recomendado es modificar también las listas de nombres alternativos de sujeto en certificados para sus proxies inversos. Debe agregar entradas de nombre alternativo de sujeto para cada dominio SIP de su organización.

La reemisión de certificados mediante una entidad de certificación interna suele ser un proceso sencillo, pero agregar varias entradas de nombre alternativo de sujeto a certificados públicos usados por el proxy inverso puede resultar caro. Si tiene muchos dominios SIP −lo que provoca que agregar nombres alternativos de sujeto sea muy caro−, puede configurar el proxy inverso para realizar la solicitud inicial del servicio Detección automática a través del puerto 80 con HTTP, en lugar del puerto 443 con HTTPS −la configuración predeterminada−. A continuación, la solicitud se redirige al puerto 8080 en el Director o Grupo de servidores front-end. Al publicar la solicitud inicial del servicio Detección automática en el puerto 80, no es necesario cambiar los certificados para el proxy inverso, porque la solicitud usa HTTP en lugar de HTTPS. Este método se admite, pero no lo recomendamos.

## Requisitos de Internet Information Services (IIS)

Le recomendamos que use IIS 7.5, IIS 8.0 o IIS 8.5 para la movilidad. El instalador del servicio Movilidad define marcas en ASP.NET para mejorar el rendimiento. IIS 7.5 se instala de manera predeterminada en Windows Server 2008 R2, IIS 8.0 se instala en Windows Server 2012 y IIS 8.5 se instala en Windows Server 2012 R2. El instalador del servicio Movilidad cambia automáticamente la configuración de ASP.NET.

## Requisitos del equilibrador de carga de hardware

En el equilibrador de carga de hardware que soporta al Grupo de servidores front-end, las IP virtuales (VIP) externas de servicios web del tráfico de servicios web deben estar configuradas para el origen. La afinidad de origen sirve para garantizar que varias conexiones de un único cliente se envían a un servidor para mantener el estado de la sesión. Para más información sobre requisitos de afinidad, vea [Requisitos del equilibrio de carga de Lync Server 2013](lync-server-2013-load-balancing-requirements.md).

Si planea admitir clientes móviles de Lync solo a través de su red Wi-Fi interna, debe configurar las VIP de servicios web internas para el origen tal como se describe para las VIP de servicios web externas. En esta situación, debe usar la afinidad (o TCP) source\_addr para VIP de servicios web internas en el equilibrador de carga de hardware. Para más información, vea [Requisitos del equilibrio de carga de Lync Server 2013](lync-server-2013-load-balancing-requirements.md).

## Requisitos de proxy inverso

Si admite la detección automática para clientes móviles de Lync, debe actualizar la regla de publicación actual de la siguiente manera:

  - Si decide actualizar las listas de nombres alternativos de sujeto en los certificados de proxy inverso y usa HTTPS para la solicitud inicial del servicio Detección automática, debe actualizar la regla de publicación web para lyncdiscover. *\<sipdomain\>*. Generalmente, esto se combina con la regla de publicación para la URL de servicios web externa en el Grupo de servidores front-end.

  - Si decide usar HTTP para la solicitud inicial del servicio Detección automática de modo que no necesite actualizar la lista de nombres alternativos de sujeto en los certificados del proxy inverso, debe crear una nueva regla de publicación web para el puerto HTTP/TCP 80. Si ya existe una regla para los HTTP/TCP 80, puede actualizarla para que incluya la entrada *\<sipdomain\>*.

