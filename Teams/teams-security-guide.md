---
title: Guía de seguridad para Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Consejos de seguridad y formación para administradores de TI sobre la instalación, la configuración y el mantenimiento de Microsoft Teams.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: 30599b73447e9b5ab9873c6cd48372d997def5d1
ms.sourcegitcommit: 3ef5c913318fdeeaa8c55caab07c2f8224eae2b0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2020
ms.locfileid: "43898125"
---
> [!IMPORTANT]
> El modelo de servicio de Teams está sujeto a cambios para mejorar la experiencia del cliente. Por ejemplo, el acceso predeterminado o los tiempos de vencimiento del token de actualización pueden estar sujetos a modificaciones para mejorar el rendimiento y la resistencia de autenticación para aquellos que usan Teams. Cualquiera de estos cambios se haría con el objetivo de mantener Teams seguro y confiable por naturaleza.
<p>

# <a name="security-and-microsoft-teams"></a>Seguridad y Microsoft Teams

Como parte del servicio Microsoft 365 (M365), Microsoft Teams sigue los procedimientos y prácticas de seguridad recomendados, como la seguridad de nivel de servicio a través de la defensa en profundidad, los controles de cliente dentro del servicio, el reforzamiento de la seguridad y los procedimientos operativos recomendados. Si necesita información detallada, consulte el [Centro de confianza de Microsoft](https://microsoft.com/trustcenter).

## <a name="trustworthy-by-design"></a>Confiable por su diseño

Teams está diseñado y desarrollado conforme al ciclo de vida de desarrollo de seguridad (SDL, Security Development Lifecycle) de Trustworthy Computing de Microsoft, que se describe en [Microsoft Security Development Lifecycle (SDL)](https://www.microsoft.com/sdl/default.aspx) (Ciclo de vida de desarrollo de seguridad [SDL] de Microsoft). El primer paso para crear un sistema de comunicaciones unificadas más seguro fue diseñar modelos de amenazas y probar cada característica tal como se diseñó. Se integraron múltiples mejoras relacionadas con la seguridad en el proceso y las prácticas de codificación. Las herramientas de tiempo de compilación detectan excesos de almacenaje y otras amenazas de seguridad antes de que el código se incorpore al producto final. Evidentemente no se puede diseñar una protección contra todas las amenazas de seguridad no conocidas. Ningún sistema puede garantizar una seguridad completa. Sin embargo, como el desarrollo del producto se basó en principios de diseño seguro desde el inicio, Teams cuenta con tecnologías de seguridad estándares del sector como parte fundamental de su infraestructura.

## <a name="trustworthy-by-default"></a>Confiable de forma predeterminada

Las comunicaciones de red de Teams se cifran de forma predeterminada. Al requerir que todos los servidores usen certificados y al usar OAUTH, TLS, el protocolo de transporte seguro en tiempo real (SRTP) y otras técnicas de cifrado estándares del sector, incluido el Estándar de cifrado avanzado (AES) de 256 bits, todos los datos de Teams están protegidos en la red.

## <a name="how-teams-handles-common-security-threats"></a>¿Cómo controla Teams las amenazas comunes de seguridad?

En esta sección se identifican las amenazas de seguridad más comunes del servicio Teams y la forma en que Microsoft minimiza cada una de ellas.

### <a name="compromised-key-attack"></a>Ataque mediante clave conocida

Teams usa las características de PKI en el sistema operativo Windows Server para proteger los datos clave que se usan para cifrar las conexiones de Seguridad de la capa de transporte (TLS). Las claves que se usan para cifrar medios se intercambian a través de conexiones TLS.

### <a name="network-denial-of-service-attack"></a>Ataque por denegación de servicio de red

El ataque por denegación de servicio tiene lugar cuando el atacante impide el uso y el funcionamiento normales de red a usuarios válidos. Con un ataque por denegación de servicio, el atacante puede:

- Enviar datos no válidos a las aplicaciones y los servicios que se ejecutan en la red que sufre el ataque para interrumpir su funcionamiento normal.
- Enviar una gran cantidad de tráfico, lo que sobrecarga el sistema hasta que deja de responder o responde lentamente a las solicitudes legítimas.
- Ocultar las pruebas de los ataques.
- Impedir que los usuarios obtengan acceso a los recursos de la red.
Teams ofrece protección frente a estos ataques mediante la ejecución de la protección de red Azure DDOS y la limitación de las solicitudes de los clientes desde los mismos puntos de conexión, subredes y entidades federadas.

### <a name="eavesdropping"></a>Interceptación

La interceptación se produce cuando un atacante obtiene acceso a la ruta de datos en una red y puede supervisar y leer el tráfico. Este tipo de ataque también se denomina rastreo o espionaje. Si el tráfico se produce como texto sin formato, el atacante puede leerlo cuando obtiene acceso a la ruta. Un ejemplo es un ataque que se realiza al controlar un enrutador de la ruta de acceso a los datos.

Teams utiliza TLS mutua (MTLS) para las comunicaciones del servidor en O365 y TLS de los clientes al servicio. Esto lo convierte en un ataque muy difícil o imposible de llevar a cabo en el período de tiempo en el que se puede atacar una conversación determinada. TLS autentica a todos los participantes y cifra todo el tráfico. Esto no impide la interceptación, pero el atacante no puede leer el tráfico a menos se interrumpa el cifrado.

El protocolo TURN se usa para lograr objetivos relacionados con elementos multimedia en tiempo real. El protocolo TURN no impone el cifrado del tráfico, y la información que envía está protegida por la integridad del mensaje. Si bien este protocolo está abierto a la interceptación, la información que envía (es decir, direcciones IP y puerto) se puede extraer directamente examinando simplemente las direcciones de origen y de destino de los paquetes. El servicio Teams se asegura de que los datos son válidos comprobando la integridad del mensaje mediante la clave derivada de algunos elementos, como una contraseña TURN, la cual no se envía nunca en texto no cifrado. SRTP (Secure Real-Time Transport Protocol) se utiliza para el tráfico de elementos multimedia y también está encriptado.

### <a name="identity-spoofing-ip-address-spoofing"></a>Suplantación de identidad (imitación de direcciones IP)

La suplantación de identidad (spoofing) se produce cuando el atacante identifica y usa una dirección IP de una red, un equipo o un componente de red sin tener autorización para ello. Un ataque con éxito permite al atacante operar como si el atacante fuera la entidad que normalmente se identifica por la dirección IP.

TLS autentica todas las partes y cifra todo el tráfico. El uso de TLS impide que un atacante realice la suplantación de direcciones IP en una conexión específica (por ejemplo, conexiones de TLS mutua). Un atacante aún podría suplantar la dirección del servidor DNS. Pero, puesto que la autenticación en Teams se realiza con certificados, un atacante no tendrá un certificado válido necesario para suplantar a una de las partes de la comunicación.

### <a name="man-in-the-middle-attack"></a>Ataque de intermediario

Un ataque de intermediario se produce cuando un atacante desvía la comunicación entre dos usuarios a través del equipo del atacante sin que lo sepan esos dos usuarios. El atacante puede supervisar y leer el tráfico antes de enviarlo al destinatario previsto. Sin darse cuenta, todos los usuarios que participan en la comunicación envían tráfico al atacante y reciben tráfico del mismo pensando que la comunicación se produce únicamente con el usuario previsto. Esto puede suceder si un atacante modifica los Servicios de dominio de Active Directory para agregar su servidor como un servidor de confianza o modifica el Sistema de nombres de dominio (DNS) para que los clientes se conecten al servidor a través del atacante.

Los ataques de intermediario en el tráfico multimedia entre dos puntos de conexión que participen en audio, vídeo y uso compartido de aplicaciones en Teams, se impide usando SRTP para cifrar la secuencia multimedia. Las claves de cifrado se negocian entre los dos puntos de conexión a través de un protocolo de señalización de propietario (protocolo de señalización de llamada de Teams) que usa el canal de cifrado UDP/TCP de TLS 1.2 y AES-256 (en modo GCM).

### <a name="rtp-replay-attack"></a>Ataque de reproducción RTP

Un ataque de reproducción se produce cuando se intercepta y retransmite una transmisión multimedia válida entre dos usuarios con fines malintencionados. Teams usa SRTP junto con un protocolo de señalización segura que protege las transmisiones de estos ataques al permitir que el receptor tenga un índice de los paquetes RTP ya recibidos y pueda comparar cada paquete nuevo con los que figuran en ese índice.

### <a name="spim"></a>Mensajes instantáneos no deseados

Los mensajes instantáneos no deseados son mensajes instantáneos comerciales no solicitados o solicitudes de suscripción de presencia, como el correo no deseado, pero en forma de mensaje instantáneo. Si bien estos mensajes por sí mismos no son un peligro para la seguridad de la red, son como mínimo molestos, pueden reducir la disponibilidad y la productividad de los recursos, y podrían llegar a poner en peligro la red. Un ejemplo de ello es el caso de usuarios que se envían solicitudes no deseadas entre sí. Los usuarios pueden bloquearse entre sí para evitarlo, pero con la federación, si se establece un ataque coordinado de este tipo, puede ser difícil de solucionar a menos que se deshabilite la federación para el asociado.

### <a name="viruses-and-worms"></a>Virus y gusanos

Un virus es una unidad de código cuyo propósito es reproducir otras unidades de código similares. Para que funcione, un virus necesita un anfitrión, como un archivo, un correo electrónico o un programa. Al igual que un virus, un gusano es una unidad de código que está codificada para reproducir unidades de código adicionales similares, pero que, a diferencia de un virus, no necesita un host. Los virus y los gusanos suelen aparecer principalmente durante las transferencias de archivo entre clientes o cuando otros usuarios envían direcciones URL. Si hay un virus en su equipo, podrá, por ejemplo, usar su identidad y enviar mensajes instantáneos en su nombre. Las medidas estándar de seguridad de cliente como los análisis periódicos en busca de virus pueden mitigar este problema.

## <a name="security-framework-for-teams"></a>Marco de seguridad de Teams

Esta sección ofrece información general sobre los elementos fundamentales que conforman un marco de seguridad de Microsoft Teams.

Los elementos básicos son:

- Azure Active Directory (AAD), que proporciona un único repositorio de back-end de confianza para cuentas de usuario. La información de perfil de usuario se almacena en AAD a través de las acciones de Microsoft Graph.
  - Tenga en cuenta que pueden emitirse varios tokens que es posible que vea si realiza un seguimiento de su tráfico de red. Esto incluye los tokens de Skype que puede ver en los seguimientos mientras se observa el tráfico de audio y el chat.
- Seguridad de la capa de transporte (TLS) y TLS mutua (MTLS) que cifran el tráfico de mensajes instantáneos y permiten la autenticación de extremos. Las secuencias de audio, vídeo y uso compartido de aplicaciones punto a punto se cifran y se comprueba su integridad con el protocolo de transporte seguro en tiempo real (SRTP). También puede ver el tráfico de OAuth en el seguimiento, especialmente en torno a los permisos negociables mientras se cambia entre pestañas en Teams, por ejemplo, para desplazarse de Publicaciones a Archivos. Para obtener un ejemplo del flujo de OAuth para pestañas, [consulte este documento](https://docs.microsoft.com/microsoftteams/platform/tabs/how-to/authentication/auth-flow-tab).
- Teams usa protocolos estándar del sector para la autenticación de usuarios, siempre que sea posible.

En las siguientes secciones se tratan algunas de estas tecnologías básicas.

### <a name="azure-active-directory"></a>Azure Active Directory

Azure Active Directory funciona como el servicio de directorio para Office 365 (O365). Almacena todas las asignaciones de directivas y la información de directorio de usuario.

#### <a name="crl-distribution-points"></a>Puntos de distribución de CRL

El tráfico de O365 se realiza en canales cifrados TLS/HTTPS, lo que significa que los certificados se usan para el cifrado de todo el tráfico. Teams requiere que todos los certificados de servidor cuenten con uno o más puntos de distribución de listas de revocación de certificados (CRL). Los puntos de distribución CRL (CDP) son ubicaciones desde las que se pueden descargar CRL para comprobar si un certificado no ha sido revocado después de su emisión y todavía se encuentra dentro del período de validez. Un punto de distribución CRL se anota en las propiedades del certificado como una dirección URL y es HTTPS. El servicio Teams comprueba CRL con cada autenticación de certificado.

#### <a name="enhanced-key-usage"></a>Uso mejorado de clave

Los componentes del servicio Teams requieren que los certificados de servidor sean compatibles con el Uso mejorado de clave (EKU) para la autenticación del servidor. La configuración del campo EKU para la autenticación de los servidores significa que el certificado es válido para la autenticación de los servidores. Este EKU es esencial para MTLS.

### <a name="tls-and-mtls-for-teams"></a>TLS y MTLS para Teams

TLS y MTLS ofrecen comunicaciones cifradas y autenticación de puntos de conexión en Internet. Teams utiliza estos dos protocolos para crear la red de servidores de confianza y garantizar que todas las comunicaciones en esa red estén cifradas. Todas las comunicaciones entre los servidores se llevan a cabo a través de MTLS. Las comunicaciones SIP restantes o heredadas entre el cliente y el servidor se realizan a través de TLS.

TLS permite a los usuarios, mediante su software cliente, autenticar los servidores Teams a los que se conectan. En una conexión TLS, el cliente solicita un certificado válido al servidor. Para que sea válido, una entidad de certificación (CA) debe haber emitido el certificado; esa CA también debe ser de confianza para el cliente y el nombre DNS del servidor debe coincidir con el nombre DNS del certificado. Si el certificado es válido, el cliente usa la clave pública del certificado para cifrar las claves de cifrado simétricas que se utilizarán para la comunicación, de modo que solo el propietario original del certificado puede usar su clave privada para descifrar el contenido de la comunicación. La conexión resultante es fiable y desde ese punto no es desafiada por otros servidores o clientes fiables.

Las conexiones de servidor a servidor se basan en TLS mutua (MTLS) para autenticación mutua. En una conexión MTLS, el servidor de origen de un mensaje y el que lo recibe intercambian certificados procedentes de una CA de confianza para ambos. Los certificados permiten a los servidores demostrarse mutuamente sus identidades. En el servicio Teams se sigue este procedimiento.

TLS y MTLS evitan la interceptación y los ataques de intermediario. En los ataques de intermediario, el atacante enruta las comunicaciones entre dos entidades de red a través del equipo del atacante sin que lo sepa ninguna de esas entidades. La especificación de los servidores de confianza por parte de TLS y de los Teams mitiga el riesgo de un ataque intermediario parcialmente en el nivel de aplicación mediante el uso de un cifrado coordinado con la criptografía de clave pública entre los dos puntos finales. Un atacante tendría que tener un certificado válido y de confianza con la clave privada correspondiente y expedir el nombre del servicio al que se comunica el cliente para descifrar la comunicación.

> [!NOTE]
> Los datos de Teams se cifran en tránsito y en reposo. Microsoft usa tecnologías estándares del sector como TLS y SRTP para cifrar todos los datos en tránsito entre los dispositivos de los usuarios y los centros de datos de Microsoft, así como entre los centros de datos de Microsoft. Esto incluye mensajes, archivos, reuniones y otro contenido. Los datos empresariales también se cifran en reposo en los centros de datos de Microsoft, para que las organizaciones puedan descifrar el contenido en caso necesario, para cumplir con sus obligaciones de seguridad y cumplimiento, como eDiscovery.

### <a name="encryption-for-teams"></a>Cifrado para Teams

Teams usa TLS y MTLS para cifrar los mensajes instantáneos. Todo el tráfico de servidor a servidor necesita MTLS, independientemente de si el tráfico está limitado a la red interna o atraviesa el perímetro de esta.

En esta tabla, se resumen los protocolos que usa Teams.

***Cifrado de tráfico***

|||
|:-----|:-----|
|**Tipo de tráfico**|**Cifrado por**|
|Servidor a servidor|MTLS|
|Cliente a servidor (p. ej., mensajería instantánea y presencia)|TLS|
|Flujos multimedia (p. ej., uso compartido de audio y vídeo en elementos multimedia)|TLS|
|Uso compartido de audio y vídeo en elementos multimedia|SRTP/TLS|
|Señalización|TLS|
|||

#### <a name="media-encryption"></a>Cifrado de medios

El tráfico de medios se cifra mediante RTP seguro (SRTP), que es un perfil de protocolo de transporte en tiempo real (RTP) que proporciona al tráfico RTP confidencialidad, autenticación y protección contra los ataques de reproducción. SRTP utiliza una clave de sesión creada con un generador de números aleatorios seguros y se intercambia mediante el canal de señalización TLS. El tráfico multimedia de cliente a cliente se negocia a través de una señalización de conexión de cliente a servidor, pero se cifra con SRTP cuando se dirige directamente de cliente a cliente.

Teams usa un token basado en credenciales para el acceso seguro a los relés multimedia mediante TURN. Los relés multimedia intercambian el token a través de un canal seguro de TLS.

#### <a name="fips"></a>FIPS

Teams utiliza algoritmos compatibles con FIPS (Estándar federal de procesamiento de información) para intercambiar claves de cifrado. Para obtener más información sobre la implementación de FIPS, vea la [publicación 140-2 de Estándares Federales de Procesamiento de la Información (FIPS)](https://docs.microsoft.com/microsoft-365/compliance/offering-fips-140-2?view=o365-worldwide).

### <a name="user-and-client-authentication"></a>Autenticación de usuario y cliente

Un usuario de confianza es aquél cuyas credenciales se han autenticado mediante AAD en Office 365/Microsoft 365.

La autenticación consiste en proporcionar credenciales de usuario a un servicio o servidor de confianza. Teams utiliza los siguientes protocolos de autenticación, según el estado y la ubicación del usuario.

- La **Autenticación moderna (MA)** consiste en la implementación por parte de Microsoft de OAUTH 2.0 para la comunicación de cliente a servidor. Ofrece características de seguridad, por ejemplo, Autenticación multifactor de O365 y Acceso condicional de O365. Para poder usar MA, tanto el inquilino en línea como los clientes deben estar habilitados para MA. Los clientes de Teams entre equipos y dispositivos móviles, así como el cliente web, [son compatibles con MA](https://docs.microsoft.com/microsoftteams/sign-in-teams).

> [!NOTE]
> Si necesita ponerse al día sobre la autenticación y los métodos de autorización de Azure AD, las secciones Introducción y "Aspectos básicos de la autenticación en Azure AD" de este artículo le serán útiles.

La autenticación de Teams se lleva a cabo mediante AAD y OAuth. El proceso de autenticación se puede simplificar de la manera siguiente:

- Inicio de sesión del usuario > emisión del token > token emitido de uso para solicitud posterior.

Las solicitudes del cliente al servidor se autentican y autorizan mediante el uso de la autenticación de OAuth. Los usuarios con credenciales válidas emitidas por un socio federado son de confianza y pasan por el mismo proceso que los usuarios nativos. Sin embargo, los administradores pueden aplicar otras restricciones.

Para la autenticación multimedia, los protocolos ICE y TURN también usan el desafío de autenticación implícita que se describe en la RFC del IETF referente a TURN.

### <a name="windows-powershell-and-team-management-tools"></a>Herramientas de administración de Teams y Windows PowerShell

En Teams, los administradores de TI pueden administrar sus servicios a través del portal de administración de O365 o mediante el uso de Tenant Remote PowerShell (TRPS). Los administradores de inquilinos usan la Autenticación moderna para autenticarse en TRPS.

### <a name="configuring-access-to-teams-at-your-internet-boundary"></a>Configurar el acceso a Teams en su límite de Internet

Para que Teams pueda funcionar correctamente (de modo que los usuarios puedan unirse a reuniones, etc.), los clientes deben configurar el acceso a Internet para que se permita el tráfico UDP y TCP saliente a los servicios en la nube de Teams. Para obtener más información, consulte aquí: [Intervalos de direcciones IP y URL de Office 365](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).

### <a name="udp-3478-3481-and-tcp-443"></a>UDP 3478-3481 y TCP 443

Los clientes usan los puertos UDP 3478 a 3481 y TCP 443 para solicitar el servicio audiovisual. Un cliente utiliza estos dos puertos para asignar puertos UDP y TCP, respectivamente, con el fin de permitir estos flujos multimedia. Los flujos multimedia en estos puertos se protegen con una clave que se intercambia a través de un canal de señalización protegida TLS.

### <a name="udptcp-5000059999-optional"></a>UDP/TCP 50 000 – 59 999 (opcional)

Los puertos del intervalo alto no usan la retransmisión de transporte. Dado que son puertos opcionales, no los encontrará en las direcciones URL ni los intervalos de direcciones IP de Office 365. Esto también implica que Teams funcionará si estos puertos están bloqueados, debido a que el tráfico usa los intervalos de puertos de 3478 a 3481 (retransmisión de transporte). Se usan para el tránsito multimedia, pero incluso si estos rangos se desbloquean, la reducción del retraso será mínima (unos milisegundos). En la mayoría de los casos, los problemas con la calidad multimedia no se verán afectados al desbloquear y usar estos puertos. Es necesario que todas las investigaciones de estos problemas se centren en otro lugar.

### <a name="federation-safeguards-for-teams"></a>Protecciones de federación de Teams

La federación ofrece a su organización la posibilidad de comunicarse con otras organizaciones para compartir mensajería instantánea y presencia. En Teams, la federación está activada de forma predeterminada. Pero los administradores de inquilinos pueden controlar esta opción mediante el Portal de administración de O365.

## <a name="addressing-threats-to-teams-meetings"></a>Solucionar amenazas para reuniones de Teams

Hay dos opciones para controlar quién llega a las reuniones de Teams y quién tendrá acceso a la información que se presenta.

1. Puede controlar quién se une a las reuniones mediante la configuración de la **sala de espera**.</p>

|Hay opciones de configuración para "¿Quién puede omitir la sala de espera?" disponibles en la página Opciones de reunión   |Tipos de usuarios que se unen a la reunión directamente  |Tipos de usuarios que van a la sala de espera   |
|---------|---------|---------|
|Usuarios en mi organización     |  - Cuentas empresariales  </br>- Invitados del espacio empresarial         |  - Federados</br>  - Anónimos</br>  - Acceso telefónico PSTN</br>     |
|Usuarios de mi organización y de organizaciones de confianza      |  - Cuentas empresariales</br> - Invitados del espacio empresarial</br> - Federados</br>        |  - Anónimos</br>  - Acceso telefónico PSTN</br>      |
|Todos      |   - Cuentas empresariales</br>  - Invitados del espacio empresarial</br>  - Federados anónimos</br>  - Acceso telefónico PSTN</br>       |         |

2. El segundo método consiste en **reuniones estructuradas** (donde los moderadores pueden hacer todo lo que se debería hacer, y los asistentes tienen una experiencia controlada). Después de unirse a una reunión estructurada, los moderadores controlan lo que pueden hacer los asistentes en la reunión. </p>

|Acciones  |Moderadores  |Asistentes  |
|---------|---------|---------|
|Hablar y compartir su vídeo     |   v      |   v      |
|Participar en el chat de la reunión     |   v    |    v     |
|Cambiar la configuración en las opciones de reunión     |   v      |  N       |
|Silenciar a otros participantes| v | N |
|Quitar a otros participantes      |  v       |   N      |
|Compartir contenido     |     v    |     N    |
|Admitir a otros participantes de la sala de espera|  v       |   N      |
|Hacer que otros participantes sean moderadores o asistentes     |   v      | N        |
|Iniciar o detener una grabación     |     v    |    N     |
|Tomar el control cuando otro participante comparte una presentación de PowerPoint     |  v         | N        |

Teams permite que los usuarios empresariales creen reuniones en tiempo real y se unan a ellas. Los usuarios empresariales también pueden invitar a usuarios externos que no tengan una cuenta de AAD/Office 365 para que participen en estas reuniones. Los usuarios que son empleados de socios externos con una identidad segura y autenticada también pueden unirse a las reuniones y, si se les promueve para hacerlo, pueden actuar como moderadores. Los usuarios anónimos no pueden crear una reunión ni unirse a una como moderadores, pero se pueden promover a moderador después de que se unan.

Para que los usuarios anónimos puedan unirse a las reuniones de Teams, debe estar activada la opción Participantes para reuniones en el Centro de administración de Teams.

> [!NOTE]
> El término *usuarios anónimos* significa que los usuarios no se autentican en el inquilino de la organización. En este contexto, todos los usuarios externos se consideran anónimos. Los usuarios autenticados pueden ser usuarios o invitados del inquilino.

Permitir que los usuarios externos participen en las reuniones de Teams puede ser muy útil, pero conlleva ciertos riesgos de seguridad. Para abordar estos riesgos, Teams usa las siguientes medidas de seguridad adicionales:

- Los roles de los participantes determinan los privilegios de control de la reunión.
- Los tipos de participante permiten limitar el acceso a reuniones específicas.
- La programación de reuniones está restringida a los usuarios que tienen una cuenta de AAD y una licencia de Teams.
- Los usuarios anónimos, es decir, que no están autenticados, que deseen unirse a una conferencia de acceso por marcado necesitan marcar uno de los números de acceso a la conferencia. Si la opción "Permitir siempre que los autores de llamadas eviten la sala de espera" está *activada*, también tendrán que esperar hasta que un moderador o usuario autenticado se una a la reunión.

> [!CAUTION]
> Si no quiere que los usuarios anónimos (usuarios que no invite explícitamente) se unan a una reunión, debe asegurarse de que **Usuarios anónimos pueden unirse a una reunión** esté configurado como **Desactivado** para la sección de reunión **Participantes**.

También es posible que un organizador establezca las opciones de configuración para permitir que los autores de llamadas de acceso por marcado sean los primeros en una reunión. Esta opción se establece en la configuración de conferencia de audio para los usuarios y se aplicará a todas las reuniones programadas por el usuario.

> [!NOTE]
> Para obtener más información sobre el acceso externo y de invitados en Teams, consulte este [artículo](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations). En él se explican las características que los usuarios externos o invitados pueden ver y usar cuando inician sesión en Teams.

### <a name="participant-roles"></a>Roles de los participantes

Los participantes de la reunión se dividen en tres grupos, cada uno con sus propios privilegios y restricciones:

- **Organizador**: el usuario que crea una reunión, independientemente de si es improvisada o programada. Un organizador debe ser un usuario de cuenta empresarial autenticada y tener el control sobre todos los aspectos de usuario final de la reunión.
- **Moderador**: un usuario al que se autoriza la presentación de información durante una reunión con cualquier elemento multimedia admitido. El organizador de la reunión es, por definición, también un moderador y determina quién más puede serlo. Un organizador puede determinarlo cuando se programa una reunión o mientras se está llevando a cabo.
- **Asistente**: un usuario al que se le ha invitado a asistir a una reunión, pero que no está autorizado para actuar como moderador.

Un moderador también puede promover a un asistente al rol de moderador durante la reunión.

### <a name="participant-types"></a>Tipos de participantes

Los participantes en la reunión también se clasifican por ubicación y credenciales. Puede utilizar estas dos características para decidir qué usuarios pueden tener acceso a reuniones específicas. Los usuarios se pueden dividir de forma general en las siguientes categorías:

1. **Usuarios que pertenecen al inquilino**: estos usuarios tienen una credencial en Azure Active Directory para el inquilino.
    a. *Usuarios de mi organización*: estos usuarios tienen una credencial en Azure Active Directory para el inquilino. *Usuarios de mi organización* incluye cuentas de invitado.
    b. *Usuarios remotos*: estos usuarios se unen desde fuera de la red corporativa. Pueden incluir empleados que trabajan desde casa o mientras viajan, y otros, como empleados de proveedores de confianza, a quienes se les han otorgado credenciales empresariales por sus términos de servicio. Los usuarios remotos pueden crear reuniones y unirse a ellas, así como actuar como moderadores.
.
2. **Usuarios que no pertenecen al inquilino** estos usuarios no tienen una credencial en Azure AD para el inquilino.
    a. *Usuarios federados*: los usuarios federados tienen credenciales válidas con asociados federados y, por lo tanto, se tratan como autenticadas por Teams, pero siguen siendo anónimos para el inquilino del organizador de la reunión. Los usuarios federados pueden unirse a reuniones y ser promovidos a moderadores después de unirse a la reunión, pero no pueden crear reuniones en las empresas con las que se hayan federado.
    b. *Usuarios anónimos*: no tienen una identidad de Active Directory y no están federados con el inquilino.

En muchas reuniones se incluyen usuarios externos. Esos clientes también quieren confirmar la identidad de los usuarios externos antes de permitir que se unan a una reunión. En la siguiente sección, se describe cómo Teams limita el acceso a una reunión a los tipos de usuarios permitidos y requiere que todos los tipos de usuario presenten las *credenciales* adecuadas al entrar en una reunión.

### <a name="participant-admittance"></a>Admisión de participantes

> [!CAUTION]
> Si no quiere que los usuarios anónimos (usuarios que no invite explícitamente) se unan a una reunión, debe asegurarse de que **Usuarios anónimos pueden unirse a una reunión** esté configurado como **Desactivado** para la sección de reunión **Participantes**.

En Teams, los usuarios anónimos pueden transferirse a un área llamada sala de espera. A continuación, los moderadores pueden *admitir* a estos usuarios en la reunión o *rechazarlos*. Cuando estos usuarios se transfieren a la sala de espera, se notifica al moderador y a los asistentes, y los usuarios anónimos tienen que esperar hasta que se les acepte o rechace, o se agote el tiempo de espera de la conexión.

De forma predeterminada, los participantes que marcan para acceder desde RTC pasan directamente a la reunión cuando un usuario autenticado se une a ella, pero esta opción se puede cambiar para obligarlos a pasar a la sala de espera.

Los organizadores de la reunión controlan si los participantes pueden unirse a una reunión sin aguardar en la sala de espera. Cada reunión puede configurarse para permitir el acceso mediante cualquiera de los métodos siguientes:

Los valores predeterminados son:

- *Usuarios de mi organización*: todos los usuarios externos a la organización esperarán en la sala de espera hasta que se les admita.
- *Usuarios de mi organización y de organizaciones de confianza*: los usuarios autenticados y usuarios externos de Teams y dominios de Skype Empresarial que están en la lista de permitidos de acceso externo pueden evitar la sala de espera. Los demás usuarios permanecerán en la sala de espera hasta que se les admita.
- *Todos los usuarios*: todos los participantes de la reunión evitan la sala de espera cuando un usuario autenticado se une a la reunión.

### <a name="presenter-capabilities"></a>Capacidades del presentador

Los organizadores de la reunión controlan si los participantes pueden realizar presentaciones durante una reunión. Cada reunión puede configurarse para limitar los presentadores, según estas opciones:

- *Usuarios de mi organización*: todos los usuarios del inquilino, incluidos los invitados, pueden presentar contenido.
- *Usuarios de mi organización y de organizaciones de confianza*: todos los usuarios del inquilino, incluidos los invitados, pueden presentar contenido, y los usuarios externos de Teams y de dominios de Skype Empresarial que estén en la lista de permitidos de acceso externo pueden presentar contenido.  
- *Todos*: todos los participantes de la reunión son moderadores.

### <a name="modify-while-meeting-is-running"></a>Modificar mientras se lleva a cabo la reunión

Las opciones de reunión se pueden modificar mientras se celebra la reunión. Cuando se guarde el cambio, este afectará a la reunión en marcha en cuestión de segundos. También afectará a las repeticiones futuras de la reunión.

## <a name="related-topics"></a>Temas relacionados

[Las 12 tareas principales de los equipos de seguridad para dar soporte al trabajo desde casa](https://docs.microsoft.com/microsoft-365/security/top-security-tasks-for-remote-work)

[Centro de confianza de Microsoft](https://microsoft.com/trustcenter)

[Administrar la configuración de reuniones en Microsoft Teams](https://docs.microsoft.com/microsoftteams/meeting-settings-in-teams)

[Optimizar la conectividad de Office 365 para usuarios remotos que usan túnel dividido de VPN](https://docs.microsoft.com/Office365/Enterprise/office-365-vpn-split-tunnel)

- [Implementación de túnel dividido de VPN en Office 365](https://docs.microsoft.com/Office365/Enterprise/office-365-vpn-implement-split-tunnel)
