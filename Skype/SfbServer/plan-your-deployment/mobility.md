---
title: Planear la movilidad de Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 2/17/2018
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7117eff5-6860-4673-b366-afe0756c4bb2
description: Planee la implementación de movilidad de Skype empresarial Server.
ms.openlocfilehash: 8b0ba8dd4ae07d3330a8ca722a1101c6b41a7cec
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297326"
---
# <a name="plan-for-mobility-for-skype-for-business-server"></a>Planear la movilidad de Skype empresarial Server
 
Planee la implementación de movilidad de Skype empresarial Server.
  
Con Skype empresarial Server, puede implementar la característica de movilidad para proporcionar la funcionalidad de Skype empresarial Server en dispositivos móviles. Este artículo proporciona detalles sobre la característica de movilidad y le ayuda a planificar su implementación.
  
La característica de movilidad de Skype empresarial Server puede admitir clientes móviles para Skype empresarial, así como clientes de Lync que regresan a 2010. Una vez que se haya implementado, los usuarios podrán conectarse a la implementación de Skype empresarial Server mediante dispositivos móviles compatibles con iOS, Android y Windows Phone para aprovechar varias características diferentes, entre las que se incluyen las características de telefonía IP empresarial. Hemos incluido una lista parcial a continuación, y también puedes comprobar la [comparación de características de cliente de escritorio de Skype empresarial](clients-and-devices/desktop-feature-comparison.md) para obtener más información:
  
- Enviar y recibir mensajes
    
- Ver presencia
    
- Ver contactos
    
- Hacer clic para unirse a una conferencia
    
- Llamar a través de la cuenta del trabajo
    
- Conexión con un solo número
    
- Correo de voz
    
- Notificación de llamada perdida
    
- Voz sobre IP (VoIP)
    
- Vídeo para asistentes (H.264)
    
- Visualización de contenido de reuniones (PowerPoint y uso compartido de aplicaciones/escritorios)
    
Todo esto es posible gracias a la API web de comunicaciones unificadas (UCWA). UCWA se presentó por primera vez en Lync Server 2013, y aún está en uso en Skype empresarial Server. Hay una funcionalidad adicional para comunicarse con los clientes de Lync 2010 y el servicio de movilidad (MCX). Estos son servicios complementarios, lo que permite que los clientes de Lync Server 2010 y 2013, así como los clientes de Skype empresarial, tengan acceso a las implementaciones de Skype empresarial Server correctamente.
  
> [!NOTE]
> La compatibilidad con MCX (Mobility Service) para clientes móviles heredados ya no está disponible en Skype empresarial Server 2019. Todos los clientes móviles actuales de Skype empresarial ya usan la API Web de comunicaciones unificadas (UCWA) para admitir la mensajería instantánea, la presencia y los contactos. Los usuarios con clientes heredados que usen MCX deberán actualizar a un cliente actual.
  
Es importante tener en cuenta que, aunque todas estas características están disponibles una vez que se ha implementado la movilidad, es posible que funcionen de manera algo diferente en algunos dispositivos. Tenemos un sitio web en el que se explica qué características funcionan en qué dispositivos, en la [comparación de características de los clientes móviles de Skype empresarial](clients-and-devices/mobile-feature-comparison.md). También tenemos una excelente información sobre dispositivos y sistemas operativos en el [plan de clientes y dispositivos](clients-and-devices/clients-and-devices.md).
  
La movilidad usa la característica de detección automática, que permite a los clientes ubicar automáticamente los servicios Web de Skype empresarial Server sin que los usuarios tengan que introducirlos en ninguna dirección URL (ni siquiera necesitan conocerlos). Si necesita solucionar algún problema, también se sigue admitiendo la entrada manual de URL.
  
También se admiten las notificaciones push para cuando la aplicación de Skype empresarial no se ejecuta en segundo plano (o para dispositivos móviles que no admiten aplicaciones que se ejecutan en segundo plano). Se envía una notificación de inserción a un dispositivo móvil cuando el dispositivo o la aplicación están inactivos. Un buen ejemplo es un mensaje de MI cuando el teléfono no está activo, que produciría el envío de una notificación de inserción (esto se presenta como una notificación, como cuando la aplicación se ejecuta en segundo plano). Con las notificaciones de inserción, los usuarios no se perderán MI ni llamadas de voz.
  
