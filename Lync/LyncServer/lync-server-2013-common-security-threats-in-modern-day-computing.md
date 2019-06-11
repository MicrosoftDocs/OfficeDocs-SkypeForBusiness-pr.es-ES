---
title: 'Lync Server 2013: amenazas de seguridad comunes en los equipos informáticos modernos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Common security threats in modern day computing
ms:assetid: 56d22197-e8e2-46b8-b3a3-507bd663700e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn433220(v=OCS.15)
ms:contentKeyID: 56708403
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e32d62cef3870e7134a628e0d5cedf20bb16200a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842543"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="common-security-threats-in-modern-day-computing"></a><span data-ttu-id="e9402-102">Amenazas de seguridad comunes en la informática moderna</span><span class="sxs-lookup"><span data-stu-id="e9402-102">Common security threats in modern day computing</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e9402-103">_**Última modificación del tema:** 2013-09-10_</span><span class="sxs-lookup"><span data-stu-id="e9402-103">_**Topic Last Modified:** 2013-09-10_</span></span>

<span data-ttu-id="e9402-104">Puesto que Lync Server 2013 es un sistema de comunicaciones de clase empresarial, debe tener en cuenta los ataques de seguridad comunes que podrían afectar a su infraestructura y sus comunicaciones.</span><span class="sxs-lookup"><span data-stu-id="e9402-104">Because Lync Server 2013 is an enterprise-class communications system, you should be aware of common security attacks that could affect its infrastructure and communications.</span></span>

<div>

## <a name="compromised-key-attack"></a><span data-ttu-id="e9402-105">Ataque de clave comprometida</span><span class="sxs-lookup"><span data-stu-id="e9402-105">Compromised-Key Attack</span></span>

<span data-ttu-id="e9402-p101">Una clave es un código o número secreto que se usa para cifrar, descifrar o comprobar información secreta. Hay dos claves confidenciales en uso en la infraestructura de claves públicas (PKI) que deben tenerse en cuenta:</span><span class="sxs-lookup"><span data-stu-id="e9402-p101">A key is a secret code or number that is used to encrypt, decrypt, or validate secret information. There are two sensitive keys in use in public key infrastructure (PKI) that must be considered: .</span></span>

  - <span data-ttu-id="e9402-108">La clave privada que tiene cada titular de un certificado</span><span class="sxs-lookup"><span data-stu-id="e9402-108">The private key that each certificate holder has</span></span>

  - <span data-ttu-id="e9402-109">La clave de sesión que se utiliza después de realizarse correctamente la identificación y el intercambio de las claves de sesión por parte de las entidades de comunicación</span><span class="sxs-lookup"><span data-stu-id="e9402-109">The session key that is used after a successful identification and session key exchange by the communicating partners</span></span>

<span data-ttu-id="e9402-p102">Un ataque de clave comprometida se produce cuando el atacante consigue la clave privada o de sesión. Cuando el atacante consigue la clave, puede usarla para descifrar datos cifrados sin que el remitente lo sepa.</span><span class="sxs-lookup"><span data-stu-id="e9402-p102">A compromised-key attack occurs when the attacker determines the private key or the session key. When the attacker is successful in determining the key, the attacker can use the key to decrypt encrypted data without the knowledge of the sender.</span></span>

<span data-ttu-id="e9402-112">Lync Server 2013 usa las características de PKI del sistema operativo Windows Server para proteger los datos clave usados para el cifrado de las conexiones de seguridad de la capa de transporte (TLS).</span><span class="sxs-lookup"><span data-stu-id="e9402-112">Lync Server 2013 uses the PKI features in the Windows Server operating system to protect the key data used for encryption for the Transport Layer Security (TLS) connections.</span></span> <span data-ttu-id="e9402-113">Las claves que se usan para cifrar medios se intercambian en las conexiones TLS.</span><span class="sxs-lookup"><span data-stu-id="e9402-113">The keys used for media encryption are exchanged over TLS connections.</span></span>

