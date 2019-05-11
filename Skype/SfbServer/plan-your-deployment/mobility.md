---
title: Planeación de movilidad de Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 2/17/2018
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7117eff5-6860-4673-b366-afe0756c4bb2
description: Planeación de la implementación de movilidad de Skype para Business Server.
ms.openlocfilehash: e981f7d9ac22739dc38bc48e574d96670536594b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33907209"
---
# <a name="plan-for-mobility-for-skype-for-business-server"></a>Planeación de movilidad de Skype para Business Server
 
Planeación de la implementación de movilidad de Skype para Business Server.
  
Con Skype para Business Server, puede implementar la característica de movilidad para proporcionar Skype para la funcionalidad del servidor de negocio en dispositivos móviles. En este artículo se proporciona información detallada acerca de la característica de movilidad y le ayudará a planear la implementación.
  
La característica de movilidad de Skype para Business Server es capaz de admitir clientes móviles de Skype para la empresa, así como los clientes de Lync regrese a 2010. Una vez que se haya implementado, los usuarios pueden conectarse a su Skype para iOS, admite el uso de la implementación de Business Server dispositivos móviles Android y Windows Phone para aprovechar las diferentes características, incluidas las características de Enterprise Voice. Hemos incluido una lista parcial siguiente, y también puede comprobar la [comparación de características de cliente de escritorio de Skype para la empresa](clients-and-devices/desktop-feature-comparison.md) para obtener más información:
  
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
    
Todo esto es posible gracias a la API web de comunicaciones unificadas (UCWA). UCWA se presentó en Lync Server 2013, y todavía está en uso para Skype para Business Server. No hay una funcionalidad adicional para la comunicación con los clientes de Lync 2010, y es el servicio de movilidad (MCX). Estos son los servicios de cortesía, lo que permite para Lync Server 2010 y clientes de 2013, así como Skype para clientes empresariales, para tener acceso a Skype para las implementaciones de Business Server correctamente.
  
> [!NOTE]
> Compatibilidad con MCX (servicio de movilidad) para los clientes móviles heredados ya no está disponible en Skype para Business Server 2019. Todos los Skype actual para los clientes móviles de negocio ya usa la API de Web de comunicaciones unificadas (UCWA) para admitir la mensajería instantánea (IM), presencia y contactos. Los usuarios con los clientes heredados con MCX necesitará actualizar a un cliente actual.
  
Es importante tener en cuenta que mientras todas estas características están disponibles una vez que se ha implementado la movilidad, es posible que funcionan un poco diferente en algunos dispositivos. Tenemos un sitio Web que se describe qué características funcionan en qué dispositivos, en [comparación de características de cliente móvil de Skype para la empresa](clients-and-devices/mobile-feature-comparison.md). También tenemos algunos excelente dispositivo y la información del sistema operativo en la [planificación para los clientes y dispositivos](clients-and-devices/clients-and-devices.md).
  
Movilidad hace uso de la detección automática característica, que permite a los clientes localizarse Skype para los servicios web de Business Server sin necesidad de escribir en todas las direcciones URL (que no necesita saber ellos) a los usuarios. Si necesita solucionar algún problema, también se sigue admitiendo la entrada manual de URL.
  
También se admiten las notificaciones de inserción, para cuando el Skype para la aplicación empresarial no se está ejecutando en segundo plano (o para dispositivos móviles que no son compatibles con aplicaciones que se ejecutan en segundo plano). Se envía una notificación de inserción a un dispositivo móvil cuando el dispositivo o la aplicación están inactivos. Un buen ejemplo es un mensaje de MI cuando el teléfono no está activo, que produciría el envío de una notificación de inserción (esto se presenta como una notificación, como cuando la aplicación se ejecuta en segundo plano). Con las notificaciones de inserción, los usuarios no se perderán MI ni llamadas de voz.
  
Para obtener más información, dispone de las secciones siguientes:
  
