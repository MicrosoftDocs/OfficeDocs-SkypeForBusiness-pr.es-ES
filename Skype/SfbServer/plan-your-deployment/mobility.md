---
title: Plan for Mobility for Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 2/17/2018
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7117eff5-6860-4673-b366-afe0756c4bb2
description: Planee su implementación de movilidad para Skype Empresarial Server.
ms.openlocfilehash: 6452154db1047cfe91a7c8ceaf6ee6c63b94ee6b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49810080"
---
# <a name="plan-for-mobility-for-skype-for-business-server"></a>Plan for Mobility for Skype for Business Server
 
Planee su implementación de movilidad para Skype Empresarial Server.
  
Con Skype Empresarial Server, puede implementar la característica de movilidad para proporcionar la funcionalidad de Skype Empresarial Server en dispositivos móviles. En este artículo se proporcionan detalles sobre la característica de movilidad y se le ayuda a planear la implementación.
  
La característica de movilidad de Skype Empresarial Server es capaz de admitir clientes móviles para Skype Empresarial, así como clientes de Lync que se van a volver a 2010. Una vez implementado, los usuarios pueden conectarse a su implementación de Skype Empresarial Server con dispositivos móviles compatibles con iOS, Android y Windows Phone para aprovechar varias características diferentes, incluidas las Telefonía IP empresarial compatibles. Hemos incluido una lista parcial a continuación y también puede consultar la comparación de características de cliente de escritorio [para Skype Empresarial](clients-and-devices/desktop-feature-comparison.md) para obtener más información:
  
- Enviar y recibir mensajes
    
- Ver presencia
    
- Ver contactos
    
- Haga clic para unirse a una conferencia
    
- Vía trabajo
    
- Alcance de número único
    
- Correo de voz
    
- Notificación de llamada perdida
    
- Voz sobre IP (VoIP)
    
- Vídeo del asistente (H.264)
    
- Visualización del contenido de las reuniones (PowerPoint y uso compartido de aplicaciones o escritorio)
    
Todo esto se logra a través de la API web de comunicaciones unificadas o UCWA. UCWA se introdujo por primera vez en Lync Server 2013 y aún está en uso para Skype Empresarial Server. Hay una funcionalidad adicional para comunicarse con los clientes de Lync 2010 y es mobility Service (MCX). Estos son servicios complementarios, lo que permite que los clientes de Lync Server 2010 y 2013, así como los clientes de Skype Empresarial, accedan correctamente a las implementaciones de Skype Empresarial Server.
  
> [!NOTE]
> La compatibilidad con MCX (Mobility Service) para clientes móviles heredados ya no está disponible en Skype Empresarial Server 2019. Todos los clientes móviles actuales de Skype Empresarial ya usan la API web de comunicaciones unificadas (UCWA) para admitir la mensajería instantánea (MI), la presencia y los contactos. Los usuarios con clientes heredados que usen MCX tendrán que actualizar a un cliente actual.
  
Es importante tener en cuenta que, aunque todas estas características están disponibles una vez implementada la movilidad, pueden funcionar de forma un poco diferente en algunos dispositivos. Tenemos un sitio web que describe las características que funcionan en qué dispositivos, en la comparación de características de cliente móvil [para Skype Empresarial.](clients-and-devices/mobile-feature-comparison.md) También tenemos información excelente sobre dispositivos y sos en [Plan para clientes y dispositivos.](clients-and-devices/clients-and-devices.md)
  
La movilidad hace uso de la característica Detección automática, que permite a los clientes localizar automáticamente los servicios web de Skype Empresarial Server sin que los usuarios necesiten escribir en ninguna dirección URL (ni siquiera necesitarán conocerlas). Si necesita solucionar algún problema, aún se admite la entrada manual de direcciones URL.
  
También se admiten notificaciones de inserción, cuando la aplicación de Skype Empresarial no se ejecuta en segundo plano (o para dispositivos móviles que no admiten aplicaciones que se ejecutan en segundo plano). Se envía una notificación de inserción a un dispositivo móvil sobre un evento que se produce cuando el dispositivo o la aplicación está inactivo. Un buen ejemplo es que falta un mensaje de mensajería instantánea cuando el teléfono no está activo, lo que daría como resultado el envío de una notificación de inserción (esto se presenta como una notificación del sistema o una notificación, como cuando la aplicación se ejecuta en segundo plano). Con las notificaciones de inserción, los usuarios no se perderán las llamadas de mensajería instantánea o de voz.
  
