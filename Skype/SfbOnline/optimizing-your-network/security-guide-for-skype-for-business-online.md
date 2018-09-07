---
title: Guía de seguridad para Skype Empresarial Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: ''
ms.date: 01/22/2018
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Skype for Business Online
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Security
description: Guía de seguridad para Skype Empresarial Online <add description>
ms.openlocfilehash: 646f4235a590532739ae4f06edeaf9c5a3070d5d
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23856777"
---
#  <a name="security-and-skype-for-business-online"></a>Seguridad y Skype para la empresa en línea

Skype Empresarial Online (SfBO, Skype for Business Online), como parte del servicio Office 365, sigue las mejores prácticas y procedimientos de seguridad, como la seguridad de nivel de servicio a través de la "defensa en profundidad", los controles de cliente en el servicio, el reforzamiento de la seguridad y las mejores prácticas operativas.  Si quiere información detallada, consulte el Centro de confianza de Office 365 (https://products.office.com/en-us/business/office-365-trust-center-security).

## <a name="trustworthy-by-design"></a>Fiabilidad basada en el diseño
Skype Empresarial Online está diseñado y desarrollado conforme al ciclo de vida de desarrollo de seguridad (SDL, Security Development Lifecycle) de Trustworthy Computing de Microsoft, que se describe en https://www.microsoft.com/en-us/sdl/default.aspx. El primer paso para crear un sistema de comunicaciones unificadas más seguro fue diseñar modelos de amenazas y probar cada característica tal como se diseñó. Se incorporaron muchas mejoras relacionadas con la seguridad, tanto al proceso como a las prácticas de codificación. Las herramientas de tiempo de compilación detectan excesos de almacenaje y otras amenazas de seguridad antes de que el código se incorpore al producto final. Obviamente, es imposible realizar diseños contra amenazas de seguridad desconocidas. Ningún sistema puede garantizar la seguridad total. Sin embargo, como el desarrollo del producto se basó en principios de diseño seguro desde el inicio, Skype Empresarial Online cuenta con tecnologías de seguridad estándar del sector como parte fundamental de su infraestructura. 

## <a name="trustworthy-by-default"></a>Confiable de forma predeterminada
En Skype Empresarial Online, las redes de comunicación están encriptadas de forma predeterminada. Al requerir que todos los servidores para usar certificados y mediante el uso de OAUTH, TLS, seguro protocolo de transporte en tiempo real (SRTP) y otras técnicas de cifrado estándar del sector, como el cifrado de 256 bits estándar de cifrado avanzado (AES), todos los Skype para la empresa Datos en línea está protegidos en la red.

## <a name="how-sfbo-handles-common-security-threats"></a>¿Cómo gestiona SfBO las amenazas comunes de seguridad?
Esta sección identifica las amenazas de seguridad más comunes del servicio SfBO y la forma en que Microsoft minimiza cada amenaza.

### <a name="compromised-key-attack"></a>Ataque de clave comprometida
Una clave es un código o número secreto que se usa para cifrar, descifrar o comprobar información secreta. Existen dos claves importantes en uso en la infraestructura de clave pública (PKI, Public Key Infrastructure) que deben ser consideradas: la clave privada que tiene cada titular de certificado y la clave de sesión, que se utiliza después de una identificación exitosa y de un intercambio de claves de sesión entre las partes que se estén comunicando.  Un ataque de clave comprometida se produce cuando el atacante consigue la clave privada o de sesión. Cuando el atacante consigue la clave, puede usarla para descifrar datos cifrados sin que el remitente lo sepa.

Skype para profesionales Online usa las características PKI en el sistema operativo Windows Server para proteger los datos de clave utilizados para el cifrado para las conexiones de seguridad de capa de transporte (TLS). Las teclas usadas para cifrar los datos multimedia se intercambian a través de las conexiones TLS. 

### <a name="network-denial-of-service-attack"></a>Ataque por denegación de servicio de la red
El ataque por denegación de servicio se produce cuando el atacante impide que los usuarios válidos usen la red de forma normal. Mediante el uso de un ataque por denegación de servicio, el atacante puede:
- Enviar datos no válidos a las aplicaciones y los servicios que se ejecutan en la red que sufre el ataque para interrumpir su funcionamiento normal.
- Enviar una gran cantidad de tráfico, lo que sobrecarga el sistema hasta que deja de responder o responde lentamente a las solicitudes legítimas.
- Ocultar las pruebas de los ataques.
- Impedir que los usuarios obtengan acceso a los recursos de la red.

SfBO ofrece protección frente a estos ataques mediante la ejecución de la protección de red Azure DDOS y limitando las solicitudes de los clientes desde los mismos extremos, subredes y entidades federadas.

### <a name="eavesdropping"></a>Interceptación
La interceptación se produce cuando un atacante obtiene acceso a la ruta de datos en una red y puede supervisar y leer el tráfico. Este tipo de ataque también se denomina rastreo o espionaje. Si el tráfico se produce como texto sin formato, el atacante puede leerlo cuando obtiene acceso a la ruta. Un ejemplo es un ataque que se realiza al controlar un enrutador de la ruta de acceso a los datos. 

SfBO utiliza TLS mutua (MTLS) para las comunicaciones del servidor en O365 y TLS de los clientes al servicio. Esto lo convierte en un ataque muy difícil o imposible de llevar a cabo en el período de tiempo en el que puede atacarse una conversación determinada. TLS autentica a todos los participantes y cifra todo el tráfico. Esto no impide la interceptación, pero el atacante no puede leer el tráfico a menos se interrumpa el cifrado.

El protocolo TURN se usa para lograr objetivos relacionados con elementos multimedia en tiempo real.  El protocolo de activar no exigir la aplicación de que se pueden cifrar el tráfico y la información que está enviando está protegida por la integridad de los mensajes. Aunque es open interceptación, la información está enviando (es decir, las direcciones IP y puerto) que pueden extraerse directamente observando simplemente las direcciones de origen y de destino de los paquetes. El servicio SfBO se asegura de que los datos son válidos mediante la comprobación de la integridad de los mensajes del mensaje mediante la clave derivada de unos elementos incluidos una contraseña activar, que nunca se envía en texto no cifrado. SRTP (Secure Real-Time Transport Protocol) se utiliza para el tráfico de elementos multimedia y también está encriptado.

### <a name="identity-spoofing-ip-address-spoofing"></a>Suplantación de identidad (suplantación de dirección IP)
La suplantación de identidad (spoofing) se produce cuando el atacante identifica y usa una dirección IP de una red, un equipo o un componente de red sin tener autorización para ello. En este tipo de ataque, el atacante actúa como si fuese la entidad que hubiera identificado la dirección IP en un caso normal. En el contexto de Microsoft Lync Server 2010, esta situación puede producirse únicamente si un administrador ha realizado estas dos de las siguientes opciones:
- Ha configurado conexiones compatibles únicamente con el Protocolo de control de transmisión (TCP) (lo cual no se recomienda porque las comunicaciones TCP no están cifradas).
- Ha marcado las direcciones IP de esas conexiones como hosts de confianza. 

Este es un problema menor para las conexiones TLS (Seguridad de la capa de transporte), puesto que TLS autentica todas las partes y cifra todo el tráfico. El uso de TLS evita que un atacante suplante las direcciones IP en una conexión concreta (por ejemplo, conexiones Mutual TLS). Pero un atacante aún podría suplantar la dirección del servidor DNS que usa SfBO. Sin embargo, debido a que se realiza la autenticación en SfBO con certificados, un atacante no tiene un certificado válido necesario para la suplantación de una de las partes en la comunicación.

### <a name="man-in-the-middle-attack"></a>Ataque de tipo "Man in the middle"
Un ataque de tipo "Man in the middle" se produce cuando un atacante desvía la comunicación entre dos usuarios a través del equipo del atacante sin que lo sepan esos dos usuarios. El atacante puede supervisar y leer el tráfico antes de enviarlo al destinatario previsto. Sin darse cuenta, todos los usuarios que participan en la comunicación envían tráfico al atacante y reciben tráfico del mismo pensando que la comunicación se produce únicamente con el usuario previsto. Esto puede suceder si un atacante modifica los Servicios de dominio de Active Directory para agregar su servidor como un servidor de confianza o modifica el Sistema de nombres de dominio (DNS) para que los clientes se conecten al servidor a través del atacante. 

También se puede producir un ataque "Man in the middle" con tráfico de elementos multimedia entre dos clientes, excepto que en SfBO las transmisiones de uso compartido y punto a punto de audio, video y aplicaciones se encriptan con SRTP, usando claves criptográficas que se negocian entre pares empleando el protocolo de inicio de sesión (SIP, Session Initiation Protocol) sobre TLS. 

### <a name="rtp-replay-attack"></a>Ataque de reproducción RTP
Un ataque de reproducción tiene lugar cuando una transmisión de medios válida entre dos partes se intercepta y retransmite con fines malintencionados. SfBO usa SRTP junto con un protocolo de señalización seguro que protege las transmisiones de los ataques de reproducción habilitando el receptor de mantener un índice de los paquetes RTP ya recibidos y comparar cada paquete nuevo con esos ya enumerados en el índice.

### <a name="spim"></a>Mensajes instantáneos no deseados
El término inglés "spim" hace referencia a los mensajes instantáneos comerciales no deseados o a las solicitudes de suscripción de presencia no deseadas. Si bien estos mensajes por sí mismos no son un peligro para la seguridad de la red, son como mínimo molestos, pueden reducir la disponibilidad y la productividad de los recursos, y podrían llegar a poner en peligro la red. Un ejemplo de ello es el caso de usuarios que se envían solicitudes no deseadas entre sí. Los usuarios pueden bloquearse entre sí para evitarlo, pero con la federación, si se establece un ataque coordinado de este tipo, puede ser difícil de solucionar a menos que se deshabilite la federación para el asociado.

### <a name="viruses-and-worms"></a>Virus y gusanos
Un virus es una unidad de código que tiene por objeto reproducir más unidades de código similares. Los virus necesitan un host, como un archivo, un correo electrónico o un programa, para poder funcionar. Al igual que un virus, un gusano es una unidad de código que está codificada para reproducir unidades de código adicionales similares, pero que, a diferencia de un virus, no necesita un host. Los virus y los gusanos suelen aparecer principalmente durante las transferencias de archivo entre clientes o cuando otros usuarios envían direcciones URL. Si hay un virus en su equipo, podrá, por ejemplo, usar su identidad y enviar mensajes instantáneos en su nombre.  Las medidas estándar de seguridad de cliente como los análisis periódicos en busca de virus pueden mitigar este problema.  

## <a name="personally-identifiable-information"></a>Información de identificación personal
SfBO tiene divulgar información a través de una red pública, que es posible que pueda vincularse a un individuo. Dicha información se puede desglosar en dos categorías:
- **Datos de presencia mejorada**&nbsp;&nbsp;&nbsp;datos de presencia mejorada están información que un usuario puede elegir para compartir o no a través de un vínculo a un socio federado o con los contactos dentro de una organización. Estos datos no se comparten con los usuarios de una red de mensajería instantánea pública. Las directivas de cliente y otras opciones de configuración del cliente pueden otorgar algún tipo de control al administrador del sistema. En el servicio SfBO, se puede configurar el modo de privacidad de presencia ampliada para que un usuario individual evitar que los usuarios de SfBO no en la lista de contactos del usuario no pueden ver información de presencia del usuario. 
- **Datos obligatorios**&nbsp;&nbsp;&nbsp;Los datos obligatorios son datos que se requieren para el correcto funcionamiento del servidor o del cliente. Se trata de información que es necesaria en un servidor o una red para el enrutamiento, el mantenimiento de estados y la señalización.
Las siguientes tablas enumeran los datos que se requieren para que SfBO funcione.

***Tabla 1: datos de presencia mejorados***

<!--start table here -->

||||
|:-----|:-----|:-----|
|**Datos**|**Configuración** **posible**|
|Datos personales |Nombre, puesto, compañía, dirección de correo electrónico, zona horaria|
|Números de teléfono|Trabajo, Móvil, Particular|
|Información de calendario|Información de disponibilidad, aviso de fuera, detalles (para los usuarios que tengan acceso a su calendario) de la reunión| 
|Estado de presencia|Ausente, Disponible, No disponible, No molestar, No conectado|
|||||

<!-- end of table -->

***Tabla 2: datos obligatorios***

<!--start table here -->

||||
|:-----|:-----|:-----|
|**Categoría** |**Valores posibles** |
|Dirección IP|Dirección real del equipo o dirección traducida|
|URI del SIP|<u>david.campbell@contoso.com</u>|
|Nombre|David Campbell (tal y como se define en los servicios de dominio de Active Directory)|
|||||

<!-- end of table -->

## <a name="security-framework-for-sfbo"></a>Marco de seguridad para SfBO
En esta sección se proporciona una visión general de los elementos fundamentales que constituyen el marco de seguridad de Microsoft SfBO. Dichos elementos son los siguientes:
- Azure Active Directory (AAD) proporciona un único depósito de back-end de confianza para cuentas de usuario. 
- Infraestructura de clave pública (PKI) utiliza certificados emitidos por entidades de certificación de confianza (CA) para autenticar los servidores y garantizar la integridad de los datos.
- La Seguridad de la capa de transporte (TLS), HTTPS sobre SSL (HTTPS) y Mutual TLS (MTLS) permiten la autenticación de los extremos y el cifrado de la mensajería instantánea. Audio de punto a punto, vídeo y uso compartido de secuencias de aplicaciones se cifran y ha comprobado su integridad con protocolo seguro de transporte en tiempo real (SRTP).
- Para la autenticación del usuario se usan los protocolos estándar de la industria, siempre que sea posible.

En los temas de esta sección se describen cómo funciona cada uno de estos elementos fundamentales para mejorar la seguridad del servicio de SfBO.

### <a name="azure-active-directory"></a>Azure Active Directory
Azure Active Directory funciona como el servicio de directorio para O365. Almacena toda la información de directorio de usuario y las asignaciones de directivas. 

### <a name="public-key-infrastructure-for-sfbo"></a>Infraestructura de clave pública para SfBO
Servicio de SfBO se basa en certificados para la autenticación de servidor y para establecer una cadena de confianza entre los clientes y servidores y entre las distintas funciones de servidor. La infraestructura de claves públicas (PKI, Public Key Infrastructure) de Windows Server proporciona la infraestructura para establecer y validar esta cadena de confianza.
Los certificados son identificadores digitales. Identifican un servidor por nombre y especifican sus propiedades. Para asegurarse de que la información de un certificado es válida, el certificado debe ser emitido por una entidad de certificación (CA) que es de confianza clientes u otros servidores que se conectan al servidor. Si el servidor se conecta únicamente a otros clientes y servidores de una red privada, la CA puede ser una CA de empresa. Si el servidor interactúa con entidades ubicadas fuera de la red privada, es posible que se requiera una CA pública.

Incluso si la información incluida en el certificado es válida, es preciso comprobar de alguna manera que el servidor que presenta el certificado es realmente el servidor representado por el certificado. Ahí es donde entra en juego la PKI de Windows.
Cada certificado está asociado a una clave pública. El servidor indicado en el certificado tiene una clave privada correspondiente que solo él conoce. El cliente o servidor que se conecta usa la clave pública para cifrar un fragmento de información aleatorio y enviarlo al servidor. Si el servidor descifra la información y la devuelve como texto sin formato, la entidad que se conecta puede estar segura de que el servidor tiene la clave privada asociada al certificado y, por consiguiente, es el servidor indicado en el certificado.

#### <a name="crl-distribution-points"></a>Puntos de distribución CRL
SfBO requiere que todos los certificados de servidor para contener uno o varios puntos de distribución de lista de revocación de certificados (CRL). Los puntos de distribución CRL (CDP) son ubicaciones desde las que se pueden descargar CRL para comprobar si un certificado no ha sido revocado después de su emisión y todavía se encuentra dentro del período de validez. Un punto de distribución CRL se anota en las propiedades del certificado como una dirección URL y es HTTP seguro.  El servicio SfBO comprueba CRL con cada autenticación de certificado.

#### <a name="enhanced-key-usage"></a>Uso mejorado de clave
Los componentes del servicio SfBO requieren que los certificados de servidor sean compatibles con el uso mejorado de clave (EKU, Enhanced Key Usage) para la autenticación del servidor. La configuración del campo EKU para la autenticación de los servidores significa que el certificado es válido para la autenticación de los servidores. Este EKU es esencial para MTLS. 

### <a name="tls-and-mtls-for-sfbo"></a>TLS y MTLS para SfBO
Los protocolos MTLS y TLS proporcionan comunicaciones cifradas y autenticación de los extremos en Internet. SfBO utiliza estos dos protocolos para crear una red de servidores de confianza y para asegurarse de que se cifran todas las comunicaciones a través de esa red. Todas las comunicaciones SIP entre los servidores se llevan a cabo a través de MTLS. Las comunicaciones SIP entre el cliente y el servidor se realizan a través de TLS.

TLS permite a los usuarios, mediante su software cliente, autenticar los servidores SfBO a los que se conectan. En una conexión TLS, el cliente solicita un certificado válido del servidor. Para que sea válido, el certificado debe haber sido emitido por una CA que también sea de confianza para el cliente y el nombre DNS del servidor debe coincidir con el nombre DNS del certificado. Si el certificado es válido, el cliente usa la clave pública del certificado para cifrar las claves de cifrado simétricas que se utilizarán para la comunicación, de modo que solo el propietario original del certificado puede usar su clave privada para descifrar el contenido de la comunicación. La conexión resultante es fiable y desde ese punto no es desafiada por otros servidores o clientes fiables. En este contexto, SSL, tal como se usa con los servicios web, se puede asociar como basada en TLS.

Las conexiones de servidor a servidor se basan en TLS mutua (MTLS) para autenticación mutua. En una conexión MTLS, el servidor de origen de un mensaje y el que lo recibe intercambian certificados procedentes de una CA de confianza para ambos. Los certificados permiten a los servidores demostrarse mutuamente sus identidades. El servicio SfBO sigue este procedimiento.

TLS y MTLS ayudan a evitar los ataques de interceptación y de tipo "Man in the middle". En los ataques de tipo "Man in the middle", el atacante enruta las comunicaciones entre dos entidades de red a través del equipo del atacante sin que lo sepa ninguna de esas entidades. TLS y especificación del SfBO de servidores de confianza mitigan el riesgo de un ataque intermedio man in the parcialmente en el nivel de aplicación mediante el cifrado de extremo a extremo coordinado el uso de la criptografía de clave pública entre los dos extremos, y un atacante tendría que tener un certificado válido y de confianza con la privada correspondiente clave y emitido para el nombre del servicio a la que se está comunicando el cliente para descifrar la comunicación. 

### <a name="encryption-for-sfbo"></a>Encriptación para SfBO
SfBO usa TLS y MTLS para cifrar los mensajes instantáneos. Todo el tráfico de servidor a servidor requiere MTLS, independientemente de si el tráfico se limita a la red interna o de si cruza el perímetro de la red interna.

La siguiente tabla resume el protocolo utilizado por SfBO.

***Tabla 3: protección de tráfico***

<!--start table here with header -->


|||
|:-----|:-----|
|**Tipo de tráfico**|**Protegido por**|
|Servidor a servidor|MTLS|
|Cliente a servidor|TLS|
|Mensajería instantánea y presencia|TLS (si está configurado para TLS)|
|Audio, vídeo y uso compartido de escritorio|SRTP|
|Uso compartido de escritorio (señalización)|TLS|
|Conferencia web|TLS|
|Descarga del contenido de las reuniones, descarga de la libreta de direcciones y expansión de grupos de distribución|HTTPS|
|||

<!-- end of table -->

#### <a name="media-encryption"></a>Cifrado de medios
El tráfico de medios se cifra mediante RTP seguro (SRTP), que es un perfil de protocolo de transporte en tiempo real (RTP) que proporciona al tráfico RTP confidencialidad, autenticación y protección contra los ataques de reproducción. SRTP utiliza una clave de sesión creada con un generador de números aleatorios seguros y se intercambia mediante el canal de señalización TLS. Además, los medios que fluyen en ambas direcciones entre el servidor de mediación y el servidor interno del próximo salto también se cifran mediante SRTP. 

SfBO genera nombres de usuario/contraseñas para acceder de forma segura a relés multimedia mediante TURN. Los relés multimedia intercambian el nombre de usuario/contraseña a través de un canal SIP protegido con TLS.

#### <a name="fips"></a>FIPS
SfBO utiliza algoritmos compatibles con FIPS para intercambiar claves de cifrado. 

### <a name="user-and-client-authentication"></a>Autenticación de usuario y cliente 
Un usuario confianza es aquel cuyas credenciales se han autenticado por AAD en O365. 

La autenticación es el suministro de credenciales de usuario a un servidor de confianza o servicio. SfBO utiliza los siguientes protocolos de autenticación, según el estado y la ubicación del usuario.
- La **autenticación moderna** consiste en la implementación de Microsoft de OAUTH 2.0 para la comunicación de cliente a servidor. Ofrece características de seguridad, por ejemplo, autenticación basada en certificados O365, autenticación multifactor O365 y acceso condicional O365.  Para usar la autenticación moderna, tanto el inquilino en línea como los clientes deben tener habilitada la MA.  Los inquilinos de SfBO creados después de mayo de 2017 tienen la MA habilitada por defecto.  Siga las instrucciones aquí incluidas para habilitar la MA de los inquilinos creados antes de esa fecha.  Los siguientes clientes son compatibles con MA: cliente de Skype Empresarial 2015 o 2016, Skype Empresarial para Mac, cliente de Lync 2013, teléfonos IP 3PIP, iOS y Android. 
- Cuando la autenticación moderna no está habilitada (o no está disponible) se usa **ID de organización**.
- **Protocolo de autenticación** implícita para los usuarios denominados anónimos. Los usuarios anónimos son usuarios externos que no tienen credenciales de Active Directory reconocidas, pero que han recibido una invitación a una conferencia local y tienen una clave de conferencia válida. La autenticación implícita no se utiliza para otras interacciones del cliente.

Autenticación de SfBO consta de dos fases:
1. Se establece una asociación de seguridad entre el cliente y el servidor.
2. El cliente y el servidor utilizan la asociación de seguridad existente para firmar los mensajes que envían y comprobar los que reciben. Cuando la autenticación está habilitada en el servidor, no se aceptan los mensajes no autenticados de un cliente.

La confianza en un usuario se adjunta a cada mensaje que procede del usuario, no a la identidad del usuario. El servidor comprueba cada mensaje para determinar si las credenciales de usuario son válidas. Si las credenciales del usuario son válidas, el mensaje es no representan ningún riesgo no sólo por el primer servidor en recibir pero por todos los demás servidores de SfBO.

Los usuarios con credenciales válidas emitidas por un socio federado son de confianza pero, de manera opcional, algunas restricciones adicionales impiden que disfruten de todos los privilegios otorgados a los usuarios internos.

Para la autenticación de medios, los protocolos ICE y TURN también usar el desafío de autenticación implícita, tal como se describe en la RFC de IETF activar. Para más obtener más información, consulte [recorrido de elementos multimedia](#external-user-av-traffic-traversal).

Certificados de cliente proporcionan un método alternativo para los usuarios se autentiquen mediante SFBO. En vez de proporcionar un nombre de usuario y una contraseña, los usuarios cuentan con un certificado y una clave privada correspondiente al certificado necesario para resolver un desafío criptográfico. 

### <a name="windows-powershell-and-sfbo-management-tools"></a>Herramientas de administración de Windows PowerShell y SfBO
En SfBO, los administradores de TI pueden administrar sus servicios a través del portal de administración de O365 o mediante el uso de Tenant Remote PowerShell (TRPS).  Los administradores de inquilinos usan la autenticación moderna para autenticarse en TRPS.

### <a name="configuring-access-to-sfbo-at-your-internet-boundary"></a>Configurar el acceso a SfBO en su límite de Internet
Se permite para que SfBO funcione correctamente la necesidad de los clientes (los usuarios pueden unirse a reuniones, etc.), para configurar su acceso a internet de manera que el tráfico saliente UDP y TCP a los servicios en el SfBO en la nube.  Para obtener más información, vea:https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_lyo 

### <a name="udp-3478-3481-and-tcp-443"></a>UDP 3478-3481 y TCP 443

Los clientes usan los puertos UDP 3478-3481 y TCP 443 para solicitar el servicio A/V Edge. El cliente utiliza estos dos puertos para asignar puertos UDP y TCP, respectivamente, para que la ubicación remota se conecte a ellos. Para acceder al servicio A/V Edge, el cliente, primero, debe haber establecido una sesión de señalización SIP autenticada con el registrador SfBO para obtener credenciales de autenticación del servicio A/V Edge. Estos valores se envían a través del canal de señalización protegido con TLS y se generan por ordenador para reducir el riesgo de ataques de diccionario. Los clientes pueden usar estas credenciales para la autenticación de texto implícita con el servicio A/V Edge para asignar puertos al objeto de usarlos en una sesión de elementos multimedia. El cliente envía una solicitud de asignación inicial y es respondido con un mensaje 401 nonce/desafío por parte del servicio A/V Edge. El cliente envía una segunda asignación que contiene el nombre de usuario y un código hash de autenticación de mensaje hash (HMAC), hash del nombre de usuario y nonce. 

También existe un mecanismo de número de secuencia para prevenir ataques de repetición. El servidor calcula el HMAC previsto en función de su propia información sobre el nombre de usuario y la contraseña. Si los valores HMAC coinciden, se realiza el procedimiento de asignación. De lo contrario, el paquete se descarta. Este mecanismo HMAC también se aplica a mensajes posteriores en la misma sesión de llamada. Este nombre de usuario/contraseña tiene una duración máxima de ocho horas, momento en el que el cliente vuelve a adquirir un nuevo nombre de usuario/contraseña para llamadas posteriores.

### <a name="udptcp-50000-59999"></a>UDP/TCP 50 000-59 999
Se utiliza TCP 50 000 de salida para SfBO para compartir aplicaciones y escritorios y transferencia de archivos. Los rangos de puertos UDP/TCP 50 000-59 999 se utilizan para sesiones de elementos multimedia con socios de Microsoft Office Communications Server 2007 que requieren el servicio NAT/cortafuegos transversal desde el servicio A/V Edge. Debido a que el servicio A/V Edge es el único proceso que utiliza estos puertos, el tamaño del rango del puerto no indica la posible superficie de ataque. Una buena práctica de seguridad es minimizar siempre el número total de puertos de escucha; se consigue no ejecutando servicios de red innecesarios. Si un servicio de red no está en ejecución, un atacante remoto no lo puede aprovechar y la superficie de ataque del sistema host se reduce. Sin embargo, en un solo servicio, reducir el número de puertos no proporciona la misma ventaja. El software de servicio A/V Edge no está más expuesto al ataque con 10 000 puertos abiertos que con 10. La asignación de puertos en este rango se realiza al azar y los puertos que no están asignados en ese momento no están a la escucha de paquetes.
 
### <a name="external-user-av-traffic-traversal"></a>Transversal de tráfico A/V de usuario externo
La habilitación de usuarios externos y usuarios internos para intercambiar elementos multimedia requiere un servicio perimetral de acceso para administrar la señalización SIP necesaria para configurar y anular una sesión. También requiere un servicio perimetral A/V que actúe como relé para la transferencia de los elementos multimedia. La secuencia de llamadas se muestra en la figura siguiente.


![Secuencia de llamadas para unirse a la reunión](media/sfbo-call-sequence-security.png) 

1. Un usuario recibe un correo electrónico que contiene una invitación para unirse a una reunión de SfBO. El correo electrónico contiene una clave de conferencia y una URL basada en HTTP vinculada a la conferencia. Tanto la clave como la URL son únicas para una reunión determinada.<p>El usuario inicia el procedimiento para unirse haciendo clic en la URL de la reunión del correo electrónico, que inicia un proceso de detección de cliente en el equipo del usuario.  Si se detecta al cliente, se inicia.  Si no se detecta, el usuario es redirigido al cliente web.<p/>
2. El cliente SfBO envía un SIP INVITE que contiene las credenciales del usuario. Un usuario federado o remoto se une a una conferencia utilizando sus credenciales de empresa. Para un usuario federado, SIP INVITE se envía primero a su servidor principal, que autentica al usuario y reenvía el INVITE a SfBO. Se requiere que un usuario anónimo supere la autenticación de texto implícita.<p>SfBO autentica al usuario remoto o anónimo y lo notifica al cliente. Como se ha indicado en el paso 2, los usuarios federados que se unen a una conferencia son autenticados por su empresa.<p/>

3. El cliente envía una solicitud INFO para agregar al usuario a la conferencia A/V.

    Las conferencias A/V envían una respuesta Agregar usuario que contiene el token para presentar al servicio perimetral de conferencia A/V, entre otra información.

    [Nota]  Todo el tráfico SIP anterior anteriormente indicado fluye a través del servicio de servidor perimetral de acceso.

    El cliente se conecta al servidor de conferencia A/V, que valida el token y transmite la solicitud (que contiene otro token de autorización) al servidor de conferencia A/V interno. El servidor de conferencia A/V valida el token de autorización que emitió originalmente mediante el canal SIP para garantizar que un usuario válido se une a la conferencia.
    
4. Entre el cliente y el servidor de conferencia AV, se negocia y configura una conexión de elementos multimedia mediante SRTP.
5. Un usuario recibe un correo electrónico que contiene una invitación para unirse a una reunión de SfBO. El correo electrónico contiene una clave de conferencia y una URL basada en HTTP vinculada a la conferencia. Tanto la clave como la URL son únicas para una reunión determinada.

### <a name="federation-safeguards-for-sfbo"></a>Garantías de la federación para SfBO
La federación permite que su organización se comunique con otras organizaciones para compartir presencia y mensajería instantánea. En SfBO, la federación está activada de forma predeterminada.  Sin embargo, los administradores de inquilinos pueden controlarla mediante el portal de administración de O365.  Más información.

## <a name="addressing-threats-to-sfbo-conferences"></a>Atajar amenazas a las conferencias de SfBO

SfBO permite que los usuarios empresariales creen y se unan a conferencias web en tiempo real. Los usuarios empresariales también pueden invitar a participar en estas reuniones a usuarios externos que no tengan una cuenta de AAD/O365. Los usuarios que son empleados de socios federados con una identidad segura y autenticada también pueden unirse a las reuniones y, si se les promociona para hacerlo, pueden actuar como presentadores. Los usuarios anónimos no pueden crear una reunión ni unirse a ella como presentadores, pero pueden ser promocionados a presentador una vez que se hayan unido.

Permitir que usuarios externos participen en las reuniones de SfBO aumenta considerablemente el valor de esta función, pero también implica algunos riesgos de seguridad. Para atajar estos riesgos, SfBO proporciona las siguientes garantías adicionales:
- Los roles de los participantes determinan los privilegios de control de la conferencia.
- Los tipos de participantes le permiten limitar el acceso a reuniones específicas.
- Los tipos de reunión definidos determinan qué tipos de participantes pueden asistir.
- La programación de la conferencia está restringida a los usuarios que tienen una cuenta de AAD y una licencia de SfBO.
- Anónimo, es decir, no autenticado, los usuarios que deseen marcado de conferencia unirse a una conferencia de uno de la conferencia a números de acceso y, a continuación, se les pide que escriba el identificador de conferencia. A los usuarios anónimos sin autenticar también se les pide que registren su nombre. El nombre grabado identifica a los usuarios sin autenticar en la conferencia. No se admiten usuarios anónimos en la conferencia hasta que se haya unido a ella al menos un coordinador o un usuario autenticado, y no se les puede asignar un rol definido previamente.

### <a name="participant-roles"></a>Roles de los participantes
Los participantes de la reunión se dividen en tres grupos, cada uno con sus propios privilegios y restricciones:
- **Organizador** &nbsp; &nbsp; El usuario que crea una reunión, si improvisada o programada. Un organizador debe ser un usuario empresarial autenticado y tener control sobre todos los aspectos del usuario final de una reunión.
- **Moderador** &nbsp; &nbsp; Un usuario que está autorizado para presentar información en una reunión, utilizando es compatible con independencia de los medios. Un organizador de reunión es, por definición, también un presentador y determina quién más puede ser un presentador. Un organizador puede determinar esto al programar la reunión o mientras la reunión está en curso.
- **ATTENDEE** &nbsp; &nbsp; Un usuario que ha sido invitado a asistir a una reunión pero que no está autorizado para actuar como moderador.

Un presentador también puede promocionar a un asistente al rol de presentador durante la reunión.

### <a name="participant-types"></a>Tipos de participantes

Los participantes en la reunión también se clasifican por ubicación y credenciales. Puede utilizar estas dos características para especificar qué usuarios pueden tener acceso a reuniones específicas. Los usuarios se pueden dividir, en términos generales, en las siguientes categorías:
1.  **Usuarios que pertenecen al inquilino**&nbsp;&nbsp;Estos usuarios tienen una credencial en Azure Active Directory para el inquilino.<br/>
    a. *Dentro de corpnet* – se une estos usuarios desde dentro de la red corporativa.<br/>b. *Los usuarios remotos* , estos usuarios se une a desde fuera de la red corporativa. Pueden incluir empleados que trabajan desde casa o mientras viajan, y otros, como empleados de proveedores de confianza, a quienes se les han otorgado credenciales empresariales por sus términos de servicio. Los usuarios remotos pueden crear y unirse a conferencias y actuar como presentadores.
2.  **Usuarios que no pertenecen al inquilino**&nbsp;&nbsp;Estos usuarios no tienen una credencial en Azure Active Directory para el inquilino.<br/>a. *Los usuarios federados* - los usuarios federados tienen credenciales válidas con socios federados y, por tanto, se tratan como autenticados por SFBO. Los usuarios federados pueden unirse a conferencias y ser promocionados a presentadores una vez que se hayan unido a la reunión, pero no pueden crear conferencias en las empresas en las que están federados.<br/>b. *Los usuarios anónimos* - los usuarios anónimos no tienen una identidad de Active Directory y no son contactos asociados externos con el inquilino. 

Los datos del cliente muestran que muchas conferencias involucran usuarios externos. Esos clientes también quieren confirmar la identidad de los usuarios externos antes de permitir que se unan a una conferencia. Como se describe en la siguiente sección, SfBO limita el acceso a la reunión a los tipos de usuarios permitidos y requiere que todos los tipos de usuario presenten las credenciales adecuadas al entrar en una reunión.

### <a name="participant-admittance"></a>Admisión de los participantes
En SfBO, los usuarios anónimos se transfieren a un área llamada sala de espera. A continuación, los presentadores pueden admitir a estos usuarios en la reunión o rechazarlos. Estos usuarios son transferidos a la sala de espera, el líder es informado, y a continuación esperan a que un líder los acepte o rechace o hasta que su conexión caduque. Mientras están en la sala de espera escuchan música. 

De forma predeterminada, los participantes que llaman desde la PSTN pasan directamente a la reunión, pero esta opción se puede cambiar para obligarlos a ir a la sala de espera.  
Los organizadores de la reunión controlan si los participantes pueden unirse a una reunión sin aguardar en la sala de espera. Cada reunión puede configurarse para permitir el acceso mediante cualquiera de los métodos siguientes:
- **Solo yo, el organizador de la reunión**&nbsp;&nbsp;Todos, excepto el organizador, deben aguardar en la sala de espera hasta a ser admitidos.
- **Personas a las que invito de mi empresa**&nbsp;&nbsp;Cualquier persona de su empresa puede entrar a la reunión directamente, incluso si no está invitado.
- **Cualquier persona de mi empresa**&nbsp;&nbsp;Todos los usuarios de SfBO de la cuenta empresarial de O365 pueden unirse a la reunión sin aguardar en la sala de espera, incluso si no están en la lista de distribución. El resto, incluidos todos los usuarios externos y anónimos, deben aguardar en la sala de espera hasta ser admitidos.
- **Cualquier persona**&nbsp;&nbsp;Cualquier persona (sin restricciones) que tenga acceso al vínculo de la reunión entra directamente en la reunión.
Cuando se especifica cualquier método, excepto "Solo el organizador" (bloqueado), el organizador de la reunión también puede establecer que las personas que llamen por teléfono no pasen por la sala de espera. 

### <a name="presenter-capabilities"></a>Capacidades del presentador
Los organizadores de la reunión controlan si los participantes pueden realizar presentaciones durante una reunión. Cada reunión puede configurarse para limitar los presentadores, según estas opciones:
- **Solo organizador**&nbsp;&nbsp; Solo el organizador de la reunión puede presentar.
- **Gente de mi empresa**&nbsp;&nbsp; Todos los usuarios internos pueden presentar.
- **Todas las personas, incluidas las de fuera de mi empresa**&nbsp;&nbsp; Todas las personas (sin restricciones) que se unan a la reunión pueden presentar.
- **La gente que yo invite**&nbsp;&nbsp;El organizador de la reunión especifica qué usuarios pueden presentar agregándolos a una lista de presentadores.

## <a name="related-topics"></a>Temas relacionados
[Centro de confianza de Office 365](https://products.office.com/en-us/business/office-365-trust-center-security)

