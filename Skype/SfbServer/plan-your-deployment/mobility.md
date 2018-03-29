---
title: Planificar la movilidad para Skype Empresarial Server 2015
ms.author: heidip
author: microsoftheidi
ms.date: 2/17/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7117eff5-6860-4673-b366-afe0756c4bb2
description: Plan para la implementación de la movilidad para Skype para Business Server 2015.
ms.openlocfilehash: f0d822050055ea7255786128fcaecd144f91367a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-mobility-for-skype-for-business-server-2015"></a>Planificar la movilidad para Skype Empresarial Server 2015
 
Plan para la implementación de la movilidad para Skype para Business Server 2015.
  
Con Skype para Business Server 2015, puede implementar la característica de movilidad para proporcionar funcionalidad de Business Server 2015 en dispositivos móviles Skype. Este artículo proporciona información detallada acerca de la característica de movilidad y le ayuda a planear la implementación.
  
La característica de movilidad para Skype para Business Server 2015 es capaz de admitir clientes móviles de Skype para el negocio, así como los clientes de Lync volviendo a 2010. Una vez implementado, los usuarios pueden conectarse a su Skype para Business Server 2015 implementación mediante compatibles iOS, Android y Windows Phone dispositivos móviles aprovechar las diferentes características, incluidas las características de Telefonía IP empresarial. Hemos incluido una lista parcial de abajo, y también puede comprobar la [comparación de características de cliente de escritorio de Skype para empresas](clients-and-devices/desktop-feature-comparison.md) para obtener más información:
  
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
    
Todo esto es posible gracias a la API web de comunicaciones unificadas (UCWA). UCWA se presentó en Lync Server 2013, y se encuentra todavía en uso para Skype para Business Server 2015 hoy. Hay una funcionalidad adicional para la comunicación con los clientes de Lync 2010 y es el servicio de movilidad (MCX). Estos son servicios complementarios, permitiendo para Lync Server 2010 y clientes de 2013, así como Skype para clientes de negocios, acceso a Skype para implementaciones de Business Server correctamente.
  
> [!NOTE]
> Se ha incluido MCX aquí, pero debe quedar claro que si bien la funcionalidad es compatible, en la siguiente versión esta quedará obsoleta, de modo que deberá tenerlo en cuenta en su planificación. Seguiremos utilice el UCWA y recomienda 2013 de Lync y Skype para clientes empresariales se utilizan en el futuro en un entorno eventual post-MCX. 
  
Es importante destacar que mientras que todas estas características están disponibles una vez que se ha implementado la movilidad, que trabajen un poco diferente en algunos dispositivos. Tenemos un sitio Web que describe qué características funcionan en los dispositivos, en la [comparación de características de cliente móvil de Skype para el negocio](clients-and-devices/mobile-feature-comparison.md). También tenemos algunos gran dispositivo y la información del SO en el [Plan para los clientes y dispositivos](clients-and-devices/clients-and-devices.md).
  
Movilidad hace uso de la detección automática de la característica que permite a los clientes localizar automáticamente Skype para los servicios web de Business Server sin necesidad de entrar en cualquier dirección URL (que no necesita conocerlos) a los usuarios. Si necesita solucionar algún problema, también se sigue admitiendo la entrada manual de URL.
  
También se admiten las notificaciones de inserción, para cuando el Skype para el negocio de la aplicación no se está ejecutando en segundo plano (o para los dispositivos móviles que no admiten aplicaciones que se ejecutan en segundo plano). Se envía una notificación de inserción a un dispositivo móvil cuando el dispositivo o la aplicación están inactivos. Un buen ejemplo es un mensaje de MI cuando el teléfono no está activo, que produciría el envío de una notificación de inserción (esto se presenta como una notificación, como cuando la aplicación se ejecuta en segundo plano). Con las notificaciones de inserción, los usuarios no se perderán MI ni llamadas de voz.
  
Para obtener más información, dispone de las secciones siguientes:
  