Para obtener más información, tenemos las siguientes secciones:
  
- [Componentes de movilidad](mobility.md#MobilityComponents)
    
- [Topologías admitidas](mobility.md#SupportedTopos)
    
- [Requisitos técnicos](mobility.md#TechRequirements)
    
- [Definir las necesidades de movilidad](mobility.md#MobilityNeeds)
    
## <a name="mobility-components"></a>Componentes de movilidad
<a name="MobilityComponents"> </a>

Hay cuatro servicios que conforman la movilidad de Skype Empresarial Server:
  
- **Unified Communications Web API (UCWA)**
    
    Proporciona servicios para comunicaciones en tiempo real con clientes móviles y web para Skype Empresarial Server. Cuando se implementa Skype Empresarial Server, se crea un directorio virtual de UCWA en los servicios web internos y externos. Componente virtual de este directorio virtual que acepta llamadas de clientes habilitados para UCWA. Las aplicaciones cliente se comunican a través de una interfaz de transferencia de estado representacional (REST) para:
    
  - presencia
    
  - contacts
    
  - mensajería instantánea (MI)
    
  - VoIP
    
  - videoconferencia
    
  - colaboración
    
    UCWA usa un canal basado en P-GET para enviar eventos, como una llamada entrante, mensajería instantánea entrante o un mensaje a la aplicación cliente.
    
- **Servicio de movilidad (MCX)**
    
    Admite la funcionalidad de Skype Empresarial Server, como mensajería instantánea, presencia y contactos, en dispositivos móviles. El servicio de movilidad se instala en todos los servidores front-end de cada grupo que está pensado para admitir la funcionalidad de Skype Empresarial Server en dispositivos móviles. Al instalar Skype Empresarial Server 2015, se crea un nuevo directorio virtual (Mcx) en los sitios web internos y externos en los servidores front-end.
    
    > [!NOTE]
    > La compatibilidad con MCX (Mobility Service) para clientes móviles heredados ya no está disponible en Skype Empresarial Server 2019. Todos los clientes móviles actuales de Skype Empresarial ya usan la API web de comunicaciones unificadas (UCWA) para admitir la mensajería instantánea (MI), la presencia y los contactos. Los usuarios con clientes heredados que usen MCX tendrán que actualizar a un cliente actual.
  
- **Servicio Detección automática**
    
    Identifica la ubicación del usuario y permite que los dispositivos móviles y otros clientes de Skype Empresarial busquen recursos (como las direcciones URL internas y externas para los servicios web de Skype Empresarial Server, la dirección URL de Mcx o la dirección URL de UCWA) independientemente de la ubicación de red. La detección automática usa nombres de host codificados de forma rígida (lyncdiscoverinternal para usuarios dentro de la red, lyncdiscover para usuarios fuera de la red) y el dominio SIP del usuario. Admite conexiones de cliente que usan HTTP o HTTPS. 
    
    El servicio de detección automática se instala en todos los servidores front-end y en todos los directores de cada grupo de servidores que están diseñados para admitir la funcionalidad de Skype Empresarial Server en dispositivos móviles. Al instalar el servicio, se crea un nuevo directorio virtual (Detección automática) en los sitios web internos y externos en los servidores y directores front-end.
    
- **Servicio de notificación de inserción**
    
    Un servicio basado en la nube que se encuentra en su centro de datos de Skype Empresarial Online. En los teléfonos que no tienen un cliente de Skype Empresarial ejecutándose en segundo plano, cuando se produce un nuevo evento, en su lugar se envía una notificación de un evento perdido (denominado notificación de inserción) al dispositivo móvil. El servicio de movilidad envía una notificación al servicio de notificación de inserción (MPNS), que luego la envía al dispositivo móvil. A continuación, el usuario puede responder a la notificación en su dispositivo móvil para activar la aplicación. Se requiere un servidor perimetral para esta funcionalidad.
    
## <a name="supported-topologies"></a>Topologías admitidas
<a name="SupportedTopos"> </a>

Tenemos las siguientes aplicaciones compatibles de Skype Empresarial Server para la planeación de la topología:
  
- Mobility Standard Edition
    
- Mobility Enterprise Edition
    
Debería poder usar esta funcionalidad con los servidores perimetrales de Skype Empresarial Server o los servidores perimetrales de Lync Server 2013.
  
El servicio de movilidad se admite en los servidores front-end cuando se coloca con el rol de servidor de mediación, con dos interfaces de red, pero debe realizar los pasos adecuados para configurar dichas interfaces. Deberá asignar direcciones IP a la interfaz específica que se comunicará como servidor de mediación y la interfaz IP de red que se comunicará como servidor front-end. Puede hacerlo en el Generador de topologías seleccionando la dirección IP correcta para cada servicio, en lugar de usar la selección predeterminada Usar todas las **direcciones IP configuradas.**
  
## <a name="technical-requirements"></a>Requisitos técnicos
<a name="TechRequirements"> </a>

Es importante planear los distintos escenarios de aplicaciones móviles que pueden encontrar los usuarios móviles. Por ejemplo, alguien puede empezar a usar una aplicación móvil fuera del trabajo conectándose a través de una red 3G y, a continuación, cambiar a la red Wi-Fi corporativa cuando llegue al trabajo. Pueden cambiar a 4G al salir de su edificio. La planeación ahora le permitirá admitir estas transiciones de red y garantizar una experiencia de usuario coherente.
  
### <a name="dns-configuration"></a>Configuración de DNS

Los servicios de movilidad Mcx y UCWA usan DNS de la misma manera. Con la detección automática, los dispositivos móviles usan DNS para buscar recursos. Durante la búsqueda de DNS, se intenta una conexión al FQDN asociado con el registro DNS interno (lyncdiscoverinternal.[ nombre de dominio interno]). Si no se puede usar el registro DNS interno para realizar esa conexión, se intenta una segunda conexión, esta vez al registro DNS externo (lyncdiscover.[ sipdomain]). ¿Por qué tener dos? Un dispositivo móvil interno de la red podrá usar la dirección URL interna de Detección automática. Los dispositivos móviles externos usarán la dirección URL de Detección automática externa. En cualquier caso, el servicio Detección automática devolverá todas las direcciones URL del servicio web del grupo de servidores principal del usuario, que incluye el servicio de movilidad (Mcx y UCWA).
  
Se espera que las solicitudes de detección automática externas pasen por el proxy inverso que haya configurado para Skype Empresarial Server. Sin embargo, tanto la dirección URL interna del servicio de movilidad como la dirección URL del servicio de movilidad externa están asociadas con el FQDN de servicios web externos. Por lo tanto, independientemente de si un dispositivo móvil es interno o externo a la red, el dispositivo siempre se conecta al servicio de movilidad de Skype Empresarial Server externamente, a través del proxy inverso.
  
> [!NOTE]
> Como hemos indicado, todo el tráfico del servicio de movilidad (interno y externo) pasará por el proxy inverso. Pero a veces se produce un problema cuando el tráfico interno sale de una interfaz, solo para intentar volver a entrar en la misma interfaz. Esto puede infringir las reglas de seguridad de suplantación (formalmente se denomina suplantación de paquetes TCP). Deberás permitir que el **anclado de vello** tenga una función de movilidad.
  
> [!NOTE]
> Si está listo para hacerlo, también puede usar un proxy inverso que sea independiente del firewall (por motivos de seguridad, la prevención de suplantación de seguridad siempre debe aplicarse en el firewall). De este modo, la chinena puede producirse en la interfaz externa del proxy inverso, en lugar de en la interfaz externa del firewall. Esto le permite detectar la suplantación correctamente en el firewall mientras se reactiva la regla en el proxy inverso y se obtiene la funcionalidad de movilidad. 
  
> [!NOTE]
> Si va a esta ruta, asegúrese de usar el host DNS o los registros CNAME para definir el proxy inverso para el comportamiento de la red de red (no el firewall), si es posible. 
  
Hay algunas cosas que deberá configurar para admitir usuarios dentro y fuera de la red corporativa.
  
Estas son las reglas para FQDN web internos y externos:
  
- Nuevos registros DNS CNAME o A (host, si IPv6, AAAA), para la detección automática.
    
- Nueva regla de firewall, si quieres admitir notificaciones de inserción a través de la Wi-Fi cliente.
    
- Nombres alternativos de sujeto en certificados de servidor internos y certificados de proxy inverso, para la detección automática.
    
- La configuración equilibrada de carga de hardware del servidor front-end cambia la afinidad de origen.
    
Estos son los requisitos de topología necesarios para admitir el servicio de movilidad y el servicio de detección automática:
  
- El FQDN web interno del grupo de servidores front-end debe ser distinto del FQDN web externo del grupo de servidores front-end.
    
- El FQDN web interno solo debe resolverse y ser accesible desde dentro de la red corporativa.
    
- El FQDN web externo solo debe resolverse en Internet y ser accesible desde Internet.
    
- Para un usuario dentro de la red corporativa, la dirección URL del servicio de movilidad debe dirigirse al FQDN web externo. Este requisito es para el servicio de movilidad y solo se aplica a esta dirección URL.
    
- Para un usuario fuera de la red corporativa, la solicitud debe ir al FQDN web externo del grupo de servidores front-end o del director.
    
Si admite la detección automática, deberá realizar los siguientes registros DNS para cada dominio SIP:
  
- Un registro DNS interno para admitir usuarios móviles que se conectan desde dentro de la red de su organización.
    
- Un registro DNS externo o público para admitir usuarios móviles que se conectan desde Internet.
    
La dirección URL de detección automática interna no debe ser direccionable desde fuera de la red interna. La dirección URL de detección automática externa no debe ser direccionable desde dentro de la red. Pero si esto no es posible para la dirección URL externa, es probable que la funcionalidad del cliente móvil no se verá afectada, ya que la dirección URL interna siempre se probará primero.
  
### <a name="port-and-firewall-requirements"></a>Requisitos de puerto y firewall

Hemos cubierto la mayor parte de esto en nuestra otra documentación, pero específicamente para movilidad, querrá tener los siguientes puertos abiertos en la red de Wi-Fi de empresa si tiene usuarios que se alomen en una aplicación de sucursal con funciones de supervivencia (SBA):
  
- UcwaSipExternalListeningPort requiere 5088.
    
- UcwaSipPrimaryListeningPort requiere 5089.
    
### <a name="certificate-requirements"></a>Requisitos de certificado

If you're using automatic discovery for your Skype for Business mobile clients, you'll need to modify the SAN (subject alternative name) lists on your certificates to support secure connections from your mobile clients. Si ya tiene certificados locales, deberá solicitar y asignar nuevos certificados con las entradas de SAN que se describen aquí. Esto tendrá que hacerse para cada servidor front-end y director (si se encuentra en su entorno) que ejecute el servicio Detección automática. También recomendamos modificar las listas de SAN en los certificados de proxy inverso y agregar entradas de SAN para cada dominio SIP de la organización.
  
Este debe ser un proceso sencillo si solicita los nuevos certificados de una entidad de certificación interna (entidad de certificación), pero los certificados públicos son más complejos y, potencialmente, mucho más costosos de volver a solicitar, por no mencionar que puede resultar costoso agregar una gran cantidad de dominios SIP a un nuevo certificado público. En esa situación, hay un enfoque que es compatible, pero **no recomendado.** Puede configurar el proxy inverso para realizar la solicitud de servicio de detección automática inicial a través del puerto 80, que usará HTTP, en lugar del puerto 443, que es HTTPS (y 443 es la configuración predeterminada). Esa solicitud entrante se redirigirá al puerto 8080 del grupo de servidores front-end o del director. Al hacerlo, no tendrá que realizar ningún cambio de certificado, ya que este tráfico no usa HTTPS para las solicitudes. Pero, de nuevo, no lo recomendamos, aunque funcionará para usted.
  
### <a name="windows-and-iis-requirements"></a>Requisitos de Windows e IIS

Debe tener una versión compatible de Windows Server para su entorno de Skype Empresarial Server. Como resultado, también debe tener IIS 8 o IIS 8.5 para sus necesidades de movilidad. Deberá haber algunos cambios en la configuración predeterminada de ASP.NET, pero el instalador del servicio de movilidad lo hará automáticamente.
  
### <a name="hlb-requirements"></a>Requisitos de HLB

Si usa una topología para Skype Empresarial Server que incluya un HLB para su grupo de servidores front-end (que sería cualquier topología que incluya más de un servidor front-end), las IP virtuales (VIP) externas de servicios web para el tráfico de servicios web deben configurarse para el origen. La afinidad de origen ayuda a garantizar que se envíen varias conexiones de un solo cliente al mismo servidor para mantener el estado de sesión.
  
Si planea admitir clientes móviles de Skype Empresarial solo a través de su red Wi-Fi interna, debe configurar las VIP de servicios web internos para el origen, tal como se describe para VIP de servicios web externos. En esta situación, debe usar la afinidad source_addr (o TCP) para los VIP de servicios web internos en el HLB.
  
Para obtener información detallada sobre todo esto, revise los [requisitos de](network-requirements/load-balancing.md) equilibrio de carga para la documentación de Skype Empresarial.
  
### <a name="reverse-proxy-requirements"></a>Requisitos de proxy inverso

Para admitir la detección automática para clientes móviles de Skype Empresarial, tendrá que actualizar la regla de publicación actual de la siguiente manera:
  
- Si decide actualizar las listas de SAN en los certificados de proxy inverso y usa HTTPS para la solicitud de servicio de detección automática inicial, debe actualizar la regla de publicación web para \<sipdomain\> lyncdiscover. Normalmente, esto se combina con el rul de publicación para la dirección URL de servicios web externos en el grupo de servidores front-end.
    
- Si ha decidido usar HTTP para la solicitud de servicio de detección automática inicial para evitar tener que actualizar la lista de SAN de los certificados de proxy inverso (lo que no recomendamos), deberá crear una nueva regla de publicación web para el puerto HTTP/TCP 80, si aún no existe. Si esa regla existe, actualíctela para incluir una detección de lync.\<sipdomain\> entrada.
    
## <a name="defining-your-mobility-needs"></a>Definir las necesidades de movilidad
<a name="MobilityNeeds"> </a>

Ahora que hemos revisado las topologías, los componentes y los requisitos técnicos, veamos lo que su organización puede necesitar en términos de una implementación de movilidad.
  
### <a name="do-you-want-to-use-automatic-discovery-for-skype-for-business-mobile-clients"></a>¿Desea usar la detección automática para clientes móviles de Skype Empresarial?

Se recomienda encarecidamente usar la detección automática. Requerirá la creación de nuevos registros DNS internos y externos, como se documenta en la sección de requisitos técnicos anterior. Con la detección automática, los clientes de Skype Empresarial pueden buscar automáticamente los servicios web de Skype Empresarial Server desde cualquier ubicación, sin necesidad de especificar una dirección URL manualmente.
  
Puede usar la configuración manual si es necesario. Los usuarios tendrán que introducir estas direcciones URL en sus dispositivos móviles:
  
- **https:// \<ExtPoolFQDN\> /Autodiscover/autodiscoverservice.svc/Root** para el acceso externo.
    
- **https:// \<IntPoolFQDN\> /Autodiscover/autodiscoverservice.svc/Root** para el acceso interno.
    
De nuevo, se recomienda usar la detección automática. Es posible que la configuración manual sea útil para solucionar problemas.
  
### <a name="are-you-going-to-support-push-notifications"></a>¿Va a admitir notificaciones de inserción?

Las notificaciones de inserción se usan para aplicaciones móviles que admiten esta funcionalidad para notificar a un usuario de eventos mientras la aplicación no está activa. El servidor perimetral necesitará tener una relación de federación con el servicio de notificación de inserción de Skype Empresarial Server basado en la nube, que se encuentra en el centro de datos de Skype Empresarial Online. Deberá ejecutar un cmdlet para habilitar las notificaciones de inserción.
  
> [!NOTE]
> Si tiene a alguien que aún usa clientes de Lync Server 2010, necesitará el puerto TCP 5223 saliente abierto en la red WiFi empresarial. 
  
### <a name="do-you-want-all-your-users-accessing-all-mobility-features-or-do-you-want-to-specify-the-users-who-can-access-these-features-instead"></a>¿Desea que todos los usuarios tengan acceso a todas las características de movilidad o desea especificar los usuarios que pueden acceder a estas características en su lugar?

Tenemos una tabla para ayudar con algunas de las características que están disponibles para todos los usuarios, y si se establecen de esa forma o no de forma predeterminada. Para obtener una lista completa, revise [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).
  
> [!NOTE]
> Los ámbitos de todas estas características son Global/Site/User. 
  
|**Característica**|**Nombre del parámetro**|**Descripción**|**Configuración predeterminada**|
|:-----|:-----|:-----|:-----|
|Habilitar la movilidad  <br/> |EnableMobility  <br/> |Controla los usuarios de un ámbito determinado que tienen instalado el cliente móvil de Skype Empresarial. Si la directiva se establece en False, los usuarios no podrán iniciar sesión con su cliente.  <br/> |Verdadero  <br/> |
|Voz externa  <br/> |EnableOutsideVoice  <br/> |Permite que un usuario pueda usar Vía trabajo, lo que permite a los usuarios enviar y recibir llamadas mediante su número de trabajo en lugar de su número de teléfono móvil. Si se establece en False, los usuarios no podrán realizar ni recibir llamadas en su teléfono móvil cuando utilicen su número de teléfono del trabajo.  <br/> |Verdadero  <br/> |
|Habilitar audio y vídeo IP  <br/> |EnableIPAudioVideo  <br/> |Se establece en el valor predeterminado, que permite a un usuario usar VoIP para realizar o recibir llamadas de teléfono o vídeo en su dispositivo móvil. Cuando se establece en False, los usuarios no podrán usar su dispositivo móvil para realizar ninguna de estas cosas.  <br/> |Verdadero  <br/> |
|Requerir WiFi para audio IP  <br/> |RequireWiFiForIPAudio  <br/> |Define si un cliente necesitará realizar y recibir llamadas a través de VoIP en WiFi en lugar de una red de datos móviles. Si se establece en True, los usuarios solo podrán realizar y recibir llamadas VoIP cuando estén conectados a través de WiFi.  <br/> |Falso  <br/> |
|Requerir WiFi para vídeo IP  <br/> |RequireWiFiForIPVideo  <br/> |Define si un cliente necesitará realizar y recibir videollamadas en una red WiFi en lugar de una red de datos móviles. Si se establece en True, los usuarios solo podrán realizar y recibir llamadas VoIP cuando estén conectados a través de WiFi.  <br/> |Falso  <br/> |
   
### <a name="should-users-who-arent-enabled-for-enterprise-voice-be-able-to-use-click-to-join-to-join-conferences"></a>¿Los usuarios que no están habilitados para Telefonía IP empresarial pueden usar Hacer clic para unirse para unirse a conferencias?

Para que los usuarios tengan acceso a las características de movilidad y Vía trabajo, deben estar habilitados para Telefonía IP empresarial. Pero incluso si no están habilitados, aún pueden unirse a conferencias haciendo clic en un vínculo en su dispositivo móvil, pero solo si tienen asignada una directiva de voz adecuada. Puede:
  
- asignar una directiva de voz específica a estos usuarios o,
    
- asegúrese de que existe una directiva global o de nivel de sitio y se aplica a ella.
    
En ambos casos, la directiva de voz que asigne debe tener registros de uso de la red telefónica conmutada (RTC) y rutas que definan dónde podrán llamar los usuarios para unirse a conferencias.
  
> [!NOTE]
> Los usuarios móviles que quieran usar Hacer clic para unirse requieren una directiva de voz, junto con los registros de uso de RTC y rutas de voz relacionados, ya que al hacer clic en ese vínculo en sus dispositivos móviles, se dará como resultado una llamada saliente de Skype Empresarial Server. 
  

