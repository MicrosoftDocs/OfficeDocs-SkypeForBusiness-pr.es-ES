---
title: Guía de seguridad para Skype Empresarial Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.reviewer: ''
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
- Skype for Business Online
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Security
description: Guía de seguridad para Skype Empresarial Online <add description>
ms.openlocfilehash: a430d2b6aa4f1992e8710c4a7105530b3dd9fc24
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48505197"
---
# <a name="security-and-skype-for-business-online"></a>Seguridad y Skype Empresarial Online

Skype Empresarial Online (SfBO), como parte de los servicios de Microsoft 365 y Office 365, sigue todos los procedimientos y procedimientos recomendados de seguridad, como la seguridad a nivel de servicio a través de defensa en profundidad, controles del cliente dentro del servicio, seguridad y procedimientos recomendados de funcionamiento. Para obtener información detallada, consulta el Centro de confianza de Microsoft ( https://microsoft.com/trustcenter) .

## <a name="trustworthy-by-design"></a>Fiabilidad basada en el diseño
Skype for Business Online is designed and developed in compliance with the Microsoft Trustworthy Computing Security Development Lifecycle (SDL), which is described at https://www.microsoft.com/sdl/default.aspx. The first step in creating a more secure unified communications system was to design threat models and test each feature as it was designed. Multiple security-related improvements were built into the coding process and practices. Build-time tools detect buffer overruns and other potential security threats before the code is checked in to the final product. Of course, it is impossible to design against all unknown security threats. No system can guarantee complete security. However, because product development embraced secure design principles from the start, Skype for Business Online incorporates industry standard security technologies as a fundamental part of its architecture. 

## <a name="trustworthy-by-default"></a>Confiable de forma predeterminada
Network communications in Skype for Business Online are encrypted by default. By requiring all servers to use certificates and by using OAUTH, TLS, Secure Real-Time Transport Protocol (SRTP), and other industry-standard encryption techniques, including 256-bit Advanced Encryption Standard (AES) encryption, all Skype for Business Online data is protected on the network.

## <a name="how-sfbo-handles-common-security-threats"></a>¿Cómo gestiona SfBO las amenazas comunes de seguridad?
En esta sección se identifican las amenazas más comunes a la seguridad del servicio SfBO y cómo Microsoft mitigará cada amenaza.

### <a name="compromised-key-attack"></a>Ataque mediante clave conocida
Una clave es un código secreto o número que se usa para cifrar, descifrar o validar la información secreta. Hay dos claves confidenciales en uso en la infraestructura de claves públicas (PKI) que deben tenerse en cuenta: la clave privada que tiene cada titular de certificados y la clave de sesión que se usa después de un intercambio de claves de sesión e identificación correcto por los partners de comunicación. Un ataque de clave en peligro se produce cuando el atacante determina la clave privada o la clave de sesión. Cuando el atacante determina correctamente la clave, el atacante puede usar la clave para descifrar datos cifrados sin la información del remitente.

Skype for Business Online uses the PKI features in the Windows Server operating system to protect the key data used for encryption for the Transport Layer Security (TLS) connections. The keys used for media encryptions are exchanged over TLS connections. 

### <a name="network-denial-of-service-attack"></a>Ataque por denegación de servicio de red
The denial-of-service attack occurs when the attacker prevents normal network use and function by valid users. By using a denial-of-service attack, the attacker can:
- Enviar datos no válidos a las aplicaciones y los servicios que se ejecutan en la red que sufre el ataque para interrumpir su funcionamiento normal.
- Enviar una gran cantidad de tráfico, lo que sobrecarga el sistema hasta que deja de responder o responde lentamente a las solicitudes legítimas.
- Ocultar las pruebas de los ataques.
- Impedir que los usuarios obtengan acceso a los recursos de la red.

SfBO se mitigará contra estos ataques ejecutando la protección de red DDOS de Azure y limitando las solicitudes de cliente de los mismos puntos de conexión, subredes y entidades federadas.

### <a name="eavesdropping"></a>Interceptación
La interceptación se produce cuando un atacante obtiene acceso a la ruta de datos en una red y puede supervisar y leer el tráfico. Este tipo de ataque también se denomina rastreo o espionaje. Si el tráfico se produce como texto sin formato, el atacante puede leerlo cuando obtiene acceso a la ruta. Un ejemplo es un ataque que se realiza al controlar un enrutador de la ruta de acceso a los datos. 

SfBO usa TLS mutuo (MTLS) para las comunicaciones de servidor dentro de Microsoft 365 u Office 365 y TLS de los clientes al servicio, lo que hace que este ataque sea muy difícil de conseguir dentro del período de tiempo en el que una conversación determinada podría ser objeto de conversación. TLS autentica a todas las partes y cifra todo el tráfico. Esto no impide el ataque, pero el atacante no puede leer el tráfico a menos que se rompa el cifrado.

El protocolo TURN se usa para medios en tiempo real. El protocolo TURN no ordena que el tráfico esté cifrado y la información que envía está protegida por la integridad del mensaje. Aunque está abierto a los envíos, la información que envía (es decir, las direcciones IP y el puerto) se puede extraer directamente simplemente mirando las direcciones de origen y destino de los paquetes. El servicio SfBO garantiza que los datos son válidos comprobando la integridad del mensaje mediante la clave derivada de algunos elementos, incluida una contraseña TURN, que nunca se envía en texto sin formato. EL SRTP se usa para el tráfico multimedia y también se cifra.

### <a name="identity-spoofing-ip-address-spoofing"></a>Suplantación de identidad (imitación de direcciones IP)
Spoofing occurs when the attacker determines and uses an IP address of a network, computer, or network component without being authorized to do so. A successful attack allows the attacker to operate as if the attacker is the entity normally identified by the IP address. Within the context of Microsoft Lync Server 2010, this situation comes into play only if an administrator has done both of the following:
- Ha configurado conexiones compatibles únicamente con el Protocolo de control de transmisión (TCP) (lo cual no se recomienda porque las comunicaciones TCP no están cifradas).
- Ha marcado las direcciones IP de esas conexiones como hosts de confianza. 

This is less of a problem for Transport Layer Security (TLS) connections, as TLS authenticates all parties and encrypts all traffic. Using TLS prevents an attacker from performing IP address spoofing on a specific connection (for example, mutual TLS connections). But an attacker could still spoof the address of the DNS server that SfBO uses. However, because authentication in SfBO is performed with certificates, an attacker would not have a valid certificate required to spoof one of the parties in the communication.

### <a name="man-in-the-middle-attack"></a>Ataque de intermediario
A man-in-the-middle attack occurs when an attacker reroutes communication between two users through the attacker’s computer without the knowledge of the two communicating users. The attacker can monitor and read the traffic before sending it on to the intended recipient. Each user in the communication unknowingly sends traffic to and receives traffic from the attacker, all while thinking they are communicating only with the intended user. This can happen if an attacker can modify Active Directory Domain Services to add his or her server as a trusted server or modify Domain Name System (DNS) to get clients to connect through the attacker on their way to the server. 

También se puede producir un ataque "Man in the middle" con tráfico de elementos multimedia entre dos clientes, excepto que en SfBO las transmisiones de uso compartido y punto a punto de audio, video y aplicaciones se encriptan con SRTP, usando claves criptográficas que se negocian entre pares empleando el protocolo de inicio de sesión (SIP, Session Initiation Protocol) sobre TLS. 

### <a name="rtp-replay-attack"></a>Ataque de reproducción RTP
A replay attack occurs when a valid media transmission between two parties is intercepted and retransmitted for malicious purposes. SfBO uses SRTP in conjunction with a secure signaling protocol that protects transmissions from replay attacks by enabling the receiver to maintain an index of already received RTP packets and compare each new packet with those already listed in the index.

### <a name="spim"></a>Mensajes instantáneos no deseados
El término inglés "spim" hace referencia a los mensajes instantáneos comerciales no deseados o a las solicitudes de suscripción de presencia no deseadas. Si bien estos mensajes por sí mismos no son un peligro para la seguridad de la red, son como mínimo molestos, pueden reducir la disponibilidad y la productividad de los recursos, y podrían llegar a poner en peligro la red. Un ejemplo de ello es el caso de usuarios que se envían solicitudes no deseadas entre sí. Los usuarios pueden bloquearse entre sí para evitarlo, pero con la federación, si se establece un ataque coordinado de este tipo, puede ser difícil de solucionar a menos que se deshabilite la federación para el asociado.

### <a name="viruses-and-worms"></a>Virus y gusanos
Un virus es una unidad de código cuyo propósito es reproducir unidades de código adicionales y similares. Para funcionar, un virus necesita un host, como un archivo, un correo electrónico o un programa. Al igual que un virus, un gusano es una unidad de código codificada para reproducir unidades de código adicionales y similares, pero que a diferencia de un virus no necesita un host. Los virus y gusanos se muestran principalmente durante las transferencias de archivos entre clientes o cuando se envían direcciones URL de otros usuarios. Si hay un virus en su equipo, puede, por ejemplo, usar su identidad y enviar mensajes instantáneos en su nombre. Los procedimientos recomendados de seguridad estándar para los clientes, como la detección periódica de virus, pueden mitigar este problema. 

## <a name="personally-identifiable-information"></a>Información de identificación personal
SfBO has the potential to disclose information over a public network that might be able to be linked to an individual. The information types can be broken down to two specific categories:
- **Enhanced presence data**&nbsp;&nbsp;&nbsp;Enhanced presence data is information that a user can choose to share or not share over a link to a federated partner or with contacts within an organization. This data is not shared with users on a public IM network. Client policies and other client configuration may put some control with the system administrator. In the SfBO service, enhanced presence privacy mode can be configured for an individual user to prevent SfBO users not on the user’s Contacts list from seeing the user’s presence information. 
- **Mandatory data**&nbsp;&nbsp;&nbsp;Mandatory data is data that is required for the proper operation of the server or the client. This is information that is necessary at a server or network level for the purposes of routing, state maintenance, and signaling. The following tables list the data that is required for SfBO to operate.

***Tabla 1: datos de presencia mejorados***

<!--start table here -->


|                      |                                                                                            |   |
|:---------------------|:-------------------------------------------------------------------------------------------|:--|
| **Datos**             | **Configuración** **posible**                                                                  |   |
| Datos personales        | Nombre, Puesto, Compañía, Dirección de correo electrónico, Zona horaria                                             |   |
| Números de teléfono    | Trabajo, Móvil, Particular                                                                         |   |
| Información de calendario | Disponibilidad, aviso fuera de la ciudad, detalles de la reunión (para aquellos que tienen acceso a su calendario) |   |
| Estado de presencia      | Ausente, Disponible, No disponible, No molestar, No conectado                                             |   |
|                      |                                                                                            |   |

<!-- end of table -->

***Tabla 2: datos obligatorios***

<!--start table here -->


|              |                                                                 |   |
|:-------------|:----------------------------------------------------------------|:--|
| **Categoría** | **Posibles opciones de configuración**                                           |   |
| Dirección IP   | Dirección real del equipo o dirección traducida                     |   |
| URI del SIP      | <u>david.campbell@contoso.com</u>                               |   |
| Nombre         | David David (como se define en Servicios de dominio de Active Directory) |   |
|              |                                                                 |   |

<!-- end of table -->

## <a name="security-framework-for-sfbo"></a>Marco de seguridad para SfBO
This section provides an overview of the fundamental elements that form the security framework for Microsoft SfBO. These elements are as follows:
- Azure Active Directory (AAD) proporciona un único depósito de back-end de confianza para cuentas de usuario. 
- La infraestructura de clave pública (PKI) usa certificados emitidos por entidades de certificación de confianza (CA) para autenticar servidores y garantizar la integridad de los datos.
- Transport Layer Security (TLS), HTTPS over SSL (HTTPS), and mutual TLS (MTLS) enable endpoint authentication and IM encryption. Point-to-point audio, video, and application sharing streams are encrypted and integrity checked using Secure Real-Time Transport Protocol (SRTP).
- Para la autenticación del usuario se usan los protocolos estándar de la industria, siempre que sea posible.

En los temas de esta sección se describe cómo funciona cada uno de estos elementos fundamentales para mejorar la seguridad del servicio SfBO.
 
### <a name="azure-active-directory"></a>Azure Active Directory
Azure Active Directory funciona como servicio de directorio para Microsoft 365 y Office 365. Almacena toda la información del directorio de usuarios y las asignaciones de directivas. 

### <a name="public-key-infrastructure-for-sfbo"></a>Infraestructura de clave pública para SfBO
SfBO service relies on certificates for server authentication and to establish a chain of trust between clients and servers and among the different server roles. The Windows Server public key infrastructure (PKI) provides the infrastructure for establishing and validating this chain of trust. Certificates are digital IDs. They identify a server by name and specify its properties. To ensure that the information on a certificate is valid, the certificate must be issued by a Certificate Authority (CA) that is trusted by clients or other servers that connect to the server. If the server connects only with other clients and servers on a private network, the CA can be an enterprise CA. If the server interacts with entities outside the private network, a public CA might be required.

Even if the information on the certificate is valid, there must be some way to verify that the server presenting the certificate is actually the one represented by the certificate. This is where the Windows PKI comes in. Each certificate is linked to a public key. The server named on the certificate holds a corresponding private key that only it knows. A connecting client or server uses the public key to encrypt a random piece of information and sends it to the server. If the server decrypts the information and returns it as plain text, the connecting entity can be sure that the server holds the private key to the certificate and therefore is the server named on the certificate.

#### <a name="crl-distribution-points"></a>Puntos de distribución de CRL
SfBO requiere que todos los certificados de servidor contengan uno o varios puntos de distribución de lista de revocación de certificados (CRL). Los puntos de distribución crl (CDP) son ubicaciones desde las que las CRL se pueden descargar con el fin de comprobar que el certificado no se ha revocado desde el momento en que se emitió y el certificado todavía está dentro del período de validez. Un punto de distribución CRL se indica en las propiedades del certificado como una dirección URL y es HTTP seguro. El servicio SfBO comprueba la CRL con cada autenticación de certificado.

#### <a name="enhanced-key-usage"></a>Uso mejorado de clave
All components of the SfBO service require all server certificates to support Enhanced Key Usage (EKU) for the purpose of server authentication. Configuring the EKU field for server authentication means that the certificate is valid for the purpose of authenticating servers. This EKU is essential for MTLS. 

### <a name="tls-and-mtls-for-sfbo"></a>TLS y MTLS para SfBO
TLS and MTLS protocols provide encrypted communications and endpoint authentication on the Internet. SfBO uses these two protocols to create the network of trusted servers and to ensure that all communications over that network are encrypted. All SIP communications between servers occur over MTLS. SIP communications from client to server occur over TLS.

TLS enables users, through their client software, to authenticate the SfBO servers to which they connect. On a TLS connection, the client requests a valid certificate from the server. To be valid, the certificate must have been issued by a CA that is also trusted by the client and the DNS name of the server must match the DNS name on the certificate. If the certificate is valid, the client uses the public key in the certificate to encrypt the symmetric encryption keys to be used for the communication, so only the original owner of the certificate can use its private key to decrypt the contents of the communication. The resulting connection is trusted and from that point is not challenged by other trusted servers or clients. Within this context, Secure Sockets Layer (SSL) as used with Web services can be associated as TLS-based.

Server-to-server connections rely on mutual TLS (MTLS) for mutual authentication. On an MTLS connection, the server originating a message and the server receiving it exchange certificates from a mutually trusted CA. The certificates prove the identity of each server to the other. In the SfBO service, this procedure is followed.

TLS and MTLS help prevent both eavesdropping and man-in-the middle attacks. In a man-in-the-middle attack, the attacker reroutes communications between two network entities through the attacker’s computer without the knowledge of either party. TLS and SfBO’s specification of trusted servers mitigate the risk of a man-in-the middle attack partially on the application layer by using end-to-end encryption coordinated using the Public Key cryptography between the two endpoints, and an attacker would have to have a valid and trusted certificate with the corresponding private key and issued to the name of the service to which the client is communicating to decrypt the communication. 

### <a name="encryption-for-sfbo"></a>Encriptación para SfBO
SfBO uses TLS and MTLS to encrypt instant messages. All server-to-server traffic requires MTLS, regardless of whether the traffic is confined to the internal network or crosses the internal network perimeter.

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
Media traffic is encrypted using Secure RTP (SRTP), a profile of Real-Time Transport Protocol (RTP) that provides confidentiality, authentication, and replay attack protection to RTP traffic. SRTP uses a session key generated by using a secure random number generator and exchanged using the signaling TLS channel. In addition, media flowing in both directions between the Mediation Server and its internal next hop is also encrypted using SRTP. 

SfBO generates username/passwords for secure access to media relays over TURN. Media relays exchange the username/password over a TLS-secured SIP channel.

#### <a name="fips"></a>FIPS
SfBO utiliza algoritmos compatibles con FIPS para intercambiar claves de cifrado. 

### <a name="user-and-client-authentication"></a>Autenticación de usuario y cliente 
Un usuario de confianza es uno cuyas credenciales han sido autenticadas por AAD en Microsoft 365 u Office 365. 

Authentication is the provision of user credentials to a trusted server or service. SfBO uses the following authentication protocols, depending on the status and location of the user.
- **La autenticación** moderna es la implementación de Microsoft de OAUTH 2.0 para la comunicación de cliente a servidor. Habilita características de seguridad como la autenticación basada en certificados, la autenticación multifactor y el acceso condicional. Para usar MA, tanto el espacio empresarial en línea como los clientes deben estar habilitados para MA. Los inquilinos de SfBO creados después de mayo de 2017 tienen habilitado MA de forma predeterminada. Para inquilinos creados antes de este momento, siga las instrucciones aquí para activarlo. Los siguientes clientes son compatibles con ma: cliente de Skype Empresarial 2015 o 2016, Skype Empresarial en Mac, cliente de Lync 2013, teléfonos IP 3PIP, iOS y Android. 
- **El id. de** organización se usa cuando la autenticación moderna no está habilitada (o no está disponible).
- **Protocolo de autenticación** implícita para los usuarios denominados anónimos. Los usuarios anónimos son usuarios externos que no tienen credenciales de Active Directory reconocidas, pero que han recibido una invitación a una conferencia local y tienen una clave de conferencia válida. La autenticación implícita no se utiliza para otras interacciones del cliente.

La autenticación SfBO consta de dos fases:
1. Se establece una asociación de seguridad entre el cliente y el servidor.
2. El cliente y el servidor utilizan la asociación de seguridad existente para firmar los mensajes que envían y comprobar los que reciben. Cuando la autenticación está habilitada en el servidor, no se aceptan los mensajes no autenticados de un cliente.

User trust is attached to each message that originates from a user, not to the user identity itself. The server checks each message for valid user credentials. If the user credentials are valid, the message is unchallenged not only by the first server to receive it but by all other servers in SfBO.

Los usuarios con credenciales válidas emitidas por un socio federado son de confianza pero, de manera opcional, algunas restricciones adicionales impiden que disfruten de todos los privilegios otorgados a los usuarios internos.

For media authentication, the ICE and TURN protocols also use the Digest challenge as described in the IETF TURN RFC. For details, see [media traversal](#external-user-av-traffic-traversal).

Los certificados de cliente proporcionan una forma alternativa de autenticar a los usuarios mediante SfBO. En lugar de proporcionar un nombre de usuario y una contraseña, los usuarios tienen un certificado y la clave privada correspondiente al certificado necesario para resolver un reto del cifrado. 

### <a name="windows-powershell-and-sfbo-management-tools"></a>Herramientas de administración de Windows PowerShell y SfBO
En SfBO, los administradores de TI pueden administrar su servicio a través del Portal de administración de O365 o mediante PowerShell remoto de inquilino (TRPS). Los administradores de inquilinos usan la autenticación moderna para autenticarse en TRPS.

### <a name="configuring-access-to-sfbo-at-your-internet-boundary"></a>Configurar el acceso a SfBO en su límite de Internet
Para que SfBO funcione correctamente (los usuarios pueden unirse a reuniones, etc.), los clientes necesitan configurar su acceso a Internet de modo que se permita el tráfico UDP y TCP de salida a los servicios de la nube SfBO. Para obtener más información, consulta aquí: https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_lyo 

### <a name="udp-3478-3481-and-tcp-443"></a>UDP 3478-3481 y TCP 443

Los clientes usan los puertos UDP 3478-3481 y TCP 443 para solicitar el servicio desde el servicio perimetral A/V. Un cliente usa estos dos puertos para asignar puertos UDP y TCP, respectivamente, a los que la entidad remota se conecte. Para obtener acceso al servicio perimetral A/V, el cliente debe haber establecido primero una sesión de señalización SIP autenticada con el registrador de SfBO para obtener las credenciales de autenticación del servicio perimetral A/V. Estos valores se envían a través del canal de señalización protegido con TLS y se generan en el equipo para mitigar ataques de diccionario. A continuación, los clientes pueden usar estas credenciales para la autenticación de resumen con el servicio perimetral A/V para asignar puertos para su uso en una sesión multimedia. Se envía una solicitud de asignación inicial desde el cliente y se ha respondido con un mensaje de nonce/challenge 401 desde el servicio perimetral A/V. El cliente envía un segundo envío que contiene el nombre de usuario y un hash del Código de autenticación de mensajes hash (HMAC) del nombre de usuario y de nonce. 

A sequence number mechanism is also in place to prevent replay attacks. The server calculates the expected HMAC based on its own knowledge of the user name and password and if the HMAC values match, the allocate procedure is carried out. Otherwise, the packet is dropped. This same HMAC mechanism is also applied to subsequent messages within this call session. The lifetime of this user name/password value is a maximum of eight hours at which time the client reacquires a new user name/password for subsequent calls.

### <a name="udptcp-5000059999"></a>UDP/TCP 50.000-59.999
TCP 50,000 outbound is used for SfBO, including for application and desktop sharing, file transfer. UDP/TCP 50,000-59,999 port ranges are used for media sessions with Microsoft Office Communications Server 2007 partners that require NAT/firewall traversal service from the A/V Edge service. Because the A/V Edge service is the sole process using these ports, the size of the port range does not indicate the potential surface of attack. Good security practice is to always minimize the total number of listening ports by not running unnecessary network services. If a network service is not running, it is not exploitable by a remote attacker and the surface of attack of the host computer is reduced. However, within a single service, reducing the number of ports does not provide the same benefit. The A/V Edge service software is no more exposed to attack with 10,000 ports open as it is with 10. The allocation of ports within this range is done randomly and ports not currently allocated do not listen for packets.

### <a name="external-user-av-traffic-traversal"></a>Transversal de tráfico A/V de usuario externo
Enabling external users and internal users to exchange media requires an Access Edge service to handle the SIP signaling that is necessary to set up and tear down a session. It also requires an A/V Edge service to act as a relay for the transfer of the media. The call sequence is illustrated in the following figure.


![Secuencia de llamadas para unirse a la reunión](media/sfbo-call-sequence-security.png) 

1. A user receives an email containing an invitation to join an SfBO meeting. The email contains a conference key and a HTTP-based URL linking to the conference. Both the key and the URL are unique for a particular meeting.<p>El usuario inicia el procedimiento de combinación haciendo clic en la dirección URL de la reunión en el correo electrónico que inicia un proceso de detección de cliente en el equipo del usuario. Si se detecta, este cliente se inicia. Si no se detecta, el usuario se redirige al cliente web.<p/>
2. El cliente SfBO envía una INVITACIÓN SIP que contiene las credenciales del usuario. Un usuario federado o remoto se une a una conferencia con sus credenciales de empresa. Para un usuario federado, la INVITACIÓN SIP se envía primero a su servidor principal, que autentica al usuario y reenvía la INVITACIÓN a SfBO. Se requiere un usuario anónimo para pasar la autenticación de resumen.<p>SfBO authenticates the remote or anonymous user and notifies the client. As mentioned in step 2, federated users joining a conference are authenticated by their enterprise.<p/>

3. El cliente envía una solicitud INFO para agregar al usuario a la conferencia A/V.

    Las conferencias A/V envían una respuesta agregar usuario que contiene el token para presentar al servicio perimetral de conferencia de A/V, entre otra información.

    [Nota]  Todo el tráfico SIP anterior fluyó por el servicio perimetral de Access.

    The client connects to the A/V Conference Server, which validates the token and proxies the request, which contains another authorization token, to the internal A/V Conferencing Server. The A/V Conferencing Server validates the Authorization Token, which it originally issued over the SIP channel, to further ensure that a valid user is joining the conference.

4. Entre el cliente y el servidor de conferencia de A/V, se negocia una conexión multimedia y se configura a través del SRTP.
5. A user receives an email containing an invitation to join an SfBO meeting. The email contains a conference key and a HTTP-based URL linking to the conference. Both the key and the URL are unique for a particular meeting.

### <a name="federation-safeguards-for-sfbo"></a>Medidas de seguridad de la federación para SfBO
La federación proporciona a su organización la capacidad de comunicarse con otras organizaciones para compartir mensajería instantánea y presencia. En sfBO la federación está predeterminada. Sin embargo, los administradores de inquilinos pueden controlar esto a través del Portal de administración de Microsoft 365 u Office 365. Ver más.

## <a name="addressing-threats-to-sfbo-conferences"></a>Atajar amenazas a las conferencias de SfBO

SfBO ofrece la capacidad de los usuarios empresariales de crear y unirse a conferencias web en tiempo real. Los usuarios de empresa también pueden invitar a usuarios externos que no tienen una cuenta de AAD, Microsoft 365 u Office 365 a participar en estas reuniones. Los usuarios empleados por socios federados con una identidad segura y autenticada también pueden unirse a reuniones y, si se promueve para hacerlo, pueden actuar como presentadores. Los usuarios anónimos no pueden crear una reunión como moderador, pero pueden promoverse a moderador después de unirse.

Enabling external users to participate in SfBO meetings greatly increases the value of this feature, but it also entails some security risks. To address these risks, SfBO provides the following additional safeguards:
- Los roles de los participantes determinan los privilegios de control de la conferencia.
- Los tipos de participantes le permiten limitar el acceso a reuniones específicas.
- Los tipos de reunión definidos determinan qué tipos de participantes pueden asistir.
- La programación de la conferencia está restringida a los usuarios que tienen una cuenta de AAD y una licencia de SfBO.
- Anonymous, that is, unauthenticated, users who want to join a dial-in conference dial one of the conference access numbers and then they are prompted to enter the conference ID. Unauthenticated anonymous users are also prompted to record their name. The recorded name identifies unauthenticated users in the conference. Anonymous users are not admitted to the conference until at least one leader or authenticated user has joined, and they cannot be assigned a predefined role.

### <a name="participant-roles"></a>Roles de los participantes
Los participantes de la reunión se dividen en tres grupos, cada uno con sus propios privilegios y restricciones:
-  &nbsp; Organizador &nbsp; El usuario que crea una reunión, ya sea de forma improvisada o programando. Un organizador debe ser un usuario empresarial autenticado y tener control sobre todos los aspectos de usuario final de una reunión.
- **Moderador** &nbsp; &nbsp; Un usuario con autorización para presentar información en una reunión, con cualquier medio que sea compatible. El organizador de la reunión es, por definición, también moderador y determina quién más puede ser moderador. Un organizador puede tomar esta determinación cuando se programa una reunión o mientras se está en marcha.
-  &nbsp; Asistente &nbsp; Un usuario que ha sido invitado a asistir a una reunión pero que no está autorizado para actuar como moderador.

Un moderador también puede promover a un asistente al rol de moderador durante la reunión.

### <a name="participant-types"></a>Tipos de participantes

Meeting participants are also categorized by location and credentials. You can use both of these characteristics to specify which users can have access to specific meetings. Users can be divided broadly into the following categories:
1.  **Usuarios que pertenecen al inquilino** &nbsp; &nbsp; Estos usuarios tienen una credencial de Azure Active Directory para el inquilino.<br/> a. *Inside corpnet* – These users are joining from inside the corporate network.<br/>b. *Remote users* – These users are joining from outside the corporate network. They can include employees who are working at home or on the road, and others, such as employees of trusted vendors, who have been granted enterprise credentials for their terms of service. Remote users can create and join conferences and act as presenters.
2.  **Usuarios que no pertenecen al inquilino**&nbsp;&nbsp;Estos usuarios no tienen una credencial en Azure Active Directory para el inquilino.<br/>a. *Usuarios federados:* los usuarios federados poseen credenciales válidas con socios federados y, por tanto, son tratados como autenticados por SfBO. Los usuarios federados pueden unirse a conferencias y promoverse a los presentadores después de unirse a la reunión, pero no pueden crear conferencias en empresas con las que estén federados.<br/>b. *Anonymous Users* - Anonymous users do not have an Active Directory identity and are not federated with the tenant. 

Customer data shows that many conferences involve external users. Those same customers also want reassurance about the identity of external users before allowing those users to join a conference. As the following section describes, SfBO limits meeting access to those user types that have been explicitly allowed and requires all user types to present appropriate credentials when entering a meeting.

### <a name="participant-admittance"></a>Admisión de los participantes
In SfBO, anonymous users are transferred to a waiting area called the lobby. Presenters can then either admit these users to the meeting or reject them. These users are transferred to the lobby, the leader is notified, and the users then wait until a leader either accepts or rejects them or their connection times out. While in the lobby, the users hear music. 

De forma predeterminada, los participantes que llaman desde la PSTN pasan directamente a la reunión, pero esta opción se puede cambiar para obligarlos a ir a la sala de espera.  
Meeting organizers control whether participants can join a meeting without waiting in the lobby. Each meeting can be set up to enable access using any one of the following methods:
- **Solo yo, el organizador de la reunión**&nbsp;&nbsp;Todos, excepto el organizador, deben aguardar en la sala de espera hasta a ser admitidos.
- **Personas a las que invito de mi empresa**&nbsp;&nbsp;Cualquier persona de su empresa puede entrar a la reunión directamente, incluso si no está invitado.
- **Cualquier persona de mi organización** &nbsp; &nbsp; Todos los usuarios de SfBO del espacio empresarial de Microsoft 365 u Office 365 pueden unirse a la reunión sin esperar en la sala de espera, incluso si los que no están en la lista de distribución. Todos los demás, incluidos todos los usuarios externos y anónimos, deben esperar en la sala de espera hasta que se les admita.
-  &nbsp; Cualquiera &nbsp; Cualquier persona (sin restricciones) que tenga acceso al vínculo de la reunión entra directamente en la reunión. Cuando se especifica un método excepto el Organizador (bloqueado), el organizador de la reunión también puede especificar las personas que marcan por teléfono omita la sala de espera. 

### <a name="presenter-capabilities"></a>Capacidades del presentador
Meeting organizers control whether participants can present during a meeting. Each meeting can be set up to limit presenters to any one of the following:
- **Solo el organizador** &nbsp; &nbsp; Solo el organizador de la reunión puede presentar.
- **Personas de mi empresa** &nbsp; &nbsp; Pueden presentar todos los usuarios internos.
- **Todos, incluidas las personas de fuera de mi compañía** &nbsp; &nbsp; Todos los usuarios (sin restricciones) que se unan a la reunión pueden presentar.
- **La gente que yo invite**&nbsp;&nbsp;El organizador de la reunión especifica qué usuarios pueden presentar agregándolos a una lista de presentadores.

## <a name="related-topics"></a>Temas relacionados
[Centro de confianza de Microsoft](https://microsoft.com/trustcenter)