- [Componentes de movilidad](mobility.md#MobilityComponents)
    
- [Topologías compatibles](mobility.md#SupportedTopos)
    
- [Requisitos técnicos](mobility.md#TechRequirements)
    
- [Definir las necesidades de movilidad](mobility.md#MobilityNeeds)
    
## <a name="mobility-components"></a>Componentes de movilidad
<a name="MobilityComponents"> </a>

Hay cuatro servicios que conforman la movilidad de Skype para Business Server:
  
- **API web de comunicaciones unificadas (UCWA)**
    
    Proporciona servicios para las comunicaciones en tiempo real con mobile y los clientes web de Skype para Business Server. Cuando se implementa Skype para Business Server, crea un directorio virtual de UCWA en los servicios web internos y externos. Un componente virtual dentro de este directorio virtual acepta las llamadas de los clientes habilitados para UCWA. Las aplicaciones cliente se comunican mediante una interfaz de Transferencia de estado de representación (REST) para:
    
  - presencia
    
  - contactos
    
  - mensajería instantánea (MI)
    
  - VoIP
    
  - videoconferencias
    
  - colaboración
    
    UCWA usa un canal basado en P-GET para enviar eventos como una llamada entrante, un mensaje instantáneo entrante o un mensaje enviado a la aplicación cliente.
    
- **Servicio de movilidad (MCX)**
    
    Admite Skype para la funcionalidad del servidor empresarial, como mensajería instantánea, presencia y contactos, en dispositivos móviles. El servicio de movilidad se instala en cada servidor Front-End de cada grupo de servidores que se va a admitir Skype para la funcionalidad del servidor de negocio en dispositivos móviles. Al instalar Skype para Business Server 2015 se crea un nuevo directorio virtual (Mcx) en ambos sitios internos y externos en los servidores Front-End.
    
    > [!NOTE]
    > Compatibilidad con MCX (servicio de movilidad) para los clientes móviles heredados ya no está disponible en Skype para Business Server 2019. Todos los Skype actual para los clientes móviles de negocio ya usa la API de Web de comunicaciones unificadas (UCWA) para admitir la mensajería instantánea (IM), presencia y contactos. Los usuarios con los clientes heredados con MCX necesitará actualizar a un cliente actual.
  
- **Servicio Detección automática**
    
    Identifica la ubicación del usuario y permite a los dispositivos móviles y otro Skype para clientes empresariales localizar recursos (por ejemplo, las direcciones de URL internas y externas de Skype para servicios Web de servidor empresarial, la dirección URL Mcx o dirección URL de UCWA) independientemente de la ubicación de red. La detección automática usa nombres de host codificados de forma rígida (lyncdiscoverinternal para usuarios internos de la red y lyncdiscover para los externos) y el dominio SIP del usuario. Admite conexiones de cliente con HTTP o HTTPS. 
    
    El servicio Detección automática se instala en cada servidor Front-End y en cada Director en cada grupo de servidores que se va a admitir Skype para la funcionalidad del servidor de negocio en dispositivos móviles. Al instalar el servicio, se crea un nuevo directorio virtual (detección automática) en ambos sitios internos y externos en los servidores Front-End y directores.
    
- **Servicio de notificaciones de inserción**
    
    Un servicio basado en la nube que se encuentra en su Skype para el centro de datos profesionales en línea. En los teléfonos que no tengan Skype para clientes empresariales que se ejecuta en segundo plano, cuando ocurre un evento nuevo, notificación de un evento perdido (denominado una notificación de inserción) se envía al dispositivo móvil. El servicio de movilidad, envía una notificación al servicio de notificación de inserción (MPNS), que, a continuación, se envía al dispositivo móvil. Llegado este punto, el usuario puede responder a la notificación en su dispositivo móvil para activar la aplicación. Un servidor perimetral se requiere para esta funcionalidad.
    
## <a name="supported-topologies"></a>Topologías compatibles
<a name="SupportedTopos"> </a>

Tenemos el siguiente Skype admitido para aplicaciones de servidor de negocio para la planeación de la topología:
  
- Movilidad Standard Edition
    
- Movilidad Enterprise Edition
    
Debe poder usar esta funcionalidad con Skype para los servidores perimetrales de servidor empresarial o los servidores perimetrales de Lync Server 2013.
  
El servicio de movilidad es compatible con los servidores Front-End cuando se combina con el rol de servidor de mediación, con dos interfaces de red, pero debe seguir los pasos adecuados para configurar las interfaces. Debe asignar direcciones IP a la interfaz específica que se va a comunicar como el servidor de mediación y la interfaz de red IP que se va a comunicar como el servidor Front-End. Puede hacerlo en el generador de topología mediante la selección de la dirección IP correcta para cada servicio, en lugar de usar la selección de **usar todas las direcciones IP configuradas** de forma predeterminada.
  
## <a name="technical-requirements"></a>Requisitos técnicos
<a name="TechRequirements"> </a>

Es importante planificar para tener en cuenta varios escenarios de aplicaciones móviles a los que los usuarios móviles pueden enfrentarse. Por ejemplo, un usuario puede comenzar a usar una aplicación móvil fuera del trabajo conectándose a través de una red 3G y, posteriormente, cambiar a la red Wi-Fi corporativa al llegar al trabajo. Puede cambiar a 4G al salir de su creación. La planificación le ayudará a permitir estas transiciones entre redes y garantizar una experiencia de usuario uniforme.
  
### <a name="dns-configuration"></a>Configuración de DNS

Los servicios de movilidad Mcx y UCWA use DNS de la misma manera. Con la detección automática, los dispositivos móviles utilizan DNS para localizar recursos. Durante la búsqueda DNS, del intenta establecer una conexión para el FQDN que está asociado con el registro DNS interno (lyncdiscoverinternal. [ nombre de dominio interno]). Si el registro DNS interno no se puede usar para realizar esa conexión, una segundo intento de conexión, este tiempo para el registro DNS externo (lyncdiscover. [ sipdomain]). ¿Por qué tener dos? Un dispositivo móvil que es interno de la red podrán usar la dirección URL de detección automática interna. Los dispositivos móviles externos usará la dirección URL de detección automática externa. En cualquier caso, el servicio Detección automática devolverá todas las direcciones URL de servicios Web para el grupo de servidores principales del usuario, que incluye el servicio de movilidad (Mcx y UCWA).
  
Se espera que se realizarán las solicitudes de detección automática externas a través del proxy inverso que ha configurado para Skype para Business Server. Sin embargo, la dirección URL del servicio de movilidad interna y la dirección URL del servicio de movilidad externa están asociados con el FQDN de servicios Web externos. Por lo tanto, independientemente de si un dispositivo móvil es interno o externo a la red, el dispositivo siempre se conecta a la Skype para externamente, servicio de movilidad de servidor empresarial a través de proxy inverso.
  
> [!NOTE]
> Como mencionamos justo, todo el tráfico de servicio movilidad (interno y externo) se realizarán a través de proxy inverso. Sin embargo, a veces se produce un problema en que el tráfico interno sale de una interfaz e intenta volver a la misma interfaz. Esto puede infringir las reglas de seguridad de suplantación (formalmente, se conoce como suplantación de identidad de paquetes TCP). Debe permitir la **Fijación de la forma de** la función de movilidad.
  
> [!NOTE]
> Si está listo para ello, también puede elegir usar a un proxy inverso que es independiente de su firewall (de la seguridad con fines, prevención de suplantación de identidad siempre se deben aplicar en su servidor de seguridad). De este modo, la horquilla puede ocurrir en la interfaz externa del proxy inverso, en lugar de la interfaz externa del servidor de seguridad. Esto permite detectar la suplantación de identidad correctamente en el servidor de seguridad mientras se suaviza la regla en el proxy inverso y obtener la funcionalidad de movilidad. 
  
> [!NOTE]
> Si va a esta ruta, asegúrese de utilizar el host DNS o registros CNAME para definir al proxy inverso para el comportamiento de horquilla (no el firewall), si es posible. 
  
Hay algunas cosas que deberá configurar para admitir a usuarios de dentro y fuera de la red corporativa.
  
Estas son las reglas para FQDN de webs internas y externas:
  
- Nuevos registros DNS de CNAME o A (host, si es IPv6, AAAA) para la detección automática
    
- Nueva regla de firewall, si desea admitir notificaciones de inserción a través de la red Wi-Fi.
    
- Nombres alternativos asunto en certificados de servidor interno y los certificados de proxy inverso, para la detección automática.
    
- Afinidad de origen de los cambios de configuración de equilibrio de carga de hardware de Front-End Server.
    
Estos son los requisitos de topología necesarios para admitir el servicio de movilidad y Autodiscover Service:
  
- El FQDN del web interno de grupo de servidores de Front-End debe ser distinto de la web externa FQDN del grupo de servidores de Front-End.
    
- El FQDN de web interno debe resolverse solamente en la red corporativa y ser accesible desde ella.
    
- El FQDN de web externo debe resolverse solamente en Internet y ser accesible desde Internet.
    
- Para un usuario dentro de la red corporativa, se debe tratar la dirección URL de servicio de movilidad para el FQDN de web externo. Este requisito es para el servicio de movilidad y sólo se aplica a esta dirección URL.
    
- Para un usuario fuera de la red corporativa, la solicitud debe ir al sitio web externo FQDN del grupo de servidores Front-End o del Director.
    
Si admite la detección automática, debe crear los siguientes registros DNS para cada dominio SIP:
  
- Un registro DNS interno para admitir usuarios móviles que se conectan desde la red de su organización.
    
- Un registro DNS externo, o público, para admitir usuarios móviles que se conectan desde Internet.
    
La URL de detección automática interna no debería ser direccionable desde fuera de su red interna. La URL de detección automática externa no debería ser direccionable desde dentro de su red. Sin embargo, si esto no es posible para la URL externa, la funcionalidad del cliente móvil no debería verse afectada, porque la URL interna siempre se intenta primero.
  
### <a name="port-and-firewall-requirements"></a>Requisitos de puerto y de firewall

Hemos analizado la mayor parte de esto en otra documentación, pero específicamente para la movilidad, va a tener los siguientes puertos abiertos en la red de empresa Wi-Fi si tiene cualquier usuarios alojados en un dispositivo de sucursal con funciones de supervivencia (SBA):
  
- UcwaSipExternalListeningPort requiere el puerto 5088.
    
- UcwaSipPrimaryListeningPort requiere el puerto 5089.
    
### <a name="certificate-requirements"></a>Requisitos de certificados

Si utiliza la detección automática para su Skype para clientes móviles de negocio, debe modificar las listas de SAN (nombre alternativo del sujeto) en los certificados para admitir conexiones seguras de los clientes móviles. Si ya dispone de certificados, necesitará solicitar y asignar nuevos certificados con las entradas de SAN aquí descritas. Esto deberá realizarse para cada servidor Front-End y Director (si está en su entorno) que se ejecuta el servicio Detección automática. También recomendamos modificar que el SAN se enumera en los certificados de proxy inverso, agregar entradas de SAN para cada dominio SIP de la organización.
  
Esto debe ser un proceso sencillo si se solicita el nuevo certificados desactiva una CA interna (entidad emisora de certificados), pero los certificados públicos son más complejas y potencialmente mucho más caro volver a solicitar, no a mencionar puede ser costosa agregar una gran cantidad de SIP dominios a un nuevo certificado público. En esta situación, hay un enfoque que se admite, pero **no se recomienda**. Puede configurar el proxy inverso para hacer que la solicitud de servicio de detección automática inicial a través del puerto 80, que se va a utilizar HTTP, en lugar de puerto 443, que es HTTPS (y 443 es la configuración predeterminada). Dicha solicitud entrante se redirigirán al puerto 8080 de su grupo de servidores Front-End o del Director. De esta forma, no necesitará realizar cualquier cambio de certificado, debido a que el tráfico no está utilizando HTTPS para las solicitudes. Pero de nuevo, no se recomienda, aunque funcionará para usted.
  
### <a name="windows-and-iis-requirements"></a>Requisitos de Windows e IIS

Debe tener una versión compatible de Windows Server para su Skype para el entorno de servidor empresarial. Por este motivo, debería disponer también de IIS 8 o IIS 8.5 para sus necesidades de movilidad. Deberá ser algunos cambios en la configuración de ASP.NET predeterminado, pero el programa de instalación del servicio de movilidad hará automáticamente.
  
### <a name="hlb-requirements"></a>Requisitos de HLB

Si utiliza una topología de Skype para Business Server que incluye un HLB para el grupo de servidores Front-End (que sería cualquier topología que incluye más de un servidor Front-End), es necesario configurar el externo servicios Web IP virtuales (VIP) para el tráfico de servicios Web para el origen. La afinidad de origen sirve para garantizar que varias conexiones de un único cliente se envían a un servidor para mantener el estado de la sesión.
  
Si piensa admitir Skype para clientes móviles de negocio sólo a través de su red Wi-Fi interna, debe configurar a la VIP de servicios Web interno de origen tal como se describe para VIP de servicios Web externos. En esta situación, debe usar source_addr (o TCP) afinidad para la VIP de servicios Web internos en el HLB.
  
Para obtener información sobre esta cuestión, consulte el tema [Load balancing requirements for Skype for Business](network-requirements/load-balancing.md).
  
### <a name="reverse-proxy-requirements"></a>Requisitos de proxy inverso

Con el fin de admitir la detección automática de Skype para clientes móviles de negocio, necesita actualizar la regla de publicación actual de la siguiente manera:
  
- Si decide que se debe actualizar el SAN se enumera en los certificados de proxy inverso y uso de HTTPS para la solicitud de servicio de detección automática inicial, es necesario actualizar la regla de publicación web para lyncdiscover. \<sipdomain\>. Normalmente, esto se combina con la publicación rul para la URL de servicios Web externos en el grupo de servidores Front-End.
    
- Si ha decidido utilizar HTTP para que la solicitud de servicio de detección automática inicial evitar tener que actualizar la SAN de lista para los certificados de proxy inverso (que no se recomienda), que necesitará para crear una nueva regla de publicación de web para el puerto 80 HTTP/TCP, si no hay uno ya. Si existe dicha regla, actualícela para que incluya un lyncdiscover. \<sipdomain\> entrada.
    
## <a name="defining-your-mobility-needs"></a>Definir las necesidades de movilidad
<a name="MobilityNeeds"> </a>

Ahora que hemos revisado los requisitos técnicos, componentes y topologías, veamos lo que es posible que necesita su organización en términos de una implementación de movilidad.
  
### <a name="do-you-want-to-use-automatic-discovery-for-skype-for-business-mobile-clients"></a>¿Quiere usar la detección automática para los clientes móviles de Skype Empresarial?

Se recomienda encarecidamente que utilice la detección automática. Requerirá la creación de nuevos registros DNS internos y externos, tal y como se documenta en la sección anterior, Requisitos técnicos. Con la detección automática, el Skype para los clientes empresariales puede localizarse Skype para servicios Web de servidor empresarial desde cualquier ubicación, sin necesidad de una dirección URL que debe escribirse manualmente en.
  
Puede utilizar la configuración manual si lo requiere. Los usuarios deberán introducir estas URL en sus dispositivos móviles:
  
- **https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root** para el acceso externo.
    
- **https://\<IntPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root** para el acceso interno.
    
De nuevo, recomendamos utilizar la detección automática. Puede que encuentre útil la configuración manual para la resolución de problemas.
  
### <a name="are-you-going-to-support-push-notifications"></a>¿Va a admitir las notificaciones de inserción?

Las notificaciones de inserción se utilizan para las aplicaciones móviles compatibles con esta funcionalidad para notificar eventos a un usuario mientras la aplicación no está activa. El servidor perimetral necesitará tener una relación de federación con su Skype basados en la nube para Business Server inserción servicio de notificación, que se encuentra en la Skype para centro de datos profesionales en línea. Deberá ejecutar un cmdlet para habilitar las notificaciones de inserción.
  
> [!NOTE]
> Si tiene cualquier persona aún con clientes de Lync Server 2010, será necesario abrir el puerto 5223 de TCP salientes en su red de empresa WiFi. 
  
### <a name="do-you-want-all-your-users-accessing-all-mobility-features-or-do-you-want-to-specify-the-users-who-can-access-these-features-instead"></a>¿Desea que todos los usuarios obtener acceso a todas las características de movilidad o desea especificar los usuarios que pueden tener acceso a estas características en su lugar?

Tenemos una tabla para ayudar a con algunas de las características que están disponibles para todos los usuarios y, si está configurados que manera o no por valor predeterminado. Para obtener una lista completa, consulte [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).
  
> [!NOTE]
> Los ámbitos para todas estas características son Global/Sitio/Usuario. 
  
|**Característica**|**Nombre del parámetro**|**Descripción**|**Valor predeterminado**|
|:-----|:-----|:-----|:-----|
|Permitir movilidad  <br/> |EnableMobility  <br/> |Controla a los usuarios que disponen de Skype para clientes móviles de negocio instalado en un ámbito determinado. Si la directiva está definida en falso, los usuarios no podrán iniciar sesión con su cliente.  <br/> |True  <br/> |
|Voz externa  <br/> |EnableOutsideVoice  <br/> |Habilita la capacidad de un usuario para usar Vía trabajo, que permite a los usuarios enviar y recibir llamadas utilizando su número de teléfono del trabajo en lugar de su número de teléfono móvil. Si está definida en falso, los usuarios no podrán realizar o recibir llamadas en su teléfono móvil cuando utilicen su número de teléfono del trabajo.  <br/> |True  <br/> |
|Permitir Audio y vídeo IP  <br/> |EnableIPAudioVideo  <br/> |Si se define en el valor predeterminado, permite a un usuario utilizar VoIP para realizar o recibir llamadas de teléfono o videollamadas en su dispositivo móvil. Si se define en falso, los usuarios no podrán utilizar su dispositivo móvil para dichos fines.  <br/> |True  <br/> |
|Requerir Wi-Fi para audio IP  <br/> |RequireWiFiForIPAudio  <br/> |Define si un cliente necesitará realizar y recibir llamadas de VoIP con una red WiFi en lugar de con una red de datos de telefonía móvil. Si se define en verdadero, los usuarios solo podrán realizar y recibir llamadas de VoIP cuando estén conectados a una red WiFi.  <br/> |False  <br/> |
|Requerir Wi-Fi para vídeo IP  <br/> |RequireWiFiForIPVideo  <br/> |Define si un cliente necesitará realizar y recibir videollamadas con una red WiFi en lugar de con una red de datos de telefonía móvil. Si se define en verdadero, los usuarios solo podrán realizar y recibir llamadas de VoIP cuando estén conectados a una red WiFi.  <br/> |Falso  <br/> |
   
### <a name="should-users-who-arent-enabled-for-enterprise-voice-be-able-to-use-click-to-join-to-join-conferences"></a>¿Los usuarios no habilitados para Telefonía IP empresarial deberán poder hacer clic para unirse a conferencias?

Para que los usuarios que tengan acceso a las características de movilidad y vía trabajo, deben estar habilitados para Enterprise Voice. Pero incluso si no lo están, podrán unirse a conferencias en su dispositivo móvil haciendo clic en un vínculo, siempre y cuando tengan asignada la directiva de voz adecuada. En tal caso puede:
  
- asignar una directiva de voz específica a estos usuarios, o
    
- asegurarse de que haya una directiva global o de nivel de sitio que se aplique a ellos.
    
En ambos casos, la directiva de voz que asigne debe disponer de registros de uso de la RTC (red telefónica conmutada) y rutas que definan desde dónde podrán los usuarios realizar llamadas salientes para unirse a conferencias.
  
> [!NOTE]
> Los usuarios móviles que deseen hacer clic para unirse requieren una directiva de voz, junto con los registros relacionados de uso de RTC y rutas de voz, porque cuando hacen clic en ese vínculo en sus dispositivos móviles, una llamada saliente desde Skype para Business Server será el resultado. 
  