</div>

<div>

## <a name="network-denial-of-service-attack"></a><span data-ttu-id="e9402-114">Ataque por denegación de servicio de la red</span><span class="sxs-lookup"><span data-stu-id="e9402-114">Network Denial-of-Service Attack</span></span>

<span data-ttu-id="e9402-p104">El *ataque por denegación de servicio* se produce cuando el atacante impide que los usuarios válidos usen la red de forma normal. Esto se realiza cuando el atacante inunda el servicio con solicitudes legítimas que sobrepasan el uso del servicio por parte de los usuarios legítimos. Con un ataque por denegación de servicio, el atacante puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e9402-p104">The *denial-of-service attack* occurs when the attacker prevents normal network use and function by valid users. This is done when the attacker floods the service with legitimate requests that overwhelm the use of the service by legitimate users. By using a denial-of-service attack, the attacker can do the following:</span></span>

  - <span data-ttu-id="e9402-118">Enviar datos no válidos a las aplicaciones y los servicios que se ejecutan en la red que sufre el ataque para interrumpir su funcionamiento normal.</span><span class="sxs-lookup"><span data-stu-id="e9402-118">Send invalid data to applications and services running in the attacked network to disrupt their normal function.</span></span>

  - <span data-ttu-id="e9402-119">Enviar una gran cantidad de tráfico, lo que sobrecarga el sistema hasta que deja de responder o responde lentamente a las solicitudes legítimas.</span><span class="sxs-lookup"><span data-stu-id="e9402-119">Send a large amount of traffic, overloading the system until it stops responding or responds slowly to legitimate requests.</span></span>

  - <span data-ttu-id="e9402-120">Ocultar las pruebas de los ataques.</span><span class="sxs-lookup"><span data-stu-id="e9402-120">Hide the evidence of the attacks.</span></span>

  - <span data-ttu-id="e9402-121">Impedir que los usuarios obtengan acceso a los recursos de la red.</span><span class="sxs-lookup"><span data-stu-id="e9402-121">Prevent users from accessing network resources.</span></span>

</div>

<div>

## <a name="eavesdropping-sniffing-snooping"></a><span data-ttu-id="e9402-122">Interceptación (rastreo o espionaje)</span><span class="sxs-lookup"><span data-stu-id="e9402-122">Eavesdropping (Sniffing, Snooping)</span></span>

<span data-ttu-id="e9402-p105">La *interceptación* se produce cuando un atacante obtiene acceso a la ruta de datos en una red y puede supervisar y leer el tráfico. Este tipo de ataque también se denomina *rastreo* o *espionaje*. Si el tráfico se produce como texto sin formato, el atacante puede leerlo cuando obtiene acceso a la ruta. Un ejemplo es un ataque que se realiza al controlar un enrutador de la ruta de acceso a los datos.</span><span class="sxs-lookup"><span data-stu-id="e9402-p105">*Eavesdropping* can occur when an attacker gains access to the data path in a network and has the ability to monitor and read the traffic. This is also called *sniffing* or *snooping*. If the traffic is in plain text, the attacker can read the traffic when the attacker gains access to the path. An example is an attack performed by controlling a router on the data path.</span></span>

<span data-ttu-id="e9402-127">La recomendación predeterminada y la configuración para el tráfico dentro de Microsoft Lync Server 2013 es usar TLS Mutual (MTLS) entre los servidores de confianza y TLS del cliente al servidor.</span><span class="sxs-lookup"><span data-stu-id="e9402-127">The default recommendation and setting for traffic within Microsoft Lync Server 2013 is to use mutual TLS (MTLS) between trusted servers and TLS from client to server.</span></span> <span data-ttu-id="e9402-128">Esta medida de protección haría extremadamente difícil o imposible de realizar un ataque en el período en que tiene lugar conversación concreta.</span><span class="sxs-lookup"><span data-stu-id="e9402-128">This protective measure would make an attack very difficult or impossible to achieve within the time period in which a given conversation occurs.</span></span> <span data-ttu-id="e9402-129">TLS autentica a todos los participantes y cifra todo el tráfico.</span><span class="sxs-lookup"><span data-stu-id="e9402-129">TLS authenticates all parties and encrypts all traffic.</span></span> <span data-ttu-id="e9402-130">Esto no impide la interceptación, pero el atacante no puede leer el tráfico a menos se interrumpa el cifrado.</span><span class="sxs-lookup"><span data-stu-id="e9402-130">This does not prevent eavesdropping, but the attacker cannot read the traffic unless the encryption is broken.</span></span>

