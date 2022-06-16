---
title: Guía de seguridad para Microsoft Teams
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
ms.date: 04/12/2022
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: pawa
description: Consejos de seguridad y formación para administradores de TI sobre la instalación, la configuración y el mantenimiento de Microsoft Teams.
ms.localizationpriority: high
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
ms.openlocfilehash: 6e5dcee1e45ec191853f088887e7ed36f8e3fbc6
ms.sourcegitcommit: 39fc58109da6b4628ffb658f2c6b94099e0ab604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/15/2022
ms.locfileid: "66103207"
---
# <a name="security-and-microsoft-teams"></a>Seguridad y Microsoft Teams

> [!IMPORTANT]
> El modelo de servicio de Teams está sujeto a cambios para mejorar la experiencia del cliente. Por ejemplo, el acceso predeterminado o los tiempos de vencimiento del token de actualización pueden estar sujetos a modificaciones para mejorar el rendimiento y la resistencia de autenticación para aquellos que usan Teams. Cualquiera de estos cambios se haría con el objetivo de mantener Teams seguro y confiable por naturaleza.

Como parte del servicio de Microsoft 365 y Office 365, Microsoft Teams sigue los procedimientos y prácticas de seguridad recomendados, como la seguridad de nivel de servicio a través de la defensa en profundidad, los controles de cliente dentro del servicio, el reforzamiento de la seguridad y los procedimientos operativos recomendados. Si necesita información detallada, consulte el [Centro de confianza de Microsoft](https://microsoft.com/trustcenter).

## <a name="trustworthy-by-design"></a>Confiable por su diseño

Teams está diseñado y desarrollado conforme al ciclo de vida de desarrollo de seguridad (SDL, Security Development Lifecycle) de Informática de confianza (Trustworthy Computing) de Microsoft, que se describe en [Microsoft Security Development Lifecycle (SDL)](https://www.microsoft.com/sdl/default.aspx) (Ciclo de vida de desarrollo de seguridad [SDL] de Microsoft). El primer paso para crear un sistema de comunicaciones unificadas más seguro fue diseñar modelos de amenazas y probar cada característica tal como se ha diseñado. Se han integrado varias mejoras relacionadas con la seguridad en los procesos y procedimientos de codificación. Las herramientas en tiempo de compilación han detectado la saturación del búfer y otras posibles amenazas para la seguridad antes de que se comprobase el código en el producto final. Es imposible que, al diseñar, se tengan en cuenta todas las amenazas desconocidas en materia de seguridad. Ningún sistema puede garantizar una total seguridad. Sin embargo, dado que el desarrollo de productos se basa en principios de diseño seguro desde un principio, Teams incorpora tecnologías de seguridad estándar en la industria como parte fundamental de su arquitectura.

## <a name="trustworthy-by-default"></a>Confiable de forma predeterminada

En Teams, todas las comunicaciones en red se cifran de forma predeterminada. Al requerir que todos los servidores usen certificados y al usar OAUTH, Transport Layer Security (TLS) y el protocolo de transporte seguro en tiempo real (SRTP), todos los datos de Teams están protegidos en la red.

## <a name="how-teams-handles-common-security-threats"></a>¿Cómo controla Teams las amenazas comunes de seguridad?

En esta sección se identifican las amenazas de seguridad más comunes del servicio Teams y la forma en que Microsoft minimiza cada una de ellas.

### <a name="compromised-key-attack"></a>Ataque mediante clave conocida

Teams usa las características de PKI en el sistema operativo Windows Server para proteger los datos clave usados para el cifrado de las conexiones TLS. Las claves usadas para los cifrados multimedia se intercambian a través de conexiones TLS.

### <a name="network-denial-of-service-attack"></a>Ataque por denegación de servicio de red

Un ataque por denegación de servicio distribuido (DDOS) tiene lugar cuando el atacante impide el uso y el funcionamiento normales de red a usuarios válidos. Al usar un ataque por denegación de servicio, el atacante puede:

- Enviar datos no válidos a las aplicaciones y los servicios que se ejecutan en la red que sufre el ataque para interrumpir su funcionamiento normal.
- Enviar una gran cantidad de tráfico, lo que sobrecarga el sistema hasta que deja de responder o responde lentamente a las solicitudes legítimas.
- Ocultar las pruebas de los ataques.
- Impedir que los usuarios obtengan acceso a los recursos de la red.

Teams ofrece protección frente a estos ataques mediante la ejecución de la protección de red Azure DDOS y la limitación de las solicitudes de los clientes desde los mismos puntos de conexión, subredes y entidades federadas.

### <a name="eavesdropping"></a>Interceptación

La interceptación se produce cuando un atacante obtiene acceso a la ruta de datos en una red y puede supervisar y leer el tráfico. El espionaje también se denomina rastreo o espionaje. Si el tráfico se produce como texto sin formato, el atacante puede leerlo cuando obtiene acceso a la ruta. Un ejemplo es un ataque que se realiza al controlar un enrutador de la ruta de acceso a los datos.

Teams usa TLS mutua (MTLS) y OAuth de servidor a servidor (S2S) (entre otros protocolos) para las comunicaciones de servidor dentro de Microsoft 365 y Office 365, y también usa TLS desde los clientes al servicio. Todo el tráfico de la red está cifrado.

Estos métodos de comunicación hacen que la interceptación sea difícil o imposible de lograr dentro del período de tiempo de una sola conversación. TLS autentica todas las partes y cifra todo el tráfico. Mientras TLS no evita la interceptación, el atacante no puede leer el tráfico a menos que se interrumpa el cifrado.

El protocolo *Traversal Using Relays around NAT* (TURN) se utiliza para elementos multimedia en tiempo real. Este protocolo no obliga al cifrado del tráfico y la información que se envía está protegida por la integridad del mensaje. Si bien este protocolo está abierto a la interceptación, la información que se envía, es decir, direcciones IP y puerto, se puede extraer directamente examinando las direcciones de origen y de destino de los paquetes. El servicio de Teams se asegura de que los datos son válidos comprobando la integridad del mensaje mediante la clave derivada de algunos elementos como la contraseña TURN, la cual nunca se envía sin cifrar. El protocolo SRTP es el que se utiliza para el tráfico multimedia y también se cifra.

### <a name="identity-spoofing-ip-address-spoofing"></a>Suplantación de identidad (imitación de direcciones IP)

La suplantación de identidad (spoofing) se produce cuando el atacante identifica y luego usa una dirección IP de una red, un equipo o un componente de red sin tener autorización para ello. El ataque ha tenido éxito cuando el atacante es capaz de operar como si él fuera la entidad que reconoce normalmente la dirección IP. 

TLS autentica a todas las partes y encripta todo el tráfico. El uso de TLS evita que un atacante suplante las direcciones IP en una conexión concreta (por ejemplo, conexiones Mutual TLS). Aún así, un atacante podría suplantar la dirección del servidor Sistema de nombres de dominio (DNS). No obstante, puesto que la autenticación en Teams se realiza con certificados, un atacante no tendrá la información válida necesaria para suplantar a una de las partes en el proceso de comunicación.

### <a name="man-in-the-middle-attack"></a>Ataque de intermediario

Un ataque de intermediario se produce cuando un atacante desvía la comunicación entre dos usuarios a través del equipo del atacante sin que lo sepan esos dos usuarios. El atacante puede supervisar y leer el tráfico antes de enviarlo al destinatario previsto. Sin darse cuenta, todos los usuarios que participan en la comunicación envían tráfico al atacante y reciben tráfico del mismo pensando que la comunicación se produce únicamente con el usuario previsto. Este escenario puede suceder si un atacante modifica los Servicios de dominio de Active Directory para agregar su servidor como un servidor de confianza o modifica la configuración de DNS o usa otros medios para que los clientes se conecten al servidor a través del atacante.

Los ataques de intermediario en el tráfico multimedia entre dos puntos de conexión que participen en audio, vídeo y uso compartido de aplicaciones en Teams, se impide usando el *Protocolo de transporte en tiempo real seguro* (SRTP) para cifrar la secuencia multimedia. Las claves de cifrado se negocian entre los dos puntos de conexión a través de un protocolo de señalización de propietario (protocolo de señalización de llamada de Teams) que usa el canal de cifrado UDP o TCP de TLS 1.2 y AES-256 (en modo GCM).

### <a name="real-time-transport-protocol-rtp-replay-attack"></a>Ataque de reproducción del Protocolo de transporte en tiempo real (RTP)

Un ataque de reproducción se produce cuando se intercepta y retransmite una transmisión multimedia válida entre dos usuarios con fines malintencionados. Teams usa SRTP con un protocolo de señalización segura que protege las transmisiones de estos ataques al permitir que el receptor tenga un índice de los paquetes RTP ya recibidos y pueda comparar cada paquete nuevo con los paquetes que ya figuran en ese índice.

### <a name="spim"></a>Mensajes instantáneos no deseados

El término inglés "spim" hace referencia a los mensajes instantáneos comerciales no deseados o a las solicitudes de suscripción de presencia no deseadas, como correo no deseado, pero en forma de mensaje instantáneo. Si bien estos mensajes por sí mismos no son un peligro para la seguridad de la red, son como mínimo molestos, pueden reducir la disponibilidad y la productividad de los recursos, y podrían llegar a poner en peligro la red. Un ejemplo es el caso de usuarios que se envían solicitudes no deseadas entre sí. Los usuarios pueden bloquearse entre sí para evitar el spimming, pero con la federación, si un actor malintencionado establece un ataque coordinado de este tipo, puede ser difícil de solucionar a menos que se deshabilite la federación del asociado.

### <a name="viruses-and-worms"></a>Virus y gusanos

Un virus es una unidad de código que tiene por objeto reproducir más unidades de código similares. Los virus necesitan un host, como un archivo, un correo electrónico o un programa, para poder funcionar. Al igual que un virus, un gusano también es una unidad de código que reproduce más unidades de código similares, pero no necesita un host. Los virus y los gusanos suelen aparecer principalmente durante las transferencias de archivo entre clientes o cuando otros usuarios envían direcciones URL. Si hay un virus en su equipo, podrá, por ejemplo, usar su identidad y enviar mensajes instantáneos en su nombre. Para mitigar este problema, el usuario medio debería seguir los procedimientos de seguridad recomendados como, por ejemplo, examinar periódicamente el equipo en busca de virus.

## <a name="security-framework-for-teams"></a>Marco de seguridad de Teams

Teams aprueba ideas de seguridad como Confianza cero y Principios de acceso con privilegios mínimos. Esta sección ofrece información general sobre los elementos fundamentales que conforman un marco de seguridad de Microsoft Teams.

Los elementos básicos son:

- Azure Active Directory (Azure AD), que proporciona un único repositorio de back-end de confianza para cuentas de usuario. La información de perfil de usuario se almacena en Azure AD a través de las acciones de Microsoft Graph.
  - Pueden emitirse varios tokens que es posible que vea si realiza un seguimiento de su tráfico de red. Incluyendo los tokens de Skype que puede ver en los seguimientos mientras se observa el tráfico de audio y el chat.
- Seguridad de la capa de transporte (TLS) cifra el canal en movimiento. La autenticación tiene lugar mediante TLS mutua (MTLS), basada en certificados, o mediante la autenticación de servicio a servicio basada en Azure AD.
- Las secuencias de audio, vídeo y uso compartido de aplicaciones punto a punto se cifran y se comprueba su integridad con el protocolo de transporte seguro en tiempo real (SRTP).
- También verá el tráfico de OAuth en el seguimiento, especialmente en torno a los intercambios de token y los permisos negociables mientras se cambia entre pestañas en Teams, por ejemplo, para desplazarse de Publicaciones a Archivos. Para obtener un ejemplo del flujo de OAuth para pestañas, [consulte este documento](/microsoftteams/platform/tabs/how-to/authentication/auth-flow-tab).
- Teams usa protocolos estándar del sector para la autenticación de usuarios, siempre que sea posible.

En las siguientes secciones se tratan algunas de estas tecnologías básicas.

### <a name="azure-active-directory"></a>Azure Active Directory

Azure Active Directory funciona como el servicio de directorio para Microsoft 365 y Office 365. Almacena toda la información del directorio de usuarios y aplicaciones, y las asignaciones de directivas.

### <a name="traffic-encryption-in-teams"></a>Cifrado de tráfico en Teams

En esta tabla, se muestran los tipos de tráfico principales y qué protocolo se usa para el cifrado.

|**Tipo de tráfico**|**Cifrado por**|
|:-----|:-----|
|Servidor a servidor|TLS (con MTLS o OAuth de servicio a servicio)|
|Del cliente al servidor, por ejemplo, mensajería instantánea y presencia|TLS|
|Flujos multimedia, por ejemplo, uso compartido de audio y vídeo multimedia|TLS|
|Uso compartido de audio y vídeo en elementos multimedia|SRTP/TLS|
|Señalización|TLS|
|Cifrado mejorado de cliente a cliente (por ejemplo, llamadas de cifrado de un extremo a otro)|SRTP/DTLS|
|||

#### <a name="certificate-revocation-list-crl-distribution-points"></a>Puntos de distribución de lista de revocación de certificados (CRL)

El tráfico de Microsoft 365 y Office 365 se lleva a cabo a través de canales cifrados TLS/HTTPS. Es decir, se utilizan certificados para cifrar todo el tráfico. Teams requiere que todos los certificados de servidor cuenten con uno o más puntos de distribución de CRL. Los puntos de distribución CRL (CDP) son ubicaciones desde las que se pueden descargar CRL para comprobar si un certificado no ha sido revocado después de su emisión y todavía se encuentra dentro del período de validez. Un punto de distribución CRL se indica en las propiedades del certificado como una dirección URL y es HTTP seguro.

#### <a name="enhanced-key-usage"></a>Uso mejorado de clave

Los componentes de Teams requieren que todos los certificados de servidor admitan el uso mejorado de clave (EKU) para la autenticación de los servidores. La configuración del campo EKU para la autenticación de los servidores significa que el certificado es válido para autenticar los servidores. Este EKU es esencial para MTLS.

#### <a name="tls-for-teams"></a>TLS para Teams

**Los datos de Teams se cifran en tránsito y en reposo en los servicios Microsoft, entre servicios, y entre clientes y servicios.** Microsoft realiza esto mediante tecnologías estándar del sector como TLS y SRTP para cifrar todos los datos en tránsito. Los datos en tránsito incluyen mensajes, archivos, reuniones y otro contenido. Los datos empresariales también se cifran en reposo en los servicios de Microsoft para que las organizaciones puedan descifrar el contenido si es necesario, para cumplir con las obligaciones de seguridad y cumplimiento a través de métodos como eDiscovery. Para obtener más información sobre el cifrado en Microsoft 365, consulte [Cifrado en Microsoft 365](/microsoft-365/compliance/encryption)

Los flujos de datos TCP se cifran mediante TLS, y los protocolos de OAuth de servicio a servicio y MTLS proporcionan comunicaciones autenticadas de punto de conexión entre servicios, sistemas y clientes. Teams utiliza estos protocolos para crear una red de sistemas de confianza y garantizar que todas las comunicaciones en esa red estén cifradas.

En una conexión TLS, el cliente solicita un certificado válido del servidor. Para que sea válido, el certificado debe proceder de una entidad de certificación (CA) en la que también confíe el cliente y el nombre DNS del servidor debe coincidir con el nombre DNS del certificado. Si el certificado es válido, el cliente utiliza la clave pública del certificado para cifrar las claves de cifrado simétrico que se utilizarán en la comunicación. De esta manera, solo el propietario original del certificado puede utilizar la clave privada para descifrar los contenidos de la comunicación. La conexión resultante es de confianza y, a partir de ese momento, no es desafiada por ningún otro cliente ni servidor de confianza.

EL uso de TLS ayuda a evitar los ataques de interceptación y de intermediario. En los ataques de intermediario, el atacante desvía las comunicaciones entre dos entidades de red a través de su propio equipo sin que lo sepa ninguna de esas entidades. El protocolo TLS y los servidores que se indiquen en Teams como servidores de confianza mitigan el riesgo de un ataque de intermediario parcialmente en el nivel de la aplicación mediante un cifrado que se coordina para utilizar otro cifrado de claves públicas entre los dos puntos de conexión. Para que un atacante pudiera descifrar la comunicación, debería tener un certificado válido y de confianza, así como la clave privada correspondiente emitida a nombre del servicio con el que el cliente se esté comunicando.

#### <a name="encryption-in-teams-and-microsoft-365"></a>Cifrado en Teams y Microsoft 365

Hay varias capas de cifrado en funcionamiento dentro de Microsoft 365. El cifrado en Teams funciona con el resto del cifrado de Microsoft 365 para proteger el contenido de su organización. En este artículo se describen las tecnologías de cifrado específicas de Teams. Para obtener información general sobre el cifrado en Microsoft 365, consulte [Cifrado en Microsoft 365](/microsoft-365/compliance/encryption).

#### <a name="media-encryption"></a>Cifrado de medios

Los flujos de llamadas en Teams se basan en el modelo de oferta y respuesta [Session Description Protocol (SDP) RFC 8866](https://datatracker.ietf.org/doc/html/rfc8866) a través de HTTPS. Una vez que el destinatario acepta una llamada entrante, el autor de la llamada y el destinatario aceptan los parámetros de la sesión.

El tráfico de medios se cifra, y fluye entre el autor de la llamada y el destinatario utilizando RTP seguro (SRTP), que es un perfil de protocolo de transporte en tiempo real (RTP) que proporciona al tráfico RTP confidencialidad, autenticación y protección contra los ataques de reproducción. SRTP utiliza una clave de sesión creada con un generador de números aleatorios seguros y se intercambia mediante el canal de señalización TLS. En muchos casos, el tráfico multimedia de cliente a cliente se negocia a través de una señalización de conexión de cliente a servidor y se cifra con SRTP cuando se dirige directamente de cliente a cliente.

En los flujos de llamada normales, la negociación de la clave de cifrado se produce a través del canal de señalización de llamadas. En una llamada cifrada de un extremo a otro, el flujo de señalización es el mismo que en una llamada de Teams uno a uno normal. Sin embargo, Teams usa DTLS para derivar una clave de cifrado basada en certificados por llamada generados en ambos puntos de conexión de cliente. Dado que DTLS deriva la clave en función de los certificados de cliente, la clave es opaca para Microsoft. Una vez que ambos clientes están de acuerdo con la clave, el medio comienza a fluir mediante esta clave de cifrado negociada por DTLS a través de SRTP.

Para protegerse frente a un ataque de tipo intermediario entre el autor de la llamada y el destinatario, Teams deriva un código de seguridad de 20 dígitos de las huellas digitales SHA-256 de los certificados de llamada de punto de conexión del autor de la llamada y del destinatario. El autor de la llamada y el destinatario pueden validar los códigos de seguridad de 20 dígitos si se leen entre sí para ver si coinciden. Si los códigos no coinciden, un ataque de tipo intermediario interceptara la conexión entre el autor de la llamada y el destinatario. Si la llamada se ha puesto en peligro, los usuarios pueden finalizar la llamada manualmente.

Teams usa un token basado en credenciales para el acceso seguro a los relés multimedia mediante TURN. Los relés multimedia intercambian el token a través de un canal seguro de TLS.

### <a name="federal-information-processing-standard-fips"></a>Estándar federal de procesamiento de información (FIPS)

Teams usa algoritmos compatibles con FIPS para intercambios de clave de cifrado. Para obtener más información sobre la implementación de FIPS, vea la [publicación 140-2 de Estándares Federales de Procesamiento de la Información (FIPS)](/microsoft-365/compliance/offering-fips-140-2).

### <a name="user-and-client-authentication"></a>Autenticación de usuario y cliente

Un usuario de confianza es aquel cuyas credenciales se han autenticado mediante Azure AD en Office 365 o Microsoft 365.

La autenticación consiste en proporcionar credenciales de usuario a un servidor o servicio de confianza. Teams utiliza los siguientes protocolos de autenticación, según el estado y la ubicación del usuario.

- La **Autenticación moderna (MA)** consiste en la implementación por parte de Microsoft de OAUTH 2.0 para la comunicación de cliente a servidor. Ofrece características de seguridad, por ejemplo, Autenticación multifactor y Acceso condicional. Para poder usar MA, tanto el inquilino en línea como los clientes deben estar habilitados para MA. Los clientes de Teams entre equipos y dispositivos móviles, y el cliente web, [son compatibles con MA](./sign-in-teams.md).

> [!NOTE]
> Si necesita más información sobre la autenticación y los métodos de autorización de Azure AD, las secciones Introducción y "Aspectos básicos de la autenticación en Azure AD" de este artículo le serán útiles.

La autenticación de Teams se lleva a cabo mediante Azure AD y OAuth. El proceso de autenticación se puede simplificar de la manera siguiente:

- Inicio de sesión de usuario > emisión de tokens > la siguiente solicitud usa el token emitido.

Las solicitudes del cliente al servidor se autentican y autorizan por Azure AD con el uso de OAuth. Los usuarios con credenciales válidas emitidas por un socio federado son de confianza y pasan por el mismo proceso que los usuarios nativos. Sin embargo, los administradores pueden aplicar otras restricciones.

Para la autenticación multimedia, los protocolos ICE y TURN también usan el desafío de autenticación implícita que se describe en la RFC del IETF referente a TURN.

### <a name="windows-powershell-and-team-management-tools"></a>Herramientas de administración de Teams y Windows PowerShell

En Teams, los administradores de TI pueden administrar sus servicios a través del Centro de administración de Microsoft 365 o mediante el uso de Tenant Remote PowerShell (TRPS). Los administradores de inquilinos utilizan autenticación moderna para autenticarse en TRPS.

### <a name="configuring-access-to-teams-at-your-internet-boundary"></a>Configurar el acceso a Teams en su límite de Internet

Para que Teams funcione correctamente, por ejemplo, para que los usuarios puedan unirse a reuniones, los clientes deben configurar su acceso a Internet de modo que se permita el tráfico UDP y TCP saliente a los servicios en la nube de Teams. Para obtener más información, vea [direcciones URL de Office 365 e intervalos de direcciones IP](/office365/enterprise/urls-and-ip-address-ranges).

### <a name="udp-3478-3481-and-tcp-443"></a>UDP 3478-3481 y TCP 443

Los clientes usan los puertos UDP 3478 a 3481 y TCP 443 para solicitar el servicio audiovisual. Un cliente utiliza estos dos puertos para asignar puertos UDP y TCP, respectivamente, con el fin de permitir estos flujos multimedia. Los flujos multimedia en estos puertos se protegen con una clave que se intercambia a través de un canal de señalización protegida TLS.

### <a name="federation-safeguards-for-teams"></a>Protecciones de federación de Teams

La federación ofrece a su organización la posibilidad de comunicarse con otras organizaciones para compartir mensajería instantánea y presencia. En Teams, la federación está activada de forma predeterminada. Pero los administradores de inquilinos pueden controlar esta federación a través del Centro de administración de Microsoft 365.

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

Teams permite que los usuarios empresariales creen reuniones en tiempo real y se unan a ellas. Los usuarios empresariales también pueden invitar a usuarios externos que no tengan una cuenta de Azure AD, Microsoft 365 u Office 365 para que participen en estas reuniones. Los usuarios que son empleados de socios externos con una identidad segura y autenticada también pueden unirse a las reuniones y, si se les promueve para hacerlo, pueden actuar como moderadores. Los usuarios anónimos no pueden crear o unirse a una reunión como moderador, pero pueden ser promovidos a moderador después de unirse.

Para que los usuarios anónimos puedan unirse a las reuniones de Teams, debe estar activada la opción Participantes para reuniones en el Centro de administración de Teams.

> [!NOTE]
> El término *usuarios anónimos* significa que los usuarios no se autentican en el inquilino de la organización. En este contexto, todos los usuarios externos se consideran anónimos. Los usuarios autenticados pueden ser usuarios o invitados del inquilino.

Permitir que los usuarios externos participen en las reuniones de Teams puede ser útil, pero conlleva ciertos riesgos de seguridad. Para abordar estos riesgos, Teams usa las siguientes medidas de seguridad:

- Los roles de los participantes determinan los privilegios de control de la reunión.
- Los tipos de participante permiten limitar el acceso a reuniones específicas.
- La programación de reuniones está restringida a los usuarios que tienen una cuenta de AAD y una licencia de Teams.
- Los usuarios anónimos, es decir, que no están autenticados, que deseen unirse a una conferencia de acceso por marcado necesitan marcar uno de los números de acceso a la conferencia. Si la opción "Permitir siempre que los autores de llamadas eviten la sala de espera" está *activada*, también tendrán que esperar hasta que un moderador o usuario autenticado se una a la reunión.

  > [!CAUTION]
  > Si no quiere que los usuarios anónimos (usuarios que no invite explícitamente) se unan a una reunión, debe asegurarse de que **Usuarios anónimos pueden unirse a una reunión** esté configurado como **Desactivado** para la sección de reunión **Participantes**.

También es posible que un organizador establezca las opciones de configuración para permitir que los autores de llamadas de acceso por marcado sean los primeros en una reunión. Esta opción se establece en la configuración de conferencia de audio para los usuarios y se aplicará a todas las reuniones programadas por el usuario.

> [!NOTE]
> Para obtener más información sobre el acceso externo y de invitados en Teams, consulte este [artículo](./communicate-with-users-from-other-organizations.md). En él se explican las características que los usuarios externos o invitados pueden ver y usar cuando inician sesión en Teams. <p> Si está grabando reuniones y desea ver una matriz de permisos que tiene acceso al contenido, consulte [este artículo](./tmr-meeting-recording-change.md) y su matriz.

### <a name="participant-roles"></a>Roles de los participantes

Los participantes de la reunión se dividen en tres grupos, cada uno con sus propios privilegios y restricciones:

- **Organizador**: el usuario que crea una reunión, independientemente de si es improvisada o programada. Un organizador debe ser un usuario de cuenta empresarial autenticada y tener el control sobre todos los aspectos de usuario final de la reunión.
- **Moderador**: un usuario al que se autoriza la presentación de información durante una reunión con cualquier elemento multimedia admitido. El organizador de la reunión es, por definición, también un moderador y determina quién más puede serlo. Un organizador puede determinarlo cuando se programa una reunión o mientras se está llevando a cabo.
- **Asistente**: un usuario al que se le ha invitado a asistir a una reunión, pero que no está autorizado para actuar como moderador.

Un moderador también puede promover a un asistente al rol de moderador durante la reunión.

### <a name="participant-types"></a>Tipos de participantes

Los participantes en la reunión también se clasifican por ubicación y credenciales. Puede utilizar estas dos características para decidir qué usuarios pueden tener acceso a reuniones específicas. Los usuarios se pueden dividir de forma general en las siguientes categorías:

- **Usuarios que pertenecen al inquilino**. Estos usuarios tienen una credencial en Azure Active Directory para el inquilino.

    *Usuarios de mi organización*: estos usuarios tienen una credencial en Azure Active Directory para el inquilino. *Usuarios de mi organización* incluye cuentas de invitado.

    *Usuarios remotos*: estos usuarios se unen desde fuera de la red corporativa. Pueden incluir empleados que trabajan desde casa o mientras viajan, y otros, como empleados de proveedores de confianza, a quienes se les han otorgado credenciales empresariales por sus términos de servicio. Los usuarios remotos pueden crear reuniones y unirse a ellas, así como actuar como moderadores.

- **Usuarios que no pertenecen al inquilino**. Estos usuarios no tienen credenciales en Azure AD para el inquilino.

    *Usuarios federados*: los usuarios federados tienen credenciales válidas con asociados federados y, por lo tanto, se tratan como autenticadas por Teams, pero son externos al espacio empresarial del organizador de la reunión. Los usuarios federados pueden unirse a reuniones y ser promovidos a moderadores después de unirse a la reunión, pero no pueden crear reuniones en las empresas con las que se hayan federado.

    *Usuarios anónimos*: no tienen una identidad de Active Directory y no están federados con el inquilino.

En muchas reuniones se incluyen usuarios externos. Esos clientes también quieren confirmar la identidad de los usuarios externos antes de permitir que se unan a una reunión. En la siguiente sección, se describe cómo Teams limita el acceso a una reunión a los tipos de usuarios permitidos y requiere que todos los tipos de usuario presenten las *credenciales* adecuadas al entrar en una reunión.

### <a name="participant-admittance"></a>Admisión de participantes

> [!CAUTION]
> Si no quiere que los usuarios anónimos (usuarios que no invite explícitamente) se unan a una reunión, debe asegurarse de que **Usuarios anónimos pueden unirse a una reunión** esté configurado como **Desactivado** para la sección de reunión **Participantes**.

En Teams, los usuarios anónimos pueden transferirse a un área llamada sala de espera. A continuación, los moderadores pueden *admitir* a estos usuarios en la reunión o *rechazarlos*. Cuando estos usuarios se transfieren a la sala de espera, se notifica al moderador y a los asistentes, y los usuarios anónimos tienen que esperar hasta que se les acepte o rechace, o se agote el tiempo de espera de la conexión.

De forma predeterminada, los participantes que marcan para acceder desde RTC pasan directamente a la reunión cuando un usuario autenticado se une a ella, pero esta opción se puede cambiar para obligarlos a pasar a la sala de espera.

Los organizadores de la reunión controlan si los participantes pueden unirse a una reunión sin aguardar en la sala de espera. Cada reunión puede configurarse para permitir el acceso mediante cualquiera de los métodos siguientes:

Los valores predeterminados son:

- *Usuarios de mi organización*: todos los usuarios externos a la organización esperarán en la sala de espera hasta que se les admita.
- *Usuarios de mi organización y de organizaciones de confianza e invitados*: Los usuarios autenticados en la organización, incluidos los usuarios invitados y los usuarios de las organizaciones de confianza, pueden unirse a la reunión directamente sin tener que esperar en la sala de espera. Los usuarios anónimos esperan en la sala de espera.
- *Todos los usuarios*: todos los participantes de la reunión evitan la sala de espera cuando un usuario autenticado se une a la reunión.

### <a name="presenter-capabilities"></a>Capacidades del presentador

Los organizadores de la reunión controlan si los participantes pueden realizar presentaciones durante una reunión. Cada reunión puede configurarse para limitar los presentadores, según estas opciones:

- *Usuarios de mi organización*: todos los usuarios del inquilino, incluidos los invitados, pueden presentar contenido.
- *Usuarios de mi organización y de organizaciones de confianza*: todos los usuarios del inquilino, incluidos los invitados, pueden presentar contenido, y los usuarios externos de Teams y de dominios de Skype Empresarial que estén en la lista de permitidos de acceso externo pueden presentar contenido.  
- *Todos*: todos los participantes de la reunión son moderadores.

### <a name="modify-while-meeting-is-running"></a>Modificar mientras se lleva a cabo la reunión

Usted puede modificar las opciones de reunión mientras se celebra la reunión. El cambio, cuando se guarde, será significativo en la reunión en ejecución en cuestión de segundos. También afectará a las repeticiones futuras de la reunión.

## <a name="related-topics"></a>Temas relacionados

[Las 12 tareas principales de los equipos de seguridad para dar soporte al trabajo desde casa](/microsoft-365/security/top-security-tasks-for-remote-work)

[Centro de confianza de Microsoft](https://microsoft.com/trustcenter)

[Administrar la configuración de reuniones en Microsoft Teams](./meeting-settings-in-teams.md)

[Optimizar la conectividad de Microsoft 365 u Office 365 para usuarios remotos que usan túnel dividido de VPN](/Office365/Enterprise/office-365-vpn-split-tunnel)

- [Implementación del túnel dividido VPN](/Office365/Enterprise/office-365-vpn-implement-split-tunnel)

[Grabaciones de reuniones en Teams, donde se almacenan grabaciones, y quien puede acceder a ellas](./tmr-meeting-recording-change.md)