- [Componentes de movilidad](mobility.md#MobilityComponents)
    
- [Topologías compatibles](mobility.md#SupportedTopos)
    
- [Requisitos técnicos](mobility.md#TechRequirements)
    
- [Definir las necesidades de movilidad](mobility.md#MobilityNeeds)
    
## <a name="mobility-components"></a>Componentes de movilidad
<a name="MobilityComponents"> </a>

Hay cuatro servicios que incluyen movilidad de Skype para Business Server 2015:
  
- **API web de comunicaciones unificadas (UCWA)**
    
    Proporciona servicios para las comunicaciones en tiempo real con mobile y los clientes web Skype para Business Server 2015. Cuando se implementa Skype para Business Server, crea un directorio virtual de UCWA en los servicios web internos y externos. Un componente virtual dentro de este directorio virtual acepta las llamadas de los clientes habilitados para UCWA. Las aplicaciones cliente se comunican mediante una interfaz de Transferencia de estado de representación (REST) para:
    
  - presencia
    
  - contactos
    
  - mensajería instantánea (MI)
    
  - VoIP
    
  - videoconferencias
    
  - colaboración
    
    UCWA usa un canal basado en P-GET para enviar eventos como una llamada entrante, un mensaje instantáneo entrante o un mensaje enviado a la aplicación cliente.
    
- **Servicio de movilidad (MCX)**
    
    Es compatible con Skype para la funcionalidad de Business Server, como mensajería instantánea, presencia y contactos en dispositivos móviles. El servicio de movilidad está instalado en cada servidor Front-End en cada grupo que se va a admitir Skype para la funcionalidad de servidor empresariales en dispositivos móviles. Al instalar Skype para Business Server 2015 se crea un nuevo directorio virtual (Mcx) en ambos sitios internos y externos en los servidores frontales.
    
    > [!NOTE]
    > Tal y como se ha mencionado anteriormente, MCX quedará obsoleto en la siguiente versión del producto. 
  
- **Servicio Detección automática**
    
    Identifica la ubicación del usuario y permite a los dispositivos móviles y otro Skype para clientes de empresa localizar recursos (como las direcciones de URL internas y externas de Skype para Business Server 2015 Web Services, la dirección URL de Mcx o UCWA URL) independientemente de la ubicación de red. La detección automática usa nombres de host codificados de forma rígida (lyncdiscoverinternal para usuarios internos de la red y lyncdiscover para los externos) y el dominio SIP del usuario. Admite conexiones de cliente con HTTP o HTTPS. 
    
    El servicio Detección automática se instala en cada servidor Front-End y en cada Director en cada grupo que se va a admitir Skype para la funcionalidad de servidor empresariales en dispositivos móviles. Cuando instala el servicio, se crea un nuevo directorio virtual (detección automática) en ambos sitios internos y externos en los servidores frontales y directores.
    
- **Servicio de notificaciones de inserción**
    
    Un servicio basado en la nube que se encuentra en su Skype para centros de datos empresariales en línea. En los teléfonos que no tienen Skype para Business client ejecutándose en segundo plano cuando se produce un nuevo evento, notificación de un evento perdido (denominado una notificación de inserción) se envía al dispositivo móvil. El servicio de movilidad, envía una notificación al servicio de notificaciones de inserción (MPN), que lo envía al dispositivo móvil. Llegado este punto, el usuario puede responder a la notificación en su dispositivo móvil para activar la aplicación. Un servidor perimetral es necesario para esta funcionalidad.
    
## <a name="supported-topologies"></a>Topologías compatibles
<a name="SupportedTopos"> </a>

Tenemos la siguiente Skype compatible para aplicaciones de servidor de negocios para el diseño de la topología:
  
- Movilidad Standard Edition
    
- Movilidad Enterprise Edition
    
Puede utilizar esta función con Skype para servidores de borde de Business Server o servidores de borde de Lync Server 2013.
  
El servicio de movilidad es compatible con los servidores frontales cuando en combinación con la función de servidor de mediación, con dos interfaces de red, pero necesitará tomar las medidas adecuadas para configurar dichas interfaces. Debe asignar direcciones IP a la interfaz específica en la que se comunicará como el servidor de mediación y la interfaz de red IP que se comunicará como el servidor Front-End. Puede hacerlo en el generador de topología seleccionando la dirección IP correcta para cada servicio, en lugar de utilizar la selección predeterminada de **utilizar todas las direcciones IP** .
  
## <a name="technical-requirements"></a>Requisitos técnicos
<a name="TechRequirements"> </a>

Es importante planificar para tener en cuenta varios escenarios de aplicaciones móviles a los que los usuarios móviles pueden enfrentarse. Por ejemplo, un usuario puede comenzar a usar una aplicación móvil fuera del trabajo conectándose a través de una red 3G y, posteriormente, cambiar a la red Wi-Fi corporativa al llegar al trabajo. Puede cambiar a 4G al salir de su edificio. La planificación le ayudará a permitir estas transiciones entre redes y garantizar una experiencia de usuario uniforme.
  
### <a name="dns-configuration"></a>Configuración de DNS

Los servicios de movilidad, Mcx y UCWA utilizan DNS de la misma manera. Descubrimiento automático, los dispositivos móviles utilizan DNS para localizar los recursos. Durante la búsqueda DNS, del intenta establecer una conexión al que está asociado con el registro DNS interno FQDN (lyncdiscoverinternal. [ nombre de dominio interno]). Si el registro DNS interno no puede utilizarse para realizar dicha conexión, una segundo intento de conexión, esta vez para el registro DNS externo (lyncdiscover. [ sipdomain]). Así que ¿por qué tener dos? Un dispositivo móvil que es interno a la red será capaz de utilizar la dirección URL de detección automática interna. Dispositivos móviles externos utilizan la dirección URL de detección automática externa. En cualquier caso, el servicio de Autodiscover devolverá todas las direcciones URL de servicios Web para el grupo principal del usuario, que incluye el servicio de movilidad (Mcx y UCWA).
  
Se espera que las solicitudes de detección automática externas pasará por el proxy inverso que ha configurado para Skype para Business Server 2015. Sin embargo, la dirección URL del servicio de movilidad interna y la dirección URL del servicio de movilidad externo están asociados con el FQDN de los servicios Web externos. Por lo tanto, independientemente de si un dispositivo móvil es interno o externo a la red, el dispositivo siempre se conecta a la Skype para servicio de Business Server 2015 movilidad externamente, a través de proxy inverso.
  
> [!NOTE]
> Como mencionamos simplemente, todo el tráfico de servicio movilidad (interno y externo) pasará a través de proxy inverso. Sin embargo, a veces se produce un problema en que el tráfico interno sale de una interfaz e intenta volver a la misma interfaz. Esto puede infringir las reglas de seguridad de suplantación (formalmente, se conoce como suplantación de identidad de paquetes TCP). Debe permitir la **Fijación de cabello** tengan función de movilidad.
  
> [!NOTE]
> Si está listo para ello, también puede utilizar un proxy inverso que es independiente de su firewall (por seguridad siempre se deben aplicar efectos, prevención de suplantación del servidor de seguridad). De este modo, la horquilla puede ocurrir en la interfaz externa del proxy inverso, en lugar de la interfaz externa del servidor de seguridad. Esto le permite detectar la suplantación correctamente en el servidor de seguridad mientras se suaviza la regla en el proxy inverso y se obtiene la funcionalidad de movilidad. 
  
> [!NOTE]
> Si continuar por este camino, asegúrese de utilizar el host DNS o registros CNAME para definir al proxy inverso para el comportamiento de la horquilla (no el servidor de seguridad), si es posible. 
  
Hay algunas cosas que deberá configurar para admitir a usuarios de dentro y fuera de la red corporativa.
  
Estas son las reglas para FQDN de webs internas y externas:
  
- Nuevos registros DNS de CNAME o A (host, si es IPv6, AAAA) para la detección automática
    
- Nueva regla de firewall, si desea admitir notificaciones de inserción a través de la red Wi-Fi.
    
- Nombres alternativos sujetos en los certificados de servidor interno y certificados de proxy inverso, la detección automática.
    
- Afinidad de origen cambios de configuración de equilibrio de carga de hardware de servidor frontal.
    
Estos son los requisitos de topología necesarios para admitir el servicio de movilidad y Autodiscover Service:
  
- El web interno FQDN pool de Front-End debe ser distinto desde el web externo FQDN del grupo de Front-End.
    
- El FQDN de web interno debe resolverse solamente en la red corporativa y ser accesible desde ella.
    
- El FQDN de web externo debe resolverse solamente en Internet y ser accesible desde Internet.
    
- Para un usuario en la red corporativa, la dirección URL de servicio de movilidad debe abordarse para el FQDN de web externo. Este requisito es para el servicio de movilidad y sólo se aplica a esta dirección URL.
    
- Para un usuario fuera de la red corporativa, la solicitud debe ir a la web externo FQDN del grupo de servidores Front-End o Director.
    
Si admite la detección automática, debe crear los siguientes registros DNS para cada dominio SIP:
  
- Un registro DNS interno para admitir usuarios móviles que se conectan desde la red de su organización.
    
- Un registro DNS externo, o público, para admitir usuarios móviles que se conectan desde Internet.
    
La URL de detección automática interna no debería ser direccionable desde fuera de su red interna. La URL de detección automática externa no debería ser direccionable desde dentro de su red. Sin embargo, si esto no es posible para la URL externa, la funcionalidad del cliente móvil no debería verse afectada, porque la URL interna siempre se intenta primero.
  
### <a name="port-and-firewall-requirements"></a>Requisitos de puerto y de firewall

Hemos cubierto casi todo esto en otra documentación, pero específicamente para la movilidad, va a tener los siguientes puertos abiertos en la red Wi-Fi de empresa si tiene los usuarios alojados en un dispositivo de sucursal funciones de supervivencia (SBA):
  
- UcwaSipExternalListeningPort requiere el puerto 5088.
    
- UcwaSipPrimaryListeningPort requiere el puerto 5089.
    
### <a name="certificate-requirements"></a>Requisitos de certificados

Si está utilizando la detección automática para tu Skype para los clientes móviles de negocio, debe modificar las listas de SAN (nombre alternativo del sujeto) en los certificados para admitir conexiones seguras de los clientes móviles. Si ya dispone de certificados, necesitará solicitar y asignar nuevos certificados con las entradas de SAN aquí descritas. Esto deberá realizarse para cada servidor Front-End y Director (si en su entorno) que ejecuta el servicio de detección automática. También recomendamos modificar que listas de SAN de los certificados de proxy inverso, agregar entradas de SAN para cada dominio SIP de su organización.
  
Esto debe ser un proceso sencillo si se solicita el nuevo certificados fuera de una entidad emisora interna (entidad emisora de certificados), pero los certificados públicos son más complejas y potencialmente mucho más costoso volver a solicitar, sin dejar de mencionar que puede resultar costoso agregar mucha SIP dominios de un nuevo certificado público. En esa situación, existe un enfoque que es compatible, pero **no se recomienda**. Puede configurar el proxy inverso para realizar la solicitud de servicio de detección automática inicial el puerto 80, que se utiliza HTTP, en lugar de utilizar el puerto 443, que es HTTPS (y 443 es la configuración predeterminada). Dicha solicitud entrante se redirigirá al puerto 8080 en el grupo de servidores Front-End o Director. Al hacerlo, no necesita realizar ningún cambio de certificado, debido a que este tráfico no está utilizando HTTPS para las solicitudes. Pero de nuevo, no es recomendable, aunque funcionará para usted.
  
### <a name="windows-and-iis-requirements"></a>Requisitos de Windows e IIS

Como se indica en nuestros principales [requisitos del servidor para Skype para Business Server 2015](requirements-for-your-environment/server-requirements.md) artículo, debe tener Windows Server 2012 o R2 de Windows Server 2012 para su Skype para entorno Business Server. Por este motivo, debería disponer también de IIS 8 o IIS 8.5 para sus necesidades de movilidad. Tendrá algunos cambios a la configuración de ASP.NET predeterminada, pero el instalador del servicio de movilidad hará automáticamente.
  
### <a name="hlb-requirements"></a>Requisitos de HLB

Si utiliza una topología de Skype para el año 2015 de servidor empresarial que incluya un HLB para el grupo de servidores Front-End (que sería cualquier topología que incluye más de un servidor de Front-End), necesita ser la externa servicios Web IPs virtual (VIP) para el tráfico de servicios Web configurado para el origen. La afinidad de origen sirve para garantizar que varias conexiones de un único cliente se envían a un servidor para mantener el estado de la sesión.
  
Si piensa admitir Skype para los clientes móviles de negocios sólo a través de la red Wi-Fi interna, debe configurar a su VIP de servicios Web internos de origen tal como se describe para VIP de servicios Web externos. En esta situación, debe utilizar source_addr (o TCP) afinidad para los VIP de servicios Web interno en HLB.
  
Para obtener más información sobre estos temas, consulte la documentación de [requisitos de Skype para el negocio de equilibrio de carga](network-requirements/load-balancing.md) .
  
### <a name="reverse-proxy-requirements"></a>Requisitos de proxy inverso

Para admitir la detección automática de Skype para los clientes móviles de negocios, necesitará actualizar la regla de publicación actual como sigue:
  
- Si decide actualizar listas de la SAN de los certificados de proxy inverso y utiliza HTTPS para la solicitud inicial del servicio de detección automática, deberá actualizar la regla de publicación de web para lyncdiscover. \<sipdomain\>. Normalmente esto se combina con la publicación rul para la URL de servicios Web externos en el grupo de servidores Front-End.
    
- Si ha decidido utilizar HTTP para que la solicitud inicial del servicio Detección automática evitar tener que actualizar la SAN lista para los certificados de proxy inverso (que no es recomendable), necesitará crear una nueva regla de publicación de web para el puerto 80 de HTTP/TCP, si no hay uno ya. Si existe esa regla, actualizarlo para incluir un lyncdiscover. \<sipdomain\> entrada.
    
## <a name="defining-your-mobility-needs"></a>Definir las necesidades de movilidad
<a name="MobilityNeeds"> </a>

Ahora que hemos revisado los requisitos técnicos, componentes y topologías, echemos un vistazo a lo que necesite su organización en términos de una implementación de movilidad.
  
### <a name="do-you-want-to-use-automatic-discovery-for-skype-for-business-mobile-clients"></a>¿Quiere usar la detección automática para los clientes móviles de Skype Empresarial?

Se recomienda encarecidamente que utilice la detección automática. Requerirá la creación de nuevos registros DNS internos y externos, tal y como se documenta en la sección anterior, Requisitos técnicos. Descubrimiento automático, el Skype para clientes de empresa puede localiza automáticamente Skype para Business Server 2015 Web Services desde cualquier ubicación, sin necesidad de una dirección URL debe escribirse manualmente en.
  
Puede utilizar la configuración manual si lo requiere. Los usuarios deberán introducir estas URL en sus dispositivos móviles:
  
- **https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root** para el acceso externo.
    
- **https://\<IntPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root** para el acceso interno.
    
De nuevo, recomendamos utilizar la detección automática. Puede que encuentre útil la configuración manual para la resolución de problemas.
  
### <a name="are-you-going-to-support-push-notifications"></a>¿Va a admitir las notificaciones de inserción?

Las notificaciones de inserción se utilizan para las aplicaciones móviles compatibles con esta funcionalidad para notificar eventos a un usuario mientras la aplicación no está activa. El servidor perimetral deberá tener una relación de federación con su Skype en la nube para Business Server Push servicio de notificación, que se encuentra en el Skype para centros de datos empresariales en línea. Deberá ejecutar un cmdlet para habilitar las notificaciones de inserción.
  
> [!NOTE]
> Si tiene cualquiera sigue utilizando a clientes de Lync Server 2010, deben abrir de puerto 5223 TCP saliente en la red de WiFi de la empresa. 
  
### <a name="do-you-want-all-your-users-accessing-all-mobility-features-or-do-you-want-to-specify-the-users-who-can-access-these-features-instead"></a>¿Desea que todos los usuarios tener acceso a todas las características de movilidad, o que desee especificar los usuarios que pueden tener acceso a estas características en su lugar?

Tenemos una tabla para ayudar con algunas de las características que están disponibles para todos los usuarios y, si está establecidos que por cierto o no predeterminada. Para obtener una lista completa, consulte [CsMobilityPolicy de nuevo](https://docs.microsoft.com/en-us/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).
  
> [!NOTE]
> Los ámbitos para todas estas características son Global/Sitio/Usuario. 
  
|**Característica**|**Nombre del parámetro**|**Descripción**|**Configuración predeterminada**|
|:-----|:-----|:-----|:-----|
|Permitir movilidad  <br/> |EnableMobility  <br/> |Usuarios de controles en un ámbito determinado que tienen Skype para Business mobile client instalado. Si la directiva está definida en falso, los usuarios no podrán iniciar sesión con su cliente.  <br/> |True  <br/> |
|Voz externa  <br/> |EnableOutsideVoice  <br/> |Habilita la capacidad de un usuario para usar Vía trabajo, que permite a los usuarios enviar y recibir llamadas utilizando su número de teléfono del trabajo en lugar de su número de teléfono móvil. Si está definida en falso, los usuarios no podrán realizar o recibir llamadas en su teléfono móvil cuando utilicen su número de teléfono del trabajo.  <br/> |True  <br/> |
|Permitir Audio y vídeo IP  <br/> |EnableIPAudioVideo  <br/> |Si se define en el valor predeterminado, permite a un usuario utilizar VoIP para realizar o recibir llamadas de teléfono o videollamadas en su dispositivo móvil. Si se define en falso, los usuarios no podrán utilizar su dispositivo móvil para dichos fines.  <br/> |True  <br/> |
|Requerir Wi-Fi para audio IP  <br/> |RequireWiFiForIPAudio  <br/> |Define si un cliente necesitará realizar y recibir llamadas de VoIP con una red WiFi en lugar de con una red de datos de telefonía móvil. Si se define en verdadero, los usuarios solo podrán realizar y recibir llamadas de VoIP cuando estén conectados a una red WiFi.  <br/> |Falso  <br/> |
|Requerir Wi-Fi para vídeo IP  <br/> |RequireWiFiForIPVideo  <br/> |Define si un cliente necesitará realizar y recibir videollamadas con una red WiFi en lugar de con una red de datos de telefonía móvil. Si se define en verdadero, los usuarios solo podrán realizar y recibir llamadas de VoIP cuando estén conectados a una red WiFi.  <br/> |Falso  <br/> |
   
### <a name="should-users-who-arent-enabled-for-enterprise-voice-be-able-to-use-click-to-join-to-join-conferences"></a>¿Los usuarios no habilitados para Telefonía IP empresarial deberán poder hacer clic para unirse a conferencias?

Para que los usuarios tengan acceso a características de movilidad y llamada a través del trabajo, deben habilitarse para Telefonía IP empresarial. Pero incluso si no lo están, podrán unirse a conferencias en su dispositivo móvil haciendo clic en un vínculo, siempre y cuando tengan asignada la directiva de voz adecuada. En tal caso puede:
  
- asignar una directiva de voz específica a estos usuarios, o
    
- asegurarse de que haya una directiva global o de nivel de sitio que se aplique a ellos.
    
En ambos casos, la directiva de voz que asigne debe disponer de registros de uso de la RTC (red telefónica conmutada) y rutas que definan desde dónde podrán los usuarios realizar llamadas salientes para unirse a conferencias.
  
> [!NOTE]
> Los usuarios móviles que desean utilizar clic a Join requieren una directiva de voz, junto con los registros relacionados de uso PSTN y las rutas de la voz, porque cuando hacen clic en ese vínculo en sus dispositivos móviles, una llamada saliente de Skype para Business Server 2015 será el resultado. 
  