<span data-ttu-id="e9402-p107">El protocolo NAT transversal con relé (TURN) no impone el cifrado del tráfico, y la información que envía está protegida por la integridad del mensaje. Si bien este protocolo está abierto a la interceptación, la información que envía (es decir, direcciones IP y puerto) se puede extraer directamente examinando simplemente las direcciones de origen y de destino de los paquetes. El servicio perimetral A/V se asegura de que los datos son válidos comprobando la integridad del mensaje mediante la clave derivada de algunos elementos, como una contraseña TURN, la cual no se envía nunca en texto no cifrado. Si se utiliza Protocolo en tiempo real seguro (SRTP), también se cifra el tráfico de medios.</span><span class="sxs-lookup"><span data-stu-id="e9402-p107">The Traversal Using Relay NAT (TURN) protocol does not mandate the traffic to be encrypted and the information that it is sending is protected by message integrity. Although it is open to eavesdropping, the information it is sending (that is, the IP addresses and port) can be extracted directly by simply looking at the source and destination addresses of the packets. The A/V Edge service ensures that the data is valid by checking the Message Integrity of the message by using the key derived from a few items, including a TURN password, which is never sent in clear text. If Secure Real Time Protocol (SRTP) is used, media traffic is also encrypted.</span></span>

</div>

<div>

## <a name="identity-spoofing-ip-address-spoofing"></a><span data-ttu-id="e9402-135">Suplantación de identidad (suplantación de dirección IP)</span><span class="sxs-lookup"><span data-stu-id="e9402-135">Identity Spoofing (IP Address Spoofing)</span></span>

<span data-ttu-id="e9402-136">La *suplantación de identidad (spoofing)* se produce cuando el atacante identifica y usa una dirección IP de una red, un equipo o un componente de red sin tener autorización para ello.</span><span class="sxs-lookup"><span data-stu-id="e9402-136">*Spoofing* occurs when the attacker determines and uses an IP address of a network, computer, or network component without being authorized to do so.</span></span> <span data-ttu-id="e9402-137">En este tipo de ataque, el atacante actúa como si fuese la entidad que hubiera identificado la dirección IP en un caso normal.</span><span class="sxs-lookup"><span data-stu-id="e9402-137">A successful attack allows the attacker to operate as if the attacker is the entity normally identified by the IP address.</span></span> <span data-ttu-id="e9402-138">En el contexto de Microsoft Lync Server 2013, esta situación entra en juego solo si un administrador ha realizado las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="e9402-138">Within the context of Microsoft Lync Server 2013, this situation comes into play only if an administrator has done both of the following:</span></span>

  - <span data-ttu-id="e9402-139">Ha configurado conexiones compatibles únicamente con el Protocolo de control de transmisión (TCP) (lo cual no se recomienda porque las comunicaciones TCP no están cifradas).</span><span class="sxs-lookup"><span data-stu-id="e9402-139">Configured connections that support only Transmission Control Protocol (TCP) (which is not recommended, because TCP communications are unencrypted).</span></span>

  - <span data-ttu-id="e9402-140">Ha marcado las direcciones IP de esas conexiones como hosts de confianza.</span><span class="sxs-lookup"><span data-stu-id="e9402-140">Marked the IP addresses of those connections as trusted hosts.</span></span>