Para obtener más información, dispone de las secciones siguientes:
  
- [Componentes de movilidad](mobility.md#MobilityComponents)
    
- [Topologías compatibles](mobility.md#SupportedTopos)
    
- [Requisitos técnicos](mobility.md#TechRequirements)
    
- [Definir las necesidades de movilidad](mobility.md#MobilityNeeds)
    
## <a name="mobility-components"></a>Componentes de movilidad
<a name="MobilityComponents"> </a>

Existen cuatro servicios que incluyen movilidad para Skype empresarial Server:
  
- **API web de comunicaciones unificadas (UCWA)**
    
    Proporciona servicios para las comunicaciones en tiempo real con clientes móviles y web para Skype empresarial Server. Cuando se implementa Skype empresarial Server, se crea un directorio virtual de UCWA en los servicios Web internos y externos. Un componente virtual dentro de este directorio virtual acepta las llamadas de los clientes habilitados para UCWA. Las aplicaciones cliente se comunican mediante una interfaz de Transferencia de estado de representación (REST) para:
    
  - presencia
    
  - contactos
    
  - mensajería instantánea (MI)
    
  - VoIP
    
  - videoconferencias
    
  - colaboración
    
    UCWA usa un canal basado en P-GET para enviar eventos como una llamada entrante, un mensaje instantáneo entrante o un mensaje enviado a la aplicación cliente.
    
- **Servicio de movilidad (MCX)**
    
    Es compatible con la funcionalidad de Skype empresarial Server, como la mensajería instantánea, la presencia y los contactos, en dispositivos móviles. El servicio de movilidad se instala en todos los servidores front-end de cada grupo de servidores que estén diseñados para admitir la funcionalidad de Skype empresarial Server en dispositivos móviles. Al instalar Skype empresarial Server 2015, se crea un nuevo directorio virtual (MCX) en los sitios Web internos y externos de los servidores front-end.
    
    > [!NOTE]
    > La compatibilidad con MCX (Mobility Service) para clientes móviles heredados ya no está disponible en Skype empresarial Server 2019. Todos los clientes móviles actuales de Skype empresarial ya usan la API Web de comunicaciones unificadas (UCWA) para admitir la mensajería instantánea, la presencia y los contactos. Los usuarios con clientes heredados que usen MCX deberán actualizar a un cliente actual.
  
- **Servicio Detección automática**
    
    Identifica la ubicación del usuario y permite que los dispositivos móviles y otros clientes de Skype empresarial encuentren recursos (como las direcciones URL internas y externas de los servicios Web de Skype empresarial Server, la URL de MCX o UCWA URL) independientemente de la ubicación de red. La detección automática usa nombres de host codificados de forma rígida (lyncdiscoverinternal para usuarios internos de la red y lyncdiscover para los externos) y el dominio SIP del usuario. Admite conexiones de cliente con HTTP o HTTPS. 
    
    El servicio Detección automática se instala en todos los servidores front-end y en cada director de cada grupo de servidores que estén diseñados para admitir la funcionalidad de Skype empresarial Server en dispositivos móviles. Al instalar el servicio, se crea un nuevo directorio virtual (detección automática) en los sitios Web internos y externos de los directores y servidores front-end.
    
- **Servicio de notificaciones de inserción**
    
    Un servicio basado en la nube que se encuentra en el centro de datos de Skype empresarial online. En los teléfonos que no tienen un cliente de Skype empresarial ejecutándose en segundo plano, cuando se produce un nuevo evento, la notificación de un evento perdido (denominada notificación de inserción) se envía al dispositivo móvil. El servicio de movilidad envía una notificación al servicio de notificaciones push (MPNS), que a su vez la envía al dispositivo móvil. Llegado este punto, el usuario puede responder a la notificación en su dispositivo móvil para activar la aplicación. Para esta funcionalidad se necesita un servidor perimetral.
    
## <a name="supported-topologies"></a>Topologías compatibles
<a name="SupportedTopos"> </a>

Tenemos las siguientes aplicaciones compatibles de Skype empresarial Server para la planificación de su topología:
  
- Mobility Standard Edition
    
- Mobility Enterprise Edition
    
Debería poder usar esta funcionalidad con servidores perimetrales de Skype empresarial Server o servidores perimetrales de Lync Server 2013.
  
El servicio de movilidad es compatible con los servidores front-end cuando se colocan con el rol de servidor de mediación, con dos interfaces de red, pero tiene que seguir los pasos adecuados para configurar esas interfaces. Tendrá que asignar direcciones IP a la interfaz específica que se comunicará como el servidor de mediación y la interfaz IP de red que se comunicará como el servidor front-end. Puede hacerlo en el generador de topología seleccionando la dirección IP correcta para cada servicio, en lugar de usar la selección predeterminada **usar todas las direcciones IP** configuradas.
  
## <a name="technical-requirements"></a>Requisitos técnicos
<a name="TechRequirements"> </a>

Es importante planificar para tener en cuenta varios escenarios de aplicaciones móviles a los que los usuarios móviles pueden enfrentarse. Por ejemplo, un usuario puede comenzar a usar una aplicación móvil fuera del trabajo conectándose a través de una red 3G y, posteriormente, cambiar a la red Wi-Fi corporativa al llegar al trabajo. Pueden cambiar a 4G cuando salen de su edificio. La planificación le ayudará a permitir estas transiciones entre redes y garantizar una experiencia de usuario uniforme.
  
### <a name="dns-configuration"></a>Configuración de DNS

Los servicios de movilidad MCX y UCWA usan DNS de la misma manera. Con el descubrimiento automático, los dispositivos móviles usan DNS para ubicar recursos. Durante la búsqueda de DNS, se ha intentado una conexión al FQDN que está asociado con el registro DNS interno (lyncdiscoverinternal. [ nombre de dominio interno]). Si el registro DNS interno no se puede usar para realizar esa conexión, se intentará una segunda conexión, esta vez al registro DNS externo (lyncdiscover. [ sipdomain]). ¿Por qué hay dos? Un dispositivo móvil que sea interno de su red podrá usar la dirección URL interna de detección automática. Los dispositivos móviles externos usarán la dirección URL externa de detección automática. En cualquiera de los casos, el servicio Detección automática devolverá todas las direcciones URL de servicios web para el grupo de usuarios domésticos, que incluye el servicio de movilidad (MCX y UCWA).
  
Se espera que las solicitudes de detección automática externas atraviesen el proxy inverso que ha configurado para Skype empresarial Server. Sin embargo, la dirección URL del servicio de movilidad interna y la dirección URL del servicio de movilidad externa están asociados con el FQDN de los servicios web externos. Por lo tanto, independientemente de si un dispositivo móvil es interno o externo a su red, el dispositivo siempre se conecta externamente con el servicio de movilidad de Skype empresarial Server a través del proxy inverso.
  
> [!NOTE]
> Como acabamos de observar, todo el tráfico del servicio de movilidad (interno y externo) pasará por el proxy inverso. Sin embargo, a veces se produce un problema en que el tráfico interno sale de una interfaz e intenta volver a la misma interfaz. Esto puede infringir las reglas de seguridad de suplantación (formalmente, se conoce como suplantación de identidad de paquetes TCP). Tendrás que permitir el **anclaje del cabello** para que funcione la movilidad.
  
> [!NOTE]
> Si está listo para hacerlo, también puede optar por usar un proxy inverso que sea independiente del firewall (por motivos de seguridad, la prevención de suplantación de identidad siempre debe ser exigido en su firewall). De esta manera, el Hairpin puede ocurrir en la interfaz externa del proxy inverso, en lugar de en la interfaz externa del firewall. Esto le permite detectar correctamente la suplantación de identidad en el Firewall mientras relaja la regla en el proxy inverso y obtiene la funcionalidad de movilidad. 
  
> [!NOTE]
> Si ve esta ruta, asegúrese de usar el host DNS o los registros CNAME para definir el proxy inverso para el comportamiento Hairpin (no el firewall), si es posible. 
  
Hay algunas cosas que deberá configurar para admitir a usuarios de dentro y fuera de la red corporativa.
  
Estas son las reglas para FQDN de webs internas y externas:
  
- Nuevos registros DNS de CNAME o A (host, si es IPv6, AAAA) para la detección automática
    
- Nueva regla de firewall, si desea admitir notificaciones de inserción a través de la red Wi-Fi.
    
- Para el descubrimiento automático, los nombres alternativos del firmante en certificados de servidor interno y en los certificados de proxy inverso.
    
- La configuración de carga equilibrada de hardware de servidor front-end
    
Estos son los requisitos de topología necesarios para admitir el servicio de movilidad y el servicio Detección automática:
  
- El FQDN de la web interna del grupo de servidores front-end debe ser distinto del FQDN de la web externa del grupo de servidores front-end.
    
- El FQDN de web interno debe resolverse solamente en la red corporativa y ser accesible desde ella.
    
- El FQDN de web externo debe resolverse solamente en Internet y ser accesible desde Internet.
    
- Para un usuario dentro de la red corporativa, la dirección URL del servicio de movilidad debe dirigirse al FQDN de la web externa. Este requisito es para el servicio de movilidad y solo se aplica a esta dirección URL.
    
- Para un usuario fuera de la red corporativa, la solicitud debe ir al FQDN de la web externa del grupo o del Director de front-end.
    
Si admite la detección automática, debe crear los siguientes registros DNS para cada dominio SIP:
  
- Un registro DNS interno para admitir usuarios móviles que se conectan desde la red de su organización.
    
- Un registro DNS externo, o público, para admitir usuarios móviles que se conectan desde Internet.
    
La URL de detección automática interna no debería ser direccionable desde fuera de su red interna. La URL de detección automática externa no debería ser direccionable desde dentro de su red. Sin embargo, si esto no es posible para la URL externa, la funcionalidad del cliente móvil no debería verse afectada, porque la URL interna siempre se intenta primero.
  
### <a name="port-and-firewall-requirements"></a>Requisitos de puerto y de firewall

Hemos cubierto la mayoría de esto en nuestra otra documentación, pero específicamente para la movilidad, desearás tener los siguientes puertos abiertos en tu red Wi-Fi de empresa si tienes algún usuario alojado en un dispositivo de sucursal con la supervivencia (SBA):
  
- UcwaSipExternalListeningPort requiere el puerto 5088.
    
- UcwaSipPrimaryListeningPort requiere el puerto 5089.
    
### <a name="certificate-requirements"></a>Requisitos de certificados

Si está usando la detección automática para sus clientes móviles de Skype empresarial, tendrá que modificar las listas SAN (nombre alternativo del sujeto) en sus certificados para admitir conexiones seguras desde sus clientes móviles. Si ya dispone de certificados, necesitará solicitar y asignar nuevos certificados con las entradas de SAN aquí descritas. Debe hacerse para cada servidor front-end y director (si se encuentra en su entorno) que ejecute el servicio Detección automática. También recomendamos modificar las listas SAN en los certificados de proxy inverso, agregando entradas SAN para cada dominio SIP de su organización.
  
Esto debe ser un proceso simple si va a solicitar los nuevos certificados de una entidad emisora de certificados interna (entidad emisora de certificados), pero los certificados públicos son más complejos y posiblemente mucho más caro para volver a solicitarlos, por lo que puede ser costoso agregar una gran cantidad de SIP Dominios a un nuevo certificado público. En ese caso, existe un enfoque que es compatible, pero que **no se recomienda**. Puede configurar su proxy inverso para que la solicitud de servicio de detección automática inicial pase por el puerto 80, que usará HTTP, en lugar del puerto 443, que es HTTPS (y que 443 es la configuración predeterminada). La solicitud entrante se redirigirá al puerto 8080 en el grupo de servidores front-end o en el director. Al hacerlo, no tendrá que realizar ningún cambio en los certificados porque este tráfico no usa HTTPS para las solicitudes. Sin embargo, de nuevo, no recomendamos esto, aunque sí lo hará.
  
### <a name="windows-and-iis-requirements"></a>Requisitos de Windows e IIS

Debe tener una versión de Windows Server admitida para su entorno de Skype empresarial Server. Por este motivo, debería disponer también de IIS 8 o IIS 8.5 para sus necesidades de movilidad. Tendrá que realizar algunos cambios en la configuración de ASP.NET predeterminada, pero el instalador del servicio de movilidad lo hará automáticamente.
  
### <a name="hlb-requirements"></a>Requisitos de HLB

Si está usando una topología de Skype empresarial Server que incluye un HLB para su grupo front-end (que sería cualquier topología que incluya más de un servidor front-end), se debe configurar el tráfico IPs virtual de servicios web (VIP) para servicios Web para el origen. La afinidad de origen sirve para garantizar que varias conexiones de un único cliente se envían a un servidor para mantener el estado de la sesión.
  
Si tiene previsto admitir clientes móviles de Skype empresarial solo en su red Wi-Fi interna, debe configurar los VIP de servicios Web internos para el origen como se describe para los VIP de servicios web externos. En esta situación, debe usar la afinidad de source_addr (o TCP) para los VIP de servicios Web internos de la HLB.
  
Para obtener información sobre esta cuestión, consulte el tema [Load balancing requirements for Skype for Business](network-requirements/load-balancing.md).
  
### <a name="reverse-proxy-requirements"></a>Requisitos de proxy inverso

Para admitir el descubrimiento automático para clientes móviles de Skype empresarial, tendrá que actualizar la regla de publicación actual de la siguiente manera:
  
- Si decide actualizar las listas SAN en los certificados de proxy inverso y usa HTTPS para la solicitud de servicio de detección automática inicial, tendrá que actualizar la regla de publicación web para lyncdiscover. \<sipdomain\>. Esto se suele combinar con el RUL de publicación de la dirección URL de los servicios web externos en el grupo de servidores front-end.
    
- Si ha decidido usar HTTP para la solicitud de servicio de detección automática inicial para evitar tener que actualizar la lista de SAN para los certificados de proxy inverso (que no recomendamos), tendrá que crear una nueva regla de publicación web para el puerto HTTP/TCP 80, si no hay ninguna Has. Si la regla existe, actualícelo para incluir un lyncdiscover. \<entrada\> sipdomain.
    
## <a name="defining-your-mobility-needs"></a>Definir las necesidades de movilidad
<a name="MobilityNeeds"> </a>

Ahora que hemos revisado las topologías, los componentes y los requisitos técnicos, echemos un vistazo a lo que su organización puede necesitar en cuanto a una implementación de movilidad.
  
### <a name="do-you-want-to-use-automatic-discovery-for-skype-for-business-mobile-clients"></a>¿Quiere usar la detección automática para los clientes móviles de Skype Empresarial?

Se recomienda encarecidamente que utilice la detección automática. Requerirá la creación de nuevos registros DNS internos y externos, tal y como se documenta en la sección anterior, Requisitos técnicos. Con el descubrimiento automático, los clientes de Skype empresarial pueden ubicar automáticamente los servicios Web de Skype empresarial Server desde cualquier ubicación, sin necesidad de escribir una dirección URL de forma manual.
  
Puede utilizar la configuración manual si lo requiere. Los usuarios deberán introducir estas URL en sus dispositivos móviles:
  
- **https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.SVC/root** para acceso externo.
    
- **https://\<IntPoolFQDN\>/Autodiscover/autodiscoverservice.SVC/root** para acceso interno.
    
De nuevo, recomendamos utilizar la detección automática. Puede que encuentre útil la configuración manual para la resolución de problemas.
  
### <a name="are-you-going-to-support-push-notifications"></a>¿Va a admitir las notificaciones de inserción?

Las notificaciones de inserción se utilizan para las aplicaciones móviles compatibles con esta funcionalidad para notificar eventos a un usuario mientras la aplicación no está activa. El servidor perimetral tendrá que tener una relación de Federación con el servicio de notificaciones de inserción de Skype empresarial Server basado en la nube, que se encuentra en el centro de negocios de Skype empresarial online. Deberá ejecutar un cmdlet para habilitar las notificaciones de inserción.
  
> [!NOTE]
> Si alguien sigue usando los clientes de Lync Server 2010, necesitarán el puerto TCP 5223 abierto de salida en la red WiFi de la empresa. 
  
### <a name="do-you-want-all-your-users-accessing-all-mobility-features-or-do-you-want-to-specify-the-users-who-can-access-these-features-instead"></a>¿Desea que todos los usuarios tengan acceso a todas las características de movilidad o desea especificar los usuarios que tienen acceso a estas características?

Tenemos una tabla para ayudar con algunas de las características que están disponibles para todos los usuarios, y si están establecidas de esa forma o no de forma predeterminada. Para obtener una lista completa, consulte [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).
  
> [!NOTE]
> Los ámbitos para todas estas características son Global/Sitio/Usuario. 
  
|**Característica**|**Nombre del parámetro**|**Descripción**|**Valor predeterminado**|
|:-----|:-----|:-----|:-----|
|Permitir movilidad  <br/> |EnableMobility  <br/> |Controla los usuarios de un ámbito dado que tienen instalado el cliente móvil de Skype empresarial. Si la directiva está definida en falso, los usuarios no podrán iniciar sesión con su cliente.  <br/> |True  <br/> |
|Voz externa  <br/> |EnableOutsideVoice  <br/> |Habilita la capacidad de un usuario para usar Vía trabajo, que permite a los usuarios enviar y recibir llamadas utilizando su número de teléfono del trabajo en lugar de su número de teléfono móvil. Si está definida en falso, los usuarios no podrán realizar o recibir llamadas en su teléfono móvil cuando utilicen su número de teléfono del trabajo.  <br/> |True  <br/> |
|Permitir Audio y vídeo IP  <br/> |EnableIPAudioVideo  <br/> |Si se define en el valor predeterminado, permite a un usuario utilizar VoIP para realizar o recibir llamadas de teléfono o videollamadas en su dispositivo móvil. Si se define en falso, los usuarios no podrán utilizar su dispositivo móvil para dichos fines.  <br/> |True  <br/> |
|Requerir Wi-Fi para audio IP  <br/> |RequireWiFiForIPAudio  <br/> |Define si un cliente necesitará realizar y recibir llamadas de VoIP con una red WiFi en lugar de con una red de datos de telefonía móvil. Si se define en verdadero, los usuarios solo podrán realizar y recibir llamadas de VoIP cuando estén conectados a una red WiFi.  <br/> |False  <br/> |
|Requerir Wi-Fi para vídeo IP  <br/> |RequireWiFiForIPVideo  <br/> |Define si un cliente necesitará realizar y recibir videollamadas con una red WiFi en lugar de con una red de datos de telefonía móvil. Si se define en verdadero, los usuarios solo podrán realizar y recibir llamadas de VoIP cuando estén conectados a una red WiFi.  <br/> |Falso  <br/> |
   
### <a name="should-users-who-arent-enabled-for-enterprise-voice-be-able-to-use-click-to-join-to-join-conferences"></a>¿Los usuarios no habilitados para Telefonía IP empresarial deberán poder hacer clic para unirse a conferencias?

Para que los usuarios tengan acceso a las características de movilidad y llamar a través del trabajo, deben estar habilitadas para telefonía IP empresarial. Pero incluso si no lo están, podrán unirse a conferencias en su dispositivo móvil haciendo clic en un vínculo, siempre y cuando tengan asignada la directiva de voz adecuada. En tal caso puede:
  
- asignar una directiva de voz específica a estos usuarios, o
    
- asegurarse de que haya una directiva global o de nivel de sitio que se aplique a ellos.
    
En ambos casos, la directiva de voz que asigne debe disponer de registros de uso de la RTC (red telefónica conmutada) y rutas que definan desde dónde podrán los usuarios realizar llamadas salientes para unirse a conferencias.
  
> [!NOTE]
> Los usuarios móviles que deseen usar hacer clic para participar requieren una directiva de voz, junto con los registros de uso de RTC y las rutas de voz relacionados, porque cuando hacen clic en ese vínculo en sus dispositivos móviles, se producirá una llamada saliente de Skype empresarial Server. 
  

