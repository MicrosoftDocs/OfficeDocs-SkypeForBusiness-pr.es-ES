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
ms.openlocfilehash: f31b9d797544e1c420087c0163986fcdc80ac6c4
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25371894"
---
#  <a name="security-and-skype-for-business-online"></a>Seguridad y Skype para la empresa en línea

Skype for Business Online (SfBO), as part of the Office 365 service, follows all the security best practices and procedures such as service-level security through defense-in-depth, customer controls within the service, security hardening and operational best practices.  For full details, please see the Office 365 Trust Center (https://products.office.com/en-us/business/office-365-trust-center-security).

## <a name="trustworthy-by-design"></a>Fiabilidad basada en el diseño
Skype for Business Online is designed and developed in compliance with the Microsoft Trustworthy Computing Security Development Lifecycle (SDL), which is described at https://www.microsoft.com/en-us/sdl/default.aspx. The first step in creating a more secure unified communications system was to design threat models and test each feature as it was designed. Multiple security-related improvements were built into the coding process and practices. Build-time tools detect buffer overruns and other potential security threats before the code is checked in to the final product. Of course, it is impossible to design against all unknown security threats. No system can guarantee complete security. However, because product development embraced secure design principles from the start, Skype for Business Online incorporates industry standard security technologies as a fundamental part of its architecture. 

## <a name="trustworthy-by-default"></a>Confiable de forma predeterminada
Network communications in Skype for Business Online are encrypted by default. By requiring all servers to use certificates and by using OAUTH, TLS, Secure Real-Time Transport Protocol (SRTP), and other industry-standard encryption techniques, including 256-bit Advanced Encryption Standard (AES) encryption, all Skype for Business Online data is protected on the network.

## <a name="how-sfbo-handles-common-security-threats"></a>¿Cómo gestiona SfBO las amenazas comunes de seguridad?
Esta sección identifica las amenazas de seguridad más comunes del servicio SfBO y la forma en que Microsoft minimiza cada amenaza.

### <a name="compromised-key-attack"></a>Ataque de clave comprometida
A key is a secret code or number that is used to encrypt, decrypt, or validate secret information. There are two sensitive keys in use in public key infrastructure (PKI) that must be considered: the private key that each certificate holder has and the session key that is used after a successful identification and session key exchange by the communicating partners.  A compromised-key attack occurs when the attacker determines the private key or the session key. When the attacker is successful in determining the key, the attacker can use the key to decrypt encrypted data without the knowledge of the sender.

Skype for Business Online uses the PKI features in the Windows Server operating system to protect the key data used for encryption for the Transport Layer Security (TLS) connections. The keys used for media encryptions are exchanged over TLS connections. 

### <a name="network-denial-of-service-attack"></a>Ataque por denegación de servicio de la red
The denial-of-service attack occurs when the attacker prevents normal network use and function by valid users. By using a denial-of-service attack, the attacker can:
- Enviar datos no válidos a las aplicaciones y los servicios que se ejecutan en la red que sufre el ataque para interrumpir su funcionamiento normal.
- Enviar una gran cantidad de tráfico, lo que sobrecarga el sistema hasta que deja de responder o responde lentamente a las solicitudes legítimas.
- Ocultar las pruebas de los ataques.
- Impedir que los usuarios obtengan acceso a los recursos de la red.

SfBO ofrece protección frente a estos ataques mediante la ejecución de la protección de red Azure DDOS y limitando las solicitudes de los clientes desde los mismos extremos, subredes y entidades federadas.

### <a name="eavesdropping"></a>Interceptación
La interceptación se produce cuando un atacante obtiene acceso a la ruta de datos en una red y puede supervisar y leer el tráfico. Este tipo de ataque también se denomina rastreo o espionaje. Si el tráfico se produce como texto sin formato, el atacante puede leerlo cuando obtiene acceso a la ruta. Un ejemplo es un ataque que se realiza al controlar un enrutador de la ruta de acceso a los datos. 

SfBO uses mutual TLS (MTLS) for server communications within O365 and TLS from clients to the service, rendering this attack very difficult to impossible to achieve within the time period in which a given conversation could be attacked. TLS authenticates all parties and encrypts all traffic. This does not prevent eavesdropping, but the attacker cannot read the traffic unless the encryption is broken.

The TURN protocol is used for real time media purposes.  The TURN protocol does not mandate the traffic to be encrypted and the information that it is sending is protected by message integrity. Although it is open to eavesdropping, the information it is sending (that is, IP addresses and port) can be extracted directly by simply looking at the source and destination addresses of the packets. The SfBO service ensures that the data is valid by checking the Message Integrity of the message using the key derived from a few items including a TURN password, which is never sent in clear text. SRTP is used for media traffic and is also encrypted.

### <a name="identity-spoofing-ip-address-spoofing"></a>Suplantación de identidad (suplantación de dirección IP)
Spoofing occurs when the attacker determines and uses an IP address of a network, computer, or network component without being authorized to do so. A successful attack allows the attacker to operate as if the attacker is the entity normally identified by the IP address. Within the context of Microsoft Lync Server 2010, this situation comes into play only if an administrator has done both of the following:
- Ha configurado conexiones compatibles únicamente con el Protocolo de control de transmisión (TCP) (lo cual no se recomienda porque las comunicaciones TCP no están cifradas).
- Ha marcado las direcciones IP de esas conexiones como hosts de confianza. 

This is less of a problem for Transport Layer Security (TLS) connections, as TLS authenticates all parties and encrypts all traffic. Using TLS prevents an attacker from performing IP address spoofing on a specific connection (for example, mutual TLS connections). But an attacker could still spoof the address of the DNS server that SfBO uses. However, because authentication in SfBO is performed with certificates, an attacker would not have a valid certificate required to spoof one of the parties in the communication.

### <a name="man-in-the-middle-attack"></a>Ataque de tipo "Man in the middle"
A man-in-the-middle attack occurs when an attacker reroutes communication between two users through the attacker’s computer without the knowledge of the two communicating users. The attacker can monitor and read the traffic before sending it on to the intended recipient. Each user in the communication unknowingly sends traffic to and receives traffic from the attacker, all while thinking they are communicating only with the intended user. This can happen if an attacker can modify Active Directory Domain Services to add his or her server as a trusted server or modify Domain Name System (DNS) to get clients to connect through the attacker on their way to the server. 

También se puede producir un ataque "Man in the middle" con tráfico de elementos multimedia entre dos clientes, excepto que en SfBO las transmisiones de uso compartido y punto a punto de audio, video y aplicaciones se encriptan con SRTP, usando claves criptográficas que se negocian entre pares empleando el protocolo de inicio de sesión (SIP, Session Initiation Protocol) sobre TLS. 

### <a name="rtp-replay-attack"></a>Ataque de reproducción RTP
A replay attack occurs when a valid media transmission between two parties is intercepted and retransmitted for malicious purposes. SfBO uses SRTP in conjunction with a secure signaling protocol that protects transmissions from replay attacks by enabling the receiver to maintain an index of already received RTP packets and compare each new packet with those already listed in the index.

### <a name="spim"></a>Mensajes instantáneos no deseados
El término inglés "spim" hace referencia a los mensajes instantáneos comerciales no deseados o a las solicitudes de suscripción de presencia no deseadas. Si bien estos mensajes por sí mismos no son un peligro para la seguridad de la red, son como mínimo molestos, pueden reducir la disponibilidad y la productividad de los recursos, y podrían llegar a poner en peligro la red. Un ejemplo de ello es el caso de usuarios que se envían solicitudes no deseadas entre sí. Los usuarios pueden bloquearse entre sí para evitarlo, pero con la federación, si se establece un ataque coordinado de este tipo, puede ser difícil de solucionar a menos que se deshabilite la federación para el asociado.

### <a name="viruses-and-worms"></a>Virus y gusanos
A virus is a unit of code whose purpose is to reproduce additional, similar code units. To work, a virus needs a host, such as a file, email, or program. Like a virus, a worm is a unit of code that is coded to reproduce additional, similar code units, but that unlike a virus does not need a host. Viruses and worms primarily show up during file transfers between clients or when URLs are sent from other users. If a virus is on your computer, it can, for example, use your identity and send instant messages on your behalf.  Standard client security best practices such as periodically scanning for viruses can mitigate this issue.  

## <a name="personally-identifiable-information"></a>Información de identificación personal
SfBO has the potential to disclose information over a public network that might be able to be linked to an individual. The information types can be broken down to two specific categories:
- **Enhanced presence data**&nbsp;&nbsp;&nbsp;Enhanced presence data is information that a user can choose to share or not share over a link to a federated partner or with contacts within an organization. This data is not shared with users on a public IM network. Client policies and other client configuration may put some control with the system administrator. In the SfBO service, enhanced presence privacy mode can be configured for an individual user to prevent SfBO users not on the user’s Contacts list from seeing the user’s presence information. 
- **Mandatory data**&nbsp;&nbsp;&nbsp;Mandatory data is data that is required for the proper operation of the server or the client. This is information that is necessary at a server or network level for the purposes of routing, state maintenance, and signaling. The following tables list the data that is required for SfBO to operate.

***Tabla 1: datos de presencia mejorados***

<!--start table here -->


|                      |                                                                                            |   |
|:---------------------|:-------------------------------------------------------------------------------------------|:--|
| **Datos**             | **Configuración** **posible**                                                                  |   |
| Datos personales        | Nombre, puesto, compañía, dirección de correo electrónico, zona horaria                                             |   |
| Números de teléfono    | Trabajo, Móvil, Particular                                                                         |   |
| Información de calendario | Información de disponibilidad, aviso de fuera, detalles (para los usuarios que tengan acceso a su calendario) de la reunión |   |
| Estado de presencia      | Ausente, Disponible, No disponible, No molestar, No conectado                                             |   |
|                      |                                                                                            |   |

<!-- end of table -->

***Tabla 2: datos obligatorios***

<!--start table here -->


|              |                                                                 |   |
|:-------------|:----------------------------------------------------------------|:--|
| **Categoría** | **Valores posibles**                                           |   |
| Dirección IP   | Dirección real del equipo o dirección traducida                     |   |
| URI del SIP      | <u>david.campbell@contoso.com</u>                               |   |
| Nombre         | David Campbell (tal y como se define en los servicios de dominio de Active Directory) |   |
|              |                                                                 |   |

<!-- end of table -->

## <a name="security-framework-for-sfbo"></a>Marco de seguridad para SfBO
This section provides an overview of the fundamental elements that form the security framework for Microsoft SfBO. These elements are as follows:
- Azure Active Directory (AAD) proporciona un único depósito de back-end de confianza para cuentas de usuario. 
- Infraestructura de clave pública (PKI) utiliza certificados emitidos por entidades de certificación de confianza (CA) para autenticar los servidores y garantizar la integridad de los datos.
- Transport Layer Security (TLS), HTTPS over SSL (HTTPS), and mutual TLS (MTLS) enable endpoint authentication and IM encryption. Point-to-point audio, video, and application sharing streams are encrypted and integrity checked using Secure Real-Time Transport Protocol (SRTP).
- Para la autenticación del usuario se usan los protocolos estándar de la industria, siempre que sea posible.

En los temas de esta sección se describen cómo funciona cada uno de estos elementos fundamentales para mejorar la seguridad del servicio de SfBO.

### <a name="azure-active-directory"></a>Azure Active Directory
Azure Active Directory functions as the directory service for O365. It stores all user directory information and policy assignments. 

### <a name="public-key-infrastructure-for-sfbo"></a>Infraestructura de clave pública para SfBO
SfBO service relies on certificates for server authentication and to establish a chain of trust between clients and servers and among the different server roles. The Windows Server public key infrastructure (PKI) provides the infrastructure for establishing and validating this chain of trust. Certificates are digital IDs. They identify a server by name and specify its properties. To ensure that the information on a certificate is valid, the certificate must be issued by a Certificate Authority (CA) that is trusted by clients or other servers that connect to the server. If the server connects only with other clients and servers on a private network, the CA can be an enterprise CA. If the server interacts with entities outside the private network, a public CA might be required.

Even if the information on the certificate is valid, there must be some way to verify that the server presenting the certificate is actually the one represented by the certificate. This is where the Windows PKI comes in. Each certificate is linked to a public key. The server named on the certificate holds a corresponding private key that only it knows. A connecting client or server uses the public key to encrypt a random piece of information and sends it to the server. If the server decrypts the information and returns it as plain text, the connecting entity can be sure that the server holds the private key to the certificate and therefore is the server named on the certificate.

#### <a name="crl-distribution-points"></a>Puntos de distribución CRL
SfBO requires all server certificates to contain one or more Certificate Revocation List (CRL) distribution points. CRL distribution points (CDPs) are locations from which CRLs can be downloaded for purposes of verifying that the certificate has not been revoked since the time it was issued and the certificate is still within the validity period. A CRL distribution point is noted in the properties of the certificate as a URL and is secure HTTP.  The SfBO service checks CRL with every certificate authentication.

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
Un usuario confianza es aquel cuyas credenciales se han autenticado por AAD en O365. 

Authentication is the provision of user credentials to a trusted server or service. SfBO uses the following authentication protocols, depending on the status and location of the user.
- **Modern Authentication** is the Microsoft implementation of OAUTH 2.0 for client to server communication. It enables security features such as O365 Certificate Based Authentication, O365 Multi-Factor Authentication and O365 Conditional Access.  In order to use MA, both the online tenant and the clients need to be enabled for MA.  SfBO tenants created after May 2017 have MA enabled by default.  For tenants created before this time, follow the instructions here to turn it on.  The following clients all support MA: Skype for Business 2015 or 2016 client, Skype for Business on Mac, Lync 2013 client, 3PIP IP Phones, iOS, and Android. 
- Cuando la autenticación moderna no está habilitada (o no está disponible) se usa **ID de organización**.
- **Protocolo de autenticación** implícita para los usuarios denominados anónimos. Los usuarios anónimos son usuarios externos que no tienen credenciales de Active Directory reconocidas, pero que han recibido una invitación a una conferencia local y tienen una clave de conferencia válida. La autenticación implícita no se utiliza para otras interacciones del cliente.

Autenticación de SfBO consta de dos fases:
1. Se establece una asociación de seguridad entre el cliente y el servidor.
2. El cliente y el servidor utilizan la asociación de seguridad existente para firmar los mensajes que envían y comprobar los que reciben. Cuando la autenticación está habilitada en el servidor, no se aceptan los mensajes no autenticados de un cliente.

User trust is attached to each message that originates from a user, not to the user identity itself. The server checks each message for valid user credentials. If the user credentials are valid, the message is unchallenged not only by the first server to receive it but by all other servers in SfBO.

Los usuarios con credenciales válidas emitidas por un socio federado son de confianza pero, de manera opcional, algunas restricciones adicionales impiden que disfruten de todos los privilegios otorgados a los usuarios internos.

For media authentication, the ICE and TURN protocols also use the Digest challenge as described in the IETF TURN RFC. For details, see [media traversal](#external-user-av-traffic-traversal).

Client certificates provide an alternate way for users to be authenticated by SFBO. Instead of providing a user name and password, users have a certificate and the private key corresponding to the certificate that is required to resolve a cryptographic challenge. 

### <a name="windows-powershell-and-sfbo-management-tools"></a>Herramientas de administración de Windows PowerShell y SfBO
In SfBO, IT Admins can manage their service via the O365 Admin portal or by using Tenant Remote PowerShell (TRPS).  Tenant admins use Modern Authentication to authenticate to TRPS.

### <a name="configuring-access-to-sfbo-at-your-internet-boundary"></a>Configurar el acceso a SfBO en su límite de Internet
For SfBO to function properly (users able to join meetings etc.), customers need to configure their internet access such that outbound UDP and TCP traffic to services in the SfBO cloud is allowed.  For more details, see here: https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_lyo 

### <a name="udp-3478-3481-and-tcp-443"></a>UDP 3478-3481 y TCP 443

The UDP 3478-3481 and TCP 443 ports are used by clients to request service from the A/V Edge service. A client uses these two ports to allocate UDP and TCP ports respectively for the remote party to connect to. To access the A/V Edge service, the client must first have established an authenticated SIP signaling session with SFBO registrar to obtain A/V Edge service authentication credentials. These values are sent across the TLS-protected signaling channel and are computer generated to mitigate against dictionary attacks. Clients can then use these credentials for digest authentication with the A/V Edge service to allocate ports for use in a media session. An initial allocate request is sent from the client and responded with a 401 nonce/challenge message from the A/V Edge service. The client sends a second allocate containing the user name and a Hash Message Authentication Code (HMAC) hash of the user name and nonce. 

A sequence number mechanism is also in place to prevent replay attacks. The server calculates the expected HMAC based on its own knowledge of the user name and password and if the HMAC values match, the allocate procedure is carried out. Otherwise, the packet is dropped. This same HMAC mechanism is also applied to subsequent messages within this call session. The lifetime of this user name/password value is a maximum of eight hours at which time the client reacquires a new user name/password for subsequent calls.

### <a name="udptcp-50000-59999"></a>UDP/TCP 50 000-59 999
TCP 50,000 outbound is used for SfBO, including for application and desktop sharing, file transfer. UDP/TCP 50,000-59,999 port ranges are used for media sessions with Microsoft Office Communications Server 2007 partners that require NAT/firewall traversal service from the A/V Edge service. Because the A/V Edge service is the sole process using these ports, the size of the port range does not indicate the potential surface of attack. Good security practice is to always minimize the total number of listening ports by not running unnecessary network services. If a network service is not running, it is not exploitable by a remote attacker and the surface of attack of the host computer is reduced. However, within a single service, reducing the number of ports does not provide the same benefit. The A/V Edge service software is no more exposed to attack with 10,000 ports open as it is with 10. The allocation of ports within this range is done randomly and ports not currently allocated do not listen for packets.

### <a name="external-user-av-traffic-traversal"></a>Transversal de tráfico A/V de usuario externo
Enabling external users and internal users to exchange media requires an Access Edge service to handle the SIP signaling that is necessary to set up and tear down a session. It also requires an A/V Edge service to act as a relay for the transfer of the media. The call sequence is illustrated in the following figure.


![Secuencia de llamadas para unirse a la reunión](media/sfbo-call-sequence-security.png) 

1. A user receives an email containing an invitation to join an SfBO meeting. The email contains a conference key and a HTTP-based URL linking to the conference. Both the key and the URL are unique for a particular meeting.<p>The user initiates the join procedure by clicking the meeting URL in the email which initiates a client detection process on the user’s machine.  If the client is detected, this client is launched.  If it is not detected, the user is redirected to the web client.<p/>
2. The SfBO client sends a SIP INVITE containing the user’s credentials. A federated or remote user joins a conferencing using their enterprise credentials. For a federated user, the SIP INVITE is first sent to his or her home server, which authenticates the user and forwards the INVITE to SfBO. An anonymous user is required to pass digest authentication.<p>SfBO authenticates the remote or anonymous user and notifies the client. As mentioned in step 2, federated users joining a conference are authenticated by their enterprise.<p/>

3. El cliente envía una solicitud INFO para agregar al usuario a la conferencia A/V.

    Las conferencias A/V envían una respuesta Agregar usuario que contiene el token para presentar al servicio perimetral de conferencia A/V, entre otra información.

    [Nota]  Todo el tráfico SIP anterior anteriormente indicado fluye a través del servicio de servidor perimetral de acceso.

    The client connects to the A/V Conference Server, which validates the token and proxies the request, which contains another authorization token, to the internal A/V Conferencing Server. The A/V Conferencing Server validates the Authorization Token, which it originally issued over the SIP channel, to further ensure that a valid user is joining the conference.

4. Entre el cliente y el servidor de conferencia AV, se negocia y configura una conexión de elementos multimedia mediante SRTP.
5. A user receives an email containing an invitation to join an SfBO meeting. The email contains a conference key and a HTTP-based URL linking to the conference. Both the key and the URL are unique for a particular meeting.

### <a name="federation-safeguards-for-sfbo"></a>Garantías de la federación para SfBO
Federation provides your organization with the ability to communicate with other organizations to share IM and presence. In SfBO federation is on by default.  However, tenant admins have the ability to control this via the O365 Admin portal.  See more.

## <a name="addressing-threats-to-sfbo-conferences"></a>Atajar amenazas a las conferencias de SfBO

SfBO provides the capability for enterprise users to create and join real-time Web conferences. Enterprise users can also invite external users who do not have an AAD/O365 account to participate in these meetings. Users who are employed by federated partners with a secure and authenticated identity can also join meetings and, if promoted to do so, can act as presenters. Anonymous users cannot create or join a meeting as a presenter, but they can be promoted to presenter after they join.

Enabling external users to participate in SfBO meetings greatly increases the value of this feature, but it also entails some security risks. To address these risks, SfBO provides the following additional safeguards:
- Los roles de los participantes determinan los privilegios de control de la conferencia.
- Los tipos de participantes le permiten limitar el acceso a reuniones específicas.
- Los tipos de reunión definidos determinan qué tipos de participantes pueden asistir.
- La programación de la conferencia está restringida a los usuarios que tienen una cuenta de AAD y una licencia de SfBO.
- Anonymous, that is, unauthenticated, users who want to join a dial-in conference dial one of the conference access numbers and then they are prompted to enter the conference ID. Unauthenticated anonymous users are also prompted to record their name. The recorded name identifies unauthenticated users in the conference. Anonymous users are not admitted to the conference until at least one leader or authenticated user has joined, and they cannot be assigned a predefined role.

### <a name="participant-roles"></a>Roles de los participantes
Los participantes de la reunión se dividen en tres grupos, cada uno con sus propios privilegios y restricciones:
- **Organizer** &nbsp;&nbsp; The user who creates a meeting, whether impromptu or by scheduling. An organizer must be an authenticated enterprise user and have control over all end-user aspects of a meeting.
- **Presenter** &nbsp;&nbsp; A user who is authorized to present information at a meeting, using whatever media is supported. A meeting organizer is by definition also a presenter and determines who else can be a presenter. An organizer can make this determination when a meeting is scheduled or while the meeting is under way.
- **ATTENDEE** &nbsp; &nbsp; Un usuario que ha sido invitado a asistir a una reunión pero que no está autorizado para actuar como moderador.

Un presentador también puede promocionar a un asistente al rol de presentador durante la reunión.

### <a name="participant-types"></a>Tipos de participantes

Meeting participants are also categorized by location and credentials. You can use both of these characteristics to specify which users can have access to specific meetings. Users can be divided broadly into the following categories:
1.  **Usuarios que pertenecen al inquilino**&nbsp;&nbsp;Estos usuarios tienen una credencial en Azure Active Directory para el inquilino.<br/> a. *Inside corpnet* – These users are joining from inside the corporate network.<br/>b. *Remote users* – These users are joining from outside the corporate network. They can include employees who are working at home or on the road, and others, such as employees of trusted vendors, who have been granted enterprise credentials for their terms of service. Remote users can create and join conferences and act as presenters.
2.  **Usuarios que no pertenecen al inquilino**&nbsp;&nbsp;Estos usuarios no tienen una credencial en Azure Active Directory para el inquilino.<br/>a. *Federated Users* - Federated users possess valid credentials with federated partners and are therefore treated as authenticated by SFBO. Federated users can join conferences and be promoted to presenters after they have joined the meeting, but they cannot create conferences in enterprises with which they are federated.<br/>b. *Anonymous Users* - Anonymous users do not have an Active Directory identity and are not federated with the tenant. 

Customer data shows that many conferences involve external users. Those same customers also want reassurance about the identity of external users before allowing those users to join a conference. As the following section describes, SfBO limits meeting access to those user types that have been explicitly allowed and requires all user types to present appropriate credentials when entering a meeting.

### <a name="participant-admittance"></a>Admisión de los participantes
In SfBO, anonymous users are transferred to a waiting area called the lobby. Presenters can then either admit these users to the meeting or reject them. These users are transferred to the lobby, the leader is notified, and the users then wait until a leader either accepts or rejects them or their connection times out. While in the lobby, the users hear music. 

De forma predeterminada, los participantes que llaman desde la PSTN pasan directamente a la reunión, pero esta opción se puede cambiar para obligarlos a ir a la sala de espera.  
Meeting organizers control whether participants can join a meeting without waiting in the lobby. Each meeting can be set up to enable access using any one of the following methods:
- **Solo yo, el organizador de la reunión**&nbsp;&nbsp;Todos, excepto el organizador, deben aguardar en la sala de espera hasta a ser admitidos.
- **Personas a las que invito de mi empresa**&nbsp;&nbsp;Cualquier persona de su empresa puede entrar a la reunión directamente, incluso si no está invitado.
- **Anyone from my organization**&nbsp;&nbsp;All SfBO users in the O365 tenant can join the meeting without waiting in the lobby, even if those who are not on the distribution list. All others, including all external and anonymous users, must wait in the lobby until admitted.
- **Anyone**&nbsp;&nbsp;Anyone (there are no restrictions)who has access to the meeting link gets in to the meeting directly. When any method except Organizer only (locked) is specified, the meeting organizer can also specify People dialing in by phone bypass the lobby. 

### <a name="presenter-capabilities"></a>Capacidades del presentador
Meeting organizers control whether participants can present during a meeting. Each meeting can be set up to limit presenters to any one of the following:
- **Solo organizador**&nbsp;&nbsp; Solo el organizador de la reunión puede presentar.
- **Gente de mi empresa**&nbsp;&nbsp; Todos los usuarios internos pueden presentar.
- **Todas las personas, incluidas las de fuera de mi empresa**&nbsp;&nbsp; Todas las personas (sin restricciones) que se unan a la reunión pueden presentar.
- **La gente que yo invite**&nbsp;&nbsp;El organizador de la reunión especifica qué usuarios pueden presentar agregándolos a una lista de presentadores.

## <a name="related-topics"></a>Temas relacionados
[Centro de confianza de Office 365](https://products.office.com/en-us/business/office-365-trust-center-security)