<span data-ttu-id="e9402-141">Este es un problema menor para las conexiones TLS (Seguridad de la capa de transporte), puesto que TLS autentica todas las partes y cifra todo el tráfico.</span><span class="sxs-lookup"><span data-stu-id="e9402-141">This is less of a problem for Transport Layer Security (TLS) connections, as TLS authenticates all parties and encrypts all traffic.</span></span> <span data-ttu-id="e9402-142">El uso de TLS evita que un atacante suplante las direcciones IP en una conexión concreta (por ejemplo, conexiones Mutual TLS).</span><span class="sxs-lookup"><span data-stu-id="e9402-142">Using TLS prevents an attacker from performing IP address spoofing on a specific connection (for example, mutual TLS connections).</span></span> <span data-ttu-id="e9402-143">Pero un atacante podría suplantar la dirección del servidor DNS que usa Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e9402-143">But an attacker could still spoof the address of the DNS server that Lync Server 2013 uses.</span></span> <span data-ttu-id="e9402-144">Sin embargo, como la autenticación en Lync se realiza con certificados, un atacante no tendría un certificado válido necesario para suplantar a una de las partes de la comunicación.</span><span class="sxs-lookup"><span data-stu-id="e9402-144">However, because authentication in Lync is performed with certificates, an attacker would not have a valid certificate required to spoof one of the parties in the communication.</span></span>

</div>

<div>

## <a name="man-in-the-middle-attack"></a><span data-ttu-id="e9402-145">Ataque de tipo "Man in the middle"</span><span class="sxs-lookup"><span data-stu-id="e9402-145">Man-in-the-Middle Attack</span></span>

<span data-ttu-id="e9402-146">Un ataque de tipo "Man in the middle" se produce cuando un atacante desvía la comunicación entre dos usuarios a través del equipo del atacante sin que lo sepan esos dos usuarios.</span><span class="sxs-lookup"><span data-stu-id="e9402-146">A man-in-the-middle attack occurs when an attacker reroutes communication between two users through the attacker’s computer without the knowledge of the two communicating users.</span></span> <span data-ttu-id="e9402-147">El atacante puede supervisar y leer el tráfico antes de enviarlo al destinatario previsto.</span><span class="sxs-lookup"><span data-stu-id="e9402-147">The attacker can monitor and read the traffic before sending it on to the intended recipient.</span></span> <span data-ttu-id="e9402-148">Sin darse cuenta, todos los usuarios que participan en la comunicación envían tráfico al atacante y reciben tráfico del mismo pensando que la comunicación se produce únicamente con el usuario previsto.</span><span class="sxs-lookup"><span data-stu-id="e9402-148">Each user in the communication unknowingly sends traffic to and receives traffic from the attacker, all while thinking they are communicating only with the intended user.</span></span> <span data-ttu-id="e9402-149">Esto puede suceder si un atacante modifica los Servicios de dominio de Active Directory para agregar su servidor como un servidor de confianza o modifica el Sistema de nombres de dominio (DNS) para que los clientes se conecten al servidor a través del atacante.</span><span class="sxs-lookup"><span data-stu-id="e9402-149">This can happen if an attacker can modify Active Directory Domain Services to add his or her server as a trusted server or modify Domain Name System (DNS) to get clients to connect through the attacker on their way to the server.</span></span> <span data-ttu-id="e9402-150">Un ataque de tipo "Man in the middle" también puede producirse con tráfico multimedia entre dos clientes.</span><span class="sxs-lookup"><span data-stu-id="e9402-150">A man-in-the-middle attack can also occur with media traffic between two clients.</span></span> <span data-ttu-id="e9402-151">Sin embargo, en Microsoft Lync Server 2013, el audio, el vídeo y el uso compartido de aplicaciones punto a punto se cifran con SRTP, usando claves criptográficas que se negocian entre los interlocutores que usan el protocolo de inicio de sesión (SIP) a través de TLS.</span><span class="sxs-lookup"><span data-stu-id="e9402-151">However, in Microsoft Lync Server 2013 point-to-point audio, video, and application sharing, streams are encrypted with SRTP, using cryptographic keys that are negotiated between the peers that are using Session Initiation Protocol (SIP) over TLS.</span></span> <span data-ttu-id="e9402-152">Los servidores como los de conversaciones en grupo utilizan HTTPS para mejorar la seguridad del tráfico web.</span><span class="sxs-lookup"><span data-stu-id="e9402-152">Servers such as Group Chat make use of HTTPS to enhance the security of web traffic.</span></span>

</div>

<div>

## <a name="rtp-replay-attack"></a><span data-ttu-id="e9402-153">Ataque de reproducción RTP</span><span class="sxs-lookup"><span data-stu-id="e9402-153">RTP Replay Attack</span></span>

<span data-ttu-id="e9402-p111">Un *ataque de reproducción* tiene lugar cuando una transmisión de medios válida entre dos partes se intercepta y retransmite con fines malintencionados. SRTP, usado en conexión con un protocolo de señalización segura, protege las transmisiones de estos ataques al permitir que el receptor tenga un índice de los paquetes RTP ya recibidos y pueda comparar cada paquete nuevo con los que figuran en dicho índice.</span><span class="sxs-lookup"><span data-stu-id="e9402-p111">A *replay attack* occurs when a valid media transmission between two parties is intercepted and retransmitted for malicious purposes. SRTP used in connection with a secure signaling protocol protects transmissions from replay attacks by enabling the receiver to maintain an index of already received RTP packets and compare each new packet with those already listed in the index.</span></span>

</div>

<div>

## <a name="spim"></a><span data-ttu-id="e9402-156">Mensajes instantáneos no deseados</span><span class="sxs-lookup"><span data-stu-id="e9402-156">Spim</span></span>

<span data-ttu-id="e9402-p112">El término inglés "*spim*" hace referencia a los mensajes instantáneos comerciales no deseados o a las solicitudes de suscripción de presencia no deseadas. Si bien estos mensajes por sí mismos no son un peligro para la seguridad de la red, son como mínimo molestos, pueden reducir la disponibilidad y la productividad de los recursos, y podrían llegar a poner en peligro la red. Un ejemplo de ello es el caso de usuarios que se envían solicitudes no deseadas entre sí. Los usuarios pueden bloquearse entre sí para evitarlo, pero con la federación, si se establece un ataque coordinado de este tipo, puede ser difícil de solucionar a menos que se deshabilite la federación para el asociado.</span><span class="sxs-lookup"><span data-stu-id="e9402-p112">*Spim* is unsolicited commercial instant messages or presence subscription requests. While not by itself a compromise of the network, it is annoying in the least, can reduce resource availability and production, and can possibly lead to a compromise of the network. An example of this is users spimming each other by sending requests. Users can block each other to prevent this, but with federation, if a coordinated spim attack is established, this can be difficult to overcome unless you disable federation for the partner.</span></span>

</div>

<div>

## <a name="viruses-and-worms"></a><span data-ttu-id="e9402-161">Virus y gusanos</span><span class="sxs-lookup"><span data-stu-id="e9402-161">Viruses and Worms</span></span>

<span data-ttu-id="e9402-p113">Un *virus* es una unidad de código que tiene por objeto reproducir más unidades de código similares. Los virus necesitan un host, como un archivo, un correo electrónico o un programa, para poder funcionar. Un *gusano* es una unidad de código cuyo propósito es reproducir más unidades de código similares, pero no necesita un host. Los virus y los gusanos suelen aparecer principalmente durante las transferencias de archivo entre clientes o cuando otros usuarios envían direcciones URL. Si hay un virus en su equipo, podrá, por ejemplo, usar su identidad y enviar mensajes instantáneos en su nombre.</span><span class="sxs-lookup"><span data-stu-id="e9402-p113">A *virus* is a unit of code whose purpose is to reproduce additional, similar code units. To work, a virus needs a host, such as a file, email, or program. A *worm* is a unit of code whose purpose is to reproduce additional, similar code units, but it does not need a host. Viruses and worms primarily show up during file transfers between clients or when URLs are sent from other users. If a virus is on your computer, it can, for example, use your identity and send instant messages on your behalf.</span></span>

</div>

<div>

## <a name="personally-identifiable-information"></a><span data-ttu-id="e9402-167">Información de identificación personal</span><span class="sxs-lookup"><span data-stu-id="e9402-167">Personally Identifiable Information</span></span>

<span data-ttu-id="e9402-168">Microsoft Lync Server 2013 tiene el potencial de divulgar información a través de una red pública que pueda vincularse a una persona.</span><span class="sxs-lookup"><span data-stu-id="e9402-168">Microsoft Lync Server 2013 has the potential to disclose information over a public network that might be able to be linked to an individual.</span></span> <span data-ttu-id="e9402-169">Dicha información se puede desglosar en dos categorías:</span><span class="sxs-lookup"><span data-stu-id="e9402-169">The information types can be broken down to two specific categories:</span></span>

  - <span data-ttu-id="e9402-170">**Datos de presencia mejorados ** Los datos de presencia mejorados son información que un usuario puede elegir para compartir o no a través de un vínculo a un socio federado o con los contactos de una organización.</span><span class="sxs-lookup"><span data-stu-id="e9402-170">**Enhanced presence data ** Enhanced presence data is information that a user can choose to share or not share over a link to a federated partner or with contacts within an organization.</span></span> <span data-ttu-id="e9402-171">Estos datos no se comparten con los usuarios de una red de mensajería instantánea pública.</span><span class="sxs-lookup"><span data-stu-id="e9402-171">This data is not shared with users on a public IM network.</span></span> <span data-ttu-id="e9402-172">Las directivas de cliente y otras opciones de configuración del cliente pueden otorgar algún tipo de control al administrador del sistema.</span><span class="sxs-lookup"><span data-stu-id="e9402-172">Client policies and other client configuration may put some control with the system administrator.</span></span> <span data-ttu-id="e9402-173">En Lync Server 2013, el modo de privacidad de presencia mejorada se puede configurar para que un usuario individual Evite que los usuarios de Lync que no estén en la lista de contactos del usuario vean la información de presencia del usuario.</span><span class="sxs-lookup"><span data-stu-id="e9402-173">In Lync Server 2013, enhanced presence privacy mode can be configured for an individual user to prevent Lync users not on the user’s Contacts list from seeing the user’s presence information.</span></span> <span data-ttu-id="e9402-174">El modo de privacidad de presencia mejorada no impide que los usuarios de  Microsoft Office Communicator 2007 y Microsoft Office Communicator 2007 R2 vean la información de presencia de un usuario.</span><span class="sxs-lookup"><span data-stu-id="e9402-174">Enhanced presence privacy mode does not prevent users of Microsoft Office Communicator 2007 and Microsoft Office Communicator 2007 R2 from seeing a user’s presence information.</span></span> <span data-ttu-id="e9402-175">Para obtener más información, consulte [novedades para clientes en Lync server 2013](lync-server-2013-what-s-new-for-clients.md) en la documentación de introducción y [configuración del modo de privacidad de presencia mejorada en Lync Server 2013](lync-server-2013-configuring-enhanced-presence-privacy-mode.md) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="e9402-175">For details, see [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md) in the Getting Started documentation and [Configuring enhanced presence privacy mode in Lync Server 2013](lync-server-2013-configuring-enhanced-presence-privacy-mode.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="e9402-176">**Datos obligatorios** Los datos obligatorios son obligatorios para que el servidor o el cliente funcionen correctamente y no están bajo el control de la administración del cliente o del sistema.</span><span class="sxs-lookup"><span data-stu-id="e9402-176">**Mandatory data** Mandatory data is required for the proper operation of the server or the client and is NOT under the control of the client or system administration.</span></span> <span data-ttu-id="e9402-177">Se trata de información que es necesaria en un servidor o una red para el enrutamiento, el mantenimiento de estados y la señalización.</span><span class="sxs-lookup"><span data-stu-id="e9402-177">This is information that is necessary at a server or network level for the purposes of routing, state maintenance, and signaling.</span></span>

<span data-ttu-id="e9402-178">En las tablas siguientes, se muestran los datos que se exponen sobre una red pública.</span><span class="sxs-lookup"><span data-stu-id="e9402-178">The following tables list the data that is exposed over a public network.</span></span>

### <a name="enhanced-presence-data"></a><span data-ttu-id="e9402-179">Datos de presencia ampliada</span><span class="sxs-lookup"><span data-stu-id="e9402-179">Enhanced Presence Data</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e9402-180">Datos que se divulgan</span><span class="sxs-lookup"><span data-stu-id="e9402-180">Data Disclosed</span></span></th>
<th><span data-ttu-id="e9402-181">Posibles configuraciones</span><span class="sxs-lookup"><span data-stu-id="e9402-181">Possible Settings</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e9402-182">Datos personales</span><span class="sxs-lookup"><span data-stu-id="e9402-182">Personal Data</span></span></p></td>
<td><p><span data-ttu-id="e9402-183">Nombre, Puesto, Compañía, Dirección de correo electrónico, Zona horaria</span><span class="sxs-lookup"><span data-stu-id="e9402-183">Name, Title, Company, Email Address, Time Zone</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9402-184">Números de teléfono</span><span class="sxs-lookup"><span data-stu-id="e9402-184">Telephone Numbers</span></span></p></td>
<td><p><span data-ttu-id="e9402-185">Trabajo, Móvil, Particular</span><span class="sxs-lookup"><span data-stu-id="e9402-185">Work, Mobile, Home</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9402-186">Información de calendario</span><span class="sxs-lookup"><span data-stu-id="e9402-186">Calendar Information</span></span></p></td>
<td><p><span data-ttu-id="e9402-187">Información de disponibilidad, aviso de fuera de la oficina, detalles de las reuniones (para las personas con acceso a su calendario)</span><span class="sxs-lookup"><span data-stu-id="e9402-187">Free/Busy, Out-Of-Town Notice, Meeting Details (to those who have access to your calendar)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9402-188">Estado de presencia</span><span class="sxs-lookup"><span data-stu-id="e9402-188">Presence Status</span></span></p></td>
<td><p><span data-ttu-id="e9402-189">Ausente, Disponible, No disponible, No molestar, No conectado</span><span class="sxs-lookup"><span data-stu-id="e9402-189">Away, Available, Busy, Do Not Disturb, Offline</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="mandatory-data"></a><span data-ttu-id="e9402-190">Datos obligatorios</span><span class="sxs-lookup"><span data-stu-id="e9402-190">Mandatory Data</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e9402-191">Datos que se divulgan</span><span class="sxs-lookup"><span data-stu-id="e9402-191">Data Disclosed</span></span></th>
<th><span data-ttu-id="e9402-192">Información de ejemplo</span><span class="sxs-lookup"><span data-stu-id="e9402-192">Example Information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e9402-193">Dirección IP</span><span class="sxs-lookup"><span data-stu-id="e9402-193">IP Address</span></span></p></td>
<td><p><span data-ttu-id="e9402-194">Dirección real del equipo o dirección traducida</span><span class="sxs-lookup"><span data-stu-id="e9402-194">Actual address of computer or NATed address</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9402-195">URI del SIP</span><span class="sxs-lookup"><span data-stu-id="e9402-195">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="e9402-196">jeremylos@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="e9402-196">jeremylos@litwareinc.com</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

